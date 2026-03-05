# Setting Up Analytics and Conversion Tracking for Your Squarespace Fine Jewelry Website

## Google Analytics 4 Setup
1. **Create a Google Analytics 4 Property:**  
   - Sign in to Google Analytics and click on the "Admin" gear icon.  
   - Under the "Property" column, click on "Create Property".  
   - Name your property and select the appropriate time zone.  
   - Click "Next" and fill in the required details.

2. **Set Up Data Streams:**  
   - After creating your property, select "Data Streams" under the property settings.  
   - Click on "Add Stream" and choose "Web".  
   - Enter your website URL and stream name, and click "Create Stream".

3. **Install GA4 Tag in Squarespace:**  
   - Copy the "Measurement ID" from your data stream settings.  
   - Go to your Squarespace site, and navigate to **Settings** > **Advanced** > **Code Injection**.  
   - Paste the GA4 tracking code in the **Header** section:
     ```html
     <script async src="https://www.googletagmanager.com/gtag/js?id=YOUR_MEASUREMENT_ID"></script>
     <script>
       window.dataLayer = window.dataLayer || [];
       function gtag(){dataLayer.push(arguments);}
       gtag('js', new Date());

       gtag('config', 'YOUR_MEASUREMENT_ID');
     </script>
     ```

## Google Search Console Configuration
1. **Verify Ownership:**  
   - Go to Google Search Console and click on "Start Now".  
   - Add your website URL and click continue.  
   - Follow the verification steps, such as adding an HTML tag or uploading a verification file.

2. **Submit Sitemap:**  
   - Once verified, navigate to the "Sitemaps" section.  
   - Enter `sitemap.xml` and click "Submit" to help Google index your site.

## Facebook Pixel Installation
1. **Create a Facebook Pixel:**  
   - Go to Facebook Events Manager and click on "Pixels".  
   - Click on "Add" to create a new Pixel and follow the prompts to name it.

2. **Add Pixel to Squarespace:**  
   - Copy the pixel code provided by Facebook.  
   - Navigate to **Settings** > **Advanced** > **Code Injection** on your Squarespace site.  
   - Paste the Pixel code in the **Header** section:
     ```html
     <script>
       !function(f,b,e,v,n,t,s)
       {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
       n.callMethod.apply(n,arguments):n.queue.push(arguments)};
       if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
       n.queue=[];t=b.createElement(e);t.async=!0;
       t.src=v;s=b.getElementsByTagName(e)[0];
       s.parentNode.insertBefore(t,s)}(window, document,'script',
       'https://connect.facebook.net/en_US/sdk.js');
       fbq('init', 'YOUR_PIXEL_ID');
       fbq('track', 'PageView');
     </script>
     ```

## Conversion Tracking for Key Actions
- **Email Signups:**  
   - Set up an event in GA4 to track when someone signs up for your newsletter.
- **Contact Form Submissions:**  
   - Use the form submission tracking feature in GA4 by adding a tag in Tag Manager or using a code snippet in Squarespace.
   - Example code snippet:
     ```html
     <script>
       document.querySelector('#contact-form-id').onsubmit = function() {
           gtag('event', 'form_submit', { 'event_category': 'Contact', 'event_label': 'Contact Form Submission' });
       };
     </script>
     ```
- **Custom Design Requests:**  
   - Similar to contact form tracking, add an event tracking code for design request submissions.
- **E-commerce Purchases:**  
   - Ensure e-commerce tracking is set up in your GA4 property to monitor sales.

## UTM Parameter Tracking for Ad Campaigns
- **Create UTM Parameters:** Use the following format:
  ```
  https://yoursite.com?utm_source=source&utm_medium=medium&utm_campaign=campaign
  ```
  Replace "source", "medium", and "campaign" with relevant terms.  
  This helps you track the efficacy of your digital marketing campaigns.

## Code Snippets for Custom Code Blocks
To implement tracking snippets in Squarespace custom code blocks, ensure you edit the correct pages and add them to the appropriate sections:
```html
<!-- Google Analytics 4 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'YOUR_MEASUREMENT_ID');
</script>

<!-- Facebook Pixel -->
<script>
  !function(f,b,e,v,n,t,s)
  {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
  n.callMethod.apply(n,arguments):n.queue.push(arguments)};
  if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
  n.queue=[];t=b.createElement(e);t.async=!0;
  t.src=v;s=b.getElementsByTagName(e)[0];
  s.parentNode.insertBefore(t,s)}(window, document,'script',
  'https://connect.facebook.net/en_US/sdk.js');
  fbq('init', 'YOUR_PIXEL_ID');
  fbq('track', 'PageView');
</script>
```

Ensure you replace placeholders with your actual Google Analytics and Facebook Pixel IDs. Follow these detailed instructions to effectively set up and track all crucial metrics for your Squarespace fine jewelry website.