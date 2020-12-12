---
description: 'Daha fazla bilgi edinin: Izleme başvurusu Işleci (C++/CLı ve C++/CX)'
title: İzleme Başvurusu İşleci (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- '%'
helpviewer_keywords:
- tracking references
- '% tracking reference [C++]'
ms.assetid: 142a7269-ab69-4b54-a6d7-833bef06228f
ms.openlocfilehash: 05f61ad3e84bdef322062c93b35285ad37ba222f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172966"
---
# <a name="tracking-reference-operator-ccli-and-ccx"></a>İzleme Başvurusu İşleci (C++/CLI ve C++/CX)

*İzleme başvurusu* ( `%` ), bir `&` nesne izleme başvurusuna atandığında nesnenin başvuru sayısının artması dışında sıradan bir C++ başvurusu () gibi davranır.

## <a name="all-platforms"></a>Tüm Platformlar

İzleme başvurusu aşağıdaki özelliklere sahiptir.

- Bir nesnenin bir izleme başvurusuna atanması, nesnenin başvuru sayısının arttırmasına neden olur.

- Bir yerel başvuru ( `&` ), başvuru yaptığınız zaman sonucudur `*` . Bir izleme başvurusu ( `%` ), başvuru yaptığınız zaman sonucudur `^` . Bir nesneye sahip olduğunuz sürece `%` nesne bellekte etkin kalır.

- Nokta ( `.` ) üye erişim işleci, nesnenin bir üyesine erişmek için kullanılır.

- İzleme başvuruları değer türleri ve işleyiciler için geçerlidir (örneğin `String^` ).

- İzleme başvurusuna null veya **`nullptr`** değer atanamaz. İzleme başvurusu, gerektiği kadar geçerli olan başka bir nesneye yeniden atanabilir.

- İzleme başvurusu birli adres alma işleci olarak kullanılamaz.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Bir izleme başvurusu, standart C++ başvurusu gibi davranır, ancak% bir başvuru sayılır. Aşağıdaki kod parçacığında,% ve ^ türleri arasında nasıl dönüştürme yapılacağı gösterilmektedir:

```cpp
Foo^ spFoo = ref new Foo();
Foo% srFoo = *spFoo;
Foo^ spFoo2 = %srFoo;
```

Aşağıdaki örnek, bir ^ ' i alan bir işleve nasıl geçirileceğini gösterir.

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

C++/CLı ' da, atık toplanmış yığında bir CLR türünün nesnesine bağladığınızda bir tanıtıcıya yönelik izleme başvurusunu kullanabilirsiniz.

CLR 'de, çöp toplayıcı başvurulan nesneyi her taşıdıkça izleme başvuru değişkeninin değeri otomatik olarak güncelleştirilir.

İzleme başvurusu yalnızca yığında bildirilebilecek. İzleme başvurusu bir sınıfın üyesi olamaz.

Atık olarak toplanmış yığında bir nesneye yerel C++ başvurusu yapmak mümkün değildir.

C++/CLı ' daki başvuruları izleme hakkında daha fazla bilgi için bkz.:

- [Nasıl yapılır: C++/CLı ' da Izleme başvurularını kullanma](../dotnet/how-to-use-tracking-references-in-cpp-cli.md)

### <a name="examples"></a>Örnekler

Aşağıdaki C++/CLı örneği, yerel ve yönetilen türlerle izleme başvurusunun nasıl kullanılacağını gösterir.

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

Aşağıdaki C++/CLı örneği bir diziye bir izleme başvurusunun nasıl bağlanacağını gösterir.

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
