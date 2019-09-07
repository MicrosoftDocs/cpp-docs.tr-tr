---
title: Tür sistemi (C++/CX)
ms.date: 02/03/2017
ms.assetid: b67bee8a-b526-4872-969e-ef22724e88fe
ms.openlocfilehash: bc45a835e37ff4e3ea239d253078bf50eab1b2ff
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740900"
---
# <a name="type-system-ccx"></a>Tür sistemi (C++/CX)

Windows Çalışma Zamanı mimarisini kullanarak, Windows API 'sine doğrudan erişen C++ve diğer Windows çalışma zamanı uygulamaları ve C# bileşenleriyle birlikte çalışan uygulamalar ve bileşenler yazmak için/CX, Visual Basic, görsel ve JavaScript kullanabilirsiniz. Doğrudan CPU 'da yürütülen yerel koda C++ derle içinde yazılan uygulamalar Evrensel Windows platformu. C# Veya Visual Basic yazılan Evrensel Windows platformu uygulamaları Microsoft ara dili 'NE (MSIL) derler ve ortak dil çalışma ZAMANıNDA (CLR) yürütülür. JavaScript 'te yazılan Evrensel Windows Platformu uygulamalar bir çalışma zamanı ortamında yürütülür. Windows Çalışma Zamanı işletim sistemi bileşenleri içine C++ yazılır ve yerel kod olarak çalıştırılır. Tüm bu bileşenler ve Evrensel Windows Platformu uygulamalar doğrudan Windows Çalışma Zamanı uygulama ikili arabirimi (ABı) aracılığıyla iletişim kurar.

Modern C++ bir IOM 'ta Windows çalışma zamanı desteğini etkinleştirmek Için, Microsoft C++/cx' i oluşturmuştur. C++/CX, C++ uygulamaların ve bileşenlerin diğer dillerde YAZıLMıŞ uygulamalarla ABI arasında iletişim kurmasını sağlayan temel Windows çalışma zamanı türlerinin yerleşik temel türlerini ve uygulamalarını sağlar. Tüm Windows Çalışma Zamanı türlerini kullanabilir veya sınıflar, yapılar, arabirimler ve diğer Evrensel Windows Platformu uygulamalar ve bileşenler tarafından tüketilen diğer Kullanıcı tanımlı türler oluşturabilirsiniz. /CX 'de C++yazılan Evrensel Windows platformu bir uygulama, genel erişilebilirliği olmadığı sürece normal C++ sınıflar ve yapılar da kullanabilir.

C++/CX dil projeksiyonunun derinlemesine bir tartışması ve bunların kapakları altında nasıl çalıştığı hakkında bilgi için şu blog gönderilerine bakın:

1. [C++/CX bölüm 0/ \[n\]: Giriş](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction)

1. [C++/CX Bölüm 1/ \[n\]: Basit bir sınıf](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class)

1. [C++/CX Bölüm 2/ \[n\]: Bu tür bir HATS](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats)

1. [C++/CX Bölüm 3/ \[n\]: Yapım aşamasında](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)

1. [C++/CX Bölüm 4/ \[n\]: Statik üye Işlevleri](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions)

## <a name="windows-metadata-winmd-files"></a>Windows meta verileri (. winmd) dosyaları

İçinde C++yazılmış bir Evrensel Windows platformu uygulamasını derlerken, derleyici yerel makine kodunda yürütülebilir dosyayı oluşturur ve ayrıca ortak Windows çalışma zamanı açıklamalarını içeren ayrı bir Windows meta veri (. winmd) dosyası oluşturur sınıflar, yapılar, numaralandırmalar, arabirimler, parametreli arabirimler ve temsilciler içeren türler. Meta verilerin biçimi .NET Framework derlemelerde kullanılan biçime benzer.  Bir C++ bileşende. winmd dosyası yalnızca meta verileri içerir; yürütülebilir kod ayrı bir dosyada yer alır. Windows ile birlikte gelen Windows Çalışma Zamanı bileşenleri için bu durum budur. WinMD dosya adı eşleşmelidir veya kaynak koddaki kök ad alanının öneki olmalıdır. (.NET Framework diller için. winmd dosyası, tıpkı bir .NET Framework derlemesi gibi hem kodu hem de meta verileri içerir.)

. Winmd dosyasındaki meta veriler, kodunuzun yayınlanan yüzeyini temsil eder. Yayımlanan türler, diğer uygulamaların yazıldığı dilden bağımsız olarak diğer Evrensel Windows platformları tarafından görülebilir. Bu nedenle, meta veriler veya yayımlanmış kodunuz yalnızca Windows Çalışma Zamanı tür sistemi tarafından belirtilen türleri içerebilir. Bir JavaScript veya C# istemci uygulaması kendileriyle C++ne yapacaklarına sahip olmadığı için, normal sınıflar, DIZILER, şablonlar veya STL kapsayıcıları gibi öğesine özgü dil yapıları meta verilerde yayımlanamaz.

