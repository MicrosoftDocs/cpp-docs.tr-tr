---
title: Genel sınıflar (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], generic
- generic classes [C++], about generic classes
- data types [C++], generic
- generic classes
- generics [C++], declaring generic classes
ms.assetid: 0beb99e1-1ec4-4fee-9836-ce9657d67a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 751c7f9efe4f5db612419d5837cc2d6f304f43da
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570678"
---
# <a name="generic-classes-ccli"></a>Genel Sınıflar (C++/CLI)
Genel bir sınıf, aşağıdaki biçimi kullanarak bildirilir:  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[attributes]  
generic <class-key type-parameter-identifier(s)>  
[constraint-clauses]  
[accessibility-modifiers] ref class identifier  [modifiers]  
[: base-list]   
{  
class-body  
} [declarators] [;]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıdaki söz diziminde aşağıdaki terimler kullanılır:  
  
 `attributes` (isteğe bağlı)  
 Ek bildirim temelli bilgiler. Öznitelikleri öznitelikleri ve öznitelik sınıfları hakkında daha fazla bilgi için bkz.  
  
 *sınıf anahtarı*  
 Her iki **sınıfı** veya **typename**  
  
 *tür-parametresi-tanımlayıcıları*,  
 Tanımlayıcılar tür parametrelerinin adlarını belirten virgülle ayrılmış listesidir.  
  
 *kısıtlama yan tümceleri*  
 (Değil virgülle ayrılmış) listesi **burada** yan tümceleri tür parametreleri için kısıtlamalar belirtme. Şu biçimi alır:  
  
 `where`  *türü parametre tanımlayıcısı*`:`*sınırlama listesi*   `...`  
  
 *sınırlama listesi*  
 *sınıf veya arabirim*[`,` *...* ]  
  
 *erişilebilirlik değiştiricileri*  
 Genel bir sınıf için erişilebilirlik değiştiricileri. Windows çalışma zamanı için yalnızca izin verilen değiştiricidir **özel**. Ortak dil çalışma zamanı için izin verilen değiştiricilerdir **özel** ve **genel**.  
  
 *tanımlayıcı*  
 Geçerli bir C++ tanımlayıcısı genel sınıfın adı.  
  
 *değiştiriciler* (isteğe bağlı)  
 Değiştiriciler dahil izin **korumalı** ve **soyut**.  
  
 *temel-liste*  
 Virgülle ayrılmış tüm arabirimleri ve herhangi bir temel sınıf içeren bir liste uygulanır.  
  
 *sınıf-gövdesi*  
 Alanlar, üye işlevleri, vb. içeren sınıfın gövdesi.  
  
 *Bildirimciler*  
 Bu türün tüm değişkenlerin bildirimleri. Örneğin: `^` *tanımlayıcı*[`,` ...]  
  
 Genel sınıflar şunlar gibi bildirebilirsiniz (unutmayın anahtar sözcüğü **sınıfı** yerine kullanılabilir **typename**). Bu örnekte, `ItemType`, `KeyType` ve `ValueType` noktada belirtilen bilinmeyen türleri burada türü. `HashTable<int, int>` genel tür bir oluşturulmuş tür `HashTable<KeyType, ValueType>`. Tek bir genel türü bir dizi farklı oluşturulan türler oluşturulabilir. Oluşturulan türler genel sınıflardan oluşturulmuş gibi başka bir başvuru sınıfı türü kabul edilir.  
  
