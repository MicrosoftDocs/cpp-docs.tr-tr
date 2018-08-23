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
ms.openlocfilehash: 7045229cc15304a88253f97e1ad3c9f171f139a0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597134"
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