Meta verilerde bir tür veya yöntemin görünür olup olmadığı, hangi erişilebilirlik değiştiricilerine uygulanacağını gösterir. Görünür olması için, bir tür ad alanında bildirilmelidir ve public olarak bildirilmelidir. Kodunuzda iç yardımcı türü olarak ortak olmayan bir başvuru sınıfına izin verilir; yalnızca meta verilerde görünmez. Ortak bir başvuru sınıfında bile, tüm üyelerin görünür olması gerekmez. Aşağıdaki tabloda, genel bir başvuru sınıfındaki C++ erişim belirticileri arasındaki ilişki ve meta veri görünürlüğü Windows çalışma zamanı listelenmiştir:

|||
|-|-|
|**Meta verilerde yayımlandı**|**Meta verilerde yayımlanmadı**|
|public|private|
|protected|internal|
|ortak korumalı|private protected|

. Winmd dosyalarının içeriğini görüntülemek için **nesne tarayıcısı** kullanabilirsiniz. Windows ile birlikte gelen Windows Çalışma Zamanı bileşenleri Windows. winmd dosyasında bulunur. Varsayılan. winmd dosyası,/CX içinde C++kullanılan temel türleri içerir ve platform. winmd Platform ad alanından ek türler içerir. Varsayılan olarak, bu üç. winmd dosyası Evrensel Windows Platformu uygulamalar için her C++ proje için dahil edilmiştir.

> [!TIP]
> [Platform:: Collections ad alanındaki](../cppcx/platform-collections-namespace.md) türler ortak olmadığından. winmd dosyasında görünmez. Bunlar, içinde C++ `Windows::Foundation::Collections`tanımlanan arabirimlerin özel özel uygulamalarıdır. JavaScript 'te yazılmış olan veya C# bir [Platform:: Collections:: vector sınıfının](../cppcx/platform-collections-vector-class.md) ne olduğunu bilmeyen, ancak bir kullanabilir bir `Windows::Foundation::Collections::IVector`Windows çalışma zamanı uygulama. `Platform::Collections` Türler Collection. h içinde tanımlanır.

## <a name="windows-runtime-type-system-in-ccx"></a>/CX içinde C++Windows çalışma zamanı tür sistemi

Aşağıdaki bölümlerde Windows Çalışma Zamanı türü sisteminin başlıca özellikleri ve bunların/Cx'de C++nasıl desteklendiği açıklanır.

### <a name="namespaces"></a>Ad Alanları

Tüm Windows Çalışma Zamanı türleri bir ad alanı içinde bildirilmelidir; Windows API 'sinin kendisi ad alanları tarafından düzenlenir. Bir. winmd dosyası, kök ad alanıyla aynı ada sahip olmalıdır. Örneğin, A. B. C. MyClass adlı bir sınıf, yalnızca bir. winmd veya A. B. winmd veya A. B. C. winmd adında bir meta veri dosyasında tanımlanmışsa oluşturulabilir. DLL 'nin adı. winmd dosya adıyla eşleşmek için gerekli değildir.

Windows API 'sinin kendisi, ad alanları tarafından düzenlenen iyi bir şekilde düzenlenmiş bir sınıf kitaplığı olarak yeniden düzenlenmiştir.  Tüm Windows Çalışma Zamanı bileşenleri Windows. * ad alanlarında bildirilmiştir.

Daha fazla bilgi için bkz. [ad alanları ve tür görünürlüğü](../cppcx/namespaces-and-type-visibility-c-cx.md).

### <a name="fundamental-types"></a>Temel türler

Windows Çalışma Zamanı, aşağıdaki temel türler, UInt8, Int16, UInt16, Int32, UInt32, Int64, UInt64, Single, Double, Char16, Boolean ve dize tanımlar. C++/CX, varsayılan ad alanındaki UInt64, uint32, uint64, int16, Int32, int64, float32, float64 ve Char16 olarak temel sayısal türleri destekler. Boolean ve dize, Platform ad alanında da tanımlanmıştır.

C++/CX Ayrıca, Windows çalışma zamanı desteklenmeyen ve genel `unsigned char`API 'lerde kullanılamayan, öğesine denk Uint8 tanımlar.

Temel bir tür, bir [Platform:: Ibox arabirim](../cppcx/platform-ibox-interface.md) arabiriminde sarmalanarak null yapılabilir hale getirilebilir. Daha fazla bilgi için bkz. [değer sınıfları ve yapıları](../cppcx/value-classes-and-structs-c-cx.md).

