---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2930'
title: Derleyici hatası C2930
ms.date: 11/04/2016
f1_keywords:
- C2930
helpviewer_keywords:
- C2930
ms.assetid: f07eecd1-e5d1-4518-bd89-b1fd2a003a17
ms.openlocfilehash: 880c6610ca175e9fee1722f4481fea35239bd452
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320352"
---
# <a name="compiler-error-c2930"></a>Derleyici hatası C2930

' class ': tür sınıfı kimliği ' enum Identifier ' numaralandırıcısı olarak yeniden tanımlandı

Bir numaralandırma üyesi olarak genel veya şablon sınıfı kullanamazsınız.

Bu hata, küme ayraçları yanlış bir şekilde eşleştirildiği için oluşur.

Aşağıdaki örnek C2930 oluşturur:

```cpp
// C2930.cpp
// compile with: /c
template<class T>
class x{};
enum SomeEnum { x };   // C2930

class y{};
enum SomeEnum { y };
```

C2930, genel türler kullanılırken de oluşabilir:

```cpp
// C2930c.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
enum SomeEnum { GC };   // C2930

ref struct GC2 {};
enum SomeEnum2 { GC2 };
```
