---
title: İşlenecek Nesne İşleci (^) (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- ^ handle to object [C++]
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
ms.openlocfilehash: 3d08b2294da1599282feeb1739331c31d64a9e59
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358325"
---
# <a name="handle-to-object-operator---ccli-and-ccx"></a>İşlenecek Nesne İşleci (^) (C++/CLI ve C++/CX)

*Tutamaç bildirimcisi* `^`( , "şapka" olarak telaffuz edilir), sistem nesnenin artık erişilemeyecegini belirlerken bildirilen nesnenin otomatik olarak silinmesi anlamına gelen tür [belirteçini](../cpp/overview-of-declarators.md) değiştirir.

## <a name="accessing-the-declared-object"></a>Bildirilen Nesneye Erişim

Tutamaç bildirimcisi ile bildirilen bir değişken nesneye işaretçi gibi bakar. Ancak, değişken tüm nesneye işaret eder, nesnenin bir üyesini işaret edemez ve işaretçi aritmetik desteklemez. Nesneye erişmek için`*`yön verme işleci () ve nesnenin bir üyesine erişmek için ok üye erişim işleci ()`->`kullanın.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Derleyici, nesnenin artık kullanılıp kullanılılıp kullanılmamadığını ve silinip silinemeyediğini belirlemek için COM *referans sayım* mekanizmasını kullanır. Windows Runtime arabiriminden türetilen bir nesne aslında bir COM nesnesi olduğundan bu mümkündür. Nesne oluşturulduğunda veya kopyalandığında başvuru sayısı artar ve nesne null olarak ayarlandığında veya kapsam dışına çıktığında verilir. Başvuru sayısı sıfıra giderse, nesne otomatik olarak ve hemen silinir.

Tanıtıcının avantajı, COM'da sıkıcı ve hataya açık bir işlem olan bir nesnenin başvuru sayısını açıkça yönetmeniz olmasıdır. Diğer bir deyişle, başvuru sayısını artım ve karara eklemek için nesnenin AddRef() ve Release() yöntemlerini aramanız gerekir. Ancak, tutamaç bildirimcisi olan bir nesneyi bildirirseniz, derleyici başvuru sayısını otomatik olarak ayarlayan kod oluşturur.

Bir nesneyi anlık olarak nasıl anons edineceğime ilişkin bilgi için [ref new'e](ref-new-gcnew-cpp-component-extensions.md)bakın.

## <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Sistem, nesnenin artık kullanılıp kullanılılıp kullanılamadığını ve silinip silinemeyediğini belirlemek için CLR *çöp toplayıcı* mekanizmasını kullanır. Ortak dil çalışma süresi, nesneleri ayırdığı bir yığın tutar ve programınızda yönetilen başvuruları (değişkenler) kullanır ve yığındaki nesnelerin konumunu gösterir. Bir nesne artık kullanılmadığında, yığında kapaldığı bellek serbest bırakılır. Çöp toplayıcı, serbest bırakılan belleği daha iyi kullanmak için yığını düzenli aralıklarla sıkıştırıyor. Yığın sıkıştırma, yönetilen başvurular tarafından başvurulan konumları geçersiz kılınan yığınları üzerinde nesneleri taşıyabilir. Ancak, çöp toplayıcı tüm yönetilen başvuruların konumunun farkındadır ve yığındaki nesnelerin geçerli konumunu belirtmek için bunları otomatik olarak güncelleştirir.

Yerel C++ işaretçileri (`*``&`) ve başvurular ( ) yönetilen başvurular olmadığından, çöp toplayıcı işaret ettikleri adresleri otomatik olarak güncelleştiremez. Bu sorunu çözmek için, çöp toplayıcısının farkında olduğu ve otomatik olarak güncelleştirebileceği bir değişken belirtmek için tutamaç bildirimini kullanın.

Daha fazla bilgi için [bkz: Yerel Türlerde Tanıtıcıları Nasıl Bildirin.](../dotnet/how-to-declare-handles-in-native-types.md)

### <a name="examples"></a>Örnekler

Bu örnek, yönetilen yığında bir başvuru türünün örneğinin nasıl oluşturulacağını gösterir.  Bu örnek ayrıca, yönetilen, çöp toplanmış yığında aynı nesneye iki başvuru yla sonuçlanan bir tutamacı başka bir işlemle başolarak açabileceğinizi de gösterir. Bir tanıtıcıya [nullptr](nullptr-cpp-component-extensions.md) atamanın çöp toplama nesnesini işaretlemediğini unutmayın.

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

Aşağıdaki örnek, nesne türünün kutulanmış bir değer türü olduğu yönetilen yığındaki bir nesneye tanıtıcının nasıl bildireceğini gösterir. Örnek, kutulu nesneden değer türünü nasıl alacağını da gösterir.

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

Bu örnek, rasgele bir nesneyi işaret `void*` etmek için işaretçi kullanmanın ortak `Object^`C++ deyiminin, herhangi bir başvuru sınıfına tutamacı tutabilen bir sözcük ile değiştirilmeye başvurulduğunu gösterir. Ayrıca, diziler ve temsilciler gibi tüm türlerin nesne tanıtıcısına dönüştürülebileceğini de gösterir.

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

Bu örnek, bir tanıtıcının referanstan arındırılmış olabileceğini ve bir üyeye dereferenced tutamacı aracılığıyla erişilebileni gösterir.

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

Bu örnek, yerel bir`&`başvurunun yönetilen bir türün **int** üyesine bağlanamayabileceğini, çünkü **int'in** toplanan çöp yığınında depolanabileceğini ve yerel başvuruların yönetilen yığındaki nesne hareketini izlemediğini gösterir. Düzeltme, yerel bir değişken kullanmak veya `&` `%`onu izleme başvurusu yapmak olarak değiştirmektir.

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

Derleyici seçeneği:`/clr`

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)<br/>
[İzleme Başvurusu İşleci](tracking-reference-operator-cpp-component-extensions.md)
