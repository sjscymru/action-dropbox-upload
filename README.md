# Dropbox Uploader

Upload artifacts to Dropbox with no-effort

Use this github-action when you want upload large, small or big dataset of files to Dropbox.

## Usage:

```
    - name: Upload to Dropbox
      id: upload-to-dropbox
      uses: sjscymru/action-dropbox-upload@v1
      env:
        PATH_DROPBOX: /syscymru-github/Demo-Project/Deployment
      with:
        accessToken: ${{ secrets.DROPBOX_ACCESS_TOKEN }}
        destination: ${{ env.PATH_DROPBOX }}
        file: my_file.tar

```

## Dropbox Access Token
You will need to generate an access token in order for this action to access your Dropbox account. To do this visit https://www.dropbox.com/developers/apps to create an App. 

Make sure you give the app the following permission: ```files.content.write```

Copy the access token from the Dropbox developer console into you repository secrets as DROPBOX_ACCESS_TOKEN

## Action Input Parameter Description

### accessToken
Required: true
Description: Dropbox access token. Create new one at:  and then add the tocken
 
### destination
- Required: true
- Description: Dropbox destination path for uploading. Must be started from /". (ex. "/actions")

### pattern
- Required: false
- Description: glob pattern for file (ex. src/**/*)

### file
- required: false
- description: path to specific file (ex. src/main.ts)

### partSizeBytes
- Required: false
- Description: Size of one uploadable chunk in bytes. default: 1024

### displayProgress
- Required: false
- Description: Display file uploading progress logs. default: false

## Action Outputs

### files
- Description: List of files uploaded to Dropbox
