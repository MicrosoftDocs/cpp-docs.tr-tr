---
title: Derleyici Uyarısı (düzey 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: d8c89967e0dc900e098ca03d22932451f26a6a0a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531038"
---
# <a name="compiler-warning-level-1-c4377"></a>Derleyici Uyarısı (düzey 1) C4377

Yerel türler varsayılan olarak özeldir; -d1PrivateNativeTypes kullanım dışıdır

Önceki sürümlerde, bütünleştirilmiş kodlarında yerel türler varsayılan ve belgelenmemiş, iç derleyici seçeneği tarafından genel (**/d1PrivateNativeTypes**) özel hale getirmek için kullanıldı.

Tüm türleri, yerel ve CLR, artık varsayılan olarak, derleme özel olan şekilde **/d1PrivateNativeTypes** artık gerekli değildir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4377 oluşturur.

```
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```