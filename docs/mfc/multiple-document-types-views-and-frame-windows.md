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
ms.openlocfilehash: 873903aadc1596fbc56f9a0b0b98dbc5a948113d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619961"
---
# <a name="multiple-document-types-views-and-frame-windows"></a>Birden Fazla Belge Türü, Görünüm ve Çerçeve Penceresi

Bir belge, görünümü ve çerçeve penceresi arasındaki standart ilişki [belge/görünüm oluşturma](document-view-creation.md)bölümünde açıklanmaktadır. Birçok uygulama, belgede tek bir görünüm ve belge başına yalnızca bir çerçeve penceresi ile tek bir belge türünü destekler (ancak bu türden birden çok açık belge olabilir). Ancak bazı uygulamaların bu varsayılandan bir veya birkaçını değiştirmek gerekebilir.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Birden çok belge türü](#_core_multiple_document_types)

- [Birden çok görünüm](#_core_multiple_views)

- [Birden çok çerçeve penceresi](#_core_multiple_frame_windows)

- [Bölümlendirici pencereleri](#_core_splitter_windows)

## <a name="multiple-document-types"></a><a name="_core_multiple_document_types"></a>Birden çok belge türü

MFC Uygulama Sihirbazı sizin için tek bir belge sınıfı oluşturur. Bazı durumlarda, ancak birden fazla belge türünü desteklemeniz gerekebilir. Örneğin, uygulamanızın çalışma sayfası ve grafik belgeleri olması gerekebilir. Her belge türü kendi belge sınıfı ve muhtemelen kendi görünüm sınıfı tarafından temsil edilir. Kullanıcı dosya yeni komutunu seçtiğinde, çerçeve desteklenen belge türlerini listeleyen bir iletişim kutusu görüntüler. Daha sonra kullanıcının seçtiği türün bir belgesini oluşturur. Her belge türü kendi belge şablonu nesnesi tarafından yönetilir.

Ek belge sınıfları oluşturmak için bkz. [sınıf ekleme](../ide/adding-a-class-visual-cpp.md). Türetebilirsiniz ve istenen belge bilgilerini sağlamak için sınıf türü olarak [CDocument](reference/cdocument-class.md) ' ı seçin. Ardından yeni sınıfın verilerini uygulayın.

Framework 'ün ek belge sınıfınız hakkında bilgi sahibi olmak için, uygulama sınıfınızın [InitInstance](reference/cwinapp-class.md#initinstance) geçersiz kılmasına Ikinci bir [AddDocTemplate](reference/cwinapp-class.md#adddoctemplate) çağrısı eklemeniz gerekir. Daha fazla bilgi için bkz. [Belge şablonları](document-templates-and-the-document-view-creation-process.md).

## <a name="multiple-views"></a><a name="_core_multiple_views"></a>Birden çok görünüm

Birçok belge yalnızca tek bir görünüm gerektirir, ancak tek bir belgenin birden fazla görünümünü desteklemek mümkündür. Birden çok görünüm uygulamanıza yardımcı olması için bir belge nesnesi görünümlerinin listesini tutar, görünümler ekleme ve kaldırma için üye işlevleri sağlar ve belge verilerinin ne zaman değiştiğini birden çok görünüme izin vermek için [UpdateAllViews](reference/cdocument-class.md#updateallviews) üye işlevini sağlar.

MFC, aynı belgede birden çok görünüm gerektiren üç ortak kullanıcı arabirimini destekler. Bu modeller şunlardır:

- Her biri ayrı bir MDI belge çerçevesi penceresinde aynı sınıfın nesnelerini görüntüleyin.

   Belge üzerinde ikinci bir çerçeve penceresi oluşturmayı desteklemek isteyebilirsiniz. Kullanıcı, aynı belgenin görünümü ile ikinci bir çerçeveyi açmak için yeni bir pencere komutu seçebilir ve sonra belgenin farklı bölümlerini aynı anda görüntülemek için iki kareyi de kullanabilir. Framework, başlangıç çerçevesi penceresini çoğaltarak ve belgeye ekli görünüm olan MDI uygulamaları için pencere menüsündeki yeni pencere komutunu destekler.

- Aynı belge çerçevesi penceresindeki aynı sınıfın nesnelerini görüntüleyin.

   Ayırıcı Windows, tek bir belge penceresinin görünüm alanını belgenin birden çok ayrı görünümüne ayırır. Çerçeve aynı görünüm sınıfından birden çok görünüm nesnesi oluşturur. Daha fazla bilgi için bkz. [bölünmüş pencereler](#_core_splitter_windows).

- Tek bir kare penceresinde farklı sınıfların nesnelerini görüntüleyin.

   Bu modelde, ayırıcı penceresinin bir çeşitlemesi olan birden çok görünüm tek bir çerçeve penceresi paylaşır. Görünümler farklı sınıflardan oluşturulur, her görünüm aynı belgeyi görüntülemenin farklı bir yolunu sağlar. Örneğin, bir görünüm bir sözcük işleme belgesini normal modda gösterebilir ve diğer görünüm bunu ana hat modunda gösterir. Bölümlendirici denetimi, kullanıcının görünümlerin göreli boyutlarını ayarlamasına olanak tanır.

Aşağıdaki şekil a, b ve c bölümlerine bölünmüştür, üç kullanıcı arabirimi modelini yukarıda sunulan sırayla gösterir.

![Birden çok&#45;Kullanıcı arabirimini görüntüleme](../mfc/media/vc37a71.gif "Birden çok&#45;Kullanıcı arabirimini görüntüleme") <br/>
Birden çok görüntüleme Kullanıcı arabirimleri

Framework, yeni pencere komutunu uygulayarak ve [Splitter Windows](#_core_splitter_windows)' da anlatıldığı gibi [CSplitterWnd](reference/csplitterwnd-class.md)sınıfı sağlayarak bu modelleri sağlar. Bunları Başlangıç noktanız olarak kullanarak başka modeller uygulayabilirsiniz. Görünümler, çerçeve pencereleri ve bölümlendiricileri farklı yapılandırma sürümlerini gösteren örnek programlar için bkz. [MFC örnekleri](../overview/visual-cpp-samples.md#mfc-samples).

Hakkında daha fazla bilgi için `UpdateAllViews` *MFC başvurusu* ve [karalama örneğinde](../overview/visual-cpp-samples.md)sınıf [CView](reference/cview-class.md) bölümüne bakın.

## <a name="multiple-frame-windows"></a><a name="_core_multiple_frame_windows"></a>Birden çok çerçeve penceresi

Aynı belgede ikinci bir çerçeve penceresi oluşturmak için MDI uygulamalarının pencere menüsündeki yeni pencere komutunu kullanabilirsiniz. Daha fazla bilgi için bkz. şekil birden çok görüntüleme Kullanıcı arabirimindeki ilk model.

## <a name="splitter-windows"></a><a name="_core_splitter_windows"></a>Bölümlendirici pencereleri

Bölümlendirici penceresinde pencere veya, iki veya daha fazla kaydırılabilir bölmeye ayrılabilir. Kaydırma çubuklarının yanındaki pencere çerçevesindeki bir ayırıcı denetimi (veya "Bölünmüş kutu"), kullanıcının bölmelerin göreli boyutlarını ayarlamasına olanak tanır. Her bölme aynı belge üzerindeki bir görünümüdür. "Dinamik" bölümlendiricileri içinde, şekil birden çok görüntüleme kullanıcı arabirimlerinin b bölümünde gösterildiği gibi, görünümler aynı sınıfta bulunur. "Statik" bölümlendiricileri içinde, görünümler farklı sınıflarda olabilir. Her iki türden de Splitter pencereleri, [CSplitterWnd](reference/csplitterwnd-class.md)sınıfı tarafından desteklenir.

Aynı sınıfın görünümleriyle dinamik Bölümlendirici pencereleri, kullanıcının bir pencereyi ' de birden çok bölmeye bölmesine izin verir ve sonra belgenin farklı parçalarını görmek için farklı bölmeleri kaydıracaktır. Kullanıcı ayrıca ek görünümleri kaldırmak için pencereyi bölebilir. [Karalama örneğine](../overview/visual-cpp-samples.md) eklenen Bölümlendirici pencereler bir örnektir. Bu konuda, dinamik Bölümlendirici pencereleri oluşturma tekniği açıklanmaktadır. Dinamik Bölümlendirici penceresi, şekil birden çok görüntüleme kullanıcı arabirimlerinin b bölümünde gösterilir.

Farklı sınıfların görünümleriyle statik Bölümlendirici pencereleri, her biri farklı bir amaca kadar birden çok bölmeye bölünmeye başlar. Örneğin, Visual C++ bit eşlem düzenleyicisinde, görüntü penceresi yan yana iki bölme gösterir. Sol bölmede, bit eşlemin yaşam boyutunda bir görüntüsü görüntülenir. Sağ bölmede aynı bit eşlemin yakınlaştırılmış veya büyütülmüş bir görüntüsü görüntülenir. Bölmeler, kullanıcının bölmelerin göreli boyutlarını değiştirmek için sürükleyemeyeceği bir "ayırıcı çubukla" ile ayrılır. Bir statik ayırıcı pencere, şekil birden çok görüntüleme kullanıcı arabirimlerinin c. bölümünde gösterilir.

Daha fazla bilgi için bkz. *MFC başvurusu* ve [MFC örnekleri](../overview/visual-cpp-samples.md#mfc-samples)Içindeki [CSplitterWnd](reference/csplitterwnd-class.md) sınıfı.

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](document-view-architecture.md)