```cpp  
// generic_classes_1.cpp  
// compile with: /clr  
using namespace System;  
generic <typename ItemType>  
ref struct Stack {  
   // ItemType may be used as a type here  
   void Add(ItemType item) {}  
};  
  
generic <typename KeyType, typename ValueType>  
ref class HashTable {};  
  
// The keyword class may be used instead of typename:  
generic <class ListItem>  
ref class List {};  
  
int main() {  
   HashTable<int, Decimal>^ g1 = gcnew HashTable<int, Decimal>();  
}  
```  
  
 Her ikisi de değer türleri (ya da yerleşik türleri gibi **int** veya **çift**, veya kullanıcı tanımlı değer türleri) ve başvuru türleri bir genel tür bağımsız değişkeni kullanılır. Söz dizimi genel tanımındaki bağımsız olarak aynıdır. Sözdizimi, bir başvuru türü değilmiş gibi bilinmeyen tür kabul edilir. Ancak, çalışma zamanı gerçekten kullanılan türü bir değer türü olup olmadığını belirleyebilir ve doğrudan erişim üyeleri için uygun oluşturulan kodu değiştirin. Genel tür bağımsız değişkenleri kullanılan değer türleri Kutulu değil ve bu nedenle kutulama ile ilişkili performans cezası karşılaşmaz. Genel gövdesinde kullanılan sözdizimi olmalıdır `T^` ve `->` yerine `.`. Kullanımı [yeni başvuru, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) tür bağımsız değişkeni bir değer türü ise türü için parametre uygun şekilde çalışma zamanı tarafından basit oluşturulmasını bir değer türü yorumlanacaktır.  
  
 Genel bir sınıf ile aynı zamanda bildirebilirsiniz [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) türlerinde tür parametresi için kullanılabilir. Aşağıdaki örnekte herhangi bir türü kullanılan `ItemType` uygulamalıdır `IItem` arabirimi. Kullanılmaya çalışılıyor **int**, örneğin, hangi uygulamıyor `IItem`, tür bağımsız değişkeni kısıtlamasını karşılamaz çünkü bir derleme zamanı hatası oluşturur.  
  
```cpp  
// generic_classes_2.cpp  
// compile with: /clr /c  
interface class IItem {};  
generic <class ItemType>  
where ItemType : IItem  
ref class Stack {};  
```  
  
 Genel sınıflar aynı ad alanında, sayı veya tür parametrelerinin türleri yalnızca değiştirerek aşırı yüklenemez. Her sınıf, farklı bir ad alanında yaşıyorsa, ancak bunlar aşırı yüklenebilir. Örneğin, aşağıdaki iki sınıf düşünün `MyClass` ve `MyClass<ItemType>`, ad alanlarında `A` ve `B`. İki sınıf ardından üçüncü bir ad alanında C: aşırı yüklenebilir  
  
```cpp  
// generic_classes_3.cpp  
// compile with: /clr /c  
namespace A {  
   ref class MyClass {};  
}  
  
namespace B {  
   generic <typename ItemType>   
   ref class MyClass2 { };  
}  
  
namespace C {  
   using namespace A;  
   using namespace B;  
  
   ref class Test {  
      static void F() {  
         MyClass^ m1 = gcnew MyClass();   // OK  
         MyClass2<int>^ m2 = gcnew MyClass2<int>();   // OK  
      }  
   };  
}  
```  
  
 Taban sınıfı ve temel arabirimleri tür parametreleri olamaz. Ancak, temel sınıf tür parametresi, aşağıdaki durumda olduğu gibi bir bağımsız değişken olarak içerebilir:  
  
```cpp  
// generic_classes_4.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
interface class IInterface {};  
  
generic <typename ItemType>  
ref class MyClass : IInterface<ItemType> {};  
```  
  
 Oluşturucular ve Yıkıcılar kez her bir nesne örneği için (zamanki); yürütülür statik Oluşturucular, oluşturulan her tür için bir kez yürütülür.  
  
## <a name="fields-in-generic-classes"></a>Genel sınıflar alanları  
 Bu bölümde, örnek ve Genel sınıflar statik alanları kullanımını gösterir.  
  
### <a name="instance-variables"></a>Örnek değişkenleri  
 Bir genel sınıfın örneği değişkenleri türleri ve kapsayan sınıftaki herhangi bir tür parametreleri içeren değişken başlatıcılar olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, üç farklı örnekleri MyClass genel sınıfın\<Itemtype >, uygun tür bağımsız değişkeni kullanılarak oluşturulur (**int**, **çift**ve **dize**).  
  
```cpp  
// generics_instance_fields1.cpp  
// compile with: /clr  
// Instance fields on generic classes  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
// Field of the type ItemType:  
public :  
   ItemType field1;  
   // Constructor using a parameter of the type ItemType:  
   MyClass(ItemType p) {  
     field1 = p;   
   }  
};  
  
int main() {  
   // Instantiate an instance with an integer field:  
   MyClass<int>^ myObj1 = gcnew MyClass<int>(123);  
   Console::WriteLine("Integer field = {0}", myObj1->field1);  
  
   // Instantiate an instance with a double field:  
   MyClass<double>^ myObj2 = gcnew MyClass<double>(1.23);  
   Console::WriteLine("Double field = {0}", myObj2->field1);  
  
   // Instantiate an instance with a String field:  
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>("ABC");  
   Console::WriteLine("String field = {0}", myObj3->field1);  
   }  
```  
  
