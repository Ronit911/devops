# Self-Hosted Runner Troubleshooting

Self-hosted runners introduce another infrastructure layer, so troubleshooting requires checking both GitHub and the server.

## 1. Check Runner Status

If the runner is installed as a service:

sudo systemctl status <runner-service>

This can show whether the service is running.

## 2. Check the Runner Process

The runner process can be inspected with:

ps -ef | grep '[R]unner.Listener'

If the runner process is present, the runner software is running.

## 3. Check GitHub

In the repository settings, check the Actions runner configuration.

A runner may appear as:

- Online
- Offline
- Busy

If the runner is offline, investigate the server and service.

## 4. Check Network Connectivity

The runner needs network connectivity to communicate with GitHub.

Basic checks can include:

ping example.com

curl -I https://github.com

The exact network tests depend on the server environment.

## 5. Check Service Logs

If the runner is managed by systemd, service logs can help identify problems.

Example:

sudo journalctl -u <runner-service>

Follow recent logs:

sudo journalctl -u <runner-service> -f

## 6. Check Permissions

Deployment failures can occur when the runner user does not have permission to access:

- Application directories
- Docker
- Nginx
- System services
- Required files

The solution should be to grant only the required permissions rather than simply running everything as root.

## 7. Check Workflow Logs

GitHub Actions provides logs for each workflow job and step.

A useful troubleshooting order is:

GitHub Actions
    |
    v
Workflow Step
    |
    v
Runner
    |
    v
Server
    |
    v
Application

## 8. Common Problems

### Runner Offline

Possible causes:

- Runner service stopped
- Server unavailable
- Network connectivity problem
- Runner configuration issue

### Job Stuck Waiting

Possible causes:

- No matching runner
- Incorrect runner labels
- Runner offline
- Runner already busy

### Permission Denied

Possible causes:

- Incorrect file ownership
- Missing group membership
- Insufficient sudo permissions
- Restricted application directory

### Docker Permission Error

The runner user may not have permission to communicate with the Docker daemon.

This should be addressed through appropriate user/group configuration rather than running the entire workflow as root.

## Troubleshooting Principle

Do not immediately change multiple things at once.

Check the system layer by layer:

1. GitHub workflow
2. Runner availability
3. Runner service
4. Network connectivity
5. Linux permissions
6. Deployment commands
7. Application
8. Nginx / external access

This makes it easier to identify the actual cause of a deployment failure.
