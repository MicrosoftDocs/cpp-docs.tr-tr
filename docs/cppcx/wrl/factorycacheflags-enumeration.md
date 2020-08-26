---
title: FactoryCacheFlags Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 3381b2bcfcbf298270b547199ae614291855a2f7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843280"
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
