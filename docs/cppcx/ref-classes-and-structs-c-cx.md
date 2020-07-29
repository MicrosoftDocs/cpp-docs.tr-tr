---
title: Başvuru Sınıfları ve Yapıları (C++/CX)
ms.date: 01/22/2017
ms.assetid: 3d736b82-0bf0-48cf-bac1-cc9d110b70d1
ms.openlocfilehash: d128734f8c78c9198f0731b415c1be35b0c58e65
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214964"
---
# <a name="ref-classes-and-structs-ccx"></a>Başvuru Sınıfları ve Yapıları (C++/CX)

C++/CX Kullanıcı tanımlı *başvuru sınıflarını* ve *başvuru*yapılarını ve Kullanıcı tanımlı *değer sınıflarını* ve *değer*yapılarını destekler. Bu veri yapıları, C++/CX Windows Çalışma Zamanı tür sistemini desteklediği birincil kapsayıcılardır. İçerikleri belirli belirli kurallara göre meta verilere dağıtılır ve bu, C++ veya diğer dillerde yazılan Windows Çalışma Zamanı bileşenleri ve Evrensel Windows Platformu uygulamalar arasında geçirilmesini sağlar.

Bir başvuru sınıfı veya başvuru yapısına bu temel özellikler sahiptir:

- Ad alanı kapsamında bir ad alanı içinde bildirilmelidir ve bu ad alanında public veya Private erişilebilirliği olabilir. Meta verilere yalnızca ortak türler dağıtılır. İç içe geçmiş genel [sabit listesi](../cppcx/enums-c-cx.md) sınıfları dahil, iç içe ortak sınıf tanımlarına izin verilmez. Daha fazla bilgi için bkz. [ad alanları ve tür görünürlüğü](../cppcx/namespaces-and-type-visibility-c-cx.md).

- Bu, başvuru sınıfları, değer sınıfları, başvuru yapıları, değer yapıları veya null yapılabilir değer yapıları dahil olmak üzere, Üyeler C++/CX olarak içerebilir. Ayrıca, vb. gibi skaler türler de `float64` içerebilir **`bool`** . `std::vector`Ortak olmadığı sürece, veya özel bir sınıf gibi standart C++ türlerini de içerebilir. C++/CX yapıları,, **`public`** , **`protected`** **`internal`** **`private`** veya **`protected private`** erişilebilirliğine sahip olabilir. Tüm **`public`** veya **`protected`** Üyeler meta verilere dağıtılır. Standart C++ türlerinde,, **`private`** **`internal`** veya erişilebilirliği olmalıdır ve bu, **`protected private`** meta verilere yayılmasını önler.

- Bir veya daha fazla *arabirim sınıfı* veya *arabirim yapıları*uygulayabilir.

- Bir temel sınıftan devralınabilir ve temel sınıfların kendilerine ek kısıtlamalar vardır. Ortak başvuru sınıfı hiyerarşilerindeki devralmanın özel başvuru sınıflarında devralmayla daha fazla kısıtlaması vardır.

- Bu, genel olarak bildirilemez. Özel erişilebilirliği varsa, bu bir şablon olabilir.

- Yaşam süresi otomatik başvuru sayımına göre yönetilir.

## <a name="declaration"></a>Bildirim

Aşağıdaki kod parçası `Person` başvuru sınıfını bildirir. Standart C++ `std::map` türünün özel üyelerde kullanıldığını ve Windows çalışma zamanı `IMapView` arabiriminin ortak arabirimde kullanıldığını unutmayın. Ayrıca, "^" öğesinin başvuru türleri bildirimlerine eklenmiş olduğuna dikkat edin.

