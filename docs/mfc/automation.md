---
title: Otomasyon
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
ms.openlocfilehash: e9320ccf7a21c6110c51366fa8af96596512a4a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370817"
---
# <a name="automation"></a>Otomasyon

Otomasyon (eski adıyla OLE Automation), bir uygulamanın başka bir uygulamada uygulanan nesneleri işlemesini veya nesneleri manipüle edilebilmeleri için ortaya çıkarmasını mümkün kılar.

[Otomasyon sunucusu,](../mfc/automation-servers.md) işlevlerini COM arabirimleri aracılığıyla [otomasyon istemcileri](../mfc/automation-clients.md)adı verilen diğer uygulamalara maruz eden bir uygulamadır (bir COM sunucusu türüdür). Pozlama, Otomasyon istemcilerinin nesnelere doğrudan erişerek ve sağladıkları hizmetleri kullanarak belirli işlevleri otomatikleştirmesini sağlar.

Otomasyon sunucuları ve istemciler, her `IDispatch` zaman otomasyon türleri adı verilen belirli bir veri türü kümesinden türetilen ve iade edilen COM arabirimleri kullanır. Diğer uygulamalardan erişebileceğiniz yöntemler ve özellikler sağlayarak Otomasyon arabirimini ortaya çıkaran herhangi bir nesneyi otomatikleştirebilirsiniz. Otomasyon hem OLE hem de COM nesneleri için kullanılabilir. Otomatik nesne yerel veya uzak olabilir (ağ üzerinden erişilebilen başka bir makinede); bu nedenle otomasyonun iki kategorisi vardır:

- Otomasyon (yerel).

- Uzaktan Otomasyon (bir ağ üzerinden, Distributed COM veya DCOM kullanarak).

Uygulamalar diğer uygulamalar için yararlı işlevsellik sağladığında nesneleri açığa çıkarmak yararlıdır. Örneğin, ActiveX denetimi bir Otomasyon sunucusu türüdür; ActiveX denetimini barındıran uygulama, bu kontrolün otomasyon istemcisidir.

Başka bir örnek olarak, bir sözcük işlemci yazım denetimi işlevini diğer programlara gösterebilir. Nesnelerin pozlama, satıcıların diğer uygulamaların hazır işlevselliğini kullanarak uygulamalarını geliştirmelerine olanak tanır. Bu şekilde Otomasyon, yeniden kullanılabilirlik ve kapsülleme gibi nesne yönelimli programlama ilkelerinden bazılarını uygulama düzeyinde uygular.

Daha da önemlisi Otomasyon'un kullanıcılara ve çözüm sağlayıcılarına sağladığı destektir. Otomasyon, uygulama işlevselliğini ortak ve iyi tanımlanmış bir arayüz aracılığıyla ortaya çıkararak, uygulamaya özgü makro diller yerine Microsoft Visual Basic gibi tek bir genel programlama dilinde kapsamlı çözümler oluşturmayı mümkün kılar.

Microsoft Excel ve Microsoft Visual C++ gibi birçok ticari uygulama, işlevselliklerinin çoğunu otomatikleştirmenize olanak sağlar. Örneğin, Visual C++'da, yapıları, kod düzenleme nin yönlerini veya hata ayıklama görevlerini otomatikleştirmek için VBScript makroları yazabilirsiniz.

## <a name="passing-parameters-in-automation"></a><a name="_core_passing_parameters_in_automation"></a>Otomasyonda Geçiş Parametreleri

Otomasyon yöntemleri oluşturmada bir zorluk otomasyon sunucuları ve istemciler arasında veri aktarmak için tek tip bir "güvenli" mekanizma sağlamak için yardımcı olmaktır. Otomasyon, verileri aktarmak için **VARIANT** türünü kullanır. **VARIANT** türü etiketli bir birliktir. Değer için bir veri üyesi (bu anonim bir C++ birleşmesidir) ve birleşimde depolanan bilgi türünü belirten bir veri üyesi vardır. **VARIANT** türü bir dizi standart veri türünü destekler: 2- ve 4 bayt tamsayılar, 4- ve 8 bayt kayan nokta numaraları, dizeleri ve Boolean değerleri. Buna ek olarak, **HRESULT** (OLE hata kodları), **CURRENCY** (sabit nokta sayısal türü) ve **DATE** (mutlak tarih ve `IUnknown` `IDispatch` saat) türlerinin yanı sıra işaretçileri ve arabirimleri destekler.

**VARIANT** türü [COleVariant](../mfc/reference/colevariant-class.md) sınıfında kapsüllenir. Destekleyici **PARA VE** **DATE** sınıfları COleCurrency ve [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) sınıflarında kapsüllenir. [COleCurrency](../mfc/reference/colecurrency-class.md)

## <a name="automation-samples"></a>Otomasyon Örnekleri

- [OTOCLIK](../overview/visual-cpp-samples.md) Otomasyon tekniklerini öğrenmek ve Uzaktan Otomasyon u yürütmek için bir temel olarak bu çeteyi kullanım.

- [ACDUAL](../overview/visual-cpp-samples.md) Otomasyon sunucusu uygulamasına çift arabirim ekler.

- [CALCDRIV](../overview/visual-cpp-samples.md) MFCCALC sürüş otomasyon istemci uygulaması.

- [INPROC](../overview/visual-cpp-samples.md) İşlem Içi Otomasyon sunucu uygulamasını gösterir.

- [IPDRIVE](../overview/visual-cpp-samples.md) INPROC'u yönlendiren otomasyon istemci uygulaması.

- [MFCCALC](../overview/visual-cpp-samples.md) Bir Otomasyon istemci sİstemi uygulaması gösterir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Otomasyon Müşterileri](../mfc/automation-clients.md)

- [Otomasyon Sunucuları](../mfc/automation-servers.md)

- [OLE](../mfc/ole-in-mfc.md)

- [Aktif Teknoloji](../mfc/mfc-com.md)

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsun?

- [Otomasyon sınıfı ekleme](../mfc/automation-servers.md)

- [Tür kitaplıklarını kullanma](../mfc/automation-clients-using-type-libraries.md)

- [Erişim otomasyon sunucuları](../mfc/automation-servers.md)

- [C++'da otomasyon istemcileri yazın](../mfc/automation-clients.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC COM](../mfc/mfc-com.md)
