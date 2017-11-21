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
ms.openlocfilehash: 0a5d3888657d491502b13283b5b9d7141940ade3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
[Modül sınıfı](../windows/module-class.md)

 