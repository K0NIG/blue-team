<header>

<!--
  <<< Author notes: Course header >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  Add your open source license, GitHub uses MIT license.
-->

# Statement of Purpose 

_Creating this page in order to build documentation on everything I learn and discover while I work on leveling up my pen testing skills. At some point I'm going to seperate these by individual pages because I think it will get long, but for right now I'm going to stick with this._

</header>

<!--
  <<< Author notes: Step 1 >>>
  Choose 3-5 steps for your course.
  The first step is always the hardest, so pick something easy!
  Link to docs.github.com for further explanations.
  Encourage users to open new tabs for steps!
-->

## The Toolbelt

I'm currently learning python, C#, and lua. As of this point in time, all the tools in my repository are all provided by _Linux Kali_. I do not own any of these tools, and Linux is an open source OS that can be downloaded for free online.

1. Nmap
  > While delving deeper into nmap, I started using scripts. I'm still going through the script repository and figuring out use cases, but I noticed when installing vulscan from the github repo the setup was a little different.
1. telnet/smbclient
1. redis-cli
1. xfreerdp
1. gobuster
1. mongo shell
1. rsync

### Nmap

1. [vulscan.nse](https://github.com/scipag/vulscan)
   - When navigating to the repository and going through the documentation, it states to use the following lines:
   ```bash
   git clone https://github.com/scipag/vulscan scipag_vulscan
   ln -s `pwd`/scipag_vulscan /usr/share/nmap/scripts/vulscan
``

I ran into some trouble with this because on the first attempt I was told the following.
```bash
ln: failed to create symbolic link 'usr/share/nmap/scripts/vulscan': File exists
```

It looks like people using vulners were having the same issue [over in this thread](https://github.com/vulnersCom/nmap-vulners/issues/13). They clued me in on half the puzzle, which is that I wasn't currently in the file directory before trying to ececute the nmap scan, but the first half on how to establish the symnolic link was still missing. After a few searches later, I discovered a few things.
1. Those are backticks, very different from commas.
2. It's reversed.
3. You need sudo.

Here's the revised entry:
```bash
sudo ln -s /usr/share/nmap/scripts/vulscan `pwd`/scipag_vulscan
```

Now you'll have ONE more problem before you get a successful entry. When you call the script you don't use script=vulscan/vulscan.nse, you go into the vulscan directory and use scipag_vulscan/vulscan.nse. Again, here's the revision:
```bash
nmap -sV --script=scipag_vulscan/vulscan.nse {IP HERE}
```



<footer>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Get help: [Post in our discussion board](https://github.com/orgs/skills/discussions/categories/github-pages) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)

</footer>
