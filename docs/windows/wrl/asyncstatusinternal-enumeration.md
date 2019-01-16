---
title: AsyncStatusInternal Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: b38d58603eafeaa76c79873bbf375b4a3b405cdb
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335208"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)