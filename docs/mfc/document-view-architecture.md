---
description: 'Daha fazla bilgi edinin: belge/görünüm mimarisi'
title: Document-View mimarisi
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
ms.openlocfilehash: ef6746a77a3f8a482c347d61685fccad3e6b4dfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339728"
---
# <a name="documentview-architecture"></a>Belge/Görünüm Mimarisi

Varsayılan olarak, MFC Uygulama Sihirbazı bir belge sınıfı ve bir görünüm sınıfı ile bir uygulama iskelet 'i oluşturur. MFC veri yönetimini bu iki sınıfa ayırır. Belge verileri saklar ve verilerin yazdırılmasını yönetir ve verilerin birden çok görünümünü günceller. Görünüm, verileri görüntüler ve seçim ve düzenlemeyle birlikte kullanıcı etkileşimini yönetir.

Bu modelde, bir MFC belge nesnesi kalıcı depolamaya verileri okur ve yazar. Belge, verilerin bulunduğu yerde (örneğin, bir veritabanında) bir arabirim de sağlayabilir. Ayrı bir görünüm nesnesi, bir penceredeki verilerin Kullanıcı seçimine ve düzenlenmesine kadar veri görüntülemesini yönetir. Görünüm, belgedeki görüntü verilerini alır ve veri değişikliklerinin bulunduğu belgeye geri iletişim kurar.

Belge/görünüm ayırmayı kolayca geçersiz kılabilir veya yoksayabilirsiniz, ancak çoğu durumda bu modeli izlemek için çekici nedenler vardır. En iyisi, aynı belgenin hem elektronik tablo hem de grafik görünümü gibi birden çok görünümüne ihtiyaç duyduktan biridir. Belge/görünüm modeli, ayrı bir görünüm nesnesinin verilerin her görünümünü temsil etmesini sağlar, ancak tüm görünümlerde ortak kod (örneğin bir hesaplama motoru) belgede bulunabilir. Belge, veriler değiştiğinde tüm görünümleri güncelleştirme görevini de alır.

MFC belge/görünüm mimarisi, birden fazla görünümü, birden çok belge türünü, Splitter pencerelerini ve diğer değerli kullanıcı arabirimi özelliklerini desteklemeyi kolaylaştırır.

MFC çerçevesinin her ikisi de hem Kullanıcı hem de sizin için görünebilir olan parçalar belge ve görünümlerdir. Çerçeve ile uygulama geliştirme işlerinde çalışmanızın çoğu belge ve görünüm sınıflarını yazmaya devam ediyor. Bu makale ailesinde şunları anlatmaktadır:

- Belge ve görünümlerin ve çerçevede nasıl etkileşime gireceğini gösteren amaçlar.

- Bunları uygulamak için yapmanız gerekenler.

Belge/görünüm 'in Kupa dört anahtar sınıfı vardır:

[CDocument](reference/cdocument-class.md) (veya [cotadocument](reference/coledocument-class.md)) sınıfı, programınızın verilerini depolamak veya denetlemek için kullanılan nesneleri destekler ve programcı tanımlı belge sınıfları için temel işlevselliği sağlar. Belge, kullanıcının Dosya menüsündeki Aç komutuyla genellikle açtığı veri birimini temsil eder ve Dosya menüsünde Kaydet komutuyla kaydeder.

[CView](reference/cview-class.md) (veya birden çok türetilmiş sınıflarından biri), programcı tanımlı görünüm sınıfları için temel işlevleri sağlar. Bir görünüm belgeye iliştirilir ve belge ve Kullanıcı arasında bir aracı görevi görür: görünüm, ekranda belgenin bir görüntüsünü oluşturur ve Kullanıcı girişini belge üzerinde işlemler olarak yorumlar. Görünüm, görüntüyü hem yazdırma hem de baskı önizleme için de işler.

[CFrameWnd](reference/cframewnd-class.md) (veya varyasyonlarından biri), bir belgenin bir veya daha fazla görünümü etrafında çerçeve sağlayan nesneleri destekler.

[CDocTemplate](reference/cdoctemplate-class.md) (veya [CSingleDocTemplate](reference/csingledoctemplate-class.md) veya [CMultiDocTemplate](reference/cmultidoctemplate-class.md)), belirli bir türün varolan bir veya daha fazla belgesini koordine eden bir nesneyi destekler ve bu tür için doğru belge, görünüm ve çerçeve pencere nesnelerini oluşturmayı yönetir.

Aşağıdaki şekilde, bir belge ve görünümü arasındaki ilişki gösterilmektedir.

![Görünüm, görüntülenen belgenin parçasıdır](../mfc/media/vc379n1.gif "Görünüm, görüntülenen belgenin parçasıdır") <br/>
Belge ve görünüm

Sınıf kitaplığındaki belge/görünüm uygulamasının verileri kendi görüntüsüne ve verilerdeki Kullanıcı işlemlerinden ayırır. Verilerde yapılan tüm değişiklikler belge sınıfı aracılığıyla yönetilir. Görünüm, verileri erişmek ve güncelleştirmek için bu arabirimi çağırır.

Belgeler, ilişkili görünümleri ve görünümleri çerçevesini görüntüleyen çerçeve pencereleri bir belge şablonu tarafından oluşturulur. Belge şablonu, bir belge türünün tüm belgelerini oluşturmaktan ve yönetmekten sorumludur.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge/görünüm mimarisinin dikey](a-portrait-of-the-document-view-architecture.md)

- [Belge/görünüm mimarisinin avantajları](advantages-of-the-document-view-architecture.md)

- [Uygulama Sihirbazı tarafından oluşturulan belge ve Görünüm sınıfları](document-and-view-classes-created-by-the-mfc-application-wizard.md)

- [Belge/görünüm mimarisi alternatifleri](alternatives-to-the-document-view-architecture.md)

- [Tek bir belgeye birden çok görünüm ekleme](adding-multiple-views-to-a-single-document.md)

- [Belgeleri kullanma](using-documents.md)

- [Görünümleri kullanma](using-views.md)

- [Birden çok belge türü, görünüm ve çerçeve penceresi](multiple-document-types-views-and-frame-windows.md)

- [Belgeleri ve görünümleri başlatma ve temizleme](initializing-and-cleaning-up-documents-and-views.md)

- [Belge & Görünüm sınıfları için kendi eklemelerinizi başlatın](creating-new-documents-windows-and-views.md)

- [Belgeler ve görünümler ile veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-with-documents-and-views.md)

- [Belgeler ve görünümler olmadan veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-without-documents-and-views.md)

- [Örnekler](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](user-interface-elements-mfc.md)<br/>
[Windows](windows.md)<br/>
[Çerçeve pencereleri](frame-windows.md)<br/>
[Belge şablonları ve belge/görünüm oluşturma Işlemi](document-templates-and-the-document-view-creation-process.md)<br/>
[Belge/görünüm oluşturma](document-view-creation.md)<br/>
[Yeni belgeler, pencereler ve görünümler oluşturma](creating-new-documents-windows-and-views.md)
