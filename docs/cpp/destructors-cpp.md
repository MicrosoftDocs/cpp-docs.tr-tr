---
description: 'Daha fazla bilgi edinin: Yıkıcılar (C++)'
title: Yıkıcılar (C++)
ms.date: 07/20/2019
helpviewer_keywords:
- objects [C++], destroying
- destructors, C++
ms.assetid: afa859b0-f3bc-4c4d-b250-c68b335b6004
ms.openlocfilehash: 121df368fc79f7dbabe4ccac6fe93c36788c5e51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195573"
---
# <a name="destructors-c"></a>Yıkıcılar (C++)

Yıkıcı, nesne kapsam dışına geçtiğinde veya öğesine yapılan bir çağrı tarafından açıkça yok edildiğinde otomatik olarak çağrılan bir üye işlevdir **`delete`** . Yıkıcı, önünde bir tilde () ile aynı ada sahiptir `~` . Örneğin, `String` sınıfının yok edicisi şu şekilde bildirilir: `~String()`.

Yok edicisi tanımlamadıysanız, derleyici varsayılan bir tane sağlar; birçok sınıf için bu yeterlidir. Sınıf, yalnızca yayımlanması gereken sistem kaynaklarına veya işaret ettikleri belleğe ait işaretçileri depoladığında özel bir yıkıcı tanımlamanız gerekir.

`String` sınıfıyla ilgili aşağıdaki bildirimi dikkate alın:

```cpp
// spec1_destructors.cpp
#include <string>

class String {
public:
   String( char *ch );  // Declare constructor
   ~String();           //  and destructor.
private:
   char    *_text;
   size_t  sizeOfText;
};

// Define the constructor.
String::String( char *ch ) {
   sizeOfText = strlen( ch ) + 1;

   // Dynamically allocate the correct amount of memory.
   _text = new char[ sizeOfText ];

   // If the allocation succeeds, copy the initialization string.
   if( _text )
      strcpy_s( _text, sizeOfText, ch );
}

// Define the destructor.
String::~String() {
   // Deallocate the memory that was previously reserved
   //  for this string.
   delete[] _text;
}

int main() {
   String str("The piper in the glen...");
}
```

Önceki örnekte, yıkıcı `String::~String` **`delete`** metin depolaması için dinamik olarak ayrılan alanı serbest bırakmak için işlecini kullanır.

## <a name="declaring-destructors"></a>Yıkıcıları bildirme

Yok ediciler, sınıfla aynı adı taşıyan, ancak önüne bir tilde () gelen işlevlerdir `~`

Birçok kural, yok edicilerin bildirimini yönetir. Yıkıcılar

- Bağımsız değişkenleri kabul etmez.

- Değer döndürmez (veya **`void`** ).

- , Veya olarak bildirilemez **`const`** **`volatile`** **`static`** . Ancak,, veya olarak belirtilen nesnelerin yok edilmesi için çağrılabilir **`const`** **`volatile`** **`static`** .

- Olarak bildirilebilecek **`virtual`** . Sanal yıkıcıları kullanarak, türünü bilmeden nesneleri yok edebilirsiniz — nesnenin doğru yıkıcısı sanal işlev mekanizması kullanılarak çağrılır. Yok edicilerin soyut sınıflar için saf sanal işlev olarak da bildirilebilecek olduğunu unutmayın.

## <a name="using-destructors"></a>Yıkıcıları kullanma

Aşağıdaki olaylardan biri gerçekleştiğinde yok ediciler çağrılır:

- Blok kapsamlı bir yerel (otomatik) nesne kapsam dışına gider.

- İşleci kullanılarak ayrılan bir nesne **`new`** , kullanılarak açıkça serbest bırakılır **`delete`** .

- Geçici bir nesnenin kullanım ömrü sona erer.

- Bir program sona erer ve genel veya statik nesneler kalır.

- Yok edici, işlevinin tam adı kullanılarak çağrılır.

Yok ediciler, sınıf üyesi işlevlerini serbestçe çağırabilir ve sınıf üyesi verilerine erişebilir.

Yok ediciler kullanılarak iki kısıtlama vardır:

- Adresini alamaz.

- Türetilmiş sınıflar, temel sınıflarının yok edicisini almıyor.

## <a name="order-of-destruction"></a>Yok etme sırası

