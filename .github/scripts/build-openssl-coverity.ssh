#!/bin/bash
# .github/scripts/build-openssl-coverity.sh

# Exit immediately if a command exits with a non-zero status.
set -e

echo "--- Starting OpenSSL Build Script for Coverity ---"

# Run the configuration step required by OpenSSL
echo "Running OpenSSL Configure..."
./Configure --prefix=/usr/local/ssl --openssldir=/usr/local/ssl '-Wl,-rpath,$(LIBRPATH)'
echo "OpenSSL Configure finished successfully."

# Run the main build command (e.g., make all)
# This is the part Coverity's build capture needs to monitor
echo "Running make all..."
make all
echo "Make all finished successfully."

echo "--- OpenSSL Build Script Finished Successfully ---"

# The cov-build/coverity scan command wrapping this script will capture the 'make all' compiler invocations.
