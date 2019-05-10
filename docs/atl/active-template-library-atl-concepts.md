---
title: Etkin Şablon Kitaplığı (ATL) Kavramlar
ms.date: 05/06/2019
helpviewer_keywords:
- ATL, about ATL
ms.assetid: a3960991-4d76-4da5-9568-3fa7fde53ff4
ms.openlocfilehash: 785b929e935962f6461ffbc3722f573a61cb8749
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221305"
---
# <a name="active-template-library-atl-concepts"></a>Etkin Şablon Kitaplığı (ATL) Kavramlar

Etkin Şablon kitaplığı (ATL), küçük, hızlı Bileşen Nesne Modeli (COM) nesnelerini oluşturmanıza olanak sağlayan şablon tabanlı C++ sınıfları kümesidir. Kalıp uygulamalar, ikili arabirimler, standart COM Numaralandırıcı arabirimleri, bağlantı noktaları, etiket arabirimleri ve ActiveX denetimleri de dahil olmak üzere anahtar COM özellikleri için özel destek var.

ATL programlama birçok bunu yaparsanız, COM ve .NET öznitelikleri hakkında daha fazla bilgi edinmek, COM programlama basitleştirmek için tasarlanmış isteyebilirsiniz. Daha fazla bilgi için [Öznitelikli Programlama](../windows/attributed-programming-concepts.md). (COM ve .NET öznitelikleri olduğundan ile karıştırılmamalıdır \[ \[özniteliği]] içinde özellik C++ standart.)

## <a name="in-this-section"></a>Bu Bölümde

[ATL öğretici](../atl/active-template-library-atl-tutorial.md)<br/>
Bir denetimin oluşturulmasını müşteri adayları ve işleminde bazı ATL temelleri gösterir.

[COM ve ATL’ye Giriş](../atl/introduction-to-com-and-atl.md)<br/>
Bileşen Nesne Modeli (COM) arkasında önemli kavramlar tanıtılmaktadır. Bu makalede, ATL nedir ve hangi durumlarda kullanmalıdır de kısaca açıklanmaktadır.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)<br/>
Çeşitli ATL sınıfları ve bu sınıfların nasıl uygulandığını arasındaki ilişkiyi açıklar.

[Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)<br/>
ATL açısından ikili arabirimler açıklanmaktadır.

[ATL Koleksiyonları ve Numaralandırıcıları](../atl/atl-collections-and-enumerators.md)<br/>
Uygulama ve koleksiyonları ve numaralandırıcıları ATL içinde oluşturulmasını açıklar

[Bileşik Denetim temelleri](../atl/atl-composite-control-fundamentals.md)<br/>
Bileşik denetim oluşturmak için adım adım yönergeler sağlar. Bileşik Denetim, diğer ActiveX denetimlerini veya Windows denetimlerini içerebilen ActiveX denetiminin bir türdür.

[ATL Denetim Kapsamı SSS](../atl/atl-control-containment-faq.md)<br/>
ATL denetimleriyle barındırma ile ilgili temel soruları kapsar

[ATL COM Özellik Sayfaları](../atl/atl-com-property-pages.md)<br/>
Belirtin ve COM özellik sayfaları uygulama işlemi gösterilmektedir.

[DHTML Denetimleri için ATL Desteği](../atl/atl-support-for-dhtml-controls.md)<br/>
DHTML denetimi oluşturmak için adım adım yönergeler sağlar.

[ATL Bağlantı Noktaları](../atl/atl-connection-points.md)<br/>
Bağlantı noktaları nelerdir ve ATL bunları nasıl uyguladığını açıklanmaktadır.

[Olay İşleme ve ATL](../atl/event-handling-and-atl.md)<br/>
ATL kullanarak COM olayları işlemek için atmanız gereken adımları açıklar [Idispeventımpl](../atl/reference/idispeventimpl-class.md) ve [Idispeventsimpleımpl](../atl/reference/idispeventsimpleimpl-class.md) sınıfları.

