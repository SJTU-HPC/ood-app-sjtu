# ood-app-sjtu

[![GitHub License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)

OOD (Open OnDemand) Application Collection for [SJTU Center for High Performance Computing](https://docs.hpc.sjtu.edu.cn/).

## Prerequisites

This Batch Connect app requires the following software be installed on the
**compute nodes** that the batch job is intended to run on (**NOT** the
OnDemand node):

- [Lmod] 6.0.1+ or any other `module purge` and `module load <modules>` based
  CLI used to load appropriate environments within the batch job before
  launching Code server.
- [Singularity] 3.6.0+

[Singularity]: https://sylabs.io/singularity/
[Lmod]: https://www.tacc.utexas.edu/research-development/tacc-projects/lmod

## Install

1. Use Git to clone this app and checkout the desired branch/version you want to
use and place this wherever you store batch connect apps (`/var/www/ood/apps/sys` or `~/ondemand/dev`):

    ```sh
    git clone <repo>
    cd <dir>
    git checkout <tag/branch>
    ln -s <app> /var/www/ood/apps/sys/<app>
    ```

3. Update the related infomation in the script like the path to singularity image.

4. Update form.yml to use the correct cluster, and any other changes as necessary to form.yml or submit.yml that is appropriate for your cluster.

## Update

To update the app you would:

```sh
cd <dir>
git fetch
git checkout <tag/branch>
```

Again, you do not need to restart the app as it isn't a Passenger app.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
