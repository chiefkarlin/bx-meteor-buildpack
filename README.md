# Meteor Buildpack for Bluemix

[![Deploy to Bluemix](https://bluemix.net/deploy/button.png)](https://bluemix.net/deploy)

A Bluemix buildpack for Meteor v1.3+, forked from the [meteor horse buildpack](https://github.com/AdmitHub/meteor-buildpack-horse) 

To use this with your meteor app on Bluemix:

1. Download and [install the CloudFoundry or Bluemix CLI](https://console.ng.bluemix.net/docs/cli/index.html#cli) tools
2. Navigate to the root directory of your meteor app:

	    cd <my-app-name>

3. Add a .cfignore file telling Bluemix to ignore your meteor local files:

	    echo ".meteor/local/" >> .cfignore

4. Push your app to Bluemix using this buildpack: 

	    cf push <my-app-name> -b https://github.com/chiefkarlin/bx-meteor-buildpack.git --no-start

4. Create an instance of the mongodb service on Bluemix:

        cf create-service mongodb 100 <my-app-name-mongodb>

5. Bind the mongodb service to your app:

	    cf bind-service <my-app-name> <my-app-name-mongodb>

6. Start the app:

	    cf start <my-app-name>
        
