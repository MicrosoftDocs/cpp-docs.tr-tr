---
title: Yok edici anlamlarında yapılan değişiklikler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- finalizers [C++]
- destructors, C++
ms.assetid: f1869944-a407-452f-b99a-04d8c209f0dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c25045291afed1e8072867ee668716b2f396ef30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420029"
---
# <a name="changes-in-destructor-semantics"></a>Yok Edici Anlamlarında Yapılan Değişiklikler

Semantiği sınıfı yok ediciler için önemli ölçüde Yönetilen Uzantılar'dan C++ için Visual C++ için değiştirildi.

Yönetilen Uzantılar'başvuru sınıfı içinde ancak değer sınıfı içinde değil, bir sınıf yok edicisini verilmişti. Yeni sözdiziminde değiştirilmemiştir. Ancak, sınıf yok edicisini semantiği değişti. Bu konuda nedenlerine değiştirin ve var olan CLR kod çevirisi nasıl etkilediği açıklanır odaklanır. Dil iki sürümü arasındaki en önemli programcı düzeyinde değişiklik olabilir.

## <a name="non-deterministic-finalization"></a>Belirleyici sonlandırma

Çöp toplayıcısının, ilişkili bir nesne türüyle ilişkili bellek alınmadan önce `Finalize` yöntemi varsa çağrılır. Nesne program ömrünü bağlı değildir çünkü bu yöntem süper yıkıcı bir tür olarak düşünebilirsiniz. Bu sonlandırma diyoruz. Zamanlama yalnızca zaman veya hatta olup olmadığını bir `Finalize` yöntemi çağrıldığında tanımsızdır. Çöp toplama belirleyici sonlandırma sergiler dediğimiz olduğunda ne demek isteriz budur.

Olmayan sonlandırma da dinamik bellek yönetimi ile çalışır. Kullanılabilir bellek nadir hale geldiğinde, çöp toplayıcı devreye girer. Çöpü ortamı, belleği boşaltmak için Yıkıcılar gereksiz toplanır. Bir nesne bir veritabanı bağlantısı veya tür bir kilit gibi kritik bir kaynak olduğunda olmayan sonlandırma de ancak çalışmaz. Bu durumda, biz o kaynak olabildiğince çabuk serbest bırakmalısınız. Yerel dünyada, bir oluşturucu/yıkıcı çifti kullanarak elde edilir. Nesne ömrü sona erer hemen sonra yerel blok içinde bildirildiği sona erdiğinde veya yığın oluşan bir özel durum nedeniyle açıldığı zaman yok Edicisi yürütür ve kaynak otomatik olarak yayımlanır. Bu yaklaşım çok iyi çalışır ve Yönetilen Uzantılar altında'yokluğu hissedilir.

CLR tarafından sağlanan bir sınıf uygulamak çözümüdür `Dispose` yöntemi `IDisposable` arabirimi. Burada sorun `Dispose` kullanıcı tarafından açık bir çağırma gerektirir. Hataya budur. C# dili biçiminde bir özel Otomasyon büyüklükteki bir form sağlar `using` deyimi. Yönetilen Uzantılar tasarım hiçbir özel destek sağlanır.

## <a name="destructors-in-managed-extensions-for-c"></a>C++ için Yönetilen Uzantılar yıkıcılarda

Yönetilen Uzantılar, aşağıdaki iki adımı kullanarak bir başvuru sınıfının yıkıcısı uygulanır:

1. Kullanıcı tarafından sağlanan yok Edicisi dahili olarak yeniden adlandırıldı `Finalize`. Sınıfın temel sınıf varsa (unutmayın, CLR nesne modeli altında yalnızca tek devralma desteklenir), kullanıcı tarafından sağlanan kod yürütmeyi izleyen nesnenin Sonlandırıcısı için bir çağrı derleyici yerleştirir. Örneğin, yönetilen uzantıları dil belirtiminden alınan aşağıdaki basit hiyerarşi göz önünde bulundurun:

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

Bu örnekte, her iki Yıkıcılar yeniden adlandırılamaz `Finalize`. `B`ın `Finalize` çağrısından sahip `A`'s `Finalize` eklenen yöntemi çağırmayı aşağıdaki `WriteLine`. Ne çöp toplayıcının sonlandırma sırasında varsayılan olarak çağıracağı budur. İşte bu iç transformation aşağıdaki gibi görünmelidir:

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

1. İkinci adımda, derleyici sanal bir yıkıcı sentezler. Yönetilen Uzantılar kullanıcı programlarımızla doğrudan veya bir uygulama sil ifadesinin aracılığıyla çağırmak bu yok edici olur. Ayrıca, çöp toplayıcı tarafından hiçbir zaman çağrılır.

     İki deyim, bu Sentezlenen yıkıcı içine yerleştirilir. Bir çağrı biridir `GC::SuppressFinalize` hiçbir daha fazla çağrılarını olduğundan emin olmak için `Finalize`. İkincisi, gerçek çağrıdır `Finalize`, o sınıf için kullanıcı tarafından sağlanan yok Edicisi temsil eder. Bu görünebileceği aşağıda verilmiştir:

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

Bu uygulama kullanıcının sınıfı açıkça sağlar, ancak `Finalize` yöntemi artık yerine, hiçbir kontrole sahip, bir zaman, gerçekten ile tie değil `Dispose` yöntemi çözümü. Bu, Visual c++'ta değiştirilir.

## <a name="destructors-in-new-syntax"></a>Yeni sözdiziminde yok ediciler

