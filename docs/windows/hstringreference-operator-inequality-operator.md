---
title: HStringReference::Operator! = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
dev_langs:
- C++
ms.assetid: 01ab6691-1fc7-4feb-85f0-fe795593a160
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e2fc27d47fa218dd4378538bb193d650727ed22
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606533"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator!= İşleci
İki parametrenin eşit olup olmadığını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
inline bool operator!=(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator!=(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator!=(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
```  
  
### <a name="parameters"></a>Parametreler  
 *lhs*  
 Karşılaştırılacak ilk parametre. *lhs* olabilir bir **HStringReference** nesnesi veya bir HSTRING tanıtıcısına.  
  
 *Sol*  
 Karşılaştırılacak ikinci parametre.  *Sol* olabilir bir **HStringReference** nesnesi veya bir HSTRING tanıtıcısına.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa *lhs* ve *sol* parametreleri eşit; Aksi takdirde değil **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HStringReference Sınıfı](../windows/hstringreference-class.md)