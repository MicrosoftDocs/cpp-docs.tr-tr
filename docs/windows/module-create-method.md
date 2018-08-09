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
ms.openlocfilehash: 1b3f865addd83bec64250807285947ea1c92e59f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016619"
---
# <a name="modulecreate-method"></a>Module::Create Yöntemi
Bir modülün örneği oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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