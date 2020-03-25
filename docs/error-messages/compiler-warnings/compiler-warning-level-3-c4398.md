---
title: Derleyici Uyarısı (düzey 3) C4398
ms.date: 11/04/2016
f1_keywords:
- C4398
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
ms.openlocfilehash: 041bf9f6bfce17b16f301604bb8706be30095c13
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198672"
---
# <a name="compiler-warning-level-3-c4398"></a>Derleyici Uyarısı (düzey 3) C4398

> '*değişken*': işlem başına genel nesne birden çok AppDomain ile doğru çalışmayabilir; __declspec (AppDomain) kullanmayı düşünün

## <a name="remarks"></a>Açıklamalar

Yerel bir türde [__clrcall](../../cpp/clrcall.md) çağırma kuralına sahip sanal bir işlev, uygulama etki alanı vtable başına oluşturulmasına neden olur. Bu tür bir değişken, birden çok uygulama etki alanında kullanıldığında doğru şekilde doğru çalışmayabilir.

`__declspec(appdomain)`değişkeni açıkça işaretleyerek bu uyarıyı çözebilirsiniz. Visual Studio 2017 ' den önceki Visual Studio sürümlerinde, varsayılan olarak AppDomain başına genel değişkenleri oluşturan **/clr: Pure**ile derleme yaparak bu uyarıyı çözebilirsiniz. **/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Daha fazla bilgi için bkz. [AppDomain](../../cpp/appdomain.md) ve [uygulama etki alanları C++ve görsel ](../../dotnet/application-domains-and-visual-cpp.md).

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
