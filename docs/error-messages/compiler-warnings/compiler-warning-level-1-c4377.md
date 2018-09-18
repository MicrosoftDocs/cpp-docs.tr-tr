---
title: Derleyici Uyarısı (düzey 1) C4377 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4377
dev_langs:
- C++
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 613ebe183b61c6b9894ed3b726f90061e2b24ef6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047180"
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