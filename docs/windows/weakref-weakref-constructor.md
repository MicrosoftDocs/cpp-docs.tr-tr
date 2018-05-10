---
title: WeakRef::WeakRef Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef, constructor
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ae70dabdd86fedf82c26c0c7d9a09d842e2310e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
 İlk Oluşturucu boş WeakRef nesneyi başlatır. İkinci Oluşturucu, bir işaretçi bir WeakRef nesnesi IWeakReference arabirimine başlatır. Bir ComPtr başvuru WeakRef nesnesinden üçüncü Oluşturucu başlatır\<IWeakReference > nesne. Dördüncü ve beşinci oluşturucular başka bir WeakRef nesne WeakRef nesnesinden başlatır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakRef Sınıfı](../windows/weakref-class.md)