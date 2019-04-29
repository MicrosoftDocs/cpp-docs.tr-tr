---
title: Başvuru sınıfları ve yapıları (C++/CX)
ms.date: 01/22/2017
ms.assetid: 3d736b82-0bf0-48cf-bac1-cc9d110b70d1
ms.openlocfilehash: e9ac14762dba580967fbecd245a81a4ff4356b64
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368597"
---
# <a name="ref-classes-and-structs-ccx"></a>Başvuru sınıfları ve yapıları (C++/CX)

C++Kullanıcı tanımlı /CX destekler *başvuru sınıfları* ve *başvuru yapı birimleri*ve kullanıcı tanımlı *değer sınıfları* ve *yapılar değer*. Bu veri yapıları tarafından hangi C + birincil kapsayıcılardır +/ CX Windows çalışma zamanı tür sistemi destekler. İçeriklerini meta verilerine belirli belirli kurallara göre gönderilir ve bu bunları Windows çalışma zamanı bileşenleri ve evrensel Windows platformu uygulamaları, C++ veya diğer dillerde yazılmış arasında geçirilmesini sağlar.

Başvuru sınıfı veya ref struct önemli özelliklere sahiptir:

- Ad alanı kapsamında bir ad alanı içinde bildirilmelidir ve o ad alanında erişilebilirlik genel veya özel olabilir. Yalnızca genel türleri için meta veriler gönderilir. İç içe geçmiş genel sınıf tanımları izin verilmez, iç içe geçmiş genel dahil olmak üzere [enum](../cppcx/enums-c-cx.md) sınıfları. Daha fazla bilgi için [ad alanları ve tür görünürlüğü](../cppcx/namespaces-and-type-visibility-c-cx.md).

- Üye olarak içerebilir C++/CX başvuru sınıfları, değer sınıfları, başvuru yapı birimleri, değer yapılar veya boş değer atanabilen değer yapılar dahil. Ayrıca, float64, bool vb. gibi skaler türler de içerebilir. Ayrıca standart C++ türler gibi içerebilir `std::vector` veya özel bir sınıf genel olmadıkları sürece. C++/CX yapıları olabilir `public`, `protected`, `internal`, `private`, veya `protected private` erişilebilirlik. Tüm `public` veya `protected` üyeleri için meta verileri yayılır. Standart C++ türlerinin olmalıdır `private`, `internal`, veya `protected private` meta verileri yayılan engelleyen ve erişilebilirlik.

- Bir veya daha fazla uygulayabilir *arabirim sınıfları* veya *yapı birimleri arabirim*.

- Bir temel sınıftan devralabilir ve temel sınıflar kendilerini ek kısıtlamalar söz konusudur. Genel başvuru sınıf Hiyerarşiler Devralmada devralma değerinden daha fazla kısıtlama özel ref sınıfları vardır.

- Bu genel'olarak bildirilemez. Özel erişilebilirlik varsa, bir şablon olabilir.

- Ömrü otomatik başvuru sayımı tarafından yönetilir.

## <a name="declaration"></a>Bildirim

Aşağıdaki kod parçası bildirir `Person` başvuru sınıfı. Dikkat standart C++ `std::map` özel üyeler ve Windows çalışma zamanı türü kullanılan`IMapView` arabirimi ortak arabiriminde kullanılır. Ayrıca dikkat "^" başvuru türlerinin bildirimleri için eklenir.

