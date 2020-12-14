---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4716'
title: Derleyici Uyarısı (düzey 1) C4716
ms.date: 11/04/2016
f1_keywords:
- C4716
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
ms.openlocfilehash: 3ea67c6220cfda97989e4ea095856082608aab0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249080"
---
# <a name="compiler-warning-level-1-c4716"></a>Derleyici Uyarısı (düzey 1) C4716

' function ' bir değer döndürmelidir

Verilen işlev bir değer döndürmedi.

Yalnızca void dönüş türüne sahip işlevler return komutunu, eşlik eden bir dönüş değeri olmadan kullanabilir.

Bu işlev çağrıldığında tanımsız bir değer döndürülür.

Bu uyarı otomatik olarak bir hataya yükseltilir. Bu davranışı değiştirmek isterseniz [#pragma uyarı](../../preprocessor/warning.md)kullanın.

Aşağıdaki örnek C4716 oluşturur:

```cpp
// C4716.cpp
// compile with: /c /W1
// C4716 expected
#pragma warning(default:4716)
int test() {
   // uncomment the following line to resolve
   // return 0;
}
```
