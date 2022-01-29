# 기본 설치 (mac)

## 1. Docker 설치
* **brew install --cask docker**

## 2. kubectl 설치
* **brew install kubectl**

## 3. kustomize 설치
* **brew install kustomize**

## 4. minikube 설치 및 쿠버네티스 클러스터 구성
* brew install minikube
* minikube start --driver docker
* cat ~/.kube/config
* minikube status
* kubectl cluster-info
