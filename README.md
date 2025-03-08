# Setting up CI/CD with GitHub Actions

The tutorial will use AWS EC2 instance as an example and won't include web server setup tutorial, any remote machines will work as long as SSH is supported.

> [!WARNING]
> This repository is for education purposes only and must not be used for production.

1. [Fork this repository](https://github.com/sglkc/github-scp-ci-cd/fork) or create a new repository
   
   ![image](https://github.com/user-attachments/assets/eb0d349e-d690-4f06-933a-f030979343da)


2. Clone your forked repository

   ![image](https://github.com/user-attachments/assets/8d7b5843-6c74-4381-b42b-20731cbe2475)

   ```sh
   # replace url with your repository url
   git clone https://github.com/sglkc/github-scp-ci-cd.git
   cd github-scp-ci-cd
   ```
   
3. Setup AWS EC2 Security Groups to enable SSH
   
   ![image](https://github.com/user-attachments/assets/f27bf77d-6e73-4fbd-9c2f-fcb7cda36e23)

4. Go to your [repository settings](./settings) page

   ![image](https://github.com/user-attachments/assets/8327d322-0034-4ccd-bcda-09934b1f6c69)

5. Go to [Secrets and Environments](./settings/secrets/actions)

   ![image](https://github.com/user-attachments/assets/ffabdb29-9d3c-4f1e-9430-de2a8bd1b107)

6. Click on [new repository secret](./settings/secrets/actions/new)

   ![image](https://github.com/user-attachments/assets/8880a0a7-1df9-41f2-8f7d-93c81eb44964)

7. Add the following variables:
   - `SSH_HOST` with your EC2 public IPv4 DNS

     ![image](https://github.com/user-attachments/assets/b821d797-1d2b-44cf-bd34-e7a5f7e98498)
     ![image](https://github.com/user-attachments/assets/1f9c5d8e-3f7e-443b-a8c7-a945baf6d0be)
  
   - `SSH_USRNAME` with your SSH username, EC2 default is `ec2-user`, below is just an example

     ![image](https://github.com/user-attachments/assets/d164c1cd-637b-4679-a852-9b083f17934c)

   - `SSH_PRIVATE_KEY` with your .pem private key file content, screenshot content is cropped

     ![image](https://github.com/user-attachments/assets/984f3527-5e14-4854-8932-84ccea27a14f)

8. Once done, head to repository Actions page and click on [CI/CD tab](./actions/workflows/ci.yml)

   ![image](https://github.com/user-attachments/assets/bd8ffd8a-2b2f-40e2-9309-97babe8940ef)

9. Click on Run Workflow to test your CI/CD

   ![image](https://github.com/user-attachments/assets/a020eb43-3642-4287-946d-667b9f52e003)

10. Refresh the page and wait for the green light
    
    ![image](https://github.com/user-attachments/assets/3f01bf76-1ffd-42b5-bcd4-32044a97ff1e)

11. Check your website on `/github`, see if it has changed

    ![image](https://github.com/user-attachments/assets/e53aa030-0c4b-43f7-a97f-c05d579b845e)

12. Edit `index.html` and push the commit
    
    ```sh
    # after editing index.html file
    git add .
    git commit -m 'edit index.html'
    git push origin master
    ```
    
13. Congratulations! You're now a self-certified professional CI/CD engineer, your next step is to apply to the highest paying companies!

    ![image](https://github.com/user-attachments/assets/226d0166-340a-4a06-8cf9-ba4e74ac8f99)
