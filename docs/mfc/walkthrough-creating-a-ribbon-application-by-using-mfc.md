---
title: 'İzlenecek yol: MFC kullanarak şerit uygulaması oluşturma'
ms.date: 09/09/2019
helpviewer_keywords:
- ribbon application, creating (MFC)
- creating a ribbon aplication (MFC)
ms.assetid: e61393e2-1d6b-4594-a7ce-157d3d1b0d9f
ms.openlocfilehash: 41084a78287521610ba400deab32d1052c9217c1
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907388"
---
# <a name="walkthrough-creating-a-ribbon-application-by-using-mfc"></a>İzlenecek yol: MFC kullanarak şerit uygulaması oluşturma

Bu izlenecek yol, varsayılan olarak şerit içeren bir uygulama oluşturmak için **MFC Uygulama Sihirbazı** ' nın nasıl kullanılacağını gösterir. Daha sonra, bir **Sık Kullanılanlar** şerit paneline sahip **özel** bir Şerit kategorisi ekleyerek ve ardından panele bazı sık kullanılan komutları ekleyerek şeridi genişletebilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yol, Visual Studio 'Yu **genel geliştirme ayarlarını**kullanacak şekilde ayarlamış olduğunuzu varsayar. Farklı ayarlar kullanıyorsanız, aşağıdaki yönergelerde başvurulan kullanıcı arabirimi (UI) öğelerinden bazıları görüntülenmeyebilir.

### <a name="to-create-an-mfc-application-that-has-a-ribbon"></a>Şeridi olan bir MFC uygulaması oluşturmak için

1. Bir şeridi olan bir MFC uygulaması oluşturmak için **MFC Uygulama Sihirbazı** ' nı kullanın. Bkz [. İzlenecek yol: Visual Studio sürümünüz için sihirbazın nasıl](walkthrough-using-the-new-mfc-shell-controls.md) açılacağı hakkında yönergeler için yeni MFC kabuk denetimlerini kullanma.

1. **MFC Uygulama Sihirbazı**'nda aşağıdaki seçenekleri ayarlayın:

    1. **Uygulama türü** bölümünde, **görsel stil ve renkler**altında **Office 2007 (mavi tema)** seçeneğini belirleyin.

    1. **Birleşik belge desteği** bölümünde, **hiçbirinin** seçili olmadığından emin olun.

    1. **Belge şablonu özellikleri** bölümünde, **Dosya Uzantısı** kutusunda, bu uygulamanın oluşturduğu belgeler için bir dosya adı uzantısı yazın; örneğin, *mfcrbnapp*.

    1. **Veritabanı desteği** bölümünde (yalnızca Visual Studio 2015), **hiçbirinin** seçili olmadığından emin olun.

    1. **Kullanıcı arabirimi özellikleri** bölümünde, **bir şerit kullan** ' ın seçili olduğundan emin olun.

    1. Varsayılan olarak, **MFC Uygulama Sihirbazı** birkaç yerleştirme bölmesi için destek ekler. Bu kılavuz sadece şerit hakkında bilgi verdiğinden bu seçenekleri uygulamadan kaldırabilirsiniz. **Gelişmiş Özellikler** bölümünde tüm seçenekler ' i temizleyin.

1. MFC uygulamasını oluşturmak için **son** ' a tıklayın.

1. Uygulamanın başarıyla oluşturulduğunu doğrulamak için derleyin ve çalıştırın. Uygulamayı derlemek için, **Yapı** menüsünde **çözüm oluştur**' a tıklayın. Uygulama başarıyla yapılandığında **hata ayıklama** menüsünde **hata ayıklamayı Başlat** ' a tıklayarak çalıştırın.

    Sihirbaz, **giriş**adlı bir şerit kategorisine sahip bir şeridi otomatik olarak oluşturur. Bu şerit, **Pano**, **Görünüm**ve **pencere**olarak adlandırılan üç şerit paneli içerir.

### <a name="to-add-a-category-and-panel-to-the-ribbon"></a>Şerite kategori ve panel eklemek için

1. Sihirbazın oluşturduğu Şerit kaynağını açmak için, **Görünüm** menüsünde **diğer pencereler** ' in üzerine gelin ve **kaynak görünümü**' ye tıklayın. **Kaynak görünümü**, **Şerit** ' e tıklayın ve ardından **IDR_RIBBON**öğesine çift tıklayın.

