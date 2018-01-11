---
title: "Baskı Önizleme mimarisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- print preview [MFC], process
- previewing printing
- print preview [MFC], architecture
- printing [MFC], print preview
- print preview [MFC], modifications to MFC
ms.assetid: 0efc87e6-ff8d-43c5-9d72-9b729a169115
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ffffa6c446487752974549f4a070cf8e86e91aea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="print-preview-architecture"></a>Baskı Önizleme Mimarisi
Bu makalede, MFC çerçevesi Baskı Önizleme işlevselliği nasıl uyguladığını açıklanmaktadır. Kapsanan konular şunlardır:  
  
-   [Baskı Önizleme işlemi](#_core_the_print_preview_process)  
  
-   [Baskı Önizleme değiştirme](#_core_modifying_print_preview)  
  
 Görüntüyü bir aygıtta doğrudan çizim yerine, uygulama ekran kullanarak yazıcı benzetimini gerekir çünkü Baskı Önizleme ekran ve yazdırma biraz farklıdır. Bunu yapabilmek için Microsoft Foundation Class Kitaplığı türetilmiş bir özel (belgelenmemiş) sınıf tanımlar [CDC sınıfı](../mfc/reference/cdc-class.md)adlı **CPreviewDC**. Tüm `CDC` nesneleri içeren iki cihaz bağlamları, ancak genellikle bunlar aynıdır. İçinde bir **CPreviewDC** nesnesi, farklı oldukları: benzetimli yazıcı ilk ve ikinci üzerinde çıkış gerçekte görüntülendiği ekran temsil eder.  
  
##  <a name="_core_the_print_preview_process"></a>Baskı Önizleme işlemi  
 Baskı Önizleme komuttan seçtiğinde kullanıcı **dosya** framework menüsünde oluşturur bir **CPreviewDC** nesnesi. Uygulamanızı karakteristiğini yazıcı cihaz bağlamı, ayarlar bir işlem gerçekleştirdiğinde, framework ekran cihaz bağlamı üzerinde benzer bir işlem de gerçekleştirir. Örneğin, uygulamanızın yazdırma için yazı tipi seçerse, framework yazıcı yazı tipi benzetim ekran görüntüsü için bir yazıtipi seçer. Uygulamanızı yazıcıya çıktı gönderebilir her framework ekrana yerine çıkış gönderir.  
  
 Baskı Önizleme ayrıca her bir belgenin sayfaları çizer sırayla yazdırma farklıdır. Belirli bir sayfa aralığını işlenip işlenmediğini kadar yazdırma sırasında framework yazdırma döngü devam eder. Baskı Önizleme sırasında herhangi bir anda bir veya iki sayfa görüntülenir ve uygulama bekler; Kullanıcı yanıt verene kadar başka hiçbir sayfaları da görüntülenir. Baskı Önizleme sırasında uygulama ayrıca yanıt gerekir `WM_PAINT` , normal ekran görüntüsünü sırasında çalıştığı gibi iletileri.  
  
 [CView::OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) işlevi çağrıldığında önizleme modunda çağrıldığında, bir yazdırma işinin başlangıcında olduğu gibi. [Cprintınfo yapısı](../mfc/reference/cprintinfo-structure.md) işleve yapı değerleri Baskı Önizleme işlemi belirli özelliklerini ayarlamak için ayarlayabileceğiniz birkaç üye içeriyor. Örneğin, ayarlayabileceğiniz **m_nNumPreviewPages** üye tek sayfalı veya iki sayfa modu belgede Önizleme isteyip istemediğinizi belirtin.  
  
##  <a name="_core_modifying_print_preview"></a>Baskı Önizleme değiştirme  
 Bunun yerine kolayca çeşitli yollarla baskı önizlemede görünümünü ve davranışını değiştirebilirsiniz. Örneğin, size, diğerlerinin yanında yapabilirsiniz:  
  
-   Belge herhangi bir sayfayı için kolay erişim için bir kaydırma çubuğu görüntülemek Baskı Önizleme penceresinden neden.  
  
-   Geçerli sayfada görünümünü başlayarak belgedeki kullanıcının konumunu korumak Baskı Önizleme neden.  
  
-   Baskı Önizleme ve yazdırma için gerçekleştirilecek farklı başlatma neden.  
  
-   Sayfa sayıları kendi biçimlerde görüntülemek Baskı Önizleme neden.  
  
 Belgenin ne kadar olacağını bildiğiniz ve arama `SetMaxPage` uygun değerle framework bu bilgileri Önizleme modundadır ve aynı zamanda yazdırma sırasında kullanabilirsiniz. Belgenin uzunluğunu framework belirledikten sonra onu bir kaydırma çubuğunun, belgenin önizleme modunda aracılığıyla geri ve İleri sayfasında arkasından önizleme penceresi sağlayabilirsiniz. Belgenin uzunluğunu ayarlamadıysanız framework framework bir kaydırma çubuğunun eklemez şekilde geçerli konumunu belirtmek üzere kaydırma kutusunun konumunu olamaz. Bu durumda, kullanıcı bir sonraki sayfa ve önceki sayfaya düğmeleri Önizleme pencerenin denetim çubuğundaki Belge sayfadan kullanmanız gerekir.  
  
 Baskı Önizleme için bir değer atamak yararlı `m_nCurPage` üyesi `CPrintInfo`rağmen hiç sıradan yazdırmak için bunu. Sıradan yazdırma sırasında bu üye framework bilgilerinden görünüm sınıfınıza taşır. Hangi sayfa yazdırılacağı framework görünümü nasıl söyler budur.  
  
 Bunun aksine, Baskı Önizleme modunu başlatıldığında, `m_nCurPage` üye ters yönde bilgi taşır: Framework görünümünden. Framework bu üyenin değerini hangi sayfa ilk önizlemesi belirlemek için kullanır. Belgenin ilk sayfası başlangıçta görüntülenen şekilde bu üyenin varsayılan değer 1 ' dir. Geçersiz kılabilirsiniz `OnPreparePrinting` bu üye Baskı Önizleme komutunu çağrıldığı aynı anda görüntülenen sayfa sayısını ayarlamak için. Bu şekilde, uygulama kullanıcının geçerli konumunu normal ekran modundan Baskı Önizleme modunu taşırken tutar.  
  
 Bazen isteyebilirsiniz `OnPreparePrinting` olup Baskı Önizleme veya yazdırma işi için çağrılır bağlı olarak farklı başlatılmasını gerçekleştirmek için. Bu inceleyerek belirleyin **m_bPreview** üye değişkeni `CPrintInfo` yapısı. Bu üye kümesine **TRUE** Baskı Önizleme zaman çağrılır.  
  
 `CPrintInfo` Yapı ayrıca adlı bir üye içeriyor **m_strPageDesc**, ekranın alt kısmındaki tek sayfalı ve birden çok sayfa modda görüntülenen dizeleri biçimlendirmek için kullanılır. Varsayılan olarak bu dizeler biçimidir "Sayfa  *n* " ve "sayfaları  *n*   -  *m*," ancak değiştirebilirsiniz **m_ strPageDesc** içinden `OnPreparePrinting` ve daha karmaşık bir şey için dizeleri ayarlayın. Bkz: [Cprintınfo yapısı](../mfc/reference/cprintinfo-structure.md) içinde *MFC başvurusu* daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazdırma ve Baskı Önizleme](../mfc/printing-and-print-preview.md)   
 [Yazdırma](../mfc/printing.md)   
 [CView sınıfı](../mfc/reference/cview-class.md)   
 [CDC Sınıfı](../mfc/reference/cdc-class.md)
