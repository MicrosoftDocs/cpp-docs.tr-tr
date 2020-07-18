---
title: Derleyici Uyarısı (düzey 1) C4293
description: MSVC derleyicisi uyarı C4293 nedenlerini açıklar ve nasıl düzeltileceğini gösterir.
ms.date: 07/15/2020
f1_keywords:
- C4293
helpviewer_keywords:
- C4293
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
ms.openlocfilehash: 3b5a05d4a744b084f1cc34210a5374962064e85d
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446482"
---
# <a name="compiler-warning-level-1-c4293"></a>Derleyici Uyarısı (düzey 1) C4293

> '*operator*': kaydırma sayısı negatif veya çok büyük, tanımsız davranış

Bir kaydırma sayısı negatifse veya çok büyükse, sonuçta elde edilen görüntünün davranışı tanımsızdır.

## <a name="remarks"></a>Açıklamalar

Bu sorunu çözmek için, ilk işlenen üzerinde bir cast kullanarak sonuç türünün boyutuna genişletebilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4293 oluşturur ve bu hatayı gidermeye yönelik yolları gösterir:

```cpp
// C4293.cpp
// compile with: /c /W1
unsigned __int64 combine (unsigned lo, unsigned hi)
{
   return (hi << 32) | lo;   // C4293

   // In C, try the following line instead:
   // return ( (unsigned __int64)hi << 32) | lo;
   // In C++, try this line instead:
   // return (static_cast<unsigned __int64>(hi) << 32) | lo;
}
```