```Output  
Integer field = 123  
Double field = 1.23  
String field = ABC  
```  
  
## <a name="static-variables"></a>Statik değişkenler  
 Yeni bir genel tür oluşturma, tüm statik değişkenler, yeni örneklerini oluşturulur ve herhangi bir statik Oluşturucu türüne yürütülür.  
  
 Statik değişkenler kapsayan sınıftaki herhangi bir tür parametreleri kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, statik alanları ve genel bir sınıf içinde statik Oluşturucu kullanmayı gösterir.  
  
```cpp  
// generics_static2.cpp  
// compile with: /clr  
using namespace System;  
  
interface class ILog {  
   void Write(String^ s);  
};  
  
ref class DateTimeLog : ILog {  
public:  
   virtual void Write(String^ s) {  
      Console::WriteLine( "{0}\t{1}", DateTime::Now, s);  
   }  
};  
  
ref class PlainLog : ILog {  
public:  
   virtual void Write(String^ s) { Console::WriteLine(s); }  
};  
  
generic <typename LogType>  
where LogType : ILog  
ref class G {  
   static LogType s_log;  
  
public:  
   G(){}  
   void SetLog(LogType log) { s_log = log; }  
   void F() { s_log->Write("Test1"); }  
   static G() { Console::WriteLine("Static constructor called."); }     
};  
  
int main() {  
   G<PlainLog^>^ g1 = gcnew G<PlainLog^>();  
   g1->SetLog(gcnew PlainLog());  
   g1->F();  
  
   G<DateTimeLog^>^ g2 = gcnew G<DateTimeLog^>();  
   g2->SetLog(gcnew DateTimeLog());  
  
   // prints date  
   // g2->F();  
}  
```  
  
```Output  
Static constructor called.  
Static constructor called.  
Static constructor called.  
Test1  
```  
  
## <a name="methods-in-generic-classes"></a>Genel sınıflar yöntemleri  
 Genel sınıflar, yöntemler, genel olabilir; kendilerini Genel olmayan yöntemler sınıf türü parametresi tarafından örtük olarak parametreli.  
  
 Genel sınıflar yöntemlerinde aşağıdaki özel kurallar geçerlidir:  
  
-   Genel sınıflar, yöntemler tür parametreleri, parametre, dönüş türleri veya yerel değişkenler kullanabilirsiniz.  
  
-   Genel sınıflar yöntemleri açık veya kapalı oluşturulan türler parametre, dönüş türleri veya yerel değişkenler kullanabilirsiniz.  
  
### <a name="non-generic-methods-in-generic-classes"></a>Genel sınıflar genel olmayan yöntemleri  
 Örtük olarak kapsayan genel bir sınıf tarafından parametreli ancak hiçbir ek tür parametrelerine sahip genel sınıflardaki yöntemler genellikle için genel olmayan adlandırılır.  
  
 Genel olmayan yöntemin imzası kapsayan sınıfın, bir veya daha fazla tür parametreleri, doğrudan ya da açık bir oluşturulmuş tür içerebilir. Örneğin:  
  
 `void MyMethod(MyClass<ItemType> x) {}`  
  
 Bu tür yöntemler gövdesi, bu tür parametreleri olarak da kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir genel olmayan yöntemin bildirir `ProtectData`, genel bir sınıf içinde `MyClass<ItemType>`. Sınıf türü parametresini kullanmaktadır `ItemType` imzası açık bir oluşturulmuş tür içinde.  
  
```cpp  
// generics_non_generic_methods1.cpp  
// compile with: /clr  
// Non-generic methods within a generic class.  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
public:  
   String^ name;  
   ItemType data;  
  
   MyClass(ItemType x) {  
      data = x;  
   }  
  
   // Non-generic method using the type parameter:  
   virtual void ProtectData(MyClass<ItemType>^ x) {  
      data = x->data;  
   }  
};  
  
// ItemType defined as String^  
ref class MyMainClass: MyClass<String^> {  
public:  
   // Passing "123.00" to the constructor:  
   MyMainClass(): MyClass<String^>("123.00") {  
      name = "Jeff Smith";   
   }   
  
   virtual void ProtectData(MyClass<String^>^ x) override {  
      x->data = String::Format("${0}**", x->data);  
   }  
  
   static void Main() {  
      MyMainClass^ x1 = gcnew MyMainClass();  
  
      x1->ProtectData(x1);  
      Console::WriteLine("Name: {0}", x1->name);  
      Console::WriteLine("Amount: {0}", x1->data);  
   }  
};  
  
int main() {  
   MyMainClass::Main();  
}  
```  
  
