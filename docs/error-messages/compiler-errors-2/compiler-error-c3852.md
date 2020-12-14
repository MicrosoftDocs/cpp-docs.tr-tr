---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3852'
title: Derleyici hatası C3852
ms.date: 11/04/2016
f1_keywords:
- C3852
helpviewer_keywords:
- C3852
ms.assetid: 194e5c5e-0dfb-414e-86db-791c11eb610c
ms.openlocfilehash: f5bfeb5507943dc4f860b81912bfb6880621f290
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255242"
---
# <a name="compiler-error-c3852"></a>Derleyici hatası C3852

' Member ' türü ' Type ' türüne sahip: toplu başlatma bu üyeyi başlatamadı

Toplam başlatma işleminde varsayılan bir başlatma alamamak üzere bir veri üyesine toplu başlatmanın parçası olarak varsayılan bir başlatma atamaya çalışıldı.

Aşağıdaki örnekler C3852 oluşturur:

```cpp
// C3852.cpp
struct S
{
   short s;
};

struct S1
{
   int i;
   const S s;
};

struct S2
{
   int i;
   char & rc;
};

int main()
{
   S1 s1 = { 1 };   // C3852 const member
   // try the following line instead
   // S1 s1 = { 1, 2 };

   S2 s2 = { 2 };   // C3852 reference member
   // try the following line instead
   // char c = 'a';
   S2 s2 = { 2, c };
}
```
