---
title: Module::Create yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c0d49a6f0b5172b0971f755fc61b7767f0f4427d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603309"
---
# <a name="modulecreate-method"></a>Module::Create Yöntemi
Bir modülün örneği oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW static Module& Create();  
template<typename T>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<typename T>  
WRL_NOTHROW static Module& Create(  
   _In_ T* object,  
   _In_ void (T::* method)()  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Modül türü.  
  
 *geri çağırma*  
 Son örnek nesnesi modülünün bırakıldığında çağırılır.  
  
 *object*  
 *Nesne* ve *yöntemi* parametreleri birlikte kullanılır. Son örnek nesne modülünde yayımlandığında son örnek nesnesi işaret eder.  
  
 *Yöntemi*  
 *Nesne* ve *yöntemi* parametreleri birlikte kullanılır. Nesnenin son örnek nesne modülünde yayımlandığında son örneği noktaları yöntemi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Modül başvuru.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Modül Sınıfı](../windows/module-class.md)