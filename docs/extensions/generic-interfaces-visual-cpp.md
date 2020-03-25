---
title: Genel arabirimler (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- generic interfaces
- interfaces, generic [C++}
ms.assetid: f3da788a-ba83-4db7-9dcf-9b95a8fb9d1a
ms.openlocfilehash: 35dba37f1441144a3f7276388be1f61bebc84139
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182025"
---
# <a name="generic-interfaces-ccli"></a>Genel arabirimler (C++/CLI)

Sınıflarda tür parametrelerine uygulanan kısıtlamalar, arabirimlerde tür parametrelerine uygulananlarla aynıdır (bkz. [genel sınıflar (C++/CLI)](generic-classes-cpp-cli.md)).

İşlev aşırı yüklemesini denetleyen kurallar, genel sınıflar veya genel arabirimler içindeki işlevler için aynıdır.

Açık arabirim üyesi uygulamalar, basit arabirim türleriyle aynı şekilde oluşturulmuş arabirim türleriyle çalışır (aşağıdaki örneklere bakın).

Arabirimler hakkında daha fazla bilgi için bkz. [interface class](interface-class-cpp-component-extensions.md).

## <a name="syntax"></a>Sözdizimi

```cpp
[attributes] generic <class-key type-parameter-identifier[, ...]>
[type-parameter-constraints-clauses][accesibility-modifiers] interface class identifier [: base-list] {   interface-body} [declarators] ;
```

## <a name="remarks"></a>Açıklamalar

*özelliklerine*<br/>
Seçim Ek bildirime dayalı bilgiler. Öznitelikler ve öznitelik sınıfları hakkında daha fazla bilgi için bkz. **öznitelikler**.

*sınıf anahtarı*<br/>
**Class** veya **TypeName**

*tür-parametre tanımlayıcıları*<br/>
Virgülle ayrılmış tanımlayıcılar listesi.

*tür-parametre-kısıtlamalar-yan tümceler*<br/>
[Genel tür parametrelerindeki (C++/CLI) kısıtlamalarda](constraints-on-generic-type-parameters-cpp-cli.md) belirtilen formu alır

*Erişilebilirlik-değiştiriciler*<br/>
Seçim Erişilebilirlik değiştiricileri (örn. **Genel, özel**).

*Tanımlayıcısını*<br/>
Arabirim adı.

*temel liste*<br/>
Seçim Virgülle ayrılmış bir veya daha fazla açık temel arabirim içeren bir liste.

*arabirim-gövde*<br/>
Arabirim üyelerinin bildirimleri.

*Bildirimciler*<br/>
Seçim Bu türe göre değişkenlerin bildirimleri.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, genel bir arabirimin nasıl bildirildiği ve örneklendirileceğini gösterilmektedir. Örnekte, genel arabirim `IList<ItemType>` bildirilmiştir. Daha sonra, farklı uygulamalarla `List1<ItemType>` ve `List2<ItemType>`iki genel sınıf tarafından uygulanır.

```cpp
// generic_interface.cpp
// compile with: /clr
using namespace System;

// An exception to be thrown by the List when
// attempting to access elements beyond the
// end of the list.
ref class ElementNotFoundException : Exception {};

// A generic List interface
generic <typename ItemType>
public interface class IList {
   ItemType MoveFirst();
   bool Add(ItemType item);
   bool AtEnd();
   ItemType Current();
   void MoveNext();
};

// A linked list implementation of IList
generic <typename ItemType>
public ref class List1 : public IList<ItemType> {
   ref class Node {
      ItemType m_item;

   public:
      ItemType get_Item() { return m_item; };
      void set_Item(ItemType value) { m_item = value; };

      Node^ next;

      Node(ItemType item) {
         m_item = item;
         next = nullptr;
      }
   };

   Node^ first;
   Node^ last;
   Node^ current;

   public:
   List1() {
      first = nullptr;
      last = first;
      current = first;
   }

   virtual ItemType MoveFirst() {
      current = first;
      if (first != nullptr)
        return first->get_Item();
      else
         return ItemType();
   }

   virtual bool Add(ItemType item) {
      if (last != nullptr) {
         last->next = gcnew Node(item);
         last = last->next;
      }
      else {
         first = gcnew Node(item);
         last = first;
         current = first;
      }
      return true;
   }

   virtual bool AtEnd() {
      if (current == nullptr )
        return true;
      else
        return false;
   }

   virtual ItemType Current() {
       if (current != nullptr)
         return current->get_Item();
       else
         throw gcnew ElementNotFoundException();
   }

   virtual void MoveNext() {
      if (current != nullptr)
       current = current->next;
      else
        throw gcnew ElementNotFoundException();
   }
};

// An array implementation of IList
generic <typename ItemType>
ref class List2 : public IList<ItemType> {
   array<ItemType>^ item_array;
   int count;
   int current;

   public:

   List2() {
      // not yet possible to declare an
      // array of a generic type parameter
      item_array = gcnew array<ItemType>(256);
      count = current = 0;
   }

   virtual ItemType MoveFirst() {
      current = 0;
      return item_array[0];
   }

   virtual bool Add(ItemType item) {
      if (count < 256)
         item_array[count++] = item;
      else
        return false;
      return true;
   }

   virtual bool AtEnd() {
      if (current >= count)
        return true;
      else
        return false;
   }

   virtual ItemType Current() {
      if (current < count)
        return item_array[current];
      else
        throw gcnew ElementNotFoundException();
   }

   virtual void MoveNext() {
      if (current < count)
         ++current;
      else
         throw gcnew ElementNotFoundException();
   }
};

// Add elements to the list and display them.
generic <typename ItemType>
void AddStringsAndDisplay(IList<ItemType>^ list, ItemType item1, ItemType item2) {
   list->Add(item1);
   list->Add(item2);
   for (list->MoveFirst(); ! list->AtEnd(); list->MoveNext())
   Console::WriteLine(list->Current());
}

int main() {
   // Instantiate both types of list.

   List1<String^>^ list1 = gcnew List1<String^>();
   List2<String^>^ list2 = gcnew List2<String^>();

   // Use the linked list implementation of IList.
   AddStringsAndDisplay<String^>(list1, "Linked List", "List1");

   // Use the array implementation of the IList.
   AddStringsAndDisplay<String^>(list2, "Array List", "List2");
}
```

```Output
Linked List
List1
Array List
List2
```

## <a name="example"></a>Örnek

Bu örnek, `IMyGenIface`özelleştirecek genel bir arabirim, `IMyGenIface`ve genel olmayan iki arabirim `IMySpecializedInt` ve `ImySpecializedString`bildirir. Bu iki özel arabirim daha sonra iki sınıf tarafından uygulanır, `MyIntClass` ve `MyStringClass`. Örnek, genel arabirimlerin nasıl özelleştirilecek, genel ve genel olmayan arabirimlerin nasıl oluşturulacağı ve arabirimlerde açıkça uygulanan üyelerin nasıl çağrılacağını gösterir.

```cpp
// generic_interface2.cpp
// compile with: /clr
// Specializing and implementing generic interfaces.
using namespace System;

generic <class ItemType>
public interface class IMyGenIface {
   void Initialize(ItemType f);
};

public interface class IMySpecializedInt: public IMyGenIface<int> {
   void Display();
};

public interface class IMySpecializedString: public IMyGenIface<String^> {
   void Display();
};

public ref class MyIntClass: public IMySpecializedInt {
   int myField;

public:
   virtual void Initialize(int f) {
      myField = f;
   }

   virtual void Display() {
      Console::WriteLine("The integer field contains: {0}", myField);
   }
};

public ref struct MyStringClass: IMySpecializedString {
   String^ myField;

public:
   virtual void Initialize(String^ f) {
      myField = f;
    }

   virtual void Display() {
      Console::WriteLine("The String field contains: {0}", myField);
   }
};

int main() {
   // Instantiate the generic interface.
   IMyGenIface<int>^ myIntObj = gcnew MyIntClass();

   // Instantiate the specialized interface "IMySpecializedInt."
   IMySpecializedInt^ mySpIntObj = (IMySpecializedInt^) myIntObj;

   // Instantiate the generic interface.
   IMyGenIface<String^>^ myStringObj = gcnew MyStringClass();

   // Instantiate the specialized interface "IMySpecializedString."
   IMySpecializedString^ mySpStringObj =
            (IMySpecializedString^) myStringObj;

   // Call the explicitly implemented interface members.
   myIntObj->Initialize(1234);
   mySpIntObj->Display();

   myStringObj->Initialize("My string");
   mySpStringObj->Display();
}
```

```Output
The integer field contains: 1234
The String field contains: My string
```

## <a name="see-also"></a>Ayrıca bkz.

[Genel Türler](generics-cpp-component-extensions.md)
