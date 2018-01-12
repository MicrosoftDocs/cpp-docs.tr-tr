---
title: "Değişiklik yok edici anlamlarında | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- finalizers [C++]
- destructors, C++
ms.assetid: f1869944-a407-452f-b99a-04d8c209f0dc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c85ac0b082e8ea1dfbff007a68061e6a286390cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="changes-in-destructor-semantics"></a>Yok Edici Anlamlarında Yapılan Değişiklikler
Sınıf Yıkıcılar anlamları önemli ölçüde Yönetilen Uzantılar'dan C++ için Visual C++ için değiştirilmiştir.  
  
 Yönetilen Uzantılar'sınıf yıkıcı bir başvuru sınıfı içinde ancak değer sınıfı içinde değil verilmişti. Bu yeni söz diziminde değişmemiştir. Ancak, sınıf yıkıcı semantiği değiştirilmiştir. Bu konuda nedenlerine değiştirin ve varolan CLR kodunun çevirisini nasıl etkilediği açıklanır odaklanır. En önemli programcı düzeyinde değişiklik dil iki sürümü arasında olabilir.  
  
## <a name="non-deterministic-finalization"></a>Belirleyici sonlandırma  
 Bir nesneyle ilişkilendirilmiş bellek çöp toplayıcı tarafından ilişkili bir alınmadan önce `Finalize` yöntemi varsa, çağrılır. Nesne program ömrü bağlı değildir çünkü bu yöntem süper yıkıcı bir tür olarak düşünebilirsiniz. Biz bu sonlandırma bakın. Zamanlama yalnızca zaman veya hatta olup olmadığını bir `Finalize` yöntemi çağrıldığında tanımlanmadı. Çöp toplama belirleyici sonlandırma sergiler dediğimiz olduğunda ne demek isteriz budur.  
  
 Olmayan sonlandırma da dinamik bellek yönetimi ile çalışır. Kullanılabilir bellek olması hale geldiğinde atık toplayıcı devreye girer. Çöp altında ortamı, belleği boşaltmak için Yıkıcılar gereksiz toplanır. Bir nesne bir veritabanı bağlantısı veya tür kilit gibi kritik bir kaynak olduğunda olmayan sonlandırma iyi, ancak çalışmaz. Bu durumda, biz bu kaynak mümkün olan en kısa sürede serbest bırakmalısınız. Yerel dünyada, Oluşturucusu/yıkıcı çifti kullanılarak elde edilir. Nesne ömrü sona erer hemen içinde bildirilmiş yerel blok sona erdiğinde veya oluşturulan bir özel durum nedeniyle yığın açıldığı zaman yıkıcı yürütür ve kaynak otomatik olarak yayımlanır. Bu yaklaşım çok iyi çalışır ve Yönetilen Uzantılar altında yokluğu hissedilir.  
  
 CLR tarafından sağlanan çözümü uygulamak bir sınıftır `Dispose` yöntemi `IDisposable` arabirimi. Burada sorun `Dispose` kullanıcı tarafından açık bir çağrı gerektirir. Hataya yatkın budur. C# dili uygun form özel bir form Otomasyon sağlar `using` deyimi. Yönetilen Uzantılar tasarımı hiçbir özel destek sağlanır.  
  
## <a name="destructors-in-managed-extensions-for-c"></a>C++ için Yönetilen Uzantılar yıkıcılarda  
 Yönetilen Uzantılar ', aşağıdaki iki adımları kullanarak bir başvuru sınıfı yıkıcısı gerçekleştirilir:  
  
1.  Kullanıcı tarafından sağlanan yıkıcı dahili olarak yeniden adlandırıldı `Finalize`. Sınıfın temel sınıf varsa (unutmayın, CLR nesne modeli altında yalnızca tek devralma desteklenir), bir kullanıcı tarafından sağlanan kod yürütmeyi izleyen kendi sonlandırıcıyı çağrısına derleyici yerleştirir. Örneğin, Yönetilen Uzantılar dil belirtiminden alınan aşağıdaki basit hiyerarşi göz önünde bulundurun:  
  
```  
__gc class A {  
public:  
   ~A() { Console::WriteLine(S"in ~A"); }  
};  
  
__gc class B : public A {  
public:  
   ~B() { Console::WriteLine(S"in ~B");  }  
};  
```  
  
 Bu örnekte, iki yıkıcı adlandırılır `Finalize`. `B`kişinin `Finalize` bir sahip `A`'s `Finalize` çağrılmasını eklenen yöntemine `WriteLine`. Ne atık toplayıcı sonlandırma sırasında varsayılan olarak çağıracağı budur. İşte bu iç dönüşüm aşağıdaki gibi görünmelidir:  
  
