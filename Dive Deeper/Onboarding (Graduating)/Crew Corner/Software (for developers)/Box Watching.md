# Why
We want to be able to detect when a new file lands in Dropbox, to pick it up and process it. This is used in e.g. [[Voice-to-Wiki Pipeline]].
# What
An automation that watches for file changes in a given Dropbox folder and triggers an action. 
# Where

# How
Make allows you to build your own app: https://docs.integromat.com/apps/basics/module. We'll use this to make available an API endpoint for a microservice we've built using FaasD, running on Digital Ocean.