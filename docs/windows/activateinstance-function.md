---
title: "Activateınstance işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
dev_langs: C++
helpviewer_keywords: ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1fbf79a38dedf2a7978bdaf1be4bea084283efe9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="activateinstance-function"></a>ActivateInstance İşlevi
Kaydeder ve bir belirtilen sınıf kimliği tanımlanan belirtilen bir türün bir örneğini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename T  
>  
inline HRESULT ActivateInstance(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Etkinleştirmek için bir tür.  
  
 `activatableClassId`  
 Parametre tanımlar sınıf kimliği adını `T`.  
  
 `instance`  
 Bu işlem tamamlandığında, bir örneği için bir başvuru `T`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, hatanın nedenini gösterir HRESULT hata.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Windows::Foundation  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::Foundation Namespace](../windows/windows-foundation-namespace.md)