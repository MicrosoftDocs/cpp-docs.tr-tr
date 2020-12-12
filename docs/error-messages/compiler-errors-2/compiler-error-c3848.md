---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3848'
title: Derleyici hatası C3848
ms.date: 11/04/2016
f1_keywords:
- C3848
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
ms.openlocfilehash: 8bd81f59927dd1b34c23148dd1e9bd69ec715609
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255385"
---
# <a name="compiler-error-c3848"></a>Derleyici hatası C3848

' Type ' türüne sahip olan ifade ' function ' çağırmak için bazı const-volatile niteleyicileri kaybeder

Belirtilen const-volatile türüne sahip bir değişken, yalnızca aynı veya daha fazla const-volatile niteliğine sahip üye işlevlerini çağırabilir.

Aşağıdaki örnekler C3848 oluşturur:

```cpp
// C3848.cpp
void glbFunc1()
{
}

typedef void (* pFunc1)();

struct S3
{
   operator pFunc1() // const
   {
      return &glbFunc1;
   }
};

int main()
{
   const S3 s3;
   s3();   // C3848, uncomment const qualifier
}
```
