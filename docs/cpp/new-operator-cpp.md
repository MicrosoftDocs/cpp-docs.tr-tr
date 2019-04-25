---
title: new İşleci (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
ms.openlocfilehash: bcb7784e59966510970bd9b3ae0157ae982e462d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245393"
---
# <a name="new-operator-c"></a>new İşleci (C++)

Bir nesne veya nesneler dizisi için bellek ayırır *tür adı* boş depolamak ve nesneye uygun türde, sıfır olmayan bir işaretçi döndürür.

> [!NOTE]
>  Microsoft C++ bileşen uzantıları için destek sağlar **yeni** anahtar sözcüğü vtable yuvası girişlerinin eklenebilmesi için. Daha fazla bilgi için [yeni (vtable'da yeni yuva)](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

## <a name="syntax"></a>Sözdizimi

```
[::] new [placement] new-type-name [new-initializer]
[::] new [placement] ( type-name ) [new-initializer]
```

## <a name="remarks"></a>Açıklamalar

İşlem başarısız olursa, **yeni** sıfır döndürür veya bir özel durum oluşturur; bkz [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md) daha fazla bilgi için. Bu varsayılan davranışı özel bir özel durum işleme yordamı yazarak ve çağırma değiştirebilirsiniz [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) değişken bağımsız değişken olarak çalışma zamanı kitaplığı işlevi.

Yönetilen yığındaki bir nesne oluşturma hakkında daha fazla bilgi için bkz: [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md).

Zaman **yeni** olduğu bellek atandıktan sonra bir C++ sınıfı nesne için bellek ayırmak için kullanıldığında, nesnenin oluşturucusunun adı verilir.

Kullanım [Sil](../cpp/delete-operator-cpp.md) operatörü ile ayrılan belleği serbest bırakmak **yeni** işleci.

Aşağıdaki örnek ayırır ve ardından iki boyutlu bir dizi karakter boyutunu serbest bırakır `dim` 10. Çok boyutlu bir dizi tahsis ederken ilki dışındaki tüm boyutlar, pozitif değerlere dönüşen sabit ifadeler olmalıdır; en soldaki dizi boyutu pozitif bir değer veren herhangi bir ifade olabilir. Kullanarak bir dizi tahsis ederken **yeni** işleci, ilk boyut sıfır olabilir — **yeni** işleci benzersiz bir işaretçi döndürür.

```cpp
char (*pchar)[10] = new char[dim][10];
delete [] pchar;
```

*Tür adı* içeremez **const**, **geçici**, sınıf bildirimi veya numaralandırma bildirimleri. Bu nedenle aşağıdaki ifade geçersizdir:

```cpp
volatile char *vch = new volatile char[20];
```

**Yeni** işleci ayrılamadı başvuru türleri nesne olmadıklarından.

**Yeni** bir işlevi atamak için işleç kullanılamaz ancak işlevlere belirticiler atamak için kullanılabilir. Aşağıdaki örnek, ayırır ve ardından, tamsayı döndüren işlevlere yedi işaretçiden oluşan bir dizi serbest bırakır.

```cpp
int (**p) () = new (int (*[7]) ());
delete *p;
```

İşlecini kullanıyorsanız **yeni** herhangi ek bağımsız değişkenler ve derleme ile olmadan [/GX](../build/reference/gx-enable-exception-handling.md), [/eha](../build/reference/eh-exception-handling-model.md), veya [EHS](../build/reference/eh-exception-handling-model.md) derleyici seçeneği, olur işlecini çağırmak için kod oluşturmak **Sil** Oluşturucusu bir özel durum atar.

Aşağıdaki listede dilbilgisi öğelerini açıklar **yeni**:

*yerleştirme*<br/>
İşlecini aşırı yüklediyseniz ek bağımsız değişkenleri geçirme bir yol sağlayan **yeni**.

*tür adı*<br/>
Ayrılacak türü belirtir. Bu, yerleşik veya kullanıcı tanımlı türü olabilir. Tür belirtimi karmaşıksa, bağlama sırasının zorlanması için parantez içine.

*Başlatıcı*<br/>
Başlatılan nesne için bir değer sağlar. Başlatıcılar diziler için belirtilemez. **Yeni** işleci yalnızca sınıfın varsayılan bir oluşturucusu varsa nesne dizileri oluşturacaktır.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir karakter dizisi ve sınıfın bir nesnesi ayırır `CName` ve serbest bırakır.

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

Yerleştirme yeni biçimini kullanırsanız **yeni** işleci ayırma, derleyici bağımsız değişken boyutuna ek olarak formun değiştirilmesini desteklemiyor **Sil** işleci, Oluşturucusu bir özel durum oluşturur. Örneğin:

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

## <a name="initializing-object-allocated-with-new"></a>New ile ayrılmış nesne başlatma

İsteğe bağlı *Başlatıcı* alanı için dilbilgisine eklenir **yeni** işleci. Bu, kullanıcı tanımlı oluşturucularla yeni nesnelerin başlatılmasını sağlar. Başlatmanın nasıl yapılacağı hakkında daha fazla bilgi için bkz. [başlatıcılar](../cpp/initializers.md). Aşağıdaki örnekte bir başlatma ifadesinin kullanılması gösterilmektedir **yeni** işleci:

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

Bu örnekte, nesne `CheckingAcct` kullanılarak ayrılmış **yeni** işleci, ancak varsayılan başlatma belirtildi. Bu nedenle, `Acct()` sınıfı için varsayılan oluşturucu çağrılır. Ardından `SavingsAcct` nesnesi aynı şekilde ayrılır, ancak açıkça 34.98'e başlatılır. 34.98 türünde olduğu için **çift**, başlatma işlemini, türünde bir bağımsız değişken alan oluşturucu çağrılır. Son olarak, `HowMuch` nonclass türü 43.0 için başlatılır.

Tarafından bir sınıf türünde bir nesnedir ve o sınıfın oluşturucuları (Yukarıdaki örnekteki) varsa, nesne başlatılabilir **yeni** yalnızca şu koşullardan biri karşılanırsa işleci:

- Başlatıcıda sağlanan bağımsız değişkenler oluşturucununkilerle uyumludur.

- Sınıfın varsayılan bir oluşturucusu (bağımsız değişken olmadan çağrılabilecek bir oluşturucu) vardır.

Kullanarak dizileri ayırırken hiçbir açık öğe başına başlatma yapılamaz **yeni** işleci; yalnızca varsayılan oluşturucusu varsa çağrılır. Bkz: [varsayılan bağımsız değişkenler](../cpp/default-arguments.md) daha fazla bilgi için.

Bellek ayırma başarısız olursa (**new işleci** 0 değerini döndürür), hiçbir başlatma gerçekleştirilmez. Bu, var olmayan verileri başlatma girişimlerini önler.

İşlev çağrılarında olduğu gibi, başlatılan ifadelerin değerlendirilme sırası tanımlı değildir. Ayrıca, bellek ayırma işlemi yapılmadan önce bu ifadelerin tamamen değerlendirileceğine güvenmemelisiniz. Bellek ayırma başarısız olursa ve **yeni** işleci sıfır döndürürse, başlatıcıdaki bazı ifadeler tamamen Değerlendirilmedi.

## <a name="lifetime-of-objects-allocated-with-new"></a>New ile ayrılmış nesnelerin ömrü

İle ayrılmış nesneleri **yeni** işleci bunların tanımlandığı kapsamı çıkıldı zaman yok edilmez. Çünkü **yeni** işleci bir işaretçiyi ayırdığı nesnelere döndürür, program bu nesnelere erişmek için uygun kapsama sahip bir işaretçi tanımlamalıdır. Örneğin:

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

## <a name="how-new-works"></a>New nasıl çalışır

*Ayırma ifade* — ifadesi içeren **yeni** işleci — üç şeyi yapar:

- Bulur ve nesneyi veya ayrılacak nesneleri için depolama alanı ayırır. Bu aşama tamamlandıktan sonra doğru depolama miktarını ayrılır, ancak, henüz bir nesne değil.

- Nesneyi başlatır. Başlatma tamamlandıktan sonra bir nesne olması ayrılmış depolama için yeterli bilgi yok.

- Sınıfından türetilen bir işaretçi türü nesneler için bir işaretçi döndürür *tür adı yeni* veya *tür adı*. Program bu işaretçi yeni ayrılan bir nesneye erişmek için kullanır.

**Yeni** işleci bir işlevi çağırır **new işleci**. Herhangi bir türde diziler için ve biri olmayan nesneler için **sınıfı**, **yapı**, veya **birleşim** türleri, genel bir işlev **:: new işleci**, olan depolama alanı ayırmak üzere çağrılır. Sınıf türü nesneleri tanımlayabilirsiniz, kendi **new işleci** sınıfı başına temelinde statik üye işlevi.

Derleyici karşılaştığında **yeni** işleci türünde bir nesne ayrılamadı **türü**, çağrı verdiği `type` **:: new işleci (sizeof (** `type` **))** veya kullanıcı tanımlı Hayır ise **new işleci** tanımlanan **:: new işleci (sizeof (** `type` **))**. Bu nedenle, **yeni** işleci, nesne için bellek miktarını doğru ayırabilirsiniz.

> [!NOTE]
>  Bağımsız değişkeni **new işleci** türünde `size_t`. Bu tür tanımlanan \<direct.h >, \<malloc.h >, \<memory.h >, \<search.h >, \<stddef.h >, \<stdio.h >, \<stdlib.h >, \<string.h >, ve \<TIME.h >.

Bir seçenek dilbilgisi içinde belirtilmesine izin verir. *yerleştirme* (dil bilgisi için bkz. [new işleci](../cpp/new-operator-cpp.md)). *Yerleştirme* parametresi yalnızca kullanıcı tarafından tanımlanan uygulamaları için kullanılabilir **new işleci**; geçirilecek ek bilgi sağlayan **new işleci**. Bir ifade içeren bir *yerleştirme* gibi alan `T *TObject = new ( 0x0040 ) T;` çevrildiğinde `T *TObject = T::operator new( sizeof( T ), 0x0040 );` sınıfı T üye işleci yeni, aksi takdirde gerekiyorsa `T *TObject = ::operator new( sizeof( T ), 0x0040 );`.

Özgün amacınıza *yerleştirme* alan haline donanım bağımlı nesneler kullanıcı tarafından belirtilen adresi ayrılmasını sağlar.

> [!NOTE]
>  Önceki örnekte, tek bir bağımsız değişkende gösterir, ancak *yerleştirme* alan, kaç ek bağımsız değişkenler geçirilebilir üzerinde bir kısıtlama yoktur **new işleci** bu şekilde.

Zaman bile **new işleci** tanımlanmış bir sınıf türü için bu örnekte formu kullanarak global işleci kullanılabilir:

```cpp
T *TObject =::new TObject;
```

Kapsam çözümleme işleci (`::`) zorlar genel kullanım **yeni** işleci.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Yeni ve delete işleçleri](../cpp/new-and-delete-operators.md)