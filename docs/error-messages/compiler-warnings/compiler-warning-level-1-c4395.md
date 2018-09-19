---
title: Derleyici Uyarısı (düzey 1) C4395 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4395
dev_langs:
- C++
helpviewer_keywords:
- C4395
ms.assetid: 8051469a-3a39-4677-80f7-1300fbffe8ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d80f4bd5e01fdcc055452a66226f6f27ae920e90
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080148"
---
# <a name="compiler-warning-level-1-c4395"></a>Derleyici Uyarısı (düzey 1) C4395

'function': üye işlev 'member' initonly veri üyesinin bir kopyası üzerinde çağrılacak

Bir üye işlev çağrıldı bir [initonly (C + +/ CLI)](../../dotnet/initonly-cpp-cli.md) veri üyesi.  C4395 uyarır **initonly** veri üyesi işlev tarafından değiştirilemez.

Aşağıdaki örnek, C4395 oluşturur:

```
// C4395.cpp
// compile with: /W1 /clr
public value class V {
public:
   V(int data) : m_data(data) {}

   void Mutate() {
      System::Console::WriteLine("Enter Mutate: m_data = {0}", m_data);
      m_data *= 2;
      System::Console::WriteLine("Leave Mutate: m_data = {0}", m_data);
   }

   int m_data;
};

public ref class R {
public:
   static void f() {
      System::Console::WriteLine("v.m_data = {0}", v.m_data);
      v.Mutate();   // C4395
      System::Console::WriteLine("v.m_data = {0}", v.m_data);
   }

private:
   initonly static V v = V(4);
};

int main() {
   R::f();
}
```