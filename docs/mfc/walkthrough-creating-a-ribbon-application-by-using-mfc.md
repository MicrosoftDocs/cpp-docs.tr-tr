---
title: "İzlenecek yol: MFC kullanarak Şerit uygulaması oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ribbon application, creating (MFC)
- creating a ribbon aplication (MFC)
ms.assetid: e61393e2-1d6b-4594-a7ce-157d3d1b0d9f
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bfad78b64f72b9ee9a896832e008039aa241e2ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-creating-a-ribbon-application-by-using-mfc"></a>İzlenecek yol: MFC Kullanarak Şerit Uygulaması Oluşturma
Bu kılavuzda nasıl kullanılacağını gösterir **MFC Uygulama Sihirbazı'nı** Şerit varsayılan olan bir uygulama oluşturmak için. Sonra ekleyerek Şerit genişletebilirsiniz bir **özel** sahip Şerit kategori bir **Sık Kullanılanlar** Şerit paneli ve bazı sık kullanılan komutlar paneline ekleme.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuz, ayarladığınız varsayar [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] kullanmak için **genel geliştirme ayarları**. Farklı ayarlar kullanıyorsanız aşağıdaki yönergelerde başvurulan kullanıcı arabirimi (UI) öğelerinin bazılarını görüntüleyemiyor olabilirsiniz. Ayarları değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: ayarlarınızı sıfırlayın](http://msdn.microsoft.com/en-us/c95c51be-e609-4769-abba-65e6beedec76).  
  
### <a name="to-create-an-mfc-application-that-has-a-ribbon"></a>Şeridi olan bir MFC uygulaması oluşturmak için  
  
1.  Kullanım **MFC Uygulama Sihirbazı'nı** Şerit sahip bir MFC uygulaması oluşturmak için. Sihirbazı'nı çalışma **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C++** düğümü altında **yüklü şablonlar**seçin **MFC**ve ardından seçin **MFC Uygulama**. Proje için bir ad yazın, örneğin, `MFCRibbonApp`ve ardından **Tamam**.  
  
3.  İlk sayfasında **MFC Uygulama Sihirbazı'nı**, tıklatın **sonraki**.  
  
4.  Üzerinde **uygulama türü** sayfasında **görsel stil ve renkleri**seçin **Office 2007 (mavi tema)**. Diğer ayarları olduğu gibi bırakın. **İleri**'ye tıklayın.  
  
5.  Üzerinde **bileşik belge desteği** sayfasında, olduğundan emin olun **hiçbiri** seçilir ve ardından **sonraki**.  
  
6.  Üzerinde **belge şablonu özellikleri** sayfasında **dosya uzantısı** kutusuna, bu uygulama oluşturur, örneğin, belgeler için bir dosya adı uzantısı yazın `mfcrbnapp`. **İleri**'ye tıklayın.  
  
7.  Üzerinde **veritabanı desteği** sayfasında, olduğundan emin olun **hiçbiri** seçilir ve ardından **sonraki**.  
  
8.  Üzerinde **kullanıcı arabirimi özellikleri** sayfasında, olduğundan emin olun **Şerit kullanmak** seçilir. **İleri**'ye tıklayın.  
  
9. Varsayılan olarak, **MFC Uygulama Sihirbazı'nı** birkaç yerleşik bölmeleri için destek ekler. Bu kılavuz sadece şerit hakkında bilgi verdiğinden bu seçenekleri uygulamadan kaldırabilirsiniz. Üzerinde **Gelişmiş Özellikler** sayfasında, tüm seçeneklerini temizleyin. **İleri**'ye tıklayın.  
  
10. Üzerinde **oluşturulan sınıflar** sayfasında, **son** MFC uygulaması oluşturmak için.  
  
11. Uygulamanın başarıyla oluşturulduğunu doğrulamak için derleyin ve çalıştırın. Uygulama üzerinde oluşturmak için **yapı** menüsünde tıklatın **yapı çözümü**. Uygulama başarıyla oluşturursa çalıştırın tıklayarak **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menüsü.  
  
     Adlı bir Şerit kategorinin bir Şerit sihirbaz otomatik olarak **giriş**. Bu Şerit adlandırıldığı üç Şerit paneller içeren **Pano**, **Görünüm**, ve **penceresi**.  
  
### <a name="to-add-a-category-and-panel-to-the-ribbon"></a>Şerite kategori ve panel eklemek için  
  
1.  Sihirbaz oluşturulan, üzerinde Şerit kaynağı açmaya **Görünüm** menüsündeki **diğer pencereler** ve ardından **kaynak görünümü**. İçinde **kaynak görünümü**, tıklatın **Şerit** çift tıklayın ve ardından **IDR_RIBBON**.  
  
