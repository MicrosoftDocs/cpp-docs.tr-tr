---
title: Derleyici Uyarısı (Düzey 3) C4398
ms.date: 11/04/2016
f1_keywords:
- C4398
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
ms.openlocfilehash: 4126a1267b41cdf9c0161c7e85a9057b2a301d77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401975"
---
# <a name="compiler-warning-level-3-c4398"></a>Derleyici Uyarısı (Düzey 3) C4398

> '*değişkeni*': başına-process genel nesnesi birden fazla AppDomain ile doğru çalışmayabilir; __declspec(appdomain) kullanmayı düşünün

## <a name="remarks"></a>Açıklamalar

Bir sanal işlev ile [__clrcall](../../cpp/clrcall.md) neden oluşturulmasını çağırma kuralı yerel bir tür bir uygulama etki alanı vtable başına. Böyle bir değişkene doğru birden çok uygulama etki alanlarında kullanıldığında düzeltmemeyi.

Açıkça değişken işaretleyerek bu uyarıyı çözümleyebilirsiniz `__declspec(appdomain)`. Visual Studio 2017 önce Visual Studio sürümlerinde, bu uyarı ile derleme tarafından çözebilirsiniz **/CLR: pure**, varsayılan uygulama etki alanı başına genel değişkenler yapar. **/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Daha fazla bilgi için [appdomain](../../cpp/appdomain.md) ve [uygulama etki alanları ve Visual C++](../../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4398 oluşturur.

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```