Yeni sözdiziminde, yok edici dahili olarak yeniden adlandırılır `Dispose` yöntemi ve başvuru sınıfı otomatik olarak genişletilir uygulamak için `IDispose` arabirimi. Diğer bir deyişle, Visual C++'ın altında aşağıdaki gibi sınıfların bizim çifti dönüştürülür:

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

Yeni sözdiziminde ya da Yıkıcı açıkça çağrıldığında ya da zaman `delete` temel bir izleme işleyicisi uygulanan `Dispose` yöntemi otomatik olarak çağrılır. Çağrı türetilmiş bir sınıf olup olmadığını `Dispose` temel sınıf yöntemini Sentezlenen yöntemi kapanışında eklenir.

Ancak bu bize tüm sonlandırma için almaz. Ulaşmak için ek destek yerel başvuru nesnelerinin gerekiyor. (Bu Yönetilen Uzantılar içinde'benzer bir desteği vardır ve bu nedenle bir çeviri sorunu değildir.)

## <a name="declaring-a-reference-object"></a>Bir başvuru nesnesi bildirme

Doğrudan erişilebilir gibi visual C++ yerel yığında veya bir sınıf üyesi olarak bir başvuru sınıfının bir nesnesi bildirimini destekler. Yıkıcı ile ilişkisini ile birleştirildiğinde `Dispose` yöntem, sonuç sonlandırma semantiği başvuru türlerinde otomatik çağrılmasını olur.

Bir kaynak sınıfı oluşturucusu aracılığıyla alımını nesne oluşturma görür, ilk olarak, bizim başvuru sınıfı tanımlarız. İkincisi, sınıf yok edicisini içinde biz nesne oluşturulduğu sırada alındı kaynağı bırakmak.

```
public ref class R {
public:
   R() { /* acquire expensive resource */ }
   ~R() { /* release expensive resource */ }

   // everything else...
};
```

Nesne türü adını kullanarak yerel olarak ancak eşlik eden hat olmadan bildirilir. Bir yöntem çağırma nesnesinin tüm kullanımları üye seçimi nokta yapılır (`.`) yerine ok (`->`). Bloğun sonunda, ilişkili bir yıkıcı dönüştürülmüş `Dispose`, burada gösterildiği gibi otomatik olarak çağrılır:

```
void f() {
   R r;
   r.methodCall();

   // r is automatically destructed here -
   // that is, r.Dispose() is invoked
}
```

Olduğu gibi `using` ifadesi C# içinde bunu değil ayrılmaları tüm başvuru türleri temel alınan CLR kısıtlaması CLR yığın üzerinde ayrılan gerekir. Temel alınan semantiği değişmeden kalır. Kullanıcı eşdeğer aşağıdaki yazmış (ve derleyici tarafından gerçekleştirilen iç transformation büyük olasılıkla budur):

```
// equivalent implementation
// except that it should be in a try/finally clause
void f() {
   R^ r = gcnew R;
   r->methodCall();

   delete r;
}
```

Aslında, yeni sözdiziminde, Yıkıcılar yeniden oluşturucularla otomatik bir alım/yayın eşleştirilmelidir mekanizması için yerel bir nesnenin ömrünü bağlanır.

## <a name="declaring-an-explicit-finalize"></a>Açık bir Sonlandırıcı Bildirme

Anlatıldığı gibi yeni sözdiziminde, yok edici içinde oluşturulan `Dispose` yöntemi. Yıkıcı açıkça çağrılmaz, çöp toplayıcı sonlandırma sırasında önceki gibi ilişkili bir bulmaz, yani `Finalize` nesne için yöntemi. Yok etme hem sonlandırma desteklemek için bir sonlandırıcı sağlamak için özel bir sözdizimi ekledik. Örneğin:

```
public ref class R {
public:
   !R() { Console::WriteLine( "I am the R::finalizer()!" ); }
};
```

`!` Önekidir tilde benzer (`~`) bir sınıf yok edicisini sunan - diğer bir deyişle, sınıf adını önek olarak bir belirteç ömür sonrası her iki yöntem vardır. Varsa Sentezlenen `Finalize` yönteminin bir türetilen sınıf içinde temel sınıfın bir çağrı ortaya çıkar `Finalize` yöntemi sonuna eklenir. Yıkıcıyı açıkça çağrılırsa, sonlandırıcı bastırılır. İşte dönüşümü aşağıdaki gibi görünmelidir:

```
// internal transformation under new syntax
public ref class R {
public:
   void Finalize() {
      Console::WriteLine( "I am the R::finalizer()!" );
   }
};
```

## <a name="moving-from-managed-extensions-for-c-to-visual-c-2010"></a>Yönetilen Uzantılar'dan C++ için Visual C++ 2010'a taşıma

Visual C++ derlendiğinde Önemsiz olmayan bir yıkıcı bir başvuru sınıfı içeren her bir Yönetilen Uzantılar ' C++ programı için çalışma zamanı davranışını değiştirilir. Gerekli çeviri algoritması, aşağıdakine benzer:

1. Bir yok Edicisi varsa, Sonlandırıcıları olacak şekilde yeniden yazın.

1. Varsa bir `Dispose` yöntemi varsa, bu sınıf yok edicisini yeniden yazma.

1. Bir yok Edicisi varsa ancak hiçbir `Dispose` yöntemi, yok edici ilk öğeyi gerçekleştirilirken korur.

Kodunuzu Yönetilen Uzantılar'dan yeni sözdizimine taşıma, bu dönüşüm gerçekleştirme eksik. Uygulama başka bir yolla ilişkili sonlandırma yöntemleri yürütülmesine hazırlanması, uygulama davranışını sessizce, hedeflediğinizden farklı olacaktır.

## <a name="see-also"></a>Ayrıca Bkz.

[Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[Yok ediciler ve sonlandırıcılar, nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)