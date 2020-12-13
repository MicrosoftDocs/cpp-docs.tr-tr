---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3914'
title: Derleyici hatası C3914
ms.date: 11/04/2016
f1_keywords:
- C3914
helpviewer_keywords:
- C3914
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
ms.openlocfilehash: 7f5291e09d7f3f794d7d1bec90f0a753d7dfe38f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143968"
---
# <a name="compiler-error-c3914"></a>Derleyici hatası C3914

Varsayılan bir özellik statik olamaz

Varsayılan bir özellik yanlış bildirildi.  Daha fazla bilgi için bkz. [nasıl yapılır: C++/CLI üzerinde özellikleri kullanma](../../dotnet/how-to-use-properties-in-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3914 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C3914.cpp
// compile with: /clr /c
ref struct X {
   static property int default[int] {   // C3914
   // try the following line instead
   // property int default[int] {
      int get(int) { return 0; }
      void set(int, int) {}
   }
};
```
