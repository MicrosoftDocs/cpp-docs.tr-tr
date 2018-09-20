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
ms.openlocfilehash: 933d332ce2653fd8ea907a5fafda524ae0220906
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409005"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator= İşleci

Başka bir değer taşır **HStringReference** geçerli nesneye **HStringReference** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
HStringReference& operator=(HStringReference&& other) throw()  
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Mevcut bir **HStringReference** nesne.

## <a name="remarks"></a>Açıklamalar

Varolan değerin *diğer* nesne geçerli kopyalanır **HStringReference** nesnesi ve ardından *diğer* nesnesi yok edildiğinde.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HStringReference Sınıfı](../windows/hstringreference-class.md)