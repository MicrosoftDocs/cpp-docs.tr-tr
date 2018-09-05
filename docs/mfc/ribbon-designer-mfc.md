---
title: Şerit Tasarımcısı (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.editors.ribbon.F1
dev_langs:
- C++
helpviewer_keywords:
- Ribbon Designer (MFC)
- MFC Ribbon Designer
ms.assetid: 0806dfd6-7d11-471a-99e1-4072852231f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0a812ff5304288a2a7c25edeb07d76a4d06ded8
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683021"
---
# <a name="ribbon-designer-mfc"></a>Şerit Tasarımcısı (MFC)
Şerit Tasarımcısı oluşturmanızı ve MFC uygulamalarında şeritler özelleştirme sağlar. Şerit, mantıksal gruplarda komutları düzenleyen bir kullanıcı arabirimi (UI) öğesidir. Bu grupların bir Şeritte ayrı sekmeler pencerenin üst kısmında görünür. Şerit menü çubuğu ve araç çubukları değiştirir. Şerit, uygulamanın kullanılabilirliğini önemli ölçüde artırabilir. Daha fazla bilgi için [şeritler](/windows/desktop/uxguide/cmd-ribbons). Aşağıdaki çizim Şerit gösterir.  
  
 ![MFC Şerit kaynak denetimi](../mfc/media/ribbon_no_callouts.png "ribbon_no_callouts")  
  
 Visual Studio'nun önceki sürümlerinde şeritler gerekiyordu gibi MFC Şerit sınıflarını kullanan kod yazılarak oluşturulmak [CMFCRibbonBar sınıfı](../mfc/reference/cmfcribbonbar-class.md). Visual Studio 2010 ve sonraki sürümlerinde, Şerit Tasarımcısı Şerit oluşturmak için alternatif bir yöntem sağlar. İlk olarak, oluşturma ve bir Şerit kaynağı olarak özelleştirebilirsiniz. Ardından MFC uygulamasındaki koddan Şerit kaynağını yükleyin. Hatta Şerit kaynaklarını ve MFC Şerit sınıflarını birlikte kullanabilirsiniz. Örneğin, bir Şerit kaynağı oluşturabilir ve ardından program aracılığıyla daha fazla öğe çalışma zamanında kodu kullanarak ekleyin.  
  
## <a name="understanding-the-ribbon-designer"></a>Şerit Tasarımcısı'nı anlama  
 Şerit Tasarımcısı oluşturur ve şeridi bir kaynak olarak depolar. Bir Şerit kaynağı oluşturduğunuzda, Şerit Tasarımcısı şu üç şeyi yapar:  
  
-   Bir giriş ekler proje kaynağı tanımlama betiğine (* .rc). Aşağıdaki örnekte, ıdr_rıbbon Şerit kaynağını tanımlayan benzersiz addır, RT_RIBBON_XML kaynak türüdür ve ribbon.mfcribbon ms kaynak dosyasının adıdır.  
  
 ```  
    IDR_RIBBON RT_RIBBON_XML      "res\\ribbon.mfcribbon-ms"  
 ```  
  
-   Tanımları komut kimliklerinin tanımını resource.h öğesine ekler.  
  
 ```  
 #define IDR_RIBBON            307  
 ```  
  
-   Şeridin düğmeleri, denetimleri ve özniteliklerini tanımlayan XML kodunu içeren bir Şerit kaynak dosyası (*.mfcribbon-ms) oluşturur. Şerit tasarımcısındaki Şeritte yapılan değişiklikler kaynak dosyasında XML olarak depolanır. Aşağıdaki kod örneği içeriğini parçası gösterir bir \*.mfcribbon-ms dosyası:  
  
 ```  
 <RIBBON_BAR>  
 <ELEMENT_NAME>RibbonBar</ELEMENT_NAME>  
 <IMAGE>  
 <ID>  
 <NAME>IDB_BUTTONS</NAME>  
 <VALUE>113</VALUE>  
 </ID>   
 ```  
  
 Şerit kaynağını MFC uygulamanızda kullanmak için çağırarak kaynağı yükleyin [CMFCRibbonBar::LoadFromResource](../mfc/reference/cmfcribbonbar-class.md#loadfromresource).  
  
## <a name="creating-a-ribbon-by-using-the-ribbon-designer"></a>Şerit Tasarımcısı kullanarak Şerit oluşturma  
 MFC projenize Şerit kaynağı eklemek için iki şekilde şunlardır:  
  
-   Bir MFC uygulaması oluşturun ve şeridi oluşturmak üzere MFC proje sihirbazını yapılandırın. Daha fazla bilgi için [izlenecek yol: bir Şerit uygulama tarafından kullanarak MFC oluşturma](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md).  
  
-   Mevcut bir MFC projesinde bir Şerit kaynağı oluşturabilir ve yükleyin. Daha fazla bilgi için [izlenecek yol: MFC karalama uygulamasını (Kısım 1) güncelleştirme](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md).  
  
 Projeniz el ile kodlanmış bir Şerit zaten varsa, MFC, mevcut şeridi bir Şerit kaynağına dönüştürmek için kullanabileceğiniz işlevleri vardır. Daha fazla bilgi için [nasıl yapılır: varolan bir MFC şeridini Şerit kaynağına dönüştürme](../mfc/how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource.md).  
  
> [!NOTE]
>  İletişim tabanlı uygulamalarda Şerit oluşturulamaz. Daha fazla bilgi için [Application Type, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md).  
  
## <a name="customizing-ribbons"></a>Şeritleri özelleştirme  
 Şerit Tasarımcısı'nda bir Şerit açmak için kaynak görünümünde Şerit kaynağını çift tıklayın. Tasarımcıda ekleyin, kaldırın ve Şerit, uygulama düğmesini veya hızlı erişim araç çubuğu öğelerini özelleştirdiğiniz. Düğme tıklama olayları ve menü olayları gibi olayları da uygulamanızda bir yönteme de bağlayabilirsiniz.  
  
 Aşağıdaki çizim Şerit tasarımcısındaki çeşitli bileşenleri gösterir.  
  
 ![MFC Şerit Tasarımcısı](../mfc/media/ribbon_designer.png "ribbon_designer")  
  
- **Araç kutusu:** Tasarımcı yüzeyine sürüklenebilen denetimler içerir.  
  
- **Tasarımcı yüzeyi:** Şerit kaynağını görsel temsilini içerir.  
  
- **Özellikler penceresi:** Tasarımcı yüzeyinde seçilen öğenin özniteliklerini listeler.  
  
- **Kaynak Görünümü penceresi:** projenize Şerit kaynakları dahil kaynakları görüntüler.  
  
- **Şerit Düzenleyicisi araç çubuğu:** sağlayan komutları içerir şeridi önizlemenizi ve görsel temasını değiştirmenizi.  
  
 Aşağıdaki konular, Şerit Tasarımcısı'nda özelliklerini kullanmak nasıl açıklar:  
  
- [Nasıl yapılır: Uygulama Düğmesini Özelleştirme](../mfc/how-to-customize-the-application-button.md)  
  
- [Nasıl yapılır: Hızlı Erişim Araç Çubuğunu Özelleştirme](../mfc/how-to-customize-the-quick-access-toolbar.md)  
  
- [Nasıl yapılır: Şerit Denetimleri ve Olay İşleyicileri Ekleme](../mfc/how-to-add-ribbon-controls-and-event-handlers.md)  
  
- [Nasıl yapılır: Bir MFC Uygulamasından Şerit Kaynağı Yükleme](../mfc/how-to-load-a-ribbon-resource-from-an-mfc-application.md)  
  
## <a name="definitions-of-ribbon-elements"></a>Şerit öğelerinin tanımları  
 ![MFC Şerit](../mfc/media/ribbon.png "Şerit")  
  
- **Uygulama düğmesi:** Şerit üzerinde üst sol löşede görüntülenen düğme. Uygulama düğmesi Dosya menüsünün yerini alır ve hatta Şerit küçültüldüğünde bile görülebilir. Düğme tıklandığında komutların bir listesini içeren bir menü görüntülenir.  
  
- **Hızlı Erişim Araç çubuğu:** sık görüntüleyen küçük ve özelleştirilebilir bir araç komutları kullanılır.  
  
- **Kategori**: bir Şerit sekmesinin içeriğini temsil eden mantıksal gruplama.  
  
- **Kategori varsayılan düğmesi:** Şerit küçültüldüğünde Şerit üzerinde görüntülenen düğme. Düğme tıklandığında kategori menü olarak yeniden görüntülenir.  
  
- **Pano:** bir ilgili denetimlerin grubunu görüntüleyen Şerit çubuğu bir alan. Her Şerit kategorisi bir veya daha fazla Şerit paneli içerir.  
  
- **Şerit öğeleri:** kontrol panellerinde, örneğin, düğmeler ve birleşik giriş kutuları. Bir Şeritte barındırılabilecek farklı denetimleri görmek için bkz: [RibbonGadgets örneği: Şerit araçları uygulaması](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)   
 [Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)

