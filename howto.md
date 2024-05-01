# Part-1
# Move an App from one region to another

Often times, developers would want to relocate their app's Fly Machine and Fly Volume from one region to another due to various reasons. For example, if your users are primarily centered around a specific region while your pre-existing machine and its associated volume is located in another region.


So, in such scenarios, developers can change their app's machine and volume into their desired region via a combination of `fly scale` command which allows you to scale your app to your desired region, followed by `fly destroy` command to destroy the unnecessary pre-existing machine and volume.

__`fly scale count 1 --region <target_region>`__

This command will let you scale your app by another single instance in the desired target region specified using the `--region` flag(you can see a list of regions [here](https://fly.io/docs/reference/regions/). This will create a new machine and volume for your app in the desired region.

Once this is done, you can destroy your previously existing, unnecessary machines and volume.

__`fly machines destroy <machine_id>`__
__`fly volumes destroy <volume_id>`__

You can then re-check the resources for your app via the `fly scale show` command.
