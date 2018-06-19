---
title: Çerçeve Windows | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame widows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 515df19bcc11f7a6706985014fc44bc4ff315f36
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352069"
---
# <a name="frame-windows"></a>Çerçeve Pencereleri
Bir uygulamayı Windows altında çalıştığında, kullanıcı çerçeve pencerelerinde görüntülenen belgeleri ile etkileşim kurar. Belge çerçeve penceresi iki önemli bileşeni vardır: çerçeve ve onu çerçeve içeriği. Belge çerçeve penceresi olabilir bir [tek belge arabirimi](../mfc/sdi-and-mdi.md) (SDI) çerçeve penceresi veya [birden çok belge arabirimi](../mfc/sdi-and-mdi.md) (MDI) alt pencere. Windows kullanıcı etkileşimi çerçeve penceresi ile çoğunu yönetir: taşıma pencerede yeniden boyutlandırma, kapatma ve en aza ve onu en üst düzeye çıkarma. Çerçeve içine içeriği yönetin.  
  
## <a name="frame-windows-and-views"></a>Çerçeve pencereleri ve görünümler  
 MFC çerçevesi çerçeve pencereleri görünümler içermesi için kullanır. İki bileşeni — çerçeve ve içeriği — temsil ve MFC içinde iki farklı sınıflar tarafından yönetilir. Çerçeve pencere sınıfı çerçeve yönetir ve görünüm sınıfı içeriği yönetir. Çerçeve penceresi alt görünüm penceredir. Çizim ve başka bir kullanıcı etkileşimi belgeyle görünümün istemci alanı, çerçeve penceresinin istemci alanını gerçekleşir. Çerçeve penceresi görünümü, tam bir başlık çubuğu ve denetim menüsünde, en aza indirmek ve pencere en üst düzeye çıkarmak için düğmeleri gibi standart pencere denetimleriyle etrafında görünür bir çerçeve sağlar ve pencereyi yeniden boyutlandırma için denetler. Tam olarak bir alt pencere tarafından kullanılıyor pencerenin istemci alanını "İçerik" oluşur — görünümü. Aşağıdaki şekilde bir çerçeve penceresinde ve bir görünüm arasındaki ilişkiyi gösterir.  
  
 ![Çerçeve penceresi görünümü](../mfc/media/vc37fx1.gif "vc37fx1")  
Çerçeve penceresi ve görünümü  
  
## <a name="frame-windows-and-splitter-windows"></a>Çerçeve pencereleri ve Bölümlendirici pencereler  
 Çerçeve penceresi kullanımı genellikle birden çok görünüm çerçeve başka bir genel düzenleme olan bir [Bölümlendirici pencere](../mfc/multiple-document-types-views-and-frame-windows.md). Bölümlendirici penceresinde, çerçeve penceresinin istemci alanını sırayla görünümlerdir bölmeleri adlı birden çok alt windows sahip bir Bölümlendirici pencere tarafından kullanılıyor.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
 **Genel çerçeve penceresi konuları**  
  
-   [Pencere nesneleri](../mfc/window-objects.md)  
  
-   [Çerçeve penceresi sınıfları](../mfc/frame-window-classes.md)  
  
-   [Uygulama Sihirbazı tarafından oluşturulan çerçeve pencere sınıfları](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)  
  
-   [Çerçeve pencerelerinin görevi](../mfc/what-frame-windows-do.md)  
  
 **Çerçeve pencerelerini kullanma konuları**  
  
-   [Çerçeve pencerelerini kullanma](../mfc/using-frame-windows.md)  
  
-   [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)  
  
-   [Çerçeve pencerelerini yok etme](../mfc/destroying-frame-windows.md)  
  
-   [MDI alt öğe pencerelerini yönetme](../mfc/managing-mdi-child-windows.md)  
  
-   [Geçerli görünümü yönetme](../mfc/managing-the-current-view.md) birden çok görünüm içeren bir çerçeve penceresinde  
  
-   [Menüleri, Denetim çubuklarını ve Hızlandırıcıları (çerçeve pencere alanını paylaşan diğer nesnelerin) yönetme](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 **Özel çerçeve pencere yetenekleri konularda**  
  
-   [Dosyaları sürükleme ve bırakma](../mfc/dragging-and-dropping-files-in-a-frame-window.md) dosya Gezgini veya bir çerçeve penceresinde içine Dosya Yöneticisi  
  
-   [Dinamik veri değişimine (DDE) yanıt verme](../mfc/responding-to-dynamic-data-exchange-dde.md)  
  
-   [Yarı kalıcı durumlar: Context-sensitive (diğer pencere işlemlerini yönetme) Windows Yardım](../mfc/orchestrating-other-window-actions.md)  
  
-   [Yarı kalıcı durumlar: yazdırmayı ve Baskı Önizleme (diğer pencere işlemlerini yönetme)](../mfc/orchestrating-other-window-actions.md)  
  
 **Diğer pencere cinsleri konularda**  
  
-   [Görünümleri Kullanma](../mfc/using-views.md)  
  
-   [İletişim kutuları](../mfc/dialog-boxes.md)  
  
-   [Denetimler](../mfc/controls-mfc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows](../mfc/windows.md)

