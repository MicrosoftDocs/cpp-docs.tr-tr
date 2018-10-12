---
title: Issame yapısı | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
- internal/Microsoft::WRL::Details::IsSame::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::IsSame structure
- Microsoft::WRL::Details::IsSame::value constant
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2af59860016835f8e8dfddc9d0a77204ff866bd3
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161859"
---
# <a name="issame-structure"></a>IsSame Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T1, typename T2>
struct IsSame;

template <typename T1>
struct IsSame<T1, T1>;
```

### <a name="parameters"></a>Parametreler

*T1*<br/>
Bir tür.

*T2*<br/>
Başka bir tür.

## <a name="remarks"></a>Açıklamalar

Belirtilen türü testleri bir türü belirtilmiş olup olmadığını başka aynıdır.

## <a name="members"></a>Üyeler

### <a name="public-constants"></a>Genel sabitler

Ad                    | Açıklama
----------------------- | --------------------------------------------------
[Issame::Value](#value) | Bir türden diğerine aynı olup olmadığını belirtir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IsSame`

## <a name="requirements"></a>Gereksinimler

**Başlık:** internal.h

**Namespace:** Microsoft::wrl:: details

## <a name="value"></a>Issame::Value

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
template <typename T1, typename T2>
struct IsSame
{
    static const bool value = false;
};

template <typename T1>
struct IsSame<T1, T1>
{
    static const bool value = true;
};
```

### <a name="remarks"></a>Açıklamalar

Bir türden diğerine aynı olup olmadığını belirtir.

`value` olan **true** şablon parametreleri aynı ise ve **false** şablon parametreleri farklıysa.
