# Get Last Succesfull Scan date

Outputs projects across multiple Snyk Organisations in a Group together with the date of the last time issue count was updated.

## Features

`get_projects.py` - gathers project information for entire Snyk Orgnisation. Uses [Snyk's REST API](https://apidocs.snyk.io/).


## Configuration

Install dependencies
```sh
pip install -r requirements.txt
```

Update variables in `get_projects.py`. Get the latest API Version from [Snyk's REST API](https://apidocs.snyk.io/)
```py
API_VERSION = "2024-08-15"
RATE_LIMIT_DELAY = 0.2 (in seconds)
```

## Usage

### Gather project information 

Run the script locally

```sh
python3 get_projects.py --group YOUR_GROUP_ID --token your_api_token
```

Script will output multiple json files split by individual days e.g.`2024-12-09.json` 

```json
[
    {
        "org_name": "Test_Org",
        "org_id": "**************",
        "project_name": "nodejs-goof/nodejs-goof(main)",
        "project_id": "**************",
        "type": "sast",
        "target_file": "",
        "status": "active",
        "issue_count_updated_at": "2024-12-09T23:34:27.293Z"
    }
]
```

