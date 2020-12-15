---
#####
# Required
#####
publishDate: "" # Date that the event should be published on the site (Any builds that you run after this date will display the site). Useful if you want to time this with some kind of social media push/press release.
speakers: ["chris-reddington"] # The urlized version of the group, so that it can be displayed on the group's page.
title: "DevOps in a Cloud World" # Name of the activity, e.g. session name

#####
# Optional
#####
# activity_date: "" # Datetime that this specific activity takes place. e.g. The start time for this particular talk/session.
# event_track: "" # Additional metadata to be associated with an activity if there are multiple "tracks" in the event which should be rendered separately. E.g. A track of sessions on DevOps, a track of sessions on Cloud Architecture, etc.
# location: "" # Location of this particular activity, e.g. rom number. Useful if being use for a conference type event, where there is one overall location, but activities (e.g. sessions) would beheld in different rooms smin a conference venue.
topics: ["Azure DevOps", "GitHub"] # Topic metadata to be associated with the Activity. This will displayed as tags on the page, and will also be available underneath the /topics/ taxonomy on the website.

#####
# Please do not remove or change the below front matter.
#####
type: "activity"      # There is no activity type in the /layouts folder, just like there is deliberately no default single or list. This means this file will not be generated, and positively impacts the build tests.
page_type: "activity" # This is used as part of the queries in /layouts/groups/single.html
private: true         # If false or unset, shows this in siteMap. Otherwise, does not.
---
Some information about the activity here.
