---
title: 'MFC ActiveX Denetimleri: Başka Bir Özel Özellik Sayfası Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
ms.openlocfilehash: 02c87c2c5283b7293c2a7ab028ec9a2abbba2b33
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364736"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX Denetimleri: Başka Bir Özel Özellik Sayfası Ekleme

Bazen, ActiveX denetimi bir özellik sayfasına sığabilecekten daha fazla özelliğe sahip olur. Bu durumda, bu özellikleri görüntülemek için ActiveX denetimine özellik sayfaları ekleyebilirsiniz.

Bu makalede, zaten en az bir özellik sayfası olan activex denetimine yeni özellik sayfaları eklenmesi açıklanmıştır. Stok özelliği sayfaları (yazı tipi, resim veya renk) ekleme hakkında daha fazla bilgi için [MFC ActiveX Denetimleri makalesine bakın: Stok Özelliği Sayfalarını kullanma.](../mfc/mfc-activex-controls-using-stock-property-pages.md)

Aşağıdaki yordamlar ActiveX Denetim Sihirbazı tarafından oluşturulan örnek ActiveX denetim çerçevesi kullanır. Bu nedenle, sınıf adları ve tanımlayıcıları bu örneğe özgütür.

ActiveX denetiminde özellik sayfalarını kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [MFC ActiveX Denetimleri: Özellik Sayfaları](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)

    > [!NOTE]
    >  Yeni özellik sayfalarının ActiveX denetim özelliği sayfaları için boyut standardına uyması önerilir. Stok resmi ve renk özelliği sayfaları 250x62 iletişim birimlerini (DLU) ölçer. Standart yazı tipi özelliği sayfası 250x110 DLUs'dur. ActiveX Denetim Sihirbazı tarafından oluşturulan varsayılan özellik sayfası 250x62 DLU standardını kullanır.

### <a name="to-insert-a-new-property-page-template-into-your-project"></a>Projenize yeni bir özellik sayfası şablonu eklemek için

1. Denetim projeniz açıkken, proje çalışma alanında Kaynak Görünümü'ni açın.

1. Kısayol menüsünü açmak için Kaynak Görünümü'nde sağ tıklatın ve **Kaynak Ekle'yi**tıklatın.

1. **İletişim** düğümünü genişletin ve **IDD_OLE_PROPPAGE_SMALL'ı**seçin.

1. Projenize kaynak eklemek için **Yeni'yi** tıklatın.

1. **Özellikler** penceresini yenilemek için yeni özellik sayfası şablonunu seçin **(Kaynak**Görünümü'nde).

1. **Kimlik** özelliği için yeni bir değer girin. Bu örnekte **IDD_PROPPAGE_NEWPAGE.**

1. Araç çubuğunda **Kaydet** seçeneğine tıklayın.

### <a name="to-associate-the-new-template-with-a-class"></a>Yeni şablonu bir sınıfla ilişkilendirmek için

1. Sınıf Görünümünü Aç.

1. Kısayol menüsünü açmak için Sınıf Görünümü'nde sağ tıklatın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Sınıf Ekle'yi**tıklatın.

   Bu, [Sınıf Ekle](../ide/add-class-dialog-box.md) iletişim kutusunu açar.

1. **MFC Sınıfı** şablonuna çift tıklayın.

1. [MFC Sınıf Sihirbazı'ndaki](../mfc/reference/mfc-add-class-wizard.md) **Sınıf Adı** kutusunda, yeni iletişim sınıfı için bir ad yazın. (Bu örnekte, `CAddtlPropPage`.)

1. Dosya adlarını değiştirmek istiyorsanız **Değiştir'i**tıklatın. Uygulama ve üstbilgi dosyalarınızın adlarını yazın veya varsayılan adları kabul edin.

1. Taban **Sınıf** kutusunda. `COlePropertyPage`

1. İletişim **Kimliği** kutusunda **IDD_PROPPAGE_NEWPAGE'** yi seçin.

1. Sınıfı oluşturmak için **Bitir'i** tıklatın.

Denetim kullanıcılarının bu yeni özellik sayfasına erişmesine izin vermek için, denetimin özellik sayfası dIs makro bölümünde (denetim uygulama dosyasında bulunan) aşağıdaki değişiklikleri yapın:

[!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]

BEGIN_PROPPAGEIDS makronun ikinci parametresini (özellik sayfası sayısı) 1'den 2'ye çıkarmanız gerektiğini unutmayın.

Denetim uygulama dosyasını da değiştirmeniz gerekir (. CPP) dosya üstbilgi (. H) yeni özellik sayfası sınıfının dosyası.

Bir sonraki adım, yeni özellik sayfası için bir tür adı ve bir altyazı sağlayacak iki yeni dize kaynağı oluşturmayı içerir.

#### <a name="to-add-new-string-resources-to-a-property-page"></a>Özellik sayfasına yeni dize kaynakları eklemek için

1. Denetim projeniz açıkken Kaynak Görünümü'ni açın.

1. **String Table** klasörünü çift tıklatın ve ardından dize eklemek istediğiniz varolan dize tablosu kaynağını çift tıklatın.

   Bu, bir penceredeki dize tablosunu açar.

1. Dize tablosunun sonundaki boş satırı seçin ve dizedeki metni veya alt yazıyı yazın: örneğin, "Ek Özellik Sayfası."

   Bu, **Resim Yazısı** ve **kimlik** kutularını gösteren bir **String Özellikleri** sayfasını açar. **Resim Yazısı** kutusu yazdığınız dizeyi içerir.

1. **Kimlik** kutusunda, dize için bir kimlik seçin veya yazın. Bitirdiğinde Enter tuşuna basın.

   Bu **örnekte,** yeni özellik sayfasının tür adı için IDS_SAMPLE_ADDPAGE kullanır.

1. Kimlik için **IDS_SAMPLE_ADDPPG_CAPTION** ve resim yazısı için "Ek Özellik Sayfası" kullanarak 3 ve 4 adımlarını yineleyin.

1. İçinde. Yeni özellik sayfası sınıfının CPP dosyası `CAddtlPropPage`(bu `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` örnekte), aşağıdaki örnekte olduğu gibi, IDS_SAMPLE_ADDPAGE [AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass)tarafından geçirilir şekilde değiştirin:

   [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]

1. IDS_SAMPLE_ADDPPG_CAPTION'nin `CAddtlPropPage` `COlePropertyPage` oluşturucuya aktarılması için oluşturucuyu aşağıdaki gibi değiştirin:

   [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]

Gerekli değişiklikleri yaptıktan sonra projenizi yeniden oluşturun ve yeni özellik sayfasını test etmek için Test Kapsayıcısı'nı kullanın. Test kapsayıcısına nasıl erişireceksiniz hakkında bilgi almak için [Test Kapsayıcısı ile Test Özellikleri ve Olayları'na](../mfc/testing-properties-and-events-with-test-container.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)
