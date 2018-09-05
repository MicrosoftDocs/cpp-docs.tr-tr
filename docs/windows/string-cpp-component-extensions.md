---
title: Dize (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- string support with /clr
- /clr compiler option [C++], string support
ms.assetid: c695f965-9be0-4e20-9661-373bfee6557e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e37a3a934fbc66af62a30fd2fc2c23e1c659ef2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43692104"
---
# <a name="string--c-component-extensions"></a>Dize (C++ Bileşen Uzantıları)

Visual C++ derleyicisi destekleyen *dizeleri*, metin bir karakter dizisi temsil eden nesneleri olduğu. Visual C++ dize değişkenleri, değeri örtük olarak ve değeri olan bir açık alıntılanmış dize değişmez değerleri, destekler.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Windows çalışma zamanı ve ortak dil çalışma zamanı dizeleri, ayrılan bellek otomatik olarak yönetilen nesneler olarak temsil eder. Diğer bir deyişle, kapsamdan dize değişkeni çıktığında veya uygulamanızı sona erdiğinde bir dize için belleği açıkça iptal gerekmez. Bir dize nesnesi ömrü otomatik olarak yönetilecek olduğunu belirtmek için ile dize türü bildirin [tanıtıcı nesnesi (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) değiştiricisi.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Windows çalışma zamanı mimariyi uygulamak Visual C++ gerektirir `String` veri türü olarak `Platform` ad alanı. Kolaylık olması için de Visual C++ sağlar `string` veri türü, bu değer için bir eşanlamlı `Platform::String`, `default` ad alanı.

### <a name="syntax"></a>Sözdizimi

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

Bu konuda, Visual C++ derleyicisi kullanarak çalıştırdığınızda dize değişmez değerleri nasıl işlediğini ele alınmaktadır `/clr` derleyici seçeneği. Kullanılacak `/clr`, ortak dil çalışma zamanı (CLR), C + ayrıca kullanmalısınız +/ CLI söz dizimi ve yönetilen nesneler. Hakkında daha fazla bilgi için `/clr`, bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

İle derlerken `/clr`, derleyici dize sabit değerleri türü dizeye dönüştürür <xref:System.String>. Varolan kodu ile geriye dönük uyumluluk korumak için bu iki özel durumlar şunlardır:

- Özel durum işleme. Derleyici bir dize sabit değeri oluştuğunda, bir dize sabit değeri olarak yakalar.

- Şablon kesintisi. Bir şablon bağımsız değişken olarak geçirilen bir dize sabit değeri, derleyici için dönüştürmez. bir <xref:System.String>. Unutmayın, genel bir bağımsız değişken olarak geçirilen bir dize değişmez değerleri için yükseltilecek <xref:System.String>.

Derleyici, bunların davranışını özelleştirmek için geçersiz kılabilirsiniz üç işleçleri için yerleşik destek de vardır:

- System::String ^ işleci + (System:: String'i, System::String);

- System::String ^ + işleci (System::Object, System::String);

- System::String ^ + işleci (System::String, System::Object);

Geçirildiğinde bir <xref:System.String>, derleyici kutusuna, gerekirse ve ardından nesne (ToString) dizesi ile birleştirin.

> [!NOTE]
> Giriş işaretini ("^") için C + tanıtıcı bildirilmiş bir değişken gösterir +/ CLI yönetilen nesne.

Daha fazla bilgi için [dize ve karakter değişmez değerleri](../cpp/string-and-character-literals-cpp.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:   **/CLR**

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, birleştirme ve dizeleri karşılaştırma gösterir.

```cpp
// string_operators.cpp
// compile with: /clr
// In the following code, the caret ("^") indicates that the
// declared variable is a handle to a C++/CLI managed object.
using namespace System;

int main() {
   String ^ a = gcnew String("abc");
   String ^ b = "def";   // same as gcnew form
   Object ^ c = gcnew String("ghi");

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

   // you can append to a System::String ^
   Console::WriteLine(a + 1);
   Console::WriteLine(a + 'a');
   Console::WriteLine(a + 3.1);

   // test System::String ^ for equality
   a += b;
   Console::WriteLine(a);
   a = b;
   if (a == b)  
      Console::WriteLine("a and b are equal");

   a = "abc";
   if (a != b)  
      Console::WriteLine("a and b are not equal");

   // System:String ^ and tracking reference
   String^% rstr1 = a;
   Console::WriteLine(rstr1);

   // testing an empty System::String ^
   String ^ n;
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

Aşağıdaki örnek, derleyici tarafından sağlanan işleçleri Aşırı yüklenme olabilir ve derleyicinin temel işlev aşırı yüklemesi bulabilirsiniz gösterir <xref:System.String> türü.

```cpp
// string_operators_2.cpp
// compile with: /clr
using namespace System;

// a string^ overload will be favored when calling with a String
void Test_Overload(const char * a) {
   Console::WriteLine("const char * a");
}
void Test_Overload(String ^ a) {
   Console::WriteLine("String ^ a");
}

// overload will be called instead of compiler defined operator
String ^ operator +(String ^ a, String ^ b) {
   return ("overloaded +(String ^ a, String ^ b)");
}

// overload will be called instead of compiler defined operator
String ^ operator +(Object ^ a, String ^ b) {
   return ("overloaded +(Object ^ a, String ^ b)");
}

// overload will be called instead of compiler defined operator
String ^ operator +(String ^ a, Object ^ b) {
   return ("overloaded +(String ^ a, Object ^ b)");
}

int main() {
   String ^ a = gcnew String("abc");
   String ^ b = "def";   // same as gcnew form
   Object ^ c = gcnew String("ghi");

   char d[100] = "abc";

   Console::WriteLine(a + b);
   Console::WriteLine(a + c);
   Console::WriteLine(c + a);

   Test_Overload("hello");
   Test_Overload(d);
}
```

```Output
overloaded +(String ^ a, String ^ b)

overloaded +(String ^ a, Object ^ b)

overloaded +(Object ^ a, String ^ b)

String ^ a

const char * a
```

Aşağıdaki örnek, derleyici yerel dizeler arasında ayıran gösterir ve <xref:System.String> dizeleri.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)  
[Dize ve Karakter Değişmez Değerleri](../cpp/string-and-character-literals-cpp.md)  
[/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)