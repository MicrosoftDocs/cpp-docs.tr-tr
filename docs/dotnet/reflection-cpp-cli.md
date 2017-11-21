---
title: "Yansıma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cff5256d94593959c280614858cdde8be3dee9f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="reflection-ccli"></a>Yansıma (C++/CLI)
Yansıma çalışma zamanında denetlenecek bilinen veri türlerine izin verir. Belirli bir sınıf ya da değer türü üyeleri bulunan ve yansıma verilen derlemedeki veri türlerini numaralandırma sağlar. Bu tür bilinen veya derleme zamanında başvurulan bakılmaksızın bakılmaksızın geçerlidir. Bu yansıma geliştirme ve kod Yönetim Araçları için kullanışlı bir özelliği sağlar.  
  
 Sağlanan derleme adı tanımlayıcı ad olduğuna dikkat edin (bkz [bkz](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)), derleme sürüm, kültür ve imzalama bilgilerini içerir. Ayrıca, veri türünün tanımlandığı ad alanı, temel sınıfın adını birlikte alınabilir olduğunu unutmayın.  
  
 Yansıma özelliklerine erişmek için en yaygın yolu aracılığıyladır <xref:System.Object.GetType%2A> yöntemi. Bu yöntem tarafından sağlanan [System::Object](https://msdn.microsoft.com/en-us/library/system.object.aspx), hangi çöp toplanan tüm sınıflar türetilen gelen.  
  
 Visual C++ derleyicisi ile .exe yansıma .exe ile oluşturulursa yalnızca izin **/CLR: pure** veya **/CLR: safe** derleyici seçenekleri. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı. Bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) daha fazla bilgi için.  
  
 Bu bölümdeki konular:  
  
-   [Nasıl yapılır: yansıma kullanarak eklenti bileşeni mimarisi uygulama (C + +/ CLI)](../dotnet/how-to-implement-a-plug-in-component-architecture-using-reflection-cpp-cli.md)  
  
-   [Nasıl yapılır: yansıma kullanarak derlemelerde veri türlerini numaralandırma (C + +/ CLI)](../dotnet/how-to-enumerate-data-types-in-assemblies-using-reflection-cpp-cli.md)  
  
 Daha fazla bilgi için bkz: [System.Reflection Namespace](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)  
  
## <a name="example"></a>Örnek  
 `GetType` Yöntemi döndürür gösteren bir işaretçi bir <xref:System.Type> nesne zaman tabanlı bağlı türünü açıklayan sınıf nesnesi. ( **Türü** nesnesi hiçbir örnek özgü bilgileri içermiyor.) Böyle bir öğe gibi görüntülenecek türü tam adıdır:  
  
 Tür adı türü, ad alanı dahil tanımlandığı tam kapsamı içerir ve kapsam çözümü işleci olarak bir nokta olan .NET sözdiziminde görüntülenip görüntülenmediğini unutmayın.  
  
```  
// vcpp_reflection.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^ s = "sample string";  
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());  
}  
```  
  
```Output  
full type name of 'sample string' is 'System.String'  
```  
  
## <a name="example"></a>Örnek  
 Değer türleri ile kullanılabilir `GetType` de çalışır, ancak bunlar ilk Kutulu gerekir.  
  
```  
// vcpp_reflection_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Int32 i = 100;   
   Object ^ o = i;  
   Console::WriteLine("type of i = '{0}'", o->GetType());  
}  
```  
  
```Output  
type of i = 'System.Int32'  
```  
  
## <a name="example"></a>Örnek  
 Olduğu gibi `GetType` yöntemi, [TypeID](../windows/typeid-cpp-component-extensions.md) işleci döndürür gösteren bir işaretçi bir **türü** nesnesi türü adı bu kodu gösterir şekilde **System.Int32**. Tür adları görüntüleme yansıma en temel özellik, ancak büyük olasılıkla daha kullanışlı bir Teknik İnceleme veya numaralandırılmış türler için geçerli değerleri bulmak için. Bu statik kullanılarak yapılabilir **Enum::GetNames** işlev, her bir numaralandırma değeri metin biçiminde içeren dizeler, bir dizi döndürür.  Aşağıdaki örnek için değer numaralandırma değerlerini tanımlayan bir dize dizisi alır **seçenekleri** (CLR) enum ve bunları bir döngüde görüntüler.  
  
 Dördüncü bir seçenek eklenirse **seçenekleri** numaralandırma, bu kod gerekmeksizin numaralandırması ayrı bir derlemede tanımlanan olsa bile yeni seçenek bildirir.  
  
```  
// vcpp_reflection_3.cpp  
// compile with: /clr  
using namespace System;  
  
enum class Options {   // not a native enum  
   Option1, Option2, Option3  
};  
  
int main() {  
   array<String^>^ names = Enum::GetNames(Options::typeid);  
  
   Console::WriteLine("there are {0} options in enum '{1}'",   
               names->Length, Options::typeid);  
  
   for (int i = 0 ; i < names->Length ; i++)  
      Console::WriteLine("{0}: {1}", i, names[i]);  
  
   Options o = Options::Option2;  
   Console::WriteLine("value of 'o' is {0}", o);  
}  
```  
  
```Output  
there are 3 options in enum 'Options'  
0: Option1  
1: Option2  
2: Option3  
value of 'o' is Option2  
```  
  
