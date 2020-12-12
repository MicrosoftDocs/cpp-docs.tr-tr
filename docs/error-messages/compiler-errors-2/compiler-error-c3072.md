---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3072'
title: Derleyici hatası C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: 02876a6983a47ce76f6e089bafde68af41034131
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320285"
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
