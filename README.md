# Wazuh-Implementation:
  Implementation of a SIEM (Wazuh) for simulation of real world cybersecurity project .

Hello, I am Rayane, I was doing this work as 1 month internship project in @CMPE Maroc in ordre to try to enhance the entreprise security and upgrade my skills in this field .

#Why I've done This and from where did this Idea Came from ?
  First the idea came from my deep obssession of Cybersecurity and the desire of experiencing real world CyberProjects, so during the internship I was thinking 100% of a Cybersecurity project even if i do not have a solid background (I have a solid background in networking, Linux System Administration, and Coding which is i think not enough for pushing directly into those projects) but i'll do it because i know 100% i can do it, and next after lot of prijects spawned in my head i choosed something that is relatively basic and solid which is simulating a centralized SIEM environement using Wazuh as part of gaining learning and experience in cybersecurity, and I have discussed this with my manager who gave me the permission to do it and a big thank to him from here . 

#Introduction
  During This internship I had done and learned lot of thing as not completing others even so I count it as a success .
  I've Implemented Wazuh on My Machine( Ubuntu [24.04.2 LTS] ) and installed all dependencies (wazuh-manager, wazuh-indexer, wazuh-dashboard) in same machine, parsing logs received from a Watchguard Firewall, which was configured to send logs via Syslog PORT[514/UDP] to my local Syslog server for analysis. 

!! All testing and configurations were performed on a separate machine under a controlled and safe conditions while respecting entreprise policies.

#Tools Used
  -Wazuh (Open Source SIEM and XDR)
  -Syslog Server (For Sending/Receiving Logs)
  -Watchguard Firewall (For Sending Logs)
  -Ubuntu (My Machine)
  -Wazuh decoders and Rules (XML)
  -Bash + Linux tools (diagnosis and Error fixing)

#Steps Done During This Project
  1-The first step is to Find a Powerfull,Free, and Open-source SIEM which after lot of searching and recommendations I found one named Wazuh .
  2-Installing it while following the official installation documentation from Wazuh:
  [https://documentation.wazuh.com/current/installation-guide/index.html], i've faced a lot of bugs in this phase see more in [##Challenges Faced and what i've learned] section .
  3-Asking my Manager to allow watchguard to send logs via Syslog into my local Syslog server, and configuring it to parse those logs into a file named [watchguard.log] in [/var/log] directory .
  4-This Step is where i had the most time in it which was implementing decoders for those logs so it wazuh can extract data from those raw logs and read them, also writting rules so Wazuh knows where to raise alerts and what to do if a rule matched see more in [##Challenges Faced and what i've learned] .


#Challenges Faced and what i've learned
  1-During installation process: 
    I uninstalled and reinstalled Wazuh more than 7 times or more !! .
    and that because of various problem during this phase, everytime a problem appears sometimes from configuration errors, or from installation process itself some packages may be broken, and also some essential files were not installed many times and that because of what i've concluded:
      -No good internet connection while installation process .
      -when uninstalling wazuh, I didn't remove all the related files that they were not removed by removing the program of even when executing the [purge] command that delete apps with their config files .
      -Ip Address was changing in very short times which is not a good thing for implementing a SIEM solution for a server that have a variable IP address .
  2-Decoders, and Regex patterns:
    -it wasn't hard to write regex for logs at all, it was very easy .
    the problem was that Wazuh decoders doesnt accept, support all regex patterns the thing that i realized too late and take mo so much time, and that's because all the regex I write was correct and when I test Them in Various regex Websites they works and extract the data correctly, but when I implement those regex patterns in Wazuh decoders, Boom!, so many syntax errors, and why this has taken me so much time because even AI has failed to find the problem (Which was with wazuh decoders supported syntax for regex) the thing that may seem so easy to find, but for me and considering that is a new experience it was very hard, and I spent lot of times with AI figuring the problem (ChatGPT, Gemini Pro, Copilot) and those all have failed to find the problem which later i've figured it by myself by analysing and playing with regex syntax .
  3-I passed more than 15 days just figuring out how the regex patterns are working in Wazuh decoders and passed lot of times trying to fix the errors with AI but no results, until I relied on my self even with i dont have any background in it, and yeah i've found it, I found a lot of regex patterns that are not supported by wazuh decoders . 
  3- A low end laptop which was crashin lot of times .
  4- Not Enough Time to complete the desired project .

#What did I Benefit and Learned
  -First real world project experience that has Cybersecurity background .
  -Learned Installing wazuh and working with it, also how to debug related problems .
  -Writting regex patterns, decoders and rules .
  -Analyse Logs .
  -Enhanced my Problem Solving Skills .
  -Perseverance
