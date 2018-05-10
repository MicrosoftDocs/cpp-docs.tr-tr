---
title: SyncLockWithStatusT::GetStatus yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 03addd8d89c54eddb5deb721ab47d46e8b945edd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="synclockwithstatustgetstatus-method"></a>SyncLockWithStatusT::GetStatus Metodu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 SyncLockWithStatusT sınıfı üzerinde gibi temel nesne üzerinde bir bekleme işleminin sonucu bir [Mutex](../windows/mutex-class1.md) veya [semafor](../windows/semaphore-class.md). Sıfır (0) bekleme işlem iş durumu döndüren gösterir; zaman aşımı değerini geçen gibi Aksi halde, başka bir durumu, oluştu.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli SyncLockWithStatusT nesnesinin bekleme durumunu alır.  
  
 Arka plandaki değeri GetStatus() işlevi alır [status_](../windows/synclockwithstatust-status-data-member.md) veri üyesi. SyncLockWithStatusT sınıfı tabanlı bir nesne bir kilit işlemi gerçekleştirdiğinde, nesnenin ilk nesnenin kullanılabilir olması için bekler. Bu bekleme işleminin sonucu depolanan `status_` veri üyesi. Olası değerlerini `status_` veri üyesi bekleme işlemin dönüş değerlerdir. Dönüş değerleri daha fazla bilgi için bkz: **WaitForSingleObjectEx()** MSDN Kitaplığı'nda işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SyncLockWithStatusT Sınıfı](../windows/synclockwithstatust-class.md)