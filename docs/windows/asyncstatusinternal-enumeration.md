---
title: Asyncstatusınternal numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c7751929a55993876034bb3c1918b82193681fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016890"
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

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)