---
title: Derleyici Hatası C2280 | Microsoft Docs
ms.custom: ''
ms.date: 04/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2280
helpviewer_keywords:
- C2280
dev_langs:
- C++
ms.assetid: e6c5b1fb-2b9b-4554-8ff9-775eeb37161b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e71d801f2abaaf83ae1064551b40a5a5a6ba8964
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820613"
---
# <a name="compiler-error-c2280"></a>Derleyici Hatası C2280

'*bildirimi*': silinmiş bir işleve başvurmaya çalışıyor

Derleyicinin başvuru girişimi algıladı bir `deleted` işlevi. Bu hata, açıkça olarak işaretlenen bir üye işlevine bir çağrı tarafından kaynaklanabilir `= deleted` kaynak kodunda. Bu hata, yapı ya da otomatik olarak bildirildi ve olarak işaretlenmiş bir sınıf, bir örtük özel üye işlevine bir çağrı tarafından da kaynaklanabilir `deleted` derleyici tarafından. Ne zaman derleyici otomatik olarak oluşturduğu hakkında daha fazla bilgi için `default` veya `deleted` özel üye işlevleri [özel üye işlevleri](../../cpp/special-member-functions.md).

## <a name="example-explicitly-deleted-functions"></a>Örnek: Açıkça işlevleri silindi

Bir çağrı bir açıkça `deleted` işlevi bu hataya neden olur. Bir açıkça `deleted` üye işlevi gelir sınıfın veya yapının kasıtlı olarak bu nedenle bu sorunu gidermek için kullanımını önlemek üzere tasarlanmış, bunu önlemek için kodunuzu değiştirmeniz gerekir.

```cpp
// C2280_explicit.cpp
// compile with: cl /c /W4 C2280_explicit.cpp
struct A {
    A();
    A(int) = delete;
};

struct B {
    A a1;
    A a2 = A(3); // C2280, calls deleted A::A(int)
    // To fix, remove the call to A(int)
};

void f() {
    B b;    // calls implicit B::B(void)
}
```

## <a name="example-uninitialized-data-members"></a>Örnek: Başlatılmamış veri üyesi

Bir başlatılmamış bir başvuru türü veri üyesi veya `const` veri üyesi örtük olarak bildirmek derleyicinin neden olan bir `deleted` varsayılan oluşturucu. Bu sorunu düzeltmek için bildirildiğinde veri üyesi başlatılamıyor.

```cpp
// C2280_uninit.cpp
// compile with: cl /c C2280_uninit.cpp
struct A {
    const int i; // uninitialized const-qualified data
    // members or reference type data members cause
    // the implicit default constructor to be deleted.
    // To fix, initialize the value in the declaration:
    // const int i = 42;
} a;    // C2280
```

## <a name="example-reference-and-const-data-members"></a>Örnek: Başvuru ve const veri üyeleri

A `const` veya başvuru türü veri üyesi neden bildirmek derleyicinin bir `deleted` kopya atama işleci. Basit kopyalama veya taşıma çalışamaz. Bu nedenle başlatıldıktan sonra bu üyeler, atanamaz. Bu sorunu gidermek için hataya neden atama işlemleri kaldırmak için mantığınızı değiştirmeniz önerilir.

```cpp
// C2280_ref.cpp
// compile with: cl /c C2280_ref.cpp
extern int k;
struct A {
    A();
    int& ri = k; // a const or reference data member causes
    // implicit copy assignment operator to be deleted.
};

void f() {
    A a1, a2;
    // To fix, consider removing this assignment.
    a2 = a1;    // C2280
}
```

## <a name="example-movable-deletes-implicit-copy"></a>Örnek: Taşınabilir örtülü kopya siler.

Bir sınıf, bir taşıma Oluşturucusu veya taşıma atama işleci bildirir ancak açıkça bir kopya Oluşturucu bildirmiyor derleyici örtük olarak bir kopya Oluşturucusu bildirir ve olarak tanımladığı `deleted`. Benzer şekilde, bir sınıf için bir taşıma Oluşturucusu veya taşıma atama işleci bildirir, ancak bu kopya atama işleci açıkça bildirmiyor derleyici örtük olarak bir kopya atama işleci bildirir ve tanımlar olarak `deleted`. Bu sorunu gidermek için bu üyeleri açıkça bildirmeniz gerekir.

