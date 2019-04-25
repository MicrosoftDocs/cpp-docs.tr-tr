---
title: Genel temsilciler (C++/CLI)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- generic delegates
- delegates, generic [C++]
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
ms.openlocfilehash: 449659126f52997d548ebd7785a78c1200038ee6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62254929"
---
# <a name="generic-delegates-ccli"></a>Genel temsilciler (C++/CLI)

Genel tür parametreleri ile temsilciler kullanabilirsiniz. Temsilciler hakkında daha fazla bilgi için bkz. [temsilci (C++/CLI ve C++/CX)](delegate-cpp-component-extensions.md).

## <a name="syntax"></a>Sözdizimi

```cpp
[attributes]
generic < [class | typename] type-parameter-identifiers>
[type-parameter-constraints-clauses]
[accessibility-modifiers] delegate result-type identifier
([formal-parameters]);
```

### <a name="parameters"></a>Parametreler

*Öznitelikleri*<br/>
(İsteğe bağlı) Ek bildirim temelli bilgiler. Öznitelikleri öznitelikleri ve öznitelik sınıfları hakkında daha fazla bilgi için bkz.

*tür-parametresi-tanımlayıcıları*<br/>
Virgülle ayrılmış tanımlayıcılar tür parametrelerinin listesi.

*tür parametresi kısıtlamaları tümceleri*<br/>
Belirtilen biçimi alır [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](constraints-on-generic-type-parameters-cpp-cli.md)

*erişilebilirlik değiştiricileri*<br/>
(İsteğe bağlı) Erişilebilirlik değiştiricileri (örneğin **genel**, **özel**).

*Sonuç türü*<br/>
Temsilcinin dönüş türü.

*tanımlayıcı*<br/>
Metot temsilcisinin adı.

*Resmi-Parametreler*<br/>
(İsteğe bağlı) Metot temsilcisinin parametre listesi.

## <a name="example"></a>Örnek

Bir temsilci nesnesinin oluşturulduğu noktada temsilci tür parametreleri belirtilmiş. Temsilci ve onunla ilişkili yöntemi aynı imzaya sahip olmalıdır. Genel temsilci bildirimi bir örnek verilmiştir.

```cpp
// generics_generic_delegate1.cpp
// compile with: /clr /c
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, gösterir.

- Aynı temsilci nesne farklı oluşturulan türler ile kullanamazsınız. Nesneler farklı türleri için farklı bir temsilci oluşturun.

- Temsilci ile genel yöntem ilişkilendirilebilir.

- Tür bağımsız değişkenleri belirtmeden bir genel yöntem çağrıldığında, derleyici, tür bağımsız değişkenlerini çağrısı için tanım Çıkarsama dener.

```cpp
// generics_generic_delegate2.cpp
// compile with: /clr
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);

generic <class ItemType>
ref struct MyGenClass {
   ItemType MyMethod(ItemType i, ItemType % j) {
      return ItemType();
   }
};

ref struct MyClass {
   generic <class ItemType>
   static ItemType MyStaticMethod(ItemType i, ItemType % j) {
      return ItemType();
   }
};

int main() {
   MyGenClass<int> ^ myObj1 = gcnew MyGenClass<int>();
   MyGenClass<double> ^ myObj2 = gcnew MyGenClass<double>();
   GenDelegate<int>^ myDelegate1 =
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);

   GenDelegate<double>^ myDelegate2 =
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);

   GenDelegate<int>^ myDelegate =
      gcnew GenDelegate<int>(&MyClass::MyStaticMethod<int>);
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, Genel temsilci bildirir `GenDelegate<ItemType>`ve yönteme ilişkilendirerek başlatır `MyMethod` tür parametresi kullanan `ItemType`. Metot temsilcisinin (bir tamsayı ve bir çift) iki örneği oluşturulur ve çağrılır.

```cpp
// generics_generic_delegate.cpp
// compile with: /clr
using namespace System;

// declare generic delegate
generic <typename ItemType>
delegate ItemType GenDelegate (ItemType p1, ItemType% p2);

// Declare a generic class:
generic <typename ItemType>
ref class MyGenClass {
public:
   ItemType MyMethod(ItemType p1, ItemType% p2) {
      p2 = p1;
      return p1;
    }
};

int main() {
   int i = 0, j = 0;
   double m = 0.0, n = 0.0;

   MyGenClass<int>^ myObj1 = gcnew MyGenClass<int>();
   MyGenClass<double>^ myObj2 = gcnew MyGenClass<double>();

   // Instantiate a delegate using int.
   GenDelegate<int>^ MyDelegate1 =
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);

   // Invoke the integer delegate using MyMethod.
   i = MyDelegate1(123, j);

   Console::WriteLine(
      "Invoking the integer delegate: i = {0}, j = {1}", i, j);

   // Instantiate a delegate using double.
   GenDelegate<double>^ MyDelegate2 =
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);

   // Invoke the integer delegate using MyMethod.
   m = MyDelegate2(0.123, n);

   Console::WriteLine(
      "Invoking the double delegate: m = {0}, n = {1}", m, n);
}
```

```Output
Invoking the integer delegate: i = 123, j = 123
Invoking the double delegate: m = 0.123, n = 0.123
```

## <a name="see-also"></a>Ayrıca bkz.

[Genel Türler](generics-cpp-component-extensions.md)