2.  Önce özel bir kategori Şerit'e çift tıklayarak ekleyin. **kategori** içinde **araç**.  
  
     Başlık bir kategori **Kategori1** oluşturulur. Varsayılan olarak, kategori tek bir panel içerir.  
  
     Sağ **Kategori1** ve ardından **özellikleri**. İçinde **özellikleri** penceresinde, değişiklik **resim yazısı** için `Custom`.  
  
     **Görüntülerin büyük** ve **küçük resimler** özellikleri simgelerle bu kategorideki Şerit öğeleri için kullanılan bit eşlemler belirtin. Özel bit eşlemler oluşturma bu yönerge kapsamının dışında olduğundan, basitçe sihirbaz tarafından oluşturulan bit eşlemleri yeniden kullanın. Küçük bit eşlemler 16x16 pikseldir. Küçük resimler için IDB_FILESMALL kaynak kimliği ile erişilen bit eşlemler kullanın. Büyük bit eşlemler 32x32 pikseldir. Büyük resimler için IDB_FILELARGE kaynak kimliği ile erişilen bit eşlemler kullanın.  
  
    > [!NOTE]
    >  Yüksek nokta/inç (HDPI) ekranlarda otomatik olarak görüntülerin HDPI sürümleri kullanılır.  
  
3.  Ardından, paneli özelleştirin. Paneller birbirlerine mantıksal olarak ilişkili öğeleri gruplandırmak için kullanılır. Örneğin, **giriş** sekme, bu uygulamanın **Kes**, **kopya**, ve **Yapıştır** komutları tüm bulunur  **Pano** paneli. Bölmenin özelleştirmek için sağ **Panel1** ve ardından **özellikleri**. İçinde **özellikleri** penceresinde, değişiklik **resim yazısı** için `Favorites`.  
  
     Belirleyebileceğiniz **görüntü dizini** bölmesinin. Şerit paneli eklenirse, görüntülenen simge bu numarayı belirtir **hızlı erişim araç çubuğu**. Simgenin kendisi şerit panelinde görüntülenmez.  
  
4.  Şerit kategorisi ve panelin başarılı bir şekilde oluşturulduğunu doğrulamak için şerit denetiminin önizlemesini görüntüleyin. Üzerinde **Şerit Düzenleyicisi araç**, tıklatın **Test Şerit** düğmesi. A **özel** sekmesi ve **Sık Kullanılanlar** Masası Şerit'te görüntülenmesi.  
  
### <a name="to-add-elements-to-the-ribbon-panels"></a>Şerit panele öğe eklemek için  
  
1.  Önceki yordamda oluşturduğunuz panel öğeleri eklemek için denetimlerden sürükleyin **Şerit Düzenleyicisi** bölümünü **araç** Tasarım görünümünde paneline.  
  
2.  İlk olarak, ekleyin bir **yazdırma** düğmesi. **Yazdırma** düğmesi içeren bir alt sahip olacak bir **Hızlı Yazdır** varsayılan yazıcıyı kullanarak yazdırır komutu. Bu komutların ikisi de bu uygulama için tanımlanmış durumdadır. Uygulama menüsünde yer alırlar.  
  
     Oluşturmak için **yazdırma** düğmesini tıklatın, bir düğme aracını paneline sürükleyin.  
  
     İçinde **özellikleri** penceresinde, değişiklik **kimliği** özelliğine **ıd_fıle_prınt**, hangi zaten tanımlanmalıdır. Değişiklik **resim yazısı** için `Print`. Değişiklik **görüntü dizini** için `4`.  
  
     Oluşturmak için **hızlı yazdırma** düğmesini tıklatın, özellik değeri sütununu tıklayın **menü öğeleri**ve ardından üç nokta (**...** ). İçinde **öğeleri Düzenleyicisi**, etiketlenmemiş tıklatın **Ekle** menü öğesi oluşturmak için düğmesini. İçinde **özellikleri** penceresinde, değişiklik **resim yazısı** için `Quick Print`, **kimliği** için `ID_FILE_PRINT_DIRECT`, ve **görüntü** için `5` . Resim özelliği IDB_FILESMALL bit eşlem kaynağındaki Hızlı Yazdır simgesini belirtir.  
  
3.  Düğmelerin şerit paneline eklendiğini doğrulamak için uygulamayı derleyin ve çalıştırın. Uygulama üzerinde oluşturmak için **yapı** menüsünde tıklatın **yapı çözümü**. Uygulama başarıyla oluşturursa tıklayarak uygulamayı çalıştırın **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menüsü. **Yazdırma** düğmesi ve birleşik giriş kutusu üzerinde **Sık Kullanılanlar** üzerinde panel **özel** Şeritteki sekmenin görüntülenmesi.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 [Nasıl yapılır: Hızlı Erişim Araç Çubuğunu Özelleştirme](../mfc/how-to-customize-the-quick-access-toolbar.md)  
  
 [Nasıl yapılır: Uygulama Düğmesini Özelleştirme](../mfc/how-to-customize-the-application-button.md)  
  
 Uçtan uca örnekler için bkz: [örnekler (MFC özellik paketi)](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yollar](../mfc/walkthroughs-mfc.md)   
 [Örnekler (MFC özellik paketi)](../visual-cpp-samples.md)

