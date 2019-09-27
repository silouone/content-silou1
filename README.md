content
=======

# Intro

This repo stores all the JSON and YAML files for the Coorpacademy content.

On the branch 'master', you will find the content version that are available on production platforms. For example, if you stay on the 'master' branch and go to the 'pernod-ricard' folder, you will exactly find the content that lives on the pernod-ricard.coorpacademy.com platform.

We will use other branches to keep track of our modifications. For example, the branch 'digital-staging' is used to make modifications on the content, and then import these modifications on the digital-staging.coorpacademy.com platform.

# Workflow

To start working on some modifications, create a new branch from the master branch with the name:

`YYYYMMDD-platform-subject`

where subject is the nature of the work. It could be 'new_discipline' or 'fix' for example.

There should be exactly **one commit per question** in case of a fix. The commit should have the following message:

`platform-fix-question_id`

where question_id could for example be: '01B3_5' or '11C4_8'.

# Scripts

There are two scripts in this repo: `validateJson.js` and `udpateSels.js`.

### validateJson
It goes through the list of all JSON files of a given platform, and remove extra `,` so that the result JSON is valide. To run it, enter

`node scripts/validateJson.js platform` where `platform` can be digital, sfr, pernod-ricard, etc.

### updateSels
It goes through the list of all slide JSON files of a given platform and updates the `__selXXXX__` and `__inpXXXX__` values in the corresponding `yaml` files. To run it, enter:

`node scripts/updateSels.js platform`
