---
title: İzleme başvurusu işleci (C + +/ CLI ve C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- '%'
dev_langs:
- C++
helpviewer_keywords:
- tracking references
- '% tracking reference [C++]'
ms.assetid: 142a7269-ab69-4b54-a6d7-833bef06228f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9f2277e09bc4835cabd73d9be5177042dd0817e5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056106"
---
# <a name="tracking-reference-operator-ccli-and-ccx"></a>İzleme başvurusu işleci (C + +/ CLI ve C + +/ CX)

A *yönelik izleme başvurusuna* (`%`) sıradan bir C++ başvurusu gibi davranır (`&`) dışında bir nesne bir izleme başvurusuna atandığında, nesnenin başvuru sayısının artırılır.

## <a name="all-platforms"></a>Tüm Platformlar

İzleme başvurusu aşağıdaki özelliklere sahiptir.

- Bir nesne bir izleme başvurusuna atanması, nesnenin başvuru sayısının artırılması neden olur.

- Yerel başvuru (`&`) başvurusunun sonucu olan bir `*`. İzleme başvurusu (`%`) başvurusunun sonucu olan bir `^`. Sahip olduğunuz sürece bir `%` nesneye, nesne bellekte geçerli kalır.

- Nokta (`.`) üye erişim işleci, nesnenin bir üyesine erişmek için kullanılır.

- İzleme başvuruları değer türleri ve tanıtıcılar için geçerlidir (örneğin `String^`).

- Bir izleme başvurusuna null atanamaz veya **nullptr** değeri. İzleme başvurusu, başka bir geçerli nesneye gerektiği gibi birçok kez atanabilir.

- İzleme başvurusu, tekli adres alma işleci kullanılamaz.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

İzleme başvurusu, başvuru sayılan bir % olması dışında standart bir C++ başvurusu gibi davranır. Aşağıdaki kod parçacığı % arasında nasıl dönüştürme yapılacağını gösterir ve ^ türleri:

```cpp
Foo^ spFoo = ref new Foo();
Foo% srFoo = *spFoo;
Foo^ spFoo2 = %srFoo;
```

Aşağıdaki örnek nasıl geçirileceğini gösterir. bir ^ % alan bir işlev.

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

C + +/ CLI, kullanabileceğiniz bir tanıtıcı izleme başvurusu atık olarak toplanmış yığındaki CLR türü bir nesneye bağlanırken.

CLR değeri içinde çöp toplayıcı başvurulan nesneyi her taşıdığında izleme başvurusu değişken otomatik olarak güncelleştirilir.

İzleme başvurusu yalnızca yığında bildirilebilir. İzleme başvurusu, bir sınıfın üyesi olamaz.

Yerel bir C++ başvurusu bir nesnenin toplanan çöp yığınındaki mümkün değildir.

C + başvuruları izleme hakkında daha fazla bilgi için +/ CLI, bkz:

- [Nasıl yapılır: C++/CLI Üzerinde İzleme Başvurularını Kullanma](../dotnet/how-to-use-tracking-references-in-cpp-cli.md)

### <a name="examples"></a>Örnekler

Aşağıdaki örnek C + +/ CLI bir izleme başvurusu yerel ve yönetilen türlerle kullanma işlemini gösterir.

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

Aşağıdaki örnek C + +/ CLI nasıl bir izleme başvurusunun bir diziye bağlanacağını gösterir.

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