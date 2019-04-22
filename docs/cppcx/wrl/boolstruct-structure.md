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
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787688"
---
# <a name="boolstruct-structure"></a>BoolStruct Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Açıklamalar

`BoolStruct` Yapısını tanımlar olup olmadığını bir `ComPtr` bir arabirimin nesne ömrü yönetimi. `BoolStruct` tarafından dahili olarak kullanılan [BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype) işleci.

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Ad                          | Açıklama
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[BoolStruct::Member](#member) | Belirten bir [ComPtr](comptr-class.md) ya da bir arabirimin nesnenin ömrünü yönetmek değildir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BoolStruct`

## <a name="requirements"></a>Gereksinimler

**Başlık:** internal.h

**Namespace:** Microsoft::wrl:: details

## <a name="member"></a>BoolStruct::Member

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
int Member;
```

### <a name="remarks"></a>Açıklamalar

Belirten bir [ComPtr](comptr-class.md) ya da bir arabirimin nesnenin ömrünü yönetmek değildir.
