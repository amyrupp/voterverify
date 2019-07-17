# Voter Registration Verification

This tool automates the checking of whether a given voter, or list of voters, are currently registered to vote.

To use this tool, you will:

* Get a cryptographic key (one time)
* Generate a hash for each voter in your verification list
* Call a web service method, providing your hash(es)
* Read the response for each hash

### Get a key

You'll need credentials to use our endpoint.  Send email to help@register2vote.org stating that you need a key for Voter Verification.

### Generate hashes

Generate a hash for each voter.  Hashes don't contain a voter's personal information, so submitting a hash to us doesn't disclose sensitive data.

This javascript file generates hashes:

  <<makeHash.js>>

Refer to the algorithm in the javascript file if you want to write a similar tool in a different language.

### Call a web service

GET: 1 hash per request
POST: 100 or fewer hashes per request -> json[]

#### GET

https://civintel-endpoints-4r6lbwbrta-uc.a.run.app/api/voter/verify

#### POST

https://civintel-endpoints-4r6lbwbrta-uc.a.run.app/api/voter/verifyList

For Postman users:

  <<Postman config>>

### POWER USERS

Documentation of this API is here: (requires authentication with your Google Cloud account)

https://endpointsportal.civintel.cloud.goog/docs/civintel-endpoints-4r6lbwbrta-uc.a.run.app/0/types/VoterVerification
