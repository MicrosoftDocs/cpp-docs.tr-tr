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
ms.openlocfilehash: 99ede64c239909956f1f767db34a2a6a14c02314
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874895"
---
# <a name="modulecreate-method"></a>Module::Create Yöntemi
Bir modül bir örneğini oluşturur.  
  
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
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Modül türü.  
  
 `callback`  
 Modülün son örnek nesne serbest bırakıldığında çağrılır.  
  
 `object`  
 `object` Ve `method` parametreleri birlikte kullanılır. Modül son örnek nesnesinde serbest bırakıldığında son örnek nesne işaret eder.  
  
 `method`  
 `object` Ve `method` parametreleri birlikte kullanılır. Modül son örnek nesnesinde serbest bırakıldığında son örnek nesnesinin noktalarını yöntemi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Modül başvuru.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Modül Sınıfı](../windows/module-class.md)

 