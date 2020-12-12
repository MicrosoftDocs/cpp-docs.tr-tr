---
description: ': String (C++/CLı ve C++/CX) hakkında daha fazla bilgi'
title: Dize (C++/CLI ve C++/CX)
ms.date: 10/08/2018
ms.topic: reference
helpviewer_keywords:
- string support with /clr
- /clr compiler option [C++], string support
ms.assetid: c695f965-9be0-4e20-9661-373bfee6557e
ms.openlocfilehash: a47842713d1e7349717eaaeddcd4f3cba86fbbea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206337"
---
# <a name="string--ccli-and-ccx"></a>Dize (C++/CLI ve C++/CX)

Windows Çalışma Zamanı ve ortak dil çalışma zamanı, ayrılan bellek otomatik olarak yönetilen nesneler olarak dizeleri temsil eder. Diğer bir deyişle, dize değişkeni kapsam dışına geçtiğinde veya uygulamanız sona erdiğinde bir dizenin belleğini açıkça atmak zorunda değilsiniz. Bir dize nesnesinin yaşam süresinin otomatik olarak yönetileceğini göstermek için, dize türünü [Handle-to-Object (^)](handle-to-object-operator-hat-cpp-component-extensions.md) değiştiricisi ile bildirin.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Windows Çalışma Zamanı mimarisi, `String` veri türünün `Platform` ad alanında bulunmasını gerektirir. Kolaylık olması için Visual C++, `string` ad alanındaki için bir eş anlamlı olan veri türünü de sağlar `Platform::String` `default` .

### <a name="syntax"></a>Syntax

```cpp
// compile with /ZW
using namespace Platform;
using namespace default;
   Platform::String^ MyString1 = "The quick brown fox";
   String^ MyString2 = "jumped over the lazy dog.";
   String^ MyString3 = "Hello, world!";
```

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

İle derlerken `/clr` , derleyici dize değişmez değerlerini tür dizelerine dönüştürür <xref:System.String> . Mevcut kodla geriye dönük uyumluluğu korumak için bunun iki özel durumu vardır:

- Özel durum işleme. Bir dize sabit değeri oluşturulduğunda, derleyici onu bir dize sabit değeri olarak yakalayacak.

- Şablon kesintisi. Bir dize sabit değeri, bir şablon bağımsız değişkeni olarak geçirildiğinde, derleyici onu bir öğesine dönüştürmeyecektir <xref:System.String> . Genel bir bağımsız değişken olarak geçirilen dize sabit değerleri, öğesine Yükseltilecek <xref:System.String> .

Derleyici Ayrıca, davranışlarını özelleştirmek için geçersiz kılabileceğiniz üç işleç için yerleşik desteğe sahiptir:

- System:: String ^ işleç + (System:: String, System:: String);

- System:: String ^ işleç + (System:: Object, System:: String);

- System:: String ^ işleç + (System:: String, System:: Object);

Bir geçirildiğinde, <xref:System.String> derleyici, gerekirse, sonra da nesnesini (ToString ile) dize ile birleştirir.

> [!NOTE]
> Şapka işareti ("^"), belirtilen değişkenin bir C++/CLı yönetilen nesnesine yönelik bir tanıtıcı olduğunu gösterir.

Daha fazla bilgi için bkz. [dize ve karakter sabit değerleri](../cpp/string-and-character-literals-cpp.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/clr**

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği dizeleri birleştirerek ve karşılaştırmayı gösterir.

```cpp
// string_operators.cpp
// compile with: /clr
// In the following code, the caret ("^") indicates that the
// declared variable is a handle to a C++/CLI managed object.
using namespace System;

int main() {
   String^ a = gcnew String("abc");
   String^ b = "def";   // same as gcnew form
   Object^ c = gcnew String("ghi");

   char d[100] = "abc";

   // variables of System::String returning a System::String
   Console::WriteLine(a + b);
   Console::WriteLine(a + c);
   Console::WriteLine(c + a);

   // accessing a character in the string
   Console::WriteLine(a[2]);

   // concatenation of three System::Strings
   Console::WriteLine(a + b + c);

   // concatenation of a System::String and string literal
   Console::WriteLine(a + "zzz");

   // you can append to a System::String^
   Console::WriteLine(a + 1);
   Console::WriteLine(a + 'a');
   Console::WriteLine(a + 3.1);

   // test System::String^ for equality
   a += b;
   Console::WriteLine(a);
   a = b;
   if (a == b)
      Console::WriteLine("a and b are equal");

   a = "abc";
   if (a != b)
      Console::WriteLine("a and b are not equal");

   // System:String^ and tracking reference
   String^% rstr1 = a;
   Console::WriteLine(rstr1);

   // testing an empty System::String^
   String^ n;
   if (n == nullptr)
      Console::WriteLine("n is empty");
}
```

```Output
abcdef

abcghi

ghiabc

c

abcdefghi

abczzz

abc1

abc97

abc3.1

abcdef

a and b are equal

a and b are not equal

abc

n is empty
```

Aşağıdaki örnek, derleyicinin sunduğu işleçleri aşırı yükleyebilir ve derleyicinin türü temel alarak bir işlev aşırı yüklemesi bulabileceğinizi gösterir <xref:System.String> .

```cpp
// string_operators_2.cpp
// compile with: /clr
using namespace System;

// a string^ overload will be favored when calling with a String
void Test_Overload(const char * a) {
   Console::WriteLine("const char * a");
}
void Test_Overload(String^ a) {
   Console::WriteLine("String^ a");
}

// overload will be called instead of compiler defined operator
String^ operator +(String^ a, String^ b) {
   return ("overloaded +(String^ a, String^ b)");
}

// overload will be called instead of compiler defined operator
String^ operator +(Object^ a, String^ b) {
   return ("overloaded +(Object^ a, String^ b)");
}

// overload will be called instead of compiler defined operator
String^ operator +(String^ a, Object^ b) {
   return ("overloaded +(String^ a, Object^ b)");
}

int main() {
   String^ a = gcnew String("abc");
   String^ b = "def";   // same as gcnew form
   Object^ c = gcnew String("ghi");

   char d[100] = "abc";

   Console::WriteLine(a + b);
   Console::WriteLine(a + c);
   Console::WriteLine(c + a);

   Test_Overload("hello");
   Test_Overload(d);
}
```

```Output
overloaded +(String^ a, String^ b)

overloaded +(String^ a, Object^ b)

overloaded +(Object^ a, String^ b)

String^ a

const char * a
```

Aşağıdaki örnekte, derleyicinin yerel dizeler ve dizeler arasında ayrım gösterdiği gösterilmektedir <xref:System.String> .

```cpp
// string_operators_3.cpp
// compile with: /clr
using namespace System;
int func() {
   throw "simple string";   // const char *
};

int func2() {
   throw "string" + "string";   // returns System::String
};

template<typename T>
void func3(T t) {
   Console::WriteLine(T::typeid);
}

int main() {
   try {
      func();
   }
   catch(char * e) {
      Console::WriteLine("char *");
   }

   try {
      func2();
   }
   catch(String^ str) {
      Console::WriteLine("String^ str");
   }

   func3("string");   // const char *
   func3("string" + "string");   // returns System::String
}
```

```Output
char *

String^ str

System.SByte*

System.String
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)<br/>
[Dize ve karakter değişmez değerleri](../cpp/string-and-character-literals-cpp.md)<br/>
[/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)
