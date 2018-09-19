---
title: Derleyici Uyarısı (düzey 1) C4350 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4350
dev_langs:
- C++
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ad49a7471be257fa0c22f66fa1bb2bbea049194
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096697"
---
# <a name="compiler-warning-level-1-c4350"></a>Derleyici Uyarısı (düzey 1) C4350

behavior change: 'member2' yerine 'member1' çağrıldı

Bir rvalue başvurusu const olmayan bağlanamaz. Visual Studio 2003 önce Visual C++ sürümlerinde, bir rvalue doğrudan başlatmadaki sabit olmayan başvuru bağlamak mümkündü. Bu kod artık bir uyarı verir.

Geriye dönük uyumluluk için sabit olmayan başvurular rvalues bağlamak yine de mümkündür, ancak standart dönüştürmeler mümkünse tercih edilir.

Bu uyarı, Visual C++ .NET 2002 derleyicisinden davranış değişikliği temsil eder. Etkinleştirilirse, bu uyarı için doğru kodu büyük olasılıkla verilebilir. Örneğin, bu kullanırken verilebilir **std::auto_ptr** sınıf şablonu.

Bu uyarı alırsanız, sabit olmayan başvurular bağlama rvalues bağımlı olmadığını görmek için kodunuzu inceleyin. Bir const başvuru eklemeyi veya ek bir const başvuru aşırı yükleme sağlayarak bu sorunu çözebilir.

Varsayılan olarak bu uyarıyı kapalıdır. Daha fazla bilgi için [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Aşağıdaki örnek, C4350 oluşturur:

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