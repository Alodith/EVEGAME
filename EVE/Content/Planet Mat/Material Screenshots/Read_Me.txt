I got a PM asking for a .uasset, but for certain reasons I am not providing one. Instead I have put together a bunch of screenshots with everything you need to recreate my material. I'm going to list the steps for you here.

See the folder labeled "Start Here"? Start there. There will be a photo of the material overview (yes it's unreadable, but it provides a clean look at where the node wires are going) and that will be your basis of the whole material when it's done. From there you'll want to look at the landmass color set up, which has an extremely large material function that you'll need to make. At this point you need to go into the "Functions" folder and recreate the "colorlutmf" function. That function handles the color bands for the landmass that the noise node creates later on. You can make as many as you want, but don't come asking me for help if it creates bugs. ;)

Once that's done, you can bring the function into your main planet material graph and start hooking up your vector 3 colors. Again, you can see all this clearly in the screenshots provided. After you've plugged up the colors and band location values into the material function, it's time to create the noise and world space lock that your function will provide color to. That screenshot shows the noise lock (if you don't use this, your noise will scale based on planet size and move around in world space) and the cloud generation noise node at the end of the chain. 

If you're confused about how many noise nodes I used, technically there are 3.

-Landmass noise
-Cloud noise
-Polar cap noise

The landmass noise node is in the landmass color screenshot, and that's connected to the noise lock chain add node that is right behind "object radius". I've provided screenshots of the values used for the landmass noise and cloud noise nodes in the extras folder. Anyway, the landmass noise values go into the first 3 "UV" pins of the colorlut function, and the cloud noise goes into the 4th "UV" pin. You can see this in the noise value screenshot.

Next we have the normal generation, and I must say that that feature is very finnicky, so you'll have to manually tweak those values a lot. I used switch parameters so I could just shut them off if I didn't like how they looked, and the values being input into the switches are the 3 output pins of the colorlut function. Add the 3 normals together and that just goes into the normal input pin of the material. 

After that we have the atmosphere set up (in the original screen shots I think my set up was different and the one I have included is some variation of JBaldwin's set up IIRC). That whole thing just plugs directly into the emissive pin.

Lastly we have the polar cap setup, but as stated in the original thread, it only shows up in the material editor preview. I think the function is technically correct, but it just would never show up. You can remove this entirely or try to get it to work. 

That's it for the setup. I hope it helps you in some way.
