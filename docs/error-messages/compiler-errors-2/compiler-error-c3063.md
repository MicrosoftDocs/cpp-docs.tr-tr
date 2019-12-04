---
title: Derleyici hatası C3063
ms.date: 11/04/2016
f1_keywords:
- C3063
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
ms.openlocfilehash: c52a0a4c4255eeed5f49a7e6c1e86a1f64b8ad77
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755661"
---
# <a name="compiler-error-c3063"></a>Derleyici hatası C3063

işleç ' operator ': tüm işlenenler aynı numaralandırma türüne sahip olmalıdır

Numaralandırıcılar üzerinde işleçler kullanırken her iki işlenen de sabit listesi türünde olmalıdır. Daha fazla bilgi için bkz. [nasıl yapılır:/CLI içinde C++numaralandırmalar tanımlama ve kullanma](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3063 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3063.cpp
// compile with: /clr
enum class E { a, b } e, mask;
int main() {
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)

   if ( ( e & mask ) != E() )   // OK
      ;
}
```