Temel türler hakkında daha fazla bilgi için bkz. [temel türler](../cppcx/fundamental-types-c-cx.md)

### <a name="strings"></a>Dizeler

Windows Çalışma Zamanı dize, 16 bit UNICODE karakterlerinden oluşan sabit bir dizidir. Windows Çalışma Zamanı bir dize olarak `Platform::String^`yansıtıldır. Bu sınıf, dize oluşturma, işleme ve dönüştürme `wchar_t`için yöntemler sağlar.

Daha fazla bilgi için bkz. [dizeler](../cppcx/strings-c-cx.md).

### <a name="arrays"></a>Diziler

Windows Çalışma Zamanı herhangi bir türdeki 1 boyutlu dizileri destekler. Dizi dizileri desteklenmez.  /CX C++'de, Windows çalışma zamanı dizileri [Platform:: Array sınıfı](../cppcx/platform-array-class.md)olarak yansıtıllardır.

Daha fazla bilgi için bkz. [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)

### <a name="ref-classes-and-structs"></a>Başvuru sınıfları ve yapıları

Windows Çalışma Zamanı sınıfı, başvuruya göre kopyalandıklarından, bir başvuru sınıfı veya başvuru yapısı olarak/CX içinde C++yansıtılmalıdır. Ref sınıfları ve başvuru yapıları için bellek yönetimi, başvuru saymasına göre saydam olarak işlenir. Bir nesneye yönelik son başvuru kapsam dışına geçtiğinde, nesne yok edilir. Başvuru sınıfı veya başvuru yapısı şunları yapabilir:

- Üye oluşturucular, Yöntemler, Özellikler ve olaylar olarak içerir. Bu üyelerin ortak, özel, korumalı veya iç erişilebilirliği olabilir.

- Özel iç içe Enum, struct veya Class tanımları içerebilir.

