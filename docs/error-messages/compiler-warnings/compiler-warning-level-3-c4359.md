---
title: Derleyici Uyarısı (Düzey 3) C4359
ms.date: 11/04/2016
f1_keywords:
- C4359
helpviewer_keywords:
- C4359
ms.assetid: d8fe993c-ef82-45a0-a43d-c29f9d1bacdb
ms.openlocfilehash: 3856c50aabce497f28a179b30346b30371986e51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432818"
---
# <a name="compiler-warning-level-3-c4359"></a>Derleyici Uyarısı (Düzey 3) C4359

'type': Gerçek hizalama (8) __declspec(align()) içinde belirtilen değerden büyükse

Bir türü için belirtilen hizalama veri üyelerini birinin türü hizalamasını küçüktür.  Daha fazla bilgi için [hizalama](../../cpp/align-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4359 oluşturur.

```
// C4359.cpp
// compile with: /W3 /c
struct __declspec(align(8)) C8 { __int64 i; };
struct __declspec(align(4)) C4  { C8 m8; };   // C4359
struct __declspec(align(8)) C8_b  { C8 m8; };   // OK
struct __declspec(align(16)) C16  { C8 m8; };   // OK
```