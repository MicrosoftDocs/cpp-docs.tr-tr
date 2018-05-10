---
title: AsWeak işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 039d210e9a204c485e2f44c39ea87b4d35089d88
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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