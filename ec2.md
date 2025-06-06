#EC2
 Amazon EC2 (Elastic Compute Cloud) is a core service provided by Amazon Web Services (AWS) that allows you to run virtual machines (VMs) called instances on the cloud.

### Key Features of EC2:
- Scalable computing capacity: You can easily start, stop, and scale instances up or down.
- Customizable VMs: Choose the operating system, CPU, memory, storage, and network capacity.
- Pay-as-you-go pricing: You only pay for the compute time you use.
- Secure and reliable: Integrated with AWS security, IAM, VPC, and monitoring tools.
- Supports automation: Through tools like EC2 Auto Scaling, Launch Templates, and AWS CLI.

### Common Use Cases:
Hosting websites and applications
Running backend services and APIs
Batch processing and data analysis
Development and test environments

### Instance Type

🔹 1. General Purpose
Balanced for compute, memory, and networking.

T Series (e.g., t3, t4g) – Burstable CPU performance; low-cost.

M Series (e.g., m5, m6i) – Balanced performance for most workloads.

✅ Use for: web servers, small databases, dev/test.

🔹 2. Compute Optimized
High-performance processors for compute-heavy tasks.

C Series (e.g., c6g, c7i) – Optimized for compute-intensive workloads.

✅ Use for: high-performance web servers, gaming, scientific modeling.

🔹 3. Memory Optimized
Large memory capacity for memory-bound workloads.

R Series (e.g., r6g, r7i) – Balanced memory optimization.

X Series (e.g., x2idn) – High memory with fast networking.

u- or z- Instances – Ultra/high memory (used for SAP HANA, etc.)

✅ Use for: in-memory databases, big data, analytics.

🔹 4. Storage Optimized
Optimized for high disk throughput and IOPS.

I Series (e.g., i4i) – Fast SSD for transactional workloads.

D Series (e.g., d3en) – HDD-based for dense storage.

✅ Use for: NoSQL DBs, file systems, data warehousing.

🔹 5. Accelerated Computing
Include GPUs or FPGAs for specialized workloads.

P Series (e.g., p4) – GPU for ML/AI training.

G Series (e.g., g5) – GPU for graphics and ML inference.

Inf, Trn, F1 – ML inference (Inferentia), training (Trainium), and FPGA.

✅ Use for: AI/ML, 3D rendering, HPC.


### Instance type based on pricing 

🔹 1. On-Demand Instances
Pay-as-you-go (per second/hour)

No long-term commitment

Ideal for short-term, unpredictable workloads

✅ Use for: Dev/test environments, temporary applications

💰 Most expensive option (but flexible)

🔹 2. Spot Instances
Use spare AWS capacity at up to 90% discount

AWS can terminate them with 2 minutes’ notice

Prices fluctuate based on demand and supply

✅ Use for: Fault-tolerant workloads, batch jobs, big data, ML training

⚠️ Not ideal for apps that can’t handle interruptions

🔹 3. Reserved Instances (RI)
1- or 3-year commitment

Up to 75% cheaper than On-Demand

Reserved for a specific instance type, region, and AZ

✅ Use for: Steady-state workloads (e.g., databases, production servers)

🔁 Can be Standard (non-flexible) or Convertible (change instance family/type)

🔹 4. Dedicated Instances
Run on hardware dedicated to you

Share the same physical server only with your instances

Charged per hour, slightly more than On-Demand

✅ Use for: Compliance or licensing needs (e.g., BYOL software)