## <a name="example"></a>Örnek  
 `GetType` Nesnesi bir dizi üyeleri ve bir türü incelemek için kullanılan özelliklerini destekler. Bu kod alır ve bu bilgilerin bazıları görüntüler:  
  
```  
// vcpp_reflection_4.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Console::WriteLine("type information for 'String':");  
   Type ^ t = String::typeid;  
  
   String ^ assemblyName = t->Assembly->FullName;  
   Console::WriteLine("assembly name: {0}", assemblyName);  
  
   String ^ nameSpace = t->Namespace;  
   Console::WriteLine("namespace: {0}", nameSpace);  
  
   String ^ baseType = t->BaseType->FullName;  
   Console::WriteLine("base type: {0}", baseType);  
  
   bool isArray = t->IsArray;  
   Console::WriteLine("is array: {0}", isArray);  
  
   bool isClass = t->IsClass;  
   Console::WriteLine("is class: {0}", isClass);  
}  
```  
  
```Output  
type information for 'String':  
assembly name: mscorlib, Version=1.0.5000.0, Culture=neutral,   
PublicKeyToken=b77a5c561934e089  
namespace: System  
base type: System.Object  
is array: False  
is class: True  
```  
  
## <a name="example"></a>Örnek  
 Yansıma derlemedeki türleri ve sınıflardaki üyelerin listesi de sağlar. Bu özellik göstermek için basit bir sınıf tanımlayın:  
  
```  
// vcpp_reflection_5.cpp  
// compile with: /clr /LD  
using namespace System;  
public ref class TestClass {  
   int m_i;  
public:  
   TestClass() {}  
   void SimpleTestMember1() {}  
   String ^ SimpleMember2(String ^ s) { return s; }   
   int TestMember(int i) { return i; }  
   property int Member {  
      int get() { return m_i; }  
      void set(int i) { m_i = i; }  
   }  
};  
```  
  
## <a name="example"></a>Örnek  
 Yukarıdaki kod vcpp_reflection_6.dll adlı bir DLL'e derlenmiş ise, bu derleme içeriğini incelemek için yansıma kullanabilirsiniz. Bu statik yansıma API işlevi kullanarak içerir [Assembly::Load](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx) derlemesi yüklenemedi. Bu işlev adresini döndürür bir **derleme** içinde türleri ve modülleri hakkında sorgulanabilir nesnesi.  
  
 Yansıma sistem başarıyla derleme, bir dizi yükler sonra **türü** nesneleri ile alınır [Assembly::GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx) işlevi. Bu durumda, yalnızca bir sınıf tanımlanan olsa da her dizi öğesi farklı bir türü hakkında bilgi içerir. Bir döngü kullanarak her **türü** bu dizide kullanarak tür üyeleri hakkında sorgulanır **Type::GetMembers** işlevi. Bu işlev bir dizi döndürür **MethodInfo** nesneleri, üye işlevi, veri üyesi veya özellik türü hakkında bilgi içeren her bir nesne.  
  
 Yöntemlerin listesi işlevleri açıkça içerdiğini unutmayın tanımlanan **TestClass** ve işlevleri örtük olarak devralınan **System::Object** sınıfı. .NET yerine Visual C++ söz diziminde tanımlanmakta parçası olarak, Özellikler get/set işlevleri tarafından erişilen temel alınan veri üyesi olarak görünür. Get/set işlevleri normal yöntemler olarak bu listede görünür. Yansıma ortak dil çalışma zamanı değil Visual C++ derleyicisi tarafından desteklenir.  
  
 Bu kodu tanımladığınız derlemeyi incelemek için kullanılan rağmen .NET derlemelerini incelemek için bu kodu de kullanabilirsiniz. Örneğin, TestAssembly mscorlib olarak değiştirirseniz, her tür ve mscrlib.dll tanımlanan yöntemi listesini görürsünüz.  
  
```  
// vcpp_reflection_6.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
using namespace System::Reflection;  
int main() {  
   Assembly ^ a = nullptr;  
   try {  
      // load assembly -- do not use file extension  
      // will look for .dll extension first  
      // then .exe with the filename  
      a = Assembly::Load("vcpp_reflection_5");  
   }  
   catch (FileNotFoundException ^ e) {  
      Console::WriteLine(e->Message);  
      return -1;  
   }  
  
   Console::WriteLine("assembly info:");  
   Console::WriteLine(a->FullName);  
   array<Type^>^ typeArray = a->GetTypes();  
  
   Console::WriteLine("type info ({0} types):", typeArray->Length);  
  
   int totalTypes = 0;  
   int totalMembers = 0;  
   for (int i = 0 ; i < typeArray->Length ; i++) {  
      // retrieve array of member descriptions  
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();  
  
      Console::WriteLine("  members of {0} ({1} members):",   
      typeArray[i]->FullName, member->Length);  
      for (int j = 0 ; j < member->Length ; j++) {  
         Console::Write("       ({0})",   
         member[j]->MemberType.ToString() );  
         Console::Write("{0}  ", member[j]);  
         Console::WriteLine("");  
         totalMembers++;  
      }  
      totalTypes++;  
   }  
   Console::WriteLine("{0} total types, {1} total members",  
   totalTypes, totalMembers);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)