<p align="center">
  <a href="https://github.com/troke12/gopi" target="blank"><img src="https://socialify.git.ci/troke12/MikrotikToDiscord/image?description=1&descriptionEditable=Monitoring%20your%20mikrotik%20from%20your%20discord!&font=Rokkitt&forks=1&issues=1&pattern=Brick%20Wall&pulls=1&stargazers=1&theme=Dark" alt="Go" /></a>
</p>
<p align="center">
  <a href="https://heroku.com/deploy?template=https://github.com/troke12/MikrotikToDiscord" target="blank"><img src="https://www.herokucdn.com/deploy/button.svg"/></a> <a href="https://forum.mikrotik.com/viewtopic.php?f=9&t=173923" target="blank"><img src="https://img.shields.io/badge/Mikrotik-Forum-yellowgreen?style=for-the-badge&logo=appveyor"/></a>
</p>

Monitor your mikrotik devices easily! used for sending your mikrotik logs from netwatch/hostpot/interface to your discord, you can also use this with another device too! 

# Requirements
|  | Note |
| --- | --- |
| Discord | Download the [Discord](https://discord.com) through to the website |
| Webhook Discord | [Read this](https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks) guide to make your own discord webhook |
| Mikrotik | You can use any type of Mikrotik |

# How to use
1. You can use my url that already deployed in Heroku or you can deploy your own by pressing Deploy to heroku button.
2. Copy this script to your mikrotik, for example in netwatch Up/Down :

```bash
/tool fetch url="https://trokewebhook.herokuapp.com/form.php?text=INPUT_YOUR_TEXT_HERE&id=INPUT_ID_WEBHOOK&token=INPUT_TOKEN_WEBHOOK" keep-result=no;
```
Notes
 - The `INPUT_YOUR_TEXT` you need to change to whatever you want, example `THE+RB+FRONT+IS+UP` (You need add `+` for spacing)
 - The `INPUT_ID_WEBHOOK` change to your id discord webhook url, `https://discord.com/api/webhooks/7939909737777777/REl22gJR5WIp0I7BwCiMu2UPHG3_jXMNPddddddddddddddddna9EmmW39buWI3` then the `7939909737777777` is your ID
 - The `INPUT_ID_WEBHOOK` change to your discord webhook token, `REl22gJR5WIp0I7BwCiMu2UPHG3_jXMNPddddddddddddddddna9EmmW39buWI3` it's your token

![image](https://user-images.githubusercontent.com/10250068/112728650-4067a280-8f63-11eb-8945-da7d2cec3184.png)

3. After that you can apply and ok. The results will be like this :

![image](https://user-images.githubusercontent.com/10250068/112728601-10200400-8f63-11eb-95cd-1378b27458c0.png)

4. Enjoy monitoring your devices guys!!
