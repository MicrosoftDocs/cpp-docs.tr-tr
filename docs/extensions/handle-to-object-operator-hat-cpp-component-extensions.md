---
title: İşlenecek Nesne İşleci (^) (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- ^ handle to object [C++]
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
ms.openlocfilehash: c8927ef0e34f2c2b12722d453e0dde6f7357eb33
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503140"
---
# <a name="handle-to-object-operator---ccli-and-ccx"></a>İşlenecek Nesne İşleci (^) (C++/CLI ve C++/CX)

*Tanıtıcı bildirimci* ( `^` , "hat"), tür [belirticisini](../cpp/declarations-and-definitions-cpp.md) , sistem nesnenin artık erişilebilir olmadığını belirlediğinde, belirtilen nesnenin otomatik olarak silinmesi gerektiği anlamına gelir.

## <a name="accessing-the-declared-object"></a>Belirtilen nesneye erişme

Tanıtıcı bildirimci ile tanımlanmış bir değişken, nesnesine bir işaretçi gibi davranır. Ancak, değişkeni nesnenin tamamına işaret eder, nesnenin bir üyesini işaret edemez ve işaretçi aritmetiğini desteklemez. Nesneye erişmek için yöneltme işlecini ( `*` ) ve `->` nesnenin üyesine erişmek için ok üye erişim işlecini () kullanın.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Derleyici, nesnenin artık kullanılmadığını ve silinemediğini anlamak için COM *başvuru sayma* mekanizmasını kullanır. Bu, Windows Çalışma Zamanı arabiriminden türetilen bir nesne gerçekten bir COM nesnesi olduğundan mümkündür. Başvuru sayısı, nesne oluşturulduğunda veya kopyalandığında artırılır ve nesne null ya da kapsam dışına geçtiğinde azaltılır. Başvuru sayısı sıfır olursa, nesne otomatik olarak ve hemen silinir.

Tanıtıcı bildirimcisinin avantajı, COM içinde, sıkıcı ve hataya açık bir işlem olan bir nesnenin başvuru sayısını açıkça yönetmeniz gerekir. Diğer bir deyişle, başvuru sayısını artırmak ve azaltmak için nesnenin AddRef () ve Release () yöntemlerini çağırmanız gerekir. Ancak, tanıtıcı bildirimci ile bir nesne bildirirseniz derleyici, başvuru sayısını otomatik olarak ayarlayan kodu oluşturur.

Bir nesnenin örneğini oluşturma hakkında daha fazla bilgi için bkz. [Yeni başvuru](ref-new-gcnew-cpp-component-extensions.md).

## <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Sistem, nesnenin artık kullanılmadığını ve silinemediğini anlamak için CLR *çöp toplayıcı* mekanizmasını kullanır. Ortak dil çalışma zamanı, nesneleri ayırdığı bir yığını korur ve programınızda bulunan nesnelerin konumunu belirtmek için programınızdaki yönetilen başvuruları (değişkenler) kullanır. Bir nesne artık kullanılmıyorsa, yığında kapladığı bellek serbest bırakılır. Düzenli olarak, çöp toplayıcı serbest bırakılan belleği daha iyi kullanmak için yığını sıkıştırır. Yığın sıkıştırılırken, yönetilen başvuruların başvurduğu konumları geçersiz kılan yığında nesneler öbek üzerinde taşınabilir. Ancak, çöp toplayıcı tüm yönetilen başvuruların konumunu algılar ve bunları yığındaki nesnelerin geçerli konumunu belirtecek şekilde otomatik olarak güncelleştirir.

Yerel C++ işaretçileri ( `*` ) ve başvuruları ( `&` ) yönetilen başvurular olmadığından, çöp toplayıcı işaret ettikleri adresleri otomatik olarak güncelleştiremez. Bu sorunu çözmek için, çöp toplayıcısının farkında olduğu ve otomatik olarak güncelleştirebildiği bir değişken belirtmek için tanıtıcı bildirimci ' i kullanın.

Daha fazla bilgi için bkz. [nasıl yapılır: yerel türlerde Işleyicileri bildirme](../dotnet/how-to-declare-handles-in-native-types.md).

### <a name="examples"></a>Örnekler

Bu örnek, yönetilen yığında bir başvuru türü örneğinin nasıl oluşturulacağını gösterir.  Bu örnek ayrıca, bir tanıtıcıyı başka bir tanıtıcı başlatabilir ve bu, yönetilen, atık toplanmış yığında aynı nesneye iki başvuru oluşmasına neden olur. Bir tanıtıcıya [nullptr](nullptr-cpp-component-extensions.md) atamanın, çöp toplama için nesneyi işaretlemediğine dikkat edin.

```cpp
// mcppv2_handle.cpp
// compile with: /clr
ref class MyClass {
public:
   MyClass() : i(){}
   int i;
   void Test() {
      i++;
      System::Console::WriteLine(i);
   }
};

int main() {
   MyClass ^ p_MyClass = gcnew MyClass;
   p_MyClass->Test();

   MyClass ^ p_MyClass2;
   p_MyClass2 = p_MyClass;

   p_MyClass = nullptr;
   p_MyClass2->Test();
}
```

```Output
1
2
```

Aşağıdaki örnek, bir nesnenin türünün paketlenmiş bir değer türü olduğu yönetilen yığında bir nesne için nasıl bir tanıtıcı bildirimi yapıldığını gösterir. Örnek ayrıca kutulanmış nesneden değer türünün nasıl alınacağını gösterir.

```cpp
// mcppv2_handle_2.cpp
// compile with: /clr
using namespace System;

void Test(Object^ o) {
   Int32^ i = dynamic_cast<Int32^>(o);

   if(i)
      Console::WriteLine(i);
   else
      Console::WriteLine("Not a boxed int");
}

int main() {
   String^ str = "test";
   Test(str);

   int n = 100;
   Test(n);
}
```

```Output
Not a boxed int
100
```

Bu örnek **`void*`** , rastgele bir nesneyi işaret etmek için bir işaretçi kullanmanın ortak C++ deyim sayısının `Object^` , herhangi bir başvuru sınıfına yönelik bir tanıtıcı tutan, tarafından değiştirildiğini gösterir. Ayrıca, diziler ve temsilciler gibi tüm türlerin bir nesne tanıtıcısına dönüştürülebileceğini gösterir.

```cpp
// mcppv2_handle_3.cpp
// compile with: /clr
using namespace System;
using namespace System::Collections;
public delegate void MyDel();
ref class MyClass {
public:
   void Test() {}
};

void Test(Object ^ x) {
   Console::WriteLine("Type is {0}", x->GetType());
}

int main() {
   // handle to Object can hold any ref type
   Object ^ h_MyClass = gcnew MyClass;

   ArrayList ^ arr = gcnew ArrayList();
   arr->Add(gcnew MyClass);

   h_MyClass = dynamic_cast<MyClass ^>(arr[0]);
   Test(arr);

   Int32 ^ bi = 1;
   Test(bi);

   MyClass ^ h_MyClass2 = gcnew MyClass;

   MyDel^ DelInst = gcnew MyDel(h_MyClass2, &MyClass::Test);
   Test(DelInst);
}
```

```Output
Type is System.Collections.ArrayList

Type is System.Int32

Type is MyDel
```

Bu örnek, bir tanıtıcının başvurulduğunu ve bir üyeye başvurusu kaldırılmış bir tanıtıcı aracılığıyla erişilebilir olduğunu gösterir.

```cpp
// mcppv2_handle_4.cpp
// compile with: /clr
using namespace System;
value struct DataCollection {
private:
   int Size;
   array<String^>^ x;

public:
   DataCollection(int i) : Size(i) {
      x = gcnew array<String^>(Size);
      for (int i = 0 ; i < Size ; i++)
         x[i] = i.ToString();
   }

   void f(int Item) {
      if (Item >= Size)
      {
         System::Console::WriteLine("Cannot access array element {0}, size is {1}", Item, Size);
         return;
      }
      else
         System::Console::WriteLine("Array value: {0}", x[Item]);
   }
};

void f(DataCollection y, int Item) {
   y.f(Item);
}

int main() {
   DataCollection ^ a = gcnew DataCollection(10);
   f(*a, 7);   // dereference a handle, return handle's object
   (*a).f(11);   // access member via dereferenced handle
}
```

```Output
Array value: 7

Cannot access array element 11, size is 10
```

Bu örnek, yerel bir başvurunun ( `&` ) **`int`** yönetilen bir türün üyesine bağlanamaz, çünkü **`int`** atık toplanan yığında depolanabilir ve yerel başvurular yönetilen yığında nesne hareketini izlemez. Bu, yerel bir değişken kullanmak veya `&` olarak değiştirmek `%` , bir izleme başvurusu yapmak için kullanılır.

```cpp
// mcppv2_handle_5.cpp
// compile with: /clr
ref struct A {
   void Test(unsigned int &){}
   void Test2(unsigned int %){}
   unsigned int i;
};

int main() {
   A a;
   a.i = 9;
   a.Test(a.i);   // C2664
   a.Test2(a.i);   // OK

   unsigned int j = 0;
   a.Test(j);   // OK
}
```

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)<br/>
[İzleme başvurusu Işleci](tracking-reference-operator-cpp-component-extensions.md)
