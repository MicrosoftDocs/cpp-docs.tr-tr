---
title: DontUseNewUseMake sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs:
- C++
helpviewer_keywords:
- DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc2b2f03cfbd488de8358b2e4b123716efcbfe15
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431315"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Açıklamalar

İşleç engel **yeni** içinde `RuntimeClass`. Sonuç olarak, kullanmanız gereken [olun işlevi](../windows/make-function.md) yerine.

## <a name="members"></a>Üyeler

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[DontUseNewUseMake::operator new İşleci](../windows/dontusenewusemake-operator-new-operator.md)|İşleç aşırı **yeni** ve içinde kullanılmasını engeller `RuntimeClass`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DontUseNewUseMake`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)<br/>
[Make İşlevi](../windows/make-function.md)