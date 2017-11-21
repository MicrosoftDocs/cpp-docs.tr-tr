---
title: "AsyncBase::TryTransitionToError yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs: C++
helpviewer_keywords: TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 04019cc27866c41f263f7d51fa6b5ae0cfd9e000
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasetrytransitiontoerror-method"></a>AsyncBase::TryTransitionToError Yöntemi
Belirtilen hata kodu iç hata durumu değişiklik olup olmadığını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `error`  
 HRESULT hata.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`İç hata durumu değişti Aksi takdirde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca hata durumu için S_OK zaten ayarlanmışsa, bu işlem hata durumu değiştirir. Hata durumunda zaten iptal edildi, tamamlandı ya da kapalı hata ise bu işlem bir etkisi yoktur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase sınıfı](../windows/asyncbase-class.md)