# Welcome to the TraceView OpenShift Cartridge

![TraceView](https://s3.amazonaws.com/pglombardo/traceview-logo.png)
![OpenShift](https://s3.amazonaws.com/pglombardo/openshift-online-logo.png)

This is a downloadable [TraceView](http://www.appneta.com/products/traceview/) cartridge for 
Application Performance Monitoring on [OpenShift](https://www.openshift.com/).

This downloadable cartridge installs the base TraceView libraries required to
properly instrument your OpenShift application.

_This is currently a work in progress.  Currently, you can fully instrument your
Ruby applications on OpenShift by using a combination of this cartridge and the TraceView
[oboe gem](https://github.com/appneta/oboe-ruby).  Other language variations coming
soon._

# Installation

You can add the downloadable cartridge to your OpenShift application via the UI or via the command line.

## Via Command Line

To install the catridge using the `rhc` command via the command-line, run the following:

    rhc cartridge-add https://raw.githubusercontent.com/appneta/openshift-cartridge-traceview/master/metadata/manifest.yml -a My_App_Name

Make sure to replace _My_App_Name_ with the actual OpenShift application name.

If at anytime you wish to remove the cartridge, it can be done with:

    rhc cartridge-remove traceview -a My_App_Name

## Via Web Browser

On your OpenShift application page, click on the link _...see the entire list of cartridges you can add_
at the bottom of the page.  This brings you to a list of installable cartridges.  At the bottom
of the page, you will see an area to _Install your own catridge_ as follows:

![Install your own cartridge](https://s3.amazonaws.com/pglombardo/openshift-install-your-own.png)

Insert the URL of the raw catridge manifest file on Github and click Next:

    https://raw.githubusercontent.com/appneta/openshift-cartridge-traceview/master/metadata/manifest.yml

From there, you will be taken to a confirmation page.  Click _Add Cartridge_ to confirm the installation.

# Summary

Congratulations, the the TraceView cartridge is now installed.  If, by chance you received any errors
or warnings during this process please let us know by contacting us through our [support portal](https://support.tv.appneta.com/) or on IRC @ #appneta on [Freenode](http://freenode.net/).  We appreciate all feedback!

# Ruby

Once the cartridge has been installed, you can instrument your Ruby applications by simply adding the [oboe gem](https://github.com/appneta/oboe-ruby) to your application as detailed in the oboe-ruby [README](https://github.com/appneta/oboe-ruby/blob/master/README.md).

Note:  Make sure that you install the Ruby gem after you add the TraceView cartridge to your application.  If you
fail to do this in this order, the gem will fail to build the bundled c-extension.  In this case, a `gem pristine oboe`
will force the gem to search for a re-link to the TraceView libraries.

