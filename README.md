TQ Systems's Community Yocto BSP
================================

To get the BSP you need to have `repo` installed and use it as:

Install the `repo` utility:

    $: mkdir ~/bin
    $: curl https://dl-ssl.google.com/dl/googlesource/git-repo/repo > ~/bin/repo
    $: chmod a+x ~/bin/repo

NOTE: http://stackoverflow.com/questions/19126603

Download the BSP source:

    $: PATH=${PATH}:~/bin
    $: mkdir tqs-community-bsp
    $: cd tqs-community-bsp
    $: repo init -u https://github.com/lipro/tqs-community-bsp-platform -b dylan
    $: repo sync

Once this has complete, you will have all you need. To start a build, do:

    $: . ./setup-environment build
    $: bitbake core-image-minimal

You can use any directory to host your build.

The source code will be checked out at tqs-community-bsp/sources.

Contributing
------------

To contribute to this layer you should submit the patches for review
to the authors mailing address (rexut95@gmail.com).

Issue tracker:

    https://github.com/lipro/tqs-community-bsp-platform/issues

Source code:

    https://github.com/lipro/tqs-community-bsp-platform

When creating patches, please use something like:

    git format-patch -s --subject-prefix='tqs-community-bsp-platform][PATCH' origin

When sending patches, please use something like:

    git send-email --to rexut95@gmail.com <generated patch>

Using Development and Testing Branches
--------------------------------------

Replace the `repo init` command above with one of the following:

master: for developers

    $: repo init -u https://github.com/lipro/tqs-community-bsp-platform -b master

master-next: for intrepid developers and testers

Patches are typically merged into master-next and then are merged into
master after a testing and comment period. It's possible that master-next
has something you want or need. But it's also possible that using
master-next will break something that was working before. Use with caution.

    $: repo init -u https://github.com/lipro/tqs-community-bsp-platform -b master-next