```  
// internal transformation of destructor under Managed Extensions  
__gc class A {  
public:  
   void Finalize() { Console::WriteLine(S"in ~A"); }  
};  
  
__gc class B : public A {  
public:  
   void Finalize() {   
      Console::WriteLine(S"in ~B");  
      A::Finalize();   
   }  
};  
```  
  
1.  İkinci adımda derleyici sanal bir yıkıcıyı sentezler. Bu yıkıcı bizim Yönetilen Uzantılar kullanıcı programlarının doğrudan veya delete deyiminin bir uygulama aracılığıyla çağırma olduğu. Ayrıca, atık toplayıcısı tarafından hiçbir zaman çağrılır.  
  
     İki deyimleri bu birleştirilen yıkıcı içine yerleştirilir. Çağrı biridir `GC::SuppressFinalize` yönelik daha fazla hiçbir çağrılarını emin olmak için `Finalize`. İkincisi, gerçek çağrıdır `Finalize`, bu sınıf için kullanıcı tarafından sağlanan yıkıcı temsil eder. İşte ne bunu aşağıdaki gibi görünmelidir:  
  
```  
__gc class A {  
public:  
   virtual ~A() {  
      System::GC::SuppressFinalize(this);  
      A::Finalize();  
   }  
};  
  
__gc class B : public A {  
public:  
   virtual ~B() {  
      System::GC::SuppressFinalize(this);  
      B::Finalize();  
   }  
};  
```  
  
 Bu uygulama sınıfı açıkça kullanıcıya sağlar, ancak `Finalize` yöntemi şimdi yerine, hiçbir kontrole sahip, bir seferde, gerçekten ile tie değil `Dispose` yöntemi çözümü. Bu, Visual c++'ta değiştirilir.  
  
## <a name="destructors-in-new-syntax"></a>Yeni sözdiziminde Yıkıcılar  
 Yeni sözdiziminde yıkıcı dahili olarak yeniden adlandırılır `Dispose` yöntemi ve başvuru sınıfı otomatik olarak genişletilir uygulamak için `IDispose` arabirimi. Diğer bir deyişle, Visual C++ altında bize ait sınıflar çifti aşağıdaki gibi dönüştürülür:  
  
```  
// internal transformation of destructor under the new syntax  
__gc class A : IDisposable {  
public:  
   void Dispose() {   
      System::GC::SuppressFinalize(this);  
      Console::WriteLine( "in ~A");  
   }  
};  
  
__gc class B : public A {  
public:  
   void Dispose() {   
      System::GC::SuppressFinalize(this);  
      Console::WriteLine( "in ~B");    
      A::Dispose();   
   }  
};  
```  
  
 Yeni sözdizimi altında ya da bir yıkıcı açıkça çağrıldığında ya da zaman `delete` temel bir izleme işleyicisi uygulanan `Dispose` yöntemi otomatik olarak çağrılır. Çağrı türetilmiş bir sınıf olup olmadığını `Dispose` yöntemi temel sınıfın birleştirilen yöntemi kapanışında eklenir.  
  
 Ancak bu bize Bu süreç boyunca tüm belirleyici sonlandırma almaz. Ulaşmak için ek destek yerel başvuru nesnelerinin ihtiyacımız var. (Bu Yönetilen Uzantılar içinde benzer bir desteği vardır ve bu nedenle bir çeviri sorunu değildir.)  
  
## <a name="declaring-a-reference-object"></a>Başvuru nesnesi bildirme  
 Doğrudan erişilebilir gibi visual C++ yerel yığında ya da bir sınıf üyesi olarak bir başvuru sınıfın bir nesnesi bildirimi destekler. Yıkıcı ile ilişkilendirme ile birleştirildiğinde `Dispose` yöntem, sonuç sonlandırma semantiği başvuru türlerinde otomatik çağrılmasını olur.  
  
 İlk olarak, kaynak sınıf oluşturucusu üzerinden alımını nesne oluşturma görür, biz bizim başvuru sınıfı tanımlayın. İkincisi, sınıf yıkıcı içinde nesne oluşturduğunuzda edindiğiniz kaynak biz bırakın.  
  
