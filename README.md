# Todo-list

- 即时通讯
  - WeChat (√)
  - TIM
- 日常
  - DesktopCal
  - Vmware-Player
  - iTunes
- 游戏
  - Steam
  - EpicGames
  - WeGame
- 科学上网
  - VeePN
  - Astar
  - Psiphon3

# How to bulid

- Create a new GitHub repo called e.g. `my-bucket`

- Add an app to your bucket. In a powershell session

  ```bash
  git clone https://github.com/<your-username>/my-bucket
  cd my-bucket
  '{ "version": "1.0", "url": "https://gist.github.com/lukesampson/6446238/raw/hello.ps1", "bin": "hello.ps1"}' > hello.json
  git add .
  git commit -m "add hello app"
  git push
  ```

-  Edit app manifest in json

  ```json
  {
      "version": "1.0",
      "url": "https://github.com/lukesampson/cowsay-psh/archive/master.zip",
      "extract_dir": "cowsay-psh-master",
      "bin": "cowsay.ps1"
  }
  
  ```

- Configure Scoop to use your new bucket

  ```bash
  scoop bucket add my-bucket https://github.com/<your-username>/my-bucket
  ```

- Check that it works

  ```bash
  scoop bucket list # -> you should see 'my-bucket'
  scoop search hello # -> you should see hello listed under, 'my-bucket bucket:'
  scoop install hello
  hello # -> you should see 'Hello, <windows-username>!'
  ```

# Add to dir

- If you want your bucket listed in the [Scoop Directory](https://github.com/rasa/scoop-directory) , add a topic of `scoop-bucket` to its github page.
- https://scoop-docs.vercel.app/apps/
- https://scoop.netlify.app/apps/

# How to install

- Run below command in PowerShell to add the bucket

  ```bash
  scoop bucket add scoop-lunar https://github.com/lunarwhite/scoop-lunar.git
  ```

- Install apps from this bucket with below command

  ```bash
  scoop install scoop-lunar/<app_name>
  scoop install scoop-lunar/wechat
  ```

# References

- [Buckets - scoop wiki](https://github.com/lukesampson/scoop/wiki/Buckets)
- [App Manifests - scoop wiki](https://github.com/lukesampson/scoop/wiki/App-Manifests)
- [scoop-extras - github repo](https://github.com/lukesampson/scoop-extras)
- [dorado - github repo](https://github.com/chawyehsu/dorado)
