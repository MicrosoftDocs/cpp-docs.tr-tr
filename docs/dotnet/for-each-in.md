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
ms.openlocfilehash: c5ee72e557c62e3db2eeb5dac4811133719183f6
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746330"
---
# <a name="for-each-in"></a>for each, in

Bir dizi ya da koleksiyonda yinelenir. Bu standart olmayan anahtar sözcük, hem C++/CLI hem de yerel C++ projelerinde kullanılabilir. Ancak, kullanımı önerilmez. Standart kullanmayı [aralık tabanlı for deyimi (C++)](../cpp/range-based-for-statement-cpp.md) yerine.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="syntax"></a>Sözdizimi

> **Her (** *türü* *tanımlayıcı* **içinde** *ifade* **) {**<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;*Deyimleri*<br/>
> **}**

### <a name="parameters"></a>Parametreler

*type*<br/>
Türünü `identifier`.

*tanımlayıcı*<br/>
Koleksiyon öğesini temsil eden yineleme değişkeni.  Zaman `identifier` olduğu bir [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md), öğeyi değiştirebilirsiniz.

*İfade*<br/>
Bir dizi ifadesi veya koleksiyon. Koleksiyon öğesi, derleyicinin kendisine dönüştürebileceği şekilde olmalıdır `identifier` türü.

*Deyimleri*<br/>
Yürütülecek bir veya daha fazla deyim.

### <a name="remarks"></a>Açıklamalar

`for each` Deyimi bir koleksiyon içinde yineleme için kullanılır. Bir koleksiyondaki öğeleri değiştirebilirsiniz, ancak öğe ekleyemez veya silemezsiniz.

*Deyimleri* dizi veya koleksiyon içindeki her öğe için yürütülür. Koleksiyondaki tüm öğeler için yineleme tamamlandıktan sonra Denetim izleyen deyime aktarılır `for each` blok.

`for each` ve `in` olan [bağlama duyarlı anahtar sözcükler](../windows/context-sensitive-keywords-cpp-component-extensions.md).

Daha fazla bilgi için:

- [foreach Kullanarak Bir C++ Standart Kitaplığı Koleksiyonu Üzerinden Yineleme Yapma](../dotnet/iterating-over-stl-collection-by-using-for-each.md)

- [Nasıl yapılır: İle diziler üzerinden foreach yineleme yapma](../dotnet/how-to-iterate-over-arrays-with-for-each.md)

- [Nasıl yapılır: İle bir genel koleksiyon üzerinden foreach yineleme yapma](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)

- [Nasıl yapılır: İle kullanıcı tanımlı bir koleksiyon üzerinden foreach yineleme yapma](../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

### <a name="example"></a>Örnek

Bu örnek nasıl kullanılacağını gösterir `for each` bir dize içinde yineleme için.

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

**Output**

```Output
abcd

Testing
```

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

**Açıklamalar**

CLR sözdizimi aynıdır **tüm çalışma zamanları** söz dizimiyle aynıdır.

*İfade*<br/>
Yönetilen dizi ifadesi veya koleksiyon. Koleksiyon öğesi, derleyicinin buradan dönüştürebileceği şekilde olmalıdır <xref:System.Object> için *tanımlayıcı* türü.

*ifade* uygulayan bir türe değerlendirir <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, veya tanımlayan bir tür bir `GetEnumerator` ya da döndüren yöntemi uygulayan <xref:System.Collections.IEnumerator> veya tüm içindetanımlananyöntemleribildirir`IEnumerator`.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:   **/CLR**

### <a name="example"></a>Örnek

Bu örnek nasıl kullanılacağını gösterir `for each` bir dize içinde yineleme için.

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

**Output**

```Output
abcd

Testing
```

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)
