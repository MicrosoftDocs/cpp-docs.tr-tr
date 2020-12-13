---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4350'
title: Derleyici Uyarısı (düzey 1) C4350
ms.date: 11/04/2016
f1_keywords:
- C4350
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
ms.openlocfilehash: 0626c9c8d0196396c0d13a0697df2dfc64061db0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340001"
---
# <a name="compiler-warning-level-1-c4350"></a>Derleyici Uyarısı (düzey 1) C4350

behavior change: 'member2' yerine 'member1' çağrıldı

Rvalue, const olmayan bir başvuruya bağlanamaz. Visual Studio 2003 ' den önceki Visual C++ sürümlerinde, bir rvalue 'yı doğrudan başlatmada const olmayan bir başvuruya bağlamak mümkündür. Bu kod şimdi bir uyarı verir.

Geriye dönük uyumluluk için, rvalues 'u const olmayan başvurulara bağlamak yine de mümkündür, ancak standart dönüştürmeler mümkün olduğunca tercih edilir.

Bu uyarı, Visual C++ .NET 2002 derleyicisinden bir davranış değişikliğini temsil eder. Etkinleştirilirse, bu uyarı doğru kod için verilebilir. Örneğin, **std:: auto_ptr** sınıf şablonu kullanılırken bu verilebilir.

Bu uyarıyı alırsanız, rvalues değerlerini const olmayan başvurulara bağlamaya bağlı olup olmadığını görmek için kodunuzu inceleyin. Başvuruya bir const eklemek veya ek bir const başvurusu aşırı yüklemesi sağlamak sorunu çözebilir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Aşağıdaki örnek C4350 oluşturur:

```cpp
// C4350.cpp
// compile with: /W1
#pragma warning (default : 4350)
class A {};

class B
{
public:
   B(B&){}
   // try the following instead:
   // B(const B&){}

   B(A){}
   operator A(){ return A();}
};

B source() { return A(); }

int main()
{
   B ap(source());   // C4350
}
```
