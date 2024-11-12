Containerization is a method of virtualizing applications so they run in isolated user spaces, called containers, while sharing the underlying operating system (OS). Below is a breakdown of how it works and what’s happening under the hood:
1. Isolation and Lightweight Virtualization

    Containers are built on lightweight virtualization, isolating applications and their dependencies from the rest of the system and from each other. Unlike virtual machines (VMs), containers share the host OS kernel, making them much more efficient in terms of resource usage and performance.
    Containers operate with isolated environments provided by namespaces and control groups (cgroups) within the OS. Namespaces isolate processes and networking within the container, while cgroups limit the amount of resources (CPU, memory, disk I/O) a container can use.

2. Namespaces: Process and Network Isolation

    Process Namespace: Isolates the container’s processes so they only see other processes within the same container.
    Network Namespace: Provides isolated network resources (such as IP addresses and ports) to each container, allowing containers to have their own network interfaces.
    Mount Namespace: Controls which parts of the filesystem each container can access. Each container usually has its own root filesystem, isolating the files and libraries it needs from others.
    Other namespaces include UTS (for hostname isolation) and IPC (for inter-process communication isolation), all working together to keep containers separate from the host and each other.

3. cgroups: Resource Limitation and Management

    Control groups (cgroups) in the Linux kernel are used to manage and limit resource usage by containers. They control how much CPU, memory, and disk I/O a container can consume.
    By setting these limits, containers can coexist on the same host without one monopolizing resources, ensuring a predictable performance for all applications running on the system.

4. Union File Systems: Layered Storage

    Containers use a union file system (like OverlayFS or AUFS) to create a layered filesystem structure, where each layer represents a set of changes to the file system.
    Each container image is made up of these layers. The base layer typically contains the OS libraries and dependencies, and each additional layer holds application-specific files.
    When a container starts, it uses these layers to create a unified file system view, but only the top layer is writable. This makes container images more efficient and helps speed up deployments since they only require updates to the top layer instead of the whole image.

5. Images and Registries

    Containers run from images, which are pre-built snapshots of the application, its dependencies, and configuration files. Images are stored in registries like Docker Hub or private registries, making it easy to share and distribute application setups.
    A container image is immutable; any changes made to it at runtime only occur in the writable layer, keeping the image itself intact. This immutability makes containers predictable and repeatable across different environments.

6. Runtime: Executing the Container

    The container runtime (e.g., Docker, containerd) is responsible for managing the lifecycle of containers, including starting, stopping, and handling resources.
    When a container is run, the runtime:
        Loads the container image and creates an isolated environment using namespaces and cgroups.
        Applies the layered filesystem.
        Sets up networking and mounts volumes if specified.
        Executes the container's main process, such as an application or a service, within the isolated environment.
