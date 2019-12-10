# hipster-source

```shell
kubectl apply -f -<< EOF
apiVersion: v1
kind: Secret
metadata:
  name: git-ssh
  namespace: beer
  annotations:
    tekton.dev/git-0: github.com
type: kubernetes.io/ssh-auth
data:
  # Generated by:
  # cat id_rsa | base64 -w 0
  # This deploy key has read-only permissions on github.com/knative/build
  ssh-privatekey: LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVktLS0tLQpNSUlFb2dJQkFBS0NBUUVBeHBnVy9FcW1YQnJodk1NSkdoeTFENnlWajlYanlwd2tEZkd5ZU1ac1crTGk2cjhhCmhSKzZDWnlESXNIS0U4MFJxa0FTcTU0N3VCUUxkOURnZ1FsM3BqcGtqRDlidEM1NG1DR2VoK29NR3NmaFFxYmwKSXZjYS9Zd1UvWVBTWjRobzRpZzMrUjlyY29RR0ZLSmh6KzZsMVRTNjhaV0dqU3hQWXRJL0JGMjd5SlZPODY0UwpYZ1IrbE1uOEJqdzAvbUl3KzMrUGZpUWtSd0lpVy8wUW1MQ1JVUlJqU0VJakVwSXlpRXh3NjBzc1hpSmFqSmlQCjlnWjVIQVorenF5cDh4RU9GczR6UDFJVGp5UzFEdUc5THhvTWIxK1lOT3V2VjBWYm5ieHg2UEhNUVhLTmlKbmkKTVp4aW5pWWVzeUpqNnZyVnJ4VEx5TE9aSUllV3RPRTR2YkxMalFJREFRQUJBb0lCQUc4UDRWTG93STZqN2ZodApybXB2QVljcGdsNzFSRFlzQ2pIT0tIeElvNUxqbVBtbE5FU2MwS0xOWjcwSldXU25lNmlWdXB0Rm02by9jNFpuClJ4YUMzK29UbitXYkRVTC85aXRHS2UxaW83QmFkZ3liWDJ1bGUrK3Q1cE04cEcrSUp2ZkxmRG9US3pqWXdybkoKY2lBaUc1WFhybkNxcVp2TDJ2MnVETlg1UWFwVGNaejdmQXEyZnN5KzdQQlV5dUNhT0YxU1FFRDllY2Z2TkpMRApva0hYMkNCR2YwZ1J5RTlzNVBGRm0yR0dRODJua0pTUERjOUtESTk3TlBDRW4vaHdlcWZqTzZNaTdSVTdoUDU2CjUwL1gvdjZIcDYvVWhDckdrY0VqTDREQ0dlbVd2b21HZ1QzNmlXbW15MDF4U1JaUnRMVzRBdXhyQkxhb2ZwZGgKSVorOHhoVUNnWUVBNWMxR3p4Q3pkUlJqc3FGVzlvNktKRmVwdnorVzRwMWJBcFBlTTBtWGtJb01ybStwcnhwcgpyNUozT3ZZV2lGSE56ZVlsZGRBOTZsYU5xdTRmdDNHeVp6K3YxNnEvNmRFMVFGS3g4UkhYWGQ1M0RHcDFrS1k1CnlNN0YxUUhLNDEyMFZtdmZFV1RyTENyTER1ZWVFNjBUZUsrTmZHSkUzUGlVbXVwRFNocmdSeXNDZ1lFQTNUd0YKU1hKLytLNHphVjVteUZlU01kRDVRNmpYWnRxYU9EeFlvcmxlNkR0bVNLUDZnbzhqdFVWSnd2a2MwOHY5bld0Ngp2M2Z1dy8rMHRtQVJjOXRCQjB4Qkp3RFBmUE5tVzFGQjBBVkQrYWZ1eUM5Z1hMeE1zR2UxR1JSRE9ubHFjRTFKCnJXc05vRG9tRTBkY094OWVIbUluNmdwb2Z5T2FhRlJHZlVtZDNDY0NnWUJrL1RadUR6ZmVid3gxVnlRQmpKaTIKNmZPR1Fhck1nanlad0dQNUJCRmdpdHFSMmk2bTdpUis3dzRJMGxjS3AzQ2JXTllEbFhWd1E0TlVwL3MyUWZnVwpHYzNzS0hUWWk0RXNlR3NNdHp0L1hDSFRTZ0hLaE5LR0ppQ1l3SVhxTDZidUI4L3JNLytKMUhDU1owVjMvaXE5CmNlRHExY0RQbjBxblhlWWViZnM4S3dLQmdINHFBbUhXV0VCN0ozcUppVmZyQ01ZOEJFcWZlT2VBOXIzblBDemcKUmMxdVFuQmVnemY5WlVHMDE5SEd1cmZWOXpYVTIxVmhrZHBZY3JnbXBRMUxGaFNSV2Y1aUtmRjU1UDlpb1lOOQozVHY4bHVHMmt0K1B5clEzRUVIVEdsdTRiZ2pKS3FFcEVjWTBJdzZQZlh1QjhleWwwVmxZd2lydkpOa21abVNBCm5QTzFBb0dBQU55dmtybUhRL211Z1N6YktaWXRvWUxLSGZVSmx3RTJkY0dHUXJXRFVUa2RHOEJ0THMzckx4Y3IKdnU4RFp6U2FtdU9VQlBCL1NjSHlYMmtvRW9vY3BrOUQ1VWlxWDNNckltbEZMY3M1aFI5bENmRTJFMUMyUkdCMgpyMG5tTTg1aWEra0ZJaTVOUC9uWHlmdEtUMEpRL1lSMzg3WmpGWnAvYW1JQ3ZldEEwc0U9Ci0tLS0tRU5EIFJTQSBQUklWQVRFIEtFWS0tLS0tCg==
  # Generated by:
  # ssh-keyscan github.com | base64 -w 0
  known_hosts: Z2l0aHViLmNvbSBzc2gtcnNhIEFBQUFCM056YUMxeWMyRUFBQUFCSXdBQUFRRUFxMkE3aFJHbWRubTl0VURiTzlJRFN3Qks2VGJRYStQWFlQQ1B5NnJiVHJUdHc3UEhrY2NLcnBwMHlWaHA1SGRFSWNLcjZwTGxWREJmT0xYOVFVc3lDT1Ywd3pmaklKTmxHRVlzZGxMSml6SGhibjJtVWp2U0FIUXFaRVRZUDgxZUZ6TFFOblBIdDRFVlZVaDdWZkRFU1U4NEtlem1ENVFsV3BYTG12VTMxL3lNZitTZTh4aEhUdktTQ1pJRkltV3dvRzZtYlVvV2Y5bnpwSW9hU2pCK3dlcXFVVW1wYWFhc1hWYWw3MkorVVgyQisyUlBXM1JjVDBlT3pRZ3FsSkwzUktyVEp2ZHNqRTNKRUF2R3EzbEdIU1pYeTI4RzNza3VhMlNtVmkvdzR5Q0U2Z2JPRHFuVFdsZzcrd0M2MDR5ZEdYQThWSmlTNWFwNDNKWGlVRkZBYVE9PQo=
EOF


kubectl apply -f -<< EOF
apiVersion: v1
kind: Secret
metadata:
  name: git-ssh-build
  namespace: beer
  annotations:
    tekton.dev/git-0: github.com
type: kubernetes.io/ssh-auth
data:
  # Generated by:
  # cat id_rsa | base64 -w 0
  # This deploy key has read-only permissions on github.com/knative/build
  ssh-privatekey: LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVktLS0tLQpNSUlFcEFJQkFBS0NBUUVBc2Z5cVd6UjFyb3FYVjRRS1FEL3F0ck0valQ5U1lUdmZGejlJMktBeTZFeWcwTU5OCkh0NlVtakhYbjhBdXl6bEF2WE5ML1VjY2VkZFdIR0tFRWVwOTlnQ0RzTWJvNG1ONEV0RGxGeXhNTzZ1UnE3WUwKaExHeDlQQlBvaGN2SHdNWFlKUnVXUkR2cEc2MHNVZDRBWk8xejJGUkRYSnpvL0tyRlNRa1krekE3a0ZOL0MrRwpWUVlTenhFMUFhWEczL3dWcFR3YVo3UngvUnZDYW5xM1pDRHFNTGovK1dTZWlQV25GdDNqZGdsdGxUVjVMdmNMCkh4QXUrRS9jcXlLczE2UHcvUmtiWFo4MkFzelhxNXo4Qi9HUUhDQ0hnNHFrZTV0VnpxU0ZCS2ZpbzRIazUvUUkKNjJDNldSZzRtNXR4SkR5azVDdEhIRkZYVnQ2UzFNYWN2ZlVFK3dJREFRQUJBb0lCQVFDSTNIcTZheHBhdm1NbApmbmpMY3RxdTVpSm1JRnplTzhXT0FMR3BNWFl6dmtpaWZxcmNvOWFzd3NyRkltaFpDSXRKb2xDNlQyWU1JcE1xCmZHNkZ3RVJmVjRIcit1ZTB2VHZsYkEvY3c4bFMwTmpRcXNrc25kN3pNNTVvUzErR2YwQUltZHBJVG9lWGJ6RXUKYUlCVTVob1Zmd1Z1UzZXMFdiTklMR1IzR2VRNHoyRXIwUCtweE4ycy8yMVNFL1ZoK0VoTGdlV3Zra3JleW5rNwpON1IvVmxtTTQ4ZDVYMkxFN2xxcmlkeVFBUEpreG4vR0JQV29JL24wUzVxSkxHaGI4ZXE1MllHWER4amZLbjJXCnhaZGppbWMzZk4wMkhqUjdTY0ZLYTdJUVpLTnd4R1p1K2lzMTE2VncyQjNEU1pUTlBvN2VML003bHpKdkkxTjkKdHVZWWZpMmhBb0dCQU9kTXRVWGtqbWtyVVczdDcyR0hZcXg0VnFQNE1welF5NDZyRUFYR0J1WVZmSDIwaWd6Sgp5NzVSQjk0dUg5ekFqSUhQVGo4OWpvajhnMlBoWk81WmdMUnkyc1FsRThKazVQZEYvSnlFUGcxdnBqZC82RVk5CnJraEdVMWpFZzNjcUJmWU9iMjM0VDlCcEVmL0d4Q2xvZ1NIcnRZWWROREJiQkdvSjkyWEdqcTVqQW9HQkFNVCsKZlpPZ0FNdFBkT2hOY2VaNnNwM0dRbmlIL2lNbndUczZIUlZmYTYveUFDV1ZpaWNXQ1NBTEhTdVFjbGpVbldiSQo4VzUwWS9zYUtLdEhiTTFnRUJUakQzNytnZlpzdVlpQjBIV1Rld3c5YUs1M1ZxOEdzZ0t3NFhZOEd1NW9vU3haCjJGcEtvL0VqZE1lRlNDTG8xZS9obmNSRk54eGRiZkZRVElTcG5TYUpBb0dBU250NUpEaWxZMWgvc0ZhZWIxbVoKZk5DRGxlbW00cmlaMUNkaDBYb2pYcFFzc280Z3BsMlZMb1FKZEpLRjBDQnhIcHdUSm1vOExBQ2tqdFZXR3lyWApOMFNGRGdTaWlFYlZOSXRrL1VIWWVac3FlMVRGQjFsMWRmQ3ZoalpCMzIyNDNiTm9UcEZYb2xVelpwb3JNT3BtCkt2WXNUak81U3BrRW91RHl1ZU5tcnVFQ2dZQmxEQ204SE5ucmNCR0d5NXIrWDdmWmlJWTJMNFBqNHBPUzN1ZG0KUERFUDZuRzYxYTh0QjNlYzBUYWdUeExvai85Qlp4ZTQwY2tyVjZxKzJQOXRoYllhRUxLMU1MWFhnc1BVeXNuMApWYmRMZXdDRVpjQzRQUlg0bldTNWNuRmFFNStCRVlFU0o3RmFreFptOWU0ZndoRmpYL2ErWThhMkxSS2xNc3hkClRHZkpDUUtCZ1FEUWVxbjdDNDkwSEVWUWd2N1pXYjFabWpIaUZZRUw4Z3lxaC9yQ1ZjS2x1YVhTTEd5VGM2akcKUlNGSSsxa2plaHlYd2tVQkhlVStRNEROWGFUTHNWRDVWbTRuQnR2aVNEeDFRMm1iamhnaVA4c3BqL1hUOFIwUwpNNmV6MGNvU2QrZkVNOGtUaGYvZjRraVg3UHRaTG9SQ3JVU0dUYUlNOUxWQVpuTVR4QW5iMXc9PQotLS0tLUVORCBSU0EgUFJJVkFURSBLRVktLS0tLQo=
  # Generated by:
  # ssh-keyscan github.com | base64 -w 0
  known_hosts: Z2l0aHViLmNvbSBzc2gtcnNhIEFBQUFCM056YUMxeWMyRUFBQUFCSXdBQUFRRUFxMkE3aFJHbWRubTl0VURiTzlJRFN3Qks2VGJRYStQWFlQQ1B5NnJiVHJUdHc3UEhrY2NLcnBwMHlWaHA1SGRFSWNLcjZwTGxWREJmT0xYOVFVc3lDT1Ywd3pmaklKTmxHRVlzZGxMSml6SGhibjJtVWp2U0FIUXFaRVRZUDgxZUZ6TFFOblBIdDRFVlZVaDdWZkRFU1U4NEtlem1ENVFsV3BYTG12VTMxL3lNZitTZTh4aEhUdktTQ1pJRkltV3dvRzZtYlVvV2Y5bnpwSW9hU2pCK3dlcXFVVW1wYWFhc1hWYWw3MkorVVgyQisyUlBXM1JjVDBlT3pRZ3FsSkwzUktyVEp2ZHNqRTNKRUF2R3EzbEdIU1pYeTI4RzNza3VhMlNtVmkvdzR5Q0U2Z2JPRHFuVFdsZzcrd0M2MDR5ZEdYQThWSmlTNWFwNDNKWGlVRkZBYVE9PQo=
EOF

kubectl apply -f -<< EOF
apiVersion: v1
kind: Secret
metadata:
  name: git-ssh-deploy
  namespace: beer
  annotations:
    tekton.dev/git-1: github.com
type: kubernetes.io/ssh-auth
data:
  # Generated by:
  # cat id_rsa | base64 -w 0
  # This deploy key has read-only permissions on github.com/knative/build
  ssh-privatekey: LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVktLS0tLQpNSUlFb3dJQkFBS0NBUUVBdG9jUlpHOVluS2h0Rmc3djN2Q2pndFJxUDFnNHlBTkRTM0xWV3NicUdRQ2tyZUI4ClE1THhCOTRFb2pEVEFBcnJ0K2hjL2tRanRkNnFXTVFMVW9vZFJzUXRNYmlYZDJHckNlUGl0dUN4UEJrSXZEd2cKVk5MVDkzdUVPS3hHZVVqWmU5WnhyejFiNldVcXVOd2dZVEZxR2Qxcy9aNnhhTFErc2E0aGRCVzhyclVxSEQwRAprdGFOK1hlMDh4VGVXZEdkTVNhVTdwYy9TMVg2cTRJMGZ0NHRGS01YckZueXpNc3YrTHRZYyt5Qjdsa0RialZ6ClQvOURRRUd6aU5PTkpiUDNVMS9LSGdKajZvOThoa0c0YXIzeE5UakNuMVBPb3VrMkE0Y2Fpd3NuV0FmY1A5Vk4Kb0FaMU9nVVZaN0ZlSnZlbVVXZUNvLzh4VTdXbCtSY3ZxVDFETXdJREFRQUJBb0lCQUNUQ0FxQ2xROFVZcmc4NQpKdGxRd0wwQ0pmdG51dGVjd0pxYkg1aE9ZcXB5VkxlbmM1N3dJcFloQWZIZnZ6NU05TGR1bGZ1bW9VSm8rd2t4ClFjNTNmZm5ZVy9tZFlQTnJ1ZFFlRG5RaHY4K0lneGZWUy9XSkY2TEpQeEZpc0RhUWt5dTdQZDI2ajUzcS83V0cKcndhanV1aEdqVUp1Q1BBN0REMGdBaUNzbC9qZXI5b012Y0pRYzdqWm5Tamp5dEp5anFkMGkrUUJPME52aW9Wdwo3T2s3M1N4OXMvL0RyaWRndUViVWFCam4vTDR3cWdUNVhhOHZqUlA4amtHQWhQQTJpcUVtOGJDeWNKL0FpUURPCmtiaUNHb2pFV1BJK3JzZm5xeithQTV5ZkE1RmhLQ3RvNDVnTENMalUxZ1lvVG91QXdoZzZLMWlWeGlnR0UwSDkKMURvNHViRUNnWUVBNGx1bTVpL25OTC9IMUNvK1dvckpHNlJCN0ZMYURuVkRUZWdDSVpzOXR2cGcyWDRaN2cwbAo1TUZFcENDN09raUdLblQrVDhnb0NMcmNIZ0JRdjIrTkVrWWFtSFd0QlhuYmY4dnpubkVUbU94M2lUTTFsSmk0ClQwVFVMaERhbmFZUXNDV3FsM2grTlFJOVhJbXA3UkdjdFdSbFRNVnJ6b0JyT0VudnhlMkZrODBDZ1lFQXptNFAKZ1JEaHp3NDJURm1QR2VXcGVwRTIvZDNJZElTMDh6R3ZieU03eUp3cGU2UHE4Z2VOWjAvajkrckNFS0ovdFY0cgpMWE45SlBYeDBaK240Y0R5V2dWZFdKMEt2aTMwa0cyb0s1c0RGYko5VFUvaUozSTZKcE1sMkpwQ2lOV0dmRE5JCjM2VktGcUl6TS9xNjQxV3dWWCs0dEZ4NmdUNWJaUy9qck1TVk12OENnWUVBcWJHQjluRVZDSU41b0VHbkN5T2UKVHAyZVdqZG1oNDQ3VGExUDQ3ZkkxV0x3dGp3RjNtTjI4LzQ3b2p0emdPY2J4YnA5YUh3cUh4bE9xU01kWmRhUAowSkpEbitZZ05zbTYxeHlqM3pUd055V1hHNEVMZXdIZXNuWnNCcmpWMjNmQ2JQdGYzendTaVZUTGdaTW1rN1l2CllBRUt2RG9JYnYvdzRYcjBTTktlNEVVQ2dZQUxad0RzUENaODdXZ0taNWdEOGkrZVdZOFVEc0FYejR5L01pdGkKbEN1bE5Sc0ZmVlJvOGduWmZ3dzBrWDhPdENzaHRZWGxDTkFNenBrQTN6VEN2NG1qZDFCa3FLZ0RRVDZWQzdtUwpUd21vbFNkZXNkN29GdU1uWmxGYzJZaDdUbkFUUkRIdVNJOERHUXFEQUlKNk5DMTlTNFRFVWFkaXBETWdMN2ovCnZnd1B1UUtCZ0FZcTFGRzROQnNlU1daZnlLeFFFNmtWMVJFOC81Rm8rNjlmYkxWcXRWSXg0MTNkSFNYYmxoTXgKaTBSL1NIOTNuWWFONUx4OExrRFdpNWFvUGtUZEhBU1g2eDRwTE10Mmd2aUlrd0s0TFlUbllvL3lMaGQraDFDOQpsejAzSUYvaW9CUzFISm1rVHNIdTg4RWFGT3Q3VmJpaWFUNWJ3UjBITXMvWUhsL2IvU2lZCi0tLS0tRU5EIFJTQSBQUklWQVRFIEtFWS0tLS0tCg==
  # Generated by:
  # ssh-keyscan github.com | base64 -w 0
  known_hosts: Z2l0aHViLmNvbSBzc2gtcnNhIEFBQUFCM056YUMxeWMyRUFBQUFCSXdBQUFRRUFxMkE3aFJHbWRubTl0VURiTzlJRFN3Qks2VGJRYStQWFlQQ1B5NnJiVHJUdHc3UEhrY2NLcnBwMHlWaHA1SGRFSWNLcjZwTGxWREJmT0xYOVFVc3lDT1Ywd3pmaklKTmxHRVlzZGxMSml6SGhibjJtVWp2U0FIUXFaRVRZUDgxZUZ6TFFOblBIdDRFVlZVaDdWZkRFU1U4NEtlem1ENVFsV3BYTG12VTMxL3lNZitTZTh4aEhUdktTQ1pJRkltV3dvRzZtYlVvV2Y5bnpwSW9hU2pCK3dlcXFVVW1wYWFhc1hWYWw3MkorVVgyQisyUlBXM1JjVDBlT3pRZ3FsSkwzUktyVEp2ZHNqRTNKRUF2R3EzbEdIU1pYeTI4RzNza3VhMlNtVmkvdzR5Q0U2Z2JPRHFuVFdsZzcrd0M2MDR5ZEdYQThWSmlTNWFwNDNKWGlVRkZBYVE9PQo=
EOF


kubectl create secret docker-registry regcred \
                    --namespace beer \
                    --docker-server=registry.arctiqtim.anthos.labs.arctiq.ca \
                    --docker-username=admin \
                    --docker-password=Arct1q \
                    --docker-email="tim.fairweather@arctiq.ca"

kubectl apply -f -<<EOF
apiVersion: v1
kind: ServiceAccount
metadata:
  name: arctiqtim-git-ssh
  namespace: beer
secrets:
- name: git-ssh-build
- name: git-ssh-deploy
- name: regcred
EOF
```