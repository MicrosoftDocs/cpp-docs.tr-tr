---
title: "Yıkıcılar (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- objects [C++], destroying
- Visual C++, destructors
- destroying objects, destructors
- ~ operator [C++], specifying destructors
- destructors, about destructors
- destructors, C++
ms.assetid: afa859b0-f3bc-4c4d-b250-c68b335b6004
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4fb96ae6763d9b2ca86f99ee42a10f56e93d7e3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="destructors-c"></a>Yıkıcılar (C++)
Bir yıkıcı nesne kapsam dışında geçip geçmeyeceğini veya bir çağrı tarafından açıkça yok olduğunda çağrılan otomatik olarak bir üye işlevdir `delete`. Bir yıkıcı bir tilde tarafından öncesinde sınıfı, aynı ada sahip (`~`). Örneğin, `String` sınıfının yok edicisi şu şekilde bildirilir: `~String()`. Bir yıkıcı tanımlamıyorsa derleyici bir varsayılan sağlar; birçok sınıflar için bu yeterlidir. Bellek kendi işaretçileri bunların işaret veya yalnızca özel bir yıkıcı sınıfı serbest bırakılması gereken sistem kaynaklarını işleyicilerine depoladığında tanımlamak gerekir.

`String` sınıfıyla ilgili aşağıdaki bildirimi dikkate alın:  
  
```  
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
  
 Önceki örnekte, `String::~String` yok edicisi, metin depolama için dinamik olarak ayrılan alanı kaldırmak için `delete` işlecini kullanmaktadır.  
  
## <a name="delcaring-destructors"></a>Delcaring Yıkıcılar  
 Yıkıcılar işlevleri sınıfı bir tilde tarafından preceded ancak aynı ada sahip olan (`~`)  
  
 Çeşitli kurallar Yıkıcılar bildirimi kapsar. Yıkıcılar:  
  
-   Bağımsız değişkenler kabul etmez.  
  
-   Bir değer döndürmeyen (veya `void`).  
  
-   Olarak bildirilemez **const**, `volatile`, veya **statik**. Nesneleri yok etme olarak bildirilen için ancak, bunlar çağrılabilir **const**, `volatile`, veya **statik**.  
  
-   Olarak bildirilen **sanal**. Sanal yıkıcıları kullanma, size nesneleri tipine bilmeden yok edebilir — nesne için doğru yıkıcı sanal işlev mekanizması kullanılarak çağrılır. Yıkıcılar de saf sanal işlevleri olarak soyut sınıflar için bildirilebilir olduğunu unutmayın.  
  
## <a name="using-destructors"></a>Yıkıcıları kullanma  
 Aşağıdaki olaylardan biri gerçekleştiğinde yok ediciler çağrılır:  

-   Blok kapsamlı bir yerel (otomatik) nesne kapsam dışına gider.  

-   Kullanılarak ayrılmış bir nesne **yeni** işleci açıkça serbest kullanarak **silmek**.   
  
-   Geçici bir nesnenin kullanım ömrü sona erer.  
  
-   Bir program sona erer ve genel veya statik nesneler kalır.  
  
-   Yok edici, işlevinin tam adı kullanılarak çağrılır.
  
 Yok ediciler, sınıf üyesi işlevlerini serbestçe çağırabilir ve sınıf üyesi verilerine erişebilir.
  
 Yıkıcıları kullanma iki kısıtlamalar vardır:
 - adresini alamıyor
-  türetilmiş sınıflar temel sınıf yıkıcı devralmaz.
  
## <a name="order-of-destruction"></a>Yok etme sırası  
 Bir nesne kapsam dışında gider veya silinirse, kendi tam yok etme olaylar dizisini aşağıdaki gibidir:  
  
1.  Sınıfının yıkıcı denir ve yıkıcı işlevinin gövdesi yürütülür.  
  
2.  Statik olmayan üye nesneleri için Yıkıcılar sınıfı bildiriminde görüntüleneceği ters sırada denir. Bu üyeler yapısında kullanılan isteğe bağlı üye başlatma listesi oluşturma veya yok etme sırası etkilemez.   
  
3.  Sanal olmayan tabanlı sınıflar için Yıkıcılar bildirimi ters sırada denir.  
  
4.  Sanal tabanlı sınıflar için Yıkıcılar bildirimi ters sırada denir.  
  
```  
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
 Sanal tabanlı sınıflar için Yıkıcılar (derinliği ilk, soldan sağa, postorder geçişi) yönlendirilmiş Çevrimsiz Grafik görünümlerini ters sırada denir. Aşağıdaki şekilde bir Devralma Grafiği gösterir.  
  
 ![Sanal Taban sınıflar gösteren Devralma Grafiği](../cpp/media/vc392j1.gif "vc392J1")  
Sanal Taban sınıflar gösteren Devralma Grafiği  
  
 Aşağıdaki çizimde gösterilen sınıfların sınıfı kafa listeler.  
  
