---
title: 'MFC ActiveX denetimleri: Başka bir özel özellik sayfası ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
ms.openlocfilehash: 09d85d69efc4c6cf0bf253099bae78c1e570f8a5
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907375"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX denetimleri: Başka bir özel özellik sayfası ekleme

Bazen, bir ActiveX denetimi bir özellik sayfasına makul bir şekilde uyum sağlayacak daha fazla özelliğe sahip olur. Bu durumda, bu özellikleri göstermek için ActiveX denetimine Özellik sayfaları ekleyebilirsiniz.

Bu makalede, daha önce en az bir özellik sayfası olan bir ActiveX denetimine yeni özellik sayfaları ekleme ele alınmaktadır. Hisse senedi özellik sayfaları (yazı tipi, resim veya renk) ekleme hakkında daha fazla bilgi için bkz [. MFC ActiveX denetimleri: Hisse senedi özellik sayfalarını](../mfc/mfc-activex-controls-using-stock-property-pages.md)kullanma.

Aşağıdaki yordamlar, ActiveX Denetim Sihirbazı tarafından oluşturulan örnek bir ActiveX denetim çerçevesini kullanır. Bu nedenle, sınıf adları ve tanımlayıcıları bu örneğe özeldir.

ActiveX denetiminde Özellik sayfaları kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [MFC ActiveX Denetimleri: Özellik Sayfaları](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX Denetimleri: Stok Özelliği Sayfaları Kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)

    > [!NOTE]
    >  Yeni özellik sayfalarının ActiveX denetimi özellik sayfaları için boyut standardına bağlı olması önemle önerilir. Hisse senedi resmi ve renk özellik sayfaları 250x62 iletişim birimleri (DLU) olarak ölçer. Standart yazı tipi özellik sayfası 250x110 DLUs ' dir. ActiveX Denetim Sihirbazı tarafından oluşturulan varsayılan özellik sayfası, 250x62 DLU standardını kullanır.

### <a name="to-insert-a-new-property-page-template-into-your-project"></a>Projenize yeni bir özellik sayfası şablonu eklemek için

1. Denetim projeniz açıkken, proje çalışma alanında Kaynak Görünümü açın.

1. Kaynak Görünümü sağ tıklayarak kısayol menüsünü açın ve **Kaynak Ekle**' ye tıklayın.

1. **Iletişim kutusunu** genişletin ve **IDD_OLE_PROPPAGE_SMALL**' ı seçin.

1. Kaynağı projenize eklemek için **Yeni** ' ye tıklayın.

1. **Özellikler** penceresini yenilemek için yeni özellik sayfası şablonunu seçin ( **kaynak görünümü**).

1. **ID** özelliği için yeni bir değer girin. Bu örnek, **IDD_PROPPAGE_NEWPAGE**kullanır.

1. Araç çubuğunda **Kaydet** ' e tıklayın.

### <a name="to-associate-the-new-template-with-a-class"></a>Yeni şablonu bir sınıfla ilişkilendirmek için

1. Sınıf Görünümü açın.

1. Kısayol menüsünü açmak için Sınıf Görünümü ' ye sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Sınıf Ekle**' ye tıklayın.

   Bu, [Sınıf Ekle](../ide/add-class-dialog-box.md) iletişim kutusunu açar.

1. **MFC sınıf** şablonuna çift tıklayın.

1. [MFC sınıf Sihirbazı](../mfc/reference/mfc-add-class-wizard.md)' nın **sınıf adı** kutusuna yeni iletişim kutusu sınıfı için bir ad yazın. (Bu örnekte, `CAddtlPropPage`.)

1. Dosya adlarını değiştirmek istiyorsanız **Değiştir**' e tıklayın. Uygulamanızın ve başlık dosyalarınızın adlarını yazın veya varsayılan adları kabul edin.

1. **Taban sınıf** kutusunda öğesini seçin `COlePropertyPage`.

1. Iletişim kutusu **kimliği** kutusunda **IDD_PROPPAGE_NEWPAGE**öğesini seçin.

9. Sınıfı oluşturmak için **son** ' a tıklayın.

Denetimin kullanıcılarının bu yeni özellik sayfasına erişmesine izin vermek için, denetimin özellik sayfası kimlikleri makrosu bölümünde (denetim uygulama dosyasında bulunur) aşağıdaki değişiklikleri yapın:

[!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]

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

1. KOD için **IDS_SAMPLE_ADDPPG_CAPTION** ve başlık Için "ek özellik sayfası" kullanarak 3 ve 4. adımları yineleyin.

1. İçinde. Yeni özellik sayfası sınıfınızın cpp dosyası (Bu örnekte, `CAddtlPropPage`), `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` aşağıdaki örnekte olduğu gibi, IDS_SAMPLE_ADDPAGE [AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass)tarafından geçirilecek şekilde değiştirin:

   [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]

1. IDS_SAMPLE_ADDPPG_CAPTION oluşturucusunu, aşağıdaki gibi, `COlePropertyPage` oluşturucuya geçirilecek şekildedeğiştirin:`CAddtlPropPage`

   [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]

Gerekli değişiklikleri yaptıktan sonra projenizi yeniden oluşturun ve yeni özellik sayfasını test etmek için test kapsayıcısını kullanın. Test kapsayıcısına erişme hakkında bilgi için bkz. test [kapsayıcı Ile özellikleri ve olayları test etme](../mfc/testing-properties-and-events-with-test-container.md) .

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)
