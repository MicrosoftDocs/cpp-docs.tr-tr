---
description: 'Hakkında daha fazla bilgi edinin: bad_any_cast sınıfı'
title: bad_any_cast sınıfı
ms.date: 04/04/2019
f1_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
helpviewer_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
ms.openlocfilehash: 5b38405bf1fc826592995df4037c5853e88ad9eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321633"
---
# <a name="bad_any_cast-class"></a>bad_any_cast sınıfı

Bir tarafından oluşturulan nesneler başarısız oldu `any_cast` .

## <a name="syntax"></a>Syntax

```cpp
class bad_any_cast
```

### <a name="member-functions"></a>Üye işlevleri

|Ad|Açıklama|
|-|-|
|[Yazdırılacak](#what)|Türü döndürür.|

## <a name="what"></a><a name="what"></a> Yazdırılacak

Türü döndürür.

```cpp
const char* what() const noexcept override;
```
