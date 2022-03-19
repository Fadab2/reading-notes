# Permissions
* Permissions are a way to grant or deny access to certain resouces.
* Authentication information in the ` request.user` and `request.auth` used to determine permissions.
* The `IsAuthenticated` REST class allows access to only autheticated users.
* The `IsAuthenticatedOrReadOnly` REST class allows access to only autheticated while unauthenticated users can still have read access.
### How permissions are determined
* In REST permissions are defined as classes.
* Permissions are checked before views.
* If permissions fail for some reason `"403 Forbidden"` or a `"401 Unauthorized"` response will be returned,
### Object level permissions
* Object-level permissions check whether a user has permission to act on specific object.
* REST supports object-level permissions using `.get_object()`
* An `exceptions.PermissionDenied` exception is raised if user is not allowed.
* You need to call the `.check_object_permissions(request, obj)` on your views if you writing your object-level permissions as below:
```
def get_object(self):
    obj = get_object_or_404(self.get_queryset(), pk=self.kwargs["pk"])
    self.check_object_permissions(self.request, obj)
    return obj
```

### Setting the permission policy
Setting global default permission can be acheived as below:
```
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```
The `APIView` allows setting authentication policy per view/views as the below example:

```
from rest_framework.permissions import IsAuthenticated
from rest_framework.response import Response
from rest_framework.views import APIView

class ExampleView(APIView):
    permission_classes = [IsAuthenticated]

    def get(self, request, format=None):
        content = {
            'status': 'request was permitted'
        }
        return Response(content)

```
### Permission classes:
* `AllowAny` allows untrestricted access.
* `IsAuthenticated` denies permission to unauthenticated users.
* `IsAdminUser` this class denies access to users unless the `user.is_staff` is set to `True`
* `IsAuthenticatedOrReadOnly` allows read permission to anyone.

### DjangoModelPermissions
* Applied to views that have `.queryset` property or `get_queryset()` method.
* Authorization is granted to authenticated users only.
* `POST` requires the user to have the `add` permission on the model.
* `PUT` and `PATCH` require the user to have the `change` permission on the model.
* `DELETE` requires the user to have the `delete` permission on the model.

### Custom permissions

* Custom permissions can be implemented by modifying `BasePermission` and implementing `.has_permission(self, request, view)` and/or `.has_object_permission(self, request, view, obj)`
* Permission class that checks incoming request's IP address against a blocklist, and denies the request if the IP has been blocked.
```
from rest_framework import permissions

class BlocklistPermission(permissions.BasePermission):
    """
    Global permission check for blocked IPs.
    """

    def has_permission(self, request, view):
        ip_addr = request.META['REMOTE_ADDR']
        blocked = Blocklist.objects.filter(ip_addr=ip_addr).exists()
        return not blocked
```

<br />

## References

[Permissions](https://www.django-rest-framework.org/api-guide/permissions/)

<br />

## [<-- Back](README.md)
