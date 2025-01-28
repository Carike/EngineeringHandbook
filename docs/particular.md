# Particular

## Leaning

- [Documentation](https://docs.particular.net/platform/)
- [How does ServiceControl work?](https://docs.particular.net/servicecontrol/how)

## ServicePulse

- [Maintenance Mode](https://docs.particular.net/servicecontrol/ravendb/accessing-database#windows-deployment-maintenance-mode)


## Running in containers

- [Running ServicePulse in containers](https://docs.particular.net/servicepulse/containerization/)
- [ServiceControl on Linux containers early access questions](https://discuss.particular.net/t/servicecontrol-on-linux-containers-early-access-questions/4000?u=carikebs)
  - https://discuss.particular.net/t/servicecontrol-on-linux-containers-early-access-questions/4000/23?u=carikebs
- [Particular Software on Docker Hub](https://hub.docker.com/u/particular)
- [Platform Container Examples](https://github.com/Particular/PlatformContainerExamples)
- GitHub 
  - [Issue #3651 - Support for Linux containers](https://github.com/Particular/ServiceControl/issues/3651)
  - [Particular platform container examples](https://github.com/Particular/PlatformContainerExamples/blob/main/kubernetes/README.md)
- ParticularDocs
  - [Deploying ServiceControl to a Cluster](https://docs.particular.net/servicecontrol/deploying-servicecontrol-in-a-cluster)
  - [Running ServicePulse in containers](https://docs.particular.net/servicepulse/containerization/)
  - Container deployment docs for each instance type ([add other links](https://discuss.particular.net/t/servicecontrol-on-linux-containers-early-access-questions/4000/23?u=carikebs)):
    - [Audit & Error instances](https://docs.particular.net/servicecontrol/servicecontrol-instances/deployment/containers)
    - [Monitoring instances](https://docs.particular.net/servicecontrol/monitoring-instances/deployment/containers)
    - [Database containers](https://docs.particular.net/servicecontrol/ravendb/deployment/containers)
  - [Migration guide from Windows to containers](https://docs.particular.net/servicecontrol/migrations/windows-to-containers)
  - The migration process leans heavily on the same procedures previously used for migrating from RavenDB 3.5 to RavenDB 5. This process been generalized in Replacing Error instances and Replacing Audit instances
  - The configuration pages for Error, Audit, and Monitoring instances have been updated so it’s clearer how to set the value whether you’re using an App config key, Environmnent variable, or ServiceControl Management field.
  - The ServiceControl Transports 1 page has been updated to document the transport types that were previously only available in the ServiceControl Management dropdown or via a PowerShell cmdlet.

## Upgrading ServiceControl and ServicePulse


## URLs

- [Monitoring NServiceBus systems with ServicePulse](https://www.youtube.com/watch?v=V6IZq-17LdQ)
- [NServiceBus monitoring demo](https://docs.particular.net/tutorials/monitoring-demo/)
- Single sign-on for production instance
  - https://docs.particular.net/servicecontrol/securing-servicecontrol 
  - https://docs.particular.net/servicepulse/install-servicepulse-in-iis#advanced-configuration-role-based-security 
  - https://fafach.wordpress.com/2014/10/24/securing-servicepulse/ 