---
title: Tür sistemi (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: b67bee8a-b526-4872-969e-ef22724e88fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7b9f17007c1614761f1b7872d8d421f0f5e18df
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105178"
---
# <a name="type-system-ccx"></a>Tür sistemi (C + +/ CX)

Windows çalışma zamanı mimarisi kullanarak, C + kullanabileceğiniz +/ CX, Visual Basic, Visual C# ve JavaScript uygulamaları ve bileşenleri, doğrudan Windows API'sine erişmeniz ve diğer Windows çalışma zamanı uygulamaları ve bileşenleri ile birlikte çalışmak yazılacak. CPU doğrudan yürüten yerel kod için C++ programında yazılan Evrensel Windows platformu uygulamaları derleyin. C# veya Visual Basic'te yazılmış Evrensel Windows platformu uygulamaları, Microsoft Ara dili (MSIL) derleyin ve ortak dil çalışma zamanında (CLR) yürütme. JavaScript'te yazılmış Evrensel Windows platformu uygulamaları bir çalışma zamanı ortamında yürütme. Windows çalışma zamanı işletim sistemi bileşenleri kendilerini C++ programında yazılan ve yerel kod çalıştırın. Tüm bu bileşenleri ve evrensel Windows platformu uygulamaları doğrudan Windows çalışma zamanı uygulama ikili arabirimi (ABI) iletişim kurar.

Windows çalışma zamanı'nda bir modern C++ deyim desteğini etkinleştirmek için Microsoft C + oluşturulan +/ CX. C + +/ CX yerleşik taban türleri ve uygulamalarının C++ uygulamaları ve bileşenleri ABI'si ile diğer dillerde yazılmış uygulamalar arasında iletişim kurmak için temel Windows çalışma zamanı türleri sağlar. Herhangi bir Windows çalışma zamanı türü tüketen veya sınıflar, yapılar, arabirimler ve diğer evrensel Windows platformu uygulamaları ve bileşenleri tarafından kullanılan diğer kullanıcı tanımlı türler oluşturun. bir evrensel Windows platformu uygulaması yazılır C + +/ CX de kullanabilir normal bir C++ sınıfları ve yapıları ortak erişilebilirlik yok mu sürece.

Ayrıntılı bir irdelemesi ve C + +/ CX dil öngörü ve, perde şekli şu blog postalarına bakın:

1. [C + +/ CX parçası 0 \[n\]: Giriş](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction)

1. [C + +/ CX bölüm 1 / \[n\]: basit bir sınıfı](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class)

1. [C + +/ CX parçası 2 \[n\]: Hats Wear türleri](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats)

1. [C + +/ CX parçası 3 \[n\]: aşamasında](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)

1. [C + +/ CX parçası 4 \[n\]: statik üye işlevleri](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions)

## <a name="windows-metadata-winmd-files"></a>Windows meta veri (.winmd) dosyaları

C++ ile yazılmış bir evrensel Windows platformu uygulaması derlerken, derleyici yerel makine kodda yürütülebilir dosya oluşturur ve aynı zamanda ortak Windows çalışma zamanı türlerinin açıklamaları içeren ayrı bir Windows meta veri (.winmd) dosyası oluşturur, sınıflar, yapılar, numaralandırmalar, arabirimler, parametreli arabirimlerde ve temsilcilerde içeren. Meta veri biçimi, .NET Framework derlemeleri kullanılan biçimde benzer.  Bir C++ bileşeni .winmd dosyası yalnızca meta veriler içeriyor; yürütülebilir kodu ayrı bir dosyada yer alıyor. Windows ile birlikte Windows çalışma zamanı bileşenleri için durum budur. WinMD dosya adı ile aynı veya kaynak kodunda kök ad alanı öneki olmalıdır. (.NET Framework dillerinde, .winmd dosyası hem kod hem de .NET Framework derlemesinin gibi meta veriler içeriyor.)

Meta verilerde .winmd dosyası, kodunuzun yayımlanmış yüzeyi temsil eder. Yayımlanan türleri diğer evrensel Windows platformları için görünür hangi dilde olursa olsun diğer uygulamalarla yazılır. Bu nedenle, meta veriler ya da yayımlanan kodunuzu yalnızca Windows çalışma zamanı tür sistem tarafından belirtilen türleri içerebilir. Bir Javascript ya da C# istemci uygulaması ile yapmanız gerekenler bilmez olduğundan meta veriler gibi normal sınıfları, diziler, şablonları veya STL kapsayıcılar, C++, belirli dil yapılarını yayımlanamaz.

Bir türün veya yöntemin meta verilerinde görünür olup, kendisine uygulanan hangi erişilebilirlik değiştiricileri üzerinde bağlıdır. Görünür olması için bir tür bir isim uzayında bildirilmelidir ve genel olarak bildirilmelidir. Genel olmayan başvuru sınıfı, kodunuzda iç Yardımcısı türü olarak izin verilir; yalnızca meta verilerde görünür değildir. Bir ortak başvuru sınıfında bile tüm üyeleri mutlaka görülebilir. Aşağıdaki tabloda, C++ erişim belirticileri public ref class'nda ve Windows çalışma zamanı meta verileri görünürlük arasındaki ilişkiyi listelenmektedir:

|||
|-|-|
|**Meta verilerde yayımlandı**|**Meta verilerde yayımlanmayan**|
|public|private|
|protected|internal|
|Genel korumalı|Özel korumalı|

Kullanabileceğiniz **Nesne Tarayıcısı** .winmd dosyalarını içeriğini görüntülemek için. Windows ile birlikte Windows çalışma zamanı Windows.winmd'i dosyasında bileşenlerdir. C +'da kullanılan temel türler default.winmd dosyayı içeren +/ CX ve platform.winmd Platform ad alanı ek türleri içerir. Varsayılan olarak, bu üç .winmd dosyaları her C++ projesi Evrensel Windows platformu uygulamaları için dahil edilir.

> [!TIP]
> Türlerinde [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md) genel olmadıklarından .winmd dosyasında görünmez. Bunlar özel C++ diline özgü tanımlanan arabirimlerin uygulamalarıdır `Windows::Foundation::Collections`. JavaScript veya C# ile yazılmış bir Windows çalışma zamanı uygulama tanıdığınız değil bir [Platform::Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md) olduğunu, ancak bunu tüketebileceği bir `Windows::Foundation::Collections::IVector`. `Platform::Collections` Türleri collection.h içinde tanımlanır.

## <a name="windows-runtime-type-system-in-ccx"></a>Windows çalışma zamanı tür sistemi C + +/ CX

Aşağıdaki bölümlerde Windows çalışma zamanı tür sistemi ve nasıl bunlar C +'da desteklenen ana özelliklerini +/ CX.

### <a name="namespaces"></a>Ad Alanları

Tüm Windows çalışma zamanı türleri bir ad alanı içinde bildirilmelidir; Windows API ad alanları tarafından düzenlenir. .Winmd dosyası, kök ad alanı olan aynı ada sahip olmalıdır. Örneğin, yalnızca A.winmd veya A.B.winmd veya A.B.C.winmd adlı bir meta veri dosyasında tanımlanan A.B.C.MyClass adlı bir sınıf oluşturulabilir. DLL adını .winmd dosyası adı ile eşleşmesi için gerekli değildir.

Windows API, ad alanları tarafından düzenlenir bir katsayıları iyi belirlenmiş bir sınıf kitaplığı olarak satmanıza.  Tüm Windows çalışma zamanı bileşenleri Windows.* ad alanlarında bildirilir.

Daha fazla bilgi için [ad alanları ve tür görünürlüğü](../cppcx/namespaces-and-type-visibility-c-cx.md).

### <a name="fundamental-types"></a>Temel türler

Windows çalışma zamanı, aşağıdaki temel türler, UInt8, Int16, Uınt16, Int32, Uınt32, Int64, UInt64, tek, Double, Char16, Boolean ve dize tanımlar. C + +/ CX UInt16, UInt32, UInt64, Int16, Int32, Int64, float32, float64 ve char16 bu temel sayısal türler, varsayılan ad alanında destekler. Ayrıca Boolean ve dize Platform ad alanında tanımlanır.

C + +/ CX da uint8, eşdeğer tanımlar `unsigned char`, Windows çalışma zamanı'nda desteklenmiyor ve genel API'ler kullanılamaz.

Temel tür sarmalama tarafından null yapılabilir bir [Platform::ıbox arabirimi](../cppcx/platform-ibox-interface.md) arabirimi. Daha fazla bilgi için [değer sınıfları ve yapıları](../cppcx/value-classes-and-structs-c-cx.md).

Temel türler hakkında daha fazla bilgi için bkz: [temel türler](../cppcx/fundamental-types-c-cx.md)

### <a name="strings"></a>Dizeler

Bir Windows çalışma zamanı dize 16-bit UNICODE karakterlerin sabit bir dizisidir. Bir Windows çalışma zamanı dize olarak öngörülen `Platform::String^`. Bu sınıfın dizesini oluşturma, düzenleme ve dönüştürme için ve ondan sağladığı yöntemlerle `wchar_t`.

Daha fazla bilgi için [dizeleri](../cppcx/strings-c-cx.md).

### <a name="arrays"></a>Diziler

Windows çalışma zamanı, herhangi bir türde 1 boyutlu dizilerini destekler. Diziler diziler desteklenmez.  C + +/ CX, Windows çalışma zamanı diziler olarak yansıtılır [Platform::Array sınıfı](../cppcx/platform-array-class.md).

Daha fazla bilgi için [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)

### <a name="ref-classes-and-structs"></a>Başvuru sınıfları ve yapıları

Bir Windows çalışma zamanı sınıf gsyih C + +/ CX olarak bir başvuru sınıfının veya ref struct, çünkü bunlar başvuruya göre kopyalanır. Bellek yönetimi başvuru sınıfları ve başvuru yapı birimleri için başvuru sayımı yoluyla şeffaf bir şekilde ele alınır. Son bir nesneye başvuru kapsam dışına çıktığında, nesne yok edilir. Başvuru sınıfı veya ref struct yapabilirsiniz:

- Üyeleri Oluşturucular, yöntemler, özellikler ve olaylar içerir. Bu üye genel, özel, korumalı veya iç erişilebilirlik sahip olabilir.

- Özel iç içe geçmiş sabit listesi, yapı veya sınıf tanımlarını içerebilir.

- Doğrudan bir taban sınıftan devralabilirsiniz ve herhangi bir sayıda arabirim uygulayabilir. Tüm başvuru sınıfları için örtük olarak dönüştürülebilir [Platform::Object sınıfı](../cppcx/platform-object-class.md) ve kendi sanal yöntemleri geçersiz kılabilirsiniz — Örneğin, [Object::ToString](../cppcx/platform-object-class.md#tostring).

Ortak yapıcıya sahip bir başvuru sınıfının bildirilmelidir türetme ileriki işlemleri önlemek için olarak korumalı.

Daha fazla bilgi için [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md)

### <a name="value-classes-and-structs"></a>Değer sınıfları ve yapıları

Değer sınıfı veya değer yapı temel veri yapısını temsil eder ve değer sınıfları, yapılar değer veya tür olabilen yalnızca alanları içerir `Platform::String^`.  Değer yapıları ve değer sınıfları değere göre kopyalanır.

Değeri yapı sarmalama IBox arabirimdeki tarafından null yapılabilir.

Daha fazla bilgi için [değer sınıfları ve yapıları](../cppcx/value-classes-and-structs-c-cx.md).

### <a name="partial-classes"></a>Kısmi sınıflar

Kısmi sınıf özelliği üzerinde birden çok dosya tanımlanacak bir sınıf sağlar. Öncelikle dosyayı düzenlemeniz dokunmadan bir dosyayı değiştirmek için XAML Düzenleyicisi gibi kod oluşturma araçları etkinleştirmek için kullanılır.

Daha fazla bilgi için [kısmi sınıflar](../cppcx/partial-classes-c-cx.md)

### <a name="properties"></a>Özellikler

Bir özellik, herhangi bir Windows çalışma zamanı türü genel veri üyesi olan ve alma/ayarlama yöntemi çift olarak uygulanır. Ortak alan değilmiş gibi istemci kodu bir özelliğine erişir. Hiçbir özel gerektiren bir özellik get veya set kod olarak bilinen bir *Önemsiz özellik* ve açık get olmadan bildirilen veya ayarlamanıza yöntemleri.

Daha fazla bilgi için [özellikleri](../cppcx/properties-c-cx.md).

### <a name="windows-runtime-collections-in-ccx"></a>Windows çalışma zamanı koleksiyonları C + +/ CX

Windows çalışma zamanı, arabirimler için her bir dilin kendi şekilde uygulayan koleksiyon türleri kümesi tanımlar. C + +/ CX sağlar uygulamalarında [Platform::Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md), [Platform::Collections:: Map sınıfı](../cppcx/platform-collections-map-class.md)ve ile uyumlu diğer ilgili somut koleksiyon türleri, Standart Şablon kitaplığı (STL) ortaklarınıza.

Daha fazla bilgi için [koleksiyonları](../cppcx/collections-c-cx.md).

### <a name="template-ref-classes"></a>Şablon başvuru sınıfları

Özel ve iç başvuru sınıfları, şablonlu ve özel olabilir.

Daha fazla bilgi için [şablon başvuru sınıfları](../cppcx/template-ref-classes-c-cx.md).

### <a name="interfaces"></a>Arabirimler

Bir Windows çalışma zamanı arabiriminin, bir dizi ortak özellikleri, yöntemleri ve varsa bu arabirimden devralan bir başvuru sınıfının veya ref struct uygulamalıdır olayları tanımlar.

Daha fazla bilgi için [arabirimleri](../cppcx/interfaces-c-cx.md).

### <a name="enums"></a>Numaralandırmalar

Kapsamlı enum C++'ta Windows çalışma zamanı içinde bir sabit listesi sınıfı benzer. [Flags] özniteliği uygulanan sürece Int32, temel alınan türüdür; bu durumda, temel alınan uint32 türüdür.

Daha fazla bilgi için [numaralandırmalar](../cppcx/enums-c-cx.md).

### <a name="delegates"></a>Temsilciler

Windows çalışma zamanı içinde bir temsilci, C++'ta std::function nesnesine benzer. Uyumlu bir imzası olan istemci tarafından sağlanan işlevleri çağırmak için kullanılan başvuru sınıfı özel bir türüdür.  Temsilciler, olay türü olarak Windows çalışma zamanı'nda en yaygın olarak kullanılır.

Daha fazla bilgi için [Temsilciler](../cppcx/delegates-c-cx.md).

### <a name="exceptions"></a>Özel Durumlar

C + +/ CX, özel durum türleri yakalayabilir [std::exception](../standard-library/exception-class.md) türleri ve [Platform::Exception](../cppcx/platform-exception-class.md) türleri.

Daha fazla bilgi için [özel durumları](../cppcx/exceptions-c-cx.md).

### <a name="events"></a>Olaylar

Bir olay, bir başvuru sınıfı veya ref struct, türü bir temsilci türü olan genel bir üyesidir. Bir olay yalnızca çağrılabilir; diğer bir deyişle, harekete — sahip olan bir sınıf tarafından. Ancak, istemci kodu olay işleyicileri bilinir ve sahip olan sınıfın bir olay oluşturulduğunda çağrılır, kendi işlevler sağlayabilir.

Daha fazla bilgi için [olayları](../cppcx/events-c-cx.md).

### <a name="casting"></a>Atama

C + +/ CX standart dönüştürme C++ işleçleri destekler [static_cast](../cpp/static-cast-operator.md), [dynamic_cast](../cpp/dynamic-cast-operator.md), ve [reinterpret_cast](../cpp/reinterpret-cast-operator.md)hem de **safe_cast**C + özgü işleci +/ CX.

Daha fazla bilgi için [atama](../cppcx/casting-c-cx.md).

### <a name="boxing"></a>Kutulama

Paketlenmiş bir değişken başvuru semantiği gerekli olduğu durumlarda bir başvuru türü içinde sarmalanmış bir değer türüdür.

Daha fazla bilgi için [kutulama](../cppcx/boxing-c-cx.md).

### <a name="attributes"></a>Öznitelikler

Bir meta veri değeri herhangi bir Windows çalışma zamanı türü veya tür üyesi uygulanabilir ve çalışma zamanında inceledi özniteliğidir. Windows çalışma zamanı ortak öznitelikleri kümesini tanımlayan `Windows::Foundation::Metadata` ad alanı. Kullanıcı tanımlı öznitelikler genel arabirimlerde, bu sürümde Windows çalışma zamanı tarafından desteklenmez.

## <a name="api-deprecation"></a>API kullanımdan kaldırma

Genel API'leri Windows çalışma zamanı sistemi türleri tarafından kullanılan aynı özniteliğini kullanarak kullanım dışı bırakıldı olarak işaretlemek açıklar.

Daha fazla bilgi için [türleri ve üyeleri geçersiz kılma](../cppcx/deprecating-types-and-members-c-cx.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)
