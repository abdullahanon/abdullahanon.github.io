---
title: Sync Virtual PC Xen Error
layout: post
---

Pernah mengalami kegagalan sinkronisasi antar pc (guest) pada xen ketika power failure, server berhasil di hidupkan kembal tapi.. guest pc tidak bisa saling sinkronisasi, alhamdulillah bisa diatasi dengancara sbb:

1. #drbdadm secondary r0
2. #drbdadm disconnect r0
3. #drbdadm connect --discard-my-data r0
4. Selesai ..barakallah fiikum. :)
