# -*- mode: Python -*-
# SPDX-FileCopyrightText: 2025 SAP SE or an SAP affiliate company and IronCore contributors
# SPDX-License-Identifier: Apache-2.0

# Don't track us.
analytics_settings(False)

allow_k8s_contexts(['minikube', 'kind-network'])

docker_build('controller:latest', '.', ignore=['*/*/zz_generated.deepcopy.go', 'config/crd/bases/*'], only=[
    'api/', 'cmd/', 'hack/', 'internal/', 'go.mod', 'go.sum', 'Makefile',
])

k8s_yaml(kustomize('config/default'))
k8s_resource('network-operator-controller-manager')

print('🚀 network-operator development environment')
print('👉 Edit the controller code inside the api/, cmd/, or internal/ directories')
print('👉 Tilt will automatically rebuild and redeploy when changes are detected')
# vim: ft=tiltfile syn=python
