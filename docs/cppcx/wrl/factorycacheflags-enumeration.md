---
description: 'Daha fazla bilgi edinin: FactoryCacheFlags sabit listesi'
title: FactoryCacheFlags Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 68a86049bf1f6287a84ae4df2e27dbe3c63c91c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198511"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags Numaralandırması

Fabrika nesnelerinin önbelleğe alınıp alınmayacağını belirler.

## <a name="syntax"></a>Syntax

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir [Modül](module-class.md) nesnesi oluşturduğunuzda, fabrika önbelleğe alma Ilkesi, [ModuleType](moduletype-enumeration.md) şablonu parametresi olarak belirtilir. Bu ilkeyi geçersiz kılmak için, bir Factory nesnesi oluştururken bir **FactoryCacheFlags** değeri belirtin.

| İlke | Açıklama |
|-|-|
|`FactoryCacheDefault`|Nesnesinin önbelleğe alma ilkesi `Module` kullanılır.|
|`FactoryCacheEnabled`|`ModuleType`Bir nesne oluşturmak için kullanılan şablon parametresinden bağımsız olarak fabrika önbelleğe almayı sağlar `Module` .|
|`FactoryCacheDisabled`|`ModuleType`Bir nesne oluşturmak için kullanılan şablon parametresi ne olursa olsun, fabrika önbelleğini devre dışı bırakır `Module` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
