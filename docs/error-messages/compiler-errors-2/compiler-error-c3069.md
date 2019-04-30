---
title: Derleyici Hatası C3069
ms.date: 11/04/2016
f1_keywords:
- C3069
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
ms.openlocfilehash: 6c6451d31da2bb708d3f233225be713981b062e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406762"
---
# <a name="compiler-error-c3069"></a>Derleyici Hatası C3069

'operator': numaralandırma türü için izin verilmiyor

Bir işleç CLR sabit listeleri için desteklenmiyor.  Daha fazla bilgi için [nasıl yapılır: İçinde numaralandırmaları tanımlama ve kullanma C++/CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3069 oluşturur:

```
// C3069.cpp
// compile with: /clr
enum struct E { e1 };
enum F { f1 };

int main() {
   E e = E::e1;
   bool tf;
   tf = !e;   // C3069

   // supported for native enums
   F f = f1;
   tf = !f;
}
```