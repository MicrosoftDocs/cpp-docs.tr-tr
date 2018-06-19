---
title: WeakRef::operator&amp; işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c8221b405618b1879f4e4c865115a227eb09857
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890127"
---
# <a name="weakrefoperatoramp-operator"></a>WeakRef::operator&amp; işleci
Geçerli WeakRef nesnesini temsil eden bir ComPtrRef nesnesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&() throw()  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli WeakRef nesnesini temsil eden bir ComPtrRef nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Kodunuzda kullanılmak üzere tasarlanmamıştır iç yardımcı operatörün budur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakRef Sınıfı](../windows/weakref-class.md)