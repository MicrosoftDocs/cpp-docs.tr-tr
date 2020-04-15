---
title: Birden Fazla Belge Türü, Görünüm ve Çerçeve Penceresi
ms.date: 11/19/2018
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
ms.openlocfilehash: 5d8cec0a4ba1580e7ac5fb0e3b81052de08223fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370715"
---
# <a name="multiple-document-types-views-and-frame-windows"></a>Birden Fazla Belge Türü, Görünüm ve Çerçeve Penceresi

Belge, görünümü ve çerçeve penceresi arasındaki standart ilişki [Belge/Görünüm Oluşturma'da](../mfc/document-view-creation.md)açıklanmıştır. Birçok uygulama, belgede tek bir görünüm ve belge başına yalnızca bir çerçeve penceresiyle tek bir belge türünü (ancak bu türdeki büyük olasılıkla birden çok açık belgeyi) destekler. Ancak bazı uygulamaların bu varsayılanlardan birini veya daha fazlasını değiştirmesi gerekebilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Birden çok belge türü](#_core_multiple_document_types)

- [Birden çok görüntüleme](#_core_multiple_views)

- [Birden çok çerçeve penceresi](#_core_multiple_frame_windows)

- [Ayırıcı pencereler](#_core_splitter_windows)

## <a name="multiple-document-types"></a><a name="_core_multiple_document_types"></a>Birden Çok Belge Türleri

MFC Uygulama Sihirbazı sizin için tek bir belge sınıfı oluşturur. Ancak bazı durumlarda, birden fazla belge türünü desteklemeniz gerekebilir. Örneğin, uygulamanızın çalışma sayfası ve grafik belgelerine ihtiyacı olabilir. Her belge türü kendi belge sınıfı ve büyük olasılıkla kendi görünüm sınıfı tarafından da temsil edilir. Kullanıcı Yeni Dosya komutunu seçtiğinde, çerçeve desteklenen belge türlerini listeleyen bir iletişim kutusu görüntüler. Daha sonra, kullanıcının seçtiği türden bir belge oluşturur. Her belge türü kendi belge şablonu nesnesi tarafından yönetilir.

Ek belge sınıfları oluşturmak için [bkz.](../ide/adding-a-class-visual-cpp.md) İstenen belge bilgilerini almak ve sağlamak için Sınıf Türü olarak [CDocument'i](../mfc/reference/cdocument-class.md) seçin. Ardından yeni sınıfın verilerini uygulayın.

Çerçeveye ek belge sınıfınızı bildirmek için, uygulama sınıfınızın [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) geçersiz kılınmasına [AddDocTemplate'e](../mfc/reference/cwinapp-class.md#adddoctemplate) ikinci bir çağrı eklemeniz gerekir. Daha fazla bilgi için [Belge Şablonları'na](../mfc/document-templates-and-the-document-view-creation-process.md)bakın.

## <a name="multiple-views"></a><a name="_core_multiple_views"></a>Birden Çok Görünüm

Birçok belge yalnızca tek bir görünüm gerektirir, ancak tek bir belgenin birden fazla görünümünü desteklemek mümkündür. Birden çok görünüm uygulamanıza yardımcı olmak için, bir belge nesnesi görünümlerinin bir listesini tutar, görünüm eklemek ve kaldırmak için üye işlevler sağlar ve belgenin verilerinin ne zaman değiştiğini birden çok görünüme bildirmek için [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) üye işlevini sağlar.

MFC, aynı belgede birden çok görünüm gerektiren üç ortak kullanıcı arabirimini destekler. Bu modeller şunlardır:

- Her biri ayrı bir MDI belge çerçevesi penceresinde aynı sınıfın nesnelerini görüntüleyin.

   Belgede ikinci bir çerçeve penceresi oluşturmayı desteklemek isteyebilirsiniz. Kullanıcı, aynı belgenin görünümüyle ikinci bir çerçeveyi açmak için Yeni Pencere komutunu seçebilir ve belgenin farklı bölümlerini aynı anda görüntülemek için iki çerçeveyi kullanabilir. Çerçeve, belgeye eklenen ilk çerçeve penceresini ve görünümü çoğaltarak MDI uygulamaları için Pencere menüsündeki Yeni Pencere komutunu destekler.

- Aynı belge çerçevesi penceresinde aynı sınıfın nesnelerini görüntüleyin.

   Bölme pencereleri, tek bir belge penceresinin görünüm alanını belgenin birden çok ayrı görünümüne böler. Çerçeve, aynı görünüm sınıfından birden çok görünüm nesnesi oluşturur. Daha fazla bilgi için Bkz. [Splitter Windows.](#_core_splitter_windows)

- Farklı sınıfların nesnelerini tek bir çerçeve penceresinde görüntüleyin.

   Bu modelde, bölücü penceresinin bir varyasyonu, birden çok görünüm tek bir çerçeve penceresi paylaşır. Görünümler, her görünüm aynı belgeyi görüntülemek için farklı bir yol sağlayan farklı sınıflardan oluşturulur. Örneğin, bir görünüm bir sözcük işleme belgesini normal modda, diğer görünüm ise anahat modunda gösterebilir. Ayırıcı denetimi, kullanıcının görünümlerin göreli boyutlarını ayarlamasına olanak tanır.

A, b ve c parçalarına bölünmüş aşağıdaki şekil, yukarıda sunulan sırada üç kullanıcı arabirimi modelini gösterir.

![Birden çok&#45;görüntüleme kullanıcı arabirimleri](../mfc/media/vc37a71.gif "Birden çok&#45;görüntüleme kullanıcı arabirimleri") <br/>
Çoklu Görünüm Kullanıcı Arabirimleri

Çerçeve Yeni Pencere komutunu uygulayarak ve sınıf [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)sağlayarak bu modelleri sağlar , [Splitter Windows'da](#_core_splitter_windows)tartışılan gibi . Bunları başlangıç noktanız olarak kullanarak diğer modelleri uygulayabilirsiniz. Farklı görünüm, çerçeve pencereleri ve ayırıcıyapılandırmalarını gösteren örnek programlar için [Bkz. MFC Örnekleri.](../overview/visual-cpp-samples.md#mfc-samples)

Hakkında `UpdateAllViews`daha fazla bilgi için *MFC Başvurusu* ve [Karalama örneğinde](../overview/visual-cpp-samples.md) [CView](../mfc/reference/cview-class.md) sınıfına bakın.

## <a name="multiple-frame-windows"></a><a name="_core_multiple_frame_windows"></a>Çoklu Çerçeve Pencereleri

Aynı belgede ikinci bir çerçeve penceresi oluşturmak için MDI uygulamaları için Pencere menüsünde Yeni Pencere komutunu kullanabilirsiniz. Daha fazla bilgi için, birden çok görünümkullanıcı arabirimlerindeki ilk modele bakın.

## <a name="splitter-windows"></a><a name="_core_splitter_windows"></a>Bölme Windows

Ayırıcı penceresinde, pencere iki veya daha fazla kaydırılabilir bölmeye bölünmüştür veya olabilir. Kaydırma çubuklarının yanındaki pencere çerçevesindeki ayırıcı denetimi (veya "bölme kutusu"), kullanıcının bölmelerin göreli boyutlarını ayarlamasına olanak tanır. Her bölme aynı belgeüzerinde bir görünümdür. "Dinamik" ayırıcılarda, görünümler, birden çok görünüm kullanıcı arabirimlerinin b bölümünde gösterildiği gibi aynı sınıftadır. "Statik" ayırıcılarda görünümler farklı sınıflardan olabilir. Her iki türsplitter pencereler [sınıf CSplitterWnd](../mfc/reference/csplitterwnd-class.md)tarafından desteklenir.

Aynı sınıfın görünümlerine sahip dinamik ayırıcı pencereleri, kullanıcının pencereyi olduğu zaman birden çok bölmeye bölmesine ve belgenin farklı bölümlerini görmek için farklı bölmeleri kaydırmasına olanak sağlar. Kullanıcı, ek görünümleri kaldırmak için pencereyi de kaldırabilir. [Karalama örneğine](../overview/visual-cpp-samples.md) eklenen ayırıcı pencereleri buna bir örnektir. Bu konu, dinamik ayırıcı pencereler oluşturma tekniğini açıklar. Dinamik bir ayırıcı penceresi, birden çok görünümkullanıcı arabirimlerinin b bölümünde gösterilir.

Statik ayırıcı pencereler, farklı sınıfların görünümleri ile, pencere birden çok bölmeye bölünmüş, her biri farklı bir amaç ile başlar. Örneğin, Visual C++ bitmap düzenleyicisinde görüntü penceresi iki bölmeyi yan yana gösterir. Sol bölme, bit eşlemin gerçek boyutlu bir görüntüsünü görüntüler. Sağ bölme, aynı bit eşlenin yakınlaştırılmış veya büyütülmüş bir görüntüsünü görüntüler. Bölmeler, kullanıcının bölmelerin göreli boyutlarını değiştirmek için sürükleyebileceği bir "ayırıcı çubuğu" ile ayrılır. Statik ayırıcı penceresi, birden çok görünümkullanıcı arabirimlerinin c bölümünde gösterilir.

Daha fazla bilgi için *MFC Başvurusu* ve [MFC Örnekleri'nde](../overview/visual-cpp-samples.md#mfc-samples) [CSplitterWnd](../mfc/reference/csplitterwnd-class.md) sınıfına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Belge/Görünüm Mimarisi](../mfc/document-view-architecture.md)
