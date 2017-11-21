---
title: "Belge görünüm mimarisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 63bf1b92521f7a99baed0d4a000b2f3cb1f804cb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="documentview-architecture"></a>Belge/Görünüm Mimarisi
Varsayılan olarak, MFC Uygulama Sihirbazı'nı bir belge ve görünüm sınıfı ile uygulamanın çatıyı oluşturur. MFC bu iki sınıf veri yönetime ayırır. Belge verileri depolar ve verileri yazdırma yönetir ve verilerin birden çok görünüm güncelleştiriliyor düzenler. Görünüm verileri görüntüler ve onunla, düzenleme ve seçim dahil olmak üzere kullanıcı etkileşimi yönetir.  
  
 Bu modelde bir MFC belge nesnesi okur ve kalıcı depolama alanına veri yazar. (Bir veritabanı gibi) bulunduğu yerde belge verileri için bir arabirim de sağlayabilir. Ayrı Görünüm nesnesi veri görüntüleme, kullanıcı Seçimi penceresinde veri işleme ve veri düzenlemesini yönetir. Görünüm belgeden görüntü verilerini alır ve belgeye geri tüm veri değişiklikleri iletişim kurar.  
  
 Kolayca geçersiz kılabilir veya belge/görünüm ayrımı yoksay olsa da, çoğu durumda bu modelini izlemek için ilgi çekici nedeni vardır. Elektronik Tablo ve grafik görünümü gibi aynı belgenin birden çok görünüm gerektiğinde en iyi biridir. Belge/görünüm modeli her kod ortak tüm görünümleri (örneğin, bir hesaplama altyapısı) belgesinde bulunabilir sırasında verilerin görünümünü temsil eden ayrı Görünüm nesnesi sağlar. Belge ayrıca veriler değiştiğinde, tüm görünümleri güncelleştirme görevi alır.  
  
 MFC belge/görünüm mimarisinin birden çok görünüm, birden çok belge türü, bölümlendirici pencereler ve diğer değerli kullanıcı arabirimi özellikleri desteklemek daha kolay hale getirir.  
  
 Belge ve görünüm de hem kullanıcı hem de siz Programcı en görünür MFC çerçevesi bölümlerdir. Framework ile bir uygulama geliştirirken, işinizin çoğunu gider, belge ve görünüm sınıfları yazma içine. Bu makale ailesi açıklanmaktadır:  
  
-   Belgeler ve görünümler ve framework nasıl etkileşim kurduklarını amaçları.  
  
-   Bunları uygulamak için neler gerekir.  
  
 Belge/görünüm Kalp dört anahtar sınıfları şunlardır:  
  
 [CDocument](../mfc/reference/cdocument-class.md) (veya [COleDocument](../mfc/reference/coledocument-class.md)) sınıf depolamak veya programınızın verileri denetlemek için kullanılan nesneleri destekler ve belge Programcı tanımlı sınıflar için temel işlevleri sağlar. Bir belge kullanıcı genellikle Dosya menüsünde Aç komutuyla açar ve Dosya menüsünde Kaydet komutuyla kaydeden veri birimi temsil eder.  
  
 [CView](../mfc/reference/cview-class.md) (veya birçok türetilmiş sınıflarından biri) temel işlevleri için programcı tanımlı görünüm sınıfları sağlar. Bir görünüm belgeye eklenir ve belge ve kullanıcı arasındaki bir aracı gibi davranır: görünüm belgenin ekran görüntüsünü oluşturur ve işlemleri belge bağlı olarak kullanıcı girişini yorumlama. Görünümü de yazdırmayı ve Baskı Önizleme için görüntü oluşturur.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md) (veya kendi çeşitleri) bir belge bir veya daha fazla görünümlerini etrafındaki çerçeveyi sağlar nesneleri destekler.  
  
 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) (veya [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) veya [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)) belirli bir türde bir veya daha fazla var olan belgeler düzenler ve doğru oluşturma yöneten bir nesne destekler Belge, Görünüm ve çerçeve pencere nesneleri türü için.  
  
 Aşağıdaki şekilde, bir belge ve kendi görünüm arasındaki ilişkiyi gösterir.  
  
 ![Görünüm görüntülenir belge parçasıdır](../mfc/media/vc379n1.gif "vc379n1")  
Belge ve Görünüm  
  
 Belge/görünüm uygulama Sınıf Kitaplığı'nda verilerin kendisini görünümünü ve veriler üzerinde kullanıcı işlemler ayırır. Veri yapılan tüm değişiklikler belge sınıfı üzerinden yönetilir. Görünüm erişme ve verileri güncelleştirmek için bu arabirimi çağırır.  
  
 Belgeler, bunların ilişkili görünümleri ve görünüm çerçeve çerçeve pencereleri bir belge şablonu tarafından oluşturulur. Belge şablonu oluşturma ve bir belge türü tüm belgeleri yönetme sorumludur.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Belge/görünüm mimarisinin bir özeti](../mfc/a-portrait-of-the-document-view-architecture.md)  
  
-   [Belge/görünüm mimarisinin avantajları](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Uygulama Sihirbazı tarafından oluşturulan belge ve görünüm sınıfları](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)  
  
-   [Belge/görünüm mimarisinin alternatifleri](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [Tek bir belgeye birden çok görünüm ekleme](../mfc/adding-multiple-views-to-a-single-document.md)  
  
-   [Belgeleri kullanma](../mfc/using-documents.md)  
  
-   [Görünümleri kullanma](../mfc/using-views.md)  
  
-   [Birden çok belge türü, görünümler ve çerçeve pencereleri](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Başlatma ve belgeleri ve görünümleri temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
-   [Belge ve görünüm sınıfları kendi eklemeler başlatma](../mfc/creating-new-documents-windows-and-views.md)  
  
-   [Belgeler ve görünümler ile veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-with-documents-and-views.md)  
  
-   [Belgeler ve görünümler olmadan veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-without-documents-and-views.md)  
  
-   [Örnekleri](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)   
 [Windows](../mfc/windows.md)   
 [Çerçeve pencereleri](../mfc/frame-windows.md)   
 [Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Belge/görünüm oluşturma](../mfc/document-view-creation.md)   
 [Yeni belgeler, pencereler ve görünümler oluşturma](../mfc/creating-new-documents-windows-and-views.md)

