---
title: Etkin Şablon Kitaplığı (ATL) Kavramlar
ms.date: 05/06/2019
helpviewer_keywords:
- ATL, about ATL
ms.assetid: a3960991-4d76-4da5-9568-3fa7fde53ff4
ms.openlocfilehash: c87eedff5b6ce7d906c05ac0678425af575f0af8
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504277"
---
# <a name="active-template-library-atl-concepts"></a>Etkin Şablon Kitaplığı (ATL) Kavramlar

Etkin Şablon kitaplığı (ATL), küçük, hızlı bileşen nesne modeli (COM) nesneleri oluşturmanıza olanak sağlayan bir şablon tabanlı C++ sınıfları kümesidir. Hisse senedi uygulamaları, çift arabirimler, standart COM Numaralandırıcı arabirimleri, bağlantı noktaları, yırkal arabirimleri ve ActiveX denetimleri dahil olmak üzere temel COM özellikleri için özel destek içerir.

Çok sayıda ATL programlama yaparsanız, com programlama basitleştirilmesi için tasarlanan COM ve .NET öznitelikleri hakkında daha fazla bilgi edinmek isteyeceksiniz. Daha fazla bilgi için bkz. [öznitelikli programlama](../windows/attributes/cpp-attributes-com-net.md). (COM ve .NET özniteliklerinin \[ \[ özniteliği]] C++ standardında özelliği.)

## <a name="in-this-section"></a>Bu Bölümde

