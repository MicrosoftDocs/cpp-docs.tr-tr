---
title: "Kullanıcı arabirimi özellikleri, MFC Uygulama Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.ui
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, user interface features
ms.assetid: 59e7b829-a665-42eb-be23-3f2a36eb2dad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5906cf607e09df536825eed88e7b1be59d8fdee2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="user-interface-features-mfc-application-wizard"></a>Kullanıcı Arabirimi Özellikleri, MFC Uygulama Sihirbazı
Bu konu, uygulamanızı görünümünü belirtmek için kullanabileceğiniz seçenekleri açıklar. Projeniz için kullanılabilir kullanıcı arabirimi özellikleri, belirttiğiniz uygulama türüne bağlıdır [uygulama türü, MFC Uygulama Sihirbazı'nı](../../mfc/reference/application-type-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası. Örneğin, bir tek belge arabirimi uygulama oluşturursanız, alt çerçeve stiller ekleyemezsiniz.  
  
 **Ana pencere stilleri**  
 Uygulamanızın ana pencere çerçevesi özelliklerini ayarlar.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Kalın çerçeve**|Boyutlandırma kenarlık sahip bir pencere oluşturur. Varsayılan.|  
|**Kutusunu simge durumuna küçült**|Bir simge durumuna küçült kutusu ana çerçeve penceresinde içerir. Varsayılan.|  
|**Kutusunu en üst düzeye çıkarmak**|Ekranı Kapla kutusu ana çerçeve penceresinde içerir. Varsayılan.|  
|**Simge durumuna küçültülmüş**|Ana çerçeve penceresi simge olarak açılır.|  
|**Tam ekran**|Tam boyutlu görüntü için ana çerçeve penceresi açılır.|  
|**Sistem menüsü**|Bir sistem menüsü ana çerçeve penceresinde içerir. Varsayılan.|  
|**Kutusu hakkında**|İçeren bir **hakkında** kutusuna uygulama için. Kullanıcı bu kutu uygulamanın erişebilir **yardımcı** menüsü. Varsayılan ve seçtiğiniz sürece değiştirilemez **tabanlı iletişim**, [uygulama türü, MFC Uygulama Sihirbazı'nı](../../mfc/reference/application-type-mfc-application-wizard.md) sayfası.<br /><br /> **Not** kullanılamaz öğesi'nin onay kutusunun seçili ya da temizlenmiş Sihirbazı'nı seçeneği proje için geçerli değildir kullanılamayan bir seçenek genellikle gösterir. Bu durumda, sihirbaz her zaman ekler bir **hakkında** siz proje iletişim kutusu dayalı olarak belirtmediğiniz sürece projeye kutusuna ve kutunun işaretini kaldırın.|  
|**İlk durum çubuğu**|Durum çubuğu uygulamanıza ekler. Yardımı görüntüler bir ileti satırı menü komutları ve araç çubuğu düğmeleri dizeleri ve durum çubuğu klavyenin CAPS LOCK, NUM LOCK ve Kaydırma kilidi anahtarları için otomatik göstergelerini içerir. Bu seçeneğini tıklatarak, durum çubuğunu görüntüleme veya gizleme için menü komutlarını ekler. Varsayılan olarak, bir uygulama durum çubuğu sahiptir. İletişim tabanlı uygulama türleri için kullanılamaz.|  
|**Pencere Böl**|Bir ayırıcı çubuk sağlar. Ayırıcı çubuğu uygulamanın ana görünüm böler. Birden çok belge arabirimi (MDI) uygulaması MDI alt çerçeve istemci bir Bölümlendirici penceresidir ve tek belge arabirimi (SDI) uygulama ve birden çok üst düzey belge uygulaması, ana çerçeve istemci Bölümlendirici pencere penceredir. İletişim tabanlı uygulama türleri için kullanılamaz.|  
  
 **Alt çerçeve stilleri**  
 Görünüm ve alt çerçeveler ilk durumunda, uygulamanızda belirtir. Alt çerçeve stiller yalnızca MDI uygulamaları için kullanılabilir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Alt simge durumuna küçült kutusu**|Alt pencere (varsayılan olarak etkindir) bir simge durumuna Küçült düğmesini sahip olup olmadığını belirtir.|  
|**Alt en üst düzeye çıkarmak kutusu**|Alt pencere (varsayılan olarak etkindir) Ekranı Kapla düğmesi olup olmadığını belirtir.|  
|**Tam ekran alt**|Alt pencere başlangıçta cs.style bayrağını ayarlayarak ekranı olup olmadığını belirtir **ws_maxımıze** içinde [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow) üye işlevini `CChildFrame`.|  
  
 **Komut çubukları (araç çubuğu/menü/Şerit)**  
 Uygulamanızı menüleri, araç çubukları ve/veya bir Şerit içerip içermediğini gösterir. İletişim tabanlı uygulamalar için kullanılamaz.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Klasik menüsünü kullanın**|Uygulamanızı bir Klasik, sürüklenebilir olmayan menü içerdiğini belirtir.|  
|**Klasik yerleşik bir araç kullanın**|Standart bir Windows araç uygulamanıza ekler. Araç çubuğu düğmeleri yeni bir belge oluşturmak için içerir; dosyaları açma ve belge kaydetme; kopyalama, yapıştırma ya da metin yazdırma kesme; ve Yardım moduna girmeye. Bu seçeneğin etkinleştirilmesi görüntülemek veya gizlemek araç çubuğuna menü komutlarını ekler.|  
|**Bir tarayıcı stili araç kullanın**|Internet Explorer stili araç uygulamanıza ekler.|  
|**Menü çubuğu ve araç kullanın**|Uygulamanızı bir sürüklenebilir menü çubuğu ve bir araç çubuğu içerdiğini gösterir.|  
|**Kullanıcı tanımlı araç çubukları ve görüntüleri**|Araç çubuğu ve çalışma zamanında araç görüntülerini özelleştirme olanak tanır.|  
|**Kişiselleştirilmiş Menü davranışı**|Menü açıldığında öğelerin tam listesini içerip içermediğini veya kullanıcının en sık kullandığı komutları içerip içermediğini belirtir.|  
|**Şerit kullanın**|Menü çubuğu veya araç yerine, uygulamanızdaki bir Office 2007 benzeri Şerit kullanır.|  
  
 **İletişim kutusu başlığı**  
 İçin [CDialog sınıfı](../../mfc/reference/cdialog-class.md)-tabanlı uygulamaları yalnızca, bu başlık iletişim kutusunun başlık çubuğunda görünür. Bu alan düzenlemek için önce seçmelisiniz **tabanlı iletişim** altında seçeneği **uygulama türü**. Daha fazla bilgi için bkz: [uygulama türü, MFC Uygulama Sihirbazı'nı](../../mfc/reference/application-type-mfc-application-wizard.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)

