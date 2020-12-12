---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3063'
title: Derleyici hatası C3063
ms.date: 11/04/2016
f1_keywords:
- C3063
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
ms.openlocfilehash: 304359e34b6cbae07d2f901db02c6e5ed04e373c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281710"
---
# <a name="compiler-error-c3063"></a>Derleyici hatası C3063

işleç ' operator ': tüm işlenenler aynı numaralandırma türüne sahip olmalıdır

Numaralandırıcılar üzerinde işleçler kullanırken her iki işlenen de sabit listesi türünde olmalıdır. Daha fazla bilgi için bkz. [nasıl yapılır: C++/CLI üzerinde numaralandırmaları tanımlama ve kullanma](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).

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
