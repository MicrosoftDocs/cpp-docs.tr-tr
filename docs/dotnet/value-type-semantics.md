---
title: Değer türü anlamları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interior_ptr keyword [C++]
- virtual functions, value types
- inheritance, value types
- pinning pointers
- pin_ptr keyword [C++]
- __pin keyword
ms.assetid: 7f065589-ad25-4850-baf1-985142e35e52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 44662f2ad8e79712b4aab17e2784a72e01ec4116
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171860"
---
# <a name="value-type-semantics"></a>Değer Türü Anlamları
Değer türü anlamları, Visual C++ için C++ için Yönetilen Uzantılar'dan değiştirilmiştir.  
  
 C++ belirtimi için Yönetilen Uzantılar kullanılan kurallı basit değer türü şöyledir:  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
```  
  
 Yönetilen Uzantılar ' (burada forms 2 ve 3 mantıksal olarak aynıdır) size bir değer türü dört söz dizimi çeşitlemelerini sahip olabilir:  
  
```  
V v = { 0 };       // Form (1)  
V *pv = 0;         // Form (2) an implicit form of (3)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0; // Form (4) must be local   
```  
  
## <a name="invoking-inherited-virtual-methods"></a>Devralınan sanal yöntemleri çağırma  
 `Form (1)` kurallı değer nesnesidir ve onu makul iyi, birisi devralınan sanal bir yöntem gibi çağrılacak çalıştığında dışında anlaşılmalıdır `ToString()`. Örneğin:  
  
```  
v.ToString(); // error!  
```  
  
 İçinde geçersiz olduğundan bu yöntemi çağırmak için `V`, derleyici temel sınıfın ilişkili sanal tablo erişiminizin olması gerekir. Değer türleri (vptr) sanal tablosuyla ilişkilendirilmiş işaretçi olmadan durum depolama olduğundan, bu gerektiren `v` Kutulu. Yönetilen Uzantılar dil tasarımında örtük kutulama desteklenmiyor ancak olarak Programcı tarafından açıkça belirtilmelidir  
  
```  
__box( v )->ToString(); // Managed Extensions: note the arrow  
```  
  
 Bu tasarım arkasındaki birincil neden pedagojik: temel mekanizma aynen 'değer türünde bir örnek Maliyet' anlamanız için programcı görünür olması gerekir. Olan `V` örneği içerecek şekilde `ToString`, kutulama gerekli olmaz.  
  
 Nesne, ancak temel maliyeti kutulama kendisi, açıkça kutulama sözcük karmaşıklığını yeni sözdiziminde kaldırılır:  
  
```  
v.ToString(); // new syntax  
```  
  
 Ancak, büyük olasılıkla açık bir örneği sağlanmayan maliyetine Sınıf Tasarımcısı yanıltıcı `ToString` yöntemi içinde `V`. Örtük kutulamayı tercihin nedeni genellikle yalnızca bir sınıf Tasarımcısı varken, kullanıcılar kim hiçbiri değiştirme özgürlüğü sahip olabilir, sınırsız sayıda olduğu `V` açık kutulamayı kaldırmak için.  
  
 Geçersiz kılma örneği sağlayan gerekip gerekmediğini belirlemek üzere ölçüt `ToString` arasında bir değer sınıfı kullanımları konumunu ve sıklığı olmalıdır. Nadiren çağrılırsa, da Elbette tanımında az faydası yoktur. Uygulamanın kullanıcı olmayan alanlarda çağrılırsa, benzer şekilde, bunu ekleyerek sorunlarında de olmayan uygulama için genel performans ekler. Alternatif olarak, bir paketlenmiş değere izleme işleyicisi tutabilirsiniz ve o tanıtıcının çağrılar kutulama gerektirmez.  
  
## <a name="there-is-no-longer-a-value-class-default-constructor"></a>Artık bir değer sınıfı varsayılan oluşturucu yok  
 Başka bir değer türü arasındaki Yönetilen Uzantılar ve yeni sözdizimini varsayılan bir oluşturucu desteği kaldırılmasını farktır. Durumlar, ilişkili varsayılan oluşturucu çağırmadan değer türünün bir örneği CLR oluşturabilirsiniz yürütme sırasında olduğundan budur. Diğer bir deyişle, bir değer türü içinde varsayılan bir oluşturucu desteklemek için Yönetilen Uzantılar altında denemesi pratikte garanti edilmez. Garanti verildiğinde, bunu yerine tamamen bırakma desteği olan kendi uygulamasında belirleyici olması daha iyi olmasını Keçeli.  
  
 Bu başlangıçta göründüğü gibi bozuk değildir. Her bir değer türü nesnesinin otomatik olarak sıfırlanmasını olmasıdır (diğer bir deyişle, her tür için varsayılan değeri başlatılır). Sonuç olarak, yerel bir örnek üyeleri hiçbir zaman tanımlanmamış. Bu bağlamdaki Önemsiz varsayılan bir oluşturucu tanımlama yeteneği kaybı gerçekten kaybı hiç - değildir ve aslında CLR tarafından gerçekleştirildiğinde daha verimli olur.  
  
 Bir kullanıcı, Yönetilen Uzantılar Önemsiz olmayan varsayılan bir oluşturucu tanımladığında sorunudur. Bu eşleme yeni sözdizimine sahip. Kod Oluşturucu içinde kullanıcı tarafından açıkça çağrılacak gereken bir adlandırılmış başlatma yöntemiyle geçirilmesi gerekir.  
  
 Yeni söz diziminde değer türü nesnesi bildirimi, aksi halde değişmeden kalır. Bu aşağı tarafında değer türleri aşağıdaki nedenlerle yerel türler kaydırma için tatmin edici olmadığını bulunur:  
  
-   Değer türünde yıkıcı desteği yoktur. Diğer bir deyişle, bir dizi eylemi bir nesnenin ömrü ucu tarafından tetiklenen otomatik hale getirmek için bir yolu yoktur.  
  
-   Yerel bir sınıf, sonra yerel yığında ayrılan bir işaretçi olarak yalnızca bir yönetilen türü içinde bulunabilir.  
  
 Değer türü yerine bir başvuru türü çift yığın ayırma önlemek için küçük bir yerel sınıfı sarmalama isteriz: yerel tür tutmak için yerel yığın ve yönetilen sarmalayıcıyı tutmak için CLR yığını. Değer türü içinde yerel sınıfı sarmalama yönetilen yığını engellemenize olanak sağlar, ancak yerel yığın bellek kazanılmasını otomatikleştirmek için bir yol sağlar. Başvuru türleri Önemsiz olmayan yerel sınıflarda sarmalamak için içinde yalnızca mümkün yönetilen türüdür.  
  
## <a name="interior-pointers"></a>İç işaretçiler  
 `Form (2)` ve `Form (3)` bu world sonraki (diğer bir deyişle, yönetilen veya yerel her şey) neredeyse her şeyi yukarıdaki karşılayabilir. Bu nedenle, örneğin, aşağıdakilerin tümü Yönetilen Uzantılar'izin verilir:  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
  
V v = { 0 };  // Form (1)  
V *pv = 0;  // Form (2)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0;  // Form (4)  
  
R* r;  
  
pv = &v;            // address a value type on the stack  
pv = __nogc new V;  // address a value type on native heap  
pv = pvgc;          // we are not sure what this addresses  
pv = pvbx;          // address a boxed value type on managed heap  
pv = &r->vr;        // an interior pointer to value type within a  
                    //    reference type on the managed heap  
```  
  
 Bu nedenle, bir `V*` yerel bloğu içinde bir konuma karşılayabilirsiniz (ve bu nedenle sarkan), yerel içinde genel kapsamda (örneğin, adresleri nesne zaten silinmişse), CLR yığınına yığın (ve onu gerekir, bu nedenle izlenir yeniden konumlandırılmasını çöp toplama sırasında) hem de iç (iç işaretçi, bu denir ayrıca şeffaf bir şekilde izlenir) CLR yığınındaki başvuru nesnesinin içinde.  
  
 Yönetilen Uzantılar'yerel yönlerini ayırmak için bir yolu yoktur bir `V*`; diğer bir deyişle, kendi (dahil), onu bir nesne veya alt nesne yönetilen yığında adresleme olasılığını işleme işlem görür.  
  
 Yeni sözdiziminde değer türü işaretçi iki türe ayrılmıştır: `V*`, CLR olmayan yığın konumlarına ve iç işaretçi sınırlı olduğu `interior_ptr<V>`, hangi sağlar ancak Yönetilen yığın içinden bir adres gerektirmez.  
  
