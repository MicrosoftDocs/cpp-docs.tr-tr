---
title: CLR başvuru sınıf nesnesi bildirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- types [C++], reference types
- reference types, CLR
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f3e8ec6407e12d0c26331d45dc1659277feed016
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444586"
---
# <a name="declaration-of-a-clr-reference-class-object"></a>CLR Başvuru Sınıf Nesnesi Bildirimi

Bildirme ve başvuru sınıfı türü bir nesne oluşturmak için sözdizimi, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

Yönetilen Uzantılar'başvuru sınıfı türü nesnesi ile isteğe bağlı bir kullanımı ISO-C++ işaretçisi sözdizimi kullanılarak bildirilen `__gc` sol tarafındaki yıldız anahtar sözcüğü (`*`). Örneğin, sınıf türü nesne bildirimleri altında yönetilen uzantıları söz dizimi başvurusu çeşitli şunlardır:

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

Yeni sözdiziminde, bir başvuru sınıfı türü yeni bir bildirim temelli belirteç kullanarak nesne bildirme (`^`) resmi olarak adlandırılan bir *izleme işleyicisi* ve daha basit olarak bir *hat*. (İzleme sıfat bir başvuru türü CLR yığında yer alan ve bu nedenle konumları yığın sıkıştırma atık toplama sırasında saydam bir şekilde taşıyabilirsiniz anlamına gelir. İzleme işleyicisi, çalışma zamanı sırasında saydam bir şekilde güncelleştirilir. İki benzer kavramlardır *yönelik izleme başvurusuna* (`%`) ve *işaretçiye* (`interior_ptr<>`), ele [değer türü anlamları](../dotnet/value-type-semantics.md).

Bildirim temelli söz dizimi ISO-C++ işaretçi sözdizimi tekrar taşımak için en önemli nedenlerinden aşağıdaki gibidir:

- Başvuru nesnesine doğrudan uygulanması için aşırı yüklenmiş işleçler işaretçi sözdizimi kullanılmasına izin vermez. Bunun yerine, kendi iç adı gibi kullanarak işlecini çağırmak bir sahip `rV1->op_Addition(rV2)` daha sezgisel yerine `rV1+rV2`.

- Toplanan yığında atık depolanan nesneler için izin verilmez, atama ve işaretçi aritmetiğini, gibi işaretçi işlemleri sayısı. CLR başvuru türünün yapısını daha iyi izleme işleyicisi kavramı yakalar.

`__gc` İzleme işleyicisi değiştiricisi gereksizdir ve desteklenmiyor. Nesne kullanımını değiştirilmedi; yine de işaretçi üye seçme işlecinden üyeleri erişir (`->`). Örneğin, yeni sözdizimine çevrilmiş önceki Yönetilen Uzantılar kod örneği aşağıdadır:

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

## <a name="dynamic-allocation-of-an-object-on-the-clr-heap"></a>CLR yığındaki bir nesnenin dinamik ayırma

Yönetilen Uzantılar, iki varlığını `new` arasında yerel ve yönetilen yığın ayrılacak ifadeleri neredeyse şeffaftır. Hemen hemen tüm durumlarda, derleyicinin bağlam, yerel veya yönetilen yığından bellek ayırmak belirlemek için kullanabilirsiniz. Örneğin,

```
Button *button1 = new Button; // OK: managed heap
int *pi1 = new int;           // OK: native heap
Int32 *pi2 = new Int32;       // OK: managed heap
```

Bağlamsal yığın ayırma istemediğinizde, derleyici ile ya da yönlendirebilir `__gc` veya `__nogc` anahtar sözcüğü. Yeni sözdiziminde, iki yeni ifade ayrı yapısını sunulmasıyla birlikte açık hale `gcnew` anahtar sözcüğü. Örneğin, önceki üç bildirimleri gibi yeni sözdiziminde görünür:

```
Button^ button1 = gcnew Button;        // OK: managed heap
int * pi1 = new int;                   // OK: native heap
Int32^ pi2 = gcnew Int32; // OK: managed heap
```

Yönetilen Uzantılar başlatma işte `Form1` üyeleri bildirilen önceki bölümde:

```
void InitializeComponent() {
   components = new System::ComponentModel::Container();
   button1 = new System::Windows::Forms::Button();
   myDataGrid = new DataGrid();

   button1->Click +=
      new System::EventHandler(this, &Form1::button1_Click);
}
```

Aynı başlatma yeni sözdizimine dönüştürülmüş hali aşağıdadır. Hedefi olduğunda hat başvuru türünün gerekli olmadığını unutmayın bir `gcnew` ifade.

```
void InitializeComponent() {
   components = gcnew System::ComponentModel::Container;
   button1 = gcnew System::Windows::Forms::Button;
   myDataGrid = gcnew DataGrid;

   button1->Click +=
      gcnew System::EventHandler( this, &Form1::button1_Click );
}
```

## <a name="a-tracking-reference-to-no-object"></a>Bir nesne için izleme başvurusu

Yeni sözdiziminde `0` artık boş bir adresi temsil eder, ancak bir tamsayı, aynı olarak kabul edilir `1`, `10`, veya `100`. Yeni özel bir belirteç bir izleme başvurusuna null değerini temsil eder. Örneğin, Yönetilen Uzantılar'nesnesi yok gibi ele almak için bir başvuru türü biz başlatın:

```
// OK: we set obj to refer to no object
Object * obj = 0;

// Error: no implicit boxing
Object * obj2 = 1;
```

Yeni sözdiziminde, herhangi bir başlatma veya değer türü için bir `Object` o değer türü örtük olarak kutulama neden olur. Yeni sözdiziminde, her ikisi de `obj` ve `obj2` ele için 0 ve 1 değerlerini sırasıyla tutan paketlenmiş Int32 nesneleri başlatılır. Örneğin:

```
// causes the implicit boxing of both 0 and 1
Object ^ obj = 0;
Object ^ obj2 = 1;
```

Bu nedenle, açık başlatma, atama ve izleme işleyicisi null karşılaştırma gerçekleştirmek için yeni bir anahtar sözcüğünü kullanın. `nullptr`.  Doğru düzeltilmesi özgün örnek şu şekilde görünür:

```
// OK: we set obj to refer to no object
Object ^ obj = nullptr;

// OK: we initialize obj2 to a Int32^
Object ^ obj2 = 1;
```

Bu biraz var olan kod yeni söz dizimini taşıma karmaşık hale getirir. Örneğin, aşağıdaki değer sınıfı bildirimi göz önünde bulundurun:

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

Burada, her ikisi de `args` ve `env` CLR başvuru türleridir. Bu iki üyenin başlatılması `0` oluşturucuda yeni söz dizimini geçişte değişmeden kalamaz. Bunun yerine, bunlar için değiştirilmelidir `nullptr`:

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

Benzer şekilde, test için karşılaştırma bu üyelere karşı `0` üyelerine Karşılaştırılacak değiştirilmelidir `nullptr`. Yönetilen Uzantıları söz dizimi şu şekildedir:

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

Her değiştirerek düzeltme işte `0` ile örnek bir `nullptr`. Kullanım dahil olmak üzere tüm oluşumları değilse çeviri aracı, çoğu otomatik hale getirerek bu dönüşümünde yardımcı olur `NULL` makrosu.

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

`nullptr` Herhangi bir işaretçi ya da izleme tanıtıcı dönüştürülür ancak bir integral türe yükseltilmez. Örneğin, aşağıdaki başlatmalar, kümesi içinde `nullptr` yalnızca ilk iki için bir başlangıç değeri olarak geçerlidir.

```
// OK: we set obj and pstr to refer to no object
Object^ obj = nullptr;
char*   pstr = nullptr; // 0 would also work here

// Error: no conversion of nullptr to 0
int ival = nullptr;
```

Benzer şekilde, aşağıdaki gibi yöntemler aşırı yüklenmiş bir dizi verilen:

```
void f( Object^ ); // (1)
void f( char* );   // (2)
void f( int );     // (3)
```

Bir çağrı ile `nullptr` aşağıdaki gibi değişmez değeri

```
// Error: ambiguous: matches (1) and (2)
f(  nullptr );
```

belirsiz olduğundan `nullptr` izleme işleyicisi hem bir işaretçi ile eşleşen ve bir tür diğer verilen tercih yoktur. (Bu durumda ayırt etmek için bir açık tür dönüştürme gerektiriyor.)

Bir çağrı ile `0` tam olarak eşleşir (3):

```
// OK: matches (3)
f( 0 );
```

çünkü `0` integer türündedir. Olan `f(int)` yok, çağrı dönüştürmelerle BC `f(char*)` aracılığıyla standart bir dönüştürme. Eşleştirme kuralları tam bir eşleşme önceliğini standart bir dönüştürme sağlar. Tam bir eşleşme olmaması durumunda, standart bir dönüştürme, bir örtük olarak kutulama bir değer türü üzerinde öncelik verilir. Belirsizlik olmaz olmasının olmasıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[İşlenecek nesne işleci (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)<br/>
[nullptr](../windows/nullptr-cpp-component-extensions.md)