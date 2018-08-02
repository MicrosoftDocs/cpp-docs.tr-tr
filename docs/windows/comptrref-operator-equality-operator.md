---
title: ComPtrRef::operator == işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator==
dev_langs:
- C++
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 606059712e60ba181998155b55ae02ba8b27c4da
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463960"
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
 *a*  
 ComPtrRef nesnesine bir başvuru.  
  
 *b*  
 ComPtrRef başka bir nesne veya anonim bir tür için bir işaretçi başvuru (`void*`).  
  
## <a name="return-value"></a>Dönüş Değeri  
 İlk işleç sayıları **true** , nesne *bir* nesneye eşit olup *b*; Aksi takdirde **false**.  
  
 İkinci ve üçüncü işleçleri yield **true** , nesne *bir* eşittir **nullptr**; Aksi takdirde **false**.  
  
 Dördüncü ve beşinci işleçleri yield **true** , nesne *bir* nesneye eşit olup *b*; Aksi takdirde **false**.  
  
## <a name="remarks"></a>Açıklamalar  
 ComPtrRef iki nesnenin eşit olup olmadığını gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef Sınıfı](../windows/comptrref-class.md)