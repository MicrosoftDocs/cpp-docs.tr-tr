---
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
ms.openlocfilehash: a17910e0288b81723aa837ba9204bb40713d5d49
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384692"
---
# <a name="reflection-ccli"></a>Yansıma (C++/CLI)

Yansıma bilinen veri türleri, çalışma zamanında denetlenmesine olanak sağlar. Yansıma veri türlerini numaralandırma, belirtilen bir derlemede sağlar ve belirli bir sınıf veya değer türünün üyesi bulundu. Bu türü bilinen veya başvurulan derleme zamanında olup bağımsız olarak geçerlidir. Bu yansıma geliştirme ve kod Yönetim Araçları için kullanışlı bir özelliği sağlar.

Sağlanan derleme adı için tanımlayıcı adı olduğunu unutmayın (bkz [bkz](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)), derleme sürümü, kültürü ve imza bilgilerini içerir. Ayrıca, veri türünün tanımlandığı ad alanı adı, temel sınıfın adı ile birlikte alınabilir olduğunu unutmayın.

Yansıma özelliklerine erişmek için en yaygın yollarından biri sayesinde <xref:System.Object.GetType%2A> yöntemi. Bu yöntem tarafından sağlanan <xref:System.Object?displayProperty=nameWithType>, hangi atık olarak toplanmış tüm sınıflar türetilen öğesinden.

> [!NOTE]
> Visual C++ derleyicisi ile .exe yansıma .exe ile oluşturulursa yalnızca izin **/CLR: pure** veya **/CLR: safe** derleyici seçenekleri. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri, Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de kullanılamaz. Bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) daha fazla bilgi için.

Daha fazla bilgi için bkz. <xref:System.Reflection>

## <a name="example-gettype"></a>Örnek: GetType

`GetType` Yöntemi için bir işaretçi döndüren bir <xref:System.Type> nesnenin ne zaman alan temel türü tanımlayan sınıf nesnesi. ( **Türü** nesne herhangi bir örneğe özel bilgi içermiyor.) Böyle bir öğe türü şu şekilde görüntülendiğini tam adıdır:

Tür adı, türü, ad alanı dahil tanımlandığı tam kapsam içerdiğini ve .NET sözdiziminde, kapsam çözümleme işleci olarak bir nokta olan görüntülendiğinden emin unutmayın.

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

## <a name="example-boxed-value-types"></a>Örnek: paketlenmiş değer türleri

Değer türleri ile kullanılabilir `GetType` de çalışır, ancak önce paketlenmelidir.

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

## <a name="example-typeid"></a>Örnek: typeid

Olduğu gibi `GetType` yöntemi [TypeID](../extensions/typeid-cpp-component-extensions.md) işleci bir işaretçi döndürür bir **türü** nesne türü adı bu kodu gösterir şekilde **System.Int32**. Tür adları görüntüleme yansıma en temel özelliğidir, ancak potansiyel olarak daha yararlı bir Teknik İnceleme veya numaralandırılmış türler için geçerli değerleri bulmak için. Bu statik kullanarak yapılabilir **Enum::GetNames** işlev, her bir numaralandırma değeri metin biçiminde içeren bir dize dizesi döndürür.  Aşağıdaki örnek değeri sabit listesi değerlerini tanımlayan bir dize dizisi alır **seçenekleri** (CLR) sabit listesi ve bir döngüde görüntüler.

Dördüncü bir seçenek eklenirse **seçenekleri** sabit listesi, bu kod gerekmeksizin, sabit listesi, ayrı bir derlemede tanımlanan olsa bile yeni seçenek bildirir.

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

`GetType` Nesnesi bir dizi üyeleri ve bir tür incelemek için kullanılan özellikleri destekler. Bu kod, alır ve bu bilgilerin bazıları görüntüler:

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

## <a name="example-enumeration-of-types"></a>Örnek: sabit listesi türleri

Yansıma, sabit bir derleme içinde tür ve üye sınıflardaki de sağlar. Bu özellik göstermek için basit bir sınıf tanımlayın:

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

## <a name="example-inspection-of-assemblies"></a>Örnek: inceleme derleme

Yukarıdaki kod vcpp_reflection_6.dll adlı bir DLL içine derlenir, bu derlemenin içeriğini incelemek için yansıma kullanabilirsiniz. Bu derlemeyi API işlevi xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType statik yansıma kullanarak içerir. Bu işlev adresini döndürür bir **derleme** içindeki türler ve modüller hakkında sorgulanabilir bir nesne.

