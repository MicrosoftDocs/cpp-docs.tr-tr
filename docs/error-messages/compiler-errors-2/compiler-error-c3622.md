---
title: Derleyici Hatası C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 69565a1a2d159623bca927a94543834d18c13299
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518098"
---
# <a name="compiler-error-c3622"></a>Derleyici Hatası C3622

'class': bir sınıf 'anahtar sözcüğü' örneği olarak bildirilen

Olarak işaretlenmiş bir sınıf örneği için bir girişimde bulunuldu [soyut](../../windows/abstract-cpp-component-extensions.md). Bir sınıf olarak işaretlenmiş `abstract` bir temel sınıf olabilir, ancak örneği oluşturulamıyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3622 oluşturur.

```
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
