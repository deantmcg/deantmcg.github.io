# Contact Form Setup Instructions

The contact form on this website uses [Web3Forms](https://web3forms.com) - a free service that forwards form submissions to your email without requiring backend code.

## Setup Steps

### 1. Sign Up for Web3Forms (Free)
- Go to [https://web3forms.com](https://web3forms.com)
- Click "Get Started" or "Sign Up"
- Enter your email address
- Verify your email

### 2. Get Your Access Key
- Log in to your Web3Forms dashboard
- You'll see your **Access Key** (format: `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`)
- Copy this key

### 3. Configure Your Email
- In the Web3Forms dashboard, make sure your email is set to: `deantmcg@gmail.com`
- This is where form submissions will be sent

### 4. Add the Access Key to Your Website
- Open `index.html`
- Find the JavaScript section near the bottom (around line 222)
- Look for this code:
  ```javascript
  const parts = ['xxxxxxxx', '-xxxx-', 'xxxx-', 'xxxx-', 'xxxxxxxxxxxx'];
  ```
- Replace the placeholder with your actual access key, split into parts for obfuscation
- **Example**: If your key is `12345678-abcd-efgh-ijkl-123456789abc`, update it like:
  ```javascript
  const parts = ['12345678', '-abcd-', 'efgh-', 'ijkl-', '123456789abc'];
  ```

### 5. Test the Form
- Save and deploy your changes
- Open your website
- Click the Contact button
- Fill out and submit the form
- You should receive the submission at `deantmcg@gmail.com`

## Why Split the Key?

The access key is split into parts to provide basic obfuscation against automated scrapers. While the key is still visible in the source code, this makes it slightly harder for bots to harvest it. Web3Forms API keys are rate-limited and can be regenerated if needed.

## Troubleshooting

### "Contact form setup incomplete" Error
- The access key hasn't been configured yet
- Follow steps 1-4 above to set it up

### "Failed to send message" Error
- Check that you've entered a valid access key
- Verify your email is confirmed in Web3Forms
- Check the browser console for detailed error messages

### 400 Bad Request Error
- The access key format is incorrect
- Make sure you copied the complete key from Web3Forms
- Ensure the key parts are joined correctly without extra characters

## Alternative: Use Formspree

If you prefer a different service, you can also use [Formspree](https://formspree.io):
1. Sign up at formspree.io
2. Create a new form
3. Replace the Web3Forms endpoint in the code with Formspree's endpoint
4. Update the form submission code accordingly

## Need Help?

If you encounter any issues, check:
- [Web3Forms Documentation](https://docs.web3forms.com)
- Your browser's console for error messages
- That your email is verified in Web3Forms
