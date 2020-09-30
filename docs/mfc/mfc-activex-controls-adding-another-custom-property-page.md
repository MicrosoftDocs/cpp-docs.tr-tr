---
title: 'MFC ActiveX Denetimleri: Başka Bir Özel Özellik Sayfası Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
ms.openlocfilehash: a749c5d8d676ac85c3c2085eb041328aff599ab8
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508875"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX Denetimleri: Başka Bir Özel Özellik Sayfası Ekleme

Bazen, bir ActiveX denetimi bir özellik sayfasına makul bir şekilde uyum sağlayacak daha fazla özelliğe sahip olur. Bu durumda, bu özellikleri göstermek için ActiveX denetimine Özellik sayfaları ekleyebilirsiniz.

Bu makalede, daha önce en az bir özellik sayfası olan bir ActiveX denetimine yeni özellik sayfaları ekleme ele alınmaktadır. Hisse senedi özellik sayfaları (yazı tipi, resim veya renk) ekleme hakkında daha fazla bilgi için [MFC ActiveX denetimleri: stok özellik sayfalarını kullanma](mfc-activex-controls-using-stock-property-pages.md)makalesine bakın.

Aşağıdaki yordamlar, ActiveX Denetim Sihirbazı tarafından oluşturulan örnek bir ActiveX denetim çerçevesini kullanır. Bu nedenle, sınıf adları ve tanımlayıcıları bu örneğe özeldir.

ActiveX denetiminde Özellik sayfaları kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [MFC ActiveX denetimleri: Özellik sayfaları](mfc-activex-controls-property-pages.md)

- [MFC ActiveX denetimleri: stok özellik sayfalarını kullanma](mfc-activex-controls-using-stock-property-pages.md)

    > [!NOTE]
    >  Yeni özellik sayfalarının ActiveX denetimi özellik sayfaları için boyut standardına bağlı olması önemle önerilir. Hisse senedi resmi ve renk özellik sayfaları 250x62 iletişim birimleri (DLU) olarak ölçer. Standart yazı tipi özellik sayfası 250x110 DLUs ' dir. ActiveX Denetim Sihirbazı tarafından oluşturulan varsayılan özellik sayfası, 250x62 DLU standardını kullanır.

### <a name="to-insert-a-new-property-page-template-into-your-project"></a>Projenize yeni bir özellik sayfası şablonu eklemek için

1. Denetim projeniz açıkken, proje çalışma alanında Kaynak Görünümü açın.

1. Kaynak Görünümü sağ tıklayarak kısayol menüsünü açın ve **Kaynak Ekle**' ye tıklayın.

1. **Iletişim kutusu** düğümünü genişletin ve **IDD_OLE_PROPPAGE_SMALL**' yi seçin.

1. Kaynağı projenize eklemek için **Yeni** ' ye tıklayın.

1. **Özellikler** penceresini yenilemek için yeni özellik sayfası şablonunu seçin ( **kaynak görünümü**).

1. **ID** özelliği için yeni bir değer girin. Bu örnek **IDD_PROPPAGE_NEWPAGE**kullanır.

1. Araç çubuğunda **Kaydet** seçeneğine tıklayın.

### <a name="to-associate-the-new-template-with-a-class"></a>Yeni şablonu bir sınıfla ilişkilendirmek için

1. Sınıf Görünümü açın.

1. Kısayol menüsünü açmak için Sınıf Görünümü ' ye sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Sınıf Ekle**' ye tıklayın.

   Bu, [Sınıf Ekle](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) iletişim kutusunu açar.

1. **MFC sınıf** şablonuna çift tıklayın.

1. [MFC sınıf Sihirbazı](reference/mfc-add-class-wizard.md)' nın **sınıf adı** kutusuna yeni iletişim kutusu sınıfı için bir ad yazın. (Bu örnekte, `CAddtlPropPage` .)

1. Dosya adlarını değiştirmek istiyorsanız **Değiştir**' e tıklayın. Uygulamanızın ve başlık dosyalarınızın adlarını yazın veya varsayılan adları kabul edin.

1. **Taban sınıf** kutusunda öğesini seçin `COlePropertyPage` .

1. Iletişim kutusu **kimliği** kutusunda **IDD_PROPPAGE_NEWPAGE**' yi seçin.

1. Sınıfı oluşturmak için **son** ' a tıklayın.

Denetimin kullanıcılarının bu yeni özellik sayfasına erişmesine izin vermek için, denetimin özellik sayfası kimlikleri makrosu bölümünde (denetim uygulama dosyasında bulunur) aşağıdaki değişiklikleri yapın:

[!code-cpp[NVC_MFC_AxUI#32](codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]

BEGIN_PROPPAGEIDS makrosunun ikinci parametresini (özellik sayfası sayısı) 1 ' den 2 ' ye artırmanız gerektiğini unutmayın.

Ayrıca Denetim uygulama dosyasını (. CPP) dosyasına ekleyin (. H) yeni özellik sayfa sınıfının dosyası.

Sonraki adım, yeni özellik sayfası için bir tür adı ve bir açıklamalı alt yazı sağlayacak iki yeni dize kaynağı oluşturmayı içerir.

#### <a name="to-add-new-string-resources-to-a-property-page"></a>Yeni dize kaynaklarını bir özellik sayfasına eklemek için

1. Denetim projem açıkken Kaynak Görünümü açın.

1. **Dize tablosu** klasörüne çift tıklayın ve ardından bir dize eklemek istediğiniz varolan dize tablosu kaynağına çift tıklayın.

   Bu, dize tablosunu bir pencerede açar.

1. Dize tablosunun sonundaki boş satırı seçin ve dizenin metin veya açıklamalı alt yazısını yazın: Örneğin, "ek özellik sayfası."

   Bu, **başlık** ve **kimlik** kutularını gösteren bir **dize özellikleri** sayfası açar. **Başlık** kutusu, yazdığınız dizeyi içerir.

1. **Kimlik** kutusunda, dize IÇIN bir kimlik seçin veya yazın. Bitirdiğinizde ENTER tuşuna basın.

   Bu örnek, yeni özellik sayfasının tür adı için **IDS_SAMPLE_ADDPAGE** kullanır.

1. KOD ve başlık için "ek özellik sayfası" **IDS_SAMPLE_ADDPPG_CAPTION** kullanarak 3 ve 4. adımları yineleyin.

1. İçinde. Yeni özellik sayfası sınıfınızın CPP dosyası (Bu örnekte `CAddtlPropPage` ), `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` Aşağıdaki örnekte olduğu gibi, IDS_SAMPLE_ADDPAGE [AfxOleRegisterPropertyPageClass](reference/registering-ole-controls.md#afxoleregisterpropertypageclass)tarafından geçirilecek şekilde değiştirin:

   [!code-cpp[NVC_MFC_AxUI#33](codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]

1. Yapıcısını, `CAddtlPropPage` IDS_SAMPLE_ADDPPG_CAPTION `COlePropertyPage` oluşturucuya aşağıdaki gibi geçirilecek şekilde değiştirin:

   [!code-cpp[NVC_MFC_AxUI#34](codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]

Gerekli değişiklikleri yaptıktan sonra projenizi yeniden oluşturun ve yeni özellik sayfasını test etmek için test kapsayıcısını kullanın. Test kapsayıcısına erişme hakkında bilgi için bkz. test [kapsayıcı Ile özellikleri ve olayları test etme](testing-properties-and-events-with-test-container.md) .

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
