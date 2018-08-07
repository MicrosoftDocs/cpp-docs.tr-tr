---
title: HStringReference::Operator = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs:
- C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc8f919dcec994be5d4f0300e9c96dde95895e16
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608527"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator= İşleci
Başka bir değer taşır **HStringReference** geçerli nesneye **HStringReference** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
### <a name="parameters"></a>Parametreler  
 *Diğer*  
 Mevcut bir **HStringReference** nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Varolan değerin *diğer* nesne geçerli kopyalanır **HStringReference** nesnesi ve ardından *diğer* nesnesi yok edildiğinde.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HStringReference Sınıfı](../windows/hstringreference-class.md)