- , Bir temel sınıftan doğrudan devralınabilir ve herhangi bir sayıda arabirim uygulayabilir. Tüm başvuru sınıfları [Platform:: Object sınıfına](../cppcx/platform-object-class.md) örtük olarak dönüştürülebilir ve sanal yöntemlerini geçersiz kılabilir — Örneğin, [Object:: ToString](../cppcx/platform-object-class.md#tostring).

Ortak Oluşturucusu olan bir başvuru sınıfı, daha fazla türetmeyi engellemek için Sealed olarak bildirilmelidir.

Daha fazla bilgi için bkz. [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md)

### <a name="value-classes-and-structs"></a>Değer sınıfları ve yapıları

Değer sınıfı veya değer yapısı temel bir veri yapısını temsil eder ve yalnızca değer sınıfları, değer yapıları veya tür `Platform::String^`olabilecek alanlar içerir.  Değer yapıları ve değer sınıfları değere göre kopyalanır.

Değer yapısı bir Ibox arabiriminde sarmalanarak null yapılabilir hale getirilebilir.

Daha fazla bilgi için bkz. [değer sınıfları ve yapıları](../cppcx/value-classes-and-structs-c-cx.md).

### <a name="partial-classes"></a>Kısmi sınıflar

Kısmi sınıf özelliği, bir sınıfın birden çok dosya üzerinde tanımlanmasını sağlar. Bu, öncelikle XAML Düzenleyicisi gibi kod oluşturma araçlarının, düzenlediğiniz dosyaya dokunmadan tek bir dosyayı değiştirmesini sağlamak için kullanılır.

Daha fazla bilgi için bkz. [kısmi sınıflar](../cppcx/partial-classes-c-cx.md)

### <a name="properties"></a>Özellikler

Bir özellik, herhangi bir Windows Çalışma Zamanı türünün ortak veri üyesidir ve Get/Set Yöntem çifti olarak uygulanır. İstemci kodu bir özelliğe ortak bir alan gibi erişir. Özel Get veya set kodu gerektirmeyen bir özellik, *Önemsiz bir özellik* olarak bilinir ve açık get veya set yöntemleri olmadan bildirilebilecek.

Daha fazla bilgi için bkz. [Özellikler](../cppcx/properties-c-cx.md).

### <a name="windows-runtime-collections-in-ccx"></a>/CX içindeki C++koleksiyonları Windows çalışma zamanı

Windows Çalışma Zamanı, her dilin tek bir şekilde uyguladığı koleksiyon türleri için bir arabirim kümesi tanımlar. C++/CX, [Platform:: Collections:: vector Class](../cppcx/platform-collections-vector-class.md), [Platform:: Collections:: Map sınıfı](../cppcx/platform-collections-map-class.md)ve standart Şablon kitaplığı (STL) karşılıklarıyla uyumlu diğer ilgili somut koleksiyon türleri için uygulamalar sağlar.

Daha fazla bilgi için bkz. [koleksiyonlar](../cppcx/collections-c-cx.md).

### <a name="template-ref-classes"></a>Şablon başvuru sınıfları

Özel ve iç başvuru sınıfları şablonlu ve özelleştirilmiş olabilir.

Daha fazla bilgi için bkz. [şablon başvuru sınıfları](../cppcx/template-ref-classes-c-cx.md).

### <a name="interfaces"></a>Arabirimler

Windows Çalışma Zamanı arabirimi, bir başvuru sınıfının veya başvuru yapısının arabiriminden devraldığından uygulanması gereken bir dizi ortak özelliği, yöntemi ve olayları tanımlar.

Daha fazla bilgi için bkz. [arabirimler](../cppcx/interfaces-c-cx.md).

### <a name="enums"></a>Numaralandırmalar

Windows Çalışma Zamanı bir enum sınıfı içindeki C++kapsamlı bir numaralandırmaya benzer. Temel alınan tür Int32, [Flags] özniteliği uygulanmamışsa (Bu durumda, temel alınan tür uint32 olur).

Daha fazla bilgi için bkz. [enum](../cppcx/enums-c-cx.md).

### <a name="delegates"></a>Temsilciler

Windows Çalışma Zamanı bir temsilci içindeki C++bir std:: Function nesnesine benzerdir. Bu, uyumlu imzaları olan istemci tarafından sağlanmış işlevleri çağırmak için kullanılan özel bir başvuru sınıfı türüdür.  Temsilciler bir olayın türü olarak Windows Çalışma Zamanı en yaygın olarak kullanılır.

Daha fazla bilgi için bkz. [Temsilciler](../cppcx/delegates-c-cx.md).

### <a name="exceptions"></a>Özel Durumlar

/CX C++içinde özel özel durum türlerini, [std:: Exception](../standard-library/exception-class.md) türlerini ve [Platform:: Exception](../cppcx/platform-exception-class.md) türlerini yakalayabilirsiniz.

Daha fazla bilgi için bkz. [özel durumlar](../cppcx/exceptions-c-cx.md).

### <a name="events"></a>Olaylar

Bir olay, bir başvuru sınıfında veya tür bir temsilci türü olan ref yapısına ortak bir üyedir. Bir olay yalnızca sahip olan sınıf tarafından çağrılabilir — yani harekete geçirilir. Ancak, istemci kodu, olay işleyicileri olarak bilinen ve sahip olan sınıf olayı tetiklendiğinde çağrılan kendi işlevlerini sağlayabilir.

Daha fazla bilgi için bkz. [Olaylar](../cppcx/events-c-cx.md).

### <a name="casting"></a>Atama

C++/CX, static_cast, C++ [dynamic_cast](../cpp/dynamic-cast-operator.md)ve [](../cpp/static-cast-operator.md) [reinterpret_cast](../cpp/reinterpret-cast-operator.md)standart cast işleçlerini ve ayrıca/cx'e C++özgü **safe_cast** işlecini destekler.

Daha fazla bilgi için bkz. [atama](../cppcx/casting-c-cx.md).

### <a name="boxing"></a>Kutulama

Kutulanmış değişken, başvuru semantiğinin gerekli olduğu durumlarda başvuru türünde Sarmalanan bir değer türüdür.

Daha fazla bilgi için bkz. [paketleme](../cppcx/boxing-c-cx.md).

### <a name="attributes"></a>Öznitelikler

Öznitelik, herhangi bir Windows Çalışma Zamanı türüne veya tür üyesine uygulanabilen ve çalışma zamanında inceleneuygulanabilecek bir meta veri değeridir. Windows çalışma zamanı, `Windows::Foundation::Metadata` ad alanındaki ortak özniteliklerin bir kümesini tanımlar. Ortak arabirimlerde Kullanıcı tanımlı öznitelikler bu sürümdeki Windows Çalışma Zamanı tarafından desteklenmiyor.

## <a name="api-deprecation"></a>API kullanımdan kaldırma

Ortak API 'Lerin, Windows Çalışma Zamanı sistem türleri tarafından kullanılan aynı özniteliği kullanarak kullanım dışı olarak işaretlenme işlemini açıklar.

Daha fazla bilgi için bkz. [türleri ve üyeleri kullanımdan](../cppcx/deprecating-types-and-members-c-cx.md)kaldırma.

## <a name="see-also"></a>Ayrıca bkz.

[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)