```Output  
Name: Jeff Smith  
Amount: $123.00**  
```  
  
## <a name="generic-methods-in-generic-classes"></a>Genel sınıflar genel yöntemleri  
 Genel yöntemler hem genel hem de genel olmayan sınıflarda bildirebilirsiniz. Örneğin:  
  
## <a name="example"></a>Örnek  
  
```cpp  
// generics_method2.cpp  
// compile with: /clr /c  
generic <typename Type1>  
ref class G {  
public:  
   // Generic method having a type parameter  
   // from the class, Type1, and its own type  
   // parameter, Type2  
   generic <typename Type2>  
   void Method1(Type1 t1, Type2 t2) { F(t1, t2); }  
  
   // Non-generic method:  
   // Can use the class type param, Type1, but not Type2.  
   void Method2(Type1 t1) { F(t1, t1); }  
  
   void F(Object^ o1, Object^ o2) {}  
};  
```  
  
 Genel olmayan yöntemin sınıfın tür parametresi ile parametreli olup, ancak hiçbir ek tür parametreleri olan algılama içinde hala geneldir.  
  
 Genel sınıflar yöntemleri tüm türleri genel de dahil olmak üzere statik, örnek ve sanal yöntemleri olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bildirme ve genel yöntemlerle genel sınıflardaki gösterir:  
  
```cpp  
// generics_generic_method2.cpp  
// compile with: /clr  
using namespace System;  
generic <class ItemType>  
ref class MyClass {  
public:  
   // Declare a generic method member.  
   generic <class Type1>  
   String^ MyMethod(ItemType item, Type1 t) {  
      return String::Concat(item->ToString(), t->ToString());  
   }  
};  
  
int main() {  
   // Create instances using different types.  
   MyClass<int>^ myObj1 = gcnew MyClass<int>();  
   MyClass<String^>^ myObj2 = gcnew MyClass<String^>();  
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>();  
  
   // Calling MyMethod using two integers.  
   Console::WriteLine("MyMethod returned: {0}",  
            myObj1->MyMethod<int>(1, 2));  
  
   // Calling MyMethod using an integer and a string.  
   Console::WriteLine("MyMethod returned: {0}",  
            myObj2->MyMethod<int>("Hello #", 1));  
  
   // Calling MyMethod using two strings.  
   Console::WriteLine("MyMethod returned: {0}",  
       myObj3->MyMethod<String^>("Hello ", "World!"));  
  
   // generic methods can be called without specifying type arguments  
   myObj1->MyMethod<int>(1, 2);  
   myObj2->MyMethod<int>("Hello #", 1);  
   myObj3->MyMethod<String^>("Hello ", "World!");  
}  
```  
  
```Output  
MyMethod returned: 12  
MyMethod returned: Hello #1  
MyMethod returned: Hello World!  
```  
  
## <a name="using-nested-types-in-generic-classes"></a>İç içe geçmiş türler genel sınıflarında kullanma  
 Gibi sıradan sınıflarıyla genel bir sınıf içindeki diğer türlere bildirebilirsiniz. İç içe geçmiş sınıf bildirimi, dış sınıf bildiriminde tür parametreleri tarafından örtük olarak parametreli. Bu nedenle, farklı bir iç içe geçmiş sınıf, oluşturulan her dış tür için tanımlanır. Örneğin, bildirimi  
  
```cpp  
// generic_classes_5.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
ref struct Outer {  
   ref class Inner {};  
};  
```  
  
 Dış tür\<int >:: iç dış tür ile aynı değil\<çift >:: iç.  
  
 Gibi genel yöntemler genel sınıflardaki ek tür parametreleri için iç içe türü tanımlanabilir. İç ve dış sınıfında aynı tür parametresi adlarına kullanırsanız, iç tür parametresi dış tür parametresi gizler.  
  
