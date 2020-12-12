---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4377'
title: Derleyici Uyarısı (düzey 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: 674bfb69a20c901f20509a7359ed408b0e38f479
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185706"
---
# <a name="compiler-warning-level-1-c4377"></a>Derleyici Uyarısı (düzey 1) C4377

yerel türler varsayılan olarak özeldir; -D1privatenativetypes kullanımdan kalktı kullanım dışıdır

Önceki sürümlerde, derlemelerdeki yerel türler varsayılan olarak geneldir ve özel hale getirmek için dahili, belgelenmemiş bir derleyici seçeneği (**/d1PrivateNativeTypes**) kullanılmıştı.

Tüm türler, yerel ve CLR artık bir derlemede varsayılan olarak özeldir, bu nedenle **/d1PrivateNativeTypes** artık gerekli değildir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4377 oluşturur.

```cpp
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```