Bir nesne kapsam dışına geçtiğinde veya silindiğinde, kendi tamamlanmamış yok etme içindeki olayların sırası aşağıdaki gibidir:

1. Sınıfın yıkıcısı çağrılır ve yıkıcı işlevinin gövdesi yürütülür.

1. Statik olmayan üye nesneleri için Yıkıcılar, sınıf bildiriminde göründükleri ters sırada çağırılır. Bu üyelerin oluşturulması sırasında kullanılan isteğe bağlı üye başlatma listesi, oluşturma veya yok etme sırasını etkilemez.

1. Sanal olmayan taban sınıflar için Yıkıcılar bildirimin ters sırada çağırılır.

1. Sanal temel sınıflar için Yıkıcılar bildirimin ters sırada çağırılır.

```cpp
// order_of_destruction.cpp
#include <cstdio>

struct A1      { virtual ~A1() { printf("A1 dtor\n"); } };
struct A2 : A1 { virtual ~A2() { printf("A2 dtor\n"); } };
struct A3 : A2 { virtual ~A3() { printf("A3 dtor\n"); } };

struct B1      { ~B1() { printf("B1 dtor\n"); } };
struct B2 : B1 { ~B2() { printf("B2 dtor\n"); } };
struct B3 : B2 { ~B3() { printf("B3 dtor\n"); } };

int main() {
   A1 * a = new A3;
   delete a;
   printf("\n");

   B1 * b = new B3;
   delete b;
   printf("\n");

   B3 * b2 = new B3;
   delete b2;
}

Output: A3 dtor
A2 dtor
A1 dtor

B1 dtor

B3 dtor
B2 dtor
B1 dtor
```

### <a name="virtual-base-classes"></a>Sanal temel sınıflar

Sanal temel sınıflar için Yıkıcılar, bir yönlendirilmiş çevrimsiz grafiğinde görünüşlerinin ters sırada çağrılır (ilk, soldan sağa, postorder çapraz geçiş). Aşağıdaki şekilde bir devralma grafiği gösterilmektedir.

![Sanal temel sınıfları gösteren devralma grafiği](../cpp/media/vc392j1.gif "Sanal temel sınıfları gösteren devralma grafiği") <br/>
Sanal temel sınıfları gösteren devralma grafiği

Aşağıda, şekilde gösterilen sınıfların Sınıf kafaları listelenmektedir.

```cpp
class A
class B
class C : virtual public A, virtual public B
class D : virtual public A, virtual public B
class E : public C, public D, virtual public B
```

Türündeki bir nesnenin sanal temel sınıflarının yok etme sırasını tespit etmek için `E` , derleyici aşağıdaki algoritmayı uygulayarak bir liste oluşturur:

1. Grafikteki en derin noktadan başlayarak (Bu durumda,) grafiğin sol tarafında yer alın `E` .

1. Tüm düğümler ziyaret edilene kadar soltward traversals gerçekleştirin. Geçerli düğümün adını aklınızda edin.

1. Anımsanacak düğümün bir sanal temel sınıf olup olmadığını öğrenmek için önceki düğümü (aşağı ve sağa doğru) yeniden ziyaret edin.

1. Anımsanan düğüm bir sanal taban sınıfınse, zaten girilip girilmediğini görmek için listeyi tarayın. Sanal bir temel sınıf değilse, bunu yoksayın.

1. Anımsanan düğüm henüz listede yoksa, listenin en altına ekleyin.

1. Sağ taraftaki bir sonraki yol üzerinde grafiği yukarı ve aşağı doğru gez.

1. 2. adıma gidin.

1. Son yukarı doğru yol tükendiğinde, geçerli düğümün adını aklınızda bulunur.

1. 3. adıma gidin.

1. Alt düğüm geçerli düğüm olana kadar bu işleme devam edin.

Bu nedenle, sınıfı için `E` yok etme sırası şu şekilde olur:

1. Sanal olmayan temel sınıf `E` .

1. Sanal olmayan temel sınıf `D` .

1. Sanal olmayan temel sınıf `C` .

1. Sanal temel sınıf `B` .

1. Sanal temel sınıf `A` .

Bu işlem, benzersiz girişlerin sıralı bir listesini oluşturur. Sınıf adı iki kez görünmez. Liste oluşturulduktan sonra, bu, ters sırada ve listedeki her bir sınıfın yıkıcısında birinciden birincine çağırılır.

