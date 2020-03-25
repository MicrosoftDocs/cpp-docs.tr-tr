---
title: AsyncStatusInternal Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: 0eadd1e3a287feecd36b00b231b42c31218352c1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214155"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal Numaralandırması

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>Açıklamalar

Zaman uyumsuz işlemlerin durumu ve `Windows::Foundation::AsyncStatus` numaralandırması arasındaki iç numaralandırmalar arasındaki eşlemeyi belirtir.

## <a name="members"></a>Üyeler

`_Created`<br/>
`::Windows::Foundation::AsyncStatus::Created` eşdeğerdir

`_Started`<br/>
`::Windows::Foundation::AsyncStatus::Started` eşdeğerdir

`_Completed`<br/>
`::Windows::Foundation::AsyncStatus::Completed` eşdeğerdir

`_Cancelled`<br/>
`::Windows::Foundation::AsyncStatus::Cancelled` eşdeğerdir

`_Error`<br/>
`::Windows::Foundation::AsyncStatus::Error` eşdeğerdir

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)
