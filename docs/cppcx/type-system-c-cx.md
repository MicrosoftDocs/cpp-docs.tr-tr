---
title: "Sistem türü (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b67bee8a-b526-4872-969e-ef22724e88fe
caps.latest.revision: "28"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5c0db625db458bf4fb530ba4b07e742b1aad964
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="type-system-ccx"></a>Sistem türü (C + +/ CX)
Windows çalışma zamanı mimarisi kullanarak, C + kullanabileceğiniz +/ CX, Visual Basic, Visual C# ve JavaScript uygulamaları ve doğrudan Windows API'sine erişim ve diğer Windows çalışma zamanı uygulamaları ve bileşenleri ile birlikte çalışmak bileşenler yazmak için. C++ ile yazılmış Evrensel Windows platformu uygulamaları CPU doğrudan yürütür yerel koda derleyin. C# veya Visual Basic ile yazılmış Evrensel Windows platformu uygulamaları Microsoft Ara dili (MSIL) derleyip ortak dil çalışma zamanında (CLR) çalıştırın. JavaScript'te yazılmış Evrensel Windows platformu uygulamaları bir çalışma zamanı ortamında yürütün. Windows çalışma zamanı işletim sistemi bileşenleri kendilerini C++ ile yazılmış ve yerel kodu olarak çalıştırın. Tüm bu bileşenleri ve evrensel Windows platformu uygulamaları doğrudan Windows çalışma zamanı uygulama ikili arabirimi aracılığıyla (ABI) iletişim kurar.  
  
 Windows çalışma zamanı'nda modern C++ deyim desteğini etkinleştirmek için Microsoft C + oluşturulan +/ CX. C + +/ CX yerleşik taban türleri ve, C++ uygulamaları ve diğer dillerde yazılmış uygulamalar ile ABI üzerinden iletişim bileşenleri etkinleştirmek temel Windows çalışma zamanı türlerinin uygulamalarını sağlar. Herhangi bir Windows çalışma zamanı türü tüketen veya sınıflar, yapılar, arabirimler ve diğer evrensel Windows platformu uygulamaları ve bileşenleri tarafından kullanılabilecek diğer kullanıcı tanımlı türler oluşturun. C + yazılmış bir evrensel Windows Platform uygulaması +/ CX de kullanabilir normal C++ sınıfları ve yapıları ortak erişilebilirlik yok sürece.  
  
 Ayrıntılı bir irdelemesi için C + +/ CX dil projeksiyon ve perde arkasında nasıl çalıştığı bu Web günlüğü postaları bakın:  
  
1.  [C + +/ CX parçası 0 \[ n \]: Giriş](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction)  
  
2.  [C + +/ CX parçası 1 \[ n \]: basit bir sınıf](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class)  
  
3.  [C + +/ CX Kısım 2 / \[ n \]: şapkalar takmak türleri](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats)  
  
4.  [C + +/ CX parçası 3 \[ n \]: aşamasında](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)  
  
5.  [C + +/ CX parçası 4 \[ n \]: statik üye işlevleri](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions)  
  
## <a name="windows-metadata-winmd-files"></a>Windows (.winmd) meta veri dosyaları  
 C++ ile yazılmış bir evrensel Windows Platform uygulaması derlerken Derleyici yürütülebilir yerel makine kodda oluşturur ve aynı zamanda genel Windows çalışma zamanı tür açıklamaları içeren ayrı bir Windows Meta veriler (.winmd) dosyası oluşturur, Bu, sınıflar, yapılar, listeleme, arabirimler, parametreli arabirimleri ve temsilciler içerir. Meta veri biçimi, .NET Framework derlemelerde kullanılan biçimi benzer.  Bir C++ bileşeni .winmd dosyası yalnızca meta veri içeriyor; yürütülebilir kod ayrı bir dosyada yer alıyor. Bu durum Windows ile birlikte Windows çalışma zamanı bileşenleri için geçerlidir. WinMD dosya adı ile aynı veya kaynak kodundaki kök ad alanı öneki olmalıdır. (.NET Framework diller için .winmd dosya hem kod hem de .NET Framework derleme gibi meta veriler içeriyor.)  
  
 Meta veri .winmd dosyasında kodunuzu yayımlanan yüzeyinin temsil eder. Yayımlanan türleri diğer evrensel Windows platformları için görünür dil ne olursa olsun diğer uygulamalarla yazılır. Bu nedenle, meta veriler ya da yayımlanan kodunuzu yalnızca Windows çalışma zamanı tür sistem tarafından belirtilen türler içerebilir. Bir Javascript veya C# istemci uygulamasının onlarla yapmanız gerekenler bilmez için normal sınıfları, dizileri, şablonları veya STL kapsayıcıları gibi C++'ye özgü dil yapıları meta verilerde yayımlanamıyor.  
  
 Türü veya yöntemi meta verilerde görünür olup hangi erişilebilirlik değiştiricileri kendisine uygulanması bağlıdır. Görünür olması için bir tür bir ad alanındaki bildirilmelidir ve genel olarak bildirilmelidir. Genel olmayan ref sınıfı kodunuzda iç yardımcı türü olarak izin verilir; yalnızca meta verilerde görünür değil. Bir ortak ref sınıfta bile tüm üyeleri mutlaka görülebilir. Aşağıdaki tabloda ortak ref sınıfında C++ erişim tanımlayıcıları ve Windows çalışma zamanı meta veri görünürlük arasındaki ilişkiyi listelenmektedir:  
  
