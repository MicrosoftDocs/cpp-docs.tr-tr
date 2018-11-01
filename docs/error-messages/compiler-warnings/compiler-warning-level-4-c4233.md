---
title: Derleyici Uyarısı (düzey 4) C4233
ms.date: 10/25/2017
f1_keywords:
- C4233
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
ms.openlocfilehash: 361e00b7361aab51ea077d7e248503f3654e5e58
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516525"
---
# <a name="compiler-warning-level-4-c4233"></a>Derleyici Uyarısı (düzey 4) C4233

> Standart olmayan uzantı kullanıldı: '*anahtar sözcüğü*' anahtar sözcüğü yalnızca C++, C'değil ' da desteklenir.

C++ yerine C olarak derleyici kaynak kodunuzu derlediği ve yalnızca C++'da geçerli bir anahtar sözcüğü kullanılır. Kaynak dosyasının uzantısı .c veya kullandığınız kaynak dosyanızı derleyici C derler [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

Bu uyarı, bir hata için otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, [#pragma Uyarısı](../../preprocessor/warning.md). Örneğin, bir düzey 4 uyarısı sorunu C4233 yapmak için kaynak kodu dosyanızda bu satırı ekleyin:

```cpp
#pragma warning(4:4233)
```
