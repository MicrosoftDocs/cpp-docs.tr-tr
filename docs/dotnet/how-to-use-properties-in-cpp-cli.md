---
title: 'Nasıl yapılır: özellikler C + kullanan +/ CLI | Microsoft Docs'
ms.custom: ''
ms.date: 07/21/2017
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- simple properties
- properties [C++], simple
ms.assetid: f5d82547-e214-4f05-9e1b-ddb6d0dc5e4c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4873b7d37ef55c050ef074323c4644e4277f593d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33134349"
---
# <a name="how-to-use-properties-in-ccli"></a>Nasıl yapılır: C++/CLI Üzerinde Özellikleri Kullanma
Bu makalede özelliklerinin C + nasıl kullanılacağını gösterir +/ CLI.  
  
## <a name="basic-properties"></a>Temel özellikler  
 Temel özellikler için — yalnızca atamak ve bir özel veri üyesi almak o — açıkça get tanımlayın ve derleyici otomatik olarak bunları yalnızca özelliğin veri türü verildiğinde sağladığından erişimci işlevleri ayarlayın gerekmez. Bu kod bir temel özellik gösterir:  
  
```cpp  
// SimpleProperties.cpp  
// compile with: /clr  
using namespace System;  
  
ref class C {  
public:  
   property int Size;  
};  
  
int main() {  
   C^ c = gcnew C;  
   c->Size = 111;  
   Console::WriteLine("c->Size = {0}", c->Size);  
}  
```  
  
```Output  
c->Size = 111  
```  
  
## <a name="static-properties"></a>Statik özellikler  
 Bu kod örneği, bildirme ve bir statik özellik kullanma gösterilmektedir.  Bir statik özellik yalnızca kendi sınıfı statik üyeleri erişebilir.  
  
```cpp  
// mcppv2_property_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class StaticProperties {  
   static int MyInt;  
   static int MyInt2;  
  
public:  
   static property int Static_Data_Member_Property;  
  
   static property int Static_Block_Property {  
      int get() {  
         return MyInt;  
      }  
  
      void set(int value) {  
         MyInt = value;  
      }        
   }  
};  
  
int main() {  
   StaticProperties::Static_Data_Member_Property = 96;  
   Console::WriteLine(StaticProperties::Static_Data_Member_Property);  
  
   StaticProperties::Static_Block_Property = 47;  
   Console::WriteLine(StaticProperties::Static_Block_Property);  
}  
```  
  
```Output  
96  
47  
```  
  
## <a name="indexed-properties"></a>Dizinli Özellikler  
 Dizinli bir özelliği, genellikle bir alt simge işleci kullanılarak erişilen veri yapısı kullanıma sunar.  
  
 Kullanırsanız, varsayılan bir dizin oluşturulmuş özellik, yalnızca sınıf adını başvurarak veri yapısı erişebilirsiniz, ancak kullanıcı tarafından tanımlanan dizinli özelliğini kullanırsanız, veri yapısı erişmek için özellik adı belirtmeniz gerekir.  
  
 C# ile yazılmış bir dizin oluşturucusunu kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: C# dizin oluşturucusunu kullanma (C + +/ CLI)](../dotnet/how-to-consume-a-csharp-indexer-cpp-cli.md).  
  
 Bu kod örneği, varsayılan ve kullanıcı tarafından tanımlanan Dizinli Özellikler nasıl kullanılacağını gösterir:  
  
```cpp  
// mcppv2_property_2.cpp  
// compile with: /clr  
using namespace System;  
public ref class C {  
   array<int>^ MyArr;  
  
public:  
   C() {  
      MyArr = gcnew array<int>(5);  
   }  
  
   // default indexer  
   property int default[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
  
   // user-defined indexer  
   property int indexer1[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
};  
  
int main() {  
   C ^ MyC = gcnew C();  
  
   // use the default indexer  
   Console::Write("[ ");  
   for (int i = 0 ; i < 5 ; i++) {  
      MyC[i] = i;  
      Console::Write("{0} ", MyC[i]);  
   }  
  
   Console::WriteLine("]");  
  
   // use the user-defined indexer  
   Console::Write("[ ");  
   for (int i = 0 ; i < 5 ; i++) {  
      MyC->indexer1[i] = i * 2;  
      Console::Write("{0} ", MyC->indexer1[i]);  
   }  
  
   Console::WriteLine("]");  
}  
```  
  
```Output  
[ 0 1 2 3 4 ]  
[ 0 2 4 6 8 ]  
```  
  
 Sonraki örnek varsayılan dizin oluşturucu kullanarak çağrısının nasıl gerçekleştireceğini `this` işaretçi.  
  
```cpp  
// call_default_indexer_through_this_pointer.cpp  
// compile with: /clr /c  
value class Position {  
public:  
   Position(int x, int y) : position(gcnew array<int, 2>(100, 100)) {  
      this->default[x, y] = 1;  
   }  
  
   property int default[int, int] {  
      int get(int x, int y) {  
         return position[x, y];  
      }  
  
      void set(int x, int y, int value) {}  
   }  
  
private:  
   array<int, 2> ^ position;  
};  
```  
  
 Bu örnek nasıl kullanılacağını göstermektedir <xref:System.Reflection.DefaultMemberAttribute> varsayılan dizin oluşturucu belirtmek için:  
  
```cpp  
// specify_default_indexer.cpp  
// compile with: /LD /clr  
using namespace System;  
[Reflection::DefaultMember("XXX")]  
public ref struct Squares {  
   property Double XXX[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
```  
  
 Sonraki örnek önceki örnekte oluşturulan meta verileri kullanır.  
  