|||  
|-|-|  
|**Meta verilerde yayımlanan**|**Meta verilerde yayımlanmamış**|  
|public|private|  
|protected|internal|  
|Genel korumalı|Özel korumalı|  
  
 Kullanabileceğiniz **Nesne Tarayıcısı** .winmd dosyaların içeriğini görüntülemek için. Windows ile birlikte Windows çalışma zamanı bileşenleri Windows.winmd dosyasında yer alır. C + kullanılan temel türleri default.winmd dosyayı içeren +/ CX ve platform.winmd Platform ad alanından ek türler içerir. Varsayılan olarak, bu üç .winmd dosyaları her C++ projesi Evrensel Windows platformu uygulamaları için dahil edilmiştir.  
  
> [!TIP]
>  Türler [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md) ortak olmadıklarından .winmd dosyasında görünmüyor. Bunlar özel C++ özgü tanımlanan arabirimleri uygulamalarıdır `Windows::Foundation::Collections`. JavaScript veya C# ile yazılmış bir Windows çalışma zamanı uygulaması ne bilmiyor bir [Platform::Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md) olduğu, ancak bunu tüketebileceği bir `Windows::Foundation::Collections::IVector`. `Platform::Collections` Türleri collection.h içinde tanımlanmıştır.  
  
## <a name="windows-runtime-type-system-in-ccx"></a>Windows çalışma zamanı tür sistem C + +/ CX  
 Aşağıdaki bölümlerde Windows çalışma zamanı tür sistemi ve nasıl bunlar C + desteklenen ana özelliklerini +/ CX.  
  
### <a name="namespaces"></a>Ad Alanları  
 Tüm Windows çalışma zamanı türleri ad alanı içinde bildirilmelidir; Windows API ad alanları tarafından düzenlenir. Bir .winmd dosyası kök ad alanı var. aynı ada sahip olmalıdır. Örneğin, yalnızca A.winmd veya A.B.winmd veya A.B.C.winmd adlı bir meta veri dosyasında tanımlanırsa A.B.C.MyClass adlı bir sınıf oluşturulabilir. DLL adını .winmd dosya adı ile eşleşmesi için gerekli değildir.  
  
 Windows API, ad alanları tarafından düzenlenen bir iyi faktörlere göre sınıf kitaplığı olarak reinvented.  Tüm Windows çalışma zamanı bileşenleri Windows.* ad alanları ile bildirilir.  
  
 Daha fazla bilgi için bkz: [ad alanları ve tür görünürlüğü](../cppcx/namespaces-and-type-visibility-c-cx.md).  
  
### <a name="fundamental-types"></a>Temel türler  
 Windows çalışma zamanı aşağıdaki temel türleri, UInt8, Int16, UInt16, Int32, UInt32, Int64, UInt64, tek, Double, Char16, Boole ve dize tanımlar. C + +/ CX uint16, uint32, uint64, int16, int32, int64, float32, float64 ve char16 bu temel sayısal türler, varsayılan ad alanında destekler. Ayrıca Boolean ve String Platform ad alanında tanımlanır.  
  
 C + +/ CX ayrıca uint8, eşdeğer tanımlar `unsigned char`, hangi Windows çalışma zamanı'nda desteklenmiyor ve ortak API'leri kullanılamaz.  
  
 Temel türü kaydırma tarafından null yapılabilir bir [Platform::IBox arabirimi](../cppcx/platform-ibox-interface.md) arabirimi. Daha fazla bilgi için bkz: [değer sınıflar ve yapılar](../cppcx/value-classes-and-structs-c-cx.md).  
  
 Temel türleri hakkında daha fazla bilgi için bkz: [temel türler](../cppcx/fundamental-types-c-cx.md)  
  
