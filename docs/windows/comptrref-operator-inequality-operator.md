---
title: ComPtrRef::operator! = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
dev_langs:
- C++
ms.assetid: ab3093cc-6fbd-4039-890a-6df1cde992b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d5a6e7389215452177add30b587004c312aeae1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator!= İşleci
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator!=(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `a`  
 ComPtrRef bir nesneye başvuru.  
  
 `b`  
 Başka bir ComPtrRef nesne ya da bir işaretçi anonim bir nesneye başvuru (`void*`).  
  
## <a name="return-value"></a>Dönüş Değeri  
 İlk işleci veriyor `true` , nesne `a` nesnesine eşit değil `b`; Aksi halde, `false`.  
  
 İkinci ve üçüncü işleçleri verim `true` , nesne `a` eşit değil `nullptr`; Aksi halde, `false`.  
  
 Dördüncü ve beşinci işleçleri verim `true` , nesne `a` nesnesine eşit değil `b`; Aksi halde, `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 İki ComPtrRef nesnenin eşit olup olmadığını gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef Sınıfı](../windows/comptrref-class.md)