## Roll Your Own Upgrade With A Custom Workflow

One of the differentiators in the marketplace for Cloudify is its ability to automate complex post deployment tasks.  One such task is a rolling upgrade of software in a web server content.  This is a multi-step process that typically involves a coordinated dance between the loadbalancer and the web servers, along with the installation of new content and possibly restarting services.  This post is about a sample implementation of a workflow to automate the process of a zero downtime upgrade of such load balanced resources.

## The Manual Process

It is always a useful (probably essential) exercise in any kind of automation to precisely define the manual steps necessary to accomplish the end goal, and only then attempt automation.  In order to have a more precise description of the process, it is helpful to target a specific technology stack rather than deal in generalizations.  In this simplified walkthrough, we will use our old friend the Nodecellar demo, the [version)(https://github.com/cloudify-cosmo/cloudify-nodecellar-example/tree/3.3.1-build) that includes an HAProxy front end.  The stack looks like:
