---
title: "Tanıtıcı nesne işleci (^) (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: ^ handle to object [C++]
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e760181f48e4bfd197514b152701e94ac6e94a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="handle-to-object-operator---c-component-extensions"></a>İşlenecek Nesne İşleci (^) (C++ Bileşen Uzantıları)
*Bildirimcisi işlemek* (`^`, "hat" denilir), türü değiştirir [belirticisi](../cpp/overview-of-declarators.md) sistemi nesnenin olduğunu belirlediğinde, bildirilen nesnesi'nin otomatik olarak silinmesini anlamına gelir artık erişilebilir.  
  
## <a name="accessing-the-declared-object"></a>Bildirilen nesne erişme  
 Tanıtıcı bildirimcisi ile bildirilmiş bir değişken nesnesine bir işaretçi gibi davranır. Ancak, nesnenin tamamı değişken noktalarına nesne üyesine noktası olamaz ve işaretçi aritmetiği desteklemiyor. İndirection işleci kullanın (`*`) nesne ve ok üye erişimi işleci erişmek için (`->`) nesne üyesi erişmek için.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Derleyici COM kullanan *başvuru sayımı* nesne artık kullanılıyor ve silinebilir belirlemek için bir mekanizma. Windows çalışma zamanı arabiriminden türetilmiş bir nesne gerçekte bir COM nesnesi olduğundan, bu mümkündür. Nesne oluşturulan veya kopyalanan ve indirildiği olduğunda nesne null ya da gider olarak ayarlandığında, başvuru sayısı artırılır kapsam dışında. Başvuru sayısı sıfır olarak kalırsa, nesne otomatik olarak ve hemen silinir.  
  
 COM'da açıkça yorucu ve hata potansiyeli işlemi olan bir nesne için başvuru sayısı yönettiğiniz gerekir tanıtıcı bildirimcisi avantajlarından birisidir. Diğer bir deyişle, artırmak ve başvuru sayısı azaltma nesnenin AddRef() ve Release() yöntemlerini çağırmalıdır. Ancak, bir nesne ile tanıtıcı bildirimcisi bildirirseniz Visual C++ derleyici otomatik olarak başvuru sayısı ayarlar kod oluşturur.  
  
 Bir nesne örneği hakkında daha fazla bilgi için bkz: [ref yeni](../windows/ref-new-gcnew-cpp-component-extensions.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 CLR sistem kullanır *atık toplayıcı* nesne artık kullanılıyor ve silinebilir belirlemek için bir mekanizma. Ortak dil çalışma zamanı bu nesneleri ayırır yığın tutar ve programınızdaki kullanır yönetilen başvuru (değişkenler) nesneleri yığında konumunu belirtin. Bir nesne artık kullanıldığında, öbek üzerinde dolu belleği serbest bırakılır. Düzenli aralıklarla, atık toplayıcı daha iyi kullanımı için yığın bırakılmış belleğe sıkıştırır. Öbek sıkıştırılmasını nesneleri konumları refered tarafından yönetilen başvuru geçersiz kılar yığında taşıyabilirsiniz. Ancak, atık toplayıcı tüm yönetilen başvuruları konumunu farkındadır ve bunları yığında nesnelerin geçerli konumu belirtmek için otomatik olarak güncelleştirir.  
  
 Çünkü yerel C++ işaretçiler (`*`) ve başvurular (`&`) yönetilen başvuru olmayan atık toplayıcı işaret edecek şekilde adresleri otomatik olarak güncelleştirilemiyor. Bu sorunu çözmek için tanıtıcı bildirimcisi atık toplayıcı farkında olan bir değişken belirtmek için kullanın ve otomatik olarak güncelleştirebilir.  
  
 Visual C++ 2002 ve Visual C++ 2003 ' te `__gc *` nesneyi yönetilen yığında bildirmek için kullanılır.  `^` Değiştirir `__gc *` yeni sözdiziminde.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: yerel türlerde bildirimini işleme](../dotnet/how-to-declare-handles-in-native-types.md).  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Bu örnek yönetilen yığında başvuru türünde bir örnek oluşturulacağını gösterir.  Bu örnek ayrıca bir tanıtıcı başka ile yönetilen, atık toplanan yığında aynı nesne iki başvurular sonuçta başlatabilir gösterir. Bu atama fark [nullptr](../windows/nullptr-cpp-component-extensions.md) için bir tanıtıcı nesne çöp toplama için işaretlemez.  
  
```  
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
  
 **Output**  
  
```Output  
1  
2  
```  
  
 **Örnek**  
  
 Aşağıdaki örnek, bir nesne için bir tanıtıcı nesnesinin türü bir paketlenmiş değer türü olduğu yönetilen yığında bildirme gösterilmektedir. Örnek değer türü Kutulu nesnesinden alma da gösterir.  
  
```  
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
  
 **Output**  
  
```Output  
Not a boxed int  
100  
```  
  
 **Örnek**  
  
 Bu örnek, void * işaretçi rasgele bir nesneye işaret edecek şekilde kullanma ortak C++ deyim nesnesi tarafından değiştirilir göstermektedir ^, hangi tutun tanıtıcı herhangi bir başvuru sınıf. Diziler ve temsilciler gibi tüm türler için bir nesne tanıtıcı dönüştürülebilir gösterir.  
  
```  
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
  
 **Output**  
  
```Output  
Type is System.Collections.ArrayList  
  
Type is System.Int32  
  
Type is MyDel  
```  
  
 **Örnek**  
  
 Bu örnek bir tanıtıcı başvuru yapıldı ve bir üyeye dereferenced tanıtıcı erişilebilir göstermektedir.  
  
```  
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
  
 **Output**  
  
```Output  
Array value: 7  
  
Cannot access array element 11, size is 10  
```  
  
 **Örnek**  
  
 Bu örnek, yerel bir başvuru gösterir (`&`) bağlanılamıyor bir `int` bir yönetilen türü üyesi olarak `int` çöp toplanan yığınında depolanabilir ve yerel başvuruları Yönetilen yığın nesnesi hareket izleme yok. Yerel bir değişken kullanmanız veya değiştirmek için durumda düzeltme `&` için `%`, bir izleme başvuru yapma.  
  
```  
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
 Derleyici seçeneği:   **/CLR**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)   
 [İzleme başvurusu işleci](../windows/tracking-reference-operator-cpp-component-extensions.md)