# emulated_hue
Home Assistant emulated_hue that supports multiple instances.

### Note: 

This component has not been thoroughly tested. I have a very limited test bed.

### What is this?

This is a version of the Home Assistant emulated_hue component that allows for multiple instances to overcome the 49 device limit issue.

### Installation

Download the git repository and copy the files intoe the Home Assistant /config/custom_components directory.

### Configuring emulated_hue

The configuration of this emulated_hue is similar to the original. But, now you have to provide a 'name' for the emulated_hue instance. And you are able to configure multiple instances. Listent ports are required (for now) to differentiate the instances.

``` yaml
emulated_hue:
  hue1:
    type: alexa
    listen_port: 8301
    exposed_domains:
      - fan
      - group
      - climate
      - script
  hue2:
    type: alexa
    listen_port: 8302
    exposed_domains:
      - light
 ```
The above configuration devices two emulated_hue instances ('hue1' and 'hue2'). The first emulated_hue is hosted on port 8301 and the second is on port 8302. 

The `target_ip` option can be used if you have more than one Amazon Echo and you only want certain domains to be reported to a particular Echo. This is usually not required. 
