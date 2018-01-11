---
title: "Module::Create yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::Create
dev_langs: C++
helpviewer_keywords: Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1f025c446dd6a7dab9b37d126d65e640a02b939b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="modulecreate-method"></a>Module::Create Yöntemi
Bir modül bir örneğini oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW static Module& Create();  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<  
   typename T  
>  
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

 