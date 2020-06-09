---
title: Etkin Belge Kapsayıcıları
ms.date: 11/19/2018
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
ms.openlocfilehash: dc7017a205bedd716e5c87aa23ac96b257af2e16
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626028"
---
# <a name="active-document-containers"></a>Etkin Belge Kapsayıcıları

Microsoft Office Ciltçi veya Internet Explorer gibi etkin bir belge kapsayıcısı, tek bir çerçeve içinde farklı uygulama türlerinin çeşitli belgeleriyle çalışmanıza olanak sağlar (her belge türü için birden çok uygulama çerçevesi oluşturup kullanmanıza zorlamak yerine).

MFC, sınıfında etkin belge kapsayıcıları için tam destek sağlar `COleDocObjectItem` . MFC Uygulama Sihirbazı 'nın **Birleşik belge desteği** sayfasında **etkin belge kapsayıcısı** onay kutusunu seçerek etkin bir belge kapsayıcısı oluşturmak için MFC Uygulama Sihirbazı ' nı kullanabilirsiniz. Daha fazla bilgi için bkz. [etkin bir belge kapsayıcı uygulaması oluşturma](creating-an-active-document-container-application.md).

Etkin belge kapsayıcıları hakkında daha fazla bilgi için bkz.:

- [Kapsayıcı gereksinimleri](#container_requirements)

- [Belge site nesneleri](#document_site_objects)

- [Site nesnelerini görüntüle](#view_site_objects)

- [Çerçeve nesnesi](#frame_object)

- [Yardım Menüsü Birleştirme](help-menu-merging.md)

- [Program Aracılığıyla Yazdırma](programmatic-printing.md)

- [Komut hedefleri](message-handling-and-command-targets.md)

## <a name="container-requirements"></a><a name="container_requirements"></a>Kapsayıcı gereksinimleri

Etkin belge kapsayıcısında etkin belge desteği, yalnızca arabirim uygulamalarından daha fazlasını gösterir: Ayrıca, kapsanan bir nesnenin arabirimlerini kullanma bilgisi de gerektirir. Aynı zamanda kapsayıcı, etkin belge uzantıları için de geçerlidir. burada kapsayıcı, bu uzantı arabirimlerini etkin belgelerde nasıl kullanacağınızı da bilmelidir.

Etkin belgeleri tümleştiren etkin bir belge kapsayıcısı şunları içermelidir:

- Arabirim aracılığıyla nesne depolamayı işleyebilme `IPersistStorage` , diğer bir deyişle, `IStorage` her etkin belgeye bir örnek sağlaması gerekir.

- Ve ' i uygulayan OLE belgelerinin temel ekleme özelliklerini, tasarımda "site" nesnelerini (belge başına bir tane veya katıştırma) `IOleClientSite` destekler `IAdviseSink` .

- Katıştırılmış nesnelerin veya etkin belgelerin yerinde etkinleştirilmesini destekler. Kapsayıcının site nesnelerinin uygulanması `IOleInPlaceSite` ve kapsayıcının çerçeve nesnesinin sağlaması gerekir `IOleInPlaceFrame` .

- `IOleDocumentSite`Kapsayıcının belgeyle iletişim kurmasına yönelik mekanizmayı sağlamak üzere uygulayarak etkin belgelerin uzantılarını destekleme. İsteğe bağlı olarak kapsayıcı, etkin belge arabirimlerini uygulayabilir `IOleCommandTarget` ve `IContinueCallback` yazdırma ya da kaydetme gibi basit komutları alabilir.

Çerçeve nesnesi, görüntüleme nesneleri ve kapsayıcı nesnesi, `IOleCommandTarget` [komut hedeflerinde](message-handling-and-command-targets.md)anlatıldığı gibi belirli komutların dağıtım desteğini desteklemek için isteğe bağlı olarak uygulanabilir. Görüntüleme ve kapsayıcı nesneleri, `IPrint` `IContinueCallback` [programlı](programmatic-printing.md)yazdırma bölümünde anlatıldığı şekilde, programlama yoluyla yazdırmayı desteklemek için de isteğe bağlı olarak ve uygulayabilir.

Aşağıdaki şekilde, bir kapsayıcı ve bileşenleri (solda) ve etkin belge ve görünümleri arasındaki kavramsal ilişkiler (sağda) gösterilmektedir. Etkin belge depolama ve verileri yönetir ve görünüm bu verileri görüntüler ya da isteğe bağlı olarak yazdırır. Kalın olmayan arabirimler, etkin belge katılımı için gerekli olanlardır; kalın ve italik isteğe bağlıdır. Diğer tüm arabirimler gereklidir.

![Etkin belge kapsayıcısı arabirimleri](../mfc/media/vc37gj1.gif "Etkin belge kapsayıcısı arabirimleri")

Yalnızca tek bir görünümü destekleyen bir belge, hem görünüm hem de belge bileşenlerini (diğer bir deyişle, bunlara karşılık gelen arabirimleri) tek bir somut sınıfta uygulayabilir. Ayrıca, aynı anda yalnızca bir görünümü destekleyen bir kapsayıcı sitesi belge sitesini ve Görünüm sitesini tek bir somut site sınıfında birleştirebilir. Ancak kapsayıcının çerçeve nesnesi ayrı kalmalıdır ve kapsayıcının belge bileşeni, mimarinin tamamen bir resmini sağlamak için yalnızca buraya eklenir; etkin belge kapsama mimarisinden etkilenmez.

## <a name="document-site-objects"></a><a name="document_site_objects"></a>Belge site nesneleri

Etkin belge kapsama mimarisinde, bir belge sitesi, arabirimi ek olarak OLE belgelerindeki istemci sitesi nesnesiyle aynıdır `IOleDocument` :

```cpp
interface IOleDocumentSite : IUnknown
{
    HRESULT ActivateMe(IOleDocumentView *pViewToActivate);
}
```

Belge sitesi, bir veya daha fazla "görünüm sitesi" nesnesi için kavramsal olarak kapsayıcıdır. Her görünüm sitesi nesnesi, belge sitesi tarafından yönetilen belgenin ayrı görünüm nesneleriyle ilişkilendirilir. Kapsayıcı her belge sitesi için yalnızca tek bir görünümü destekliyorsa, belge sitesini ve Görünüm sitesini tek bir somut sınıfla uygulayabilir.

## <a name="view-site-objects"></a><a name="view_site_objects"></a>Site nesnelerini görüntüle

Kapsayıcının Görünüm site nesnesi, bir belgenin belirli bir görünümü için görüntüleme alanını yönetir. Standart arabirimi desteklemeye ek olarak `IOleInPlaceSite` , bir görünüm sitesi de genellikle `IContinueCallback` programlı yazdırma denetimi için de uygulanır. (Görünüm nesnesinin, `IContinueCallback` kapsayıcının istediği herhangi bir nesne üzerine gerçekten uygulanabilmesi için hiçbir şekilde sorgu olmadığını unutmayın.)

Birden çok görünümü destekleyen bir kapsayıcının belge sitesinde birden çok görünüm site nesnesi oluşturabiliyor olması gerekir. Bu, her bir görünümü ile sağlandığı şekilde ayrı etkinleştirme ve devre dışı bırakma hizmetleriyle sağlar `IOleInPlaceSite` .

## <a name="frame-object"></a><a name="frame_object"></a>Çerçeve nesnesi

Kapsayıcının çerçeve nesnesi, çoğu bölüm için, OLE belgelerinde yerinde etkinleştirme için kullanılan çerçeve, diğer bir deyişle, menü ve araç çubuğu anlaşmasını işleyen bir çerçevedir. Bir görünüm nesnesi, bu çerçeve nesnesine erişimi vardır ve `IOleInPlaceSite::GetWindowContext` kapsayıcı belgeyi temsil eden kapsayıcı nesnesine erişim sağlar (Bu, bölme düzeyi araç çubuğu anlaşmasını işleyebilir ve nesne numaralandırması dahil olabilir).

Etkin bir belge kapsayıcısı ekleyerek çerçeveyi artırabilir `IOleCommandTarget` . Bu, bu arabirimin aynı komutları (örneğin, **Yeni**, **açma**, **farklı kaydet**, **Yazdır**gibi) gönderebilmesi için etkin belgenin kullanıcı arabiriminden kaynaklanan komutları almasına izin verir. **Kopyalamayı**, **yapıştırmayı**, **geri al**ve diğerlerini) etkin bir belgeye düzenleyin. Daha fazla bilgi için bkz. [komut hedefleri](message-handling-and-command-targets.md).

## <a name="see-also"></a>Ayrıca bkz.

[Etkin belge kapsama](active-document-containment.md)
