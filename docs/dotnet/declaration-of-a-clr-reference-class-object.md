---
title: "CLR başvuru sınıf nesnesi bildirimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- types [C++], reference types
- reference types, CLR
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 973500cc276d95e523859a5fcc1b9a5f7a707bb0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="declaration-of-a-clr-reference-class-object"></a>CLR Başvuru Sınıf Nesnesi Bildirimi
Bildirme ve başvuru sınıfı türünde bir nesne örneği sözdizimi için Visual C++ C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Yönetilen Uzantılar'da, isteğe bağlı bir kullanımı ile ISO-C++ işaretçi sözdizimini kullanarak bir başvuru sınıf türü nesnesi bildirilmiş `__gc` yıldız solundaki anahtar sözcüğü (`*`). Örneğin, sınıf türü nesnesi bildirimi Yönetilen Uzantılar sözdizimi altında çeşitli başvuru şunlardır:  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   Button __gc *button1;  
   DataGrid __gc *myDataGrid;     
   DataSet __gc *myDataSet;  
  
   void PrintValues( Array* myArr ) {  
      System::Collections::IEnumerator* myEnumerator =   
         myArr->GetEnumerator();  
  
      Array *localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);  
   }  
};  
```  
  
 Yeni sözdizimi altında bir başvuru sınıf türü nesnesi yeni bildirim belirteci kullanarak bildirme (`^`) resmi olarak adlandırılan bir *izleme işleyicisi* ve daha az resmi olarak bir *hat*. (İzleme gelen bir başvuru türü CLR yığınında bulunduğu ve bu nedenle konumları yığın sıkıştırma atık toplama sırasında saydam taşıyabilirsiniz anlamına gelir. İzleme işleyicisi saydam çalışma zamanı sırasında güncelleştirilir. İki benzer kavram olan *izleme başvurusu* (`%`) ve *iç işaretçi* (`interior_ptr<>`), ele [değer türü anlamları](../dotnet/value-type-semantics.md).  
  
 ISO-C++ işaretçi sözdizimi tekrar Tanımlayıcı Sözdizimi taşımak için en önemli nedenlerinden aşağıdaki gibidir:  
  
-   İşaretçi sözdizimi kullanımı için başvuru nesnesi doğrudan uygulanacak aşırı yüklenmiş işleçler izin vermez. Bunun yerine, bir iç adını kullanarak işleci çağırmak vardı `rV1->op_Addition(rV2)` daha sezgisel yerine `rV1+rV2`.  
  
-   Toplanan yığında atık depolanan nesneler için izin verilmiyor atama ve işaretçi aritmetiği, gibi işaretçi işlemlerinin sayısı. Daha iyi izleme işleyicisi kavramı CLR başvuru türü yapısını yakalar.  
  
 `__gc` İzleme işleyicisi değiştiricisi gereksizdir ve desteklenmiyor. Nesnesinin kullanımını değiştirilmez; hala işaretçi üye seçimi işlecinden üyeleri erişir (`->`). Örneğin, yeni sözdizimine çevrilmiş önceki Yönetilen Uzantılar kod örneği şöyledir:  
  
```  
public ref class Form1: public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container^ components;  
   Button^ button1;  
   DataGrid^ myDataGrid;  
   DataSet^ myDataSet;  
  
   void PrintValues( Array^ myArr ) {  
      System::Collections::IEnumerator^ myEnumerator =  
         myArr->GetEnumerator();  
  
      Array ^localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);   }  
};  
```  
  
## <a name="dynamic-allocation-of-an-object-on-the-clr-heap"></a>CLR yığınındaki nesnenin dinamik ayırma  
 Yönetilen Uzantılar, iki varlığını `new` ifadeleri yerel ve yönetilen yığın arasında ayırma için büyük ölçüde saydam. Neredeyse tüm örneklerde derleyici bağlamı yerel veya yönetilen yığınından bellek ayıramadı belirlemek için kullanabilirsiniz. Örneğin,  
  
```  
Button *button1 = new Button; // OK: managed heap  
int *pi1 = new int;           // OK: native heap  
Int32 *pi2 = new Int32;       // OK: managed heap  
```  
  
 Bağlamsal yığın ayırma istemediğinizde derleyicisi ile ya da yönlendirebilir `__gc` veya `__nogc` anahtar sözcüğü. Yeni sözdiziminde, iki yeni ifadeler ayrı yapısını sunumuyla açık hale `gcnew` anahtar sözcüğü. Örneğin, önceki üç bildirim yeni sözdiziminde aşağıdaki gibi görünür:  
  
```  
Button^ button1 = gcnew Button;        // OK: managed heap  
int * pi1 = new int;                   // OK: native heap  
Int32^ pi2 = gcnew Int32; // OK: managed heap  
```  
  
 Yönetilen Uzantılar başlatılması işte `Form1` üyeleri olarak bildirilen önceki bölümde:  
  
```  
void InitializeComponent() {  
   components = new System::ComponentModel::Container();  
   button1 = new System::Windows::Forms::Button();  
   myDataGrid = new DataGrid();  
  
   button1->Click +=   
      new System::EventHandler(this, &Form1::button1_Click);  
}  
```  
  
 Burada, yeni sözdizimine yeniden aynı başlatma verilmiştir. Hedefi olduğunda hat başvuru türünün gerekli olmadığını unutmayın bir `gcnew` ifade.  
  
```  
void InitializeComponent() {  
   components = gcnew System::ComponentModel::Container;  
   button1 = gcnew System::Windows::Forms::Button;  
   myDataGrid = gcnew DataGrid;  
  
   button1->Click +=   
      gcnew System::EventHandler( this, &Form1::button1_Click );  
}  
```  
  
## <a name="a-tracking-reference-to-no-object"></a>Bir izleme başvuru nesnesi yok  
 Yeni sözdiziminde `0` artık boş bir adresi temsil eder, ancak bir tamsayı olarak aynı kabul `1`, `10`, veya `100`. Yeni özel bir belirteç izleme başvurusu null değerini temsil eder. Örneğin, Yönetilen Uzantılar'nesnesi yok gibi adresi için bir başvuru türü şu başlatın:  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 Yeni sözdiziminde herhangi bir değer atanması veya başlatma türü için bir `Object` bu değer türü örtük olarak kutulama neden olur. Yeni sözdiziminde, her ikisi de `obj` ve `obj2` ele sırasıyla 0 ve 1 değerlerini tutan Kutulu Int32 nesnesine başlatılır. Örneğin:  
  
```  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
```  
  
 Bu nedenle, açık başlatma, atama ve izleme işleyicisi null karşılaştırma gerçekleştirmek için yeni bir anahtar sözcük kullanın `nullptr`.  Özgün örnek doğru sürümünü şu şekilde görünür:  
  
```  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to a Int32^  
Object ^ obj2 = 1;  
```  
  
 Bu biraz var olan kod yeni sözdizimine taşıma karmaşık hale getirir. Örneğin, aşağıdaki değer sınıf bildirimini göz önünde bulundurun:  
  
```  
__value struct Holder {  
   Holder( Continuation* c, Sexpr* v ) {  
      cont = c;  
      value = v;  
      args = 0;  
      env = 0;  
   }  
  
private:  
   Continuation* cont;  
   Sexpr * value;  
   Environment* env;  
   Sexpr * args __gc [];  
};  
```  
  
 Burada, her ikisi de `args` ve `env` CLR başvuru türüdür. Bu iki üyenin başlatma `0` oluşturucuda yeni sözdizimine geçişte değişmeden kalamaz. Bunun yerine, bunlar için değiştirilmelidir `nullptr`:  
  
```  
value struct Holder {  
   Holder( Continuation^ c, Sexpr^ v )  
   {  
      cont = c;  
      value = v;  
      args = nullptr;  
      env = nullptr;  
   }  
  
private:  
   Continuation^ cont;  
   Sexpr^ value;  
   Environment^ env;  
   array<Sexpr^>^ args;  
};  
```  
  
 Benzer şekilde, test için karşılaştırma bu üyeler karşı `0` üyelerine Karşılaştırılacak değiştirilmelidir `nullptr`. Yönetilen Uzantılar sözdizimi şöyledir:  
  
```  
Sexpr * Loop (Sexpr* input) {  
   value = 0;  
   Holder holder = Interpret(this, input, env);  
  
   while (holder.cont != 0) {  
      if (holder.env != 0) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != 0) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 Her değiştirerek düzeltme, işte `0` örneği bir `nullptr`. Dahil olmak üzere tüm oluşumlarını kullanımı değilse çoğunu otomatikleştirerek bu dönüşümünde çeviri aracı yardımcı `NULL` makrosu.  
  
```  
Sexpr ^ Loop (Sexpr^ input) {  
   value = nullptr;  
   Holder holder = Interpret(this, input, env);  
  
   while ( holder.cont != nullptr ) {  
      if ( holder.env != nullptr ) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != nullptr ) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 `nullptr` Herhangi bir işaretçiye veya izleme tanıtıcı dönüştürülür ancak bir tam sayı türüne yükseltilmez. Örneğin, kümesinde aşağıdaki başlatmaları, `nullptr` sadece ilk iki için bir başlangıç değeri geçerli değil.  
  
```  
// OK: we set obj and pstr to refer to no object  
Object^ obj = nullptr;  
char*   pstr = nullptr; // 0 would also work here  
  
// Error: no conversion of nullptr to 0  
int ival = nullptr;  
```  
  
 Benzer şekilde, aşırı yüklenmiş bir dizi yöntem aşağıdaki gibi verilir:  
  
```  
void f( Object^ ); // (1)  
void f( char* );   // (2)  
void f( int );     // (3)  
```  
  
 İle bir çağrı `nullptr` aşağıdaki gibi değişmez değer  
  
```  
// Error: ambiguous: matches (1) and (2)  
f(  nullptr );  
```  
  
 belirsiz olduğundan `nullptr` izleme işleyicisi ve bir işaretçi eşleşen ve tür diğer verilen tercih yoktur. (Bu durum belirsizliği ortadan kaldırmak için bir açık atama gerektirir.)  
  
 İle bir çağrı `0` tam olarak eşleşir (3):  
  
```  
// OK: matches (3)  
f( 0 );  
```  
  
 çünkü `0` integer türündedir. Olan `f(int)` yok, çağrı belirsizliğe eşleşir `f(char*)` standart dönüştürme aracılığıyla. Eşleştirme kuralları standart dönüştürme üzerine tam bir eşleşme öncelik verin. Tam bir eşleşme olmaması durumunda, standart dönüştürme bir değer türü üzerinden bir örtük kutulama öncelik verilir. Belirsizlik olmaz olmasının olmasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)   
 [Sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Nesne işleci (^) işleme](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)