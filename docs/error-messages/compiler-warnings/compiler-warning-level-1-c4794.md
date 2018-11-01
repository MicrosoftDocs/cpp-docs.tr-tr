---
title: Derleyici Uyarısı (düzey 1) C4794
ms.date: 11/04/2016
f1_keywords:
- C4794
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
ms.openlocfilehash: d44e3af88de9457fdc5c2df905ccbae22d3562da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464083"
---
# <a name="compiler-warning-level-1-c4794"></a>Derleyici Uyarısı (düzey 1) C4794

'variable 'bölüm adı', '.tls$ için' değiştirildi' iş parçacığı yerel depolama değişkeninin segmenti

Kullanılan [kullanılmadan önce #pragma data_seg](../../preprocessor/data-seg.md) başlamıyor .tls$ ile bir bölümünde bir tls değişkeni yerleştirmek için.

.Tls$*x* bölümü nesne dosyasında var olduğu [gt;__declspec(thread)](../../cpp/thread.md) değişkenler tanımlanır. Bir EXE veya DLL .tls bölümü şu bölümlerden neden olur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4794 oluşturur:

```
// C4794.cpp
// compile with: /W1 /c
#pragma data_seg(".someseg")
__declspec(thread) int i;   // C4794

// OK
#pragma data_seg(".tls$9")
__declspec(thread) int j;
```