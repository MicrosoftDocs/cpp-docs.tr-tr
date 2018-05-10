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
ms.openlocfilehash: cfab95c400aad949f06a559fffbdb42993910bb7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="string--c-component-extensions"></a>Dize (C++ Bileşen Uzantıları)
Visual C++ Derleyici destekler *dizeleri*, metin bir karakter dizisi temsil eden nesneler olduğu. Visual C++ dize değişkenleri, değeri olan örtük ve açık bir tırnak içine alınmış dize değeri olan değişmez değerleri, destekler.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 Windows çalışma zamanı ve ortak dil çalışma zamanı dizeleri ayrılmış olan bellek otomatik olarak yönetilen nesneler olarak temsil eder. Diğer bir deyişle, kapsam dışına dize değişken duruma geçtiğinde veya uygulamanızın sona erdiğinde bir dize için bellek açıkça atmak için gerekmez. Bir dize nesnesi ömrü otomatik olarak yönetilecek olduğunu belirtmek için dize türü ile bildirme [tanıtıcı nesnesi (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) değiştiricisi.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Windows çalışma zamanı mimarisi uygulamak Visual C++ gerektirir `String` veri türü `Platform` ad alanı. Size kolaylık sağlamak için Visual C++ de sağlar `string` veri türü, olduğu eşanlamlısı `Platform::String`, `default` ad alanı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
// compile with /ZW  
using namespace Platform;  
using namespace default;  
   Platform::String^ MyString1 = "The quick brown fox";  
   String^ MyString2 = "jumped over the lazy dog.";  
   String^ MyString3 = "Hello, world!";  
  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi ve dizeleri hakkında örnekler için bkz: [Platform::String, std::wstring ve değişmez değerleri (Platform)](http://msdn.microsoft.com/en-us/ec92fbc6-edf3-4137-a85e-8e29bdb857a8)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 Bu konuda ele alınmıştır kullanarak çalıştırdığınızda, Visual C++ derleyicisi dize değişmez değerleri nasıl işlediği **/CLR** derleyici seçeneği. Kullanılacak **/CLR**, ortak dil çalışma zamanı (CLR) C + kullanmanız gerekir +/ CLI sözdizimi ve yönetilen nesneler. Hakkında daha fazla bilgi için **/CLR**, bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 İle derleme yapılırken **/CLR**, derleyici dize değişmez değerleri türü dizelere dönüştürecek <xref:System.String>. Var olan kodu ile geriye dönük uyumluluk korumak için bu iki özel durumlar şunlardır:  
  
-   Özel durum işleme. Derleyici bir değişmez dize değeri oluştuğunda bir dize yakalar.  
  
-   Şablon kesintisi. Şablon bağımsız değişken bir dize sabit değeri geçirildiğinde derleyici kendisine biçimine dönüştürmez. bir <xref:System.String>. Not: genel bir bağımsız değişken olarak geçirilen dize değişmez değerleri tanıtılması için <xref:System.String>.  
  
 Derleyici, ayrıca bunların davranışını özelleştirmek için geçersiz kılabilirsiniz üç işleç için yerleşik destek vardır:  
  
-   System::String ^ işleci + (System:: String'i, System:: String'i);  
  
-   System::String ^ işleci + (System::Object, System:: String'i);  
  
-   System::String ^ işleci + (System::String, System::Object);  
  
 Geçirildiğinde bir <xref:System.String>, derleyici, gerekirse kutusuna ve nesne (ToString) dizesi ile art arda ekler.  
  
> [!NOTE]
>  Düzeltme işareti ("^") için C + tanıtıcı bildirilen değişkeni gösterir +/ CLI yönetilen nesne.  
  
 Daha fazla bilgi için bkz: [dize ve karakter değişmez değerleri](../cpp/string-and-character-literals-cpp.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneğinde, birleştirme ve dizeleri karşılaştırma gösterir.  
  
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
  
 **Output**  
  
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
  
 **Örnek**  
  
 Aşağıdaki örnek, sağlanan derleyici işleçleri aşırı yüklenebilir ve derleyici dayalı bir işlev aşırı yüklemesiyle bulacaksınız gösterir <xref:System.String> türü.  
  
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
  
 **Output**  
  
```Output  
overloaded +(String ^ a, String ^ b)   
  
overloaded +(String ^ a, Object ^ b)   
  
overloaded +(Object ^ a, String ^ b)   
  
String ^ a  
  
const char * a  
```  
  
 **Örnek**  
  
 Aşağıdaki örnek, derleyici arasında yerel dizeler ayırt gösterir ve <xref:System.String> dizeleri.  
  
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
  
 **Output**  
  
```Output  
char *  
  
String^ str  
  
System.SByte*  
  
System.String  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)   
 [Dize ve karakter değişmez değerleri](../cpp/string-and-character-literals-cpp.md)   
 [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)