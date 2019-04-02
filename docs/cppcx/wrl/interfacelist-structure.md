---
title: InterfaceList Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
ms.openlocfilehash: 70565081338f953abb65d2cdc7c5f1eb869f75e5
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787606"
---
# <a name="interfacelist-structure"></a>InterfaceList Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T, typename U>
struct InterfaceList;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Arabirim adı; özyinelemeli listedeki ilk arabirim.

*U*<br/>
Arabirim adı; özyinelemeli listesinde kalan arabirimler.

## <a name="remarks"></a>Açıklamalar

Arabirimleri özyinelemeli listesini oluşturmak için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`FirstT`|Şablon parametresi için eş anlamlı *T*.|
|`RestT`|Şablon parametresi için eş anlamlı *U*.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InterfaceList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)