---
title: "WeakRef::WeakRef Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::WeakRef::WeakRef
dev_langs: C++
helpviewer_keywords: WeakRef, constructor
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8a4b9c6648937813a02ca842407dbb07577f289f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="weakrefweakref-constructor"></a>WeakRef::WeakRef Oluşturucusu
WeakRef sınıfı yeni bir örneğini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WeakRef();  
WeakRef(  
   decltype(__nullptr)  
);  
  
WeakRef(  
   _In_opt_ IWeakReference* ptr  
);  
  
WeakRef(  
   const ComPtr<IWeakReference>& ptr  
);  
  
WeakRef(  
   const WeakRef& ptr  
);  
  
WeakRef(  
   _Inout_ WeakRef&& ptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ptr`  
 İşaretçi, başvuru veya rvalue başvuru var olan nesneye geçerli WeakRef nesnesini başlatır.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu boş WeakRef nesneyi başlatır. İkinci Oluşturucu, bir işaretçi bir WeakRef nesnesi IWeakReference arabirimine başlatır. Bir ComPtr başvuru WeakRef nesnesinden üçüncü Oluşturucu başlatır\< IWeakReference > nesne. Dördüncü ve beşinci oluşturucular başka bir WeakRef nesne WeakRef nesnesinden başlatır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakRef sınıfı](../windows/weakref-class.md)