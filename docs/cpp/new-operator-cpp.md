---
title: new İşleci (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
ms.openlocfilehash: 81dd7483c49a699ac53ea53d33481fa6539d484c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223661"
---
# <a name="new-operator-c"></a>new İşleci (C++)

Boş depodan bir nesne veya türündeki nesne dizisi için bellek ayırır ve nesneye uygun şekilde, sıfır *olmayan* bir işaretçi döndürür.

> [!NOTE]
> Microsoft C++ Bileşen Uzantıları, **`new`** vtable yuva girdileri eklemek için anahtar sözcük desteği sağlar. Daha fazla bilgi için bkz. [Yeni (vtable 'da yeni yuva)](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

## <a name="syntax"></a>Sözdizimi

```
[::] new [placement] new-type-name [new-initializer]
[::] new [placement] ( type-name ) [new-initializer]
```

## <a name="remarks"></a>Açıklamalar

Başarısız olursa, **`new`** sıfır döndürür veya bir özel durum oluşturur; daha fazla bilgi için bkz. [New ve delete işleçleri](../cpp/new-and-delete-operators.md) . Özel bir özel durum işleme yordamı yazarak ve bağımsız değişkeni olarak işlev adınızla [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) çalışma zamanı kitaplığı işlevini çağırarak, bu varsayılan davranışı değiştirebilirsiniz.

Yönetilen yığında bir nesne oluşturma hakkında daha fazla bilgi için bkz. [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md).

**`new`** Bir C++ sınıf nesnesi için bellek ayırmak için kullanıldığında, bellek ayrıldıktan sonra nesnenin Oluşturucusu çağrılır.

İşleçle ayrılan belleği serbest bırakmak için [Delete](../cpp/delete-operator-cpp.md) işlecini kullanın **`new`** .

Aşağıdaki örnek, boyutu 10 olan iki boyutlu bir karakter dizisini ayırır ve serbest bırakır `dim` . Çok boyutlu bir dizi ayrılırken, ilki hariç tüm boyutlar pozitif değerler değerlendiren sabit deyimler olmalıdır; en soldaki dizi boyutu pozitif bir değer değerlendirilen herhangi bir ifade olabilir. İşleci kullanarak bir dizi ayrılırken **`new`** , ilk boyut sıfır olabilir — **`new`** işleç, benzersiz bir işaretçi döndürür.

```cpp
char (*pchar)[10] = new char[dim][10];
delete [] pchar;
```

*Tür adı* **`const`** ,, **`volatile`** sınıf bildirimleri veya numaralandırma bildirimleri içeremez. Bu nedenle, aşağıdaki ifade geçersizdir:

```cpp
volatile char *vch = new volatile char[20];
```

İşleç, nesne olmadıkları için **`new`** başvuru türlerini ayırmıyor.

**`new`** İşleci bir işlevi ayırmak için kullanılamaz, ancak işlevlere işaretçiler ayırmak için kullanılabilir. Aşağıdaki örnek, tamsayılar döndüren işlevlere yedi işaretçilerin bir dizisini ayırır ve serbest bırakır.

```cpp
int (**p) () = new (int (*[7]) ());
delete *p;
```

İşleci **`new`** ek bağımsız değişkenler olmadan kullanırsanız ve [/GX](../build/reference/gx-enable-exception-handling.md), [/EHa](../build/reference/eh-exception-handling-model.md)veya [/EHS](../build/reference/eh-exception-handling-model.md) seçeneğiyle derlerseniz, **`delete`** Oluşturucu bir özel durum oluşturursa, derleyici işleci çağırmak için kod üretir.

Aşağıdaki listede, öğesinin dilbilgisi öğeleri açıklanmaktadır **`new`** :

*yerleştirilmesine*<br/>
Aşırı yüklüyorsanız ek bağımsız değişkenler geçirmenin bir yolunu sağlar **`new`** .

*tür adı*<br/>
Ayrılacak türü belirtir; yerleşik veya Kullanıcı tanımlı bir tür olabilir. Tür belirtimi karmaşıktır, bağlama sırasını zorlamak için ayraçları parantez içine alabilir.

*izer*<br/>
Başlatılmış nesne için bir değer sağlar. Başlatıcılar diziler için belirtilemez. **`new`** İşleci yalnızca sınıfın varsayılan bir Oluşturucusu varsa nesne dizileri oluşturur.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir karakter dizisi ve sınıfından bir nesne ayırır `CName` ve sonra onları serbest bırakır.

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

İşlecin yeni formunu **`new`** , ayırma boyutuna ek olarak bağımsız değişkenlerle birlikte kullanırsanız, **`delete`** Oluşturucu bir özel durum oluşturursa, derleyici işlecin yerleştirme biçimini desteklemez. Örnek:

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

İsteğe bağlı bir *Başlatıcı* alanı, işlecine yönelik dilbilgisinde bulunur **`new`** . Bu, kullanıcı tanımlı oluşturucularla yeni nesnelerin başlatılmasını sağlar. Başlatmanın nasıl yapılacağı hakkında daha fazla bilgi için bkz. [başlatıcılar](../cpp/initializers.md). Aşağıdaki örnek, bir başlatma ifadesinin işleçle nasıl kullanılacağını göstermektedir **`new`** :

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

Bu örnekte, nesnesi `CheckingAcct` işleci kullanılarak ayrılır **`new`** , ancak varsayılan başlatma belirtilmez. Bu nedenle, `Acct()` sınıfı için varsayılan oluşturucu çağrılır. Ardından `SavingsAcct` nesnesi aynı şekilde ayrılır, ancak açıkça 34.98'e başlatılır. 34,98 türünde olduğu **`double`** için, bu tür bir bağımsız değişken alan Oluşturucu başlatmayı işlemek için çağırılır. Son olarak, `HowMuch` nonclass türü 43.0 için başlatılır.

Bir nesne bir sınıf türünde ise ve bu sınıfın oluşturucuları varsa (önceki örnekte olduğu gibi), nesne **`new`** yalnızca bu koşullardan biri karşılandığında işleç tarafından başlatılabilir:

- Başlatıcıda sağlanan bağımsız değişkenler oluşturucununkilerle uyumludur.

- Sınıfın varsayılan bir oluşturucusu (bağımsız değişken olmadan çağrılabilecek bir oluşturucu) vardır.

İşleci kullanılarak diziler ayrılırken açık öğe başına başlatma yapılamaz **`new`** ; yalnızca varsayılan Oluşturucu varsa, çağırılır. Daha fazla bilgi için bkz. [Varsayılan bağımsız değişkenler](../cpp/default-arguments.md) .

Bellek ayırma başarısız olursa (**New işleci** 0 değerini döndürür), başlatma gerçekleştirilmez. Bu, var olmayan verileri başlatma girişimlerini önler.

İşlev çağrılarında olduğu gibi, başlatılan ifadelerin değerlendirilme sırası tanımlı değildir. Ayrıca, bellek ayırma işlemi yapılmadan önce bu ifadelerin tamamen değerlendirileceğine güvenmemelisiniz. Bellek ayırma başarısız olursa ve **`new`** işleç sıfır döndürürse, başlatıcıdaki bazı ifadeler tamamen değerlendirilmeyebilir.

## <a name="lifetime-of-objects-allocated-with-new"></a>Yeni ile ayrılmış nesnelerin ömrü

İşleciyle ayrılan nesneler, **`new`** tanımlandıkları kapsamın çıkış sırasında yok edilmez. İşleci, **`new`** ayırdığı nesnelere bir işaretçi döndürdüğünden, program bu nesnelere erişmek için uygun kapsama sahip bir işaretçi tanımlamalıdır. Örnek:

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

*Ayırma ifadesi* — işleci içeren ifade **`new`** — üç şey yapar:

- Ayrılacak nesne veya nesneler için depolamayı bulur ve ayırır. Bu aşama tamamlandığında, doğru depolama miktarı ayrılır, ancak henüz bir nesne değildir.

- Nesneleri başlatır. Başlatma tamamlandıktan sonra, ayrılan depolamanın bir nesne olması için yeterli bilgi mevcuttur.

- *Yeni-tür-adı* veya *tür-adından*türetilmiş bir işaretçi türünün nesne (ler) i için bir işaretçi döndürür. Program, bu işaretçiyi yeni ayrılan nesneye erişmek için kullanır.

**`new`** İşleci **New işlev işlecini**çağırır. Herhangi bir türdeki diziler için ve, veya türünde olmayan nesneler için, **`class`** **`struct`** **`union`** depolama alanı ayırmak için **:: New**genel işlevi çağırılır. Sınıf türü nesneler, sınıf başına **Yeni** statik üye işlevini her sınıf temelinde tanımlayabilir.

Derleyici, türü türünde **`new`** bir nesne ayırmak için işleçle karşılaştığında, **type**:: New işleci `type` **(sizeof (** `type` **))** veya bir Kullanıcı tanımlı **işleç** tanımlanmazsa, **:: New işleci (sizeof (** `type` **))** öğesine bir çağrı yayınlar. Bu nedenle, **`new`** işleci nesne için doğru miktarda bellek ayırabilir.

> [!NOTE]
> **New işlecine** yönelik bağımsız değişken türündedir `size_t` . Bu tür,,,,,,, ve içinde tanımlanır \<direct.h> \<malloc.h> \<memory.h> \<search.h> \<stddef.h> \<stdio.h> \<stdlib.h> \<string.h> \<time.h> .

Dilbilgisinde bir seçenek, *yerleştirme* belirtimine izin verir (bkz. [Yeni operatör](../cpp/new-operator-cpp.md)için dilbilgisi). *Yerleştirme* parametresi yalnızca **New işlecinin**Kullanıcı tanımlı uygulamaları için kullanılabilir; ek bilgilerin **Yeni işleçle**geçirilmesini sağlar. Gibi *yerleştirme* alanı olan bir ifade, `T *TObject = new ( 0x0040 ) T;` `T *TObject = T::operator new( sizeof( T ), 0x0040 );` sınıf T 'de üye işleci New, aksi durumda öğesine çevrilir `T *TObject = ::operator new( sizeof( T ), 0x0040 );` .

*Yerleştirme* alanının özgün amacı, donanıma bağımlı nesnelerin Kullanıcı tarafından belirtilen adreslerde ayrılmasına izin veriydi.

> [!NOTE]
> Yukarıdaki örnekte *yerleştirme* alanında yalnızca bir bağımsız değişken gösterilse de, bu şekilde **New işlecine** kaç tane fazladan bağımsız değişken geçirilebileceğini gösteren bir kısıtlama yoktur.

Bir sınıf türü için **New işleci** tanımlandığında bile, genel işleç bu örnek formu kullanılarak kullanılabilir:

```cpp
T *TObject =::new TObject;
```

Kapsam çözümleme işleci (), `::` genel işleç kullanımını zorlar **`new`** .

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[new ve delete işleçleri](../cpp/new-and-delete-operators.md)
