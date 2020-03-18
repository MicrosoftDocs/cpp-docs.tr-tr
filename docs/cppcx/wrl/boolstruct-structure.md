---
title: BoolStruct Yapısı
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
- internal/Microsoft::WRL::Details::BoolStruct::Member
helpviewer_keywords:
- Microsoft::WRL::Details::BoolStruct structure
- Microsoft::WRL::Details::BoolStruct::Member data member
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
ms.openlocfilehash: cdec425e317585abbd9730447e2c4fbb19b8250a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418337"
---
# <a name="boolstruct-structure"></a>BoolStruct Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Açıklamalar

`BoolStruct` yapısı, bir `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini tanımlar. `BoolStruct`, [BoolType ()](comptr-class.md#operator-microsoft-wrl-details-booltype) işleci tarafından dahili olarak kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Adı                          | Açıklama
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[BoolStruct:: member](#member) | Bir arabirimin nesne ömrünü yöneten bir [ComPtr](comptr-class.md) veya değil olduğunu belirtir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BoolStruct`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** iç. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="member"></a>BoolStruct:: member

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
int Member;
```

### <a name="remarks"></a>Açıklamalar

Bir arabirimin nesne ömrünü yöneten bir [ComPtr](comptr-class.md) veya değil olduğunu belirtir.