[!code-cpp[cx_classes#03](../cppcx/codesnippet/CPP/classesstructs/class1.h#03)]

## <a name="implementation"></a>Uygulama

Bu kod örneği, başvuru sınıfının bir uygulamasını gösterir `Person` :

[!code-cpp[cx_classes#04](../cppcx/codesnippet/CPP/classesstructs/class1.cpp#04)]

## <a name="usage"></a>Kullanım

Sonraki kod örneği, istemci kodunun başvuru sınıfını nasıl kullandığını gösterir `Person` .

[!code-cpp[cx_classes#05](../cppcx/codesnippet/CPP/classesstructs/class1.cpp#05)]

Ayrıca, yerel bir başvuru sınıfı değişkeni bildirmek için yığın semantiğini de kullanabilirsiniz. Bu tür bir nesne, bellek hala dinamik olarak ayrılabileceği halde yığın tabanlı değişken gibi davranır. Önemli bir farklılık, izleme başvurusu atayamanızdır (%) yığın semantiğinin kullanılarak belirtilen bir değişkene; Bu, işlev çıktığında başvuru sayısının sıfıra azaltılanmasını güvence altına alır. Bu örnek, temel bir başvuru sınıfını `Uri` ve yığın semantiğinin kullanıldığı bir işlevi gösterir:

[!code-cpp[cx_classes#06](../cppcx/codesnippet/CPP/classesstructs/class1.cpp#06)]

## <a name="memory-management"></a>Bellek yönetimi

Anahtar sözcüğünü kullanarak bir başvuru sınıfını dinamik bellekte ayırırsınız **`ref new`** .

[!code-cpp[cx_classes#01](../cppcx/codesnippet/CPP/classesstructs/class1.h#01)]

İşleyici-nesne işleci, **`^`** bir *hat* olarak bilinir ve temel olarak bir C++ akıllı işaretçisi olur. Son hat kapsam dışına geçtiğinde veya açıkça olarak ayarlandığında, işaret ettiği bellek otomatik olarak yok edilir **`nullptr`** .

Tanım olarak, bir başvuru sınıfının başvuru semantiğini vardır. Bir başvuru sınıfı değişkeni atadığınızda, nesnenin kendisi değil kopyalanmış olan işleyicidir. Sonraki örnekte, atamadan sonra, `myClass` ve `myClass2` aynı bellek konumunu işaret edin.

[!code-cpp[cx_classes#02](../cppcx/codesnippet/CPP/classesstructs/class1.h#02)]

Bir C++/CX başvuru sınıfı örneği oluşturulduğunda, Oluşturucusu çağrılmadan önce belleği sıfır olarak başlatılır; Bu nedenle, özellikler dahil olmak üzere bireysel üyeleri sıfır olarak başlatmak gerekli değildir. C++/CX sınıfı bir Windows Çalışma Zamanı C++ Kitaplığı (WRL) sınıfından türetildiyse, yalnızca C++/CX türetilmiş sınıf bölümü sıfır olarak başlatılır.

### <a name="members"></a>Üyeler

Bir başvuru sınıfı,, **`public`** **`protected`** ve **`private`** işlev üyelerini içerebilir; yalnızca **`public`** ve **`protected`** üyeleri meta verilere yayılır. İç içe geçmiş sınıflara ve başvuru sınıflarına izin verilir, ancak bu tür olamaz **`public`** . Ortak alanlara izin verilmez; ortak veri üyeleri özellikler olarak bildirilmelidir. Özel veya korumalı iç veri üyeleri alan olabilir. Varsayılan olarak, bir başvuru sınıfında tüm üyelerin erişilebilirliği olur **`private`** .

Başvuru yapısı, başvuru sınıfıyla aynıdır, ancak varsayılan olarak üyelerinin **`public`** erişilebilirliği vardır.

**`public`** Başvuru sınıfı veya başvuru yapısı meta verilerde yayınlanır, ancak diğer Evrensel Windows platformu uygulamalardan ve Windows çalışma zamanı bileşenlerinden kullanılabilir olması için en az bir ortak veya korumalı oluşturucuya sahip olması gerekir. Ortak Oluşturucusu olan ortak bir başvuru sınıfı **`sealed`** , uygulama ikili arabirimi (ABI) aracılığıyla daha fazla türetmeyi engellemek için olarak da bildirilmelidir.

**`const`** Windows çalışma zamanı tür sistemi const desteklemediği için ortak Üyeler, olarak bildirilemez. Statik bir özelliği, sabit değerli bir ortak veri üyesini bildirmek için kullanabilirsiniz.

Ortak bir başvuru sınıfı veya yapısı tanımladığınızda, derleyici gerekli öznitelikleri sınıfa uygular ve bu bilgileri uygulamanın. winmd dosyasında depolar. Ancak, genel korumasız bir başvuru sınıfı tanımladığınızda, `Windows::Foundation::Metadata::WebHostHidden` sınıfın JavaScript 'te yazılan Evrensel Windows platformu uygulamalara görünür olmamasını sağlamak için özniteliği el ile uygulayın.

Ref sınıfı, türler dahil olmak üzere standart C++ türlerine sahip olabilir; Örneğin, herhangi bir, **`const`** **`private`** **`internal`** veya **`protected private`** Üyeler.

Tür parametrelerine sahip ortak başvuru sınıflarına izin verilmez. Kullanıcı tanımlı Genel başvuru sınıflarına izin verilmez. Özel, iç veya korunan özel başvuru sınıfı bir şablon olabilir.

## <a name="destructors"></a>Yıkıcılar

C++/CX ' te, **`delete`** genel yıkıcı çağırmak, nesnenin başvuru sayısından bağımsız olarak yıkıcıyı çağırır. Bu davranış, bir belirleyici olmayan kaynakların özel temizleme işlemini gerçekleştiren bir yıkıcı tanımlamanızı sağlar. Ancak, bu durumda bile nesnenin kendisi bellekten silinmez. Nesne için bellek yalnızca başvuru sayısı sıfıra ulaştığında serbest bırakılır.

Bir sınıfın yıkıcısı ortak değilse, yalnızca başvuru sayısı sıfıra ulaştığında çağrılır. `delete`Özel yok edicisi olan bir nesne üzerinde çağrı yaparsanız, derleyici uyarı C4493 başlatır. Bu, "DELETE ifadesinin yok edicisi \<type name> ' Public ' erişilebilirlik içermediğinden hiçbir etkisi yoktur."

Başvuru sınıfı yıkıcıları yalnızca aşağıdaki gibi gösterilebilir:

- ortak ve sanal (korumalı veya korumasız türlerde izin verilir)

- korunan özel ve sanal olmayan (yalnızca korumasız türlerde izin veriliyor)

- Özel ve sanal olmayan (yalnızca korumalı türlerde izin verilir)

Farklı erişilebilirlik, sanallaştırlık ve mevsimlik birleşimine izin verilmez.  Açıkça bir yıkıcı bildirmezsiniz, türün temel sınıfı veya herhangi bir üyenin ortak yok edicisi varsa derleyici bir ortak sanal yıkıcı oluşturur. Aksi halde, derleyici korumasız türler için korumalı bir özel sanal olmayan yıkıcı veya korumalı türler için özel bir sanal olmayan yıkıcı oluşturur.

Zaten yıkıcı çalıştırması olan bir sınıfın üyelerine erişmeye çalışırsanız davranış tanımsızdır; büyük olasılıkla programın kilitlenmesine neden olur. `delete t`Ortak yok edici olmayan bir türün çağrılması hiçbir etkiye sahip değildir. `delete this`Türü hiyerarşisinde bilinen veya yıkıcıya sahip olan bir tür veya temel sınıfın çağrılması **`private`** **`protected private`** de etkisizdir.

Ortak bir yıkıcı bildirdiğinizde, derleyici, başvuru sınıfının uyguladığı `Platform::IDisposable` ve yıkıcının yöntemi uyguladığı şekilde kodu oluşturur `Dispose` . `Platform::IDisposable`, C++/CX projeksiyonu `Windows::Foundation::IClosable` . Bu arabirimleri hiçbir daha açık olarak uygulamayın.

## <a name="inheritance"></a>Devralma

Platform:: Object tüm ref sınıfları için Evrensel temel sınıftır. Tüm başvuru sınıfları Platform:: nesnesine örtük olarak dönüştürülebilir ve [nesne:: ToString](../cppcx/platform-object-class.md#tostring)geçersiz kılınabilir. Ancak, Windows Çalışma Zamanı devralma modeli genel devralma modeli olarak tasarlanmamıştır; C++/CX ' te, Kullanıcı tanımlı ortak başvuru sınıfının temel sınıf olarak kullanamayacağı anlamına gelir.

XAML Kullanıcı denetimi oluşturuyorsanız ve nesne, bağımlılık özelliği sistemine katılıyorsa, `Windows::UI::Xaml::DependencyObject` temel sınıf olarak kullanabilirsiniz.

Öğesinden devralan korumasız bir sınıf tanımladıktan sonra `MyBase` `DependencyObject` , bileşeninizdeki veya uygulamanızdaki diğer ortak veya özel başvuru sınıfları öğesinden devralabilir `MyBase` . Ortak başvuru sınıflarında devralma yalnızca sanal yöntemlerin, polimorfik kimliğin ve kapsüllemenin geçersiz kılmalarını desteklemek için yapılmalıdır.

Özel bir temel başvuru sınıfı, varolan bir korumasız sınıftan türetmek için gerekli değildir. Kendi program yapınızı modelleyebilir veya kod yeniden kullanımını etkinleştirmek için bir nesne hiyerarşisine ihtiyacınız varsa, özel veya iç başvuru sınıflarını veya daha iyi bir standart C++ sınıfını kullanın. Özel nesne hiyerarşisinin işlevlerini ortak bir korumalı başvuru sınıfı sarmalayıcısı aracılığıyla kullanıma sunabilirsiniz.

C++/CX içinde ortak veya korumalı Oluşturucusu olan bir başvuru sınıfı Sealed olarak bildirilmelidir. Bu kısıtlama, C# veya Visual Basic gibi diğer dillerde yazılmış sınıfların, C++/CX'DE yazılmış bir Windows Çalışma Zamanı bileşende bildirdiğiniz türlerden devralması anlamına gelir.

C++/CX ' te devralma için temel kurallar şunlardır:

- Başvuru sınıfları doğrudan en çok bir temel başvuru sınıfından devralınabilir, ancak herhangi bir sayıda arabirim uygulayabilir.

- Bir sınıfta ortak bir Oluşturucu varsa, daha fazla türetmeyi engellemek için korumalı olarak bildirilmelidir.

- Temel sınıfın, gibi var olan bir korumasız taban sınıftan doğrudan veya dolaylı olarak türemesi şartıyla, iç veya korumalı özel oluşturuculara sahip ortak korumasız taban sınıflar oluşturabilirsiniz `Windows::UI::Xaml::DependencyObject` . . Winmd dosyaları arasında Kullanıcı tanımlı başvuru sınıflarının devralınması desteklenmez; Ancak, bir başvuru sınıfı, başka bir. winmd dosyasında tanımlı bir arabirimden devralınabilir. Yalnızca aynı Windows Çalışma Zamanı bileşeni veya Evrensel Windows Platformu uygulaması içinde, Kullanıcı tanımlı bir temel başvuru sınıfından türetilmiş sınıflar oluşturabilirsiniz.

- Ref sınıfları için yalnızca genel devralma desteklenir.

   [!code-cpp[cx_classes#08](../cppcx/codesnippet/CPP/classesstructs/class1.h#08)]

Aşağıdaki örnek, bir devralma hiyerarşisindeki diğer başvuru sınıflarından türetilen ortak bir başvuru sınıfının nasıl kullanıma sunumını gösterir.

[!code-cpp[cx_classes#09](../cppcx/codesnippet/CPP/classesstructs/class1.h#09)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür sistemi](../cppcx/type-system-c-cx.md)<br/>
[Değer sınıfları ve yapıları](../cppcx/value-classes-and-structs-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
