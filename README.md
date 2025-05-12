#Full Website Hosting on AWS with CloudFront, HTTPS, Route 53, and Formspree Integration

Project Overview:
This project involves setting up a fully functional website on AWS S3, utilizing CloudFront for fast delivery, Route 53 for custom domain management, and HTTPS for secure communication. Additionally, the project integrates a Formspree contact form to handle form submissions via email, all hosted under a custom domain.

The project demonstrates how to use AWS for static web hosting, how to leverage CloudFront to accelerate content delivery, and how to use Route 53 to map a custom domain to an S3-hosted website. The goal was to provide a secure, fast, and scalable hosting solution, with Formspree seamlessly handling the form submissions.

Key Features:
AWS S3 Static Website Hosting: The website is hosted using Amazon S3 for static content delivery. S3 provides a highly durable, scalable, and cost-effective way to host HTML, CSS, and JavaScript files.

CloudFront CDN: AWS CloudFront is configured to serve the website with low latency and high transfer speeds by caching the content at multiple edge locations worldwide.

Custom Domain with Route 53: AWS Route 53 is used to manage DNS and map a custom domain (e.g., ryanfurman.net) to the S3-hosted website, ensuring it’s accessible via a user-friendly URL.

Secure HTTPS with ACM: AWS Certificate Manager (ACM) is used to issue an SSL certificate, ensuring that the website is served securely via HTTPS.

Form Handling with Formspree: A contact form is integrated into the website, which sends form submissions to Formspree, forwarding them to a specified email address for easy communication.

Error Handling and Troubleshooting: Addressed issues related to CORS settings, S3 bucket permissions, CloudFront cache invalidation, and DNS configuration.
------------------------------------------------------------------------------------------------------
Project Workflow:
1. Setting Up the Website Structure:
Created a basic static website with HTML, CSS, and JavaScript for a Contact Us page, as well as other informational pages.

Designed the Contact Form using HTML with fields such as First Name, Last Name, Email, Phone, and Message, along with validation for required fields.

Integrated the Formspree API by setting the form's action to https://formspree.io/f/xpwdjkan for handling form submissions via email.

2. Hosting the Website on AWS S3:
Created an S3 Bucket to store the website files (HTML, CSS, JavaScript).

Enabled static website hosting in the S3 bucket settings.

Uploaded the website files to the S3 bucket.

Set bucket permissions to allow public read access to all website files.

3. Configuring CloudFront for CDN:
Created a CloudFront Distribution with the S3 bucket as the origin.

Configured cache settings to ensure that CloudFront would cache and serve the website content from edge locations across the globe, reducing load times.

Invalidated CloudFront cache when updating the website to ensure the latest version of files is served to users.

4. Securing the Website with HTTPS (ACM SSL Certificate):
Requested a free SSL certificate through AWS Certificate Manager (ACM) to secure the website with HTTPS.

Configured CloudFront to use the SSL certificate and ensure the website is served securely over HTTPS.

Updated CloudFront settings to enforce HTTPS, ensuring that all traffic to the website is encrypted.

5. Mapping a Custom Domain Using Route 53:
Set up Route 53 to manage DNS records for the custom domain ryanfurman.net.

Created DNS records in Route 53, pointing the domain to the CloudFront distribution to make the website accessible via https://ryanfurman.net.

Configured the A Record in Route 53 to point to the CloudFront distribution’s domain name.

6. Integrating the Contact Form with Formspree:
Integrated the Formspree service into the contact form to handle form submissions. This ensures that when the user submits a message, it is forwarded to an email address specified in the Formspree dashboard.

The form’s action URL was set to https://formspree.io/f/xpwdjkan to forward form submissions.

Tested the form on both local and live environments to ensure that the data was being correctly submitted and received via email.

7. Troubleshooting and Debugging:
CORS (Cross-Origin Resource Sharing): Encountered issues with CORS settings on S3, which prevented form submissions. Configured CORS settings in the S3 bucket to allow access from both the website domain (https://ryanfurman.net) and Formspree.

CloudFront Cache: Realized that CloudFront was serving an outdated version of the website due to cached content. Invalidated the CloudFront cache and made sure the latest files were being served.

DNS Configuration: Initially faced issues with the custom domain pointing to the wrong location. This was resolved by correctly configuring Route 53 DNS records to ensure they pointed to the CloudFront distribution.

8. Final Testing and Confirmation:
After completing the above steps, the website was tested:

Ensured the form submitted data to Formspree and received the submission in the specified email.

Verified that the website was accessible over HTTPS via the custom domain.

Confirmed that CloudFront was serving the content from edge locations and ensuring fast load times.

Checked the Route 53 configuration to ensure that the custom domain was correctly pointing to the CloudFront distribution.
------------------------------------------------------------------------------------------------------

Technologies Used:
HTML5 for creating the website and contact form.

CSS3 for styling the website and making it responsive.

JavaScript for any client-side functionality.

AWS S3 for static website hosting.

AWS CloudFront for content delivery via CDN.

AWS Route 53 for DNS management and custom domain mapping.

AWS ACM for SSL certificates and HTTPS support.

Formspree for handling form submissions via email.

CORS for setting up cross-origin resource sharing between the website and Formspree’s API.
------------------------------------------------------------------------------------------------------

Challenges Faced and Solutions:
CORS Configuration Issues:

Initially, the form submissions weren’t working due to CORS restrictions. This was resolved by configuring the correct CORS policy in the S3 bucket to allow communication between the website and Formspree.

CloudFront Cache Invalidation:

The outdated cached content was served by CloudFront. This was fixed by invalidating the CloudFront cache, ensuring that the latest version of the website was being served.

DNS Configuration with Route 53:

Faced difficulties with configuring DNS records to correctly point the custom domain to the CloudFront distribution. This was resolved by updating Route 53 DNS settings, ensuring proper routing of traffic.

Ensuring HTTPS:

Initially, the website wasn’t served over HTTPS. This was fixed by requesting an SSL certificate via AWS ACM and ensuring CloudFront was configured to serve the website securely.
------------------------------------------------------------------------------------------------------

Conclusion:
This project demonstrates how to build, deploy, and troubleshoot a static website on AWS with a custom domain, HTTPS, CloudFront CDN, and a Formspree integration for handling form submissions. Through this, I gained experience working with various AWS services, including S3, CloudFront, Route 53, and ACM, while also implementing best practices for secure, scalable web hosting and email-based form handling.
