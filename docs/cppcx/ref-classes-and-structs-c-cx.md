---
title: "Ref sınıflar ve yapılar (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d736b82-0bf0-48cf-bac1-cc9d110b70d1
caps.latest.revision: "42"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 405f1890dc99e5a20102b7602ac83534cb5ded8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ref-classes-and-structs-ccx"></a>Ref sınıflar ve yapılar (C + +/ CX)
C + +/ CX destekler kullanıcı tanımlı *ref sınıfları* ve *ref yapılar*ve kullanıcı tanımlı *değer sınıfları* ve *değer yapılar*. Bu veri yapıları tarafından hangi C + birincil kapsayıcılardır +/ CX Windows çalışma zamanı tür sistemi destekler. İçerikleri belirli belirli kurallarına göre meta verilerine yayılan ve bu bunları Windows çalışma zamanı bileşenleri ve C++ veya diğer dillerde yazılmış Evrensel Windows platformu uygulamaları arasındaki geçirilmesini sağlar.  
  
 Ref sınıfta veya ref yapı bu temel özelliklere sahiptir:  
  
-   Ad alanı kapsamında bir ad alanı içinde bildirilmelidir ve bu ad alanında Genel veya özel erişilebilirlik sahip olabilir. Yalnızca genel türleri için meta veri gösterilen. İç içe geçmiş ortak sınıf tanımları verilmez, iç içe geçmiş genel dahil olmak üzere [enum](../cppcx/enums-c-cx.md) sınıfları. Daha fazla bilgi için bkz: [ad alanları ve tür görünürlüğü](../cppcx/namespaces-and-type-visibility-c-cx.md).  
  
-   Üye olarak C + içerebilir +/ CX ref sınıfları, değer sınıfları, ref yapılar, değer yapılar veya boş değer atanabilen değer yapılar dahil olmak üzere. Ayrıca, float64, bool vb. gibi skaler türler de içerebilir. Standart C++ türleri gibi ayrıca içerebilir `std::vector` veya özel bir sınıf, ortak olmadıkları sürece. C + +/ CX yapıları olabilir `public`, `protected`, `internal`, `private`, veya `protected private` erişilebilirlik. Tüm `public` veya `protected` üyeleri için meta veri yayılan. Standart C++ türler olmalıdır `private`, `internal`, veya `protected private` meta verileri yayılan önleyen erişilebilirlik.  
  
-   Bir veya daha fazla uygulayabilir *arabirim sınıfları* veya *arabirim yapılar*.  
  
-   Bir taban sınıftan devralın ve temel sınıflar kendilerini ek kısıtlamalar söz konusudur. Ortak ref sınıf hiyerarşileri devralma özel ref sınıflarında devralma'den daha fazla sınırlamalar vardır.  
  
-   Bu gibi genel bildirilmemiş. Özel erişilebilirlik varsa, bir şablon olabilir.  
  
-   Yaşam süresi otomatik başvuru sayımı tarafından yönetilir.  
  