1. İlk olarak, **araç kutusunda** **Kategori** ' ye çift tıklayarak Şerite özel bir kategori ekleyin.

    **Kategori1 & lt** açıklamalı alt yazısının bulunduğu bir kategori oluşturulur. Varsayılan olarak, kategori tek bir panel içerir.

    **Kategori1 & lt** öğesine sağ tıklayın ve ardından **Özellikler**' e tıklayın. **Özellikler** penceresinde, **başlığı** *özel*' e değiştirin.

    **Büyük görüntüler** ve **küçük görüntüler** özellikleri, bu kategorideki Şerit öğeleri için simge olarak kullanılan bit eşlemleri belirtir. Özel bit eşlemler oluşturma bu yönerge kapsamının dışında olduğundan, basitçe sihirbaz tarafından oluşturulan bit eşlemleri yeniden kullanın. Küçük bit eşlemler 16x16 pikseldir. Küçük görüntüler için, `IDB_FILESMALL` kaynak kimliği tarafından erişilen bit eşlemler kullanın. Büyük bit eşlemler 32x32 pikseldir. Büyük görüntüler için `IDB_FILELARGE` kaynak kimliği tarafından erişilen bit eşlemler kullanın.

    > [!NOTE]
    > Yüksek nokta/inç (HDPI) ekranlarda otomatik olarak görüntülerin HDPI sürümleri kullanılır.

1. Ardından, paneli özelleştirin. Paneller birbirlerine mantıksal olarak ilişkili öğeleri gruplandırmak için kullanılır. Örneğin, bu uygulamanın **giriş** sekmesinde **Kes**, **Kopyala**ve **Yapıştır** komutlarının hepsi **Pano** panelinde bulunur. Paneli özelleştirmek için **Panel1** öğesine sağ tıklayın ve ardından **Özellikler**' e tıklayın. **Özellikler** penceresinde, **başlık yazısını** *Sık Kullanılanlar*' a değiştirin.

    Panelin **görüntü dizinini** belirtebilirsiniz. Bu sayı, şerit paneli **hızlı erişim araç çubuğuna**eklenirse görüntülenen simgeyi belirtir. Simge, şerit panelinin kendisi üzerinde gösterilmez.

1. Şerit kategorisi ve panelin başarılı bir şekilde oluşturulduğunu doğrulamak için şerit denetiminin önizlemesini görüntüleyin. **Şerit Düzenleyicisi araç çubuğunda**, **test şeridi** düğmesine tıklayın. Şeritte **özel** bir sekme ve **Sık Kullanılanlar** paneli görüntülenmelidir.

### <a name="to-add-elements-to-the-ribbon-panels"></a>Şerit panele öğe eklemek için

1. Önceki yordamda oluşturduğunuz panele öğe eklemek için, denetimleri **araç kutusunun** **Şerit Düzenleyicisi** bölümünden Tasarım görünümündeki panele sürükleyin.

1. İlk olarak, bir **Yazdır** düğmesi ekleyin. **Yazdır** düğmesi varsayılan yazıcıyı kullanarak yazdıran bir **Hızlı Yazdır** komutu içeren bir alt menüye sahip olur. Bu komutların ikisi de bu uygulama için tanımlanmış durumdadır. Bunlar uygulama menüsünde bulunur.

    **Yazdır** düğmesini oluşturmak için düğme aracını panele sürükleyin.

    **Özellikler** penceresinde, **kimlik** özelliğini önceden tanımlanmış olması gereken **ID_FILE_PRINT**olarak değiştirin. **Başlığı** *yazdırılacak*şekilde değiştirin. **Görüntü dizinini** *4*olarak değiştirin.

    **Hızlı Yazdır** düğmesini oluşturmak Için, **menü öğeleri**' nin yanındaki Özellik değeri sütununa tıklayın ve ardından üç nokta ( **...** ) simgesine tıklayın. **Öğe düzenleyicisinde**, bir menü öğesi oluşturmak Için etiketsiz **Ekle** düğmesine tıklayın. **Özellikler** penceresinde, **üst yazı başlığını** *Hızlı Yazdır*, **kimlik** - *ID_FILE_PRINT_DIRECT*ve **resim** olarak *5*' e değiştirin. Image özelliği, `IDB_FILESMALL` bit eşlem kaynağındaki **Hızlı Yazdır** simgesini belirtir.

1. Düğmelerin şerit paneline eklendiğini doğrulamak için uygulamayı derleyin ve çalıştırın. Uygulamayı derlemek için, **Yapı** menüsünde **çözüm oluştur**' a tıklayın. Uygulama başarıyla yapılandığında **hata ayıklama** menüsünde **hata ayıklamayı Başlat** ' a tıklayarak uygulamayı çalıştırın. Şeritte **özel** sekmesindeki **Sık Kullanılanlar** panelinde bulunan **Yazdır** düğmesi ve Birleşik giriş kutusu görüntülenmelidir.

## <a name="next-steps"></a>Sonraki Adımlar

[Nasıl yapılır: Hızlı Erişim Araç Çubuğunu Özelleştirme](../mfc/how-to-customize-the-quick-access-toolbar.md)

[Nasıl yapılır: Uygulama Düğmesini Özelleştirme](../mfc/how-to-customize-the-application-button.md)

Uçtan uca örnekler için bkz. [örnekler (MFC özellik paketi)](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)<br/>
[Örnekler (MFC özellik paketi)](../overview/visual-cpp-samples.md)