```  
// may not address within managed heap   
V *pv = 0;   
  
// may or may not address within managed heap  
interior_ptr<V> pvgc = nullptr;   
```  
  
 `Form (2)` ve `Form (3)` Yönetilen Uzantılar ' eşlenir `interior_ptr<V>`. `Form (4)` İzleme işleyicisidir. Yönetilen yığın Kutulu nesnenin tamamı giderir. Yeni sözdiziminde çevrilmiş bir `V^`,  
  
```  
V^ pvbx = nullptr; // __box V* pvbx = 0;    
```  
  
 Yönetilen tüm yeni sözdiziminde iç işaretçiler eşlemek uzantılar aşağıdaki bildirimler. (Değer türleri içinde oldukları `System` ad.)  
  
```  
Int32 *pi;   // => interior_ptr<Int32> pi;  
Boolean *pb; // => interior_ptr<Boolean> pb;  
E *pe;       // => interior_ptr<E> pe; // Enumeration  
```  
  
 Diğer adlar içindeki türlere olarak hizmet rağmen yerleşik türleri yönetilen türler, kabul edilmeyen `System` ad alanı. Bu nedenle aşağıdaki eşlemeler Yönetilen Uzantılar ve yeni sözdizimini arasında doğru tutun:  
  
```  
int * pi;     // => int* pi;  
int __gc * pi2; // => interior_ptr<int> pi2;  
```  
  
 Çevirirken bir `V*` varolan programınızı en koruyucu strateji etmektir her zaman Aç bir `interior_ptr<V>`. Yönetilen Uzantılar altında nasıl değerlendirilme budur. Yeni sözdiziminde Programcı belirterek değer türlerini yönetilmeyen yığın adreslerine kısıtlama seçeneği vardır `V*` yerine iç işaretçi. Programınızı çevirirken, tüm kullanımlarını geçişli kapatma yapın ve hiçbir atanan adresi yönetilen yığında olduğundan emin olarak bırakarak `V*` uygundur.  
  
