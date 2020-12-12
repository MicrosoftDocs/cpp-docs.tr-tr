---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3799'
title: Derleyici hatası C3799
ms.date: 11/04/2016
f1_keywords:
- C3799
helpviewer_keywords:
- C3799
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
ms.openlocfilehash: 31ada62b9bc347ce4d4889eca72d8d8e9c2987e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291629"
---
# <a name="compiler-error-c3799"></a>Derleyici hatası C3799

dizinli özelliğin boş bir parametre listesi olamaz

Dizinli bir özellik yanlış bildirildi. Daha fazla bilgi için bkz. [nasıl yapılır: C++/CLI üzerinde özellikleri kullanma](../../dotnet/how-to-use-properties-in-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3799 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C3799.cpp
// compile with: /clr /c
ref struct C {
   property int default[] {   // C3799
   // try the following line instead
   // property int default[int] {
      int get(int index) { return 0; }
      void set(int index, int value) {}
   }
};
```
