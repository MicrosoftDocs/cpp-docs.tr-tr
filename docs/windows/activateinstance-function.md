---
title: Activateınstance işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 413bf73d5aeaef2c210be89f3c6f4ca3a4254ba4
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461977"
---
# <a name="activateinstance-function"></a>ActivateInstance İşlevi
Kaydeder ve belirtilen sınıf kimliğinde tanımlanan belirli bir türün bir örneğini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T>  
inline HRESULT ActivateInstance(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Etkinleştirmek için bir tür.  
  
 *activatableClassId*  
 Parametre tanımlayan sınıf kimliği adını *T*.  
  
 *örneği*  
 Bu işlem tamamlandığında, bir başvuru örneğine *T*.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, hatanın nedenini gösteren HRESULT hatası.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Windows::Foundation  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::Foundation Ad Alanı](../windows/windows-foundation-namespace.md)