---
title: Birden çok belge türü, görünümler ve çerçeve Windows | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce4caa9b8a8575264563d69f47dbba1dcedb69e5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054117"
---
# <a name="multiple-document-types-views-and-frame-windows"></a>Birden Fazla Belge Türü, Görünüm ve Çerçeve Penceresi

Bir belge, kendi Görünüm ve çerçeve penceresi standart ilişkiyi açıklanan [belge/görünüm oluşturma](../mfc/document-view-creation.md). Birçok uygulama destekleyen tek bir belge türü (ancak büyük olasılıkla bu türdeki birden çok açık belgeler) tek bir görünümde belge başına yalnızca bir çerçeve penceresi ve belge. Ancak, bazı uygulamalar bir veya daha fazla bu varsayılan değerleri değiştirmek gerekebilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Birden çok belge türleri](#_core_multiple_document_types)

- [Birden çok görünüm](#_core_multiple_views)

- [Birden çok çerçeve penceresi](#_core_multiple_frame_windows)

- [Bölümlendirici pencereler](#_core_splitter_windows)

##  <a name="_core_multiple_document_types"></a> Birden çok belge türleri

MFC Uygulama Sihirbazı, bir tek belge sınıfı oluşturur. Ancak, bazı durumlarda, birden fazla belge türü desteği gerekebilir. Örneğin, uygulamanızın çalışma sayfası ve grafik belgeleri gerekebilir. Her bir belge türü kendi belge sınıfı ve belki de kendi görünüm sınıfı tarafından temsil edilir. Kullanıcı dosya yeni komutunun seçtiğinde framework desteklenen belge türlerini listeleyen bir iletişim kutusu görüntüler. Daha sonra kullanıcı türü bir belgeyi oluşturur. Her bir belge türü kendi belge şablonu nesnesi tarafından yönetilir.

Ek belge sınıfları oluşturmak için bkz [sınıf ekleme](../ide/adding-a-class-visual-cpp.md). Seçin [CDocument](../mfc/reference/cdocument-class.md) belge istenen bilgileri sağlayın ve türetilen sınıf türü olarak. Ardından yeni sınıfın veri uygulayın.

Ek belge sınıfınıza hakkında bilmeniz framework izin vermek için ikinci bir çağrı ekleyin [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) uygulama sınıfın içinde [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) geçersiz kılar. Daha fazla bilgi için [belge şablonları](../mfc/document-templates-and-the-document-view-creation-process.md).

##  <a name="_core_multiple_views"></a> Birden çok görünüm

Yalnızca tek bir görünümde birçok belgeler gerektirir, ancak tek bir belgenin birden fazla görünümünü desteklemek mümkündür. Birden çok görünüm uygulamanıza yardımcı olmak için bir belge nesnesi görünümlerini listesini tutar, ekleme ve kaldırma görünümleri için işlevleri sağlar ve kaynakları [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) birden çok görünüm ne zaman bilmeniz izin vermek için üye işlevi Belgenin verilerini değişti.

MFC aynı belgede birden çok görünüm gerektiren üç yaygın kullanıcı arabirimi destekler. Bu model şunlardır:

- Aynı sınıfın her bir ayrı MDI belge çerçevesi penceresinin nesneleri görüntüle.

   Belge üzerinde ikinci bir çerçeve penceresi oluşturma desteği isteyebilirsiniz. Kullanıcı ikinci bir çerçeve aynı belgede bir görünümünü açın ve ardından iki çerçeve belgenin farklı bölümleri aynı anda görüntülemek için bir yeni pencere komutunu seçebilir. Framework ilk çerçeve penceresi ve belgeye eklenen görünüm çoğaltarak Pencere menüsünden MDI uygulamaları için yeni pencere komutunu destekler.

- Aynı belge çerçeve penceresindeki aynı sınıfın nesneleri görüntüle.

   Bölümlendirici pencereler, belgenin birden çok ayrı görünümlere bir tek belge penceresini görüntüleme alanının bölün. Framework aynı görünüm sınıfı birden çok görünüm nesneleri oluşturur. Daha fazla bilgi için [Bölümlendirici Windows](#_core_splitter_windows).

- Tek bir çerçeve penceresinde farklı sınıfların nesneleri görüntüle.

   Bu modelde, ayırıcı penceresi çeşitlemesi birden çok görünüm tek çerçeve penceresi paylaşın. Görünümleri farklı sınıflardan aynı belgeyi görüntülemek için farklı bir yol sağlayarak her görünüm oluşturulur. Örneğin, isteğe bağlı olarak diğer görünümdeki anahat modunda gösterir ancak tek bir görünümde bir sözcük belge normal modda gösterebilir. Bölümlendirici denetimi görünüm göreli boyutlarını ayarlamak kullanıcının sağlar.

Aşağıdaki şekilde bölümlere ayrılmış üç kullanıcı arabirimi model yukarıda gösterilen sırayla a, b ve c gösterir.

![Birden çok&#45;kullanıcı arabirimlerini görüntülemek](../mfc/media/vc37a71.gif "vc37a71") birden çok görünüm kullanıcı arabirimleri

Yeni Pencere komutunu uygulama ve sınıfı sağlayarak bu modeller çerçevesini sağlar [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)bölümünde açıklandığı gibi [Bölümlendirici Windows](#_core_splitter_windows). Bu, başlangıç noktası olarak kullanmak diğer model uygulayabilir. Ayırıcılar, görünümler ve çerçeve pencereleri bakın farklı yapılandırmaları gösteren örnek programlar için [MFC örnekleri](../visual-cpp-samples.md).

Hakkında daha fazla bilgi için `UpdateAllViews`, sınıfına bakın [CView](../mfc/reference/cview-class.md) içinde *MFC başvurusu* ve [Scribble örneğinin](../visual-cpp-samples.md).

##  <a name="_core_multiple_frame_windows"></a> Birden çok çerçeve Windows

İkinci bir çerçeve penceresi aynı belgede oluşturmak için Pencere menüsünden MDI uygulamaları için yeni pencere komutunu kullanabilirsiniz. Daha fazla bilgi için şekilde birden çok görünüm kullanıcı arabirimleri birinci modelin bakın.

##  <a name="_core_splitter_windows"></a> Bölümlendirici Windows

Ayırıcı penceresi, pencere olan veya, iki veya daha fazla kaydırılabilir Bölmelere ayrılmış olabilir. Bölmelerin göreli boyutlarını ayarlamak kullanıcının, bir ayırıcı denetimi (veya "kutusunu bölme") kaydırma çubukları yanındaki pencere çerçevesi sağlar. Her bölmede aynı belgede bir görünümüdür. "Dinamik" Ayırıcılar içinde aynı sınıfı, birden çok görünüm kullanıcı arabirimleri şekil bölümü b'dedir gösterildiği görünümleridir. "Statik" Ayırıcılar farklı sınıflardaki görünümleri olabilir. Her iki tür Bölümlendirici pencereler sınıfı tarafından desteklenen [CSplitterWnd](../mfc/reference/csplitterwnd-class.md).

Dinamik Bölümlendirici pencereler, aynı sınıfın görünümlere sahip bir pencere sağlar, birden fazla bölme bölün ve ardından farklı belge parçalarını görmek için farklı bölmeler gidin izin verin. Kullanıcı ayrıca ek görünümler kaldırmak için pencerenin sayfanın toplamında. Eklenen Bölümlendirici pencereler [Scribble örneğinin](../visual-cpp-samples.md) buna örnek verilebilir. Bu konuda dinamik Bölümlendirici pencereler oluşturmak için yöntem açıklanmaktadır. Dinamik Bölümlendirici pencere birden çok görünüm kullanıcı arabirimleri şekil b bölümünde gösterilir.

Birden çok Bölmelere ayrılmış penceresi her biri farklı bir amaç görünümlerle farklı sınıfların statik Bölümlendirici pencereler başlayın. Örneğin, Visual C++ bit eşlem Düzenleyicisi'nde yan yana iki bölme görüntü penceresini gösterir. Sol bölmede life-sized bir bit eşlem görüntüsünü görüntüler. Sağ bölmede, aynı bit eşlemin yakınlaştırılmış veya büyütülmüş görüntüsünü görüntüler. Bölmeleri "bölmelerin göreli boyutlarını değiştirmek için kullanıcı sürükleyebilirsiniz bir bölme çubuğu tarafından" ayrılır. Statik Bölümlendirici pencere birden çok görünüm kullanıcı arabirimleri şekil bölümü c dilinde gösterilir.

Daha fazla bilgi için bkz. [CSplitterWnd](../mfc/reference/csplitterwnd-class.md) içinde *MFC başvurusu* ve [MFC örnekleri](../visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

