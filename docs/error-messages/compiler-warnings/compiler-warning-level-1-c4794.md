---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4794'
title: Derleyici Uyarısı (düzey 1) C4794
ms.date: 11/04/2016
f1_keywords:
- C4794
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
ms.openlocfilehash: bd43a9fb1f7f2433a4e1d337d49c1921211a9e5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334947"
---
# <a name="compiler-warning-level-1-c4794"></a>Derleyici Uyarısı (düzey 1) C4794

' bölüm adı ' olan ' değişken ' iş parçacığı yerel depolama değişkeninin segmenti '. TLS $ ' olarak değiştirildi

Bir TLS değişkenini. TLS $ ile başlamıyor bir bölüme koymak için [#pragma data_seg](../../preprocessor/data-seg.md) kullandınız.

. TLS $*x* bölümü, [__declspec (iş parçacığı)](../../cpp/thread.md) değişkenlerinin tanımlandığı nesne dosyasında bulunur. EXE veya DLL 'deki bir. TLS bölümü, bu bölümlerin oluşmasına neden olur.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4794 oluşturur:

```cpp
// C4794.cpp
// compile with: /W1 /c
#pragma data_seg(".someseg")
__declspec(thread) int i;   // C4794

// OK
#pragma data_seg(".tls$9")
__declspec(thread) int j;
```
