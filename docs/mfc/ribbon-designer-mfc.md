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
ms.openlocfilehash: dbde67e61a38190a2e26884659d273b55a63f89e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="ribbon-designer-mfc"></a>Şerit Tasarımcısı (MFC)
Şerit Tasarımcısı oluşturmanızı ve MFC uygulamalarında Şerit özelleştirme sağlar. Şerit komutları mantıksal gruplar halinde düzenler bir kullanıcı arabirimi (UI) öğesidir. Bu gruplar bir Şerit ayrı sekmeleri pencerenin üst kısmında görüntülenir. Şerit menü çubuğu ve araç çubuklarını yerini alır. Şerit uygulaması kullanılabilirliğini önemli ölçüde artırabilir. Daha fazla bilgi için bkz: [Şerit](http://go.microsoft.com/fwlink/p/?linkid=129233). Aşağıdaki çizimde bir Şerit gösterir.  
  
 ![MFC Şeridi kaynak denetimi](../mfc/media/ribbon_no_callouts.png "ribbon_no_callouts")  
  
 Visual Studio'nun önceki sürümleri Şerit gibi MFC Şerit sınıfları kullanan kodu yazarak oluşturulması gerekiyordu [CMFCRibbonBar sınıfı](../mfc/reference/cmfcribbonbar-class.md). İçinde [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)], Şerit Tasarımcısı Şerit oluşturmak için alternatif bir yöntem sağlar. İlk olarak, oluşturabilir ve bir kaynak olarak Şerit özelleştirebilirsiniz. MFC uygulaması koddan sonra Şerit kaynağı yükleyin. Hatta Şerit kaynakları ve MFC Şerit sınıfları birlikte kullanabilirsiniz. Örneğin, bir Şerit kaynağı oluşturun ve ardından program aracılığıyla daha fazla öğe çalışma zamanında kod kullanarak ekleyin.  
  
## <a name="understanding-the-ribbon-designer"></a>Şerit Tasarımcısı anlama  
 Şerit Tasarımcısı oluşturur ve Şerit bir kaynak olarak depolar. Şerit Tasarımcısı Şerit kaynağı oluşturduğunuzda, bu üç şey yapar:  
  
-   Proje kaynak tanımı komut dosyasında bir girdi ekler (* .rc). Aşağıdaki örnekte, `IDR_RIBBON` Şerit kaynağı tanımlayan benzersiz bir ad olduğundan `RT_RIBBON_XML` kaynak türü ve `ribbon.mfcribbon-ms` kaynak dosyasının adıdır.  
  
 ```  
    IDR_RIBBON RT_RIBBON_XML      "res\\ribbon.mfcribbon-ms"  
 ```  
  
-   Komut kimlikleri tanımları için resource.h ekler.  
  
 ```  
 #define IDR_RIBBON            307  
 ```  
  
-   Şeridin düğme, denetimleri ve özniteliklerini tanımlayan XML kodunu içeren bir Şerit kaynak dosyası (*.mfcribbon-ms) oluşturur. Şerit Tasarımcısı Şeritte değişiklikler XML olarak kaynak dosyasında depolanır. Aşağıdaki kod örneğinde içeriğini parçası gösterir bir \*.mfcribbon ms dosyası:  
  
 ```  
 <RIBBON_BAR>  
 <ELEMENT_NAME>RibbonBar</ELEMENT_NAME>  
 <IMAGE>  
 <ID>  
 <NAME>IDB_BUTTONS</NAME>  
 <VALUE>113</VALUE>  
 </ID>   
 ```  
  
 MFC uygulamanızda Şerit kaynağı kullanmak için kaynak çağırarak yük [CMFCRibbonBar::LoadFromResource](../mfc/reference/cmfcribbonbar-class.md#loadfromresource).  
  
## <a name="creating-a-ribbon-by-using-the-ribbon-designer"></a>Şerit Tasarımcısını kullanarak bir Şerit oluşturma  
 Şerit kaynağına MFC projenize eklemek için iki yol şunlardır:  
  
-   MFC uygulaması oluşturma ve Şerit oluşturmak için MFC projesi Sihirbazı'nı yapılandırın. Daha fazla bilgi için bkz: [izlenecek yol: bir Şerit uygulaması tarafından kullanarak MFC oluşturma](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md).  
  
-   Varolan bir MFC projesine bir Şerit kaynağı oluşturun ve yükleyin. Daha fazla bilgi için bkz: [izlenecek yol: MFC karalama uygulamasını (Kısım 1) güncelleştirme](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md).  
  
 MFC projenize el ile kodlanmış bir Şerit zaten varsa, varolan Şerit Şerit kaynağına dönüştürme için kullanabileceğiniz işlevleri vardır. Daha fazla bilgi için bkz: [nasıl yapılır: varolan bir MFC şeridini Şerit kaynağına dönüştürme](../mfc/how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource.md).  
  
> [!NOTE]
>  Şerit iletişim tabanlı uygulamalarda oluşturulamıyor. Daha fazla bilgi için bkz: [uygulama türü, MFC Uygulama Sihirbazı'nı](../mfc/reference/application-type-mfc-application-wizard.md).  
  
## <a name="customizing-ribbons"></a>Şerit özelleştirme  
 Şerit Şerit Tasarımcısı'nda, kaynak görünümünde Şerit kaynağı çift tıklatarak açın. Tasarımcısı'nda ekleyin, kaldırın ve Şerit, uygulama düğmesini veya hızlı erişim araç çubuğu üzerinde öğeleri özelleştirebilirsiniz. Yöntemi, uygulamanızda olayları, örneğin, düğme tıklama olaylarını ve menü olaylarını bağlayabilirsiniz.  
  
 Aşağıdaki çizimde, çeşitli bileşenler Şerit Tasarımcısı'nda gösterir.  
  
 ![MFC Şerit Tasarımcısı](../mfc/media/ribbon_designer.png "ribbon_designer")  
  
- **Araç kutusu:** Tasarımcı yüzeyine sürüklenebilir denetimleri içerir.  
  
- **Tasarımcı yüzeyine:** Şerit kaynağı görsel gösterimi içeriyor.  
  
- **Özellikler penceresi:** Tasarımcı yüzeyine seçili öğenin özniteliklerini listeler.  
  
- **Kaynak Görünümü penceresi:** Şerit kaynakları projenize dahil kaynakları görüntüler.  
  
- **Şerit Düzenleyicisi araç:** sağlayan komutlar içerir Şerit Önizleme ve görsel temasını değiştirin.  
  
 Aşağıdaki konular, Şerit Tasarımcısı'nda özellikleri kullanmak açıklanmaktadır:  
  
- [Nasıl yapılır: Uygulama Düğmesini Özelleştirme](../mfc/how-to-customize-the-application-button.md)  
  
- [Nasıl yapılır: Hızlı Erişim Araç Çubuğunu Özelleştirme](../mfc/how-to-customize-the-quick-access-toolbar.md)  
  
- [Nasıl yapılır: Şerit Denetimleri ve Olay İşleyicileri Ekleme](../mfc/how-to-add-ribbon-controls-and-event-handlers.md)  
  
- [Nasıl yapılır: Bir MFC Uygulamasından Şerit Kaynağı Yükleme](../mfc/how-to-load-a-ribbon-resource-from-an-mfc-application.md)  
  
## <a name="definitions-of-ribbon-elements"></a>Şerit öğelerinin tanımları  
 ![MFC Şerit](../mfc/media/ribbon.png "Şerit")  
  
- **Uygulama düğmesi:** Şerit sol üst köşesinde görüntülenen düğmeyi. Uygulama düğmesi Dosya menüsü yerini alır ve hatta Şeriti simge durumuna küçültülmüş görülebilir. Düğme tıklatıldığında komutların listesini içeren bir menüsü görüntülenir.  
  
- **Hızlı Erişim Araç çubuğu:** sık görüntüler küçük, özelleştirilebilir bir araç kullanılan komutları.  
  
- **Kategori**: Şerit sekmesi içeriğini temsil eden mantıksal gruplandırma.  
  
- **Kategori varsayılan düğme:** Şeriti simge durumundayken Şeritte görünen düğmesine. Düğme tıklatıldığında kategori menü olarak görüntülenir.  
  
- **Pano:** ilgili denetimleri bir grup görüntüler Şerit çubuğu alanı. Bir veya daha fazla Şerit paneller her Şerit kategorisi içerir.  
  
- **Şerit öğeleri:** denetimlerini paneller, örneğin, düğmeler ve birleşik giriş kutuları. Şerit'te barındırılabilir çeşitli denetimleri görmek için bkz [RibbonGadgets örnek: Şerit araçları uygulama](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)   
 [Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)