### <a name="strings"></a>Dizeler  
 Windows çalışma zamanı dize 16 bit UNICODE karakterler değişmez bir dizisidir. Windows çalışma zamanı dize olarak yansıtılır `Platform::String^`. Bu sınıfın dizesini oluşturma, düzenleme ve dönüştürme ve ondan sağladığı yöntemlerle `wchar_t`.  
  
 Daha fazla bilgi için bkz: [dizeleri](../cppcx/strings-c-cx.md).  
  
### <a name="arrays"></a>Diziler  
 Windows çalışma zamanı herhangi bir türde 1 boyutlu diziler destekler. Ayrı diziler desteklenmez.  C + +/ CX, Windows çalışma zamanı diziler öngörülen olarak [Platform::Array sınıfı](../cppcx/platform-array-class.md).  
  
 Daha fazla bilgi için bkz: [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)  
  
### <a name="ref-classes-and-structs"></a>Ref sınıflar ve yapılar  
 Windows çalışma zamanı sınıf yansıtılmıyor C + +/ CX ref sınıfta veya ref yapı olarak başvuruya göre kopyalanmadığından. Ref sınıfları ve ref yapıları için bellek yönetimi, başvuru sayımı yoluyla saydam olarak işlenir. Son bir nesneye başvuru kapsam dışına çıktığında nesnesi yok. Ref sınıfı veya ref yapı yapabilirsiniz:  
  
-   Üyeleri Oluşturucular, yöntemleri, özellikleri ve olayları içerir. Bu üye genel, özel, korumalı veya iç erişilebilirlik sahip olabilir.  
  
-   İç içe geçmiş özel enum, yapı veya sınıf tanımları içerebilir.  
  
