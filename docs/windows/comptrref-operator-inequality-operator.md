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
ms.openlocfilehash: 7ebe71706ce1091ee21fc6fbd63e65b201c096b5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462930"
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
 *a*  
 Bir başvuru bir **ComPtrRef** nesne.  
  
 *b*  
 Başka bir başvuru **ComPtrRef** nesne veya anonim bir nesneye bir işaretçi (`void*`).  
  
## <a name="return-value"></a>Dönüş Değeri  
 İlk işleç sayıları **true** , nesne *bir* nesnesine eşit değil *b*; Aksi takdirde **false**.  
  
 İkinci ve üçüncü işleçleri yield **true** , nesne *bir* eşit değildir **nullptr**; Aksi takdirde **false**.  
  
 Dördüncü ve beşinci işleçleri yield **true** , nesne *bir* nesnesine eşit değil *b*; Aksi takdirde **false**.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtir olup iki **ComPtrRef** nesneler eşit değildir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef Sınıfı](../windows/comptrref-class.md)