[COM ve ATL'ye Giriş](introduction-to-com-and-atl.md)<br/>
Bileşen nesne modeli (COM) arkasındaki ana kavramları tanıtır. Bu makalede ayrıca ATL 'nin ne olduğu ve ne zaman kullanılacağı kısaca açıklanmaktadır.

[ATL COM nesnelerinin temelleri](fundamentals-of-atl-com-objects.md)<br/>
Çeşitli ATL sınıfları ve bu sınıfların nasıl uygulandığı arasındaki ilişkiyi açıklar.

[Çift arabirimler ve ATL](dual-interfaces-and-atl.md)<br/>
ATL perspektifinden ikili arabirimleri açıklar.

[ATL koleksiyonları ve Numaralandırıcılar](atl-collections-and-enumerators.md)<br/>
ATL 'de koleksiyonların ve Numaralandırmaların uygulanmasını ve oluşturulmasını açıklar.

[Bileşik denetim temelleri](atl-composite-control-fundamentals.md)<br/>
Bileşik denetim oluşturmak için adım adım yönergeler sağlar. Bileşik denetim, diğer ActiveX denetimlerini veya Windows denetimlerini içerebilen bir ActiveX denetimi türüdür.

[ATL Denetim Kapsamı SSS](atl-control-containment-faq.md)<br/>
ATL ile barındırma denetimleriyle ilgili temel soruları kapsar.

[ATL COM özellik sayfaları](atl-com-property-pages.md)<br/>
COM özellik sayfalarını belirtme ve uygulamayı nasıl kullanacağınızı gösterir.

[DHTML denetimleri için ATL desteği](atl-support-for-dhtml-controls.md)<br/>
DHTML denetimi oluşturmak için adım adım yönergeler sağlar.

[ATL bağlantı noktaları](atl-connection-points.md)<br/>
Hangi bağlantı noktalarının olduğunu ve ATL 'in bunları nasıl uyguladığını açıklar.

[Olay Işleme ve ATL](event-handling-and-atl.md)<br/>
ATL 'nin [IDispEventImpl](reference/idispeventimpl-class.md) ve [IDispEventSimpleImpl](reference/idispeventsimpleimpl-class.md) sınıflarını kullanarak com olaylarını işlemek için gerçekleştirmeniz gereken adımları açıklar.

[ATL ve ücretsiz Iş parçacıklı Sıralayıcı](atl-and-the-free-threaded-marshaler.md)<br/>
, Sınıfınızın boş iş parçacıklı Sıralayıcı 'yı (FTM) toplamasını sağlayan, ATL basit nesne Sihirbazı 'nın seçeneği hakkında ayrıntılı bilgi sağlar.

[Projenin Iş parçacığı modelini belirtme](specifying-the-threading-model-for-a-project-atl.md)<br/>
Projenizdeki iş parçacığı ile ilgili çalışma zamanı performansını denetlemek için kullanılabilen makroları açıklar.

[ATL modül sınıfları](atl-module-classes.md)<br/>
ATL 7,0 için yeni olan modül sınıflarını açıklar. Modül sınıfları, ATL için gereken temel işlevselliği uygular.

[ATL Hizmetleri](atl-services.md)<br/>
Bir hizmet uygulandığında oluşan olay serisini ele alır. Ayrıca hizmet geliştirme ile ilgili kavramların bazıları hakkında da konuşur.

[ATL pencere sınıfları](atl-window-classes.md)<br/>
ATL 'de Windows 'un nasıl oluşturulduğunu, süper ve alt sınıfını açıklar. ATL pencere sınıfları COM sınıfları değildir.

[ATL koleksiyon sınıfları](atl-collection-classes.md)<br/>
ATL 'de dizilerin ve eşlemelerin nasıl kullanılacağını açıklar.

[ATL kayıt defteri bileşeni (kaydedici)](atl-registry-component-registrar.md)<br/>
ATL betik sözdizimi ve değiştirilebilen parametreleri açıklar. Ayrıca, kaydedici için statik bağlantı ayarlamayı da açıklar.

[ATL ve C çalışma zamanı koduyla programlama](programming-with-atl-and-c-run-time-code.md)<br/>
C çalışma zamanı kitaplığı 'na (CRT) statik veya dinamik olarak bağlanmanın avantajlarını açıklar.

[CComBSTR ile programlama](programming-with-ccombstr-atl.md)<br/>
İle programlama yaparken dikkatli olması gereken birkaç durum açıklanır `CComBSTR` .

[Kodlama başvurusu](atl-encoding-reference.md)<br/>
Atlenc. h içinde UUENCODE, onaltılı ve UTF8 gibi yaygın Internet standartları aralığında kodlamayı destekleyen işlevler ve makrolar sağlar.

[Yardımcı programlar başvurusu](atl-utilities-reference.md)<br/>
Yolları ve URL 'Leri [CPathT](reference/cpatht-class.md) ve [kıvrımlı](reference/curl-class.md)biçiminde işlemek için kod sağlar. İş parçacığı havuzu, [CThreadPool](reference/cthreadpool-class.md), kendi uygulamalarınızda kullanılabilir. Bu kod, atlpath. h ve atlutil. h içinde bulunabilir.

## <a name="related-sections"></a>İlgili Bölümler

[ATL öğreticisi](active-template-library-atl-tutorial.md)<br/>
Bir denetim oluşturma işlemi boyunca size yol gösterir ve işlemdeki bazı ATL temellerini gösterir.

[ATL örnekleri](../overview/visual-cpp-samples.md)<br/>
ATL örnek programlarının açıklamalarını ve bağlantılarını sağlar.

[ATL Projesi Oluşturma](reference/creating-an-atl-project.md)<br/>
ATL Proje Sihirbazı hakkındaki bilgileri içerir.

[ATL Denetim Sihirbazı](reference/atl-control-wizard.md)<br/>
Sınıfların nasıl ekleneceğini açıklar.

[Öznitelikli programlama](../windows/attributes/cpp-attributes-com-net.md)<br/>
COM programlamasına ve daha ayrıntılı konuların bağlantıların bir listesini basitleştirmek için öznitelikleri kullanma hakkında genel bakış sağlar.

[ATL sınıfına genel bakış](atl-class-overview.md)<br/>
, ATL sınıflarına yönelik başvuru bilgileri ve bağlantılar sağlar.