```cpp  
// generic_classes_6.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
ref class Outer {  
   ItemType outer_item;   // refers to outer ItemType  
  
   generic <typename ItemType>  
   ref class Inner {  
      ItemType inner_item;   // refers to Inner ItemType  
   };  
};  
```  
  
 Derleyici, dış tür parametresine başvuran mümkün olduğundan, bu durumda bir uyarı üretecektir.  
  
 Oluşturulan iç içe geçmiş genel türler adlı, iç türü örtük olarak dış türün tür parametresi ile parametreli olsa bile dış türün tür parametresi iç türü için tür parametre listesinde bulunmaz. Yukarıdaki durumda, dış oluşturulan tür adını olacaktır\<int >:: iç\<dizesi >.  
  
 Aşağıdaki örnek, oluşturma ve iç içe geçmiş türler genel sınıfları kullanarak bağlantılı liste okuma gösterir.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// generics_linked_list.cpp  
// compile with: /clr  
using namespace System;  
generic <class ItemType>  
ref class LinkedList {  
// The node class:  
public:  
   ref class Node {  
   // The link field:  
   public:  
      Node^ next;  
      // The data field:  
      ItemType item;   
   } ^first, ^current;  
};  
  
ref class ListBuilder {  
public:  
   void BuildIt(LinkedList<double>^ list) {  
      /* Build the list */  
      double m[5] = {0.1, 0.2, 0.3, 0.4, 0.5};  
      Console::WriteLine("Building the list:");  
  
      for (int n=0; n<=4; n++) {  
         // Create a new node:  
         list->current = gcnew LinkedList<double>::Node();  
  
         // Assign a value to the data field:  
         list->current->item = m[n];  
  
         // Set the link field "next" to be the same as   
         // the "first" field:  
         list->current->next = list->first;  
  
         // Redirect "first" to the new node:  
         list->first = list->current;  
  
         // Display node's data as it builds:  
         Console::WriteLine(list->current->item);  
      }  
   }  
  
   void ReadIt(LinkedList<double>^ list) {  
      // Read the list  
      // Make "first" the "current" link field:  
      list->current = list->first;  
      Console::WriteLine("Reading nodes:");  
  
      // Read nodes until current == null:  
      while (list->current != nullptr) {  
         // Display the node's data field:  
         Console::WriteLine(list->current->item);  
  
         // Move to the next node:  
         list->current = list->current->next;  
      }  
   }  
};  
  
int main() {  
   // Create a list:  
   LinkedList<double>^ aList = gcnew LinkedList<double>();  
  
   // Initialize first node:  
   aList->first = nullptr;  
  
   // Instantiate the class, build, and read the list:   
   ListBuilder^ myListBuilder = gcnew ListBuilder();  
   myListBuilder->BuildIt(aList);  
   myListBuilder->ReadIt(aList);  
}  
```  
  
```Output  
Building the list:  
0.1  
0.2  
0.3  
0.4  
0.5  
Reading nodes:  
0.5  
0.4  
0.3  
0.2  
0.1  
```  
  
## <a name="properties-events-indexers-and-operators-in-generic-classes"></a>Özellikleri, olayları, dizin oluşturucular ve Genel sınıflar işleçleri  
  
-   Özellikleri, olayları, dizin oluşturucular ve işleçler kullanabileceğiniz kapsayan sınıfa genel tür parametrelerini dönüş değerleri, parametre veya ne zaman gibi yerel değişkenler olarak `ItemType` bir sınıfın bir tür parametresi:  
  
    ```  
    public ItemType MyProperty {}  
    ```  
  
-   Özellikleri, olayları, dizin oluşturucular ve işleçler kendilerini parametreleştirilemez.  
  
## <a name="example"></a>Örnek  
 Bu örnek, genel bir sınıf içinde bir Instance özelliği bildirimlerini gösterir.  
  
```cpp  
// generics_generic_properties1.cpp  
// compile with: /clr  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
private:  
   property ItemType myField;  
  
public:  
   property ItemType MyProperty {  
      ItemType get() {  
         return myField;   
      }  
      void set(ItemType value) {  
         myField = value;  
      }  
   }  
};  
  
