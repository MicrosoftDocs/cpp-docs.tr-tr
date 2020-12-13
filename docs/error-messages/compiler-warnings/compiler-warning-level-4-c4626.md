---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4626'
title: Derleyici Uyarısı (düzey 4) C4626
ms.date: 11/04/2016
f1_keywords:
- C4626
helpviewer_keywords:
- C4626
ms.assetid: 7f822ff4-a4a3-4f17-b45b-e8b7b4659a14
ms.openlocfilehash: d528cab5a62abb7e91d4b7bb1487368bd44c6b41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134218"
---
# <a name="compiler-warning-level-4-c4626"></a>Derleyici Uyarısı (düzey 4) C4626

' derived class ': bir taban sınıf atama işlecine erişilemediğinden veya silindiğinden atama işleci örtük olarak silindi olarak tanımlandı

Bir atama işleci bir temel sınıfta silindi veya erişilebilir değil ve bu nedenle türetilmiş bir sınıf için üretilmedi. Bu türden nesneleri atama girişimi, bir derleyici hatasına neden olur.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4626 oluşturur ve nasıl düzeltileceğini gösterir:

```
// C4626
// compile with: /W4
#pragma warning(default : 4626)
class B
{
// public:
   B& operator = (const B&)
   {
      return *this;
   }
};

class D : public B
{

}; // C4626 - to fix, make B's copy constructor public

int main()
{
   D m;
   D n;
   // m = n;   // this line will cause an error
}
```
