---
title: Derleyici Uyarısı (düzey 1) C4794
ms.date: 11/04/2016
f1_keywords:
- C4794
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
ms.openlocfilehash: 7d669280c0dc6a730a22480e602dac8cc6153449
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052375"
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