Yansıma sistem derleme, bir dizi başarıyla yüklendikten sonra **türü** nesneleri ile alınır <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> işlevi. Bu durumda, yalnızca bir sınıf tanımlanır ancak her dizi öğesi farklı bir türle ilgili bilgi içerir. Bir döngü kullanarak her **türü** kullanarak tür üyeleri hakkında bu dizinin içinde sorgulanır **Type::GetMembers** işlevi. Bu işlev bir dizi döndürür **MethodInfo** nesneleri, üye işlevi, veri üyesi veya özellik türü hakkında bilgi içeren her bir nesne.

Yöntemlerin listesi işlevleri açıkça içeren Not tanımlanan **TestClass** ve işlev örtük olarak devralındığı **System::Object** sınıfı. .NET yerine Visual C++ sözdizimi tanımlanmakta bir parçası olarak, Özellikler get/set işlevleri tarafından erişilen temel alınan veri üyesi olarak görünür. Get/set işlevleri, normal yöntemler olarak bu listede görünür. Yansıma, ortak dil çalışma zamanı değil Visual C++ Derleyici tarafından desteklenir.

Bu kod, tanımladığınız bir derlemeyi incelemek için kullanılan olsa da, .NET derlemeleri incelemek için bu kod da kullanabilirsiniz. Örneğin, mscorlib için TestAssembly değiştirirseniz, her tür ve yöntem mscorlib.dll içinde tanımlanan bir listesini görürsünüz.

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

## <a name="implement"></a> Nasıl Yapılır: Yansıma kullanarak eklenti bileşeni mimarisi uygulama

Aşağıdaki kod örnekleri, basit bir "eklentisi" mimarisi uygulama yansıma kullanımını gösterir. İlk liste uygulamadır ve ikinci eklentidir. Uygulamanın kendisi bir komut satırı bağımsız değişken olarak sağlanan eklentisi dll bulunan herhangi bir form tabanlı sınıflar dolduran bir birden çok belge biçimidir.

Uygulamayı kullanarak sağlanan derlemesini yükleme girişiminde <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> yöntemi. Başarılı olursa derleme içindeki türler kullanılarak numaralandırılır, <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> yöntemi. Uyumluluk kullanmak için her tür denetlenir <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> yöntemi. Bu örnekte, belirtilen derlemede bulunan sınıflar nesnesinden türetilmesi gerekir <xref:System.Windows.Forms.Form> bir eklenti nitelemek için sınıf.

Uyumlu sınıflar ile ardından oluşturulur <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> kabul eden yöntemi bir <xref:System.Type> bağımsız değişken olarak ve yeni bir örneğine bir işaretçi döndürür. Her yeni örnek daha sonra forma eklenir ve görüntülenir.

Unutmayın <xref:System.Reflection.Assembly.Load%2A> yöntemi dosya uzantısı içeren derleme adları kabul etmez. Aşağıdaki kod örneği her iki durumda da çalışır. Bu nedenle uygulama main işlevi herhangi bir sağlanan uzantısı kırpar.

### <a name="example"></a>Örnek

Aşağıdaki kod eklentileri kabul eden uygulama tanımlar. İlk bağımsız değişken olarak bir derleme adı sağlanmalıdır. Bu derlemenin en az bir ortak içermelidir <xref:System.Windows.Forms.Form> türetilmiş tür.

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

Aşağıdaki kod öğelerinden türetilen üç sınıfları tanımlar <xref:System.Windows.Forms.Form>. Elde edilen derlemenin adı, önceki listede bulunan yürütülebilir geçirildiğinde, bu üç sınıfların her birini bulunur ve barındırma uygulaması derleme zamanında bilinmeyen tüm olgu rağmen örneği.

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

## <a name="enumerate"></a> Nasıl Yapılır: Yansıma kullanarak derlemelerde veri türlerini numaralandırma

Aşağıdaki kod, genel türler ve üyeler kullanarak numaralandırmasını gösterir <xref:System.Reflection>.

Aşağıdaki kod, bir derlemenin adını yerel dizindeki veya GAC'deki göz önünde bulundurulduğunda, derleme açın ve açıklamaları almak çalışır. Başarılı olursa, her tür genel üyeleri görüntülenir.

Unutmayın <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> dosyanın uzantısı kullanılmasını gerektirir. Yalnızca "mscorlib" kullanarak .NET Framework türleri görüntülenmesini neden olur bu nedenle, bir komut satırı bağımsız değişkeni "mscorlib.dll" kullanarak, başarısız olur. Bütünleştirilmiş kod adı sağlanmazsa, kod algılamak ve geçerli derlemedeki türleri (Bu koddan oluşan EXE) bildirin.

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
