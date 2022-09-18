# make connections

1. Create ssh key for Control Node
2. copy the public key paste in every manage node under:
   ~/.ssh/authorized_keys
3. remove other permisions of .ssh directory :
   ```bash
   chmod -R go= ~/.ssh
   ```
4. create ownership for required user ( in our case its ubuntu )
   ```bash
   chown -R ubuntu:ubuntu ~/.ssh
   ```

5. Now we add present ssh key to ssh-agent:
    ```bash
    ssh-agent bash
    ssh-add ~/.ssh/id_rsa
    ```


# tip: to get static site free template on remote server

1. go to https://html.design
2. select a template and click download
3. when you get to the page that says Wait for file to download:
   1. copy the the link named as *Click Here*
   2. it would be be like: https://html.design/downloads/11591/

4. Now run following command:
   ```bash
   curl https://html.design/downloads/11591/ --output site.zip
   ```
5. A zip file is downloaded as:
   ```bash
   $ ls
   site.zip
   ```
6. unzip the file 
   ```bash
      $ unzip site.zip 
   Archive:  site.zip
   inflating: html/about.html         
   inflating: html/blog.html          
   inflating: html/contact.html       
      creating: html/css/
   inflating: html/css/.DS_Store      
   inflating: html/css/animate.min.css  
   inflating: html/css/bootstrap.css  
   inflating: html/css/bootstrap.css.map  
   inflating: html/css/bootstrap.min.css  
   inflating: html/css/bootstrap.min.css.map  
   inflating: html/css/bootstrap-grid.css  
   inflating: html/css/bootstrap-grid.css.map  
   inflating: html/css/bootstrap-grid.min.css  
   inflating: html/css/bootstrap-grid.min.css.map  
   inflating: html/css/bootstrap-reboot.css  
   inflating: html/css/bootstrap-reboot.css.map  
   inflating: html/css/bootstrap-reboot.min.css  
   inflating: html/css/bootstrap-reboot.min.css.map  
   inflating: html/css/default-skin.css  
   inflating: html/css/font-awesome.min.css  
   inflating: html/css/icomoon.css    
   inflating: html/css/jquery.fancybox.min.css  
   inflating: html/css/jquery.mCustomScrollbar.min.css  
   inflating: html/css/jquery-ui.css  
   inflating: html/css/meanmenu.css   
   inflating: html/css/nice-select.css  
   inflating: html/css/normalize.css  
   inflating: html/css/owl.carousel.min.css  
   inflating: html/css/responsive.css  
   inflating: html/css/slick.css      
   inflating: html/css/style.css      
      creating: html/fonts/
   inflating: html/game.html          
      creating: html/images/
   inflating: html/images/about-bg.png  
   inflating: html/images/about-img.png  
   inflating: html/images/app-store-icon.png  
   inflating: html/images/banner-bg.png  
   inflating: html/images/blog-bg.png  
   inflating: html/images/blog-img.png  
   inflating: html/images/blog-img1.png  
   inflating: html/images/car-img.png  
   inflating: html/images/game-bg.png  
   inflating: html/images/google-app-icon.png  
   inflating: html/images/logo.png    
   inflating: html/images/toggle-icon.png  
   inflating: html/index.html         
      creating: html/js/
   inflating: html/js/.DS_Store       
   inflating: html/js/bootstrap.bundle.js  
   inflating: html/js/bootstrap.bundle.js.map  
   inflating: html/js/bootstrap.bundle.min.js  
   inflating: html/js/bootstrap.bundle.min.js.map  
   inflating: html/js/bootstrap.js    
   inflating: html/js/bootstrap.js.map  
   inflating: html/js/bootstrap.min.js  
   inflating: html/js/bootstrap.min.js.map  
   inflating: html/js/custom.js       
   inflating: html/js/jquery.mCustomScrollbar.concat.min.js  
   inflating: html/js/jquery.min.js   
   inflating: html/js/jquery.validate.js  
   inflating: html/js/jquery-3.0.0.min.js  
   inflating: html/js/modernizer.js   
   inflating: html/js/plugin.js       
   inflating: html/js/popper.min.js   
   inflating: html/js/slider-setting.js  
   ```