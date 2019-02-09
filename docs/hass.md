##Hass.io (in Docker!)

I am Running Hass.io on this [Intel Nuc](https://www.intel.com/content/www/us/en/products/boards-kits/nuc/kits/nuc5cpyh.html) with Ubuntu Server 16.04, in Docker.

To run Hass.io this way, [install manually in Docker](https://github.com/home-assistant/hassio-build/blob/master/install/README.md).

On the contrary to what some might say or think, this is not overly complicated and it's not layering OS's and VM's on top of each other. I have Docker CE, and Home Assistant runs two containers to start with; one for the Home Assistant software and one for the Supervisor (that's the Hass.io specific part, one could say, although you can't just install that on top of a regular Home Assistant docker and get Hass.io). Then every add-on I install gets it's own docker container. That's really almost all there is to it.

###Pros and cons

Okey, I haven't really found any real cons yet to this setup, so this'll mostly be pros.

When Hass.io first came as an installation method I was heavily against ever trying it out. It seemed very boxed in. When I decided to move my setup from a Raspberry Pi 3 to a Nuc it had come a long way though, already. I didn't need to use the HassOS (then ResinOS) image, but could install manually, thus keeping the option of having other things, totally non-related to Hass or even smart homes, on the same machine.

*Now* there's a lot of add-ons for all sorts of stuff, but if I find something I want that's not available as an add-on I can just install it in Docker the "regular way" and get it going in minutes. I did have to learn how to operate docker, but I just think that's fun (at least when you have a huge community that's ready to save you when you f*ck up).

At the same time as I get all the good stuff with Hass.io (snapshots, add-ons, easy to use managing interface) I also get all the freedom of a non-Hass.io setup. I have yet to find something I can't do with this setup that I could with another.

The moce to a Nuc also saves me a lot of headache with SD cards that suddenly stop working due to an electrical outage and - oh - the time I save with restarts!

##Organizing the configuration

My configuration is broken down into [packages](https://www.home-assistant.io/docs/configuration/packages/), sort of mini configuration-files. This makes it easy to see everything pertaining to a specific implementation. I am just now in the process of restructuring my config, but most things still reside in the packages folder.

!!! info "Packages"
    While using packages you can no longer reload your config with the buttons in the ui.

Most of my more advanced automations are migrated to Appdaemon apps.