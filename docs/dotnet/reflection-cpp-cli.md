---
description: 'Daha fazla bilgi edinin: yansıma (C++/CLı)'
title: Yansıma (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
- plug-ins [C++]
- reflection [C++}, plug-ins
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
ms.openlocfilehash: a3a9a33a239ec678279455ea41b7c60749cc0189
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245804"
---
# <a name="reflection-ccli"></a>Yansıma (C++/CLI)

Yansıma, bilinen veri türlerinin çalışma zamanında incelenebildiği şekilde izin verir. Yansıma, belirli bir derlemedeki veri türlerinin numaralandırılmasına izin verir ve belirli bir sınıfın veya değer türünün üyeleri bulunabilir. Bu, türün bilinen veya derleme zamanında Başvurulmuş olmasına bakılmaksızın geçerlidir. Bu, yansıma geliştirme ve kod yönetimi araçları için kullanışlı bir özellik oluşturur.

Belirtilen derleme adı, derleme sürümü, kültür ve imzalama bilgilerini içeren tanımlayıcı addır (bkz. [Strong-Named derlemeleri oluşturma ve kullanma](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)). Ayrıca, veri türünün tanımlandığı ad alanının adının, temel sınıfın adı ile birlikte alınamayacağını unutmayın.

Yansıma özelliklerine erişmenin en yaygın yolu <xref:System.Object.GetType%2A> yöntemi kullanmaktır. Bu yöntem tarafından <xref:System.Object?displayProperty=nameWithType> , tüm atık toplanan sınıfların türetileceğini tarafından sağlanır.

> [!NOTE]
> Microsoft C++ derleyicisi ile oluşturulan bir. exe ' de yansımaya yalnızca. exe **/clr: Pure** veya **/clr: Safe** derleyici seçenekleriyle derlenip izin verilir. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de kullanılamaz. Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) .

Daha fazla bilgi için bkz. <xref:System.Reflection>.

## <a name="example-gettype"></a>Örnek: GetType

`GetType`Yöntemi, <xref:System.Type> nesne tabanlı olduğunda türünü açıklayan bir sınıf nesnesine bir işaretçi döndürür. ( **Tür** nesnesi örneğe özgü herhangi bir bilgi içermiyor.) Bu tür bir öğe, aşağıdaki şekilde görüntülenebilen türün tam adıdır:

Tür adının, ad alanı dahil olmak üzere, türün tanımlandığı ve .NET söz diziminde, kapsam çözümleme operatörü olarak bir noktayla gösterildiği tam kapsamı içerdiğini unutmayın.

```cpp
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

## <a name="example-boxed-value-types"></a>Örnek: kutulanmış değer türleri

Değer türleri işlevle birlikte kullanılabilir `GetType` , ancak önce paketlenmelidir.

```cpp
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

## <a name="example-typeid"></a>Örnek: TypeId

Yönteminde olduğu gibi `GetType` , [TypeId](../extensions/typeid-cpp-component-extensions.md) işleci bir **tür** nesnesine bir işaretçi döndürür, bu nedenle bu kod **System. Int32** tür adını gösterir. Tür adlarının görüntülenmesi, yansımanın en temel özelliğidir, ancak büyük olasılıkla daha kullanışlı bir yöntem, numaralandırılmış türler için geçerli değerleri incelemek veya bulmektir. Bu, her biri metin biçiminde bir numaralandırma değeri içeren bir dize dizisi döndüren statik **enum:: GetNames** işlevi kullanılarak yapılabilir.  Aşağıdaki örnek, **Options** (CLR) sabit listesi için değer numaralandırma değerlerini açıklayan dizelerin dizisini alır ve bunları bir döngüde görüntüler.

**Seçenekler** numaralandırmasında dördüncü bir seçenek eklenirse, numaralandırma ayrı bir derlemede tanımlansa bile, bu kod yeniden derleme olmadan yeni seçeneği rapor eder.

```cpp
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

## <a name="example-gettype-members-and-properties"></a>Örnek: GetType üyeleri ve özellikleri

Nesnesi, bir `GetType` türü incelemek için kullanılabilecek sayıda üyeyi ve özelliği destekler. Bu kod, bu bilgilerden bazılarını alır ve görüntüler:

```cpp
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

## <a name="example-enumeration-of-types"></a>Örnek: türlerin numaralandırması

Yansıma ayrıca derleme içindeki türlerin ve sınıfların içindeki üyelerin numaralandırılmasına de olanak tanır. Bu özelliği göstermek için basit bir sınıf tanımlayın:

```cpp
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

## <a name="example-inspection-of-assemblies"></a>Örnek: derlemelerin incelemesi

Yukarıdaki kod vcpp_reflection_6.dll adlı bir DLL 'de derlenirse, bu derlemenin içeriğini incelemek için yansıma kullanabilirsiniz. Bu, derlemeyi yüklemek için XREF: System. Reflection. Assembly. Load% 2A? displayProperty = nameWithType statik yansıma API işlevini kullanmayı içerir. Bu işlev, içinde modüller ve türler hakkında sorgulanabilen bir **derleme** nesnesinin adresini döndürür.

Yansıma sistemi derlemeyi başarıyla yükledikten sonra, işleviyle nesne **türünde** bir dizi alınır <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> . Her dizi öğesi farklı bir tür hakkında bilgi içerir, ancak bu durumda yalnızca bir sınıf tanımlanmıştır. Bir döngü kullanarak, bu dizideki her **tür** , **Type:: GetMembers** işlevini kullanarak tür üyeleri hakkında sorgulanır. Bu işlev, tür içindeki üye işlev, veri üyesi veya özellik hakkında bilgi içeren bir **MethodInfo** nesneleri dizisini döndürür.

Yöntem listesinin **TestClass** içinde açıkça tanımlanan Işlevleri ve **System:: Object** sınıfından dolaylı olarak devralınmış işlevleri içerdiğini unutmayın. .NET ' te açıklanmakta olan Visual C++ söz dizimi yerine özellikler, Get/Set işlevleri tarafından erişilen temel alınan veri üyesi olarak görünür. Get/Set işlevleri bu listede normal yöntemler olarak görünür. Yansıma, Microsoft C++ derleyicisi tarafından değil, ortak dil çalışma zamanı aracılığıyla desteklenir.

Tanımladığınız bir derlemeyi incelemek için bu kodu kullansanız da, .NET derlemelerini incelemek için bu kodu da kullanabilirsiniz. Örneğin, TestAssembly öğesini mscorlib olarak değiştirirseniz, mscorlib.dll tanımlanan her tür ve yöntemin bir listesini görürsünüz.

```cpp
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

## <a name="how-to-implement-a-plug-in-component-architecture-using-reflection"></a><a name="implement"></a> Nasıl yapılır: yansıma kullanarak Plug-In bileşen mimarisi uygulama

Aşağıdaki kod örnekleri, basit bir "eklenti" mimarisi uygulamak için yansıma kullanımını gösterir. İlk liste uygulamadır, ikincisi ise eklentisidir. Uygulama, bir komut satırı bağımsız değişkeni olarak sağlanmış eklenti DLL 'sinde bulunan form tabanlı sınıfları kullanarak kendisini dolduran birden çok belge biçimidir.

Uygulama, yöntemi kullanarak belirtilen derlemeyi yüklemeye çalışır <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> . Başarılı olursa, derleme içindeki türler yöntemi kullanılarak numaralandırılır <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> . Her tür daha sonra yöntemi kullanılarak uyumluluk için denetlenir <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> . Bu örnekte, <xref:System.Windows.Forms.Form> bir eklenti olarak nitelendirmek için, belirtilen derlemede bulunan sınıfların sınıfından türetilmiş olması gerekir.

Daha sonra uyumlu sınıflar <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> , bir <xref:System.Type> bağımsız değişken olarak kabul edilen ve yeni bir örneğe bir işaretçi döndüren yöntemiyle oluşturulur. Her yeni örnek daha sonra forma iliştirilir ve görüntülenir.

<xref:System.Reflection.Assembly.Load%2A>Metodun dosya uzantısını içeren derleme adlarını kabul etmediğini unutmayın. Uygulamadaki Main işlevi, belirtilen tüm uzantıları kırpar, bu nedenle aşağıdaki kod örneği her iki durumda da çalışır.

### <a name="example"></a>Örnek

Aşağıdaki kod, eklentileri kabul eden uygulamayı tanımlar. Derleme adının ilk bağımsız değişken olarak sağlanması gerekir. Bu derleme en az bir ortak <xref:System.Windows.Forms.Form> türetilmiş tür içermelidir.

```cpp
// plugin_application.cpp
// compile with: /clr /c
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;

ref class PluggableForm : public Form  {
public:
   PluggableForm() {}
   PluggableForm(Assembly^ plugAssembly) {
      Text = "plug-in example";
      Size = Drawing::Size(400, 400);
      IsMdiContainer = true;

      array<Type^>^ types = plugAssembly->GetTypes( );
      Type^ formType = Form::typeid;

      for (int i = 0 ; i < types->Length ; i++) {
         if (formType->IsAssignableFrom(types[i])) {
            // Create an instance given the type description.
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));
            if (f) {
               f->Text = types[i]->ToString();
               f->MdiParent = this;
               f->Show();
            }
         }
      }
   }
};

int main() {
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");
   Application::Run(gcnew PluggableForm(a));
}
```

### <a name="example"></a>Örnek

Aşağıdaki kod, öğesinden türetilmiş üç sınıfı tanımlar <xref:System.Windows.Forms.Form> . Elde edilen derleme adının adı önceki listede yürütülebilir dosyaya geçirildiğinde, bu üç sınıfın her biri keşfedilir ve örneklenmiştir, bu da derleme zamanında barındırma uygulamasına bilinsin.

```cpp
// plugin_assembly.cpp
// compile with: /clr /LD
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;
using namespace System::Drawing;

public ref class BlueForm : public Form {
public:
   BlueForm() {
      BackColor = Color::Blue;
   }
};

public ref class CircleForm : public Form {
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);
   }
};

public ref class StarburstForm : public Form {
public:
   StarburstForm(){
      BackColor = Color::Black;
   }
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      Pen^ p = gcnew Pen(Color::Red, 2);
      Random^ r = gcnew Random( );
      Int32 w = ClientSize.Width;
      Int32 h = ClientSize.Height;
      for (int i=0; i<100; i++) {
         float x1 = w / 2;
         float y1 = h / 2;
         float x2 = r->Next(w);
         float y2 = r->Next(h);
         args->Graphics->DrawLine(p, x1, y1, x2, y2);
      }
   }
};
```

## <a name="how-to-enumerate-data-types-in-assemblies-using-reflection"></a><a name="enumerate"></a> Nasıl yapılır: yansıma kullanarak derlemelerde veri türlerini numaralandırma

Aşağıdaki kod, kullanarak genel türlerin ve üyelerin numaralandırılmasını gösterir <xref:System.Reflection> .

Bir derlemenin adı, yerel dizinde ya da GAC 'de verildiğinde, aşağıdaki kod derlemeyi açmaya ve açıklamaları almaya çalışır. Başarılı olursa, her tür ortak üyeleriyle birlikte görüntülenir.

<xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>Hiçbir dosya uzantısının kullanılmadığını unutmayın. Bu nedenle, "mscorlib.dll" komut satırı bağımsız değişkeni olarak kullanılması başarısız olur, ancak yalnızca "mscorlib" kullanılması .NET Framework türlerinin görüntülenmesini sağlayacaktır. Bütünleştirilmiş kod adı sağlanmazsa, kod geçerli derleme içindeki (bu koddan kaynaklanan EXE) türleri algılar ve bildirir.

### <a name="example"></a>Örnek

```cpp
// self_reflection.cpp
// compile with: /clr
using namespace System;
using namespace System::Reflection;
using namespace System::Collections;

public ref class ExampleType {
public:
   ExampleType() {}
   void Func() {}
};

int main() {
   String^ delimStr = " ";
   array<Char>^ delimiter = delimStr->ToCharArray( );
   array<String^>^ args = Environment::CommandLine->Split( delimiter );

// replace "self_reflection.exe" with an assembly from either the local
// directory or the GAC
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");
   Console::WriteLine(a);

   int count = 0;
   array<Type^>^ types = a->GetTypes();
   IEnumerator^ typeIter = types->GetEnumerator();

   while ( typeIter->MoveNext() ) {
      Type^ t = dynamic_cast<Type^>(typeIter->Current);
      Console::WriteLine("   {0}", t->ToString());

      array<MemberInfo^>^ members = t->GetMembers();
      IEnumerator^ memberIter = members->GetEnumerator();
      while ( memberIter->MoveNext() ) {
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);
         Console::Write("      {0}", mi->ToString( ) );
         if (mi->MemberType == MemberTypes::Constructor)
            Console::Write("   (constructor)");

         Console::WriteLine();
      }
      count++;
   }
   Console::WriteLine("{0} types found", count);
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
