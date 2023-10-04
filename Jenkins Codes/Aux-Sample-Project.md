## HOW TO CONNECT JENKINS TO GITHUB


* On Jenkins
* Clink new item
* Give the job a name
* Click on freestyle project
*  And scroll down to general
<img width="891" alt="jenkin to githib 1" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/0861df0c-9c44-4a45-b1bf-25df96facc6f">

* On General, write a description
* go down to github and tick it
* tick github project
* Enter github url of the repo on the github browser when that repo is opened on github. 
<img width="847" alt="jenkins to github 2" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/01b89067-6ad6-4552-bf40-f81ee0b705eb">

* On source code management
* click on git
* on Repository, enter the HTTP URL of the repo
<img width="960" alt="jenkins to github 3" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/e24c0572-180c-4aa3-9998-0e4e47a45865">

* Scroll down to Branch specifier and change to */main
* apply and savesave
<img width="872" alt="jenkins to github 4" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/e7caf858-3b2b-4f2e-857f-d3e0fb90283b">

* Notice github logo on the left navigation plane
* If I click on the logo, it will take me straight to the github
<img width="634" alt="see git hub logo has added on the navigation plane on the left 5" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/a6f23f35-c13e-41d5-839f-6f9c24329ae4">

* click Build now
<img width="676" alt="5" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/1e71a558-de7e-4012-996f-c0f45620121e">

<img width="759" alt="6" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/1828d62f-3932-469d-8b47-da3f001023df">

<img width="674" alt="7" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/672fb9e8-8123-401a-a555-729e8b3ae013">

<img width="641" alt="8" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/932d94d9-2e7c-40dd-bca8-5cf357461e47">

* Browse crontab guru 
<img width="952" alt="9" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/e4185fbe-b64f-4509-8b80-29fffbb30698">


<img width="925" alt="10" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/75c07076-bfc1-4fdb-ba51-b57204c930f5">

<img width="923" alt="11" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/9a7a49cf-e8df-4177-a5e5-599deb390708">

##  To automate the build now every time I pass in a code, I dont have to dclick build now manually
* Go to github:
* click settings
* webhooks
* add webhook
* add public IP:8080/github-webhook/
* add webhook
<img width="914" alt="12" src="https://github.com/Gailpositive/Jenkins-To-github-sample-job/assets/111061512/af92091c-6540-44ad-9b59-38116b5bbdf6">
