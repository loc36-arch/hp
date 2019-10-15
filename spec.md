History Provider (HP): Provides the EMF state history of whatever locations and days are specified.

Request Path Pattern: /locHistory?location={{location id}-{day}[{-another day}...{-another day}]}[_{{location id}-{day}[{-another day}...{-another day}]}..._{{location id}-{day}[{-another day}...{-another day}]}]

Example: /locHistory?location=sx100HIS-20190422-20190532_mjDD3H45-20190732_erTV5451-20191130-20191008

Maximum length of parameter "location": 1024 UTF-8 characters
Maximum number of locations: 32
Maximum number of days for a locations: 32

HTTP response code 200: Success or failure
HTTP response code not 200: Fatal error

Response content would take this format:

{

ServiceID:  "{x}",
Version:  "{z}",
Response: "{a}",
Details:  "{c}",
Data: {
	"{b}": {
		"YYYYMMDD": [
			{State: 0, EndTime: "0856"}, ...
		],
		...
	},
	...
}

}

Possible values of "response code":

rsp0: Request successfully carried out.
rsp1: Invalid request data.
rsp2: An error occured.
