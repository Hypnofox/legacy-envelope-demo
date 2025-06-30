# Legacy Envelope Demo

This repo contains:

## packer/
JSON templates to bake VM images.

## terraform/
Modules for KVM and PowerVS pods.

## ansible/
Playbooks and roles for guest configuration.

## shim/
Python (Flask/FastAPI) control-plane with hypervisor adapters.

## dashboard/
React (or plain JS) UI to visualize and control VMs.

## .github/workflows/ci.yml
CI pipeline for packer, terraform, ansible, shim, and dashboard.

### Getting Started

1. Install prerequisites with your setup script.
2. Bake an image:
   \`\`\`bash
   cd packer
   packer build x86_64.json
   \`\`\`
3. Deploy it:
   \`\`\`bash
   cd ../terraform/kvm
   terraform init && terraform apply -auto-approve
   \`\`\`
4. Configure with Ansible:
   \`\`\`bash
   cd ../../ansible
   ansible-playbook -i inventory.ini playbook.yml
   \`\`\`
5. Fire up the shim and dashboard and enjoy your envelope in the cloud.
