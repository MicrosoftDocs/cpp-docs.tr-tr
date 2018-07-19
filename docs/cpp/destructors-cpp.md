---
title: Yıkıcılar (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], destroying
- Visual C++, destructors
- destroying objects, destructors
- ~ operator [C++], specifying destructors
- destructors, about destructors
- destructors, C++
ms.assetid: afa859b0-f3bc-4c4d-b250-c68b335b6004
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2bbe849f8ec9d47c73b7d909734df600957f3afd
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941791"
---
# <a name="destructors-c"></a>Yıkıcılar (C++)

Nesne kapsam dışına gider veya bir çağrı tarafından açıkça edildiğinde çağrılan otomatik olarak bir üye işlev bir yok Edicisi olan **Sil**. Bir yok edici bir tilde işareti tarafından öncesinde, sınıfı aynı ada sahip (`~`). Örneğin, `String` sınıfının yok edicisi şu şekilde bildirilir: `~String()`.

Bir yok edici tanımlamazsanız, derleyici varsayılan bir tane sağlar; birçok sınıflar için bu yeterli olur. Yalnızca sınıf serbest bırakılması gerektiği sistem kaynaklarının tanıtıcıları depoladığında, özel bir yok ediciyi tanımlayın gerekir veya kendi bellek işaretçileri bunlar üzerine gelin.

`String` sınıfıyla ilgili aşağıdaki bildirimi dikkate alın:

```cpp
// spec1_destructors.cpp
#include <string.h>

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
   if (_text)
      delete[] _text;
}

int main() {
   String str("The piper in the glen...");
}
```

Yukarıdaki örnekte, yok edici `String::~String` kullanan **Sil** metin depolama için dinamik olarak ayrılan alanı kaldırmak için işleci.

## <a name="declaring-destructors"></a>Yıkıcıları bildirme

Yok ediciler olan işlevleri tarafından bir tilde preceded ancak sınıf olarak aynı ada sahip (`~`)

Çeşitli kurallar, Yıkıcılar bildirimi kapsar. Yok ediciler:

- Bağımsız değişkenleri kabul etmez.

- Bir değer döndürmeyen (veya **void**).

- Olarak bildirilemez **const**, **geçici**, veya **statik**. Nesnelerin yok edilmesi olarak bildirilen ancak bunlar çağrılabilir **const**, **geçici**, veya **statik**.

- Olarak bildirilen **sanal**. Sanal yıkıcı kullanarak, nesneleri türlerine bilmeden yok edebilir: sanal işlev mekanizmasını kullanarak nesne doğru yok Edicisi çağrılır. Yıkıcılar da saf sanal işlevler soyut sınıflar için bildirilebilir olduğunu unutmayın.

## <a name="using-destructors"></a>Yıkıcıları kullanma

Aşağıdaki olaylardan biri gerçekleştiğinde yok ediciler çağrılır:

- Blok kapsamlı bir yerel (otomatik) nesne kapsam dışına gider.

- Nesneyi kullanarak ayrılan **yeni** işleci açık şekilde kaldırılır kullanarak **Sil**.

- Geçici bir nesnenin kullanım ömrü sona erer.

- Bir program sona erer ve genel veya statik nesneler kalır.

- Yok edici, işlevinin tam adı kullanılarak çağrılır.

Yok ediciler, sınıf üyesi işlevlerini serbestçe çağırabilir ve sınıf üyesi verilerine erişebilir.

Yok edicilerin kullanımına ilişkin iki kısıtlama vardır:

- Kendi adresi alınamaz.

- Türetilmiş sınıfların kendi temel sınıfın yok Edicisi devralmaz.

## <a name="order-of-destruction"></a>Yok etme sırası

Bir nesne kapsam dışına gider veya silinirse, kendi tam yok etme olayları dizisini aşağıdaki gibidir:

1. Sınıfın yok Edicisi çağrılır ve yok edici işlevinin gövdesi yürütülür.

1. Sınıf bildirimi içinde göründükleri ters sırada statik olmayan üye nesneler için yok ediciler çağrılır. Bu üyeleri oluşumunu kullanılan isteğe bağlı üye başlatma listesi oluşturma veya yok etme sırası etkilemez.

1. Sanal olmayan tabanlı sınıflar için Yıkıcılar bildirimin ters sırada çağrılır.

1. Sanal tabanlı sınıflar için Yıkıcılar bildirimin ters sırada çağrılır.

