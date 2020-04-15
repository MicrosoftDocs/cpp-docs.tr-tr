---
title: Etkin Belge Kapsayıcıları
ms.date: 11/19/2018
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
ms.openlocfilehash: e2005ffed592fa1de278e0f6339d94687a20fd06
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377393"
---
# <a name="active-document-containers"></a>Etkin Belge Kapsayıcıları

Microsoft Office Bağlayıcısı veya Internet Explorer gibi etkin bir belge kapsayıcısı, tek bir çerçeve içinde farklı uygulama türlerine ait birkaç belgeyle çalışmanıza olanak tanır (her belge türü için birden çok uygulama çerçevesi oluşturmanıza ve kullanmanıza zorlamak yerine).

MFC, sınıftaki `COleDocObjectItem` etkin belge kapsayıcıları için tam destek sağlar. MFC Uygulama Sihirbazı'nın **Bileşik Belge Destek** sayfasında **etkin belge kapsayıcısı** onay kutusunu seçerek etkin bir belge kapsayıcısı oluşturmak için MFC Uygulama Sihirbazı'nı kullanabilirsiniz. Daha fazla bilgi için [bkz.](../mfc/creating-an-active-document-container-application.md)

Etkin belge kapsayıcıları hakkında daha fazla bilgi için bkz:

- [Konteyner Gereksinimleri](#container_requirements)

- [Belge Site Nesneleri](#document_site_objects)

- [Site Nesnelerini Görüntüle](#view_site_objects)

- [Çerçeve Nesnesi](#frame_object)

- [Yardım Menüsü Birleştirme](../mfc/help-menu-merging.md)

- [Program Aracılığıyla Yazdırma](../mfc/programmatic-printing.md)

- [Komut Hedefleri](../mfc/message-handling-and-command-targets.md)

## <a name="container-requirements"></a><a name="container_requirements"></a>Konteyner Gereksinimleri

Etkin bir belge kapsayıcısındaki etkin belge desteği, arabirim uygulamalarından daha fazlasını ima eder: aynı zamanda içerdiği bir nesnenin arabirimlerini kullanma bilgisi gerektirir. Aynı durum, kapsayıcının etkin belgelerdeki bu uzantı arabirimlerinin nasıl kullanılacağını da bilmesi gereken etkin belge uzantıları için de geçerlidir.

Etkin belgeleri tümleştiren etkin bir belge kapsayıcısı şunları yapmalıdır:

- `IPersistStorage` Arabirim üzerinden nesne depolama işleme yeteneğine sahip olmak, `IStorage` yani, her etkin belge için bir örnek sağlamalıdır.

- OLE belgelerinin temel katıştırma özelliklerini destekleyerek, "site" nesnelerini (belge `IOleClientSite` başına `IAdviseSink`bir veya katıştırma) uygulayıp.

- Katıştırılmış nesnelerin veya etkin belgelerin yerinde etkinleştirmesini destekleyin. Kapsayıcının site nesneleri uygulamalı `IOleInPlaceSite` ve kapsayıcının çerçeve nesnesi sağlamalıdır. `IOleInPlaceFrame`

- Kapsayıcının belgeyle konuşması için `IOleDocumentSite` mekanizmayı sağlamak için etkin belgelerin uzantılarını destekleyin. İsteğe bağlı olarak, kapsayıcı etkin `IOleCommandTarget` belge `IContinueCallback` arabirimlerini uygulayabilir ve yazdırma veya kaydetme gibi basit komutları alabilir.

Çerçeve nesnesi, görünüm nesneleri ve kapsayıcı nesnesi, Komut `IOleCommandTarget` [Hedefleri'nde](../mfc/message-handling-and-command-targets.md)belirtildiği gibi belirli komutların gönderilmesini desteklemek için isteğe bağlı olarak uygulayabilirsiniz. Görünüm ve kapsayıcı nesneleri de `IPrint` isteğe bağlı olarak uygulayabilirsiniz ve `IContinueCallback`programlı yazdırma, [Programlı Yazdırma'da](../mfc/programmatic-printing.md)anlatıldığı gibi programız yazdırmayı desteklemek için.

Aşağıdaki şekil, bir kapsayıcı ve bileşenleri (solda) ve etkin belge ve görünümleri (sağda) arasındaki kavramsal ilişkileri gösterir. Etkin belge depolama yı ve verileri yönetir ve görünüm bu verileri görüntüler veya isteğe bağlı olarak yazdırır. Kalın arayüzler aktif belge katılımı için gerekli olanlardır; bu kalın ve italik isteğe bağlıdır. Diğer tüm arabirimler gereklidir.

![Etkin belge kapsayıcı arabirimleri](../mfc/media/vc37gj1.gif "Etkin belge kapsayıcı arabirimleri")

Yalnızca tek bir görünümü destekleyen bir belge, hem görünüm hem de belge bileşenlerini (diğer bir şekilde karşılık gelen arabirimleri) tek bir somut sınıfa uygulayabilir. Buna ek olarak, aynı anda yalnızca bir görünümü destekleyen bir kapsayıcı sitesi, belge sitesini ve görünüm sitesini tek bir beton site sınıfında birleştirebilir. Ancak, kapsayıcının çerçeve nesnesi farklı kalmalıdır ve kapsayıcının belge bileşeni yalnızca mimarinin tam bir resmini vermek için buraya eklenmiştir; etkin belge çevreleme mimarisinden etkilenmez.

## <a name="document-site-objects"></a><a name="document_site_objects"></a>Belge Site Nesneleri

Etkin belge çevreleme mimarisinde, bir belge sitesi, `IOleDocument` arabirimin eklenmesiyle OLE Documents'daki istemci site nesnesiyle aynıdır:

```cpp
interface IOleDocumentSite : IUnknown
{
    HRESULT ActivateMe(IOleDocumentView *pViewToActivate);
}
```

Belge sitesi kavramsal olarak bir veya daha fazla "site" nesnesi için kapsayıcıdır. Her görüntüleme sitesi nesnesi, belge sitesi tarafından yönetilen belgenin tek tek görünüm nesneleri ile ilişkilidir. Kapsayıcı yalnızca belge sitesi başına tek bir görünümü destekliyorsa, belge sitesini ve görüntüleme sitesini tek bir beton sınıfıyla uygulayabilir.

## <a name="view-site-objects"></a><a name="view_site_objects"></a>Site Nesnelerini Görüntüle

Kapsayıcının görünüm sitesi nesnesi, belgenin belirli bir görünümü için görüntü alanını yönetir. Standart `IOleInPlaceSite` arabirimi desteklemenin yanı sıra, bir görünüm `IContinueCallback` sitesi genellikle programlı yazdırma denetimi için de uygular. (Görünüm nesnesinin hiçbir zaman `IContinueCallback` sorgulanamayacağını, bu nedenle kapsayıcının istediği herhangi bir nesneüzerinde uygulanabileceğini unutmayın.)

Birden çok görüntülemeyi destekleyen bir kapsayıcı, belge sitesi içinde birden çok görüntüleme site nesnesi oluşturabilmelidir. Bu, her görünümde, `IOleInPlaceSite`'den sağlanan ayrı etkinleştirme ve devre dışı bırakma hizmetleri sağlar.

## <a name="frame-object"></a><a name="frame_object"></a>Çerçeve Nesnesi

Kapsayıcının çerçeve nesnesi, çoğunlukla, OLE Documents'da yerinde etkinleştirme için kullanılan çerçevenin, yani menü ve araç çubuğu anlaşmasını işleyen çerçevedir. Görünüm `IOleInPlaceSite::GetWindowContext`nesnesi, kapsayıcı belgesini temsil eden kapsayıcı nesnesine (bölme düzeyinde araç çubuğu anlaşmasını işleyebilir ve nesne numaralandırması içerebilen) bu çerçeve nesnesine de erişebilir.

Etkin bir belge kapsayıcısı ekleyerek `IOleCommandTarget`çerçeveyi artırabilir. Bu, etkin belgenin kullanıcı arabiriminde bulunan komutları, bu arabirimin bir kapsayıcının aynı komutları göndermesine izin verdiği şekilde almasını sağlar **(Dosya Yeni,** **Aç,** **Kaydet**, **Yazdır**; **Kopyala,** **Yapıştır,** **Geri Al**, ve diğerleri) etkin bir belgeye kopyala. Daha fazla bilgi için Bkz. [Komut Hedefleri.](../mfc/message-handling-and-command-targets.md)

## <a name="see-also"></a>Ayrıca bkz.

[Etkin Belge İçerme](../mfc/active-document-containment.md)
