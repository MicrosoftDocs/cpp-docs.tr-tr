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
ms.openlocfilehash: 17acdca8af1250b1f88fa8a6858ffa1854f8ca8c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426412"
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

*lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* başvuru olabilir bir **HStringReference**.

*Sol*<br/>
Karşılaştırılacak ikinci parametre.  *Sol* başvuru olabilir bir **HStringReference**.

## <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *lhs* parametresi değerinden daha küçük *sol* parametre; Aksi takdirde **false**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HStringReference Sınıfı](../windows/hstringreference-class.md)