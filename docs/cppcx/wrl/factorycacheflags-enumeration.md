---
title: FactoryCacheFlags Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 250c8c8e7ade72bd1a9cd63f0b515774058f0723
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214012"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags Numaralandırması

Fabrika nesnelerinin önbelleğe alınıp alınmayacağını belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir [Modül](module-class.md) nesnesi oluşturduğunuzda, fabrika önbelleğe alma Ilkesi, [ModuleType](moduletype-enumeration.md) şablonu parametresi olarak belirtilir. Bu ilkeyi geçersiz kılmak için, bir Factory nesnesi oluştururken bir **FactoryCacheFlags** değeri belirtin.

|||
|-|-|
|`FactoryCacheDefault`|`Module` nesnesinin önbelleğe alma ilkesi kullanılır.|
|`FactoryCacheEnabled`|Bir `Module` nesnesi oluşturmak için kullanılan `ModuleType` şablonu parametresinden bağımsız olarak fabrika önbelleğe almayı sağlar.|
|`FactoryCacheDisabled`|Bir `Module` nesnesi oluşturmak için kullanılan `ModuleType` şablonu parametresinden bağımsız olarak fabrika önbelleğini devre dışı bırakır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)