## <a name="declaration"></a>Bildirim  
 Aşağıdaki kod parçası bildirir `Person` ref sınıfı. Dikkat standart C++ `std::map` özel üyelerin ve Windows çalışma zamanı türü kullanılan`IMapView` arabirimi ortak arabirimi kullanılır. Ayrıca, fark "^" başvuru türleri bildirimleri için eklenir.  
  
 [!code-cpp[cx_classes#03](../cppcx/codesnippet/CPP/classesstructs/class1.h#03)]  
  
## <a name="implementation"></a>Uygulama  
 Bu kod örneği uygulaması gösterir `Person` ref sınıfı:  
  
 [!code-cpp[cx_classes#04](../cppcx/codesnippet/CPP/classesstructs/class1.cpp#04)]  
  
## <a name="usage"></a>Kullanım  
 Sonraki kod örneği, istemci kodu nasıl kullandığını gösterir `Person` ref sınıfı.  
  
 [!code-cpp[cx_classes#05](../cppcx/codesnippet/CPP/classesstructs/class1.cpp#05)]  
  
 Yığın anlamları, bir yerel ref sınıfı değişken bildirmek için de kullanabilirsiniz. Bellek hala dinamik olarak ayrılır olsa da böyle bir nesnenin yığın tabanlı bir değişken gibi davranır. Önemli bir fark izleme başvurusu (%) atayamazsınız yığın anlamları kullanarak bildirilmiş bir değişkene; bu başvuru sayısı işlevi çıktığında sıfıra indirildiği olmasını sağlar. Bu örnek, bir temel ref sınıfı gösterir `Uri`ve yığın anlamları ile kullanan bir işlev:  
  
 [!code-cpp[cx_classes#06](../cppcx/codesnippet/CPP/classesstructs/class1.cpp#06)]  
  
## <a name="memory-management"></a>Bellek yönetimi  
 Dinamik bellek ref sınıfında kullanarak tahsis `ref new` anahtar sözcüğü.  
  
 [!code-cpp[cx_classes#01](../cppcx/codesnippet/CPP/classesstructs/class1.h#01)]  
  
 Tanıtıcı nesnenin işleç ^ "hat" bilinen ve temel bir C++ akıllı işaretçisi. Son hat kapsamının dışına geçip geçmeyeceğini veya açıkça ayarlamak, onun işaret bellek otomatik olarak yok `nullptr`.  
  
 Tanımı gereği, ref sınıfı başvurusu semantiği sahiptir. Ref sınıfı atadığınızda değişken, bu nesnenin kendisini değil kopyaladı tanıtıcı değil. Sonraki örnekte, atama sonra her ikisi de `myClass` ve `myClass2` noktası aynı bellek konumu.  
  
 [!code-cpp[cx_classes#02](../cppcx/codesnippet/CPP/classesstructs/class1.h#02)]  
  
 C + zaman +/ CX ref sınıf örneği, kendi bellek sıfır-kurucusu çağrılmadan önce; başlatılır Bu nedenle sıfır başlatma özellikleri dahil olmak üzere tek tek üyeleri gerekli değildir. Varsa C + +/ CX sınıfı türetilen Windows çalışma zamanı C++ Kitaplığı (WRL) öğesinden bir sınıf, yalnızca C + +/ CX türetilmiş sınıf bölümü sıfır başlatıldı.  
  
### <a name="members"></a>Üyeler  
 Ref sınıfı içerebilir `public`, `protected`, ve `private` işlev üyeleri; yalnızca `public` ve `protected` üye meta veri yayılan. İç içe geçmiş sınıflar ve ref sınıfları izin verilen ancak olamaz `public`. Genel alanlar izin verilmiyor; Genel veri üyelerini özellikleri olarak bildirilmesi gerekir. Özel veya korumalı iç veri üyeleri alanları olabilir. Ref sınıfında varsayılan olarak, tüm üyeleri erişilebilirliğini olduğu `private`.  
  
 Varsayılan olarak, üyeli ref yapı ref sınıf ile aynı olmasıdır `public` erişilebilirlik.  
  
 A `public` ref sınıfı ya da ref yapı meta verilerde yayılan, ancak diğer evrensel Windows platformu uygulamaları ve Windows çalışma zamanı bileşenleri kullanılabilmesi için en az bir ortak veya korumalı oluşturucuya sahip olmalıdır. Ortak bir oluşturucuya sahip bir ortak ref sınıfı ayrıca olarak bildirilmelidir `sealed` daha fazla uygulama ikili arabirimi (ABI) aracılığıyla türetme önlemek için.  
  
 Windows çalışma zamanı tür sistemi desteklemediğinden Genel üyeler olarak const const bildirilmemiş. Ortak veri üyesi sabit bir değer ile bildirmek için bir statik özellik kullanabilirsiniz.  
  
 Ortak ref sınıfta veya yapı tanımladığınızda, derleyici gerekli öznitelikler sınıfa uygulanır ve bu bilgileri uygulamanın .winmd dosyasında depolar. Ancak, bir ortak korumasız ref sınıf tanımladığınızda, el ile uygulamak `Windows::Foundation::Metadata::WebHostHidden` sınıfı JavaScript'te yazılmış Evrensel Windows platformu uygulamaları için görünür olmamasını sağlamak için öznitelik.  
  
 Ref sınıfı dahil olmak üzere standart C++ türleri olabilir `const` herhangi türleri `private`, `internal`, veya `protected private` üyeleri.  
  
 Tür parametreleri olan ortak ref sınıfları izin verilmez. Kullanıcı tanımlı genel ref sınıfları izin verilmez. Bir özel, iç ya da protected özel ref sınıfı bir şablon olabilir.  
  
## <a name="destructors"></a>Yıkıcılar  
 C + +/ CX, çağırma `delete` üzerinde ortak bir yıkıcı yıkıcı nesnenin başvuru sayısı bağımsız olarak çağırır. Bu davranış, kararlı bir biçimde RAII olmayan kaynakları özel temizliği gerçekleştiren bir yıkıcı tanımlamanızı sağlar. Ancak, bu durumda bile, nesnenin kendisini bellekten silinmez. Başvuru sayısı sıfır ulaştığında nesnesi için bellek yalnızca serbest bırakılır.  
  
 Sınıf yıkıcı ortak değilse başvuru sayısı sıfır ulaştığında sonra onu yalnızca çağrılır. Çağırırsanız `delete` özel yıkıcı sahip bir nesne üzerinde uyarı bildiren C4493 derleyici başlatır "delete ifadesi hiçbir etkisi yıkıcısı \<türü adı > 'genel' erişilebilirlik sahip değil."  
  
 Ref sınıfı Yıkıcılar yalnızca şu şekilde bildirilebilir:  
  
-   Genel ve sanal (korumalı veya korumasız türlerinde izin verilir)  
  
-   Özel ve sanal olmayan (korumasız türlerinde izin yalnızca) korumalı  
  
-   Özel ve sanal olmayan (yalnızca korumalı türlerde izin verilir)  
  
 Başka hiçbir birleşimine erişilebilirlik, virtualness ve sealedness izin verilir.  Bir yıkıcı açıkça bildirme, tür temel sınıf veya herhangi bir üyenin ortak yıkıcı varsa derleyici ortak sanal yıkıcı oluşturur. Aksi takdirde, derleyici, korumalı bir özel sanal olmayan yıkıcı korumasız türleri için ya da korumalı türleri için özel bir sanal olmayan yıkıcı oluşturur.  
  
 Çalıştırma kendi yıkıcı zaten olan bir sınıf üyeleri erişmeye çalışırsa tanımlanmamış bir davranıştır; büyük olasılıkla programın çökmesine neden olur. Çağırma `delete t` hiçbir ortak yıkıcı olan bir türü üzerinde etkisi yoktur. Çağırma `delete this` bilinen bir sahip bir türü veya temel sınıfını `private` veya `protected private` yok Edicisi türü hiyerarşi içinde de etkisi yoktur.  
  
 Bir ortak yıkıcı bildirirken ref sınıfı uygulayan böylece derleyici kod oluşturur `Platform::IDisposable` ve yıkıcı uygulayan `Dispose` yöntemi. `Platform::IDisposable`olan C + +/ CX projeksiyon çekirdeğinin `Windows::Foundation::IClosable`. Asla açıkça bu arabirimlerini uygular.  
  
## <a name="inheritance"></a>Devralma  
 Platform::Object tüm ref sınıfları için evrensel temel sınıftır. Tüm ref sınıflar için Platform::Object örtük olarak dönüştürülebilir ve kılabilirsiniz [Object::ToString](../cppcx/platform-object-class.md#tostring). Ancak, Windows çalışma zamanı devralma modeli genel devralma modeli tasarlanmamıştır; C + +/ CX yani bir kullanıcı tarafından tanımlanan ortak ref sınıfın temel sınıf olarak sunulamıyor.  
  
 XAML kullanıcı denetimi oluşturma ve bağımlılık özellik sistemi nesnenin katılan durumunda kullanabileceğiniz `Windows::UI::Xaml::DependencyObject` temel sınıf olarak.  
  
 Korumasız bir sınıf tanımladıktan sonra `MyBase` devraldığı `DependencyObject`, diğer ortak veya özel ref sınıfları, bileşen veya uygulama devral `MyBase`. Sanal yöntemler, çok biçimli kimlik ve Kapsülleme geçersiz kılmaları desteklemek için yalnızca ortak ref sınıflardaki devralma yapılması gerekir.  
  
 Özel temel ref sınıfı varolan bir korumasız sınıftan türetilen gerekli değildir. Bir nesne hiyerarşisi kodu yeniden etkinleştirmek için ya da kendi program yapısı modellemek için gerekiyorsa, özel veya dahili ref sınıflarını kullanın veya henüz, standart C++ sınıfları daha iyi. Genel korumalı ref sınıfı sarmalayıcı özel nesne hiyerarşide işlevselliğini getirebilir.  
  
 Bir genel veya korumalı Oluşturucu C + olan bir ref sınıfı +/ CX bildirilmelidir olarak korumalı. Bu kısıtlama, C# veya Visual Basic C + yazılmış bir Windows çalışma zamanı bileşeninde bildirme türleri devralınacak gibi diğer dillerde yazılmış sınıfları için hiçbir şekilde olduğu anlamına gelir +/ CX.  
  
 C + devralma temel kurallarını İşte +/ CX:  
  
-   Ref sınıfları doğrudan en çok bir temel ref sınıftan, ancak herhangi bir sayıda arabirim uygulayabilirsiniz.  
  
-   Bir sınıf bir public oluşturucuya varsa, bildirilmelidir daha fazla türetme önlemek için korumalı.  
  
-   İç veya korumalı özel oluşturucular sahip genel korumasız temel sınıfları oluşturabilirsiniz, temel sınıfın doğrudan türemesi sağlanan veya dolaylı olarak mevcut bir temel sınıf gibi korumasız `Windows::UI::Xaml::DependencyObject`. Devralma .winmd dosyalar arasında kullanıcı tanımlı ref sınıfların desteklenmiyor; Ancak, başka bir .winmd dosyasında tanımlanan bir arabirimden ref sınıfı devralabilirsiniz. Yalnızca aynı Windows çalışma zamanı bileşeni veya evrensel Windows Platform uygulaması içinde bir kullanıcı tarafından tanımlanan temel ref sınıfından türetilen sınıflar oluşturabilirsiniz.  
  
-   Ref sınıfları için yalnızca genel devralma desteklenir.  
  
     [!code-cpp[cx_classes#08](../cppcx/codesnippet/CPP/classesstructs/class1.h#08)]  
  
 Aşağıdaki örnek, bir devralma hiyerarşisindeki diğer ref sınıfından türeyen bir ortak ref sınıf kullanıma gösterilmektedir.  
  
 [!code-cpp[cx_classes#09](../cppcx/codesnippet/CPP/classesstructs/class1.h#09)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Değer sınıflar ve yapılar](../cppcx/value-classes-and-structs-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)