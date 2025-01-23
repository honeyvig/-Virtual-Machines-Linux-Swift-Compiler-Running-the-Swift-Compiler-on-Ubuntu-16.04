# -Virtual-Machines-Linux-Swift-Compiler-Running-the-Swift-Compiler-on-Ubuntu-16.04
To run the Swift Compiler on Ubuntu 16.04 inside a virtual machine or directly on Ubuntu, the following steps will guide you through installing Swift, running Swift code, and compiling it. These steps assume you're using Ubuntu 16.04 in a Virtual Machine (VM) environment like VirtualBox or VMware.
Steps to Install Swift Compiler on Ubuntu 16.04 in a Virtual Machine
1. Set Up the Virtual Machine (VM)

    Install Ubuntu 16.04 on your Virtual Machine. You can download the ISO image from the official Ubuntu website.
    Allocate sufficient resources like CPU and memory to the VM to ensure smooth operation.
    Boot the VM and complete the installation process for Ubuntu 16.04.

2. Install Dependencies

Open the terminal and install the dependencies required for the Swift compiler to run. These dependencies are required for libraries and tools needed by Swift, including clang, libicu, and others.

Run the following command to install the necessary dependencies:

sudo apt-get update
sudo apt-get install -y clang libicu-dev libssl-dev libcurl4-openssl-dev

This will ensure that your system has all the necessary libraries for Swift to run.
3. Download and Install Swift

    Download the Swift Package:

    The Swift compiler isn't available by default in Ubuntu's package manager, so you need to manually download the Swift release. Go to the official Swift website Swift Downloads and choose the appropriate version for Ubuntu 16.04.

    For instance, you can download Swift 5.6 (or whatever the latest version is):

wget https://swift.org/builds/swift-5.6-release/ubuntu1604/swift-5.6.0-RELEASE/swift-5.6.0-RELEASE-ubuntu16.04.tar.gz

This downloads the Swift release for Ubuntu 16.04.

Extract the Swift Tarball:

Once downloaded, extract the tarball:

tar xzf swift-5.6.0-RELEASE-ubuntu16.04.tar.gz

This will extract the Swift files into a folder.

Move Swift to /usr/share (Optional but recommended):

To make Swift globally available, move the extracted Swift folder to /usr/share:

sudo mv swift-5.6.0-RELEASE-ubuntu16.04 /usr/share/swift

Add Swift to Your PATH:

You’ll need to modify your .bashrc or .zshrc file to include the Swift binaries in your system’s PATH.

Open your .bashrc file:

nano ~/.bashrc

Add the following line at the end:

export PATH=/usr/share/swift/usr/bin:$PATH

Then, load the updated .bashrc:

    source ~/.bashrc

4. Verify Swift Installation

Now that Swift is installed, verify the installation by running the following command to check the Swift version:

swift --version

You should see output indicating the installed version of Swift.
5. Running Swift Code in Ubuntu 16.04

Now you can run Swift interactively or as a script.
Method 1: Running Swift Interactively (REPL)

To enter the Swift REPL (Read-Eval-Print Loop) for interactive Swift code execution, type the following:

swift

This opens a REPL session where you can run Swift code interactively. For example:

print("Hello, Swift on Ubuntu!")

Press Enter, and you should see:

Hello, Swift on Ubuntu!

Method 2: Running a Swift Script

You can also create a .swift file and execute it.

    Create a Swift file (e.g., hello.swift):

nano hello.swift

    Add the following Swift code:

print("Hello, Swift on Ubuntu!")

    Run the Swift file using the swift command:

swift hello.swift

This will execute the code and print:

Hello, Swift on Ubuntu!

Method 3: Compile Swift Code into Executable

If you want to compile Swift code into an executable binary:

    Create a Swift file (hello.swift):

print("Hello, Swift on Ubuntu!")

    Compile the Swift file using swiftc (Swift compiler):

swiftc -o hello hello.swift

This will create an executable file named hello.

    Run the compiled executable:

./hello

You should see:

Hello, Swift on Ubuntu!

Conclusion

You have now installed and set up the Swift compiler on Ubuntu 16.04 in a Virtual Machine. Here’s a summary of the steps:

    Install required dependencies (clang, libicu, etc.).
    Download and install the Swift compiler.
    Set the environment PATH for easy access to the Swift binaries.
    Run Swift interactively using the REPL or execute Swift files via the swift command.
    Compile Swift programs into executables using swiftc.

Now you can start developing and running Swift applications directly on Ubuntu 16.04!
