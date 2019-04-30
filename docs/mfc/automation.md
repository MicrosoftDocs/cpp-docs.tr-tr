---
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
ms.openlocfilehash: 7818aa708a762f2a284be029a6c3f3facd971d9a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374161"
---
# <a name="automation"></a>Otomatikleştirme

Otomasyon (eski adıyla OLE Otomasyonu da bilinir), bir uygulama için başka bir uygulamaya uygulanan nesneleri değiştirmek ya da bunlar işlenebilir nesneleri kullanıma sunmak için mümkün kılar.

Bir [Otomasyon sunucusu](../mfc/automation-servers.md) COM arabirimleri olarak adlandırılan, diğer uygulamalar aracılığıyla işlevselliği kullanıma sunan bir uygulama (COM sunucusu türünü) [Otomasyon istemcileri](../mfc/automation-clients.md). Açığa Otomasyon istemcileri belirli işlevleri doğrudan nesnelere erişme ve sağladıkları hizmetler kullanarak otomatik hale getirmenizi sağlar.

Otomasyon sunucuları ve istemciler kullanmak her zaman türetilmiştir COM arabirimleri `IDispatch` almak ve veri türleri Otomasyon türlerine adlı belirli bir dizi döndürür. Bir Otomasyon arabirimi kullanıma sunan herhangi bir nesne, yöntemleri ve diğer uygulamalardan erişebildiği özellikleri sağlayan otomatik hale getirebilirsiniz. Otomasyon OLE hem COM nesneleri için kullanılabilir. Otomatik nesne yerel veya uzak (başka bir makinedeki bir ağ üzerinden erişilebilir); olabilir. Bu nedenle Otomasyon iki kategorisi vardır:

- Otomasyon (yerel).

- Uzak Otomasyon (üzerinde dağıtılmış COM'u ya da DCOM kullanarak bir ağ).

Uygulamaların diğer uygulamalar için kullanışlı işlevler sağladığınızda nesnelerini kullanıma sunma yararlıdır. Örneğin, bir ActiveX denetimi Otomasyon sunucusu türüdür; ActiveX denetimi barındırma denetimin otomasyon istemci uygulamasıdır.

Başka bir örnek olarak, bir sözcük işlemcisi yazım denetimi işlevselliğini diğer programları doğurabilir. Nesneleri riskini diğer uygulamaların kullanıma hazır işlevler kullanılarak uygulamalarını geliştirmek satıcıları sağlar. Bu şekilde, Otomasyon bazı çalışmalarında ve saklama, uygulamaların kendileri düzeyinde gibi nesne yönelimli programlama ilkeler geçerlidir.

Otomasyon, kullanıcılar ve çözüm sağlayıcıları için sağladığı desteği daha önemlidir. Ortak, iyi tanımlanmış bir arabirim aracılığıyla uygulama işlevselliği kullanıma sunma, otomasyon, bir tek genel programlama dili, Microsoft Visual Basic gibi de yerine kapsamlı çözümler çeşitli mümkün kılar uygulamaya özgü makrosu diller.

Microsoft Excel ve Microsoft Visual C++ gibi birçok ticari uygulama işlevleriyle büyük bölümünü otomatikleştirmek sağlar. Örneğin, Visual C++'da, yapıları otomatik hale getirmek için VBScript makroları, düzenleme ve hata ayıklama görevleri kod yönlerini yazabilirsiniz.

##  <a name="_core_passing_parameters_in_automation"></a> Otomasyon parametreleri geçirme

Otomasyon yöntemi oluşturma bir zorluk, otomasyon sunucuları ve istemciler arasında veri iletmek için Tekdüzen bir "güvenli" mekanizma sağlamanız yardımcı oluyor. Otomasyon kullandığı **değişken** veri iletmek için türü. **Değişken** etiketli bir birleşim türüdür. Bu, değerin (Bu, anonim bir C++ birleşimi) için bir veri üyesi ve birleşimde depolanan bilgi türünü belirten bir veri üyesi vardır. **Değişken** türü bir dizi standart veri türlerini destekler: 2 ve 4 baytlık tamsayılar, 4 ve 8 baytlık kayan noktalı sayıların, dize ve Boole değerleri. Ayrıca, desteklediği **HRESULT** (OLE hata kodları) **para birimi** (sabit noktalı sayısal tür) ve **tarih** (mutlak tarih ve saat) türleri, işaretçileriyanısıra`IUnknown` ve `IDispatch` arabirimleri.

**Değişken** türü içinde saklanmış olduğu [COleVariant](../mfc/reference/colevariant-class.md) sınıfı. Destekleyici **para birimi** ve **tarih** sınıfları alınır [COleCurrency](../mfc/reference/colecurrency-class.md) ve [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) sınıfları.

## <a name="automation-samples"></a>Otomasyon örnekleri

- [AUTOCLIK](../overview/visual-cpp-samples.md) Otomasyon teknikleri öğrenmek için bu örneği kullanmak ve Uzaktan Otomasyon öğrenmek için bir temel olarak.

- [ACDUAL](../overview/visual-cpp-samples.md) Otomasyon sunucu uygulaması için çift arabirim ekler.

- [CALCDRIV](../overview/visual-cpp-samples.md) MFCCALC sürüş otomasyon istemci uygulaması.

- [InProc](../overview/visual-cpp-samples.md) bir işlem içi Otomasyon sunucu uygulaması gösterir.

- [IPDRIVE](../overview/visual-cpp-samples.md) InProc sürüş otomasyon istemci uygulaması.

- [MFCCALC](../overview/visual-cpp-samples.md) bir otomasyon istemci uygulaması gösterir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Otomasyon İstemcileri](../mfc/automation-clients.md)

- [Otomasyon Sunucuları](../mfc/automation-servers.md)

- [OLE](../mfc/ole-in-mfc.md)

- [Etkin teknoloji](../mfc/mfc-com.md)

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz

- [Bir otomasyon sınıfı Ekle](../mfc/automation-servers.md)

- [Tür kitaplıklarını kullanma](../mfc/automation-clients-using-type-libraries.md)

- [Erişim otomasyon sunucuları](../mfc/automation-servers.md)

- [Otomasyon istemcileri C++ olarak yazabilir.](../mfc/automation-clients.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC COM](../mfc/mfc-com.md)
