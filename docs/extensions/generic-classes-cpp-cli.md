---
title: Genel Sınıflar (C++/CLI)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- classes [C++], generic
- generic classes [C++], about generic classes
- data types [C++], generic
- generic classes
- generics [C++], declaring generic classes
ms.assetid: 0beb99e1-1ec4-4fee-9836-ce9657d67a3a
ms.openlocfilehash: 78f4bf3abb98aab5e626e8ada538a22bdbca2912
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172366"
---
# <a name="generic-classes-ccli"></a>Genel Sınıflar (C++/CLI)

Genel bir sınıf aşağıdaki form kullanılarak bildirilmiştir:

## <a name="syntax"></a>Sözdizimi

```cpp
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

Yukarıdaki sözdiziminde, aşağıdaki terimler kullanılır:

*özelliklerine*<br/>
Seçim Ek bildirime dayalı bilgiler. Öznitelikler ve öznitelik sınıfları hakkında daha fazla bilgi için bkz. öznitelikler.

*sınıf anahtarı*<br/>
Ya **Class** ya da **TypeName**

tür parametrelerinin adlarını belirten, *tür-parametre*tanımlayıcıları, virgülle ayrılmış bir liste.

*kısıtlama-yan tümceler*<br/>
Tür parametrelerinin kısıtlamalarını belirten **WHERE** yan tümcelerinin listesi (virgülle ayrılmamış). Şu formu alır:

> **burada** *tür-parametre-tanımlayıcı* **:** *kısıtlama-liste*  **...**

*kısıtlama-liste*<br/>
*sınıf-or-arabirim*[`,` *...* ]

*Erişilebilirlik-değiştiriciler*<br/>
Genel sınıf için erişilebilirlik değiştiricileri. Windows Çalışma Zamanı için, yalnızca izin verilen değiştirici **özeldir**. Ortak dil çalışma zamanı için, izin verilen değiştiriciler **Private** ve **Public**' dir.

*Tanımlayıcısını*<br/>
Genel sınıfın adı, geçerli C++ bir tanımlayıcı.

*ilerine*<br/>
Seçim İzin verilen değiştiriciler **Sealed** ve **abstract**içerir.

*temel liste*<br/>
Tek bir temel sınıfı ve uygulanan tüm arabirimleri içeren bir liste, tümü virgülle ayrılır.

*sınıf-gövde*<br/>
Alanları, üye işlevlerini vb. içeren sınıfın gövdesi.

*Bildirimciler*<br/>
Bu türdeki değişkenlerin bildirimleri. Örneğin: `^`*tanımlayıcı*[`,`...]

Bunlar gibi genel sınıflar bildirebilirsiniz (anahtar sözcük **sınıfının** **TypeName**yerine kullanılabileceğini unutmayın). Bu örnekte, `ItemType``KeyType` ve `ValueType`, türün bulunduğu noktada belirtilen bilinmeyen türlerdir. `HashTable<int, int>`, genel tür `HashTable<KeyType, ValueType>`oluşturulmuş bir türüdür. Tek bir genel türden birçok farklı oluşturulmuş tür oluşturulabilir. Genel sınıflardan oluşturulan oluşturulmuş türler, diğer herhangi bir başvuru sınıfı türü gibi işlenir.

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

Her iki değer türü ( **int** veya **Double**gibi yerleşik türler ya da Kullanıcı tanımlı değer türleri) ve başvuru türleri genel tür bağımsız değişkeni olarak kullanılabilir. Genel tanım içindeki sözdizimi, ne olursa olsun aynıdır. Sözdizimi, bilinmeyen tür bir başvuru türü gibi değerlendirilir. Ancak çalışma zamanı, gerçekten kullanılan tür bir değer türüdür ve üyelere doğrudan erişim için uygun oluşturulan kodu yerine koyun. Genel tür bağımsız değişkenleri olarak kullanılan değer türleri kutulanmış değildir ve bu nedenle kutulama ile ilişkili performans cezası devam etmez. Genel gövdesinin içinde kullanılan sözdizimi, `.`yerine `T^` ve `->` olmalıdır. Tür bağımsız değişkeni bir değer türünde ise, tür parametresi için [gcnew New, gcnew](ref-new-gcnew-cpp-component-extensions.md) , bir değer türünün basit oluşturma çalışma zamanı tarafından uygun şekilde yorumlanır.

Ayrıca, tür parametresi için kullanılabilecek türler üzerinde [genel tür parametreleri (C++/CLI) üzerinde kısıtlamalar](constraints-on-generic-type-parameters-cpp-cli.md) içeren bir genel sınıf da bildirebilirsiniz. Aşağıdaki örnekte `ItemType` için kullanılan herhangi bir tür `IItem` arabirimini uygulamalıdır. Örneğin, `IItem`uygulamayan **int**'i kullanma girişimi, tür bağımsız değişkeni kısıtlamayı karşılamadığı için derleme zamanı hatası oluşturur.

```cpp
// generic_classes_2.cpp
// compile with: /clr /c
interface class IItem {};
generic <class ItemType>
where ItemType : IItem
ref class Stack {};
```

Aynı ad alanındaki genel sınıflar yalnızca sayı veya tür parametrelerinin türleri değiştirilerek aşırı yüklenemez. Ancak, her bir sınıf farklı bir ad alanında yer alıyorsa, aşırı yüklenebilir. Örneğin, `MyClass` ve `MyClass<ItemType>`ad alanları `A` ve `B`olmak üzere aşağıdaki iki sınıfı göz önünde bulundurun. Bu iki sınıf daha sonra C. üçüncü bir ad alanında aşırı yüklenebilir:

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

Temel sınıf ve temel arabirimler tür parametreleri olamaz. Ancak, temel sınıf aşağıdaki örnekte olduğu gibi tür parametresini bağımsız değişken olarak içerebilir:

```cpp
// generic_classes_4.cpp
// compile with: /clr /c
generic <typename ItemType>
interface class IInterface {};

