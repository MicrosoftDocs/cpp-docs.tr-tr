---
title: AsyncBase::TryTransitionToError yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc677304ae7ab61e6726366869e85f731cd92484
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463213"
---
# <a name="asyncbasetrytransitiontoerror-method"></a>AsyncBase::TryTransitionToError Yöntemi
Belirtilen hata kodu iç hata durumunda değiştirip değiştiremeyeceğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Hata*  
 HRESULT hatası.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** iç hata durumunda, değiştirilen; Aksi takdirde **false**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem, yalnızca hata durumunda S_OK için zaten ayarlanmışsa hata durumu değiştirir. Hata durumunda zaten iptal edildi, tamamlandı veya kapalı hata olması durumunda bu işlem bir etkisi yoktur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)