[!code-cpp[cx_classes#03](../cppcx/codesnippet/CPP/classesstructs/class1.h#03)]

## <a name="implementation"></a>Uygulama

Bu kod örneği uygulanışı gösterilmektedir `Person` başvuru sınıfı:

[!code-cpp[cx_classes#04](../cppcx/codesnippet/CPP/classesstructs/class1.cpp#04)]

## <a name="usage"></a>Kullanım

Sonraki kod örneği, istemci kodu nasıl kullandığını gösterir `Person` başvuru sınıfı.

[!code-cpp[cx_classes#05](../cppcx/codesnippet/CPP/classesstructs/class1.cpp#05)]

Yığın anlamları, yerel başvuru sınıfı değişkenini bildirmek için de kullanabilirsiniz. Bellek hala dinamik olarak ayrılır olsa bile, böyle bir nesnenin yığın tabanlı bir değişken gibi davranır. İzleme başvurusu (%) atanamaz bir önemli fark vardır bir değişkene, yığın anlamları kullanarak bildirilir; Bu işlev, başvuru sayısı sıfıra indirildiği güvence altına alır. Bu örnek, bir temel başvuru sınıfı gösterir `Uri`ve yığın anlamları ile kullanan bir işlev:

[!code-cpp[cx_classes#06](../cppcx/codesnippet/CPP/classesstructs/class1.cpp#06)]

## <a name="memory-management"></a>Bellek yönetimi

Kullanarak bir başvuru sınıfı dinamik bellek ayırma `ref new` anahtar sözcüğü.

[!code-cpp[cx_classes#01](../cppcx/codesnippet/CPP/classesstructs/class1.h#01)]

Tanıtıcı nesnesi işleci ^ "hat" bilinir ve temelde olduğu bir C++ akıllı işaretçi. Son hat kapsamın dışına çıkıncaya veya açıkça işaret için bellek otomatik olarak edildiğinde `nullptr`.

Tanımı gereği, başvuru sınıfı başvuru semantiği vardır. Başvuru sınıfı atadığınızda nesnenin kendisini kopyalamıştır tanıtıcı olduğu değişken. Sonraki örnekte, atama sonra hem `myClass` ve `myClass2` aynı bellek konumuna gelin.

[!code-cpp[cx_classes#02](../cppcx/codesnippet/CPP/classesstructs/class1.h#02)]

C + olduğunda +/ CX başvuru sınıfı örneği, kendi bellek sıfır-kendi Oluşturucusu çağırılmadan önce; başlatılır Bu nedenle sıfır-özellikler dahil olmak üzere, tek tek üyeleri başlatma gerekli değildir. Varsa C++/CX sınıfı türetilen bir Windows çalışma zamanını şuradan C++ kitaplığı (WRL) sınıfı, yalnızca C++/CX türetilmiş sınıf bölümüdür sıfır olarak başlatılır.

### <a name="members"></a>Üyeler

Başvuru sınıfı içerebilir `public`, `protected`, ve `private` işlev üyeleri; yalnızca `public` ve `protected` üyeleri meta verilere yayılır. İç içe geçmiş sınıflar ve başvuru sınıfları izin verilir ancak olamaz `public`. Ortak alanları izin verilmiyor; ortak veri üyeleri özellikleri olarak bildirilmelidir. Alanların özel veya korumalı iç veri üyeleri olabilir. Bir başvuru sınıfının varsayılan olarak, tüm üyelerin erişilebilirlik olan `private`.

Varsayılan olarak üyelerinin olması dışında bir başvuru yapısı bir başvuru sınıfının aynıdır `public` erişilebilirlik.

A `public` başvuru sınıfı veya ref struct meta verilerinde yayılır, ancak diğer evrensel Windows platformu uygulamaları ve Windows çalışma zamanı bileşenleri kullanılabilir olması için en az bir ortak veya korumalı oluşturucuya sahip olmalıdır. Ortak yapıcıya sahip bir genel başvuru sınıfı olarak da bildirilmeleri gerekir `sealed` uygulama ikili arabiriminde (ABI) aracılığıyla türetme ileriki işlemleri önlemek için.

Windows çalışma zamanı tür sistemi desteklemediğinden Genel üyeler const olarak const bildirilemez. Statik bir özellik, bir genel veri üyesi sabit bir değer ile bildirmek için kullanabilirsiniz.

Public ref class veya struct tanımladığınızda, derleyici sınıf için gerekli özniteliklere uygulanır ve bu bilgileri uygulama .winmd dosyasında depolar. Ancak, bir ortak korumasız bir başvuru sınıfı tanımladığınızda, el ile uygulamanız `Windows::Foundation::Metadata::WebHostHidden` sınıfı JavaScript'te yazılmış bir evrensel Windows platformu uygulamaları için görünür olmamasını sağlamak için özniteliği.

Başvuru sınıfı dahil olmak üzere standart C++ türler olabilir `const` herhangi bir tür `private`, `internal`, veya `protected private` üyeleri.

Tür parametrelerine sahip genel başvuru sınıfları izin verilmez. Kullanıcı tanımlı genel başvuru sınıfları izin verilmez. Özel, iç veya korumalı özel başvuru sınıfı, bir şablon olabilir.

## <a name="destructors"></a>Yıkıcılar

İçinde C++/CX, çağırma `delete` üzerinde ortak bir yok edici yok edici nesnenin başvuru sayısının bağımsız olarak çağırır. Bu davranışı özel temizleme RAII olmayan kaynakların belirlenimci bir şekilde gerçekleştiren bir yıkıcı tanımlamanızı sağlar. Ancak, bu durumda bile, Nesne bellekten silinir. Başvuru sayısı sıfır ulaştığında yalnızca nesne için bellek serbest bırakılır.

Bir sınıfın yok Edicisi genel olmadığından, başvuru sayısı sıfır ulaştığında ardından onu yalnızca çağrılır. Çağırırsanız `delete` özel bir yok Edicisi olan bir nesne üzerinde derleyici uyarı gerektirdiğinizde C4493 başlatır "silme ifadenin etkisi yok edicisinde \<türü adı > 'public' erişilebilirlik sahip değil."

Yalnızca ref sınıf yıkıcıları şu şekilde bildirilebilir:

- Genel ve sanal (korumalı veya korumasız türlerinde izin verilir)

- Özel ve sanal olmayan (korumasız türlerinde izin yalnızca) korumalı

- Özel ve sanal olmayan (yalnızca korumalı türlerinde izin verilir)

Erişilebilirlik, virtualness ve sealedness bir birleşimini izin verilir.  Bir yıkıcı açıkça bildirmeyeceğiniz, türün temel sınıfı veya herhangi bir üyenin genel bir yok Edicisi varsa derleyici bir genel sanal yıkıcı üretir. Aksi halde, derleyici, mühürsüz türler için korumalı bir özel sanal olmayan yıkıcı veya korumalı türler için özel sanal olmayan yok edici oluşturur.

Çalıştırma yok edici zaten oluşmuş bir sınıfın üyeleri erişmeye çalışırsanız tanımsız bir davranıştır; büyük olasılıkla programın çökmesine neden olur. Çağırma `delete t` hiçbir ortak yıkıcısı olan bir türü üzerinde hiçbir etkisi olmaz. Çağırma `delete this` bilinen bir sahip yazın ya da temel sınıfta `private` veya `protected private` yıkıcıdan kendi tür hiyerarşisi içinde de etkisi yoktur.

Ortak yıkıcısı bildirdiğinizde, başvuru sınıfının uygular, böylece derleyici kodu oluşturur `Platform::IDisposable` ve yok edici uygular `Dispose` yöntemi. `Platform::IDisposable` olan C++/CX izdüşümü `Windows::Foundation::IClosable`. Bu arabirimler asla açıkça uygulayın.

## <a name="inheritance"></a>Devralma

Platform::Object tüm başvuru sınıfları için evrensel temel sınıftır. Tüm başvuru sınıfları için Platform::Object örtük olarak dönüştürülebilir ve geçersiz kılabilirsiniz [Object::ToString](../cppcx/platform-object-class.md#tostring). Ancak, Windows çalışma zamanı devralma modeli genel devralma modeli tasarlanmamıştır; içinde C++/CX yani bir kullanıcı tarafından tanımlanan ortak başvuru sınıfının bir temel sınıf olarak hizmet veremez.

XAML kullanıcı denetimi, oluşturduğunuz ve bağımlılık özelliği sistemde nesnenin katıldığı durumunda kullanabileceğiniz `Windows::UI::Xaml::DependencyObject` bir temel sınıf olarak.

Korumasız bir sınıf tanımladıktan sonra `MyBase` öğesinden devralan `DependencyObject`, diğer genel veya özel ref sınıfları, bileşeni veya uygulama devral `MyBase`. Genel başvuru sınıfları devralma, sanal yöntemler, çok biçimli bir kimlik ve Kapsülleme geçersiz kılmaları desteklemek için yalnızca yapılmalıdır.

Özel taban başvuru sınıfı, varolan bir korumasız sınıftan türetilen gerekli değildir. Bir nesne hiyerarşisine kendi program yapısı model veya kod yeniden kullanımını etkinleştirmek için gerekiyorsa, özel veya iç başvuru sınıfları kullanın veya henüz, standart C++ sınıfları daha iyi. Genel korumalı ref class sarmalayıcı aracılığıyla özel nesne hiyerarşisi işlevselliğini kullanıma sunabilirsiniz.

Ortak veya korumalı bir oluşturucuya sahip bir başvuru sınıfının C++/CX bildirilmelidir olarak korumalı. Bu kısıtlama, C# veya Visual Basic, C +'da yazılmış bir Windows çalışma zamanı bileşeni olarak bildirdiğiniz türleri devralınacak gibi diğer dillerde yazılmış sınıflar için bir yolu yoktur anlamına gelir. +/ CX.

C + devralma için temel kurallar şunlardır +/ CX:

- Başvuru sınıfları doğrudan en fazla bir taban başvuru sınıfı devralabilirsiniz, ancak herhangi bir sayıda arabirim uygulayabilir.

- Bir sınıfın ortak bir oluşturucusu varsa, bildirilmelidir türetme ileriki işlemleri önlemek için korumalı.

- İç veya korumalı özel oluşturuculara sahip korumasız ortak temel sınıflara oluşturabilirsiniz, doğrudan temel sınıfını türetilen koşuluyla veya dolaylı olarak mevcut bir temel sınıf gibi korumasız `Windows::UI::Xaml::DependencyObject`. .Winmd dosyaları arasında kullanıcı tanımlı ref sınıfların devralma desteklenmiyor; Ancak, bir başvuru sınıfı, başka bir .winmd dosyasında tanımlanan bir arabirimden devralabilir. Yalnızca aynı Windows çalışma zamanı bileşeni veya evrensel Windows platformu uygulaması içinde kullanıcı tanımlı taban başvuru sınıfından türetilmiş sınıfları oluşturabilirsiniz.

- Başvuru sınıfları için yalnızca ortak devralmayı desteklenir.

   [!code-cpp[cx_classes#08](../cppcx/codesnippet/CPP/classesstructs/class1.h#08)]

Aşağıdaki örnek, bir devralma hiyerarşisindeki diğer başvuru sınıfları türetilen ortak başvuru sınıfı nasıl sunacağınızı öğrenin gösterir.

[!code-cpp[cx_classes#09](../cppcx/codesnippet/CPP/classesstructs/class1.h#09)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[Değer sınıfları ve yapıları](../cppcx/value-classes-and-structs-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
