---
title: 'İzlenecek yol: MFC kullanarak Şerit uygulaması oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon application, creating (MFC)
- creating a ribbon aplication (MFC)
ms.assetid: e61393e2-1d6b-4594-a7ce-157d3d1b0d9f
ms.openlocfilehash: 29991a389a09e1fe3dc0074b80fd9a255458f673
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781230"
---
# <a name="walkthrough-creating-a-ribbon-application-by-using-mfc"></a>İzlenecek yol: MFC kullanarak Şerit uygulaması oluşturma

Bu izlenecek yolda nasıl kullanılacağını gösterir **MFC Uygulama Sihirbazı** varsayılan olarak şeridi olan bir uygulama oluşturmak için. Ardından, ekleyerek Şerit genişletebilirsiniz bir **özel** sahip Şerit kategorisi bir **Sık Kullanılanlar** Şerit paneli ve ardından bazı sık kullanılan komutları panele ekleyerek.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yol, Visual Studio'yu kullanın belirlediğinizi varsayar **genel geliştirme ayarları**. Farklı ayarlar kullanıyorsanız aşağıdaki yönergelerde başvurulan kullanıcı arabirimi (UI) öğelerinin bazılarını görüntüleyemiyor olabilirsiniz.

### <a name="to-create-an-mfc-application-that-has-a-ribbon"></a>Şeridi olan bir MFC uygulaması oluşturmak için

1. Kullanım **MFC Uygulama Sihirbazı** şeridi olan bir MFC uygulaması oluşturmak için. Sihirbazı çalıştırmak için **dosya** menüsünde **yeni**ve ardından **proje**.

1. İçinde **yeni proje** iletişim kutusunda **Visual C++** düğümünde **yüklü şablonlar**seçin **MFC**ve ardından seçin **MFC uygulaması**. Proje için bir ad yazın örneğin, *MFCRibbonApp*ve ardından **Tamam**.

1. Aşağıdaki seçenekler kümesinde **MFC Uygulama Sihirbazı**:

    1. İçinde **uygulama türü** bölümündeki **görsel stil ve renkler**seçin **Office 2007 (mavi tema)**.

    1. İçinde **bileşik belge desteği** bölümünde, emin **hiçbiri** seçilir.

    1. İçinde **belge şablonu özellikleri** bölümünde **dosya uzantısı** bu uygulamayı oluşturur, örneğin, belgeler için bir dosya adı uzantısı yazın *mfcrbnapp*.

    1. İçinde **veritabanı desteği** bölümünde, emin **hiçbiri** seçilir.

    1. İçinde **kullanıcı arabirimi özellikleri** bölümünde, emin **bir Şerit** seçilir.

    1. Varsayılan olarak, **MFC Uygulama Sihirbazı** birkaç takma bölme için destek ekler. Bu kılavuz sadece şerit hakkında bilgi verdiğinden bu seçenekleri uygulamadan kaldırabilirsiniz. İçinde **Gelişmiş Özellikler** bölümünde, tüm seçenekleri temizleyin.

1. Tıklayın **son** MFC uygulaması oluşturmak için.

1. Uygulamanın başarıyla oluşturulduğunu doğrulamak için derleyin ve çalıştırın. Uygulama derlemek için **derleme** menüsünde tıklatın **Çözümü Derle**. Uygulama başarıyla derlenirse tıklatarak **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menüsü.

    Sihirbaz otomatik olarak adlandırılan bir Şerit kategorisine sahip bir Şerit oluşturur **giriş**. Bu Şerit adlandırılan üç Şerit paneli içerir **Pano**, **görünümü**, ve **penceresi**.

### <a name="to-add-a-category-and-panel-to-the-ribbon"></a>Şerite kategori ve panel eklemek için

1. Sihirbazın oluşturduğu Şerit kaynağını açmak için **görünümü** menüsünde **diğer Windows** ve ardından **kaynak görünümü**. İçinde **kaynak görünümü**, tıklayın **Şerit** ve çift tıklatarak **ıdr_rıbbon**.

