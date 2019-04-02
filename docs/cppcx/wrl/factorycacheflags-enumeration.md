---
title: FactoryCacheFlags Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 6fecacd6038d1c41e57515307c1b810d0623d16f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787129"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags Numaralandırması

Fabrika nesneleri önbelleğe alınıp alınmayacağını belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, önbelleğe alma İlkesi Fabrika olarak belirtilen [ModuleType](moduletype-enumeration.md) oluşturduğunuzda şablon parametresi bir [Modülü](module-class.md) nesne. Bu ilkeyi geçersiz kılmak için belirtin bir **FactoryCacheFlags** değeri bir Fabrika nesnesine oluşturduğunuzda.

|||
|-|-|
|`FactoryCacheDefault`|Önbelleğe alma İlkesi, `Module` nesnesi kullanılır.|
|`FactoryCacheEnabled`|Fabrika bağımsız olarak, önbelleğe alınmasını etkinleştirir `ModuleType` oluşturmak için kullanılan şablon parametresi bir `Module` nesne.|
|`FactoryCacheDisabled`|Fabrika bağımsız olarak, önbelleğe alma devre dışı bırakır `ModuleType` oluşturmak için kullanılan şablon parametresi bir `Module` nesne.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)