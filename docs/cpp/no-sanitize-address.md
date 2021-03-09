---
description: 'Hakkında daha fazla bilgi edinin: no_sanitize_address'
title: no_sanitize_address
ms.date: 11/04/2016
f1_keywords:
- no_sanitize_address__cpp
helpviewer_keywords:
- __declspec keyword [C++], no_sanitize_address
- no_sanitize_address __declspec keyword
ms.openlocfilehash: a18b60f666bc53ef72db3a6d230dc7531cc6bc1f
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470733"
---
# `no_sanitize_address`

**Microsoft'a Özgü**

**`__declspec(no_sanitize_address)`** Belirtici, derleyiciye işlevler, yerel değişkenler veya genel değişkenlerde adres Temizleme özelliğini devre dışı bırakacağını söyler. Bu tanımlayıcı, [Addresstemizleme](../sanitizers/asan.md)ile birlikte kullanılır.

> [!NOTE]
> **`__declspec(no_sanitize_address)`***çalışma zamanı* davranışını değil _derleyici_ davranışını devre dışı bırakır.

## <a name="example"></a>Örnek

Örnekler için [addresstemizleyebilir derleme başvurusuna](../sanitizers/asan-building.md#__declspecno_sanitize_address) bakın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`__declspec`](../cpp/declspec.md)\
[Lerimi](../cpp/keywords-cpp.md)\
[Addresstemizleme](../sanitizers/asan.md)
