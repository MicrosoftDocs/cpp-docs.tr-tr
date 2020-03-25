---
title: Derleyici Uyarısı (düzey 1) C4794
ms.date: 11/04/2016
f1_keywords:
- C4794
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
ms.openlocfilehash: 7f7ea7555937069caf5f83c9bf00f0fa980ef020
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175122"
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
