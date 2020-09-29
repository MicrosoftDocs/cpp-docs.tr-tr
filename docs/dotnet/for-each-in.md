---
title: for each, in
description: For each için C++/CLı, for deyimleri açıklaması ve örnekleri.
ms.date: 09/25/2020
ms.topic: reference
f1_keywords:
- cliext::foreach
- for
- each
- in
helpviewer_keywords:
- for each keyword [C++]
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
ms.openlocfilehash: 7f228a773dfcbe791e26ea3e1bd8cfba7f3ab028
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413925"
---
# <a name="for-each-in"></a>for each, in

Bir dizi ya da koleksiyonda yinelenir. Bu standart olmayan anahtar sözcük, hem C++/CLI hem de yerel C++ projelerinde kullanılabilir. Ancak, kullanımı önerilmez. Bunun yerine standart bir [Aralık tabanlı for deyimleri (C++)](../cpp/range-based-for-statement-cpp.md) kullanmayı düşünün.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="syntax"></a>Sözdizimi

> **for each (** **in** *ifadede* *tür* *tanımlayıcısı* **) {**\
> &nbsp;&nbsp;&nbsp;&nbsp;*deyimler*\
> **}**

### <a name="parameters"></a>Parametreler

*türüyle*<br/>
Türü `identifier` .

*Tanımlayıcısını*<br/>
Koleksiyon öğesini temsil eden yineleme değişkeni.  `identifier`Bir [Izleme başvuru operatörü](../extensions/tracking-reference-operator-cpp-component-extensions.md)olduğunda, öğesini değiştirebilirsiniz.

*ifadesini*<br/>
Bir dizi ifadesi veya koleksiyon. Koleksiyon öğesi, derleyicinin türü türüne dönüştürebilmek için olmalıdır `identifier` .

*deyimler*<br/>
Yürütülecek bir veya daha fazla deyim.

### <a name="remarks"></a>Açıklamalar

`for each`İfade, bir koleksiyon üzerinde yinelemek için kullanılır. Bir koleksiyondaki öğeleri değiştirebilirsiniz, ancak öğe ekleyemez veya silemezsiniz.

*Deyimler* dizideki veya koleksiyondaki her öğe için yürütülür. Koleksiyondaki tüm öğeler için yineleme tamamlandıktan sonra Denetim, bloğu izleyen deyime aktarılır `for each` .

`for each` ve `in` [bağlama duyarlı anahtar sözcüklerdir](../extensions/context-sensitive-keywords-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

### <a name="example"></a>Örnek

Bu örnek, `for each` bir dize içinde yinelemek için nasıl kullanılacağını gösterir.

```cpp
// for_each_string1.cpp
// compile with: /ZW
#include <stdio.h>
using namespace Platform;

ref struct MyClass {
   property String^ MyStringProperty;
};

int main() {
   String^ MyString = ref new String("abcd");

   for each ( char c in MyString )
      wprintf("%c", c);

   wprintf("/n");

   MyClass^ x = ref new MyClass();
   x->MyStringProperty = "Testing";

   for each( char c in x->MyStringProperty )
      wprintf("%c", c);
}
```

```Output
abcd

Testing
```

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

CLR sözdizimi, aşağıdakiler hariç, tüm çalışma **zamanları** sözdizimi ile aynıdır.

*ifadesini*<br/>
Yönetilen dizi ifadesi veya koleksiyon. Koleksiyon öğesi, derleyicinin onu <xref:System.Object> *tanımlayıcı* türüne dönüştürebilmek için olmalıdır.

*ifade* , veya ' i uygulayan bir tür ya da ' <xref:System.Collections.IEnumerable> <xref:System.Collections.Generic.IEnumerable%601> `GetEnumerator` <xref:System.Collections.IEnumerator> de tanımlanan tüm metotları uygulayan veya bildiren bir tür döndüren bir yöntemi tanımlayan bir tür olarak değerlendirilir `IEnumerator` .

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/clr**

### <a name="example"></a>Örnek

Bu örnek, `for each` bir dize içinde yinelemek için nasıl kullanılacağını gösterir.

```cpp
// for_each_string2.cpp
// compile with: /clr
using namespace System;

ref struct MyClass {
   property String ^ MyStringProperty;
};

int main() {
   String ^ MyString = gcnew String("abcd");

   for each ( Char c in MyString )
      Console::Write(c);

   Console::WriteLine();

   MyClass ^ x = gcnew MyClass();
   x->MyStringProperty = "Testing";

   for each( Char c in x->MyStringProperty )
      Console::Write(c);
}
```

```Output
abcd

Testing
```

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma zamanı platformları için bileşen uzantıları](../extensions/component-extensions-for-runtime-platforms.md)\
[Aralık tabanlı for deyimleri (C++)](../cpp/range-based-for-statement-cpp.md)
