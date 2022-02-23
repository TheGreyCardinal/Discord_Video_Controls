# Discord Video Controls.
JS user-script. - Adding a control panel to the video (if Discord's native controls don't turn off the sound).

1. Add a user-script extension to your browser.  
For example: [User JavaScript and CSS](https://chrome.google.com/webstore/detail/user-javascript-and-css/nbhcbdghjpllgmfilhnhkllmkecfmpld?hl=ru)

2. Add a rule for:  
[https://discord.com/*](https://discord.com/*) 

3. Rule code:  
```js
 window.addEventListener("load", function() 
  {
   setInterval(add_video_controls, 1000);
  });

 function add_video_controls()
  {
   var list = document.querySelectorAll("video");
   
   for (var i = 0; i < list.length; i++)
    {
     if (list[i].controls == false)
      {
       list[i].setAttribute("controls", true);
       list[i].setAttribute("style", "z-index: 10000;");
      }
    }
  }
```

4. Example:  
![Example](https://i.ibb.co/3p6MG3h/1.png)
