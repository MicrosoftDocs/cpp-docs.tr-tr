---
title: Derleyici hatası C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: bcf2548fbe1182f7f6c4bd966ca6aa9ef9f10089
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212611"
---
# <a name="compiler-error-c3072"></a>Derleyici hatası C3072

> '*operator-Name*' işleci bir başvuru sınıfının örneğine uygulanamaz

bir başvuru sınıfının bir örneğini tanıtıcı türüne dönüştürmek için birli *işleç-adı* işlecini kullanın

CLR türü yerel (veya standart) işleçler değil CLR işleçleri gerektirir.  Daha fazla bilgi için bkz. [Izleme başvurusu işleci](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3072 oluşturur.

```cpp
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```
