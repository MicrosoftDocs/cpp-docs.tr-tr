---
title: İzleme Başvurusu İşleci (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- '%'
helpviewer_keywords:
- tracking references
- '% tracking reference [C++]'
ms.assetid: 142a7269-ab69-4b54-a6d7-833bef06228f
ms.openlocfilehash: ccd31b3e334dc5a4cd2e48b94c9dbe85cf13c16b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368230"
---
# <a name="tracking-reference-operator-ccli-and-ccx"></a>İzleme Başvurusu İşleci (C++/CLI ve C++/CX)

Bir *izleme* `%`başvurusu (`&`) sıradan bir C++ başvurusu gibi, bir nesne bir izleme başvurusuna atandığında, nesnenin başvuru sayısının artması dışında kullanılır.

## <a name="all-platforms"></a>Tüm Platformlar

Bir izleme başvurusu aşağıdaki özelliklere sahiptir.

- Bir nesnenin izleme başvurusuna atanması, nesnenin başvuru sayısının artışalmasına neden olur.

- Yerel bir`&`başvuru ( ) bir `*`. Bir izleme`%`başvurusu ( ) bir `^`. Bir nesneye sahip `%` olduğunuz sürece, nesne hafızada canlı kalacaktır.

- Nokta (`.`) üye erişim işleci nesnenin bir üyesine erişmek için kullanılır.

- İzleme başvuruları değer türleri ve işlonlar `String^`için geçerlidir (örneğin).

- Bir izleme başvurusuna null veya **nullptr** değeri atanamaz. Bir izleme başvurusu, gerektiğinde başka bir geçerli nesneye yeniden atanabilir.

- Bir izleme başvurusu unary take-address işleci olarak kullanılamaz.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

İzleme başvurusu, %'nin referans sayılan olması dışında standart bir C++ başvurusu gibi olur. Aşağıdaki parçacık% ve ^ türleri arasında dönüştürmek için nasıl gösterir:

```cpp
Foo^ spFoo = ref new Foo();
Foo% srFoo = *spFoo;
Foo^ spFoo2 = %srFoo;
```

Aşağıdaki örnek, ^'un %'lik bir işleve nasıl geçirilebildiğini gösterir.

```cpp
ref class Foo sealed {};

    // internal or private
    void UseFooHelper(Foo% f)
    {
        auto x = %f;
    }

    // public method on ABI boundary
    void UseFoo(Foo^ f)
    {
        if (f != nullptr) { UseFooHelper(*f); }
    }
```

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

C++/CLI'de, çöp toplanmış yığında CLR türündeki bir nesneye bağlandığınızda bir tutamaç için izleme başvurusu kullanabilirsiniz.

CLR'de, çöp toplayıcı başvurulan nesneyi her hareket ettirdiğinde izleme başvuru değişkeninin değeri otomatik olarak güncelleştirilir.

Bir izleme başvurusu yalnızca yığında bildirilebilir. İzleme başvurusu sınıfın üyesi olamaz.

Çöp toplanmış yığındaki bir nesneye yerel C++ başvurusu yapmak mümkün değildir.

C++/CLI'deki başvuruları izleme hakkında daha fazla bilgi için bkz:

- [Nasıl yapılır: C++/CLI Üzerinde İzleme Başvurularını Kullanma](../dotnet/how-to-use-tracking-references-in-cpp-cli.md)

### <a name="examples"></a>Örnekler

C++/CLI için aşağıdaki örnek, yerel ve yönetilen türleri ile bir izleme başvurusu nasıl kullanılacağını gösterir.

```cpp
// tracking_reference_1.cpp
// compile with: /clr
ref class MyClass {
public:
   int i;
};

value struct MyStruct {
   int k;
};

int main() {
   MyClass ^ x = ref new MyClass;
   MyClass ^% y = x;   // tracking reference handle to reference object

   int %ti = x->i;   // tracking reference to member of reference type

   int j = 0;
   int %tj = j;   // tracking reference to object on the stack

   int * pi = new int[2];
   int % ti2 = pi[0];   // tracking reference to object on native heap

   int *% tpi = pi;   // tracking reference to native pointer

   MyStruct ^ x2 = ref new MyStruct;
   MyStruct ^% y2 = x2;   // tracking reference to value object

   MyStruct z;
   int %tk = z.k;   // tracking reference to member of value type

   delete[] pi;
}
```

C++/CLI için aşağıdaki örnek, bir diziye izleme başvurusu nasıl bağlanılmayı gösterir.

```cpp
// tracking_reference_2.cpp
// compile with: /clr
using namespace System;

int main() {
   array<int> ^ a = ref new array<Int32>(5);
   a[0] = 21;
   Console::WriteLine(a[0]);
   array<int> ^% arr = a;
   arr[0] = 222;
   Console::WriteLine(a[0]);
}
```

```Output
21
222
```