generic <typename ItemType>
ref class MyClass : IInterface<ItemType> {};
```

Oluşturucular ve Yıkıcılar her nesne örneği için bir kez yürütülür (her zamanki gibi); statik oluşturucular, oluşturulan her tür için bir kez yürütülür.

## <a name="fields-in-generic-classes"></a>Genel sınıflardaki alanlar

Bu bölüm, genel sınıflarda örnek ve statik alanların kullanımını gösterir.

### <a name="instance-variables"></a>Örnek değişkenleri

Bir genel sınıfın örnek değişkenlerinin, kapsayan sınıftan herhangi bir tür parametresi içeren türler ve değişken başlatıcıları olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, MyClass\<ItemType > Genel sınıfının üç farklı örneği, uygun tür bağımsız değişkenleri (**int**, **Double**ve **String**) kullanılarak oluşturulur.

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

Yeni bir genel tür oluştururken, statik değişkenlerin yeni örnekleri oluşturulur ve bu tür için herhangi bir statik Oluşturucu yürütülür.

Statik değişkenler kapsayan sınıftan herhangi bir tür parametresini kullanabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, genel bir sınıf içindeki statik alanların ve statik oluşturucunun kullanımını gösterir.

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

## <a name="methods-in-generic-classes"></a>Genel sınıflardaki Yöntemler

Genel sınıflardaki yöntemler genel olabilir; Genel olmayan yöntemler, sınıf türü parametresi tarafından örtük olarak parametreleştirilecektir.

Aşağıdaki özel kurallar genel sınıfların içindeki yöntemlere uygulanır:

- Genel sınıflardaki Yöntemler tür parametrelerini parametreler, dönüş türleri veya yerel değişkenler olarak kullanabilir.

- Genel sınıflardaki Yöntemler parametreler, dönüş türleri veya yerel değişkenler olarak açık veya kapalı oluşturulmuş türler kullanabilir.

### <a name="non-generic-methods-in-generic-classes"></a>Genel sınıflarda genel olmayan Yöntemler

Ek tür parametrelerine sahip olmayan genel sınıflardaki metotlar genellikle genel olmayan olarak adlandırılır ancak kapsayan genel sınıf tarafından örtülü olarak parametrelenir.

Genel olmayan bir metodun imzası, kapsayan sınıfın bir veya daha fazla tür parametresini doğrudan ya da açık bir oluşturulmuş türde içerebilir. Örneğin:

`void MyMethod(MyClass<ItemType> x) {}`

Bu tür yöntemlerin gövdesi bu tür parametrelerini de kullanabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek genel olmayan bir yöntem `ProtectData`, genel bir sınıf içinde `MyClass<ItemType>`bildirir. Yöntemi, bir açık oluşturulmuş tür içindeki imzasında `ItemType` sınıf türü parametresini kullanır.

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

## <a name="generic-methods-in-generic-classes"></a>Genel sınıflarda genel metotlar

Genel ve genel olmayan sınıflarda genel yöntemler bildirebilirsiniz. Örneğin:

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

Genel olmayan yöntem, sınıfın tür parametresine göre parametreleştirildiği, ancak ek tür parametrelerine sahip olmadığı için hala geneldir.

Genel sınıflardaki tüm yöntem türleri, statik, örnek ve sanal yöntemler dahil genel olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek genel sınıflar içinde genel yöntemleri bildirme ve kullanma gösterir:

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

## <a name="using-nested-types-in-generic-classes"></a>Genel sınıflarda Iç Içe türler kullanma

Sıradan sınıflarda olduğu gibi, bir genel sınıf içinde başka türler de bildirebilirsiniz. İç içe geçmiş sınıf bildirimi, dış sınıf bildiriminin tür parametreleri tarafından örtük olarak parametrelenir. Bu nedenle, oluşturulan her bir dış tür için ayrı bir iç içe sınıf tanımlanmıştır. Örneğin, bildiriminde,

```cpp
// generic_classes_5.cpp
// compile with: /clr /c
generic <typename ItemType>
ref struct Outer {
   ref class Inner {};
};
```

Tür `Outer<int>::Inner` `Outer<double>::Inner`türü ile aynı değil.

Genel sınıflarda genel metotlarda olduğu gibi, iç içe geçmiş türü için ek tür parametreleri de tanımlanabilir. İç ve dış sınıfta aynı tür parametre adlarını kullanırsanız, iç tür parametresi dıştaki tür parametresini gizler.

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

Dış tür parametresine başvurmanız mümkün olmadığından, derleyici bu durumda bir uyarı oluşturur.

Oluşturulan iç içe genel türler adlandırılmışsa, dış türün tür parametresi iç türün tür parametresi listesine eklenmez, ancak iç tür dış türün tür parametresiyle örtük olarak parametrelendirilir. Yukarıdaki örnekte, oluşturulmuş bir türün adı `Outer<int>::Inner<string>`.

Aşağıdaki örnek, genel sınıflarda iç içe türler kullanılarak bağlantılı bir listeyi oluşturmayı ve okumayı gösterir.

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

## <a name="properties-events-indexers-and-operators-in-generic-classes"></a>Genel sınıflardaki özellikler, olaylar, Dizin oluşturucular ve Işleçler

- Özellikler, olaylar, Dizin oluşturucular ve işleçler kapsayan genel sınıfın tür parametrelerini dönüş değerleri, parametreler veya yerel değişkenler olarak kullanabilir, örneğin `ItemType` bir sınıfın tür parametresidir.

    ```cpp
    public ItemType MyProperty {}
    ```

- Özellikler, olaylar, Dizin oluşturucular ve işleçler parametreleştirilemez.

## <a name="example"></a>Örnek

Bu örnek, bir genel sınıf içindeki bir örnek özelliğinin bildirimlerini gösterir.

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

Sonraki örnekte, bir olayı olan genel bir sınıf gösterilmektedir.

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

Genel yapıları bildirme ve kullanma kuralları, görsel C++ dil başvurusunda belirtilen farklar dışında genel sınıflarla aynıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir alan, `myField`ve farklı türlerin (**int**, **Double**, `String^`) değerlerini bu alana atayan bir genel struct `MyGenStruct`bildirir.

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

## <a name="see-also"></a>Ayrıca bkz.

[Genel Türler](generics-cpp-component-extensions.md)
