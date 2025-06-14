#!/bin/bash

NAMESPACE=$1
RESOURCE_TYPE=$2

if [ -z "$NAMESPACE" ] || [ -z "$RESOURCE_TYPE" ]; then
  echo "Використання: $0 <namespace> <resource_type>"
  exit 1
fi

echo "Resource, Namespace, Name, CPU, Memory"

kubectl top $RESOURCE_TYPE -n $NAMESPACE --no-headers | while read line; do
  NAME=$(echo $line | awk '{print $1}')
  CPU=$(echo $line | awk '{print $2}')
  MEMORY=$(echo $line | awk '{print $3}')
  echo "$RESOURCE_TYPE, $NAMESPACE, $NAME, $CPU, $MEMORY"
done