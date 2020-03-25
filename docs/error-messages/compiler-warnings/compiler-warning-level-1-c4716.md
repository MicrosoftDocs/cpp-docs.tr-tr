---
title: Derleyici Uyarısı (düzey 1) C4716
ms.date: 11/04/2016
f1_keywords:
- C4716
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
ms.openlocfilehash: 91e836c9bb606d7759206788d1e3abd63b293fa8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175317"
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
