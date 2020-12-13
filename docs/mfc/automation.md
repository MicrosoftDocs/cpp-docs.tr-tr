---
description: 'Daha fazla bilgi edinin: Otomasyon'
title: Otomatikleştirme
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers, about Automation servers
- clients, Automation
- programmatic control [MFC]
- properties [MFC], Automation
- MFC, COM support
- OLE Automation
- Automation
- servers [MFC], Automation
- Automation clients
- sample applications [MFC], Automation
- methods [MFC]
- passing parameters, Automation
- Automation method [MFC]
- Automation, passing parameters
- Automation property [MFC]
- MFC COM, Automation
- methods [MFC], Automation
ms.assetid: 329117f0-c1aa-4680-a901-bfb71277dfba
ms.openlocfilehash: 8a038a3590c3db9c90c8f99eaaa6f98d2c4e20cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339845"
---
# <a name="automation"></a>Otomatikleştirme

Otomasyon (eski adıyla OLE Otomasyonu), bir uygulamanın başka bir uygulamada uygulanan nesneleri işlemesini veya işlenebilmeleri için nesneleri kullanıma sunmasını mümkün kılar.

[Otomasyon sunucusu](automation-servers.md) , işlevselliğini [Otomasyon istemcileri](automation-clients.md)olarak adlandırılan diğer uygulamalara com arabirimleri aracılığıyla kullanıma sunan bir uygulamadır (com Server türüdür). Bu pozlama, Otomasyon istemcilerinin nesnelere doğrudan erişerek ve sağladıkları Hizmetleri kullanarak belirli işlevleri otomatikleştirmesini sağlar.

Otomasyon sunucuları ve istemcileri, her zaman türetilmiş `IDispatch` ve otomasyon türleri olarak adlandırılan belirli bir veri türleri kümesini alıp döndüren com arabirimlerini kullanır. Otomasyon arabirimini kullanıma sunan tüm nesneleri otomatikleştirerek diğer uygulamalardan erişebileceğiniz Yöntemler ve Özellikler sağlayabilirsiniz. Otomasyon hem OLE hem de COM nesneleri için kullanılabilir. Otomatik nesne yerel veya uzak olabilir (ağ üzerinden erişilebilen başka bir makineye); Bu nedenle, iki Otomasyon kategorisi vardır:

- Otomasyon (yerel).

- Uzaktan Otomasyon (ağ üzerinden, dağıtılmış COM veya DCOM kullanarak).

Uygulamalar diğer uygulamalar için yararlı işlevler sağladığınızda nesneleri kullanıma sunma yararlı olur. Örneğin, bir ActiveX denetimi bir Otomasyon sunucusu türüdür; ActiveX denetimini barındıran uygulama, bu denetimin Otomasyon istemcsahiptir.

Başka bir örnek olarak, bir sözcük işlemcisi, yazım denetimi işlevini diğer programlarla kullanıma sunabilir. Nesnelerin açığa çıkması, satıcıların diğer uygulamaların kullanıma hazırlamış işlevlerini kullanarak uygulamalarını geliştirmesine olanak sağlar. Bu şekilde, otomasyon, uygulama düzeyindeki yeniden kullanılabilirlik ve kapsülleme gibi nesne odaklı programlama prensiplerini uygular.

Destek Otomasyonu, kullanıcılara ve çözüm sağlayıcılarına sağladığı daha önemli bir çözümdür. Otomasyon, yaygın, iyi tanımlanmış bir arabirim aracılığıyla uygulama işlevselliğini ortaya çıkararak, uygulamaya özgü çeşitli makro dilleri yerine Microsoft Visual Basic gibi tek bir genel programlama dilinde kapsamlı çözümler oluşturmayı mümkün kılar.

Microsoft Excel ve Microsoft Visual C++ gibi birçok ticari uygulama, işlevlerinin çoğunu otomatik hale getirmenizi sağlar. Örneğin, Visual C++ ' de, yapılandırmaları, kod düzenlemenin yönlerini veya hata ayıklama görevlerini otomatikleştirebilmek için VBScript makroları yazabilirsiniz.

## <a name="passing-parameters-in-automation"></a><a name="_core_passing_parameters_in_automation"></a> Otomasyon 'da parametreleri geçirme

Otomasyon yöntemleri oluştururken bir zorluk, otomasyon sunucuları ve istemciler arasında veri geçirmek için Tekdüzen "güvenli" mekanizması sağlamaya yardımcı olur. Otomasyon, verileri geçirmek için **değişken** türünü kullanır. **Değişken** türü etiketli bir birleşimdir. Bu, değer için bir veri üyesine (Bu anonim bir C++ birleşimi) ve birleşimde depolanan bilgilerin türünü gösteren bir veri üyesine sahiptir. **Değişken** türü bir dizi standart veri türünü destekler: 2-ve 4 baytlık tamsayılar, 4 ve 8 baytlık kayan noktalı sayılar, dizeler ve Boole değerleri. Ayrıca, **HRESULT** (OLE hata kodları), **para birimi** (sabit noktalı sayısal tür) ve **Tarih** (mutlak tarih ve saat) türlerini ve bunlara yönelik işaretçileri `IUnknown` ve arabirimleri de destekler `IDispatch` .

**Değişken** türü [cotavariant](reference/colevariant-class.md) sınıfında kapsüllenir. Destekleyici **para birimi** ve **Tarih** sınıfları [Copacurrency](reference/colecurrency-class.md) ve [cotadatetime](../atl-mfc-shared/reference/coledatetime-class.md) sınıflarında kapsüllenir.

## <a name="automation-samples"></a>Otomasyon örnekleri

- [AUTOCLIK](../overview/visual-cpp-samples.md) Bu örneği kullanarak Otomasyon tekniklerini öğrenin ve uzaktan Otomasyon öğrenmeye yönelik bir temel olarak.

- [Acdual](../overview/visual-cpp-samples.md) Bir Otomasyon sunucu uygulamasına çift arabirimler ekler.

- [Calcdriv](../overview/visual-cpp-samples.md) MFCCALC 'yi yönlendiren Otomasyon istemci uygulaması.

- [InProc](../overview/visual-cpp-samples.md) Bir In-Process Automation sunucu uygulaması gösterir.

- [Ipdrive](../overview/visual-cpp-samples.md) INPROC 'yi yönlendiren Otomasyon istemci uygulaması.

- [MFCCALC](../overview/visual-cpp-samples.md) Bir Otomasyon istemci uygulamasını gösterir.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Otomasyon Istemcileri](automation-clients.md)

- [Otomasyon sunucuları](automation-servers.md)

- [OLE](ole-in-mfc.md)

- [Etkin teknoloji](mfc-com.md)

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Otomasyon sınıfı ekleme](automation-servers.md)

- [Tür kitaplıklarını kullanma](automation-clients-using-type-libraries.md)

- [Otomasyon sunucularına erişme](automation-servers.md)

- [C++ ' da Otomasyon istemcileri yazma](automation-clients.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC COM](mfc-com.md)
