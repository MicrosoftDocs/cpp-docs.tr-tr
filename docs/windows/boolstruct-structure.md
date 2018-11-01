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
ms.openlocfilehash: d79ea93bf95040efe79e3e3c57ceb3397fd257de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643410"
---
# <a name="boolstruct-structure"></a>BoolStruct Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Açıklamalar

`BoolStruct` Yapısını tanımlar olup olmadığını bir `ComPtr` bir arabirimin nesne ömrü yönetimi. `BoolStruct` tarafından dahili olarak kullanılan [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) işleci.

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Ad                          | Açıklama
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[BoolStruct::Member](#member) | Belirten bir [ComPtr](../windows/comptr-class.md) ya da bir arabirimin nesnenin ömrünü yönetmek değildir.

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

Belirten bir [ComPtr](../windows/comptr-class.md) ya da bir arabirimin nesnenin ömrünü yönetmek değildir.
