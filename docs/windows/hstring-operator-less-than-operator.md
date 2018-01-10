---
title: "HString::Operator&lt; işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs: C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4cbb21e34255d5350702d949792656bdf0a849a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 Karşılaştırma yapılacak ilk parametre. `lhs`bir HString başvuru olabilir.  
  
 `rhs`  
 Karşılaştırılacak ikinci parametre. `rhs`bir HString başvuru olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `lhs` parametresi küçük `rhs` parametresi; Aksi halde, `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HString Sınıfı](../windows/hstring-class.md)