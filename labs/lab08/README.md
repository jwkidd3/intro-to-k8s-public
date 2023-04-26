# Lab 08 - StatefulSets and Jobs

You’re going to run the Nginx web server in a StatefulSet, where each Pod writes log files to a PVC of its own, and then you’ll run a Job that prints the size of each Pod’s log file. The basic pieces are there for you, so it’s about applying some of the techniques from the chapter.

The starting point is the Nginx spec in ch08/lab/nginx, which runs a single Pod writing logs to an EmptyDir volume.

The Pod spec needs to be migrated to a StatefulSet definition, which is configured to run with three Pods and provide separate storage for each of them.

When you have the StatefulSet working, you should be able to make calls to your Service and see the log files being written in the Pods.

Then you can complete the Job spec in the file disk-calc-job.yaml, adding the volume mounts so it can read the log files from the Nginx Pods.