---
title: Derleyici Uyarısı (Düzey 3) C4316
ms.date: 11/04/2016
f1_keywords:
- C4316
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
ms.openlocfilehash: 5f895a231c8b32d76e4ccd3c15ffae5717d8017f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402053"
---
# <a name="compiler-warning-level-3-c4316"></a>Derleyici Uyarısı (Düzey 3) C4316

Yığında ayrılmış nesne bu tür için hizalı olmayabilir.

Kullanarak ayrılan aşırı hizalanmış nesne `operator new` belirtilen hizalamaya sahip olmayabilir. Geçersiz kılma [new işleci](../../c-runtime-library/operator-new-crt.md) ve [delete işleci](../../c-runtime-library/operator-delete-crt.md) için aşırı hizalanmış türler hizalanmış ayırma yordamlarını kullanmasını sağlayarak — Örneğin, [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) ve [_aligned_free](../../c-runtime-library/reference/aligned-free.md). Aşağıdaki örnek, C4316 oluşturur:

```cpp
// C4316.cpp
// Test: cl /W3 /c C4316.cpp

__declspec(align(32)) struct S {}; // C4324

int main() {
    new S; // C4316
}
```