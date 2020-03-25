---
title: new İşleci (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
ms.openlocfilehash: 21e67f8d44673a15e5d3a5994597caae4cc01a2e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161132"
---
# <a name="new-operator-c"></a>new İşleci (C++)

Boş depodan bir nesne veya türündeki nesne dizisi için bellek ayırır ve nesneye uygun şekilde, sıfır *olmayan* bir işaretçi döndürür.

> [!NOTE]
>  Microsoft C++ Component Extensions, vtable yuva girdileri eklemek için **Yeni** anahtar sözcük için destek sağlar. Daha fazla bilgi için bkz. [Yeni (vtable 'da yeni yuva)](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

## <a name="syntax"></a>Sözdizimi

```
[::] new [placement] new-type-name [new-initializer]
[::] new [placement] ( type-name ) [new-initializer]
```

## <a name="remarks"></a>Açıklamalar

Başarısız olursa, **Yeni** sıfır döndürür veya bir özel durum oluşturur; daha fazla bilgi için bkz. [New ve delete işleçleri](../cpp/new-and-delete-operators.md) . Özel bir özel durum işleme yordamı yazarak ve bağımsız değişkeni olarak işlev adınızla [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) çalışma zamanı kitaplığı işlevini çağırarak, bu varsayılan davranışı değiştirebilirsiniz.

Yönetilen yığında bir nesne oluşturma hakkında daha fazla bilgi için bkz. [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md).

Bir **new** C++ sınıf nesnesi için bellek ayırmak üzere yeni kullanıldığında, bellek ayrıldıktan sonra nesnenin Oluşturucusu çağrılır.

**Yeni** işleçle ayrılan belleği serbest bırakmak için [Delete](../cpp/delete-operator-cpp.md) işlecini kullanın.

Aşağıdaki örnek, `dim` boyutlu bir karakter dizisini 10 ' a ayırarak ayırır ve serbest bırakır. Çok boyutlu bir dizi ayrılırken, ilki hariç tüm boyutlar pozitif değerler değerlendiren sabit deyimler olmalıdır; en soldaki dizi boyutu pozitif bir değer değerlendirilen herhangi bir ifade olabilir. **New** işlecini kullanarak bir dizi ayrılırken, ilk boyut sıfır olabilir — **New** işleci benzersiz bir işaretçi döndürür.

```cpp
char (*pchar)[10] = new char[dim][10];
delete [] pchar;
```

*Tür adı* **const**, **volatile**, Class bildirimleri veya Enumeration bildirimleri içeremez. Bu nedenle, aşağıdaki ifade geçersizdir:

```cpp
volatile char *vch = new volatile char[20];
```

**Yeni** işleç, nesne olmadıkları için başvuru türleri ayırmıyor.

**New** işleci bir işlev ayırmak için kullanılamaz, ancak işlevlere işaretçiler ayırmak için kullanılabilir. Aşağıdaki örnek, tamsayılar döndüren işlevlere yedi işaretçilerin bir dizisini ayırır ve serbest bırakır.

```cpp
int (**p) () = new (int (*[7]) ());
delete *p;
```

**Yeni** işleci ek bağımsız değişkenler olmadan kullanırsanız ve [/GX](../build/reference/gx-enable-exception-handling.md), [/EHa](../build/reference/eh-exception-handling-model.md)veya [/EHS](../build/reference/eh-exception-handling-model.md) seçeneğiyle derlerseniz, Oluşturucu bir özel durum oluşturursa, derleyici işleç **Delete** çağrısını çağırmak için kod üretir.

Aşağıdaki listede **Yeni**dil bilgisi öğeleri açıklanmaktadır:

*yerleştirilmesine*<br/>
**Yeni**aşırı yükleme yaparsanız ek bağımsız değişkenler geçirmenin bir yolunu sağlar.

*tür adı*<br/>
Ayrılacak türü belirtir; yerleşik veya Kullanıcı tanımlı bir tür olabilir. Tür belirtimi karmaşıktır, bağlama sırasını zorlamak için ayraçları parantez içine alabilir.

*izer*<br/>
Başlatılmış nesne için bir değer sağlar. Başlatıcılar diziler için belirtilemez. **New** işleci yalnızca sınıfın varsayılan bir Oluşturucusu varsa nesne dizileri oluşturur.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir karakter dizisi ve `CName` sınıfından bir nesne ayırır ve sonra onları serbest bırakır.

```cpp
// expre_new_Operator.cpp
// compile with: /EHsc
#include <string.h>

class CName {
public:
   enum {
      sizeOfBuffer = 256
   };

   char m_szFirst[sizeOfBuffer];
   char m_szLast[sizeOfBuffer];

public:
   void SetName(char* pszFirst, char* pszLast) {
     strcpy_s(m_szFirst, sizeOfBuffer, pszFirst);
     strcpy_s(m_szLast, sizeOfBuffer, pszLast);
   }

};

int main() {
   // Allocate memory for the array
   char* pCharArray = new char[CName::sizeOfBuffer];
   strcpy_s(pCharArray, CName::sizeOfBuffer, "Array of characters");

   // Deallocate memory for the array
   delete [] pCharArray;
   pCharArray = NULL;

   // Allocate memory for the object
   CName* pName = new CName;
   pName->SetName("Firstname", "Lastname");

   // Deallocate memory for the object
   delete pName;
   pName = NULL;
}
```

## <a name="example"></a>Örnek

**Yeni** işlecin yerleştirme boyutuna ek olarak, ' ın yeni işleç formunu kullanırsanız, Oluşturucu bir özel durum oluşturursa, derleyici **Delete** işlecinin yerleştirme formunu desteklemez. Örneğin:

```cpp
// expre_new_Operator2.cpp
// C2660 expected
class A {
public:
   A(int) { throw "Fail!"; }
};
void F(void) {
   try {
      // heap memory pointed to by pa1 will be deallocated
      // by calling ::operator delete(void*).
      A* pa1 = new A(10);
   } catch (...) {
   }
   try {
      // This will call ::operator new(size_t, char*, int).
      // When A::A(int) does a throw, we should call
      // ::operator delete(void*, char*, int) to deallocate
      // the memory pointed to by pa2.  Since
      // ::operator delete(void*, char*, int) has not been implemented,
      // memory will be leaked when the deallocation cannot occur.

      A* pa2 = new(__FILE__, __LINE__) A(20);
   } catch (...) {
   }
}

int main() {
   A a;
}
```

## <a name="initializing-object-allocated-with-new"></a>Yeni ile ayrılan nesne başlatılıyor

İsteğe bağlı bir *Başlatıcı* alanı, **Yeni** operatör için dilbilgisinde bulunur. Bu, kullanıcı tanımlı oluşturucularla yeni nesnelerin başlatılmasını sağlar. Başlatmanın nasıl yapılacağı hakkında daha fazla bilgi için bkz. [başlatıcılar](../cpp/initializers.md). Aşağıdaki örnek, **Yeni** işleçle bir başlatma ifadesinin nasıl kullanılacağını göstermektedir:

```cpp
// expre_Initializing_Objects_Allocated_with_new.cpp
class Acct
{
public:
    // Define default constructor and a constructor that accepts
    //  an initial balance.
    Acct() { balance = 0.0; }
    Acct( double init_balance ) { balance = init_balance; }
private:
    double balance;
};

int main()
{
    Acct *CheckingAcct = new Acct;
    Acct *SavingsAcct = new Acct ( 34.98 );
    double *HowMuch = new double ( 43.0 );
    // ...
}
```

Bu örnekte, nesne `CheckingAcct` **New** işleci kullanılarak ayrılır, ancak varsayılan başlatma belirtilmez. Bu nedenle, `Acct()` sınıfı için varsayılan oluşturucu çağrılır. Ardından `SavingsAcct` nesnesi aynı şekilde ayrılır, ancak açıkça 34.98'e başlatılır. 34,98 **Double**türünde olduğundan, başlatmayı işlemek için bu tür bir bağımsız değişken alan Oluşturucu çağırılır. Son olarak, `HowMuch` nonclass türü 43.0 için başlatılır.

Bir nesne bir sınıf türünde ise ve bu sınıfın oluşturucuları varsa (önceki örnekte olduğu gibi), nesne yalnızca bu koşullardan biri karşılandığında **Yeni** işleç tarafından başlatılabilir:

- Başlatıcıda sağlanan bağımsız değişkenler oluşturucununkilerle uyumludur.

- Sınıfın varsayılan bir oluşturucusu (bağımsız değişken olmadan çağrılabilecek bir oluşturucu) vardır.

**New** işleci kullanılarak diziler ayrılırken açık öğe başına başlatma yapılamaz; yalnızca varsayılan Oluşturucu varsa, çağırılır. Daha fazla bilgi için bkz. [Varsayılan bağımsız değişkenler](../cpp/default-arguments.md) .

Bellek ayırma başarısız olursa (**New işleci** 0 değerini döndürür), başlatma gerçekleştirilmez. Bu, var olmayan verileri başlatma girişimlerini önler.

İşlev çağrılarında olduğu gibi, başlatılan ifadelerin değerlendirilme sırası tanımlı değildir. Ayrıca, bellek ayırma işlemi yapılmadan önce bu ifadelerin tamamen değerlendirileceğine güvenmemelisiniz. Bellek ayırma başarısız olursa ve **Yeni** işleç sıfır döndürürse, başlatıcıdaki bazı ifadeler tamamen değerlendirilmeyebilir.

## <a name="lifetime-of-objects-allocated-with-new"></a>Yeni ile ayrılmış nesnelerin ömrü

**Yeni** işleçle ayrılan nesneler, tanımlandıkları kapsamın çıkış sırasında yok edilmez. **New** işleci ayırdığı nesnelere bir işaretçi döndürdüğünden, program bu nesnelere erişmek için uygun kapsama sahip bir işaretçi tanımlamalıdır. Örneğin:

```cpp
// expre_Lifetime_of_Objects_Allocated_with_new.cpp
// C2541 expected
int main()
{
    // Use new operator to allocate an array of 20 characters.
    char *AnArray = new char[20];

    for( int i = 0; i < 20; ++i )
    {
        // On the first iteration of the loop, allocate
        //  another array of 20 characters.
        if( i == 0 )
        {
            char *AnotherArray = new char[20];
        }
    }

    delete [] AnotherArray; // Error: pointer out of scope.
    delete [] AnArray;      // OK: pointer still in scope.
}
```

`AnotherArray` işaretçisi örnekteki kapsamdan çıktığında, nesne artık silinemez.

## <a name="how-new-works"></a>Yeni nasıl kullanılır?

*Ayırma ifadesi* — **New** işlecini içeren ifade — üç şey yapar:

- Ayrılacak nesne veya nesneler için depolamayı bulur ve ayırır. Bu aşama tamamlandığında, doğru depolama miktarı ayrılır, ancak henüz bir nesne değildir.

- Nesneleri başlatır. Başlatma tamamlandıktan sonra, ayrılan depolamanın bir nesne olması için yeterli bilgi mevcuttur.

- *Yeni-tür-adı* veya *tür-adından*türetilmiş bir işaretçi türünün nesne (ler) i için bir işaretçi döndürür. Program, bu işaretçiyi yeni ayrılan nesneye erişmek için kullanır.

**New** işleci **New işlev işlecini**çağırır. Herhangi bir türdeki diziler için ve **sınıf**, **Yapı**veya **birleşim** türü olmayan nesneler için, depolama alanı ayırmak için bir genel işlev olan **:: New**' i çağırılır. Sınıf türü nesneler, sınıf başına **Yeni** statik üye işlevini her sınıf temelinde tanımlayabilir.

Derleyici, tür türünde bir nesne ayırmak için **New** işleçle **karşılaştığında, `type`** **:: operator new (sizeof (** `type` **))** çağrısı yayınlar veya yeni bir Kullanıcı tanımlı **işleç** tanımlı değilse, **:: New işleci (sizeof (** `type` **))** . Bu nedenle, **Yeni** operatör nesne için doğru miktarda bellek ayırabilir.

> [!NOTE]
>  **New işlecine** yönelik bağımsız değişken `size_t`türündedir. Bu tür doğrudan \<tanımlıdır. h >, \<malloc. h >, \<Memory. h >, \<arama. h >, \<stddef. h >, \<stdio. h >, \<Stdlib. h >, \<String. h > ve \<Time. h >.

Dilbilgisinde bir seçenek, *yerleştirme* belirtimine izin verir (bkz. [Yeni operatör](../cpp/new-operator-cpp.md)için dilbilgisi). *Yerleştirme* parametresi yalnızca **New işlecinin**Kullanıcı tanımlı uygulamaları için kullanılabilir; ek bilgilerin **Yeni işleçle**geçirilmesini sağlar. `T *TObject = new ( 0x0040 ) T;` gibi *yerleştirme* alanı olan bir ifade, sınıf t 'nin yeni üye işleci varsa, `T *TObject = ::operator new( sizeof( T ), 0x0040 );`için `T *TObject = T::operator new( sizeof( T ), 0x0040 );` çevrilir.

*Yerleştirme* alanının özgün amacı, donanıma bağımlı nesnelerin Kullanıcı tarafından belirtilen adreslerde ayrılmasına izin veriydi.

> [!NOTE]
>  Yukarıdaki örnekte *yerleştirme* alanında yalnızca bir bağımsız değişken gösterilse de, bu şekilde **New işlecine** kaç tane fazladan bağımsız değişken geçirilebileceğini gösteren bir kısıtlama yoktur.

Bir sınıf türü için **New işleci** tanımlandığında bile, genel işleç bu örnek formu kullanılarak kullanılabilir:

```cpp
T *TObject =::new TObject;
```

Kapsam çözümleme işleci (`::`) genel **New** işlecinin kullanımını zorlar.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[New ve delete işleçleri](../cpp/new-and-delete-operators.md)
