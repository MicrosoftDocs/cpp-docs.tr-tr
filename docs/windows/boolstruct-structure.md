---
title: BoolStruct yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
- internal/Microsoft::WRL::Details::BoolStruct::Member
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::BoolStruct structure
- Microsoft::WRL::Details::BoolStruct::Member data member
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 74a292f2253d29730e8ee9104ea81308081c0496
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234274"
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
