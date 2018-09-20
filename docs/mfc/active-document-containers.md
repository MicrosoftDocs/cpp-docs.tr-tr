---
title: Etkin belge kapsayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f2d8dcc81a8e9843ffa84651a6404ba91c9ef3d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394259"
---
# <a name="active-document-containers"></a>Etkin Belge Kapsayıcıları

Microsoft Office Binder veya Internet Explorer gibi bir etkin belge kapsayıcı birkaç belge (oluşturmanızı ve her biri için birden çok uygulama çerçeveleri kullanın zorlamak yerine tek bir çerçeve içinde farklı uygulama türleri ile çalışmanıza olanak sağlar Belge türü).

MFC içinde etkin belge kapsayıcıları için tam destek sağlar `COleDocObjectItem` sınıfı. MFC Uygulama Sihirbazı'nı seçerek bir etkin belge kapsayıcısı oluşturmak için kullanabileceğiniz **etkin belge kapsayıcı** onay kutusunu **bileşik belge desteği** MFC Uygulama Sihirbazı sayfası. Daha fazla bilgi için [bir etkin belge kapsayıcı uygulaması oluşturma](../mfc/creating-an-active-document-container-application.md).

Etkin belge kapsayıcıları hakkında daha fazla bilgi için bkz:

- [Kapsayıcı gereksinimleri](#container_requirements)

- [Belge Site nesneleri](#document_site_objects)

- [Site nesneleri görüntüle](#view_site_objects)

- [Çerçeve nesnesi](#frame_object)

- [Yardım Menüsü Birleştirme](../mfc/help-menu-merging.md)

- [Program Aracılığıyla Yazdırma](../mfc/programmatic-printing.md)

- [Komut Hedefleri](../mfc/message-handling-and-command-targets.md)

##  <a name="container_requirements"></a> Kapsayıcı gereksinimleri

Etkin belge desteği etkin belge kapsayıcı arabirim uygulamaları çok daha fazlası anlamına gelir: bağımsız bir nesne arabirimleri kullanarak bilgi de gerektirir. Etkin belge uzantıları burada kapsayıcı de bu uzantı arabirimlerini etkin belgelere kendilerini nasıl kullanılacağını bilmek gerekir, aynı geçerlidir.

Etkin belgeler tümleştiren bir etkin belge kapsayıcı gerekir:

- Nesne depolama aracılığıyla işleyebilir olması `IPersistStorage` arabirimi, diğer bir deyişle, sağlamalıdır bir `IStorage` etkin her belge için örneği.

- OLE belgeleri, "site" nesneleri (tek başına belge veya ekleme) araya temel ekleme özelliklerinin desteklenmesi uygulayan `IOleClientSite` ve `IAdviseSink`.

- Katıştırılmış nesneler veya etkin belgeler yerinde etkinleştirme desteği. Kapsayıcının site nesneleri uygulamalıdır `IOleInPlaceSite` ve kapsayıcının çerçeve nesnesi sağlamalısınız `IOleInPlaceFrame`.

- Etkin belgeler uzantıları uygulayarak desteği `IOleDocumentSite` belgeye konuşmaya kapsayıcısı için bir mekanizma sağlamanız. İsteğe bağlı olarak, kapsayıcı etkin belgeyi arabirimleri gerçekleştiren `IOleCommandTarget` ve `IContinueCallback` yazdırma veya kaydetme gibi basit bir komut alması için.

Çerçeve nesnesi, görünüm nesneleri ve kapsayıcı nesnesi isteğe bağlı olarak uygulayabilirsiniz `IOleCommandTarget` bölümünde açıklandığı gibi belirli bir komut gönderme desteklemek için [komut hedefleri](../mfc/message-handling-and-command-targets.md). Görünüm ve kapsayıcı nesneleri ayrıca isteğe bağlı olarak uygulayabilirsiniz `IPrint` ve `IContinueCallback`anlatıldığı gibi program aracılığıyla yazdırma desteği için [programlı yazdırma](../mfc/programmatic-printing.md).

Aşağıdaki şekil, bir kapsayıcı (soldaki), bileşenleri ve etkin belgeyi ve görünümlerini (en sağ) arasındaki kavramsal ilişkiyi gösterir. Etkin belge depolaması ve veri yönetir ve görünümü görüntüler veya isteğe bağlı olarak bu verileri yazdırır. Kalın arabirimleri etkin belgeyi katılım için gerekli olan; Bu kalın ve italik isteğe bağlıdır. Tüm arabirimleri gereklidir.

![Etkin belge kapsayıcı arabirimleri](../mfc/media/vc37gj1.gif "vc37gj1")

Yalnızca tek bir görünümde destekleyen bir belge görünüm ve belge bileşenleri (diğer bir deyişle, kendi ilgili arabirimlere) tek bir somut sınıf uygulayabilirsiniz. Ayrıca, yalnızca tek bir görünümde bir zaman destekleyen bir kapsayıcı sitesi belge ve görünüm siteleri tek bir somut site sınıfına birleştirebilirsiniz. Kapsayıcının çerçeve nesnesi, ancak farklı kalması gereken ve kapsayıcının belge bileşeni yalnızca burada mimarisi eksiksiz bir görünümünü sağlamak için dahil edilir; Etkin belge kapsama mimari tarafından etkilenmez.

##  <a name="document_site_objects"></a> Belge Site nesneleri

Etkin belge kapsama mimaride bir belge sitesinde ek olarak istemci site nesnesi OLE belgelerde aynıdır `IOleDocument` arabirimi:

```cpp
interface IOleDocumentSite : IUnknown
{
    HRESULT ActivateMe(IOleDocumentView *pViewToActivate);
}
```

Belge sitesinde kavramsal olarak bir veya daha fazla "görünümü site" nesneleri için kapsayıcıdır. Her görünüm site nesnesi belgesinin Belge site tarafından yönetilen tek görünüm nesneleri ile ilişkilidir. Kapsayıcı yalnızca belge site başına tek bir görünümde destekliyorsa, ardından, belge ve görünüm siteleri tek bir somut sınıf ile uygulayabilirsiniz.

##  <a name="view_site_objects"></a> Site nesneleri görüntüle

Bir kapsayıcının görünümü site nesnesi, belirli bir belge görünümü görüntüleme alanı yönetir. Standart Destek yanı sıra `IOleInPlaceSite` sitesini görüntüleme ayrıca genel arabirimi uygulayan `IContinueCallback` yazdırma programlı denetim. (View nesnesinin için hiçbir zaman sorgular Not `IContinueCallback` üzerinde gerçekten uygulanabilir için tüm kapsayıcı istediği nesne.)

Birden çok görünüm destekleyen bir kapsayıcı belge sitedeki site nesneleri birden çok görünüm oluşturmak mümkün olması gerekir. Bu her görünüm ayrı etkinleştirme ve devre dışı bırakma Hizmetleri ile sağlanan sağlar `IOleInPlaceSite`.

##  <a name="frame_object"></a> Çerçeve nesnesi

Kapsayıcının çerçeve, çoğunlukla, nesnedir yerinde etkinleştirme OLE belgeleri için diğer bir deyişle kullanılır çerçevenin, menü ve araç çubuğu anlaşma işler. Bu çerçeve nesnesi bir görünüm nesnesi erişimi `IOleInPlaceSite::GetWindowContext`, kapsayıcı nesne (bölmesinde düzeyi araç anlaşma ve kapsanan nesne sabit listesini işleyebilir) bir kapsayıcı belgesi temsil eden erişim de sağlar.

Etkin belge kapsayıcı çerçeve ekleyerek iyileştirebilirsiniz `IOleCommandTarget`. Bu etkin belgenin kullanıcı arabiriminde aynı şekilde bu arabirimi aynı komutları göndermek bir kapsayıcı izin verebilirsiniz kaynaklanan komutları almasına izin verir (gibi **dosya yeni**, **açık**,  **Farklı Kaydet**, **yazdırma**; **Kopya Düzenle**, **Yapıştır**, **geri**ve diğerleri) etkin bir belge için. Daha fazla bilgi için [komut hedefleri](../mfc/message-handling-and-command-targets.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Etkin Belge Kapsaması](../mfc/active-document-containment.md)