```cpp  
// consume_default_indexer.cpp  
// compile with: /clr  
#using "specify_default_indexer.dll"  
int main() {  
   Squares ^ square = gcnew Squares();  
   System::Console::WriteLine("{0}", square[3]);  
}  
```  
  
```Output  
9  
```  
  
## <a name="virtual-properties"></a>Sanal Özellikler  
 Bu kod örneği, sanal özellikleri bildirme ve kullanma gösterilmektedir:  
  
```cpp  
// mcppv2_property_4.cpp  
// compile with: /clr  
using namespace System;  
interface struct IEFace {  
public:  
   property int VirtualProperty1;  
   property int VirtualProperty2 {  
      int get();  
      void set(int i);  
   }  
};  
  
// implement virtual events  
ref class PropImpl : public IEFace {  
   int MyInt;  
public:  
   virtual property int VirtualProperty1;  
  
   virtual property int VirtualProperty2 {  
      int get() {  
         return MyInt;  
      }  
      void set(int i) {  
         MyInt = i;  
      }  
   }  
};  
  
int main() {  
   PropImpl ^ MyPI = gcnew PropImpl();  
   MyPI->VirtualProperty1 = 93;  
   Console::WriteLine(MyPI->VirtualProperty1);  
  
   MyPI->VirtualProperty2 = 43;  
   Console::WriteLine(MyPI->VirtualProperty2);  
}  
```  
  
```Output  
93  
43  
```  
  
## <a name="abstract-and-sealed-properties"></a>Soyut ve korumalı özellikleri  
 Ancak [soyut](../windows/abstract-cpp-component-extensions.md) ve [korumalı](../windows/sealed-cpp-component-extensions.md) anahtar sözcükleri belirtilen geçerli olarak içinde ECMA C + +/ CLI belirtimi, Visual C++ Derleyici belirtemezsiniz bunları Önemsiz özellikleri veya özellik Önemsiz olmayan bir özellik bildirimi.  
  
 Bir korumalı veya Özet özelliği bildirmek için Önemsiz olmayan bir özellik tanımlayın ve ardından belirtin `abstract` veya `sealed` get anahtar sözcüğü ve erişimci işlevleri ayarlayın.  
  
```cpp  
// properties_abstract_sealed.cpp  
// compile with: /clr  
ref struct A {  
protected:  
   int m_i;  
  
public:  
   A() { m_i = 87; }  
  
   // define abstract property  
   property int Prop_1 {  
      virtual int get() abstract;  
      virtual void set(int i) abstract;  
   }  
};  
  
ref struct B : A {  
private:  
   int m_i;  
  
public:  
   B() { m_i = 86; }  
  
   // implement abstract property  
   property int Prop_1 {  
      virtual int get() override { return m_i; }  
      virtual void set(int i) override { m_i = i; }  
   }  
};  
  
ref struct C {  
private:  
   int m_i;  
  
public:  
   C() { m_i = 87; }  
  
   // define sealed property  
   property int Prop_2 {  
      virtual int get() sealed { return m_i; }  
      virtual void set(int i) sealed { m_i = i; };  
   }  
};  
  
int main() {  
   B b1;  
   // call implementation of abstract property  
   System::Console::WriteLine(b1.Prop_1);  
  
   C c1;  
   // call sealed property  
   System::Console::WriteLine(c1.Prop_2);  
}  
```  
  
```Output  
86  
87  
```  
  
## <a name="multidimensional-properties"></a>Çok boyutlu Özellikler  
 Çok boyutlu özellikleri, standart olmayan bir parametre sayısı ele özellik erişimci yöntemlerini tanımlamak için kullanabilirsiniz.  
  
```cpp  
// mcppv2_property_5.cpp  
// compile with: /clr  
ref class X {  
   double d;  
public:  
   X() : d(0) {}  
   property double MultiDimProp[int, int, int] {  
      double get(int, int, int) {  
         return d;  
      }  
      void set(int i, int j, int k, double l) {  
         // do something with those ints  
         d = l;  
      }  
   }  
  
   property double MultiDimProp2[int] {  
      double get(int) {  
         return d;  
      }  
      void set(int i, double l) {  
         // do something with those ints  
         d = l;  
      }  
   }  
  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   MyX->MultiDimProp[0,0,0] = 1.1;  
   System::Console::WriteLine(MyX->MultiDimProp[0, 0, 0]);  
}  
```  
  
```Output  
1.1  
```  
  
## <a name="overloading-property-accessors"></a>Özellik erişimcisi aşırı yüklemesi  
 Aşağıdaki örnek, Dizinli Özellikler aşırı yükleme gösterilmektedir.  
  
```cpp  
// mcppv2_property_6.cpp  
// compile with: /clr  
ref class X {  
   double d;  
public:  
   X() : d(0.0) {}  
   property double MyProp[int] {  
      double get(int i) {  
         return d;  
      }  
  
      double get(System::String ^ i) {  
         return 2*d;  
      }  
  
      void set(int i, double l) {  
         d = i * l;  
      }  
   }   // end MyProp definition  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   MyX->MyProp[2] = 1.7;  
   System::Console::WriteLine(MyX->MyProp[1]);  
   System::Console::WriteLine(MyX->MyProp["test"]);  
}  
```  
  
```Output  
3.4  
6.8  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [property](../windows/property-cpp-component-extensions.md)