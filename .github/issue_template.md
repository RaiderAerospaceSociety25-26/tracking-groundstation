# .github/ISSUE_TEMPLATE/firmware.yml

name: Firmware Task
description: Work item related to firmware
title: "[FW] <short summary>"
labels: ["subsystem:firmware"]

body:

- type: textarea
  id: scope
  attributes:
  label: Scope
  description: What needs to be done?
  validations:
  required: true
- type: textarea
  id: acceptance
  attributes:
  label: Acceptance Criteria
  description: How will we know this is complete?
  validations:
  required: true
