---
title: "Birden çok belge türü, görünümler ve çerçeve pencereleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- static splitter windows [MFC]
- multiple views [MFC]
- multiple document types [MFC]
- multiple views [MFC], frame windows
- document classes [MFC], multiple
- documents [MFC], multiple types of
- splitter windows [MFC], dynamic
- dynamic splitter windows [MFC]
- windows [MFC], dynamic splitter
- windows [MFC], static splitter
- multiple frame windows [MFC]
- splitter windows [MFC], static
ms.assetid: c6b9e4e0-7c9c-45f1-a804-aeac39c9a128
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ab8bff6484f81c482ddd8629ff33772fab1aeba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multiple-document-types-views-and-frame-windows"></a>Birden Fazla Belge Türü, Görünüm ve Çerçeve Penceresi
Bir belge, kendi Görünüm ve çerçeve penceresi standart ilişkiyi açıklanan [belge/görünüm oluşturma](../mfc/document-view-creation.md). Birçok uygulama destekleyen tek bir belge türü (ancak büyük olasılıkla bu türdeki birden çok açık belgeler) tek bir görünümde belge ve belge başına yalnızca bir çerçeve penceresi. Ancak, bazı uygulamaları bir veya daha fazla bu Varsayılanları değiştirmeniz gerekebilir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Birden çok belge türü](#_core_multiple_document_types)  
  
-   [Birden çok görünüm](#_core_multiple_views)  
  
-   [Birden çok çerçeve pencereleri](#_core_multiple_frame_windows)  
  
-   [Bölümlendirici pencereler](#_core_splitter_windows)  
  
##  <a name="_core_multiple_document_types"></a>Birden çok belge türü  
 MFC Uygulama Sihirbazı'nı tek belge sınıfı sizin için oluşturur. Ancak, bazı durumlarda, birden fazla belge türü destek gerekebilir. Örneğin, uygulamanızın çalışma sayfalarını ve grafik belgeleri gerekebilir. Her bir belge türü, kendi belge sınıfı ve büyük olasılıkla da kendi görünüm sınıfı tarafından temsil edilir. Kullanıcı dosya yeni komutu seçtiğinde framework desteklenen belge türleri listeleyen bir iletişim kutusu görüntüler. Ardından kullanıcı türü bir belge oluşturur. Her bir belge türü kendi belge şablonu nesnesi tarafından yönetilir.  
  
 Ek belge sınıfları oluşturmak için bkz: [sınıf ekleme](../ide/adding-a-class-visual-cpp.md). Seçin [CDocument](../mfc/reference/cdocument-class.md) türetmek ve istenen belge bilgileri sağlamak için bu sınıf türü olarak. Ardından yeni sınıfın veri uygulayın.  
  
 Ek belge sınıfı hakkında bilmeniz framework izin vermek için ikinci bir çağrı ekleyin [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) uygulama sınıfınızın içinde [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) geçersiz kılar. Daha fazla bilgi için bkz: [belge şablonları](../mfc/document-templates-and-the-document-view-creation-process.md).  
  
##  <a name="_core_multiple_views"></a>Birden çok görünüm  
 Birçok belgeleri yalnızca tek bir görünüm gerektirir, ancak tek bir belgenin birden fazla görünümünü desteklemek mümkündür. Birden çok görünüm uygulamanıza yardımcı olmak üzere bir belge nesnesi görünümlerini listesini tutar, ekleme ve kaldırma görünümleri için üye işlevleri sağlar ve kaynakları [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) birden çok görünüm ne zaman bilmek izin vermek için üye işlevi Belgenin veriler değişti.  
  
 MFC aynı belge üzerinde birden çok görünüm gerektiren üç ortak kullanıcı arabirimini destekler. Bu model şunlardır:  
  
-   Görünüm nesneleri aynı sınıfın her ayrı bir pencerede MDI belge çerçeve.  
  
     Bir belge üzerinde ikinci bir çerçeve penceresi oluşturma desteği isteyebilirsiniz. Kullanıcı, ikinci bir çerçeve aynı belge bir görünümünü açın ve belgenin farklı bölümlerini aynı anda görüntülemek için iki çerçeve kullanmak için yeni pencere komutu seçebilir. Framework belgeye bağlı Görünüm ve ilk çerçeve penceresi çoğaltarak MDI uygulamaları için Pencere menüsünden Yeni Pencere komutu destekler.  
  
-   Görünüm nesneleri aynı belge çerçeve penceresi aynı sınıfta.  
  
     Bölümlendirici pencereler tek belge penceresi görünümü alan birden çok ayrı belge görünümlere bölün. Framework aynı görünüm sınıfından birden çok görünüm nesneleri oluşturur. Daha fazla bilgi için bkz: [Bölümlendirici pencereler](#_core_splitter_windows).  
  
-   Tek bir çerçeve penceresinde farklı sınıfların nesnelerini görüntüle.  
  
     Bu model, bölümlendirici pencere çeşitlemesi birden çok görünüm tek çerçeve penceresi paylaşır. Görünümleri farklı sınıflardan aynı belgeyi görüntülemek için farklı bir yol sağlayarak her görünüm oluşturulur. Örneğin, isteğe bağlı olarak diğer görünüm anahat modunda gösterir ancak bir görünüm normal modda bir sözcük belge gösterebilir. Bölümlendirici denetimi görünümleri göreli boyutunu Ayarla olanak tanır.  
  
 Aşağıdaki şekil parçalara bölünür yukarıda gösterilen sırada üç kullanıcı arabirimi modeli a, b ve c gösterir.  
  
 ![Birden çok &#45; görünüm kullanıcı arabirimleri](../mfc/media/vc37a71.gif "vc37a71")  
Birden çok görünüm kullanıcı arabirimleri  
  
 Yeni Pencere komutu uygulayarak ve sınıf sağlayarak bu modeller çerçevesi sağlar [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)de anlatıldığı gibi [Bölümlendirici pencereler](#_core_splitter_windows). Bu, başlangıç noktası olarak kullanarak başka modellerinin uygulayabilirsiniz. Görünümler ve çerçeve pencereleri ayırıcılar, bkz: farklı yapılandırmaları gösteren örnek programlar için [MFC örnekleri](../visual-cpp-samples.md).  
  
 Hakkında daha fazla bilgi için `UpdateAllViews`, sınıfına bakın [CView](../mfc/reference/cview-class.md) içinde *MFC başvurusu* ve [karalama örnek](../visual-cpp-samples.md).  
  
##  <a name="_core_multiple_frame_windows"></a>Birden çok çerçeve pencereleri  
 İkinci bir çerçeve penceresi aynı belgeyi oluşturmak için Pencere menüsü MDI uygulamaları için yeni bir pencere komutunu kullanabilirsiniz. Daha fazla bilgi için ilk model birden çok görünüm kullanıcı arabirimleri şekil içinde bakın.  
  
##  <a name="_core_splitter_windows"></a>Bölümlendirici pencereler  
 Bölümlendirici pencere penceresi olduğu veya, iki veya daha fazla kaydırılabilir Bölmelere ayrılmış olabilir. Bir Bölümlendirici denetimi (veya "kutusunu bölme") kaydırma çubuklarını yanındaki pencere çerçevesi bölmelerin göreli boyutunu ayarlamak kullanıcının sağlar. Her bölme aynı belge üzerinde görülmektedir. "Dinamik" Ayırıcılar içinde aynı sınıfının birden çok görünüm kullanıcı arabirimleri şekil bölümü b'de gösterildiği gibi görünümlerdir. "Statik" Ayırıcılar içinde görünümleri farklı sınıflardaki olabilir. Bölümlendirici pencereler her iki tür sınıfı tarafından desteklenen [CSplitterWnd](../mfc/reference/csplitterwnd-class.md).  
  
 Aynı sınıfın görünümlerle dinamik Bölümlendirici pencereler adresindeki birden çok bölmesi bir pencere bölün ve belgenin farklı kısımlarını görmek için farklı bölmeleri kaydırma izin verin. Kullanıcı ayrıca ek görünümler kaldırmak için penceresini bölünmesi. Eklenen Bölümlendirici pencereler [karalama örnek](../visual-cpp-samples.md) bir örnektir. Bu konuda, dinamik Bölümlendirici pencereler oluşturma için teknik açıklanmaktadır. Dinamik Bölümlendirici pencere birden çok görünüm kullanıcı arabirimleri şekil b bölümünde gösterilir.  
  
 Farklı sınıfların görünümlerle statik Bölümlendirici pencereler birden çok Bölmelere ayrılmış penceresi her farklı bir amaç ile başlayın. Örneğin, Visual C++ bit eşlem Düzenleyicisi'nde yan yana iki bölme görüntü penceresini gösterir. Sol bölmede life-sized bir bit eşlem görüntüsünü görüntüler. Sağ bölmede aynı bit eşlem yakınlaştırılmış veya büyütülmüş görüntüsü görüntülenir. Bölmeleri "kullanıcı bölmelerin göreli boyutunu değiştirmek için sürükleyebilirsiniz bir ayırıcı çubukla" ayrılır. Statik Bölümlendirici pencere birden çok görünüm kullanıcı arabirimleri şekil bölümü C'de gösterilir.  
  
 Daha fazla bilgi için bkz [CSplitterWnd](../mfc/reference/csplitterwnd-class.md) içinde *MFC başvurusu* ve [MFC örnekleri](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