int main() {  
   MyClass<String^>^ c = gcnew MyClass<String^>();  
   MyClass<int>^ c1 = gcnew MyClass<int>();  
  
   c->MyProperty = "John";  
   c1->MyProperty = 234;  
  
   Console::Write("{0}, {1}", c->MyProperty, c1->MyProperty);  
}  
```  
  
```Output  
John, 234  
```  
  
## <a name="example"></a>Örnek  
 Sonraki örnek, bir olay ile genel bir sınıf gösterir.  
  
```cpp  
// generics_generic_with_event.cpp  
// compile with: /clr  
// Declare a generic class with an event and  
// invoke events.  
using namespace System;  
  
// declare delegates  
generic <typename ItemType>  
delegate void ClickEventHandler(ItemType);  
  
// generic class that defines events  
generic <typename ItemType>  
ref class EventSource {  
public:  
   // declare the event OnClick  
   event ClickEventHandler<ItemType>^ OnClick;   
   void FireEvents(ItemType item) {  
      // raises events  
      OnClick(item);  
   }  
};  
  
// generic class that defines methods that will called when  
// event occurs  
generic <typename ItemType>  
ref class EventReceiver {  
public:  
   void OnMyClick(ItemType item) {  
     Console::WriteLine("OnClick: {0}", item);  
   }  
};  
  
int main() {  
   EventSource<String^>^ MyEventSourceString =  
                   gcnew EventSource<String^>();  
   EventSource<int>^ MyEventSourceInt = gcnew EventSource<int>();  
   EventReceiver<String^>^ MyEventReceiverString =  
                   gcnew EventReceiver<String^>();  
   EventReceiver<int>^ MyEventReceiverInt = gcnew EventReceiver<int>();  
  
   // hook handler to event  
   MyEventSourceString->OnClick += gcnew ClickEventHandler<String^>(  
       MyEventReceiverString, &EventReceiver<String^>::OnMyClick);  
   MyEventSourceInt->OnClick += gcnew ClickEventHandler<int>(  
             MyEventReceiverInt, &EventReceiver<int>::OnMyClick);  
  
   // invoke events  
   MyEventSourceString->FireEvents("Hello");  
   MyEventSourceInt->FireEvents(112);  
  
   // unhook handler to event  
   MyEventSourceString->OnClick -= gcnew ClickEventHandler<String^>(  
        MyEventReceiverString, &EventReceiver<String^>::OnMyClick);  
   MyEventSourceInt->OnClick -= gcnew ClickEventHandler<int>(  
        MyEventReceiverInt, &EventReceiver<int>::OnMyClick);  
}  
```  
  
## <a name="generic-structs"></a>Genel yapılar  
 Kuralları bildirme ve genel yapılar kullanarak Visual C++ dil başvurusu, belirtilen farklılıklar dışında Genel sınıflar için aynıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, genel bir struct bildirir `MyGenStruct`, bir alan `myField`ve farklı türlerde değerler atar (**int**, **çift**, `String^`) Bu alan için.  
  
```cpp  
// generics_generic_struct1.cpp  
// compile with: /clr  
using namespace System;  
  
generic <typename ItemType>  
ref struct MyGenStruct {  
public:  
   ItemType myField;  
  
   ItemType AssignValue(ItemType item) {  
      myField = item;  
      return myField;  
   }  
};  
  
int main() {  
   int myInt = 123;  
   MyGenStruct<int>^ myIntObj = gcnew MyGenStruct<int>();  
   myIntObj->AssignValue(myInt);  
   Console::WriteLine("The field is assigned the integer value: {0}",  
            myIntObj->myField);  
  
   double myDouble = 0.123;  
   MyGenStruct<double>^ myDoubleObj = gcnew MyGenStruct<double>();  
   myDoubleObj->AssignValue(myDouble);  
   Console::WriteLine("The field is assigned the double value: {0}",  
            myDoubleObj->myField);  
  
   String^ myString = "Hello Generics!";  
   MyGenStruct<String^>^ myStringObj = gcnew MyGenStruct<String^>();  
   myStringObj->AssignValue(myString);  
   Console::WriteLine("The field is assigned the string: {0}",  
            myStringObj->myField);  
}  
```  
  
```Output  
The field is assigned the integer value: 123  
The field is assigned the double value: 0.123  
The field is assigned the string: Hello Generics!  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](../windows/generics-cpp-component-extensions.md)