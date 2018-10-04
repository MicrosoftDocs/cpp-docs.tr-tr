---
title: Interfacelist yapısı | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
dev_langs:
- C++
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d9cbc1dfb31d744086e7a138521ae24f58e693f
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788662"
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

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)