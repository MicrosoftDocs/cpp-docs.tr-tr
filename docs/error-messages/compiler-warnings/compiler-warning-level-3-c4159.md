---
title: Derleyici Uyarısı (Düzey 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: e898af8f109ed23bd1784df7b39c174bbed675f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552288"
---
# <a name="compiler-warning-level-3-c4159"></a>Derleyici Uyarısı (Düzey 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>pragma pragma(pop,...): daha önce POP '*tanımlayıcı*'

## <a name="remarks"></a>Açıklamalar

Kaynak kodunuzu içeren bir **anında iletme** yönerge bir pragma için olan tanımlayıcıyla arkasından bir **pop** tanımlayıcısı olmayan yönergesi. Sonuç olarak, *tanımlayıcı* POP ve sonraki kullandığında, *tanımlayıcı* beklenmeyen davranışlara neden olabilir.

## <a name="example"></a>Örnek

Bu uyarıyı engellemek için bir tanımlayıcı verin **pop** yönergesi. Örneğin:

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```