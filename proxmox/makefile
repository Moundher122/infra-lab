.PHONY: install clean help

PROXMOX_ISO_URL ?= https://enterprise.proxmox.com/iso/proxmox-ve_8.0-2.iso
INSTALL_DIR ?= /opt/proxmox
LOG_FILE ?= proxmox-install.log

help:
	@echo "Proxmox Installation Makefile"
	@echo "Available targets:"
	@echo "  make install    - Install Proxmox VE"
	@echo "  make download   - Download Proxmox ISO"
	@echo "  make clean      - Clean installation files"

download:
	@echo "Downloading Proxmox ISO..."
	wget -O proxmox-ve.iso $(PROXMOX_ISO_URL)

install: download
	@echo "Installing Proxmox VE..." | tee $(LOG_FILE)
	@echo "Note: This requires root access and system reboot"
	@sudo bash -c 'apt-get update && apt-get install -y proxmox-ve postfix open-iscsi' | tee -a $(LOG_FILE)
	@echo "Installation complete. Review $(LOG_FILE) for details."

clean:
	@echo "Cleaning up..."
	rm -f proxmox-ve.iso
	rm -f $(LOG_FILE)
	@echo "Cleanup complete"