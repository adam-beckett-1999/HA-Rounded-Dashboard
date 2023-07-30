# HA Dashboard
This is my adaptation of the Rounded Dashboard created by LE0N on the Home Assistant forums. The original theme & styling can be found here: https://community.home-assistant.io/t/rounded-dashboard-guide/543043. You will need to add the HACS plugin and install some custom cards in order for this to work.

I've made various tweaks to the styling to suit my preferences, and re-designed some of the cards and created my own in a way that matches the original theme.

![image info](images/dashboard-overview.gif)

## Cards & Elements

### Page view button card:
The page view buttons allow switching between dashboard views, they can be resized and aligned in any way you choose. I typically leave them at the very top of the dashboard when I use them.

[YAML Code](/page-view-buttons.yaml)

![image info](images/page-view-buttons.png)

### Dashboard header card:
The header is the centerpiece of each dashboard view. The name, as well as the contents of the pill below can be customized.

[YAML Code](/dashboard-header.yaml)

![image info](images/dashboard-header.png)

### Air quality swiper card:
The air quality swiper card contains multiple sensor cards showing info like humidity, CO2 and dust levels from an air quality sensor. The first card is a custom card showing an air quality score, this can be used with something like an Awair AQ sensor or Amazon AQM sensor. In the example, I have my awair air quality score showcased here.

[YAML Code](/air-quality-swiper.yaml)

![image info](images/air-quality-swiper.gif)

### Light slider cards:
The light slider cards come in two forms, for a standard yellow/white light and for a full colour light. The slider controls brightness, and press-and-hold action on the card brings up the more-info panel for the light entity.

You can use 'aspect_ratio: 1/1' to make the card square. Eg.
```
type: custom:button-card
name: Ambient Lights
aspect_ratio: 1/1
icon: hue:desk-lamp
entity: light.bedroom_ambient_lights
tap_action:
  action: toggle
  ...
```

[YAML Code](/light-card-normal.yaml)

![image info](images/light-card-normal.gif)


[YAML Code](/light-card-colour.yaml)

![image info](images/light-card-colour.gif)

In my card layout, light sliders are always placed next to scene button cards in a grid card. Below is an example of the lighting grid for one room.

[YAML Code](/full-light-grid-card.yaml)

![image info](images/full-light-grid-card.png)

### Light scene button cards:
The light scene buttons are simple custom button cards with tap_actions defined to activate a light scene. I use philips hue, so they call the 'hue.activate_scene' service.

[YAML Code](/lighting-scene-button.yaml)

![image info](images/lighting-scene-button.png)

### 'More information' button card:
This card is a simple button that can be used to show more-info about an entity or to link to a subview. I mostly use these buttons as navigation to a subview containing a full list of entities. 

The below example is configured to go to a hidden subview of the dashboard containing all my smart-lights.

[YAML Code](/more-information-button.yaml)

![image info](images/more-information-button.png)

![image info](images/more-information-button-example.gif)