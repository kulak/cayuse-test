# README

This project is for .NET Core 2.2 and is maintained in `Visual Studio Code`.

As a result it doesnot have a typical "Visual Studio" solution file out of the box.

## STATUS

work in progress

## Command Line Reference

All commands assume that you are in the root directory of this repository.

If running from directory of the target project (web service app or test project), then project identification is not necessary.

### Build

    dotnet build

### Run and Test Environment

Application requuires configuration of service keys.  Keys can come from the following sources:

* `appsettings.json` or `appsettings.{environment}.json`;
* environment variables prefixed with `CAYUSE_`.

For the list of parameters to set check `appsettings.json` file.  

Make sure that if using environment variable prefix `CAYUSE_` is added to each parameter listed in `appsettings.json` file.

Note: The inconvenience is largely driven by public nature of the project and the need to keep keys private.


### Run Web Service

    dotnet run --project .\Demo-WebApp\Demo-WebApp.csproj

Main URL for the purpose of this exercise: <http://localhost:5000/api/location/descriptionbyzip/99037>

Test URLs:

* <http://localhost:5000/api/location/weatherbyzip?zipcode=99037>
* <http://localhost:5000/api/location/timezonebyzip?zipcode=99037>
* <http://localhost:5000/api/location/elevationbyzip?zipcode=99037>
* <http://localhost:5000/api/location/allbyzip?zipcode=99037>

### Run Tests

    dotnet test .\Demo-WebApp-Test\

or if you want to see output generated by tests:

    dotnet test .\Demo-WebApp-Test\ -l:trx

and check content of *.trx files in TestResults directory.

## References

* [Time Zone API](https://developers.google.com/maps/documentation/timezone/intro)
* [Elevation API](https://developers.google.com/maps/documentation/elevation/start)
