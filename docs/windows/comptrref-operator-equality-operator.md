---
title: "ComPtrRef::operator == işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::operator==
dev_langs: C++
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cc55ab734229cc256f47185349ce79049d05723b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator== İşleci
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator==(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `a`  
 ComPtrRef bir nesneye başvuru.  
  
 `b`  
 Başka bir ComPtrRef nesne ya da anonim bir tür için bir işaretçi başvuru (`void*`).  
  
## <a name="return-value"></a>Dönüş Değeri  
 İlk işleci veriyor `true` , nesne `a` nesnesine eşit olan `b`; Aksi halde, `false`.  
  
 İkinci ve üçüncü işleçleri verim `true` , nesne `a` eşittir `nullptr`; Aksi halde, `false`.  
  
 Dördüncü ve beşinci işleçleri verim `true` , nesne `a` nesnesine eşit olan `b`; Aksi halde, `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 İki ComPtrRef nesnenin eşit olup olmadığını gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef sınıfı](../windows/comptrref-class.md)