---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4628'
title: Derleyici Uyarısı (düzey 1) C4628
ms.date: 11/04/2016
f1_keywords:
- C4628
helpviewer_keywords:
- C4628
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
ms.openlocfilehash: b5dd017afb5b8bb0d882700cb047643d6d118685
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112381"
---
# <a name="compiler-warning-level-1-c4628"></a>Derleyici Uyarısı (düzey 1) C4628

-Ze ile digraf kullanılması desteklenmez. 'digraph' karakter dizisi 'char' için alternatif bir belirteç olarak yorumlanmadı

[/Ze](../../build/reference/za-ze-disable-language-extensions.md)altında digraf desteklenmez. Bu uyarıya bir hata gelir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4628 oluşturur:

```cpp
// C4628.cpp
// compile with: /WX
#pragma warning(default : 4628)
int main()
<%   // C4628 <% digraph for {
}
```
