---
title: Derleyici Uyarısı (düzey 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: b75b6bee88d0b72e77b32e58ae2f4634a9c30fa0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187004"
---
# <a name="compiler-warning-level-1-c4377"></a>Derleyici Uyarısı (düzey 1) C4377

yerel türler varsayılan olarak özeldir; -D1privatenativetypes kullanımdan kalktı kullanım dışıdır

Önceki sürümlerde, derlemelerdeki yerel türler varsayılan olarak geneldir ve özel hale getirmek için dahili, belgelenmemiş bir derleyici seçeneği ( **/d1PrivateNativeTypes**) kullanılmıştı.

Tüm türler, yerel ve CLR artık bir derlemede varsayılan olarak özeldir, bu nedenle **/d1PrivateNativeTypes** artık gerekli değildir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4377 oluşturur.

```cpp
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```