## <a name="pinning-pointers"></a>İşaretçileri sabitleme  
 Çöp toplayıcı isteğe bağlı olarak farklı konumlara yığında CLR yığınındaki genellikle sıkıştırma aşaması sırasında bulunan nesneleri taşıyabilir. Bu taşıma tanıtıcıları, izleme başvuruları ve bu varlıkları saydam güncelleştirme iç işaretçiler izleme için bir sorun değildir. Kullanıcı çalışma zamanı ortamı dışında CLR yığınındaki nesnenin adresini geçtiyse Bu taşıma ancak bir sorun olur. Bu durumda, nesne volatile hareketini bir çalışma zamanı hatası yol açabilir. Taşınan biz gerekir yerel olarak sabitlemek bunları konumlarına dış kullanımlarını kapsamını için bunlardan gibi muafiyet nesnelere.  
  
 Yönetilen Uzantılar, bir *sabitleme işaretçisi* bir işaretçi bildirimiyle niteleme tarafından bildirilen `__pin` anahtar sözcüğü. Yönetilen Uzantılar belirtiminden biraz değiştirilmiş bir örnek aşağıda verilmiştir:  
  
```  
__gc struct H { int j; };  
  
int main()   
{  
   H * h = new H;  
   int __pin * k = & h -> j;  
  
   // ...  
};  
```  
  
 Yeni dil tasarımında, iç işaretçi benzer bir sözdizimi ile sabitleme işaretçisi bildirildi.  
  
```  
ref struct H  
{  
public:  
   int j;  
};  
  
int main()  
{  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
  
   // ...  
}  
```  
  
 Yeni söz dizimi altındaki sabitleme işaretçisi, iç işaretçi özel bir durumdur. Sabitleme işaretçisi özgün kısıtlamalar kalır. Örneğin, bir parametre olarak kullanılamaz veya dönüş türü bir yöntem; yalnızca yerel nesnede bildirilebilir. Birkaç ek kısıtlamalar, ancak yeni sözdiziminde eklenmiştir.  
  
 Varsayılan değer sabitleme işaretçisinin `nullptr`değil `0`. A `pin_ptr<>` başlatılmamış veya atanan `0`. Tüm atamalarını `0` var olan kodda şekilde değiştirilmesi gerekir `nullptr`.  
  
 Yönetilen Uzantılar belirtiminden alınan aşağıdaki örnekte olduğu gibi tüm bir nesneyi adres için Yönetilen Uzantılar altındaki sabitleme işaretçisi verilmişti:  
  
```  
__gc class G {  
public:  
   void incr(int* pi) { pi += 1; }  
};  
__gc struct H { int j; };  
void f( G * g ) {  
   H __pin * pH = new H;     
   g->incr(& pH -> j);     
};  
```  
  
 Yeni sözdiziminde tüm nesneyi sabitleme döndürdüğü `new` ifadesi desteklenmiyor. Bunun yerine, iç üye adresini sabitlenmiş gerekiyor. Örneğin,  
  
```  
ref class G {  
public:  
   void incr(int* pi) { *pi += 1; }  
};  
ref struct H { int j; };  
void f( G^ g ) {  
   H ^ph = gcnew H;  
   Console::WriteLine(ph->j);  
   pin_ptr<int> pj = &ph->j;  
   g->incr(  pj );  
   Console::WriteLine(ph->j);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Değer türleri ve davranışları (C + +/ CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md)   
 [interior_ptr (C + +/ CLI)](../windows/interior-ptr-cpp-cli.md)   
 [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)