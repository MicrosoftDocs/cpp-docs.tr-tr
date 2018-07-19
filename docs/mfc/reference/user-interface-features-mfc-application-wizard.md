---
title: Kullanıcı arabirimi özellikleri, MFC Uygulama Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.ui
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, user interface features
ms.assetid: 59e7b829-a665-42eb-be23-3f2a36eb2dad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c73a8990687633eb5fe6bc15a76563bd1237eaf
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885783"
---
# <a name="user-interface-features-mfc-application-wizard"></a>Kullanıcı Arabirimi Özellikleri, MFC Uygulama Sihirbazı
Bu konuda, uygulamanızın görünümünü belirtmek için kullanabileceğiniz seçenekler açıklanmaktadır. Projeniz için kullanılabilir kullanıcı arabirimi özellikleri, belirttiğiniz uygulama türüne bağlıdır [Application Type, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası. Örneğin, bir tek belge arabirimi uygulaması oluşturursanız, alt çerçeve stilleri ekleyemezsiniz.  
  
 **Ana çerçeve stilleri**  
 Uygulamanızın ana pencere çerçevesi özelliklerini ayarlar.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Kalın kenarlığa**|Boyutlandırma kenarlığı içeren bir pencere oluşturur. Varsayılan.|  
|**Simge durumuna küçültme kutusu**|Ana çerçeve penceresine bir simge durumuna küçült kutusu içerir. Varsayılan.|  
|**Ekranı kaplama kutusu**|Ana çerçeve penceresine ekranı kaplama kutusunu içerir. Varsayılan.|  
|**Simge durumuna küçültülmüş**|Ana çerçeve penceresi simge olarak açılır.|  
|**Tam ekran**|Tam ekran boyutuna ana çerçeve penceresi açılır.|  
|**Sistem menüsü**|Ana çerçeve penceresine bir sistem menüsünü içerir. Varsayılan.|  
|**Hakkında kutusu**|İçeren bir **hakkında** uygulamanın kutusu. Kullanıcının bu kutu uygulamanın erişebildiği **yardımcı** menüsü. Varsayılan ve seçtiğiniz sürece değiştirilemez bir biçimde **iletişim kutusu tabanlı**, [Application Type, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md) sayfası.<br /><br /> **Not** genellikle kullanılamaz öğesinin onay kutusunu seçili ya da işaretli Sihirbazı seçeneği proje için geçerli değildir kullanılamayan bir seçenek gösterir. Bu durumda, sihirbaz her zaman ekler bir **hakkında** projeye, proje iletişim kutusu tabanlı belirtmediğiniz sürece kutusuna ve ardından kutunun işaretini kaldırın.|  
|**İlk durum çubuğu**|Uygulamanız için bir durum çubuğu ekler. Durum çubuğu klavyenin CAPS LOCK ve NUM LOCK SCROLL LOCK anahtarları için otomatik göstergeleri içerir ve menü komutları ve araç için yardımı görüntüler bir ileti satırı düğmeleri dizeleri. Bu seçeneğe tıkladığınızda, menü komutlarını durum çubuğunu görüntüleme veya gizleme için ekler. Varsayılan olarak, bir uygulama bir durum çubuğu vardır. İletişim kutusu tabanlı uygulama türleri için kullanılamaz.|  
|**Bölünmüş pencere**|Bir ayırıcıyı sağlar. Ayırıcıyı uygulamanın ana görünümlerine böler. Birden çok belge arabirimi (MDI) uygulamasında MDI alt çerçeve istemci penceresidir bir ayırıcı penceresi ve tek Belgeli Arabirim (SDI) uygulama ve birden çok üst düzey belge uygulaması, ana çerçevenin istemci bir ayırıcı penceresi penceredir. İletişim kutusu tabanlı uygulama türleri için kullanılamaz.|  
  
 **Alt çerçeve stilleri**  
 Uygulamanızda görünümünü ve alt çerçeve ilk durumunu belirtir. Alt çerçeve stilleri yalnızca MDI uygulamaları için kullanılabilir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Alt simge durumuna küçült kutusu**|Alt pencere bir simge durumuna küçült düğmesi (varsayılan olarak etkindir) olup olmadığını belirtir.|  
|**Alt öğe Ekranı Kapla kutusu**|Alt pencere bir Ekranı Kapla düğmesi (varsayılan olarak etkindir) olup olmadığını belirtir.|  
|**Alt öğe ekranı**|Alt pencere ilk başta cs.style ayarlayarak ekranı olup olmadığını belirtir, ws_maxımıze bayrak [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow) üye işlevini `CChildFrame`.|  
  
 **Komut çubukları (menü/araç/Şerit)**  
 Uygulama menüleri, araç çubukları ve/veya Şerit içerip içermediğini belirtir. İletişim tabanlı uygulamalar için kullanılamaz.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Klasik menü kullan**|Uygulamanızı bir Klasik, sürüklenebilir olmayan menü içerdiğini belirtir.|  
|**Klasik bir takma araç çubuğu kullan**|Uygulamanız için standart Windows araç çubuğu ekler. Araç çubuğu düğmeleri yeni bir belge oluşturmak için içerir; açma ve belge dosyaları kaydetme; Kesme; kopyalama, yapıştırma veya metin yazdırma ve Yardım moduna girme. Bu seçeneğin etkinleştirilmesi, görüntülemek veya araç çubuğunu gizlemek için menü komutlarını ekler.|  
|**Tarayıcı stili araç çubuğu kullan**|Uygulamanız için bir Internet Explorer-stili araç çubuğu ekler.|  
|**Bir menü çubuğu ve araç çubuğu kullan**|Uygulamanızı bir sürüklenebilir menü çubuğu ve araç çubuğu içerdiğini gösterir.|  
|**Kullanıcı tanımlı araç çubukları ve görüntüler**|Araç ve çalışma zamanında araç çubuğu görüntülerini özelleştirme izin verir.|  
|**Kişiselleştirilmiş Menü davranışı**|Menü açıldığında öğelerinin tam listesini içerip içermediğini veya kullanıcının en sık kullandığı komutları içerip içermediğini belirtir.|  
|**Şerit kullan**|Menü çubuğunda veya araç yerine uygulamanızdaki bir Office 2007 benzeri Şerit kullanır.|  
  
 **İletişim kutusu başlığı**  
 İçin [CDialog sınıfı](../../mfc/reference/cdialog-class.md)-Bu konu başlığı iletişim kutusunun başlık çubuğunda görünür tabanlı uygulamaları yalnızca. Bu alan düzenlemek için önce seçmelisiniz **iletişim kutusu tabanlı** altındaki **uygulama türü**. Daha fazla bilgi için [Application Type, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)

