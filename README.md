# Django ToDo list

This is a todo list web application with basic features of most web apps, i.e., accounts/login, API, and interactive UI. To do this task, you will need:

- CSS | [Skeleton](http://getskeleton.com/)
- JS  | [jQuery](https://jquery.com/)

## Explore

Try it out by installing the requirements (the following commands work only with Python 3.8 and higher, due to Django 4):

```
pip install -r requirements.txt
```

Create a database schema:

```
python manage.py migrate
```

And then start the server (default is http://localhost:8000):

```
python manage.py runserver
```

Now you can browse the [API](http://localhost:8000/api/) or start on the [landing page](http://localhost:8000/).

## Task

Create a kubernetes manifest for a pod which will containa ToDo app container:

1. Fork this repository.
1. Create a `pv.yml` file for `PersistentVolume` resource.
1. `PersistentVolume` requirements:
3.1. `PersistentVolume` class `standard`
3.2. `PersistentVolume` persistentVolumeReclaimPolicy `Delete`
3.3. `PersistentVolume` accessModes `ReadWriteMany`
3.4. `PersistentVolume` capacity `1Gi`
3.5. `PersistentVolume` type `hostPath`
1. Create a `pvc.yml` file for `PersitentVolumeClaim` resource.
1. `PersitentVolumeClaim` requirements:
5.1. `PersitentVolumeClaim` should claim a `PersistentVolume` from a pvc file.
5.2. `Deployment` should use `PersistentVolume` throught the `PersitentVolumeClaim`
5.3 `PersistentVolume` mount path should be `/app/data`
1. Mount existing configMap as file into /app/configs folder inside container.
1. Mount existing secret as files into /app/secrets folder inside container
1. `README.md` should have commands to apply all the changes
1. `README.md` should have instructuions on how to validate the changes
1. Create PR with your changes and attach it for validation on a platform.