Oluşturma veya yok etme sırası öncelikli olarak, bir sınıftaki oluşturucular veya Yıkıcılar, ilk olarak oluşturulan veya daha az kalıcı hale getiren diğer bileşene bağlı olduğunda (örneğin, `A` yukarıda gösterilen şekilde), `B` kodu yürütüldüğünde hala mevcut olmaya güveniliyorsa veya bunun tersini yapar.

Devralma grafiğindeki sınıflar arasında bu tür bağımlılıklar, daha sonra en soldaki yol olan ve böylece oluşturma ve yok etme sırasını değiştiren sınıflar değişeceğinden,

### <a name="non-virtual-base-classes"></a>Sanal olmayan taban sınıflar

Sanal olmayan taban sınıflar için Yıkıcılar, temel sınıf adlarının bildirildiği ters sırada çağırılır. Aşağıdaki sınıf bildirimini göz önünde bulundurun:

```cpp
class MultInherit : public Base1, public Base2
...
```

Önceki örnekte, için yıkıcısı, `Base2` için yıkıcının önüne çağırılır `Base1` .

## <a name="explicit-destructor-calls"></a>Açık yıkıcı çağrıları

Bir yok ediciyi açıkça çağırmak nadiren gereklidir. Ancak, mutlak adreslerde yerleştirilen nesnelerin temizleme işlemini yapmak yararlı olabilir. Bu nesneler, genellikle **`new`** bir yerleştirme bağımsız değişkeni alan Kullanıcı tanımlı bir operatör kullanılarak ayrılır. **`delete`** İşleç, ücretsiz depodan ayrılmadığından bu belleği serbest bırakılamaz (daha fazla bilgi için bkz. [yeni ve silme işleçleri](../cpp/new-and-delete-operators.md)). Ancak yok edici için yapılan bir çağrı uygun temizleme işlemini yapabilir. `s` sınıfından bir nesne (`String`) için yok ediciyi açıkça çağırmak istediğinizde, aşağıdaki deyimleri kullanın:

```cpp
s.String::~String();     // non-virtual call
ps->String::~String();   // non-virtual call

s.~String();       // Virtual call
ps->~String();     // Virtual call
```

Yok ediciler için yapılan açık çağrıların gösterimi (daha önce gösterilmiştir), türün bir yok edici tanımlayıp tanımlamadığından bağımsız olarak kullanılabilir. Bu, tür için bir yok edicinin tanımlanmış olup olmadığını bilmeden böyle açık çağrılar yapmanızı sağlar. Hiçbiri değerinin tanımlandığı bir yok edici için yapılan açık çağrının hiçbir etkisi olmaz.

## <a name="robust-programming"></a>Güçlü programlama

Bir sınıf, kaynak alıyorsa ve kaynağı güvenli bir şekilde yönetmek için bir yıkıcı gerektirir ve muhtemelen bir kopya Oluşturucu ve bir kopya ataması uygular.

Bu özel işlevler Kullanıcı tarafından tanımlanmamışsa, derleyici tarafından örtülü olarak tanımlanmıştır. Örtük olarak oluşturulan oluşturucular ve atama işleçleri, bir nesne bir kaynağı yönetirken neredeyse kesinlikle yanlış olan yüzeysel, üye tabanlı kopyalamayı gerçekleştirir.

Sonraki örnekte, örtük olarak oluşturulan kopya Oluşturucu işaretçileri yapar `str1.text` ve `str2.text` aynı belleğe başvurur ve ' den döntiğimiz zaman, `copy_strings()` tanımsız bir davranış olan bu bellek iki kez silinir:

```cpp
void copy_strings()
{
   String str1("I have a sense of impending disaster...");
   String str2 = str1; // str1.text and str2.text now refer to the same object
} // delete[] _text; deallocates the same memory twice
  // undefined behavior
```

Açıkça bir yıkıcı, kopya Oluşturucusu veya kopya atama işleci tanımlama, taşıma oluşturucusunun ve taşıma atama işlecinin örtük tanımını önler. Bu durumda, taşıma işlemleri sağlamamakta olma başarısız olur, ancak kopyalama, kaçırılan bir iyileştirme fırsatıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Kopya oluşturucuları ve kopya atama Işleçleri](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md)</br>
[Taşıma Oluşturucuları ve taşıma atama Işleçleri](../cpp/move-constructors-and-move-assignment-operators-cpp.md)