[ATL ve Ücretsiz İş Parçacıklı Sıralayıcı](../atl/atl-and-the-free-threaded-marshaler.md)<br/>
Ayrıntılar sağlayan ücretsiz iş parçacıklı sıralayıcı (FTM) toplamak kendi sınıfınızı ATL Basit Nesne Sihirbazı'nın seçeneği sağlar.

[Projenin iş parçacıklı Model belirtme](../atl/specifying-the-threading-model-for-a-project-atl.md)<br/>
Projenizde iş parçacığı için ilgili çalışma zamanı performansını denetlemek kullanılabilen makroları tanımlar.

[ATL Modül Sınıfları](../atl/atl-module-classes.md)<br/>
Yeni modül sınıfları için ATL 7.0 açıklanır. Modül sınıfları tarafından ATL gerekli temel işlevlerini uygulamak

[ATL Hizmetleri](../atl/atl-services.md)<br/>
Bir hizmet uygulandığında gerçekleşen olaylar dizisini kapsar. Ayrıca bazı hizmet geliştirme ile ilgili kavramları hakkında konuşuyor.

[ATL Pencere Sınıfları](../atl/atl-window-classes.md)<br/>
Nasıl oluşturulacağını, üst ve alt windows ATL içinde açıklar ATL pencere sınıfları, COM sınıfları değildir.

[ATL Koleksiyon Sınıfları](../atl/atl-collection-classes.md)<br/>
Dizi kullanmayı açıklar ve ATL içinde eşler

[ATL kayıt defteri bileşeni (Kaydedici)](../atl/atl-registry-component-registrar.md)<br/>
ATL söz dizimi ve değiştirilebilir parametreler açıklanmaktadır. Ayrıca, kayıt şirketi statik bağlantı ayarlama olunacağı açıklanmaktadır.

[ATL ve C Çalışma Zamanı Koduyla Programlama](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
C çalışma zamanı kitaplığı (CRT) statik veya dinamik olarak bağlama avantajları anlatılmaktadır.

[CComBSTR ile programlama](../atl/programming-with-ccombstr-atl.md)<br/>
Programlama yaparken dikkat gerektiren birkaç durum anlatılmaktadır `CComBSTR`.

[Kodlama başvurusu](../atl/atl-encoding-reference.md)<br/>
İşlevlerle makrolar kodlama, bir dizi onaltılık uuencode gibi ortak Internet standartları ve UTF8 atlenc.h içinde desteği sağlar.

[Yardımcı programları başvurusu](../atl/atl-utilities-reference.md)<br/>
Yollar ve URL'leri biçiminde işlemek için kod sağlar [CPathT](../atl/reference/cpatht-class.md) ve [CUrl](../atl/reference/curl-class.md). İş parçacığı havuzu [CThreadPool](../atl/reference/cthreadpool-class.md), kendi uygulamalarında kullanılabilir. Bu kod, atlpath.h ve atlutil.h bulunabilir.

## <a name="related-sections"></a>İlgili Bölümler

[ATL örnekleri](../overview/visual-cpp-samples.md)<br/>
Açıklamaları ve örnek ATL programları için bağlantılar sağlar.

[ATL Projesi Oluşturma](../atl/reference/creating-an-atl-project.md)<br/>
ATL projesi Sihirbazı hakkında bilgi içerir.

[ATL Denetimi Sihirbazı](../atl/reference/atl-control-wizard.md)<br/>
Nasıl sınıf ekleneceğini açıklar.

[Öznitelikli Programlama](../windows/attributed-programming-concepts.md)<br/>
COM programlama yanı sıra daha ayrıntılı konulara bağlantılar listesini basitleştirmek için öznitelikleri kullanma hakkında genel bir bakış sağlar.

[ATL Sınıfına Genel Bakış](../atl/atl-class-overview.md)<br/>
Başvuru bilgileri ve ATL sınıfları için bağlantılar sağlar.
