---
title: Tanıtıcı nesne işleci (^) (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- ^ handle to object [C++]
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
ms.openlocfilehash: 6f61a6b95ba8f9a059606376696fd1d8d64030db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625738"
---
# <a name="handle-to-object-operator---ccli-and-ccx"></a>Tanıtıcı nesne işleci (^) (C + +/ CLI ve C + +/ CX)

*Tanıtıcı Bildiricisi* (`^`, "hat" olarak okunur), tür [belirticisi](../cpp/overview-of-declarators.md) sistem bir nesne olduğunu belirlediğinde, bildirilen nesnenin otomatik olarak silinmesi gerektiğini ifade etmek için artık erişilebilir.

## <a name="accessing-the-declared-object"></a>Bildirilen nesneye erişim

Tanıtıcı Bildiricisi ile bildirilen bir değişken, nesne işaretçisi gibi davranır. Ancak, değişken tüm nesneyi işaret nesnenin bir üyesine işaret edemez ve işaretçi aritmetiğini desteklemez. Yönlendirme işlecini kullanın (`*`) nesne ve ok üye erişimi işleci (`->`) nesnenin bir üyesine erişmek için.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Derleyici COM kullanan *başvuru sayımı* nesnenin artık kullanılıp kullanılmadığını ve silinebileceğini belirlemek için bir mekanizma. Bir Windows çalışma zamanı arabiriminden elde edilen nesnenin aslında bir COM nesnesi olduğundan, bu mümkündür. Nesne oluşturulan veya kopyalanan ya da azaltılmasına olduğunda nesnesi null ya da gelecek ayarlandığında başvuru sayısının artırılması kapsamı dışındadır. Başvuru sayısı sıfır olursa, nesne otomatik olarak ve hemen silinir.

Tanıtıcı bildiricisinin yararı COM, açıkça sıkıcı ve hata yapmaya açık bir işlem bir nesne başvuru sayımını yönetmenizin gerekli olmasıdır. Diğer bir deyişle başvuru sayısını artırmak için nesnenin AddRef() ve Release() yöntemlerini çağırmanız gerekir. Bununla birlikte tutamaç Bildiricisi olan bir nesne bildirirseniz, derleyici başvuru sayısını otomatik olarak ayarlayan kodu oluşturur.

Bir nesnenin örneğini hakkında daha fazla bilgi için bkz. [yeni başvuru](../windows/ref-new-gcnew-cpp-component-extensions.md).

## <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

CLR sisteminin kullandığı *çöp toplayıcı* nesnenin artık kullanılıp kullanılmadığını ve silinebileceğini belirlemek için bir mekanizma. Ortak dil çalışma zamanı nesneleri ayırdığı bir yığını korur ve yığındaki nesnelerin konumunu programınızdaki kullanan yönetilen başvuruları (değişken) belirtin. Bir nesne artık kullanılmadığında yığın üzerinde kapladığı bellek serbest bırakılır. Düzenli olarak, atık toplayıcı, Boşaltılan belleği daha iyi kullanmak için yığın sıkıştırır. Yığın sıkıştırma yönetilen başvurular tarafından başvurulan konumları geçersiz kılan yığın üzerindeki nesnelerin taşıyabilirsiniz. Bununla birlikte, çöp toplayıcı yönetilen tüm başvuruların konumunu farkındadır ve yığındaki nesnelerin geçerli konumunu göstermek için bunları otomatik olarak güncelleştirir.

Çünkü yerel C++ işaretçileri (`*`) ve başvuruları (`&`) yönetilen başvurular olmadığından çöp toplayıcı bunların işaret ettiği adresleri otomatik olarak güncelleştirilemiyor. Bu sorunu çözmek için tanıtıcı bildiricisinin çöp toplayıcı farkında olan bir değişken belirtmek için kullanın ve otomatik olarak güncelleştirebilirsiniz.

Daha fazla bilgi için [nasıl yapılır: yerel türlerde bildirimini işleme](../dotnet/how-to-declare-handles-in-native-types.md).

### <a name="examples"></a>Örnekler

Bu örnek yönetilen yığında başvuru türünün örneğini oluşturma işlemini gösterir.  Ayrıca bu örnek yönetilen, atık toplama yığınındaki aynı nesneye iki başvuru sonuçta bir tanıtıcıyı bir diğeriyle başlatabilirsiniz gösterir. İşaretlemediğine dikkat edin [nullptr](../windows/nullptr-cpp-component-extensions.md) için bir tanıtıcı çöp toplama için nesneyi işaretlemez.

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

Aşağıdaki örnek, kutulanmış bir değer türü nesne türü olduğu yönetilen yığındaki bir nesne için bir tanıtıcı bildirmek gösterilmektedir. Örnek ayrıca kutulanmış nesneden değer türünün nasıl gösterir.

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

Bu örnek, kullanmanın yaygın C++ deyim gösterir bir `void*` rastgele bir nesneye işaret edecek şekilde işaretçi tarafından değiştirilir `Object^`, hangi tutabilir bir tanıtıcı her başvuru sınıfı için. Ayrıca, diziler ve temsilciler gibi tüm türleri bir nesne tanıtıcısına dönüştürülebildiğini de gösterir.

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

Bu örnek, bir tanıtıcı başvurusunun nasıl kaldırılacağını olduğunu ve üye tanıtıcıyla erişilebilir olduğunu gösterir.

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

Bu örnek, yerel bir başvurunun (`&`) öğesine bağlanamaz bir **int** bir yönetilen türün üye olarak **int** atık toplanan yığında depolanmış olabilir ve yerel başvurular izlemez Yönetilen yığın içindeki nesne hareketini. Yerel bir değişken kullanılmalı veya değiştirmek için düzeltmesidir `&` için `%`, bir izleme başvurusu yapılmalıdır.

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

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP İçin Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)<br/>
[İzleme başvurusu işleci](../windows/tracking-reference-operator-cpp-component-extensions.md)
