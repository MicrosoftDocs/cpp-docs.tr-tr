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
ms.openlocfilehash: 4f2a5acf6edb824cff2121c1b6444181b5cfcf98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371848"
---
# <a name="boolstruct-structure"></a>BoolStruct Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Açıklamalar

Yapı, `BoolStruct` a'nın `ComPtr` bir arabirimin nesne ömrünü yönetip yönetmediğini tanımlar. `BoolStruct`[BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype) işleci tarafından dahili olarak kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Adı                          | Açıklama
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[BoolStruct::Üye](#member) | [ComPtr'un](comptr-class.md) arabirimin nesne ömrünü yönetip yönetmeyeceğini belirtir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BoolStruct`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** internal.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="boolstructmember"></a><a name="member"></a>BoolStruct::Üye

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
int Member;
```

### <a name="remarks"></a>Açıklamalar

[ComPtr'un](comptr-class.md) arabirimin nesne ömrünü yönetip yönetmeyeceğini belirtir.
