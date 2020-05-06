---
title: for each, in
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::foreach
- for
- each
- in
helpviewer_keywords:
- for each keyword [C++]
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
ms.openlocfilehash: f1f5523eb22bd8a839da9b3f73dd6c3718b4fd63
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825802"
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
Türü `identifier`.

*Tanımlayıcısını*<br/>
Koleksiyon öğesini temsil eden yineleme değişkeni.  Bir `identifier` [izleme başvuru operatörü](../extensions/tracking-reference-operator-cpp-component-extensions.md)olduğunda, öğesini değiştirebilirsiniz.

*ifadesini*<br/>
Bir dizi ifadesi veya koleksiyon. Koleksiyon öğesi, derleyicinin `identifier` türü türüne dönüştürebilmek için olmalıdır.

*deyimler*<br/>
Yürütülecek bir veya daha fazla deyim.

### <a name="remarks"></a>Açıklamalar

İfade `for each` , bir koleksiyon üzerinde yinelemek için kullanılır. Bir koleksiyondaki öğeleri değiştirebilirsiniz, ancak öğe ekleyemez veya silemezsiniz.

*Deyimler* dizideki veya koleksiyondaki her öğe için yürütülür. Koleksiyondaki tüm öğeler için yineleme tamamlandıktan sonra Denetim, `for each` bloğu izleyen deyime aktarılır.

`for each`ve `in` [bağlama duyarlı anahtar sözcüklerdir](../extensions/context-sensitive-keywords-cpp-component-extensions.md).

Daha fazla bilgi için:

- [foreach Kullanarak Bir C++ Standart Kitaplığı Koleksiyonu Üzerinden Yineleme Yapma](../dotnet/iterating-over-stl-collection-by-using-for-each.md)

- [Nasıl yapılır: foreach ile Diziler Üzerinden Yineleme Yapma](../dotnet/how-to-iterate-over-arrays-with-for-each.md)

- [Nasıl yapılır: foreach ile Bir Genel Koleksiyon Üzerinden Yineleme Yapma](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)

- [Nasıl yapılır: foreach ile Kullanıcı Tanımlı Bir Koleksiyon Üzerinden Yineleme Yapma](../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

### <a name="example"></a>Örnek

Bu örnek, bir dize içinde `for each` yinelemek için nasıl kullanılacağını gösterir.

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

**Çıktı**

```Output
abcd

Testing
```

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

**Açıklamalar**

CLR sözdizimi, aşağıdakiler hariç, tüm çalışma **zamanları** sözdizimi ile aynıdır.

*ifadesini*<br/>
Yönetilen dizi ifadesi veya koleksiyon. Koleksiyon öğesi, derleyicinin onu <xref:System.Object> *tanımlayıcı* türüne dönüştürebilmek için olmalıdır.

*ifade* <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>veya ' i uygulayan bir tür ya da ' de `GetEnumerator` <xref:System.Collections.IEnumerator> `IEnumerator`tanımlanan tüm metotları uygulayan veya bildiren bir tür döndüren bir yöntemi tanımlayan bir tür olarak değerlendirilir.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/clr**

### <a name="example"></a>Örnek

Bu örnek, bir dize içinde `for each` yinelemek için nasıl kullanılacağını gösterir.

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

**Çıktı**

```Output
abcd

Testing
```

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../extensions/component-extensions-for-runtime-platforms.md)
