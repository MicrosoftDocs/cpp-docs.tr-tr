---
title: Belge / görünüm mimarisi
ms.date: 11/19/2018
helpviewer_keywords:
- CView class [MFC], view architecture
- CDocument class [MFC]
- MFC, views
- views [MFC], MFC document/view model
- document objects [MFC]
- document objects [MFC], MFC document/view model
- MFC, documents
- documents [MFC], MFC document/view model
- document objects [MFC], document/view architecture
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
ms.openlocfilehash: d1b1f80f44fdc66a3174ea75c15e139f98a4520b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389685"
---
# <a name="documentview-architecture"></a>Belge/Görünüm Mimarisi

Varsayılan olarak, bir belge ve görünüm sınıfı ile bir uygulama çatısı MFC Uygulama Sihirbazı oluşturur. MFC, bu iki sınıf veri yönetime ayırır. Belge verileri depolar ve verileri yazdırma yönetir ve verilerin birden çok görünüm güncelleştiriliyor koordinatları. Görünüm verileri görüntüler ve bunu, düzenleme ve seçim dahil olmak üzere kullanıcı etkileşimi yönetir.

Bu modelde, bir MFC belge nesnesi okur ve verileri kalıcı depolamaya yazar. (Bir veritabanı gibi) bulunduğu her yerde belge verileri için bir arabirim de sağlayabilir. Ayrı view nesnesinin veri görüntüleme, kullanıcı seçimi için bir pencere içinde veri işleme ve veri düzenleme yönetir. Görünüm belgeden görünen verileri alır ve tüm veri değişiklikleri belgeye geri iletişim kurar.

Kolayca geçersiz kılabilir veya belge/görünüm ayrımı yoksay, ancak çoğu durumda bu modeli takip için ilgi çekici nedenler vardır. Aynı belgenin bir elektronik tablo hem de bir grafik görünümü gibi birden çok görünüm gerektiğinde en iyi biridir. Belge/görünüm modeli, ortak kod (örneğin, bir hesaplama altyapısını) tüm görünümleri belgede bulunabilir çalışırken verilerin her bir görünümünü temsil eden bir ayrı Görünüm nesnesi sağlar. Belge ayrıca veriler her değiştiğinde tüm görünümler güncelleştiriliyor, görev alır.

MFC belge/görünüm mimarisi, birden çok görünüm, birden çok belge türü, bölümlendirici pencereler ve diğer değerli kullanıcı arabirimi özellikleri desteklemek kolaylaştırır.

Belge ve görünüm hem kullanıcı hem de size, programcı en çok görünen MFC çerçevesi bölümlerdir. Framework ile uygulama geliştirme, işinizi çoğunu, belge ve görünüm sınıfları yazıya gider. Bu makalede ailesi açıklanmaktadır:

- Belgeleri ve görünümleri ve framework nasıl etkileştiğini amacı.

- Bunları uygulamak için neler gerekir.

Belge/görünüm yaklaşımının temelindeki dört temel sınıfları şunlardır:

[CDocument](../mfc/reference/cdocument-class.md) (veya [COleDocument](../mfc/reference/coledocument-class.md)) sınıfı, programınızın veri denetimi ya da depolamak için kullanılan nesneleri destekler ve Programcı tanımlı belge sınıfları için temel işlevleri sağlar. Bir belge, kullanıcı genellikle Dosya menüsünü Aç komutunu kullanarak açılır ve Kaydet komutu ile Dosya menüsünden kaydeden veri birimini temsil eder.

[CView](../mfc/reference/cview-class.md) (veya birçok ondan türetilen sınıflardan biri) Programcı tanımlı görünüm sınıfları için temel işlevleri sağlar. Görünüm bir belgeye ekli ve belge ile kullanıcı arasında aracı görevi görür: görünüm ekranında belgenin bir görüntü oluşturur ve işlemleri belge bağlı olarak kullanıcı girişini yorumlama. Görünümü, görüntü yazdırmayı ve baskı önizlemeyi için da işler.

[CFrameWnd](../mfc/reference/cframewnd-class.md) (veya türevlerini biri) belge bir veya daha fazla görünümlerini etrafında çerçeve sağlayan nesneleri destekler.

[CDocTemplate](../mfc/reference/cdoctemplate-class.md) (veya [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) veya [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)) belirli bir türün bir veya daha fazla belge düzenler ve doğru oluşturma yöneten bir nesneyi destekler Belge, Görünüm ve çerçeve pencere nesneleri için bu türü.

Aşağıdaki şekil, bir belge ve onun görünümü arasındaki ilişkiyi gösterir.

![Görünüm görüntülenen belgenin parçasıdır](../mfc/media/vc379n1.gif "görünümü görüntülenen belgenin parçasıdır") <br/>
Belge ve Görünüm

Belge/görünüm uygulaması Sınıf Kitaplığı'nda verilerin kendisini görünümünü ve veri kullanıcı işlemlerinde ayırır. Verilerde yapılan tüm değişiklikleri belge sınıfı yönetilir. Görünüm erişme ve verileri güncelleştirmek için bu arabirimi çağırır.

Belgeler, kendi ilişkili görünümler ve görünümlerin çerçeve çerçeve pencereleri, bir belge şablonu tarafından oluşturulur. Belge şablonu oluşturma ve bir belge türü tüm belgeleri yönetme sorumludur.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge/görünüm mimarisinin bir özeti](../mfc/a-portrait-of-the-document-view-architecture.md)

- [Belge/görünüm mimarisinin avantajları](../mfc/advantages-of-the-document-view-architecture.md)

- [Uygulama sihirbazından oluşturulan belge ve görünüm sınıfları](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)

- [Belge/görünüm mimarisinin alternatifleri](../mfc/alternatives-to-the-document-view-architecture.md)

- [Tek Bir Belgeye Birden Çok Görünüm Ekleme](../mfc/adding-multiple-views-to-a-single-document.md)

- [Belgeleri Kullanma](../mfc/using-documents.md)

- [Görünümleri Kullanma](../mfc/using-views.md)

- [Birden Fazla Belge Türü, Görünüm ve Çerçeve Penceresi](../mfc/multiple-document-types-views-and-frame-windows.md)

- [Başlatma ve belgeleri ve görünümleri temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)

- [Kendi eklemeleri belge ve görünüm sınıfları başlatma](../mfc/creating-new-documents-windows-and-views.md)

- [Belgeler ve görünümler ile veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-with-documents-and-views.md)

- [Belgeler ve görünümler olmadan veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-without-documents-and-views.md)

- [Örnekler](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)<br/>
[Windows](../mfc/windows.md)<br/>
[Çerçeve Pencereleri](../mfc/frame-windows.md)<br/>
[Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Belge/görünüm oluşturma](../mfc/document-view-creation.md)<br/>
[Yeni Belgeler, Pencereler ve Görünümler Oluşturma](../mfc/creating-new-documents-windows-and-views.md)
