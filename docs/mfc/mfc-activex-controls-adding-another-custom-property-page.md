---
title: 'MFC ActiveX denetimleri: Başka bir özel özellik sayfası ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
ms.openlocfilehash: 87b71fdddc5b52f66c34cdbcdb234c83616d0850
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160347"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX denetimleri: Başka bir özel özellik sayfası ekleme

Bazen, bir ActiveX denetimini makul bir özellik sayfasında sığmazsa daha fazla özellik gerekir. Bu durumda, bu özellikleri görüntülemek için ActiveX denetimi özellik sayfaları ekleyebilirsiniz.

Bu makalede, en az bir özellik sayfası zaten olan bir ActiveX denetimine yeni özellik sayfaları ekleme açıklanmaktadır. Stok özellik ekleme hakkında daha fazla bilgi sayfaları (yazı tipi, resim veya renk) makalesine bakın [MFC ActiveX denetimleri: Stok özellik sayfalarını kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md).

ActiveX Denetim Sihirbazı tarafından oluşturulan bir örnek ActiveX denetim çerçevesi aşağıdaki yordamları kullanın. Bu nedenle, sınıf adları ve tanımlayıcıları Bu örnek için benzersizdir.

ActiveX denetiminde özellik sayfalarını kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [MFC ActiveX denetimleri: Özellik sayfaları](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX denetimleri: Stok özellik sayfalarını kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)

    > [!NOTE]
    >  Bu yeni özellik sayfaları ActiveX denetimi özellik sayfaları için standart boyutu bağlı kalmayı önemle tavsiye edilir. Ölçü 250 x 62 iletişim kutusu birimleri (DLU) resmi ve renk stoğu özellik sayfaları. Standart yazı tipi özellik sayfası 250 x 110 Dlu'lar ' dir. ActiveX Denetim Sihirbazı tarafından oluşturulan varsayılan özellik sayfası 250 x 62 DLU standardını kullanır.

### <a name="to-insert-a-new-property-page-template-into-your-project"></a>Yeni bir özellik sayfası şablonu projenize eklemek için

1. Denetim projenizi açın, proje çalışma alanında kaynak görünümü açın.

1. Kısayol menüsünü açın ve'ı tıklatın, Kaynak Görünümü'nde sağ **kaynak Ekle**.

1. Genişletin **iletişim** düğüm ve select **IDD_OLE_PROPPAGE_SMALL**.

1. Tıklayın **yeni** kaynak projenize eklenecek.

1. Özellikler penceresini yenilemek için yeni özellik sayfası şablonu seçin.

1. İçin yeni bir değer girin **kimliği** özelliği. Bu örnekte **IDD_PROPPAGE_NEWPAGE**.

1. Tıklayın **Kaydet** araç.

### <a name="to-associate-the-new-template-with-a-class"></a>Yeni Şablon sınıfı ile ilişkilendirmek için

1. Sınıf Görünümü açın.

1. Kısayol menüsünü açın, Sınıf Görünümü'nde sağ tıklayın.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **sınıfı Ekle**.

   Bu açılır [sınıfı Ekle](../ide/add-class-dialog-box.md) iletişim kutusu.

1. Çift **MFC sınıfı** şablonu.

1. İçinde **sınıf adı** kutusunda [MFC Sınıf Sihirbazı](../mfc/reference/mfc-add-class-wizard.md), yeni iletişim kutusu sınıfı için bir ad yazın. (Bu örnekte, `CAddtlPropPage`.)

1. Dosya adlarını değiştirmek istiyorsanız, tıklayın **değiştirme**. Uygulama ve üstbilgi dosyaları adlarını yazın veya varsayılan adı kabul edin.

1. İçinde **temel sınıf** kutusunda `COlePropertyPage`.

1. İçinde **iletişim kimliği** kutusunda **IDD_PROPPAGE_NEWPAGE**.

9. Tıklayın **son** sınıfı oluşturmak için.

Denetimin kullanıcılar bu yeni özellik sayfası erişime izin vermek için denetimin özellik sayfası kimlikleri makrosu bölümü (Denetim uygulama dosyasında bulunur) için aşağıdaki değişiklikleri yapın:

[!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]

Begın_proppageıds makrosu (özellik sayfa sayısı) 1'den 2'öğesinin ikinci parametresi artırmalıdır unutmayın.

Denetim uygulama dosyasını da değiştirmeniz gerekir (. Üst bilgisi dahil edilecek CPP) dosyası (. H) yeni özellik sayfası sınıfının dosyası.

Sonraki adım, yeni özellik sayfası için bir tür adı ve açıklamalı alt yazı sağlayacak iki yeni dize kaynakları oluşturmayı içerir.

#### <a name="to-add-new-string-resources-to-a-property-page"></a>Bir özellik sayfası için yeni dize kaynakları eklemek için

1. Denetim projenize açık kaynak görünümünü açın.

1. Çift **dize tablosu** klasörüne gittikten sonra çift tıklayarak var olan dize tablosuna bir dize eklemek istediğiniz kaynak.

   Bu dize tablosu bir pencerede açılır.

1. Dize tablosu, sonunda boş satır seçin ve metin veya resim yazısı, dizenin türü: Örneğin, "ek özellik sayfası."

   Bu açılır bir **dize özellikleri** sayfasını gösteren **açıklamalı alt yazı** ve **kimliği** kutuları. **Açıklamalı alt yazı** kutusuna yazdığınız dizeyi içerir.

1. İçinde **kimliği** kutusunu seçin veya bir kimlik dizesi yazın. İşlemi tamamladığınızda, Enter tuşuna basın.

   Bu örnekte **IDS_SAMPLE_ADDPAGE** için yeni özellik sayfasının tür adı.

1. 3 ve 4 kullanarak **IDS_SAMPLE_ADDPPG_CAPTION** kimliği ve "Ek özellik sayfası" başlığını için.

1. İçinde. Yeni özellik sayfası sınıfının CPP dosyasına (Bu örnekte, `CAddtlPropPage`) değiştirme `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` IDS_SAMPLE_ADDPAGE geçirilir, böylece [AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass), aşağıdaki örnekte olduğu gibi:

   [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]

1. Oluşturucusuna değiştirme `CAddtlPropPage` IDS_SAMPLE_ADDPPG_CAPTION geçirilir, böylece `COlePropertyPage` oluşturucusu, aşağıdaki gibi:

   [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]

Projenizi yeniden derleyin ve yeni özellik sayfasını sınamak için sınama Kapsayıcınızı kullanmak gerekli değişiklikleri yaptıktan sonra. Bkz: [Test kapsayıcısı ile test etme özellikleri ve olayları](../mfc/testing-properties-and-events-with-test-container.md) test kapsayıcı erişim hakkında daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)