-   Doğrudan bir taban sınıftan devralın ve herhangi bir sayıda arabirim uygulayabilirsiniz. Tüm ref sınıflar için örtük olarak dönüştürülebilir [Platform::Object sınıfı](../cppcx/platform-object-class.md) ve sanal yöntemlerini geçersiz kılabilirsiniz — Örneğin, [Object::ToString](../cppcx/platform-object-class.md#tostring).  
  
 Ortak bir oluşturucuya sahip bir ref sınıf bildirilmelidir olarak korumalı, daha fazla türetme önlemek için.  
  
 Daha fazla bilgi için bkz: [Ref sınıflar ve yapılar](../cppcx/ref-classes-and-structs-c-cx.md)  
  
### <a name="value-classes-and-structs"></a>Değer sınıflar ve yapılar  
 Değer sınıfı ya da değer yapı temel veri yapısını temsil eder ve yalnızca alanları, değer sınıfları, değer yapılar veya türü olabilir içeren `Platform::String^`.  Değer yapıları ve değer sınıfları değeriyle kopyalanır.  
  
 Değer yapı IBox arabirimdeki kaydırma tarafından null yapılabilir.  
  
 Daha fazla bilgi için bkz: [değer sınıflar ve yapılar](../cppcx/value-classes-and-structs-c-cx.md).  
  
### <a name="partial-classes"></a>Kısmi sınıflar  
 Parçalı sınıf özelliği birden çok dosya tanımlanması için bir sınıf sağlar. Kod üretimi araçları gibi XAML Düzenleyicisi'ni düzenleme dosya dokunmadan bir dosyayı değiştirmek için öncelikle etkinleştirmek için kullanılır.  
  
 Daha fazla bilgi için bkz: [kısmi sınıflar](../cppcx/partial-classes-c-cx.md)  
  
### <a name="properties"></a>Özellikler  
 Bir özellik, herhangi bir Windows çalışma zamanı türü ortak veri üyesi olduğundan ve get/set yöntemi çifti olarak uygulanır. Genel alan değilmiş gibi istemci kodu bir özelliğe erişir. Hiçbir özel gerektiren bir özellik get veya set kod olarak bilinen bir *Önemsiz özelliği* ve açık get bildirilen veya set yöntemlerini.  
  
 Daha fazla bilgi için bkz: [özellikleri](../cppcx/properties-c-cx.md).  
  
### <a name="windows-runtime-collections-in-ccx"></a>Windows çalışma zamanı koleksiyonları C + +/ CX  
 Windows Çalışma Zamanı Modülü arabirimler her dil kendi şekilde uygulayan koleksiyon türleri için kümesini tanımlar. C + +/ CX sağlar uygulamalarında [Platform::Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md), [Platform::Collections sınıfı](../cppcx/platform-collections-map-class.md)ve ile uyumlu olan diğer ilgili somut koleksiyon türleri kendi Standart Şablon kitaplığı (STL) ortaklarınıza.  
  
 Daha fazla bilgi için bkz: [koleksiyonları](../cppcx/collections-c-cx.md).  
  
### <a name="template-ref-classes"></a>Şablon ref sınıfları  
 Özel ve iç ref sınıfları şablonlu ve özelleştirilmiş olabilir.  
  
 Daha fazla bilgi için bkz: [şablon ref sınıfları](../cppcx/template-ref-classes-c-cx.md).  
  
### <a name="interfaces"></a>Arabirimler  
 Windows çalışma zamanı arabirimi bir dizi ortak özellikleri, yöntemleri ve arabirimden devralıyorsa ref sınıfta veya ref yapı uygulamalıdır olayları tanımlar.  
  
 Daha fazla bilgi için bkz: [arabirimleri](../cppcx/interfaces-c-cx.md).  
  
### <a name="enums"></a>Numaralandırmalar  
 Windows çalışma zamanı enum sınıfında c++ kapsamlı bir liste benzer. [Flags] özniteliği uygulanan sürece Int32, temel alınan türüdür — bu durumda, temel alınan uint32 türüdür.  
  
 Daha fazla bilgi için bkz: [numaralandırmaları](../cppcx/enums-c-cx.md).  
  
### <a name="delegates"></a>Temsilciler  
 Windows çalışma zamanı bir temsilci c++ std::function nesnesine benzer. Uyumlu imzası olan istemci tarafından sağlanan işlevleri çağırmak için kullanılan ref sınıfı özel bir tür değil.  Temsilciler, bir olay türü olarak Windows çalışma zamanı'nda en yaygın olarak kullanılır.  
  
 Daha fazla bilgi için bkz: [Temsilciler](../cppcx/delegates-c-cx.md).  
  
### <a name="exceptions"></a>Özel Durumlar  
 C + +/ CX, özel durum türleri yakalayabilir [std::exception](../standard-library/exception-class.md) türleri ve [Platform::Exception](../cppcx/platform-exception-class.md) türleri.  
  
 Daha fazla bilgi için bkz: [özel durumları](../cppcx/exceptions-c-cx.md).  
  
### <a name="events"></a>Olaylar  
 Bir olay, bir ref sınıfı ya da bir temsilci türü türü olan ref yapısı ortak bir üyesidir. Bir olay yalnızca çağrılabilir — diğer bir deyişle, harekete — sahip olan sınıf tarafından. Ancak, istemci kodu olay işleyicileri olarak bilinir ve sahip olan sınıf olay başlatıldığında çağrılan kendi işlevler sağlayabilir.  
  
 Daha fazla bilgi için bkz: [olayları](../cppcx/events-c-cx.md).  
  
### <a name="casting"></a>Atama  
 C + +/ CX destekleyen standart C++ cast işleçleri [static_cast](../cpp/static-cast-operator.md), [dynamic_cast](../cpp/dynamic-cast-operator.md), ve [reinterpret_cast](../cpp/reinterpret-cast-operator.md)hem de **safe_cast**C + özgü işleci +/ CX.  
  
 Daha fazla bilgi için bkz: [atama](../cppcx/casting-c-cx.md).  
  
### <a name="boxing"></a>Kutulama  
 Paketlenmiş bir değişken başvurusu semantiği gerekli olduğu durumlarda bir başvuru türü kaydırılan bir değer türüdür.  
  
 Daha fazla bilgi için bkz: [kutulama](../cppcx/boxing-c-cx.md).  
  
### <a name="attributes"></a>Öznitelikler  
 Bir öznitelik herhangi bir Windows çalışma zamanı türü veya tür üyesi uygulanabilir ve çalışma zamanında Denetlenmekte bir meta veri değeridir. Windows çalışma zamanı ortak öznitelikleri kümesini tanımlayan `Windows::Foundation::Metadata` ad alanı. Kullanıcı tanımlı öznitelikler ortak arabirimlerde Windows çalışma zamanı tarafından bu sürümde desteklenmez.  
  
## <a name="api-deprecation"></a>API kullanımdan kaldırma  
 Ortak API'ler Windows çalışma zamanı sistem türleri tarafından kullanılan aynı özniteliğini kullanarak kullanım dışı olarak işaretlemek açıklar.  
  
 Daha fazla bilgi için bkz: [türleri ve üyeleri onaysız kılınmadan](../cppcx/deprecating-types-and-members-c-cx.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)
