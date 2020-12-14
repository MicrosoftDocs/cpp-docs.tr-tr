---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2280'
title: Derleyici hatası C2280
ms.date: 04/25/2017
f1_keywords:
- C2280
helpviewer_keywords:
- C2280
ms.assetid: e6c5b1fb-2b9b-4554-8ff9-775eeb37161b
ms.openlocfilehash: 74ed554006faa20046571971e080e0c0a2054b72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295061"
---
# <a name="compiler-error-c2280"></a>Derleyici hatası C2280

'*declaration*': silinmiş bir işleve başvurulmaya çalışılıyor

Derleyici bir işleve başvurma girişimi algıladı `deleted` . Bu hata, kaynak kodda açıkça işaretlenmiş bir üye işlevine yapılan çağrıdan kaynaklanabilir `= deleted` . Bu hata ayrıca, otomatik olarak tanımlanan ve derleyici tarafından olarak işaretlenen bir yapının veya sınıfın örtük özel üye işlevine yapılan bir çağrı nedeniyle oluşabilir `deleted` . Derleyicinin otomatik olarak ne zaman oluşturduğu veya özel üye işlevleri hakkında daha fazla bilgi için **`default`** `deleted` bkz. [özel üye işlevleri](../../cpp/special-member-functions.md).

## <a name="example-explicitly-deleted-functions"></a>Örnek: açıkça silinen işlevler

Açıkça `deleted` işlev çağrısı bu hataya neden olur. Açıkça bir `deleted` üye işlevi, sınıfın veya yapının kullanımını önlemek için kasıtlı olarak tasarlandığını gösterir, bu nedenle bu sorunu çözmemek için kodunuzu değiştirmelisiniz.

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

## <a name="example-uninitialized-data-members"></a>Örnek: başlatılmamış veri üyeleri

Başlatılmamış bir başvuru türü veri üyesi veya **`const`** veri üyesi, derleyicinin örtülü olarak varsayılan bir Oluşturucu tanımlamasına neden olur `deleted` . Bu sorunu onarmak için, veri üyesini bildirildiği zaman başlatın.

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

## <a name="example-reference-and-const-data-members"></a>Örnek: başvuru ve const veri üyeleri

Bir **`const`** veya başvuru türü veri üyesi, derleyicinin bir `deleted` kopya atama işleci tanımlamasına neden olur. Başlatıldıktan sonra, bu üyelere öğesine atanamaz, bu nedenle basit bir kopya veya taşıma çalışamıyoruz. Bu sorunu giderecek şekilde, hataya neden olan atama işlemlerini kaldırmak için mantığınızı değiştirmenizi öneririz.

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

## <a name="example-movable-deletes-implicit-copy"></a>Örnek: taşınabilir örtük kopyayı siler

Bir sınıf bir taşıma Oluşturucusu veya taşıma ataması operatörü bildiriyorsa, ancak açıkça bir kopya Oluşturucu bildirmiyorsa, derleyici dolaylı olarak bir kopya Oluşturucu bildirir ve bunu olarak tanımlar `deleted` . Benzer şekilde, bir sınıf bir taşıma Oluşturucusu veya taşıma ataması işlecini bildirirse, ancak açıkça bir kopya atama işleci bildirmiyorsa, derleyici dolaylı olarak bir kopya atama işleci bildirir ve bunu olarak tanımlar `deleted` . Bu sorunu onarmak için, bu üyeleri açıkça bildirmeniz gerekir.

Bir ile bağlantılı olarak hata C2280 gördüğünüzde `unique_ptr` , bu, bir işlev olan kopya oluşturucusunu çağırmaya çalışırken neredeyse kesinlikle olur `deleted` . Tasarıma göre, bir `unique_ptr` kopyalanamıyor. Bunun yerine sahipliği aktarmak için bir taşıma Oluşturucusu kullanın.

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

## <a name="example-variant-and-volatile-members"></a>Örnek: değişken ve geçici Üyeler

Visual Studio 2015 güncelleştirme 2 ' den önceki derleyici sürümleri, anonim birleşimler için uyumsuz ve üretilmiş varsayılan oluşturucular ve Yıkıcılar. Bunlar artık örtük olarak olarak bildirilmiştir `deleted` . Bu sürümler Ayrıca, **`default`** **`default`** üye değişkenleri olan sınıflarda ve yapılarda atama işleçlerini ve kopyalama ve taşıma oluşturucularının uyumsuz bir örtük tanımına izin verebilir **`volatile`** . Derleyici artık bunları önemsiz olmayan oluşturuculara ve atama işleçlerine sahip olacak şekilde değerlendirir ve **`default`** uygulama oluşturmaz. Böyle bir sınıf bir birleşimin üyesi veya bir sınıfın içindeki anonim bir birleşim olduğunda, birleşim veya sınıfın kopyalama ve Taşıma Oluşturucuları ile kopyalama ve taşıma atama işleçleri örtülü olarak tanımlanmıştır `deleted` . Bu sorunu onarmak için gerekli özel üye işlevlerini açıkça bildirmeniz gerekir.

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

## <a name="example-indirect-base-members-deleted"></a>Örnek: dolaylı temel Üyeler silindi

Visual Studio 2015 güncelleştirme 2 ' den önceki derleyici sürümleri uyumlu değildi ve türetilmiş bir sınıfın dolaylı olarak türetilmiş temel sınıfların özel üye işlevlerini çağırabilmesi için izin verildi `private virtual` . Derleyici artık bu tür bir çağrı yapıldığında derleyici hatası C2280 yayınlar.

Bu örnekte, sınıfı `top` dolaylı olarak özel sanal sunucudan türetilir `base` . Bu, uyumlu bir kodda, erişilemeyen üyeleri, `base` Varsayılan olarak `top` `top` oluşturulamaz veya yok edilebilir hale getirir. Eski derleyici davranışına bağlı olan koddaki bu sorunu onarmak için, ara sınıfı türetme kullanacak şekilde değiştirin `protected virtual` veya `top` sınıfı doğrudan türetmeye kullanılacak şekilde değiştirin:

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