```  
public ref class R {  
public:  
   R() { /* acquire expensive resource */ }  
   ~R() { /* release expensive resource */ }  
  
   // everything else...  
};  
```  
  
 Nesne türü adı kullanarak yerel olarak ancak eşlik eden şapka olmadan bildirildi. Üye seçimi nokta yapılır ve bir yöntemi çağırma nesnesinin tüm kullanır (`.`) ok yerine (`->`). İlişkili bir yıkıcı bloğun sonunda dönüştürülmüş `Dispose`, aşağıda gösterildiği gibi otomatik olarak çağrılır:  
  
```  
void f() {  
   R r;   
   r.methodCall();  
  
   // r is automatically destructed here -  
   // that is, r.Dispose() is invoked  
}  
```  
  
 İle `using` deyimi içinde C# bu değil ayrılmaları tüm türleri başvuru temel CLR kısıtlamasına CLR yığında ayrılmış olmalıdır. Temel alınan semantiğini değişmeden kalır. Kullanıcı eşdeğer aşağıdaki yazmıştır (ve olasılıkla derleyici tarafından gerçekleştirilen iç dönüşüm budur):  
  
```  
// equivalent implementation  
// except that it should be in a try/finally clause  
void f() {  
   R^ r = gcnew R;   
   r->methodCall();  
  
   delete r;  
}  
```  
  
 Gerçekte, yeni sözdiziminde Yıkıcılar yeniden oluşturucularla otomatik bir edinme/sürüm eşleştirilmelidir mekanizması bağlı bir yerel nesnesinin ömrü.  
  
## <a name="declaring-an-explicit-finalize"></a>Bir Açık Sonlandırıcı Bildirme  
 Anlatıldığı gibi yeni sözdiziminde yıkıcı içine oluşturulan `Dispose` yöntemi. Yıkıcı açıkça değil çağrıldığında, atık toplayıcı sonlandırma sırasında eskisi ilişkili bir bulamayacaksınız, yani `Finalize` nesnesinin yöntemi. Yok etme ve sonlandırma desteklemek için bir sonlandırıcı sağlaması için özel bir sözdizimi sunulmuştur. Örneğin:  
  
```  
public ref class R {  
public:  
   !R() { Console::WriteLine( "I am the R::finalizer()!" ); }  
};  
```  
  
 `!` Önektir tilde benzer (`~`), bir sınıf yıkıcı sunar - diğer bir deyişle, sınıfın adını önek bir belirteç ömür sonrası yöntemlerin her ikisi de içerir. Varsa birleştirilen `Finalize` yöntemi oluşur, temel sınıfın bir çağrısını gibi türetilmiş bir sınıf içinde `Finalize` yöntemi sonuna eklenir. Yıkıcı açıkça çağrılırsa, sonlandırıcıyı engellenir. İşte dönüşümü aşağıdaki gibi görünmelidir:  
  
```  
// internal transformation under new syntax  
public ref class R {  
public:  
   void Finalize() {  
      Console::WriteLine( "I am the R::finalizer()!" );  
   }  
};   
```  
  
## <a name="moving-from-managed-extensions-for-c-to-visual-c-2010"></a>Visual C++ 2010 C++ için Yönetilen Uzantılar'dan taşıma  
 Visual C++ altında derlendiğinde Önemsiz olmayan bir yıkıcı bir başvuru sınıfı içeren her bir C++ programı için Yönetilen Uzantılar çalışma zamanı davranışını değiştirilir. Gerekli çeviri algoritması aşağıdakine benzer:  
  
1.  Bir yıkıcı varsa, sınıf sonlandırıcıyı olacak şekilde yeniden yazın.  
  
2.  Varsa bir `Dispose` yöntemi varsa, sınıf yıkıcı yeniden.  
  
3.  Bir yıkıcı varsa ancak hiçbir `Dispose` yöntemi, ilk öğeyi gerçekleştirirken yıkıcı korur.  
  
 Kodunuzu Yönetilen Uzantılar'dan yeni sözdizimine taşıma, bu dönüştürmeyi gerçekleştirerek eksik. Uygulama herhangi bir yolla ilişkili sonlandırma yöntemlerinin yürütülmesi bağlıysa, uygulamanın davranışı, hedeflediğinizden sessizce farklılık gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)   
 [Yok ediciler ve sonlandırıcılar nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)