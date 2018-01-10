---
title: "Etkin belge kapsayıcıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 87546f3c02025438b3e60cd2038fdc885dfedf9f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="active-document-containers"></a>Etkin Belge Kapsayıcıları
Microsoft Office Binder veya Internet Explorer gibi bir etkin belge kapsayıcısı birkaç belge (yerine oluşturmak ve her biri için birden çok uygulama çerçeveleri kullanmak için zorlama tek çerçevesinde farklı uygulama türleri ile çalışmanıza olanak sağlar Belge türü).  
  
 MFC etkin belge kapsayıcıları için tam destek sağlar `COleDocObjectItem` sınıfı. MFC Uygulama Sihirbazı'nı seçerek bir etkin belge kapsayıcısı oluşturmak için kullanabileceğiniz **etkin belge kapsayıcısı** onay kutusunu **bileşik belge desteği** MFC Uygulama Sihirbazı sayfası. Daha fazla bilgi için bkz: [bir etkin belge kapsayıcı uygulaması oluşturma](../mfc/creating-an-active-document-container-application.md).  
  
 Etkin belge kapsayıcıları hakkında daha fazla bilgi için bkz:  
  
-   [Kapsayıcı gereksinimleri](#container_requirements)  
  
-   [Belge Site nesneleri](#document_site_objects)  
  
-   [Site nesneleri görüntüle](#view_site_objects)  
  
-   [Çerçeve nesnesi](#frame_object)  
  
-   [Yardım Menüsü Birleştirme](../mfc/help-menu-merging.md)  
  
-   [Program Aracılığıyla Yazdırma](../mfc/programmatic-printing.md)  
  
-   [Komut Hedefleri](../mfc/message-handling-and-command-targets.md)  
  
##  <a name="container_requirements"></a>Kapsayıcı gereksinimleri  
 Etkin belge kapsayıcı etkin belge desteği, çok daha fazlası arabirim uygulamaları olduğu anlamına gelir: de kapsanan bir nesne arabirimleri kullanarak bilgi gerektirir. Etkin belge uzantıları, burada kapsayıcı de bu uzantısı arabirimlerini etkin belgeler üzerinde kendilerini nasıl kullanılacağını bilmeniz gerekir aynı geçerlidir.  
  
 Etkin belgeler tümleşen bir etkin belge kapsayıcısı gerekir:  
  
-   Nesne depolama aracılığıyla işleyebilen olması **IPersistStorage** arabirimi, diğer bir deyişle, onu sağlamalıdır bir `IStorage` her etkin belgeyi örneğine.  
  
-   OLE belgeleri, "site" nesneleri (bir belge veya katıştırma başına) araya temel katıştırma özelliklerini destekleyecek uygulayan **IOleClientSite** ve **IAdviseSink**.  
  
-   Yerinde etkinleştirme katıştırılmış nesneler ya da etkin belgeler destekler. Kapsayıcının site nesneleri uygulamalıdır `IOleInPlaceSite` ve kapsayıcının çerçeve nesnesi sağlamalısınız **IOleInPlaceFrame**.  
  
-   Etkin belgeler uzantıları uygulayarak desteği `IOleDocumentSite` belgeye konuşun kapsayıcıya mekanizması sağlamak için. İsteğe bağlı olarak, kapsayıcı etkin belgeyi arabirimleri uygulayabilir `IOleCommandTarget` ve `IContinueCallback` yazdırma veya kaydetme gibi basit komutları alması.  
  
 Çerçeve nesnesi, görünüm nesneleri ve kapsayıcı nesnesinin isteğe bağlı olarak uygulayabileceğiniz **IOleCommandTarget** anlatıldığı gibi bazı komutlar gönderme desteklemek için [komut hedefleri](../mfc/message-handling-and-command-targets.md). Görünüm ve kapsayıcı nesneleri ayrıca isteğe bağlı olarak uygulayabilirsiniz `IPrint` ve `IContinueCallback`anlatıldığı gibi program aracılığıyla yazdırma desteği için [programlı yazdırma](../mfc/programmatic-printing.md).  
  
 Aşağıdaki şekilde bir kapsayıcı ve bileşenlerinin (soldaki) ve etkin belgeyi ve onun görünümlerinde (sağ) arasındaki kavramsal ilişkiyi gösterir. Etkin belge depolama ve veri yönetir ve görünümü görüntüler veya isteğe bağlı olarak bu verileri yazdırır. Kalın yazı tipiyle etkin belgeyi katılım için gerekli olanlar arabirimlerdir; Bu kalın ve italik isteğe bağlıdır. Diğer tüm arabirimler gereklidir.  
  
 ![Etkin belge kapsayıcısı arabirimleri](../mfc/media/vc37gj1.gif "vc37gj1")  
  
 Yalnızca tek bir görünüm destekleyen bir belge görünüm ve belge bileşenleri (diğer bir deyişle, karşılık gelen arabirimlerini) tek bir somut sınıf uygulayabilirsiniz. Ayrıca, yalnızca bir seferde bir görünümü destekleyen bir kapsayıcı sitesi belge ve görünüm siteleri tek somut site sınıfına birleştirebilirsiniz. Kapsayıcının çerçeve nesnesi, ancak ayrı kalmalı ve kapsayıcının belge bileşeni yalnızca burada mimarisi eksiksiz bir görünümünü sağlamak için eklenir; Etkin belge kapsama mimarisi tarafından etkilenmez.  
  
##  <a name="document_site_objects"></a>Belge Site nesneleri  
 Etkin belge kapsama mimarisinde, bir belge OLE belgeleri istemci site nesnesinde eklenmesi ile aynı sitesidir `IOleDocument` arabirimi:  
  
 `interface IOleDocumentSite : IUnknown`  
  
 `{`  
  
 `HRESULT ActivateMe(IOleDocumentView *pViewToActivate);`  
  
 `}`  
  
 Belge sitesini kavramsal olarak bir veya daha fazla "görünümü site" nesneleri için kapsayıcıdır. Her görünüm site nesnesi belge site tarafından yönetilen belgesinin ayrı görünüm nesneleri ile ilişkilidir. Kapsayıcı yalnızca belge site başına tek bir görünümde destekliyorsa, ardından bu belge sitesini ve tek bir somut sınıf görünümü sitesiyle uygulayabilirsiniz.  
  
##  <a name="view_site_objects"></a>Site nesneleri görüntüle  
 Görüntü alanı bir belgenin belirli bir görünüm için bir kapsayıcının görünümü site nesnesi yönetir. Standart Destek yanı sıra `IOleInPlaceSite` arabirimini uygulayan bir görünüm site ayrıca genellikle `IContinueCallback` programlı yazdırma denetimi için. (Görünüm nesnesi için hiçbir zaman sorgular Not `IContinueCallback` üzerinde gerçekte uygulanabilir şekilde kapsayıcı istediği herhangi bir nesne.)  
  
 Birden çok görünüm destekleyen bir kapsayıcı birden çok görünüm belge sitedeki site nesneleri oluşturmak mümkün olması gerekir. Bu her görünüm ayrı etkinleştirme ve devre dışı bırakma Hizmetleri ile sağlanan sağlar `IOleInPlaceSite`.  
  
##  <a name="frame_object"></a>Çerçeve nesnesi  
 Kapsayıcının çerçeve, çoğunlukla, nesnesidir yerinde etkinleştirme için OLE belgelerde diğer bir deyişle kullanılan aynı çerçeve, menü ve araç çubuğu anlaşma işler. Bir görünüm nesnesi çerçeve nesne üzerinden erişimi **IOleInPlaceSite::GetWindowContext**, (hangi bölmesinde düzeyi araç anlaşmasını işleyecek kapsayıcı belge temsil eden kapsayıcı nesnesinin erişim de sağlar ve içerilen nesne numaralandırma).  
  
 Etkin belge kapsayıcı çerçeve ekleyerek genişletebilirsiniz `IOleCommandTarget`. Bu aynı şekilde bu arabirimi aynı komutları göndermek bir kapsayıcı izin verebilir etkin belgenin kullanıcı arabiriminde kaynaklanan komutları almasına izin verir (gibi **dosya yeni**, **açık**,  **Farklı Kaydet**, **yazdırma**; **Düzenle kopyalama**, **Yapıştır**, **geri**ve diğerleri) etkin bir belge için. Daha fazla bilgi için bkz: [komut hedefleri](../mfc/message-handling-and-command-targets.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin Belge Kapsaması](../mfc/active-document-containment.md)

