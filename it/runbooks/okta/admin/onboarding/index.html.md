---
layout: handbook-page-toc
title: "Okta Admin Onboarding"
description: "The Okta Admin Onboarding runbook provides setup instructions for team members that have a separate admin account in Okta, Google Workspace, and 1Password."
---

## On this page
{:.no_toc}

- TOC
{:toc}

## Overview

The Okta Admin Onboarding runbook provides setup instructions for team members that have been provisioned a BLACK admin account to get started with setting up Okta, Google Workspace, and 1Password that is configured separately from your PURPLE accounts.

- **Provisioner Time to Complete:** 15 Minutes (not including approvals)  
- **User Time to Complete:** 30 Minutes Assisted Sync or 45 Minutes Async
- **Who Can Provision:** IT Systems Engineer
- **Runbook DRI:** [Jeff Martin](https://gitlab.com/jeffersonmartin)

## Step 0: Provisioner Pre-Work

This configuration is managed by Terraform in the `okta-iac` repository. A new issue and MR should be created in this repository and merged prior to the provisioning call.

### Provisioner Task 0.1: Terraform User Account Data Source

1. See `[okta-iac]/terraform/okta_admin_groups.auto.tfvars.json` for a list of the latest groups. The following list is provided as a reference and may not be up-to-date.
    - `audit_compliance`
    - `it_analyst`
    - `it_eng`
    - `it_security`
    - `sirt`

2. Create a new issue using the `okta_admin_user_add` issue template. Follow the instructions in the issue template which includes change management steps for creating the branch and MR.

2. Use the GitLab Web IDE in the branch to add a new row to `[okta-iac]/terraform/okta_admin_users.auto.tfvars.json`. All rows are in alphabetical order.

    ```
    "{firstInitial}{lastName}": {"first_name": "{firstName}", "last_name": "{lastName}", "group": "{group}"},
    ```

    ```json
    "dmurphy": {"first_name": "Dade", "last_name": "Murphy", "group": "audit_compliance"},
    ```

3. Commit the changes and assign the MR to IT Engineering (ex. `@jeffersonmartin`) for approval, merge, and `terraform apply`.

### Provisioner Task 0.2: Terraform Provisioning Sequence

> TODO: This runbook provides steps using the Terminal. This needs to be re-written using CI/CD pipelines.

1. Initialize the Terraform configuration.

    ```bash
    terraform init
    ```

2. Run Terraform plan and check the outputs. Ensure that only the specified user is being changed. Any other changes need to be reviewed by Jeff Martin prior to running `terraform apply`.

    ```bash
    terraform plan -target=okta_user.admin_user
    ```

    ```
    Terraform will perform the following actions:

    # okta_user.admin_user["dmurphy"] will be created
    + resource "okta_user" "admin_user" {
        + display_name              = "Dade Murphy (Admin)"
        + email                     = "dmurphy-admin@gitlab.com"
        + expire_password_on_create = false
        + first_name                = "Dade"
        + id                        = (known after apply)
        + last_name                 = "Murphy (Admin)"
        + login                     = "dmurphy-admin@gitlab.com"
        + organization              = "GitLab"
        + raw_status                = (known after apply)
        + skip_roles                = true
        + status                    = "ACTIVE"
        + user_type                 = "Admin"
        }

    Plan: 1 to add, 0 to change, 0 to destroy.
    ```

3. If plan review looks good, apply the changes for creating the user.

    ```bash
    terraform apply -target=okta_user.admin_user
    ```

4. Add the user to the admin groups and create the Google Workspace account.

    ```bash
    terraform apply -target=okta_user_group_memberships.admin_user_group_membership
    ```

5. Use the [Google Workspace admin console](https://admin.google.com/ac/users) to verify that the user's email address exists (ex. Email starts with `dmurphy-admin`). This may take a few minutes with SCIM provisioning so wait until this appears before proceeding.

6. Add the user to the 1Password workflow provisioning Okta group.

    ```bash
    terraform apply -target=okta_user_group_memberships.admin_user_group_onepassword
    ```

7. All Terraform tasks are now completed.

### Provisioner Task 0.3: Okta Temporary Password

1. Create a **new 1Password record** in your `AR Temp Credentials` vault named `Okta Temp Admin - {firstInitial}{lastName}-admin@gitlab.com`.
2. Set the 1Password record **username** to `{firstInitial}{lastName}-admin@gitlab.com`.
3. Set the 1Password record **website** to `https://gitlab.okta.com`.
4. **Open Chrome** and choose your **Admin** profile.
5. Sign in to `https://gitlab.okta.com` and navigate to [Directory > People](https://gitlab-admin.okta.com/admin/users).
6. Search for the user (`{firstInitial}{lastName}-admin`) and click on the user's name to navigate to their profile.
7. Click the **Set Password & Activate** button to open the popup modal and click the **Set Password & Activate** button to confirm. If you have already performed a temporary activation, click the **Resend Password Email** button and click the **Create temporary password** button in the popup modal window.
    <img style="width: 500px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_0_3_7.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_0_3_7.png" />
8. **Copy the temporary password displayed** in the browser into the 1Password record **password** field.
9. On the Zoom assisted onboarding or migration call, right click on the 1Password record and choose **Share**.
    <img style="width: 400px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_0_3_9.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_0_3_9.png" />
10. Provide the share link via Slack DM or Zoom chat. 
    > This is ephemeral for 60 minutes and the password is about to be changed so there is not a security risk with how you share it. 

---

## Step 1: Okta Account Activation

### Task 1.1: Copy 1Password Temporary Credentials to Vault

1. Open the 1Password share link that the provisioner provided you in the Slack DM.
    1. If you are not signed into 1Password, you will 
2. Copy the 1Password record to your `Private` vault.
3. Open 1Password application and have this record available to quickly edit.

### Task 1.2: Open a Chrome Incognito Browser Window

> Until we have a Chrome Profile set up with your new email account, we will perform the next few tasks using an incognito browser window to avoid interfering with your existing Okta account.

1. Open **Google Chrome**.
2. Press **Cmd+Shift+N** to open a new incognito browser window.

### Task 1.3: Sign in to Okta with temporary password

> These steps should be performed in a Chrome incognito browser window.

1. Open the 1Password record for your temporary credentials to allow you to easily copy the password.
2. Copy and paste `https://gitlab.okta.com` into the URL bar of your incognito browser window.
3. Use your new credentials:
    1. Username: `{firstInitial}{lastName}-admin@gitlab.com`
    2. Password: (copy from 1Password record)
        <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_1_3_3.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_1_3_3.png" />

### Task 1.4: Change Password

1. You will be prompted that `Your Okta password has expired`.
2. Edit the 1Password record and generate a new password with 64 characters (maximum length in 1Password Web UI). Click **Save**.  
    <img style="width: 300px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_1_4_2.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_1_4_2.png" />
3. Copy the generated password into the browser in the **New password** and **Re-enter password** fields.
4. Click **Change Password**.

### Task 1.5: Set up MFA with YubiKey 5 FIPS

> Our Okta admin account policies require `YubiKey 5 FIPS` models that are verified by IT Engineering behind-the-scenes. There is no way to restrict these models in the Okta configuration, so please be sure not to enroll your Mac Touch ID or other WebAuthn factors. You will be contacted by IT if any of your factors are not allowed and were removed administratively.

1. You will be prompted to `Set up security methods`.
2. Click the **Set up** button for `Security Key or Biometric Authenticator`.
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_1_5_2.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_1_5_2.png" />
3. On the popup prompt, select **USB security key**.
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_1_5_3.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_1_5_3.png" />
4. Touch your YubiKey to activate MFA.
5. You will be redirected to the Okta user dashboard for your new account.
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_1_5_5.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_1_5_5.png" />
   
---

## Step 2: Google Account Activation

### Task 2.1: Configure your Google Account Profile Picture

1. On the Okta user dashboard for your new account, click the `G Suite SSO Account` tile.
2. On the `Welcome to your new account` screen with the terms and conditions, click the **I understand** button.
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_1_2.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_1_2.png" />
3. You will be redirected to the Google Account homepage.
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_1_3.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_1_3.png" />
4. Click the **Personal Info** link in the left navigation.
5. Click the **Photo** icon to upload an avatar. If you don't have a picture readily available, navigate to `https://gitlab.com/{username}` and right click on your avatar and choose **Save image as** to save it to your desktop.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_1_5.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_1_5.png" />

### Task 2.2: Configure Google Account 2FA

1. Click the **Security** link in the left navigation.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_2_1.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_2_1.png" /> 
2. In the `Signing in to Google` section, click the **2-Step Verification** row.
3. In the prompt, click the **GET STARTED** button.
4. Ignore the phone number instructions and click the **Show more options** link in the bottom left corner, then click **Security Key**.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_2_4.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_2_4.png" />
5. When prompted for `Have your security key?`, click the **NEXT** button. You can ignore the instructions for `Make sure your key is with you, but not connected to your device`. You can leave your YubiKey inserted.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_2_5.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_2_5.png" />
6. When prompted, **touch your YubiKey**.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_2_6.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_2_6.png" />
7. After your Security Key has been registered, you will be prompted to **assign a name** to the YubiKey. This is at your discretion, however the model number is a best practice (ex. `YubiKey 5C FIPS`).  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_2_7.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_2_7.png" />
8. After your key has been enrolled, your Google Account activation is complete.
9. **Close the incognito browser window**.

### Task 2.3: Create Google Chrome Profile

1. Using your **normal** Google Chrome browser window (not in incognito mode), **click on your avatar in the top right corner**, then click the **Add** button below the `Other Profiles` section.  
    <img style="width: 250px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_1.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_1.png" />
2. When prompted to `Set up your new Chrome profile`, click the **Sign in** button.  
    <img style="width: 600px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_2.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_2.png" />
3. When prompted to `Sign in to Chrome`, enter your admin email address (ex. `dmurphy-admin@gitlab.com`).  
    <img style="width: 600px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_3.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_3.png" />
4. You will be redirected to Okta to sign in with your `dmurphy-admin@gitlab.com` credentials. **Copy the password from the 1Password record**.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_4.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_4.png" />
5. Remember that we never save passwords in Chrome. You can click the **Never** button.  
6. When prompted to verify your identity, click the **USB security key** option.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_6.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_6.png" />
7. You will be prompted by Google to verify it's you. Click the **Continue** button.  
    <img style="width: 350px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_7.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_7.png" />
8. You will be prompted that `Your organization will manage this profile`. Click the **Continue** button.  
    <img style="width: 450px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_8.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_8.png" />
9. When prompted to `Turn on sync?`, click the **Settings** button.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_9.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_9.png" />
10. Click the **Manage what you sync** section.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_10.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_10.png" />
11. Change the `Sync everything` to `Customize sync`, then **uncheck** the `Passwords` toggle.  
12. Click the arrow to the left of `Manage what you sync` to return back to the main configuration screen.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_12.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_12.png" />
13. To the right of your name, click the **Confirm** button.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_13.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_13.png" />
14. Click the **Customize your Chrome profile** row.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_14.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_14.png" />
15. Set the **name** to `GitLab Admin (Black)` and choose a **theme color** (ex. Black). This name refers to the PURPLE vs BLACK wristband access levels.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_15.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_15.png" />
16. You can verify your Chrome profile in the top right corner by clicking on your avatar. You can switch between profiles as needed.  
    <img style="width: 350px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_3_16.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_3_16.png" />

### Task 2.4: Add bookmarks for Okta and Gmail

1. In your Chrome browser window with your `GitLab Admin (Black)` profile selected, press **Cmd+Shift+B** to show the bookmarks menu bar.
2. Navigate to `https://gitlab.okta.com` and sign in with your `{handle}-admin@gitlab.com` account using the credentials stored in 1Password. You will be prompted to verify your identity with USB Key MFA and touching your YubiKey.
3. On the Okta user dashboard, **right click** on the `Admin` button and **open in a new tab**.
4. Press the star icon to bookmark this page, and edit the name to `Okta Admin`.
    <img style="width: 350px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_2_4_4.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_2_4_4.png" />
5. **Close** the browser tab.
6. On the Okta user dashboard, **right click** on the `G Suite SSO Mail` tile and **open in a new tab**.
7. Press the star icon to bookmark this page, and edit the name to `Gmail`.
8. Do not close the browser tab.

---

## Step 3: 1Password Configuration

### Task 3.1: Activate 1Password Account

1. In the Gmail browser tab, open the email titled `Join gitlab on 1Password`.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_1_1.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_1_1.png" />
2. Click the **Join now** button.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_1_2.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_1_2.png" />
3. You will be prompted to **enter a new 1Password master password**. 
    2. This must be different than your current 1Password master password for your `{handle}@gitlab.com` account. 
    3. This should be at least 24 characters, so it is suggested to use a phrase that you can memorably type rather than numbers and symbols that you can forget. 
    4. Do not store this password in your 1Password vault. This should only be typed from memory and written on the printed Emergency Kit and stored in your home safe or other safe offline location.
    5. This is the one password that cannot be autofilled.  
        <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_1_3.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_1_3.png" />
4. You will be showed your Secret Key. Click the button to **Download** your emergency kit.
    1. It is your discretion whether to store this in your existing 1Password private vault or only store it on paper in a safe location. Never store your secret key and master password in the same place digitally (only on paper).
    2. If you keep your credentials fully digital, never store your master password.
5. After the PDF has been downloaded, print this on your local printer. You can then write your password on it and store it in your home safe or another safe location. 
    1. Do not store this piece of paper in a backpack or anything that travels with you.
    2. Do not put this in a drawer in your desk or put it anywhere visible to anyone.
6. Delete the `1Password Emergency Kit` PDF file from the `Downloads` folder.  
    <img style="width: 400px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_1_6.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_1_6.png" />
7. Open your Trash from the dock. Right click on the `1Password Emergency Kit` PDF file and click **Delete Immediately**.  
    <img style="width: 350px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_1_7.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_1_7.png" />
8. Your account has been successfully activated. You can ignore the message `your account administrator has been notified to complete the recovery`.

### Task 3.2: Configure Browser Extension

> **Warning:** You need to wait to receive a `Welcome to 1Password` email in your new `{handle}-admin@gitlab.com` Gmail inbox (not your normal email account). Please refresh your email inbox until this email appears indicating that your account has been provisioned. This allows time for the background job automation to provision your 1Password account. No manual intervention is needed by an administrator, this simply takes up to 5 minutes usually.

1. After you have received the email (see above), open a new browser tab, and navigate to `https://gitlab.1password.com`.
2. Sign in with your email address (`{handle}-admin@gitlab.com`), secret key, and master password.
3. In the `Get the 1Password browser extension` section, click the **Get it now** button.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_2_3.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_2_3.png" />
4. On the Chrome Extension page, click the **Add to Chrome** button.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_2_4.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_2_4.png" />
5. In the top right corner, click the plugin icon and click the pin icon for 1Password.  
    <img style="width: 350px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_2_5.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_2_5.png" />
6.  In the top right corner, click the plugin icon and click the dots icon for 1Password and select **Settings**.  
    <img style="width: 400px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_2_6.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_2_6.png" />
7. On the **Settings > General** page, uncheck the toggle for `Integrate with 1Password app`. This allows us to add separate 1Password accounts that don't conflict with your normal user account on your laptop.
    <img style="width: 600px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_2_7.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_2_7.png" />
8. Scroll down to `Accounts & Vaults`.
9. (If exists) Click the arrows for your `gitlab` account and click **Sign Out**.
10. (If exists) Remove any personal/family accounts as well. This will not affect your 1Password usage in other Chrome profiles or on your Mac app.
11. Click the **Sign in to a new account** button.
12. Sign in with your email address (`{handle}-admin@gitlab.com`), secret key, and master password.
13. If this process gives you any trouble, you might need to repeat these steps to remove your existing 1Password accounts.
14. Your browser extension has now been configured and you can access your vault credentials for your `{handle}-admin@gitlab.com` 1Password account from this Chrome browser profile. You will not be able to access this 1Password account from the normal Mac app. 
15. Click on the 1Password logo in the top right corner of your browser to open the extension. If you see your vault, this is working properly. If you have a spinning wheel, try closing and re-opening the Chrome browser window to be prompted to unlock your vault.

### Task 3.3 Add 1Password bookmark

1. Click the 1Password icon in the top right browser toolbar.
2. Click **New Item** and click **Login**.  
    <img style="width: 500px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_3_2.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_3_2.png" />
3. You will be redirected to the 1Password website and automatically authenticated.
4. Click the **Cancel** button in the top right corner.
5. Click the 1Password **logo** in the top left corner.  
    <img style="width: 700px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_3_5.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_3_5.png" />
6. Click the **Private** vault tile.
7. This is the vault web UI where you can add and manage records.
8. Click the **star** icon in the top right corner to bookmark this page. Edit the description to `1Password`.  
    <img style="width: 350px; border: 1px #DCDCDE solid; padding: 2px;" alt="OktaAdminOnboarding_3_3_8.png" src="/handbook/it/runbooks/okta/admin/onboarding/images/OktaAdminOnboarding_3_3_8.png" />

### Task 3.4 Add Okta Account to New 1Password Vault

1. In the 1Password webpage, click the `+` button to add a new `Login` record.
2. Use the following to fill out the record details.
    - **Title:** `Okta Admin`
    - **Username:** `{firstInitial}{lastName}-admin@gitlab.com`
    - **Password:** Click the key icon and generate a 64-character password with symbols and numbers.
    - **Website:** `https://gitlab.okta.com`
3. Click **Save**.
4. Drag this browser tab out of the current window to move it to it's own new window.

### Task 3.5 Change Okta Password

> This password change allows us to rotate your credentials now that the record is stored in your BLACK account vault, and ensures that your PURPLE account vault does not have the credentials to sign into your Okta Admin account.

1. Using the original browser window, click on the `Okta Admin` bookmark that you created.
2. In the top right corner of the Okta webpage, click on your name and click **Settings** from the dropdown list.
3. On the right side of the page, locate the `Password` security method and click the **Reset** button. Press **Yes** when prompted.
4. You will be prompted to sign in with your YubiKey and the old password (from the `Okta Temp Admin` 1Password record).
5. When prompted to set the new password, copy the value from the 1Password record that you just created in the Web UI.
6. After your password has been changed, delete the `Okta Temp Admin` record from your 1Password app since these credentials are no longer valid and are exclusively stored in your admin vault now.

---

## Questions and Feedback

If you experience any problems, please tag `@it-eng` in `#it_help` for assistance. 

If you have feedback on this runbook, please create a new merge request with suggested changes.
