---
title: new İşleci (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
ms.openlocfilehash: ac89bf37b8aaaa9d77393b714a233f8a4c998139
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367866"
---
# <a name="new-operator-c"></a>new İşleci (C++)

Boş depodan bir nesne veya *tür adı* nesneleri dizisi için bellek ayırır ve nesneye uygun şekilde yazılmış, sıfır olmayan bir işaretçi döndürür.

> [!NOTE]
> Microsoft C++ Bileşen Uzantıları, vtable yuvası girişleri eklemek için **yeni** anahtar kelime desteği sağlar. Daha fazla bilgi için [yeni (vtable'da yeni yuva)](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

## <a name="syntax"></a>Sözdizimi

```
[::] new [placement] new-type-name [new-initializer]
[::] new [placement] ( type-name ) [new-initializer]
```

## <a name="remarks"></a>Açıklamalar

Başarısız olursa, **yeni** döndürür sıfır veya bir özel durum atar; daha fazla bilgi için [Yeni ve Sil Operatörleri'ne](../cpp/new-and-delete-operators.md) bakın. Özel bir özel durum işleme yordamı yazarak ve işlev adınız ile [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) çalışma zamanı kitaplığı işlevini bağımsız değişken olarak çağırarak bu varsayılan davranışı değiştirebilirsiniz.

Yönetilen yığında bir nesnenin nasıl oluşturulacağını zedebetmek için [bkz.](../extensions/ref-new-gcnew-cpp-component-extensions.md)

C++ sınıfı nesnesi için bellek ayırmak için **yeni** kullanıldığında, nesnenin oluşturucusu bellek ayrıldıktan sonra çağrılır.

**Yeni** işleçle ayrılan belleği bulmak için [silme](../cpp/delete-operator-cpp.md) işlecisini kullanın.

Aşağıdaki örnek, iki boyutlu bir karakter `dim` dizisini 10'a kadar ayırır ve serbest klar. Çok boyutlu bir dizi ayırırken, ilki dışındaki tüm boyutlar pozitif değerleri değerlendiren sabit ifadeler olmalıdır; en soldaki dizi boyutu, pozitif bir değere değer veren herhangi bir ifade olabilir. **Yeni** işleç kullanarak bir dizi ayırırken, ilk boyut sıfır olabilir - **yeni** işleç benzersiz bir işaretçi döndürür.

```cpp
char (*pchar)[10] = new char[dim][10];
delete [] pchar;
```

*Tür adı* **const,** **uçucu,** sınıf bildirimleri veya numaralandırma bildirimleri içeremez. Bu nedenle, aşağıdaki ifade yasadışıdır:

```cpp
volatile char *vch = new volatile char[20];
```

**Yeni** işleç, nesne olmadıkları için başvuru türlerini ayırmaz.

**Yeni** işleç bir işlev ayırmak için kullanılamaz, ancak işlevlere işaretçileri ayırmak için kullanılabilir. Aşağıdaki örnek, yedi işaretçiden oluşan bir diziyi, karşıtları döndüren işlevlere ayırır ve serbest bırakır.

```cpp
int (**p) () = new (int (*[7]) ());
delete *p;
```

İşleciyi herhangi bir ekstra bağımsız değişken olmadan **kullanır** ve [/GX](../build/reference/gx-enable-exception-handling.md), [/EHa](../build/reference/eh-exception-handling-model.md), veya [/EHs](../build/reference/eh-exception-handling-model.md) seçeneği ile derlerseniz, derleyici, oluşturucu bir özel durum atarsa operatör **silme** çağrısı yapmak için kod oluşturur.

Aşağıdaki liste **yeni**dilbilgisi öğeleriaçıklar:

*Yerleşim*<br/>
**Yeni**aşırı yüklerseniz ek bağımsız değişkenler geçirmenin bir yolunu sağlar.

*tür adı*<br/>
Ayrılacak türü belirtir; yerleşik veya kullanıcı tanımlı bir tür olabilir. Tür belirtimi karmaşıksa, bağlama sırasını zorlamak için parantez ile çevrili olabilir.

*Başlatıcı*<br/>
Başlışınmışnesne için bir değer sağlık sağlar Diziler için baş harfler belirtilemez. **Yeni** işleç, yalnızca sınıfın varsayılan bir oluşturucusu varsa, nesne dizileri oluşturur.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği bir karakter dizisini ve `CName` sınıf nesnesini ayırır ve bunları serbest bırakarak serbest bırakeder.

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

**Yeni** işlecinin yerleşim yeni biçimini, ayırma nın boyutuna ek olarak bağımsız değişkenleri olan formu kullanırsanız, derleyici, oluşturucu bir özel durum atarsa **silme** işlecinin bir yerleşim biçimini desteklemez. Örneğin:

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

## <a name="initializing-object-allocated-with-new"></a>Yeni ile ayrılan nesneyi başlatma

**Yeni** işleç için dilbilgisine isteğe bağlı bir *baş harf* alanı dahildir. Bu, kullanıcı tanımlı oluşturucularla yeni nesnelerin başlatılmasını sağlar. Başlatmanın nasıl yapıldığı hakkında daha fazla bilgi [için, bkz.](../cpp/initializers.md) Aşağıdaki örnekte, **yeni** işleçle bir başlatma ifadesinin nasıl kullanılacağı gösteriş verilmiştir:

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

Bu örnekte, `CheckingAcct` nesne **yeni** işleç kullanılarak ayrılır, ancak varsayılan başlatma belirtilmemiştir. Bu nedenle, `Acct()` sınıfı için varsayılan oluşturucu çağrılır. Ardından `SavingsAcct` nesnesi aynı şekilde ayrılır, ancak açıkça 34.98'e başlatılır. 34.98 türü **çift**olduğundan, bu tür bir bağımsız değişken alan kurucu başlatma işlemek için çağrılır. Son olarak, `HowMuch` nonclass türü 43.0 için başlatılır.

Bir nesne bir sınıf türündense ve bu sınıfın oluşturucuları varsa (önceki örnekte olduğu gibi), nesne yalnızca bu koşullardan biri karşılanırsa **yeni** işleç tarafından başharflere alınabilir:

- Başlatıcıda sağlanan bağımsız değişkenler oluşturucununkilerle uyumludur.

- Sınıfın varsayılan bir oluşturucusu (bağımsız değişken olmadan çağrılabilecek bir oluşturucu) vardır.

**Yeni** işleci kullanarak diziler ayrılırken açık öğe başına başlatma yapılamaz; yalnızca varsayılan oluşturucu, varsa, çağrılır. Daha fazla bilgi için [Varsayılan Bağımsız Değişkenler'e](../cpp/default-arguments.md) bakın.

Bellek ayırma başarısız olursa **(işleç yeni** 0 değerini döndürür), hiçbir başlatma gerçekleştirilir. Bu, var olmayan verileri başlatma girişimlerini önler.

İşlev çağrılarında olduğu gibi, başlatılan ifadelerin değerlendirilme sırası tanımlı değildir. Ayrıca, bellek ayırma işlemi yapılmadan önce bu ifadelerin tamamen değerlendirileceğine güvenmemelisiniz. Bellek ayırma başarısız olursa ve **yeni** işleç sıfır döndürürse, başharfteki bazı ifadeler tam olarak değerlendirilmeyebilir.

## <a name="lifetime-of-objects-allocated-with-new"></a>Yeni ile ayrılan nesnelerin ömrü

**Yeni** işleçle ayrılan nesneler, tanımlandıkları kapsam çıkarıldığında yok edilmez. **Yeni** işleç ayırdığı nesnelere bir işaretçi döndürür, çünkü program bu nesnelere erişmek için uygun kapsama sahip bir işaretçi tanımlamalıdır. Örneğin:

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

## <a name="how-new-works"></a>Yeni nasıl çalışır?

*Ayırma-ifade* - **yeni** işleç içeren ifade - üç şey yapar:

- Tahsis edilecek nesne veya nesneler için depolamayı bulur ve ayırır. Bu aşama tamamlandığında, doğru depolama miktarı ayrılır, ancak henüz bir nesne değildir.

- Nesne(ler) başharflerini. Başlatma tamamlandıktan sonra, ayrılan depolamaalanının nesne olması için yeterli bilgi bulunur.

- *Yeni tür adı* veya *tür*adı türetilen bir işaretçi türü nesne(ler) için bir işaretçi döndürür. Program, yeni ayrılan nesneye erişmek için bu işaretçiyi kullanır.

**Yeni** işleç işlev **işleci yeni**çağırır. Herhangi bir türdeki diziler için ve **sınıf,** **yapı**veya **birleşim** türlerine ait olmayan nesneler için, genel bir **işlev: ::işleç yeni**, depolama ayırmak için çağrılır. Sınıf türü nesneler, sınıf başına olarak kendi **işleç yeni** statik üye işlevini tanımlayabilir.

Derleyici, tür **türündeki**bir nesneyi ayırmak için **yeni** işleçle `type`karşılaştığında, kullanıcı tanımlı bir **işleç yeni** tanımlanmamışsa **::operator new(sizeof)** `type` **) )** **::operator new( sizeof(** `type` **()** için bir çağrı yayınlar. Bu nedenle, **yeni** işleç nesne için doğru bellek miktarını ayırabilirsiniz.

> [!NOTE]
> Yeni **işleç** için bağımsız `size_t`değişken türündedir. Bu tür \<direct.h>, \<malloc.h \<>, memory.h \<>, \<search.h>, \<stddef.h \<>, stdio.h \<>, stdlib.h>, string.h> ve \<time.h> olarak tanımlanır.

Dilbilgisindeki bir seçenek *yerleşim* belirtimini sağlar [(yeni Operatör](../cpp/new-operator-cpp.md)için Dilbilgisi'ne bakın). *Yerleşim* parametresi yalnızca **yeni işleç**uygulamaları için kullanılabilir; bu **operatör yeni**geçirilmesi için ekstra bilgi sağlar. T sınıfının üye işleci yeniyse, başka *bir* `T *TObject = new ( 0x0040 ) T;` `T *TObject = T::operator new( sizeof( T ), 0x0040 );` şekilde `T *TObject = ::operator new( sizeof( T ), 0x0040 );`.

*Yerleşim* alanının özgün amacı, donanıma bağımlı nesnelerin kullanıcı tarafından belirtilen adreslere ayrılmasına izin vermekti.

> [!NOTE]
> Önceki *örnek, yerleşim* alanında yalnızca bir bağımsız değişken gösterse de, bu şekilde **işleç** yeni sine kaç ek bağımsız değişken geçirilebileceği konusunda herhangi bir kısıtlama yoktur.

Bir sınıf türü için **işleç yeni** tanımlanmış olsa bile, genel işleç bu örnek formu kullanılarak kullanılabilir:

```cpp
T *TObject =::new TObject;
```

Kapsam çözümleme işleci (`::`) global **yeni** işlecinin kullanımını zorlar.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[yeni ve silme işleçleri](../cpp/new-and-delete-operators.md)
