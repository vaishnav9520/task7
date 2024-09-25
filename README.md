# task7
nessus vulnerabilty of metaspolit
Here's a README template tailored for your task using Nessus instead of OpenVAS, which includes scanning a Metasploitable VM, generating reports, 

---

# Nessus Scan of Metasploitable VM

## Overview

This repository provides instructions for performing vulnerability scans on a Metasploitable virtual machine using Nessus. The objective is to identify and document vulnerabilities in the target environment.

## Prerequisites

- **Nessus**: Ensure that Nessus is installed and configured on your machine. You can download it from [Tenable's official site](https://www.tenable.com/products/nessus).
- **Metasploitable VM**: Set up the Metasploitable VM in your local environment. You can download it from [Rapid7's website](https://information.rapid7.com/metasploitable-download.html).
- **Network Configuration**: Ensure both the Nessus scanner and Metasploitable VM are on the same network segment.

## Setup Instructions

1. **Install Nessus**:
   - Follow the installation instructions for your operating system.

2. **Start Nessus**:
   - Launch the Nessus web interface by navigating to `https://localhost:8834` in your web browser.
   - Log in with your credentials.

3. **Configure Metasploitable**:
   - Ensure your Metasploitable VM is running and you can access it via its IP address.

## Scanning Process

### Create a New Scan

1. **Navigate to the Scans Tab**:
   - Click on the **Scans** tab in the Nessus interface.

2. **Create a New Scan**:
   - Click on **New Scan** and select the **Basic Network Scan** template.

3. **Configure the Scan**:
   - **Name**: Provide a meaningful name for your scan.
   - **Targets**: Enter the IP address of the Metasploitable VM.

### Launch the Scan

1. **Save Your Scan Settings**.
2. **Start the Scan** by clicking on the scan you just created.

### Exporting Results

1. **View Scan Results**:
   - Once the scan completes, click on the scan to view the results.

2. **Export the Report**:
   - Click the **Export** button in the upper right corner.
   - Select your preferred format (PDF, HTML, etc.) and download the report.

## Generate Nikto Report

1. **Install Nikto** (if not already installed):
   ```bash
   sudo apt install nikto
   ```

2. **Run Nikto Scan**:
   - Open a terminal and execute:
   ```bash
   nikto -h http://<METASPLOITABLE_IP> -o nikto_report.html -Format htm
   ```

3. **Locate the Report**:
   - The HTML report will be saved as `nikto_report.html` in the current directory.

## Grab Banner Information Using Netcat

1. **Open a Terminal**.
2. **Use Netcat to Connect to a Port**:
   - For example, to grab the banner from port 80:
   ```bash
   nc <METASPLOITABLE_IP> 80
   ```

3. **Request the Banner**:
   - Type the following command and press Enter twice:
   ```http
   GET / HTTP/1.1
   Host: <METASPLOITABLE_IP>

   ```

4. **Take a Screenshot**:
   - Use your operating system’s screenshot tool to capture the terminal window displaying the banner information.

## Troubleshooting

- If the scan returns "0 vulnerabilities":
  - Verify that the Metasploitable VM is running and reachable.
  - Check the scan configurations to ensure the correct target IP is specified.
  - Confirm that Nessus plugins are up to date.


