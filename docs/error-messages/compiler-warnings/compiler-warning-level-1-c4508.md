---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4508'
title: Derleyici Uyarısı (düzey 1) C4508
ms.date: 11/04/2016
f1_keywords:
- C4508
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
ms.openlocfilehash: 4394f102c91934a949cdbbc82418d136187cbb7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294853"
---
# <a name="compiler-warning-level-1-c4508"></a>Derleyici Uyarısı (düzey 1) C4508

' function ': işlev bir değer döndürmelidir; ' void ' dönüş türü varsayıldı

İşlevin dönüş türü belirtilmemiş. Bu durumda, C4430 de tetiklemelidir ve derleyici C4430 tarafından bildirilen çözümü uygular (varsayılan değer int 'tir).

Bu uyarıyı çözmek için işlevlerin dönüş türünü açıkça bildirin.

Aşağıdaki örnek C4508 oluşturur:

```cpp
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```
