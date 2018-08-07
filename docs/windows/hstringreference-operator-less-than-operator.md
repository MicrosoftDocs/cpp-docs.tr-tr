---
title: HStringReference::Operator&lt; işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
dev_langs:
- C++
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 489d97252dcb4d20b7ef2f8557991a4e6016743d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605538"
---
# <a name="hstringreferenceoperatorlt-operator"></a>HStringReference::Operator&lt; işleci
İkinci parametre ilk parametre olup değerinden gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
```  
  
### <a name="parameters"></a>Parametreler  
 *lhs*  
 Karşılaştırılacak ilk parametre. *lhs* başvuru olabilir bir **HStringReference**.  
  
 *Sol*  
 Karşılaştırılacak ikinci parametre.  *Sol* başvuru olabilir bir **HStringReference**.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa *lhs* parametresi değerinden daha küçük *sol* parametre; Aksi takdirde **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HStringReference Sınıfı](../windows/hstringreference-class.md)