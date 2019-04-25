---
title: Derleyici Uyarısı (düzey 4) C4623
ms.date: 11/04/2016
f1_keywords:
- C4623
helpviewer_keywords:
- C4623
ms.assetid: e630d8d0-f6ea-469c-a74f-07b027587225
ms.openlocfilehash: d1b659a6aed593a2e3f01ac1b82e60878cb09c80
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220474"
---
# <a name="compiler-warning-level-4-c4623"></a>Derleyici Uyarısı (düzey 4) C4623

'`derived class`': varsayılan oluşturucu örtük bir şekilde bir taban sınıf varsayılan oluşturucusuna erişilemez veya silinmiş olduğundan silindi olarak tanımlandı

Bir oluşturucu, bir temel sınıfta erişilebilir durumda değildi ve türetilen sınıf için oluşturulmadı. Yığında bu türde bir nesne oluşturmak için her türlü girişim, bir derleyici hatasına neden olur.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4623 oluşturur.

```
// C4623.cpp
// compile with: /W4
#pragma warning(default : 4623)
class B {
   B();
};

class C {
public:
   C();
};

class D : public B {};   // C4623 - to fix, make B's constructor public
class E : public C {};   // OK - class C constructor is public

int main() {
   // D d;  will cause an error
}
```