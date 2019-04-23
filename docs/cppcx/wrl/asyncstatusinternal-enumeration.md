---
title: AsyncStatusInternal Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: f12bf4aafc87e44a6e2fb15ba79de4a9744bea58
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029732"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal Numaralandırması

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>Açıklamalar

Zaman uyumsuz işlemler durumu için iç sabit listeleri arasındaki eşlemeyi belirtir ve `Windows::Foundation::AsyncStatus` sabit listesi.

## <a name="members"></a>Üyeler

`_Created`<br/>
Eşdeğerdir `::Windows::Foundation::AsyncStatus::Created`

`_Started`<br/>
Eşdeğerdir `::Windows::Foundation::AsyncStatus::Started`

`_Completed`<br/>
Eşdeğerdir `::Windows::Foundation::AsyncStatus::Completed`

`_Cancelled`<br/>
Eşdeğerdir `::Windows::Foundation::AsyncStatus::Cancelled`

`_Error`<br/>
Eşdeğerdir `::Windows::Foundation::AsyncStatus::Error`

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)