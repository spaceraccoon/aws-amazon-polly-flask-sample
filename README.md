# Amazon Polly Flask Sample
Amazon Polly implementation that mirrors the [Python example](http://docs.aws.amazon.com/polly/latest/dg/examples-python.html) provided by AWS, only using the Flask framework. This cuts down the number of lines in server.py by 50% while preserving the same functionality.

## Installation
1. [Install](http://docs.aws.amazon.com/cli/latest/userguide/installing.html) the AWS Command Line Interface and [configure](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html) it.
2. Install the additional dependencies `flask` and `botocore3`.
3. Clone the repository and `cd` into it.
4. Run `python server.py`.
5. By default, the app will now be running at `http://localhost:8000/`.

## Tips
The standard `aws configure` adds a `default` profile instead of `adminuser`, so if you try to run `server.py` immediately after configuring AWS CLI you might get a `botocore.exceptions.ProfileNotFound: The config profile (adminuser) could not be found` error.

To fix this, you have to add an `adminuser` profile to your `config` file. On Linux or macOS, this is usually located at `~/.aws/config`. On Windows, this is `C:\Users\USERNAME \.aws\config`

Simply add the following at the bottom of the file.

```
[profile adminuser]
region = INSERT REGION
output = INSERT JSON
aws_access_key_id = INSERT ACCESS KEY ID
aws_secret_access_key = INSERT SECRET ACCESS KEY
```

You can simply use the same values as those under the `default` user.
