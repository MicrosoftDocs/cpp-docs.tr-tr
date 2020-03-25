---
title: Derleyici Uyarısı (düzey 1) C4964
ms.date: 11/04/2016
f1_keywords:
- C4964
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
ms.openlocfilehash: 7852340bc056e126238a2d9c7493887ef3caf93e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174498"
---
# <a name="compiler-warning-level-1-c4964"></a>Derleyici Uyarısı (düzey 1) C4964

İyileştirme seçeneği belirtilmedi; Profil bilgileri toplanmayacak

[/GL](../../build/reference/gl-whole-program-optimization.md) ve [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) belirtildi, ancak hiçbir iyileştirme istenmedi, bu nedenle hiçbir. pgc dosyası oluşturulmayacak ve bu nedenle, profil temelli en iyi duruma getirme mümkün olmayacak.

Uygulamanızı çalıştırdığınızda. pgc dosyalarının oluşturulmasını istiyorsanız, [/o](../../build/reference/o-options-optimize-code.md) derleyici seçeneklerinden birini belirtin.

Aşağıdaki örnek C4964 oluşturur:

```cpp
// C4964.cpp
// compile with: /W1 /GL /link /ltcg:pgi
// C4964 expected
// Add /O2, for example, to the command line to resolve this warning.
int main() {
   int i;
}
```
