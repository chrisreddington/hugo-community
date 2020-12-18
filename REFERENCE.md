# Reference
Community is a hugo theme intended for small community and meetup groups to easily get going. The theme is heavily driven around the concept of events and speakers, and would be well-suited to conferences, or groups that hold talks.

This guide is intended for those that wish to use the theme.

- [Reference](#reference)
  * [Site Config Settings](#site-config-settings)
    + [Core Site Configuration](#core-site-configuration)
    + [Site Rendering Options](#site-rendering-options)
    + [Site Configuration](#site-configuration)
    + [Site Required Settings](#site-required-settings)
    + [Privacy Settings](#privacy-settings)
  * [Archetypes](#archetypes)
    + [Community](#community)
      - [Community Frontmatter Details](#community-frontmatter-details)
    + [Event](#event)
      - [Event Frontmatter Details](#event-frontmatter-details)
      - [Event Activity Frontmatter Details](#event-activity-frontmatter-details)
      - [Event Sponsor Frontmatter Details](#event-sponsor-frontmatter-details)
      - [Single Event Sites](#single-event-sites)
      - [Multi Event Sites](#multi-event-sites)
    + [Group](#group)
      - [Group Frontmatter Details](#group-frontmatter-details)
      - [Group Organizer Frontmatter Details](#group-organizer-frontmatter-details)
      - [Group Sponsor Frontmatter Details](#group-sponsor-frontmatter-details)
      - [Single Group Sites](#single-group-sites)
      - [Multi Group Sites](#multi-group-sites)
    + [Speaker](#speaker)
      - [Speaker Frontmatter Details](#speaker-frontmatter-details)


## Site Config Settings

Below is an example configuration for the Hugo Community Theme. Be aware that this contains extra configuration that may not be needed in your specific deployment, and is purely to show the end-to-end options available for the configuration. For example, the permalink and menu sections are duplicated in the below snippet, to represent the common configuration options that you may want to choose from.

```
#####
#
# Configuration File
# If contributing changes into the exampleSite configuration file, then please 
# observe a few points make your contributions in line with these standards -
#
# 1. The yaml has been grouped into sections for easier readability.
# 2. Within sections, the properties have been sorted in alphabetical order to ease with 
#    maintainability/scanning through information.
#
#####

#####
# Core hugo configuration.
# You are free to edit these. However, note the 
#####

baseURL:                  "http://localhost:1313"
defaultContentLanguage:   "en"
disqusShortname:          "hugo-community"
enableGitInfo:            true
languageCode:             "en-us"
theme:                    "hugo-community"
themesdir:                "../../"
title:                    "Community, a Hugo Theme"
paginate:                  15

####
#
# Mode: Conference
# 
# Use-cases: A conference that wants to have a website for this specific conference event only.
#
####
#
# permalinks:
#   events: /event/
#   groups: /group/:title
# 
# menu:
#   main:
#     - name: "Home"
#       weight: 1
#       url: "/"
#     - name: "Group"
#       weight: 2
#       url: "/group"
#       identifier: "group"
#     - name: "About"
#       weight: 1
#       url: "/group/about"
#       parent: "group"
#     - name: "Code of Conduct"
#       weight: 2
#       url: "/group/code-of-conduct"
#       parent: "group"
#     - name: "Event"
#       weight: 3
#       url: "/event"
#     - name: "Speakers"
#       weight: 4
#       url: "/speakers"
#     - name: "Community"
#       weight: 5
#       url: "/community"
#   footer:
#     - name: "Home"
#       weight: 1
#       url: "/"
#     - name: "Group"
#       weight: 2
#       url: "/group"
#     - name: "Event"
#       weight: 3
#       url: "/event"
#     - name: "Speakers"
#       weight: 4
#       url: "/speakers"
#     - name: "Community"
#       weight: 5
#       url: "/community"

####
#
# Mode: Single Group, Many Events
#
# Use-cases: A local technical community that wants to set up their own presence quickly.
#
####
#
# permalinks:
#   groups: /group/:title
#
# menu:
#   main:
#     - name: "Home"
#       weight: 1
#       url: "/"
#     - name: "Group"
#       weight: 2
#       url: "/group"
#       identifier: "group"
#     - name: "About"
#       weight: 1
#       url: "/group/about"
#       parent: "group"
#     - name: "Code of Conduct"
#       weight: 2
#       url: "/group/code-of-conduct"
#       parent: "group"
#     - name: "Events"
#       weight: 3
#       url: "/events"
#     - name: "Speakers"
#       weight: 4
#       url: "/speakers"
#     - name: "Community"
#       weight: 5
#       url: "/community"
#   footer:
#     - name: "Home"
#       weight: 1
#       url: "/"
#     - name: "Group"
#       weight: 2
#       url: "/group"
#     - name: "Events"
#       weight: 3
#       url: "/events"
#     - name: "Speakers"
#       weight: 4
#       url: "/speakers"
#     - name: "Community"
#       weight: 5
#       url: "/community"

####
#
# Mode: Multi Group, Single Event
#
# Use-cases: A conference that wants to have a website for this specific conference event only, but have many "community groups". E.g. Web Designers, Backend Developers, etc.
#
####
#
# permalinks:
#   events: /event/
#
# menu:
#   main:
#     - name: "Home"
#       weight: 1
#       url: "/"
#     - name: "Groups"
#       weight: 2
#       url: "/groups"
#     - name: "Event"
#       weight: 3
#       url: "/event"
#     - name: "Speakers"
#       weight: 4
#       url: "/speakers"
#     - name: "Community"
#       weight: 5
#       url: "/community"
#   footer:
#     - name: "Home"
#       weight: 1
#       url: "/"
#     - name: "Groups"
#       weight: 2
#       url: "/groups"
#     - name: "Event"
#       weight: 3
#       url: "/event"
#     - name: "Speakers"
#       weight: 4
#       url: "/speakers"
#     - name: "Community"
#       weight: 5
#       url: "/community"

      
####
#
# Mode: Multi Group, Many Events
#
# Use-cases: A website that is a "platform" for many local groups,communities. E.g. showing all of the  groups for a certain technology that are within a given country.
#
####
#
# menu:
#   main:
#     - name: "Home"
#       weight: 1
#       url: "/"
#     - name: "Groups"
#       weight: 2
#       url: "/groups"
#     - name: "Events"
#       weight: 3
#       url: "/events"
#     - name: "Speakers"
#       weight: 4
#       url: "/speakers"
#     - name: "Community"
#       weight: 5
#       url: "/community"
#   footer:
#     - name: "Home"
#       weight: 1
#       url: "/"
#     - name: "Groups"
#       weight: 2
#       url: "/groups"
#     - name: "Events"
#       weight: 3
#       url: "/events"
#     - name: "Speakers"
#       weight: 4
#       url: "/speakers"
#     - name: "Community"
#       weight: 5
#       url: "/community"

#####
#
# Community Theme Parameters
#
# These are parameters specifically for changing the functionality of the community theme.
# We recommend you adjust these as needed.
#
#####

params:
  author:                            "Chris Reddington"
  disqus_enabled:                    true 
  facebook:
    app_id: ""
    admins: ""
  footer:
    copyright:                        "Copyright © 2020 Your Name Here."
    contacts:                         
       - key: "email"
         value: "hello@somewhere.com"
  github:                           "chrisreddington"
  github_repo:                      "https://github.com/chrisreddington/hugo-community"
  github_repo_subfolder:            "exampleSite/"    
  home:
    events:                         3
    jumbotron:
      heading:                      "Community - The community theme for hugo"
      text:                         "Welcome to our little community, we hope that you like it here. We're an open and inclusive environment, dedicated to help each other learn and grow. We would love your help to continue growing our community. Please explore our page to find more details!"
      buttonText:                   "Contact"
      buttonUrl:                    "/"
    speakers:                       6
  group_configuration:              "multi"
  event_configuration:              "single"
  show_last_updated:                true
  twitter:                          "reddobowen"

#####
#
# Site Required Settings
#
# The below are required for taxonomies to function correctly in Hugo, as well as the
# manifest.json to be generated for the Progress Web App Functionality.
#
# Please do not remove the taxonomies that are already set.
# If you decide to update the theme and add additional taxonomies, please add to the below.
#
#####

taxonomies:
    topic:                          "topics"
    tag:                            "tags"
    communityType:                  "communityTypes"
outputFormats:
  manifest:
    name:                           "manifest"
    baseName:                       "manifest"
    mediaType:                      "application/json"
    notAlternative:                 "true"
outputs:
  home: 
    - "HTML"
    - "MANIFEST"

#####
#
# Site Privacy Settings
#
# Optional - Configure these settings at your own discretion. These settings are built-in to  
# hugo, and allow you to enable/disable options relating to privacy 
# across platforms.
#
# https://gohugo.io/about/hugo-and-gdpr/
#
#####

privacy:
  disqus:
    disable:                        false
  googleAnalytics:
    anonymizeIP:                    true
    disable: false
    respectDoNotTrack:              true
    useSessionStorage:              false
  instagram:
    disable:                        false
    simple:                         false
  twitter:
    disable:                        false
    enableDNT:                      true
    simple:                         false
  vimeo:
    disable:                        true
    enableDNT:                      false
    simple:                         false
  youtube:
    disable:                        false
    privacyEnhanced:                true
```

### Core Site Configuration


| Field Name             | Required | Description                                                                                                                                                                                                                                                                                                                                  | Example                 |
|------------------------|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|
| baseURL                | Yes      | The BaseURL of the hugo website, as shown at https://gohugo.io/getting-started/configuration/#all-configuration-settings                                                                                                                                                                                                                     | http://localhost:1313   |
| defaultContentLanguage | Yes      | Default language to be used across the site.                                                                                                                                                                                                                                                                                                 | en                      |
| disqusShortName        | No       | If you wish to use disqus, then enter your disqus shortname here.                                                                                                                                                                                                                                                                            | hugo-community          |
| enableGitInfo          | Yes      | Recommended to keep this enabled. If you are source controlling your repository, then it will allow hugo to determine when pages were last edited, and populate the lastMod property of the page. Otherwise, for the "last edited" functionality to work, relies upon you manually populating the lastMod frontmatter on your content pages. | true                    |
| languageCode           | Yes      | The default language code for the website. The theme is capable of multi-lingual support. You just need to add additional languages to the config file, and then ensure the appropriate language-code suffixes are set in the file extensions for content.                                                                                   | en-us                   |
| theme                  | Yes      | Name of the theme. Unless you decide to change themes, you should not change this.                                                                                                                                                                                                                                                           | hugo-community          |
| themesDir              | No       | Where the theme directory is stored. If you move the theme directory, you need to update this setting. Hugo looks in the themes directory by default.                                                                                                                                                                                        | themes/                 |
| title                  | Yes      | Title of the site. This will update the title in the Navigation Menu and all ```<title>``` tags across the site.                                                                                                                                                                                                                                   | Community, a Hugo Theme |
| pagination             | Yes      | The number of results to be showed by pagination. Configure this as you prefer. As most views display 3 items per page, we have opted for 15 as a multiple of 3.                                                                                                                                                                             | 15                      |

### Site Rendering Options

| Field Name    | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                             | Example                                                                           |
|---------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| permalinks    | No       | Depending upon the Site Configuration you're choosing, you may require a permalinks section in your site configuration. Permalinks () are used to change the routes that you use to access certain sections of content. This may be required in a configuration such as the "Conference" mode, where you don't want to have a list of events, as the site refers to a single conference. Instead, you could map the events section to the /event/ path. | Several examples provided in the config snippet above for various configurations. |
| menu          | Yes      | This information is used to populate the site's Main Menu and Footer Menu navigation views. Several examples are once again provided in the configuration snippet above, to show example menu displays for each site configuration option.                                                                                                                                                                                                              | Several examples provided in the config snippet above for various configurations. |

### Site Configuration

| Field Name                       | Required | Description                                                                                                                                                                                                                                                                                                        | Example                                           |
|----------------------------------|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------|
| author                           | Yes      | This is required for SEO purposes. Please set this appropriately. This is used in the layout/partials/seo/meta.html file.                                                                                                                                                                                          | Chris Reddington                                  |
| disqus_enabled                   | No       | Boolean to determine whether disqus is enabled on this site. If true, you also need to set the disqusShortname property in the config above.                                                                                                                                                                       | true/false                                        |
| facebook.app_id, facebook.admins | No       | The information in the Facebook subsection can help with your SEO, and is used in the layout/partials/seo/meta.html file.                                                                                                                                                                                          |                                                   |
| footer.copyright                 | Yes      | The copyright information that is displayed in the footer of your site.                                                                                                                                                                                                                                            | Copyright © 2020 Your Name Here.                  |
| footer.contacts                  | Yes      | This is an array. To add additional contact methods, just add additional key/value pairs (note the - in front of the key, to denote that this is a new element in the array).                                                                                                                                      | As shown in the config snippet above.             |
| github                           | No       | The information in this section can help with your SEO, and is used in the layout/partials/seo/meta.html file.                                                                                                                                                                                                     | chrisreddington                                   |
| github_repo                      | No       | This is the base URL of the GitHub repo that you are hosting the website on.  This is used to generate the edit link in the "last edited" section of your site.                                                                                                                                                    | https://github.com/chrisreddington/hugo-community |
| github_repo_subfolder            | No       | This is only needed if your site is stored in a subfolder of your Git repository. This is used to generate the edit link in the "last edited" section of your site.                                                                                                                                                | exampleSite/                                      |
| home.events                      | Yes      | The home section is for configuration related to your homepage. The events property is used to control the number of events (ordered chronologically) shown on the homepage. Be aware that if the **event_configuration** property is set to single, then you will not see this section displayed on the homepage. | 3                                                 |
| home.jumbotron                   | Yes      | This section contains the information to be stored in the homepage's Jumbotron. Sub properties include heading, text, buttonText and buttonUrl. Examples can be found in the configuration sample above.                                                                                                           | 3                                                 |
| home.speakers                    | Yes      | The home section is for configuration related to your homepage. The speakerproperty is used to control the number of speakers (selected at random upon each build of your site) shown on the homepage.                                                                                                             | 6                                                 |
| group_configuration              | Yes      | The suggested configuration for groups on your site. If you are hosting for a single group (e.g a conference event without any smaller groups, or a single meet up group), then set this to single. Otherwise, set this to multi.                                                                                  | single or multi                                   |
| event_configuration              | Yes      | The suggested configuration for events on your site. If you are hosting for a single events (e.g This website is dedicated to a single event, e.g. an annual conference), then set this to single. Otherwise, set this to multi.                                                                                   | single or multi                                   |
| show_last_updated                | No       | Boolean which determines whether the "Last Updated" section/banner of the site should be shown site-wide. This is not required. If this is unset, then it defaults to false and will not show the banner.                                                                                                          | true / false (As a boolean, not a string)         |
| twitter                          | No       | The information in this section can help with your SEO, and is used in the layout/partials/seo/meta.html file                                                                                                                                                                                                      | reddobowen                                        |


### Site Required Settings

There are certain require "base elemenets" for the theme. These include a number of taxonomies, as well as the generation of a manifest.json file, which is used for the Progressive Web App functionality of the theme.

You can safely add additional taxonomies to the theme if you wish, but please do not remove the existing ones that are in place.

### Privacy Settings

There are a number of configuration settings built-in to Hugo to help meet Privacy / Data Protection Regulations. The configuration shown is an example configuration. You should make your own decisions on what privacy settings are required, using the [Hugo and the GEneral Data Protection Regulation Documentation](https://gohugo.io/about/hugo-and-gdpr/).

## Archetypes

Archetypes are a concept within Hugo. They are templates which can be easily used when you want to create new content. You can find more about Archetypes in Hugo [here](https://gohugo.io/content-management/archetypes/).

The Community theme leverages a number of archetypes to deliver the site's content. Please refer to the information below on how to use archetypes, so that you can add additional content to your site.

### Community

To create a new community resource, use the following command in your site folder

```
hugo new community/community-item.md
```

**Note:** Be aware of the different syntax between events/groups and community/speakers. The community example does not require the --kind parameter, as it is a single page, rather than a bundle. This is also why we need to specify the .md extension, to represent that we wish to create a markdown file.

#### Community Frontmatter Details
```
---
#####
# Required
#####
description:                      "Exploring Cloud concepts with Chris Reddington (Welsh Tech Geek, Cloud Advocate, Musical Theatre Enthusiast and Improving Improviser!). We will regularly invite guests to talk about their experiences with the cloud and hear about some of the lessons learned around their cloud journey. Cloud with Chris is a community-driven personal podcast. Content from episodes do not represent the views of any company or organisation."
image:                            "images/cloud-with-chris.png"
title:                            "Chris Reddington"
communityTypes:                   ["Podcast"]
communityUrl:                     "https://www.cloudwithchris.com"

#####
# Optional
#####
# publishDate:                    ""
# topics:                         ["DevOps", "Cloud Architecture"]
# speakers:                       []

#####
# Social - Optional
#####
# facebook:                       ""
# github:                         ""
# linkedin:                       ""
# twitter:                        ""
# twitch:                         ""
# website:                        ""
# youtube:                        ""
---
Description/Information about the Community Resource.
```

| Field Name      | Required | Description                                                                                                                                                                                                                                                                                                                                                                       | Example                                                                                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| description     | Yes      | This is a short summary of the page, which is used for SEO (Search Engine Optimisation purposes) It does not appear to the users, but is used as part of the site's metadata, which is used by search engines. Therefore, it's strongly recommended to set this to something meaningful, as it will have a positive impact on discoverability of your content in public searches. | Exploring Cloud concepts with Chris Reddington (Welsh Tech Geek, Cloud Advocate, Musical Theatre Enthusiast and Improving Improviser!). We will regularly invite guests to talk about their experiences with the cloud and hear about some of the lessons learned around their cloud journey. Cloud with Chris is a community-driven personal podcast. Content from episodes do not represent the views of any company or organisation |
| image           | Yes      | Location of the image which is used when referencing the community resource.                                                                                                                                                                                                                                                                                                      | images/cloud-with-chris.png                                                                                                                                                                                                                                                                                                                                                                                                            |
| title           | Yes      | This is the name of the Community Resource.                                                                                                                                                                                                                                                                                                                                       | Cloud With Chris                                                                                                                                                                                                                                                                                                                                                                                                                       |
| CommunityTypes  | Yes      | The type of this resources, for example Blog, Podcast, Sample Code, etc.                                                                                                                                                                                                                                                                                                          | ["Podcast"]                                                                                                                                                                                                                                                                                                                                                                                                                            |
| communityUrl    | No       | The URL to the community resources                                                                                                                                                                                                                                                                                                                                                | https://www.cloudwithchris.com                                                                                                                                                                                                                                                                                                                                                                                                         |
| publishDate     | No       | Datetime that the speaker should be published on the site (i.e. any builds that you run after this date will display the speaker on the site). Useful if you want to time this with some kind of social media push/press release.                                                                                                                                                 | 2020-12-01T10:00:00Z                                                                                                                                                                                                                                                                                                                                                                                                                   |
| topics          | No       | The list of topics that the speaker is known for. These will appear as tags in the speaker's profile page, and also be used to populate speaker details in the taxonomy pages of the site. This should be an array of strings.                                                                                                                                                    | ["DevOps", "Cloud Architecture"]                                                                                                                                                                                                                                                                                                                                                                                                       |
| speakers        | no       | A list of speakers, in their URLized form (i.e. their filename). This will link the speaker's profile page to the community resource, and also display the speaker's icon next to the item on the community page.                                                                                                                                                                 | ["chris-reddington"]                                                                                                                                                                                                                                                                                                                                                                                                                   |
| social.facebook | No       | The URL of the facebook page to link to.                                                                                                                                                                                                                                                                                                                                          | https://facebook.com/myfacebookpage                                                                                                                                                                                                                                                                                                                                                                                                    |
| social.github   | No       | The GitHub alias/repo that you wish to link to, e.g. chrisreddington or chrisreddington/hugo-community                                                                                                                                                                                                                                                                            | chrisreddington OR chrisreddington/hugo-community                                                                                                                                                                                                                                                                                                                                                                                      |
| social.linkedin | No       | The LinkedIn alias that you wish to link to.                                                                                                                                                                                                                                                                                                                                      | chrisreddington                                                                                                                                                                                                                                                                                                                                                                                                                        |
| social.twitter  | No       | The Twitter handle that you wish to link to.                                                                                                                                                                                                                                                                                                                                      | CloudWithChris                                                                                                                                                                                                                                                                                                                                                                                                                         |
| social.twitch   | No       | The Twitch Page that you wish to link to.                                                                                                                                                                                                                                                                                                                                         | CloudWithChris                                                                                                                                                                                                                                                                                                                                                                                                                         |
| social.website  | No       | The URL of the website that you wish to link to.                                                                                                                                                                                                                                                                                                                                  | https://www.cloudwithchris.com                                                                                                                                                                                                                                                                                                                                                                                                         |
| social.youtube  | No       | The channel that you wish to link to.                                                                                                                                                                                                                                                                                                                                             | CloudWithChris                                                                                                                                                                                                                                                                                                                                                                                                                         |

### Event

To create a new event, use the following command in your site folder

```
hugo new --kind event event/your-intended-directory-name
```

The event archetype contains a bundle of files, including - 
* The _index.md file which contains information about the event itself.
* A subfolder called activities, which can contain many files. These files represent individual sessions/talks/etc. To create more activities, just copy/paste the files in the activities subfolder.
* A subfolder called sponsors, which can contain many files. These files represent sponsors of this particular event. To create more sponsors, just copy/paste the files in the organizers subfolder.

#### Event Frontmatter Details
```
---
#####
# Required
#####
description:          "This is the description for My First Event in Reading Town Center!"
image:                "./images/banner.jpg"
title:                ""
lastMod:              ""
startDate:            "2023-12-25T09:00:00Z"
endDate:              "2023-12-25T10:00:00Z"
publishDate:          "2020-12-01T10:00:00Z" 
location:             "Reading Town Center, Somewhere"

#####
# Optional
#####
# activities_name:    ""
# group:              "meetup-group-london"
# lastMod:            ""
---
Test Event!!!
```
| Field Name      | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Example                                                            |
|-----------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------|
| description     | Yes      | This is a short summary of the page, which is used for SEO (Search Engine Optimisation purposes) It does not appear to the users, but is used as part of the site's metadata, which is used by search engines. Therefore, it's strongly recommended to set this to something meaningful, as it will have a positive impact on discoverability of your content in public searches.                                                                                      | This is the description for My First Event in Reading Town Center! |
| image           | Yes      | Location of the banner which is shown on the event page. If using the site in a "Multi Event" mode, then it also displays the event banner in any relevant event listings.                                                                                                                                                                                                                                                                                             | https://via.placeholder.com/150                                    |
| title           | Yes      | This is the name of the event.                                                                                                                                                                                                                                                                                                                                                                                                                                         | Contoso of London                                                  |
| startDate       | Yes      | Datetime that the event starts. This is used for display purposes on the website, and will be rendered in a more user friendly format. If the site is in a multi-event configuration, then it will be used to order the events chronologically.                                                                                                                                                                                                                        | 2023-12-25T09:00:00Z                                               |
| endDate         | Yes      | Datetime that the event finishes. This is used for display purposes on the website, and will be rendered in a more user friendly format.                                                                                                                                                                                                                                                                                                                               | 2023-12-25T09:00:00Z                                               |
| publishDate     | No       | Datetime that the speaker should be published on the site (i.e. any builds that you run after this date will display the speaker on the site). Useful if you want to time this with some kind of social media push/press release.                                                                                                                                                                                                                                      | 2020-12-01T10:00:00Z                                               |
| location        | No       | Plain text that is displayed for the "Location" of the event. Could easily be adjusted to show "Virtual Event" / "Microsoft Teams Meeting" / "Zoom Call" if this is not a physical event.                                                                                                                                                                                                                                                                              |                                                                    |
| activities_name | No       | Used as an override of the name that describes the activities associated. For example, "Talks", "Lessons", "Sessions", etc. allowing flexibility for different event types.                                                                                                                                                                                                                                                                                            | "Sessions"                                                         |
| group           | No       | The URLized version of the group (The folder name). This is used, so that the group that is associated with the event can be displayed on the event. Additionally, the event will also be available on the group's page. This is optional, and not really required in a "Single Group" configuration of the site, but is particularly useful in a "Multi Group" configuration for a cohesive experience.                                                               | meetup-group-london                                                |
| lastMod         | No       | Datetime that the file was last modified. This is not necessary if you are storing the source in a Git Repository and have the enableGitInfo parameter set in Site Configuration. In that scenario, hugo will set the last modified value of the page to the last commit in Version Control. Otherwise, if you have enable_last_updated set to true, and are not using Git/enableGitInfo, then you will need to set the lastMod property manually in your frontmatter. | 2020-12-01T10:00:00Z                                               |


#### Event Activity Frontmatter Details
```
---
---
#####
# Required
#####
title:                  "DevOps in a Cloud World"
publishDate:            ""

#####
# Optional
#####
# speakers:               ["chris-reddington"]
# startDate:              "2020-12-25T09:00:00Z"
# endDate:                "2020-12-25T10:00:00Z"
# event_track:            "DevOps"
# location:               ""
# topics:                 ["Azure DevOps", "GitHub"]

#####
# Please do not remove or change the below front matter.
#####
page_type:                "activity"
private:                  true
---
Some information/background about the activity here (e.g. session description)
```
| Field Name      | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Example                                           |
|-----------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------|
| title           | Yes      | This is the name of the activity, e.g. The name of the session/talk.                                                                                                                                                                                                                                                                                                                                                                                                   | DevOps in a Cloud World                           |
| publishDate     | No       | Datetime that the activity should be published on the site (i.e. any builds that you run after this date will display the speaker on the site). Useful if you want to time this with some kind of social media push/press release.                                                                                                                                                                                                                                     | 2020-12-01T10:00:00Z                              |
| speakers        | No       | A list of speakers, in their URLized form (i.e. their filename). This will link the speaker's profile page to the event, and also display the speaker's icon next to the activity on the event page.                                                                                                                                                                                                                                                                   | ["chris-reddington"]                              |
| startDate       | No       | Datetime that the activity starts. This is used for display purposes on the website, and will be rendered in a more user friendly format. This also helps display the schedule of the event in a chronological order.                                                                                                                                                                                                                                                  | 2020-12-01T10:00:00Z                              |
| endDate         | No       | Datetime that the activity finishes. This is used for display purposes on the website, and will be rendered in a more user friendly format.                                                                                                                                                                                                                                                                                                                            | 2020-12-01T10:00:00Z                              |
| event_track     | No       | Additional metadata to be associated with an activity. If there are multiple tracks in an event, then it will render a tabbed layout to switch between the tracks of the event. E.g. A track of sessions on DevOps, a track of sessions on Cloud Architecture, etc.                                                                                                                                                                                                    | DevOps                                            |
| location        | No       | Location of this particular activity, e.g. rom number. Useful if being use for a conference type event, where there is one overall location, but activities (e.g. sessions) would beheld in different rooms in a conference venue                                                                                                                                                                                                                                    | Room 101                                                 |
| topics          | No       | The list of topics that the activity is associated with. These will appear as tags on the event's page, and also be used to populate event details in the topics taxonomy page of the site. This should be an array of strings.                                                                                                                                                                                                                                        | ["Azure DevOps", "GitHub"]                                           |
| page_type       | Yes - Don't change | This extra metadata is required to power the queries used in the theme to display the organizers in appropriate places for groups.                                                                                                 | Must be set to **organizer**                      |
| private         | Yes                | If this property is set to "false" or unset, then this page will show up in the sitemap. Otherwise, it will not. There may be future work to remove this property, and determine that based upon the group_configuration option. | true / false                                      |

#### Event Sponsor Frontmatter Details
```
---
#####
# Required
#####
image:                "https://via.placeholder.com/150"
title:                "Contoso Conferences"

#####
# Social - Optional
#####
# facebook:                       ""
# github:                         ""
# linkedin:                       ""
# twitter:                        ""
# twitch:                         ""
# website:                        ""
# youtube:                        ""

#####
# Please do not remove or change the below front matter.
#####
page_type:                        "sponsor"
private:                          true
---
Some information about the sponsor here.
```

| Field Name      | Required           | Description                                                                                                                                                                                                                      | Example                                           |
|-----------------|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------|
| image           | Yes                | Location of the image which is used when referencing the sponsor.                                                                                                                                                                | https://via.placeholder.com/150                   |
| title           | Yes                | This is the name of the sponsor.                                                                                                                                                                                                 | Contoso of London                                 |
| social.facebook | No                 | The URL of the facebook page to link to.                                                                                                                                                                                         | https://facebook.com/myfacebookpage               |
| social.github   | No                 | The GitHub alias/repo that you wish to link to, e.g. chrisreddington or chrisreddington/hugo-community                                                                                                                           | chrisreddington OR chrisreddington/hugo-community |
| social.linkedin | No                 | The LinkedIn alias that you wish to link to.                                                                                                                                                                                     | chrisreddington                                   |
| social.twitter  | No                 | The Twitter handle that you wish to link to.                                                                                                                                                                                     | CloudWithChris                                    |
| social.twitch   | No                 | The Twitch Page that you wish to link to.                                                                                                                                                                                        | CloudWithChris                                    |
| social.website  | No                 | The URL of the website that you wish to link to.                                                                                                                                                                                 | https://www.cloudwithchris.com                    |
| social.youtube  | No                 | The channel that you wish to link to.                                                                                                                                                                                            | CloudWithChris                                    |
| show_tabs       | Yes                | Boolean value to determine whether the page should show in the "Tabs" view on the group page.                                                                                                                                    | true / false                                      |
| page_type       | Yes - Don't change | This extra metadata is required to power the queries used in the theme to display the sponsors in appropriate places for groups.                                                                                                 | Must be set to **sponsor**                        |
| private         | Yes                | If this property is set to "false" or unset, then this page will show up in the sitemap. Otherwise, it will not. There may be future work to remove this property, and determine that based upon the group_configuration option. | true / false                                      |


#### Single Event Sites

Additional information, TBC

#### Multi Event Sites

Additional information, TBC

### Group


To create a new group, use the following command in your site folder

```
hugo new --kind group group/your-intended-directory-name
```

The group archetype contains a bundle of files, including - 
* The _index.md file which contains information about the group itself.
* Several additional optional markdown files in the **your-intended-directory-name** folder. These can be shown using the tabbed interface of the Group page. Do take note of the frontmatter that drives this functionality. Details on these can be found in the comments of the example markdown files in the [archetypes/group folder](https://github.com/chrisreddington/hugo-community/tree/main/archetypes/group) folder.
* A subfolder called organizers, which can contain many files. These files represent organizers of this particular event. To create more organizers, just copy/paste the files in the organizers subfolder.
* A subfolder called sponsors, which can contain many files. These files represent sponsors of this particular event. To create more sponsors, just copy/paste the files in the organizers subfolder.

#### Group Frontmatter Details
```
---
#####
# Required
#####
description:                      "A fictitious Technical Community for the theme demo."
image:                            "./images/london.jpg"
title:                            "London Meetup Group"

#####
# Social - Optional
#####
# facebook:                       ""
# github:                         ""
# linkedin:                       ""
# twitter:                        ""
# twitch:                         ""
# website:                        ""
# youtube:                        ""

#####
# Please do not remove or change the below front matter.
#####
layout:                           "multi-group-single"
show_tabs:                        false
---
Enter your page's content here.
```

| Field Name      | Required | Description                                                                                                                                                                                                                                                                                                                                                                       | Example                                                                             |
|-----------------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|
| description     | Yes      | This is a short summary of the page, which is used for SEO (Search Engine Optimisation purposes) It does not appear to the users, but is used as part of the site's metadata, which is used by search engines. Therefore, it's strongly recommended to set this to something meaningful, as it will have a positive impact on discoverability of your content in public searches. | A fictitious Technical Community for the purposes of the Hugo Community theme demo. |
| image           | Yes      | Location of the banner which is shown on the group page. If using the site in a "Multi Group" mode, then it also displays the group banner in any relevant group listings.                                                                                                                                                                                                        | images/london.jpg                                                                   |
| title           | Yes      | This is the "User friendly" name of the group.                                                                                                                                                                                                                                                                                                                                    | London Meetup Group                                                                 |
| social.facebook | No       | The URL of the facebook page to link to.                                                                                                                                                                                                                                                                                                                                          | https://facebook.com/myfacebookpage                                                 |
| social.github   | No       | The GitHub alias/repo that you wish to link to, e.g. chrisreddington or chrisreddington/hugo-community                                                                                                                                                                                                                                                                            | chrisreddington OR chrisreddington/hugo-community                                   |
| social.linkedin | No       | The LinkedIn alias that you wish to link to.                                                                                                                                                                                                                                                                                                                                      | chrisreddington                                                                     |
| social.twitter  | No       | The Twitter handle that you wish to link to.                                                                                                                                                                                                                                                                                                                                      | CloudWithChris                                                                      |
| social.twitch   | No       | The Twitch Page that you wish to link to.                                                                                                                                                                                                                                                                                                                                         | CloudWithChris                                                                      |
| social.website  | No       | The URL of the website that you wish to link to.                                                                                                                                                                                                                                                                                                                                  | https://www.cloudwithchris.com                                                      |
| social.youtube  | No       | The channel that you wish to link to.                                                                                                                                                                                                                                                                                                                                             | CloudWithChris                                                                      |
| layout          | Yes      | This is a native-hugo property, and is used to override which underlying layout hugo uses to generate the page. Please see the details in the single group / multi group site sections below.                                                                                                                                                                                     | See below.                                                                          |
| show_tabs       | Yes      | Boolean value to determine whether the page should show in the "Tabs" view on the group page. For any non index/_index file, then you should set to true, so that it can be shown in the list of menu items on the group's page in multi-group mode.                                                                                                                                                                                                                                                                                    | true / false                                                                        |

#### Group Organizer Frontmatter Details
```
---
#####
# Required
#####
image:                "images/chris-reddington.jpg"
title:                "Chris Reddington"

#####
# Social - Optional
#####
# facebook:                       ""
# github:                         ""
# linkedin:                       ""
# twitter:                        ""
# twitch:                         ""
# website:                        ""
# youtube:                        ""

#####
# Please do not remove or change the below front matter.
#####
page_type:                        "organizer"
private:                          true
---
Welsh Tech Geek, Cloud Advocate, Musical Theatre Enthusiast and Improving Improviser!

Chris is currently a Senior Engineer on Microsoft's [FastTrack for Azure](https://azure.microsoft.com/en-gb/programs/azure-fasttrack/) team.
Enter your page's content here.
```

| Field Name      | Required           | Description                                                                                                                                                                                                                      | Example                                           |
|-----------------|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------|
| image           | Yes                | Location of the image which is used when referencing the organizer.                                                                                                                                                              | images/chris-reddington.jpg                       |
| title           | Yes                | This is the name of the organizer.                                                                                                                                                                                               | Chris Reddington                                  |
| social.facebook | No                 | The URL of the facebook page to link to.                                                                                                                                                                                         | https://facebook.com/myfacebookpage               |
| social.github   | No                 | The GitHub alias/repo that you wish to link to, e.g. chrisreddington or chrisreddington/hugo-community                                                                                                                           | chrisreddington OR chrisreddington/hugo-community |
| social.linkedin | No                 | The LinkedIn alias that you wish to link to.                                                                                                                                                                                     | chrisreddington                                   |
| social.twitter  | No                 | The Twitter handle that you wish to link to.                                                                                                                                                                                     | CloudWithChris                                    |
| social.twitch   | No                 | The Twitch Page that you wish to link to.                                                                                                                                                                                        | CloudWithChris                                    |
| social.website  | No                 | The URL of the website that you wish to link to.                                                                                                                                                                                 | https://www.cloudwithchris.com                    |
| social.youtube  | No                 | The channel that you wish to link to.                                                                                                                                                                                            | CloudWithChris                                    |
| show_tabs       | Yes                | Boolean value to determine whether the page should show in the "Tabs" view on the group page.                                                                                                                                    | true / false                                      |
| page_type       | Yes - Don't change | This extra metadata is required to power the queries used in the theme to display the organizers in appropriate places for groups.                                                                                                 | Must be set to **organizer**                      |
| private         | Yes                | If this property is set to "false" or unset, then this page will show up in the sitemap. Otherwise, it will not. There may be future work to remove this property, and determine that based upon the group_configuration option. | true / false                                      |

#### Group Sponsor Frontmatter Details
```
---
#####
# Required
#####
image:                "https://via.placeholder.com/150"
title:                "Contoso of London"

#####
# Social - Optional
#####
# facebook:                       ""
# github:                         ""
# linkedin:                       ""
# twitter:                        ""
# twitch:                         ""
# website:                        ""
# youtube:                        ""

#####
# Please do not remove or change the below front matter.
#####
page_type:                        "sponsor"
private:                          true
---
Some information about the sponsor here.
```

| Field Name      | Required           | Description                                                                                                                                                                                                                      | Example                                           |
|-----------------|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------|
| image           | Yes                | Location of the image which is used when referencing the sponsor.                                                                                                                                                                | https://via.placeholder.com/150                   |
| title           | Yes                | This is the name of the sponsor.                                                                                                                                                                                                 | Contoso of London                                 |
| social.facebook | No                 | The URL of the facebook page to link to.                                                                                                                                                                                         | https://facebook.com/myfacebookpage               |
| social.github   | No                 | The GitHub alias/repo that you wish to link to, e.g. chrisreddington or chrisreddington/hugo-community                                                                                                                           | chrisreddington OR chrisreddington/hugo-community |
| social.linkedin | No                 | The LinkedIn alias that you wish to link to.                                                                                                                                                                                     | chrisreddington                                   |
| social.twitter  | No                 | The Twitter handle that you wish to link to.                                                                                                                                                                                     | CloudWithChris                                    |
| social.twitch   | No                 | The Twitch Page that you wish to link to.                                                                                                                                                                                        | CloudWithChris                                    |
| social.website  | No                 | The URL of the website that you wish to link to.                                                                                                                                                                                 | https://www.cloudwithchris.com                    |
| social.youtube  | No                 | The channel that you wish to link to.                                                                                                                                                                                            | CloudWithChris                                    |
| show_tabs       | Yes                | Boolean value to determine whether the page should show in the "Tabs" view on the group page.                                                                                                                                    | true / false                                      |
| page_type       | Yes - Don't change | This extra metadata is required to power the queries used in the theme to display the sponsors in appropriate places for groups.                                                                                                 | Must be set to **sponsor**                        |
| private         | Yes                | If this property is set to "false" or unset, then this page will show up in the sitemap. Otherwise, it will not. There may be future work to remove this property, and determine that based upon the group_configuration option. | true / false                                      |

#### Single Group Sites

Additional information, TBC

#### Multi Group Sites

Additional information, TBC

### Speaker

To create a new group, use the following command in your site folder

```
hugo new speaker/speaker-name.md
```

**Note:** Be aware of the different syntax between events/groups and community/speakers. The community example does not require the --kind parameter, as it is a single page, rather than a bundle. This is also why we need to specify the .md extension, to represent that we wish to create a markdown file.

#### Speaker Frontmatter Details
```
---
#####
# Required
#####
description:                      "Chris is a Welsh Tech Geek, Cloud Advocate, Musical Theatre Enthusiast and Improving Improviser! He is  currently a Senior Engineer on Microsoft's FastTrack for Azure team."
image:                            "img/speakers/chris-reddington.jpg"
title:                            "Chris Reddington"

#####
# Optional
#####
# lastmod:                        ""
# pronouns:                       ""
# publishDate:                    ""
# topics:                         []

#####
# Social - Optional
#####
# facebook:                       ""
# github:                         ""
# linkedin:                       ""
# twitter:                        ""
# twitch:                         ""
# website:                        ""
# youtube:                        ""
---
Welsh Tech Geek, Cloud Advocate, Musical Theatre Enthusiast and Improving Improviser!

Chris is currently a Senior Engineer on Microsoft's [FastTrack for Azure](https://azure.microsoft.com/en-gb/programs/azure-fasttrack/) team.
```

| Field Name      | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Example                                           |
|-----------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------|
| description     | Yes      | This is a short summary of the page, which is used for SEO (Search Engine Optimisation purposes) It does not appear to the users, but is used as part of the site's metadata, which is used by search engines. Therefore, it's strongly recommended to set this to something meaningful, as it will have a positive impact on discoverability of your content in public searches.                                                                                      |                                                   |
| image           | Yes      | Location of the image which is used when referencing the speaker.                                                                                                                                                                                                                                                                                                                                                                                                      | https://via.placeholder.com/150                   |
| title           | Yes      | This is the name of the speaker.                                                                                                                                                                                                                                                                                                                                                                                                                                       | Contoso of London                                 |
| lastMod         | No       | Datetime that the file was last modified. This is not necessary if you are storing the source in a Git Repository and have the enableGitInfo parameter set in Site Configuration. In that scenario, hugo will set the last modified value of the page to the last commit in Version Control. Otherwise, if you have enable_last_updated set to true, and are not using Git/enableGitInfo, then you will need to set the lastMod property manually in your frontmatter. | 2020-12-01T10:00:00Z                              |
| pronouns        | No       | The speaker's preferred pronouns.                                                                                                                                                                                                                                                                                                                                                                                                                                      | He/him, She/her, They/Them                        |
| publishDate     | No       | Datetime that the speaker should be published on the site (i.e. any builds that you run after this date will display the speaker on the site). Useful if you want to time this with some kind of social media push/press release.                                                                                                                                                                                                                                          | 2020-12-01T10:00:00Z                              |
| topics          | No       | The list of topics that the speaker is known for. These will appear as tags in the speaker's profile page, and also be used to populate speaker details in the taxonomy pages of the site. This should be an array of strings.                                                                                                                                                                                                                                         | ["GitHub", "Kubernetes", "Azure DevOps"]          |
| social.facebook | No       | The URL of the facebook page to link to.                                                                                                                                                                                                                                                                                                                                                                                                                               | https://facebook.com/myfacebookpage               |
| social.github   | No       | The GitHub alias/repo that you wish to link to, e.g. chrisreddington or chrisreddington/hugo-community                                                                                                                                                                                                                                                                                                                                                                 | chrisreddington OR chrisreddington/hugo-community |
| social.linkedin | No       | The LinkedIn alias that you wish to link to.                                                                                                                                                                                                                                                                                                                                                                                                                           | chrisreddington                                   |
| social.twitter  | No       | The Twitter handle that you wish to link to.                                                                                                                                                                                                                                                                                                                                                                                                                           | CloudWithChris                                    |
| social.twitch   | No       | The Twitch Page that you wish to link to.                                                                                                                                                                                                                                                                                                                                                                                                                              | CloudWithChris                                    |
| social.website  | No       | The URL of the website that you wish to link to.                                                                                                                                                                                                                                                                                                                                                                                                                       | https://www.cloudwithchris.com                    |
| social.youtube  | No       | The channel that you wish to link to.                                                                                                                                                                                                                                                                                                                                                                                                                                  | CloudWithChris                                    |