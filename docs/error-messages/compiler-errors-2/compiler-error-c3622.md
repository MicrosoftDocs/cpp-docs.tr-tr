---
title: Derleyici Hatası C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: ed307f46db1261d79d5b0ec6b36852cac2e6d13e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781919"
---
# <a name="compiler-error-c3622"></a>Derleyici Hatası C3622

'class': bir sınıf 'anahtar sözcüğü' örneği olarak bildirilen

Olarak işaretlenmiş bir sınıf örneği için bir girişimde bulunuldu [soyut](../../extensions/abstract-cpp-component-extensions.md). Bir sınıf olarak işaretlenmiş `abstract` bir temel sınıf olabilir, ancak örneği oluşturulamıyor.

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
