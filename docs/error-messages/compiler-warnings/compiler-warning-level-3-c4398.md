---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4398'
title: Derleyici Uyarısı (düzey 3) C4398
ms.date: 11/04/2016
f1_keywords:
- C4398
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
ms.openlocfilehash: ea88f81e44fe0520cd096e1904c49a306863496a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160434"
---
# <a name="compiler-warning-level-3-c4398"></a>Derleyici Uyarısı (düzey 3) C4398

> '*değişken*': işlem başına genel nesne birden çok AppDomain ile doğru çalışmayabilir; __declspec (AppDomain) kullanmayı düşünün

## <a name="remarks"></a>Açıklamalar

Yerel bir türde [__clrcall](../../cpp/clrcall.md) çağırma kuralına sahip sanal bir işlev, uygulama etki alanı vtable başına oluşturulmasına neden olur. Bu tür bir değişken, birden çok uygulama etki alanında kullanıldığında doğru şekilde doğru çalışmayabilir.

Değişkeni açıkça işaretleyerek bu uyarıyı çözebilirsiniz `__declspec(appdomain)` . Visual Studio 2017 ' den önceki Visual Studio sürümlerinde, varsayılan olarak AppDomain başına genel değişkenleri oluşturan **/clr: Pure** ile derleme yaparak bu uyarıyı çözebilirsiniz. **/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Daha fazla bilgi için bkz. [AppDomain](../../cpp/appdomain.md) ve [uygulama etki alanları ve Visual C++](../../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4398 oluşturur.

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```