```cpp
// order_of_destruction.cpp
#include <stdio.h>

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

Sanal tabanlı sınıflar için Yıkıcılar görünümlerini yönlendirilmiş Çevrimsiz grafik (ilk derinlik, soldan sağa, postorder geçişi), ters sırada çağrılır. Aşağıdaki şekil, bir Devralma Grafiği gösterir.

![Sanal temel sınıflar gösteren Devralma Grafiği](../cpp/media/vc392j1.gif "vc392J1")

Sanal temel sınıflar gösteren Devralma Grafiği

Aşağıdaki çizimde gösterilen sınıfların için sınıf heads listeler.

```cpp
class A
class B
class C : virtual public A, virtual public B
class D : virtual public A, virtual public B
class E : public C, public D, virtual public B
```

Sanal temel sınıflar türünde bir nesnenin yok edilmesini sırasını belirlemek için `E`, derleyici aşağıdaki algoritması uygulayarak bir liste oluşturur:

1. Graftaki en derin noktada başlayan sol, grafiğin çapraz geçişini yapar (Bu durumda, `E`).

1. Tüm düğümleri ziyaret kadar leftward çapraz geçişleri gerçekleştirin. Geçerli düğüm adını not edin.

1. Önceki düğüm (aşağı ve sağa doğru) anımsanacak düğüm sanal bir temel sınıf olup olmadığını öğrenmek için tekrar uğrayın.

1. Sanal bir temel sınıf hatırlanan düğümü ise, zaten girilmiş olup olmadığını görmek için listenin tarayın. Sanal bir temel sınıf değilse yoksayar.

1. Hatırlanan düğüm henüz listede değilse, listenin sonuna ekleyin.

1. Yukarı ve sonraki yol boyunca grafiği sağa çapraz geçirin.

1. 2. adıma gidin.

1. Son yukarı yolu kaldığında, geçerli düğüm adını not edin.

1. 3. adıma gidin.

1. Alt düğümü geçerli düğüm yeniden olana kadar bu işleme devam edin.

Bu nedenle, sınıf için `E`, yok etme sırası:

1. Sanal olmayan taban sınıf `E`.

1. Sanal olmayan taban sınıf `D`.

1. Sanal olmayan taban sınıf `C`.

1. Sanal temel sınıfın `B`.

1. Sanal temel sınıfın `A`.

Bu işlem, benzersiz girişleri sıralanmış bir listesini oluşturur. Sınıf adı iki kez görünüyor. Liste oluşturulur, sonra ters sırada öğrendiniz ve son listesinde ilk sınıfların her birini yok Edicisi çağrılır.

Oluşturucuları veya yıkıcıları bir sınıfta ilk ya da kalıcı artık oluşturulan diğer bileşende kullanan, oluşturma veya yok etme sırası öncelikle önemlidir; Örneğin, yok Edicisi `A` (yukarıdaki şekildeki) yararlandı üzerinde `B` hala zaman, kod yürütüldüğünde, var olan ya da tam tersi.

Böyle bir Devralma Grafiği sınıfları birbirine kendiliğinden tehlikeli olduğu daha sonra türetilmiş sınıfları oluşturma ve yok etme sırası böylece değiştirme yolun en soldaki olduğu değiştirebilirsiniz.

### <a name="non-virtual-base-classes"></a>Sanal olmayan temel sınıflar

Sanal olmayan tabanlı sınıflar için Yıkıcılar temel sınıf adları bildirilen ters sırada çağrılır. Aşağıdaki sınıf bildiriminde göz önünde bulundurun:

```cpp
class MultInherit : public Base1, public Base2
...
```

Yukarıdaki örnekte, yok Edicisi `Base2` önce yok Edicisi çağrılır `Base1`.

## <a name="explicit-destructor-calls"></a>Açık yıkıcı çağrıları

Bir yok ediciyi açıkça çağırmak nadiren gereklidir. Ancak, mutlak adreslerde yerleştirilen nesnelerin temizleme işlemini yapmak yararlı olabilir. Bu nesneler, genellikle bir kullanıcı tarafından tanımlanan kullanarak ayrılır **yeni** yerleşimi bağımsız değişken alan işleci. **Sil** serbest depodan ayrılmamıştır, işleci bu belleği serbest bırakamaz (daha fazla bilgi için [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md)). Ancak yok edici için yapılan bir çağrı uygun temizleme işlemini yapabilir. `s` sınıfından bir nesne (`String`) için yok ediciyi açıkça çağırmak istediğinizde, aşağıdaki deyimleri kullanın:

```cpp
s.String::~String();     // non-virtual call
ps->String::~String();   // non-virtual call

s.~String();       // Virtual call
ps->~String();     // Virtual call
```

Yok ediciler için yapılan açık çağrıların gösterimi (daha önce gösterilmiştir), türün bir yok edici tanımlayıp tanımlamadığından bağımsız olarak kullanılabilir. Bu, tür için bir yok edicinin tanımlanmış olup olmadığını bilmeden böyle açık çağrılar yapmanızı sağlar. Hiçbiri değerinin tanımlandığı bir yok edici için yapılan açık çağrının hiçbir etkisi olmaz.
