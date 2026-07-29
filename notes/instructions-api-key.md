## Step 1: Create a Hugging Face Account

1. Go to the [Hugging Face website](https://huggingface.co/).
2. Click the **Sign Up** button in the top right corner.
3. Enter your email address and choose a password, then click **Next**.
4. Fill in your profile details (username, full name, and optional links like GitHub).
5. Agree to the Terms of Service and click **Join**.
6. Check your email inbox for a verification link from Hugging Face and click it to activate your account.

---

## Step 2: Navigate to Access Tokens

1. Once logged in, click on your **profile picture/avatar** in the top right corner of the page.
2. Select **Settings** from the dropdown menu.
3. In the left-hand sidebar, click on **Access Tokens**.

---

## Step 3: Create a Write Token

1. Click the **+ Create new token** button.
2. **Name your token:** Give it a descriptive name (e.g., `fine-tuning-upload` or `colab-write`).
3. **Select Token Type:** * Choose **Write**. A standard **Write** token allows you to push models, datasets, and spaces to your profile.
4. Click **Generate token** at the bottom of the modal.

---

## Step 4: Secure Your Key

1. Copy the generated token immediately using the copy icon.
2. Store it securely (e.g., in a password manager or an environment variable).

> ⚠️ **Important:** Hugging Face will not show this token to you again for security reasons. Keep it private—anyone with this key can modify your repositories.