```  
class A  
class B  
class C : virtual public A, virtual public B  
class D : virtual public A, virtual public B  
class E : public C, public D, virtual public B  
```  
  
 Sanal Taban sınıflar türünde bir nesnenin yok etme sırası belirlemek için `E`, aşağıdaki algoritması uygulayarak derleyici bir liste oluşturur:  
  
1.  Grafikte derin noktada başlayan sol, grafik çapraz geçiş (Bu durumda, `E`).  
  
2.  Tüm düğümleri ziyaret kadar leftward çapraz geçişlerine gerçekleştirin. Geçerli düğümün adını not edin.  
  
3.  Önceki düğüm (aşağı ve sağa) anımsanacak düğüm sanal bir temel sınıf olup olmadığını öğrenmek için yeniden ziyaret.  
  
4.  Anımsanan düğümü sanal bir temel sınıf ise, onu zaten girilmiş olup olmadığını görmek için listenin tarayın. Sanal bir temel sınıf değilse, yok sayın.  
  
5.  Anımsanan düğümü henüz listede değilse, listenin altına ekleyin.  
  
6.  Grafiğin yukarı ve sonraki yol boyunca sağa geçiş.  
  
7.  2. adıma geçin.  
  
8.  Son yukarı yolu kaldığında, geçerli düğümün adını not edin.  
  
9. 3. adıma gidin.  
  
10. Geçerli düğüm alt düğüm yeniden olana kadar bu işleme devam edin.  
  
 Bu nedenle, sınıf için `E`, yok etme sırası:  
  
1.  Sanal olmayan taban sınıf `E`.  
  
2.  Sanal olmayan taban sınıf `D`.  
  
3.  Sanal olmayan taban sınıf `C`.  
  
4.  Sanal taban sınıfı `B`.  
  
5.  Sanal taban sınıfı `A`.  
  
 Bu işlemin benzersiz girişleri sıralı bir listesi oluşturur. Sınıf adı iki kez görüntülenir. Listenin oluşturulan sonra ters sırada İlerliyor ve yıkıcı ilk son listesinde sınıfların her biri için çağrılır.  
  
 Oluşturucular ya da bir sınıf yıkıcılarda ilk ya da kalıcı artık oluşturulan diğer bileşene bağlı yapım veya yok etme sırası öncelikle önemlidir — Örneğin, varsa yıkıcı için `A` (yukarıda gösterilen şekildeki) dayanıyordu üzerinde `B` hala zaman kendi kod yürütülen, var olan veya tam tersi.  
  
 Bu tür bir Devralma Grafiği sınıfları birbirine kendiliğinden tehlikeli olduklarından daha sonra türetilmiş sınıflar, böylece oluşturma ve yok etme sırası değiştirme yolun soldaki olduğu değiştirebilirsiniz.  
  
### <a name="nonvirtual-base-classes"></a>Sanal olmayan tabanlı sınıflar  
 Sanal olmayan tabanlı sınıflar için Yıkıcılar temel sınıf adları bildirilen ters sırada denir. Aşağıdaki sınıf bildirimi göz önünde bulundurun:  
  
```  
class MultInherit : public Base1, public Base2  
...  
```  
  
 Yıkıcı için önceki örnekte `Base2` yıkıcı için önce adlı `Base1`.  
  
## <a name="explicit-destructor-calls"></a>Açık yıkıcı çağrıları  
 Bir yok ediciyi açıkça çağırmak nadiren gereklidir. Ancak, mutlak adreslerde yerleştirilen nesnelerin temizleme işlemini yapmak yararlı olabilir. Bu nesneler kullanıcı tanımlı kullanılarak yaygın olarak ayrılmış **yeni** yerleştirme bağımsız değişken işleci. **Silmek** işleci boş depolama alanından ayrılmamış çünkü bu bellek ayırması olamaz (daha fazla bilgi için bkz: [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md)). Ancak yok edici için yapılan bir çağrı uygun temizleme işlemini yapabilir. `s` sınıfından bir nesne (`String`) için yok ediciyi açıkça çağırmak istediğinizde, aşağıdaki deyimleri kullanın:  
  
```  
s.String::~String();     // Nonvirtual call  
ps->String::~String();   // Nonvirtual call  
  
s.~String();       // Virtual call  
ps->~String();     // Virtual call  
```  
  
 Yok ediciler için yapılan açık çağrıların gösterimi (daha önce gösterilmiştir), türün bir yok edici tanımlayıp tanımlamadığından bağımsız olarak kullanılabilir. Bu, tür için bir yok edicinin tanımlanmış olup olmadığını bilmeden böyle açık çağrılar yapmanızı sağlar. Hiçbiri değerinin tanımlandığı bir yok edici için yapılan açık çağrının hiçbir etkisi olmaz.  
