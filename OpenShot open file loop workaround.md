# OpenShot open file loop

OpenShot sometimes goe sinto a loop looking for missing files.

## Reference

Documented on Github repositories:

[Issue 1118 / Openshot-QT](https://github.com/OpenShot/openshot-qt/issues/1118) Marked resolved but bug is still preventing normal behavior on latest release!


[Issue 3047 / Openshot-QT](https://github.com/OpenShot/openshot-qt/issues/3047) Marked duplicate.



## Workaround

[My YouTube demonstration](https://www.youtube.com/watch?v=GnyaQah-QV4)

Delete user configuration directory:

```

cd  ~/openshot_qt

rm -rf *

```

This restores OpenShot to its first running state.

