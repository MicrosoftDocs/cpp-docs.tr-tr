---
title: "HStringReference::Operator&lt; işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
dev_langs:
- C++
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ac370a8d863e7c71dcd3564b3a5d0ae7d214322d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreferenceoperatorlt-operator"></a>HStringReference::Operator&lt; işleci
İkinci parametre ilk parametre olup değerinden gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lhs`  
 Karşılaştırma yapılacak ilk parametre. `lhs`bir HStringReference başvuru olabilir.  
  
 `rhs`  
 Karşılaştırılacak ikinci parametre.  `rhs`bir HStringReference başvuru olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `lhs` parametresi küçük `rhs` parametresi; Aksi halde, `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HStringReference Sınıfı](../windows/hstringreference-class.md)