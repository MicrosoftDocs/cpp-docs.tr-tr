---
title: Derleyici Uyarısı (düzey 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: 30e2ecb1d5e0de290c028cdfb53c7df831a732b4
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966456"
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