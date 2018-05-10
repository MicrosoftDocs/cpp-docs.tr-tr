---
title: HString::Operator&lt; işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs:
- C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8fae7195f048cd680be513bd54b635e2e1e9bbf7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="hstringoperatorlt-operator"></a>HString::Operator&lt; işleci
İkinci parametre ilk parametre olup değerinden gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lhs`  
 Karşılaştırma yapılacak ilk parametre. `lhs` bir HString başvuru olabilir.  
  
 `rhs`  
 Karşılaştırılacak ikinci parametre. `rhs` bir HString başvuru olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true` varsa `lhs` parametresi küçük `rhs` parametresi; Aksi halde, `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HString Sınıfı](../windows/hstring-class.md)