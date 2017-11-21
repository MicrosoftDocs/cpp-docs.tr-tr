---
title: "AsWeak işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::AsWeak
dev_langs: C++
helpviewer_keywords: AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 36cf91b969ac1c180f7060c2518e626a22a08284
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asweak-function"></a>AsWeak İşlevi
Belirtilen bir örneğine zayıf başvuru alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename T  
>  
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
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)