---
title: "MFC ActiveX denetimleri: Başka bir özel özellik sayfası ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 225535055f05fa8d6eeb08476004fbc5074e86b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX Denetimleri: Başka Bir Özel Özellik Sayfası Ekleme
Bazen, bir ActiveX denetimini makul bir özellik sayfasında sığmayacak daha fazla özelliği vardır. Bu durumda, bu özellikleri görüntülemek için ActiveX denetiminin özellik sayfaları ekleyebilirsiniz.  
  
 Bu makalede, en az bir özellik sayfası zaten olan bir ActiveX denetimine yeni özellik sayfaları ekleme anlatılmaktadır. Stok özellik ekleme hakkında daha fazla bilgi için sayfaları (yazı tipi, resim veya renk) makalesine bakın [MFC ActiveX denetimleri: stok özellik sayfalarını kullanarak](../mfc/mfc-activex-controls-using-stock-property-pages.md).  
  
 ActiveX Denetim Sihirbazı tarafından oluşturulan bir örnek ActiveX denetimi framework aşağıdaki yordamları kullanın. Bu nedenle, tanımlayıcılarını ve sınıf adları bu örnek için benzersizdir.  
  
 ActiveX denetiminde özellik sayfalarını kullanma ile ilgili daha fazla bilgi için aşağıdaki makalelere bakın:  
  
-   [MFC ActiveX denetimleri: Özellik sayfaları](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX denetimleri: Stok özellik sayfalarını kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
    > [!NOTE]
    >  Bu yeni özellik sayfaları ActiveX denetimi özellik sayfaları için standart boyutu uygun önemle tavsiye edilir. Stok resmi ve rengi özellik ölçü 250 x 62 iletişim kutusu birimleri (DLU) sayfaları. Standart yazı tipi özellik sayfası 250 x 110 Dlu'lar ' dir. ActiveX Denetim Sihirbazı tarafından oluşturulan varsayılan özellik sayfası 250 x 62 DLU standardını kullanır.  
  
### <a name="to-insert-a-new-property-page-template-into-your-project"></a>Yeni bir özellik sayfası şablonu projenize eklemek için  
  
1.  Denetim projenizi açın, proje çalışma alanında kaynak görünümü açın.  
  
2.  Kısayol menüsünü açın ve'ı tıklatın Kaynak Görünümü'nde sağ **kaynak ekleme**.  
  
3.  Genişletme **iletişim** düğümü ve select **IDD_OLE_PROPPAGE_SMALL**.  
  
4.  Tıklatın `New` kaynak projenize eklemek için.  
  
5.  Özellikler penceresini yenilemek için yeni özellik sayfası şablonu seçin.  
  
6.  İçin yeni bir değer girin **kimliği** özelliği. Bu örnekte **IDD_PROPPAGE_NEWPAGE**.  
  
7.  Tıklatın **kaydetmek** araç çubuğunda.  
  
### <a name="to-associate-the-new-template-with-a-class"></a>Yeni şablon sınıf ile ilişkilendirmek için  
  
1.  Sınıf Görünümü açın.  
  
2.  Kısayol menüsünü açmak için Sınıf Görünümü'nde sağ tıklayın.  
  
3.  Kısayol menüsünden tıklatın **Ekle** ve ardından **sınıfı Ekle**.  
  
     Bu açılır [sınıfı Ekle](../ide/add-class-dialog-box.md) iletişim kutusu.  
  
4.  Çift **MFC sınıfı** şablonu.  
  
5.  İçinde **sınıf adı** kutusunda [MFC Sınıf Sihirbazı](../mfc/reference/mfc-add-class-wizard.md), yeni iletişim kutusu sınıfı için bir ad yazın. (Bu örnekte, `CAddtlPropPage`.)  
  
6.  Dosya adlarını değiştirmek istiyorsanız, **değiştirmek**. Uygulama ve üst bilgi dosyalarınız için adlarını yazın veya varsayılan adı kabul edin.  
  
7.  İçinde **temel sınıf** kutusunda `COlePropertyPage`.  
  
8.  İçinde **iletişim kimliği** kutusunda **IDD_PROPPAGE_NEWPAGE**.  
  
9. Tıklatın **son** sınıfı oluşturmak için.  
  
 Denetimin kullanıcılar bu yeni özellik sayfası erişmesine izin vermek için denetimin özellik sayfası kimlikleri makrosu bölümüne (Denetim uygulama dosyası'nda bulunur) aşağıdaki değişiklikleri yapın:  
  
 [!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]  
  
 Öğesinin ikinci parametresi, artırmanız gerekir Not `BEGIN_PROPPAGEIDS` makrosu (özellik sayfası sayısı) 1'den 2.  
  
 Denetim uygulama dosyasını değiştirmeniz gerekir (. Üstbilgi eklenecek CPP) dosyası (. H) yeni özellik sayfası sınıfı dosyası.  
  
 Sonraki adım bir tür adı ve resim yazısı yeni özellik sayfasında sağlayacak iki yeni dize kaynakları oluşturursunuz.  
  
#### <a name="to-add-new-string-resources-to-a-property-page"></a>Bir özellik sayfası yeni dize kaynakları eklemek için  
  
1.  Denetim projenizi açın, kaynak görünümü açın.  
  
2.  Çift **dize tablosu** klasörü ve çift tıklatarak varolan bir dizeyi bir dize eklemek istediğiniz kaynak tablo.  
  
     Bu dize tablosu bir pencerede açılır.  
  
3.  Dize tablonun sonuna boş satır seçin ve metin veya dizenin resim yazısı yazın: Örneğin, "ek özellik sayfası."  
  
     Bu açılır bir **dize özellikleri** sayfasını gösteren **resim yazısı** ve **kimliği** kutuları. **Resim yazısı** kutusuna yazdığınız dize içeriyor.  
  
4.  İçinde **kimliği** kutusunda seçin veya bir kimlik dizesi yazın. Bitirdikten sonra Enter tuşuna basın.  
  
     Bu örnekte **IDS_SAMPLE_ADDPAGE** yeni özellik sayfası türü adı.  
  
5.  3 ve 4 kullanarak **IDS_SAMPLE_ADDPPG_CAPTION** ID ve "Ek özellik sayfası" resim yazısı.  
  
6.  İçinde. Yeni özellik sayfası sınıfınızın CPP dosya (Bu örnekte, `CAddtlPropPage`) değiştirme `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` IDS_SAMPLE_ADDPAGE geçirilen böylece [AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass), aşağıdaki örnekte olduğu gibi:  
  
     [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]  
  
7.  Oluşturucusunun değiştirme `CAddtlPropPage` böylece **IDS_SAMPLE_ADDPPG_CAPTION** geçirilir `COlePropertyPage` şekilde Oluşturucusu:  
  
     [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]  
  
 Projenizi yeniden derleyin ve yeni özellik sayfası test etmek için Test kapsayıcısını kullanmak gerekli değişiklikleri yaptıktan sonra. Bkz: [test özellikleri ve olayları Test kapsayıcısı ile](../mfc/testing-properties-and-events-with-test-container.md) test kapsayıcısı erişim hakkında bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)

