# transportRequestUploadFile

## Description
Uploads a file to a Transport Request for a Change Document on the Solution Manager.

## Prerequisites
* **[Change Management Client 2.0.0 or compatible version](http://central.maven.org/maven2/com/sap/devops/cmclient/dist.cli/)** - available for download on Maven Central.

## Parameters
| parameter        | mandatory | default                                                | possible values    |
| -----------------|-----------|--------------------------------------------------------|--------------------|
| `script`        | yes       |                                                    |                    |
| `changeDocumentId`        | yes       |                                                    |                    |
| `transportRequestId`| yes   |                                                    |                    |
| `applicationId`  | yes       |                                                    |                    |
| `filePath`        | yes       |                                                    |                    |
| `credentialsId`  | yes       |                                                    |                    |
| `endpoint`        | yes       |                                                    |                    |

* `script` - The common script environment of the Jenkinsfile running. Typically the reference to the script calling the pipeline step is provided with the `this` parameter, as in `script: this`. This allows the function to access the [`commonPipelineEnvironment`](commonPipelineEnvironment.md) for retrieving, for example, configuration parameters.
* `changeDocumentId` - The id of the change document related to the transport request to release.
* `transportRequestId` - The id of the transport request to release.
* `applicationId` - The id of the application.
* `filePath` - The path of the file to upload.
* `credentialsId` - The credentials to connect to the Solution Manager.
* `endpoint` - The address of the Solution Manager.

## Step configuration
The following parameters can also be specified as step parameters using the global configuration file:

* `credentialsId`
* `endpoint`

## Return value
None.

## Exceptions
* `AbortException`:
    * If the change id is not provided.
    * If the transport request id is not provided.
    * If the application id is not provided.
    * If the file path is not provided.
    * If the upload fails.

## Example
```groovy
transportRequestUploadFile script:this, changeDocumentId: '001', transportRequestId: '001', applicationId: '001', filePath: '/path'
```

