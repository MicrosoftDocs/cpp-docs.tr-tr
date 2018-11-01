---
title: FactoryCacheFlags Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 8320563991981f7a49d4775a2bad9c487124d907
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595656"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags Numaralandırması

Fabrika nesneleri önbelleğe alınıp alınmayacağını belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, önbelleğe alma İlkesi Fabrika olarak belirtilen [ModuleType](../windows/moduletype-enumeration.md) oluşturduğunuzda şablon parametresi bir [Modülü](../windows/module-class.md) nesne. Bu ilkeyi geçersiz kılmak için belirtin bir **FactoryCacheFlags** değeri bir Fabrika nesnesine oluşturduğunuzda.

|||
|-|-|
|`FactoryCacheDefault`|Önbelleğe alma İlkesi, `Module` nesnesi kullanılır.|
|`FactoryCacheEnabled`|Fabrika bağımsız olarak, önbelleğe alınmasını etkinleştirir `ModuleType` oluşturmak için kullanılan şablon parametresi bir `Module` nesne.|
|`FactoryCacheDisabled`|Fabrika bağımsız olarak, önbelleğe alma devre dışı bırakır `ModuleType` oluşturmak için kullanılan şablon parametresi bir `Module` nesne.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)