1. İlk olarak, özel bir kategori çift tıklayarak Şeride ekleyin **kategori** içinde **araç kutusu**.

    Resim yazısını bir kategori **Kategori1** oluşturulur. Varsayılan olarak, kategori tek bir panel içerir.

    Sağ **Kategori1** ve ardından **özellikleri**. İçinde **özellikleri** penceresinde değişiklik **açıklamalı alt yazı** için *özel*.

    **Büyük resimler** ve **küçük resimler** özellikleri bu kategorideki Şerit öğeleri için simgeler olarak kullanılan bit eşlemleri belirtir. Özel bit eşlemler oluşturma bu yönerge kapsamının dışında olduğundan, basitçe sihirbaz tarafından oluşturulan bit eşlemleri yeniden kullanın. Küçük bit eşlemler 16x16 pikseldir. Küçük resimler için tarafından erişilen bit eşlemler kullanın. `IDB_FILESMALL` kaynak kimliği. Büyük bit eşlemler 32x32 pikseldir. Büyük resimler için tarafından erişilen bit eşlemler kullanın. `IDB_FILELARGE` kaynak kimliği.

    > [!NOTE]
    > Yüksek nokta/inç (HDPI) ekranlarda otomatik olarak görüntülerin HDPI sürümleri kullanılır.

1. Ardından, paneli özelleştirin. Paneller birbirlerine mantıksal olarak ilişkili öğeleri gruplandırmak için kullanılır. Örneğin, **giriş** bu uygulama için sekmesinde **Kes**, **kopyalama**, ve **Yapıştır** komutları tüm bulunur  **Pano** paneli. Paneli özelleştirmek için sağ **Panel1** ve ardından **özellikleri**. İçinde **özellikleri** penceresinde değişiklik **açıklamalı alt yazı** için *Sık Kullanılanlar*.

    Belirtebileceğiniz **görüntü dizini** panelinin. Bu Şerit panel eklenirse görüntülenen simgeyi belirtir **hızlı erişim araç çubuğu**. Simgenin kendisi Şerit panelinde görüntülenmez.

1. Şerit kategorisi ve panelin başarılı bir şekilde oluşturulduğunu doğrulamak için şerit denetiminin önizlemesini görüntüleyin. Üzerinde **Şerit Düzenleyici araç çubuğu**, tıklayın **şeridi Sına** düğmesi. A **özel** sekmesi ve **Sık Kullanılanlar** paneli Şerit üzerinde görüntülenecektir.

### <a name="to-add-elements-to-the-ribbon-panels"></a>Şerit panele öğe eklemek için

1. Önceki yordamda oluşturduğunuz panele öğe eklemek için denetimleri sürükleyin **Şerit düzenleyici** bölümünü **araç kutusu** Tasarım görünümünde paneline.

1. İlk olarak, ekleme bir **yazdırma** düğmesi. **Yazdırma** düğmesini içeren bir alt menüye sahip olacak bir **Hızlı Yazdır** varsayılan yazıcıyı kullanarak yazdıran komutu. Bu komutların ikisi de bu uygulama için tanımlanmış durumdadır. Bunlar, uygulama menüsünde yer.

    Oluşturulacak **yazdırma** düğmesi, bir düğme aracını panele sürükleyin.

    İçinde **özellikleri** penceresinde değişiklik **kimliği** özelliğini **ıd_fıle_prınt**, hangi önceden tanımlanmış olması. Değişiklik **açıklamalı alt yazı** için *yazdırma*. Değişiklik **görüntü dizini** için *4*.

    Oluşturulacak **Hızlı Yazdır** düğme, özellik değer sütununa tıklayın **menü öğeleri**ve ardından üç nokta simgesine tıklayın (**...** ). İçinde **öğe düzenleyici**, etiketsiz tıklayın **Ekle** menü öğesi oluşturmak için. İçinde **özellikleri** penceresinde değişiklik **açıklamalı alt yazı** için *Hızlı Yazdır*, **kimliği** için *ID_FILE_PRINT_DIRECT*, ve **görüntü** için *5*. Resim özelliği belirtir **Hızlı Yazdır** simgesini `IDB_FILESMALL` kaynak bit eşlem.

1. Düğmelerin şerit paneline eklendiğini doğrulamak için uygulamayı derleyin ve çalıştırın. Uygulama derlemek için **derleme** menüsünde tıklatın **Çözümü Derle**. Uygulama başarıyla derlenirse tıklayarak uygulamayı çalıştırmak **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menüsü. **Yazdırma** düğmesi ve birleşik giriş kutusu **Sık Kullanılanlar** üzerinde panelinde **özel** Şerit sekmesinde görüntülenmesi gerekir.

## <a name="next-steps"></a>Sonraki Adımlar

[Nasıl yapılır: Hızlı Erişim Araç çubuğunu özelleştirme](../mfc/how-to-customize-the-quick-access-toolbar.md)

[Nasıl yapılır: Uygulama düğmesini özelleştirme](../mfc/how-to-customize-the-application-button.md)

Uçtan uca örnekler için bkz: [örnekler (MFC özellik paketi)](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)<br/>
[Örnekler (MFC özellik paketi)](../overview/visual-cpp-samples.md)
