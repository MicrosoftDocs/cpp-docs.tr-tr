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
ms.openlocfilehash: 84725ca0ceeb4778bec2add60c7e96eff3ab3bfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [HString sınıfı](../windows/hstring-class.md)