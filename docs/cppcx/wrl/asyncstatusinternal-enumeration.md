---
description: 'Daha fazla bilgi edinin: AsyncStatusInternal numaralandırması'
title: AsyncStatusInternal Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: 3227699a0e7b8933dc5839e65fb3489328d3b1f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175800"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal Numaralandırması

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Syntax

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>Açıklamalar

Zaman uyumsuz işlemlerin ve numaralandırmanın durumunun iç numaralandırmalar arasındaki eşlemeyi belirtir `Windows::Foundation::AsyncStatus` .

## <a name="members"></a>Üyeler

`_Created`<br/>
Eşdeğer `::Windows::Foundation::AsyncStatus::Created`

`_Started`<br/>
Eşdeğer `::Windows::Foundation::AsyncStatus::Started`

`_Completed`<br/>
Eşdeğer `::Windows::Foundation::AsyncStatus::Completed`

`_Cancelled`<br/>
Eşdeğer `::Windows::Foundation::AsyncStatus::Cancelled`

`_Error`<br/>
Eşdeğer `::Windows::Foundation::AsyncStatus::Error`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