İle hatası C2280 gördüğünüzde bir `unique_ptr`, olasılıkla olan olduğundan, kopya oluşturucuyu çağırmak denediğinizden bir `deleted` işlevi. Tasarıma göre bir `unique_ptr` kopyalanamıyor. Bir taşıma Oluşturucu, bunun yerine sahipliğini devretmek için kullanın.

```cpp
// C2280_move.cpp
// compile with: cl /c C2280_move.cpp
class base
{
public:
    base();
    ~base();
    base(base&&);
    // Move constructor causes copy constructor to be
    // implicitly declared as deleted. To fix this
    // issue, you can explicitly declare a copy constructor:
    // base(base&);
    // If you want the compiler default version, do this:
    // base(base&) = default;
};

void copy(base *p)
{
    base b{*p};  // C2280
}
```

## <a name="example-variant-and-volatile-members"></a>Örnek: Değişken ve volatile üyeleri

DSCP ve oluşturulan varsayılan oluşturucular ve Yıkıcılar anonim birleşimler için önce Visual Studio 2015 güncelleştirme 2 derleyici sürümleri yoktu. Bunlar artık örtük olarak bildirilen `deleted`. Bu sürümleri de izin DSCP örtük tanımını `default` kopyalama ve taşıma oluşturucuları ve `default` kopyalama ve taşıma atama işleçleri sınıfları ve yapıları sahip `volatile` üye değişkenleri. Derleyici artık bu Önemsiz olmayan oluşturuculara ve atama işleçleri için göz önünde bulundurur ve oluşturmadığını `default` uygulamaları. Bu tür bir sınıfının bir birleşim veya bir sınıf içinde anonim birleşim üyesi olduğunda, kopyalama ve taşıma oluşturucuları ve kopyalama ve taşıma atama işleçleri birleşim veya sınıf örtük olarak tanımlanır `deleted`. Bu sorunu gidermek için açıkça gerekli özel üye işlevleri bildirmeniz gerekir.

```cpp
// C2280_variant.cpp
// compile with: cl /c C2280_variant.cpp
struct A {
    A() = default;
    A(const A&);
};

struct B {
    union {
        A a;
        int i;
    };
    // To fix this issue, declare the required
    // special member functions:
    // B();
    // B(const B& b);
};

int main() {
    B b1;
    B b2(b1);  // C2280
}
```

## <a name="example-indirect-base-members-deleted"></a>Örnek: silinen dolaylı temel üyeleri

Visual Studio 2015 güncelleştirme 2 önce derleyici sürümleri DSCP ve türetilmiş bir sınıf özel üye işlevlerini dolaylı olarak türetilmiş çağırmak izin verilen `private virtual` temel sınıflar. Böyle bir çağrı yapıldığında derleyici artık derleyici hatası C2280 verir.

Bu örnekte, sınıf `top` özel sanal dolaylı olarak türeyen `base`. Uyumlu kod içinde bu üyeleri yapar `base` erişilemez `top`; türündeki nesne bir `top` varsayılan oluşturulmuş veya yok edilemez. Eski derleyici çalışma biçimine dayalı kod bu sorunu çözmek için kullanılacak Ara sınıfı değiştirme `protected virtual` türetme ya da değişiklik `top` doğrudan türetme kullanılacak sınıfı:

```cpp
// C2280_indirect.cpp
// compile with: cl /c C2280_indirect.cpp
class base
{
protected:
    base();
    ~base();
};

class middle : private virtual base {};
// Possible fix: Replace line above with:
// class middle : protected virtual base {};
class top : public virtual middle {};    // C4594, C4624
// Another possible fix: use direct derivation:
// class top : public virtual middle, private virtual base {};

void destroy(top *p)
{
    delete p;  // C2280
}
```
