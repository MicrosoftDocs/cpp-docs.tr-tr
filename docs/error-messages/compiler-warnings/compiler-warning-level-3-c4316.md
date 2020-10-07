---
title: Derleyici Uyarısı (düzey 3) C4316
description: C++ Derleyici Uyarısı C4316 açıklaması
ms.date: 11/04/2016
f1_keywords:
- C4316
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
ms.openlocfilehash: 3cb512aa9b851f3b3b26f7a50854a4d887087e81
ms.sourcegitcommit: 8caaf5e00aeb727741a273aecafa15de293426cf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2020
ms.locfileid: "91806570"
---
# <a name="compiler-warning-level-3-c4316"></a>Derleyici Uyarısı (düzey 3) C4316

Yığında ayrılan nesne bu tür için hizalanmamış olabilir.

Kullanılarak ayrılan, üzerine hizalanmış bir nesne `operator new` belirtilen hizalamaya sahip olmayabilir. Hizalı ayırma yordamlarını (örneğin, [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) ve [_aligned_free](../../c-runtime-library/reference/aligned-free.md)kullanması için, daha fazla hizalanmış türler için işleç [New](../../c-runtime-library/new-operator-crt.md) ve [Delete işlecini](../../c-runtime-library/delete-operator-crt.md) geçersiz kılın. Aşağıdaki örnek C4316 oluşturur:

```cpp
// C4316.cpp
// Test: cl /W3 /c C4316.cpp

__declspec(align(32)) struct S {}; // C4324

int main() {
    new S; // C4316
}
```
