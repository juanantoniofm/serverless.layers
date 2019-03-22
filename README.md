# serverless.layers
A layer provider/collection for AWS Lambda on Python 3.7

If you want to import custom libraries in your AWS λ, you can now use layers.

This collection should get you started faster.

# Using the Layers

You can either:
* Set any of the ARNs above (for your region) to be a layer for your function. For list of all layers, view the `arns.json` file.
* Download the zip file from the directory of your package name (e.g. requests) and upload as a layer to your function

# Building your own layer

To build a layer containing a single python package use the following:

    $ package.sh -p <package_name> -l <license> -r <runtime> -x <public/private> -a <aws_region>

e.g.

    $ package.sh -x public -a ap-southeast-1 -p requests -r python3.7 -l Apache-2.0
    $ package.sh -x private -a ap-southeast-1 -p beautifulsoup4 -r python3.7 -l MIT
    $ package.sh -p sqlite3 -r python3.7 -l Apache-2.0

* -p : (MANDATORY) Package Name
* -l : (MANDATORY) License information for the Package, use the SPDX license identifier
* -r : (MANDATORY) Runtime, currently only python3.7 is supported, but should work for python2.7 and python3.6
* -x : (OPTIONAL) set to public to make layer publicly accessible defaults to private
* -a : (OPTIONAL) and defaults to deploying layer in all aws_regions where lambda is available (except China)

# Asking for more layers

Make a pull requests!

