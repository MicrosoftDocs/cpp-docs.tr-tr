---
title: AsWeak işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 75d732758bac53edc40aeac50e0184d80145890d
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="asweak-function"></a>AsWeak İşlevi
Belirtilen bir örneğine zayıf başvuru alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Parametresinin türü için bir işaretçi `p`.  
  
 `p`  
 Bir türünün bir örneği.  
  
 `pWeak`  
 Bu işlem tamamlandığında, zayıf başvuru parametresi için bir işaretçi `p`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlem başarılı ise S_OK; Aksi takdirde, hatanın nedenini gösterir HRESULT hata.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)