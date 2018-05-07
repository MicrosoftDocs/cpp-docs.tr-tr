---
title: 'MFC ActiveX denetimleri: Yazı tiplerini kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnFontChanged
- HeadingFont
- InternalFont
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], MFC ActiveX controls fonts
- OnDraw method, MFC ActiveX controls
- InternalFont method [MFC]
- SetFont method [MFC]
- OnFontChanged method [MFC]
- IPropertyNotifySink class [MFC]
- MFC ActiveX controls [MFC], fonts
- Stock Font property [MFC]
- HeadingFont property [MFC]
- GetFont method [MFC]
- SelectStockFont method [MFC]
- fonts [MFC], ActiveX controls
ms.assetid: 7c51d602-3f5a-481d-84d1-a5d8a3a71761
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b53ab98e44a8696795e810b8d6f643720d8f9655
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-using-fonts"></a>MFC ActiveX Denetimleri: Yazı Tiplerini Kullanma
ActiveX denetimi metin görüntülüyorsa, yazı tipi özelliğini değiştirerek metin görünümünü değiştirmek denetim kullanıcı izin verebilirsiniz. Yazı tipi özelliklerini yazı tipi nesneleri olarak uygulanır ve iki türden biri olabilir: stok veya özel. Stok yazı tipi özellikleri Özellik Ekleme Sihirbazı'nı kullanarak ekleyebilirsiniz preimplemented yazı tipi özelliklerdir. Özel yazı tipi özelliklerini değil preimplemented ve denetim Geliştirici özelliğin davranışı ve kullanım belirler.  
  
 Bu makalede aşağıdaki konuları içerir:  
  
-   [Stock Font özelliği kullanma](#_core_using_the_stock_font_property)  
  
-   [İçinde denetim özel yazı tipi özelliklerini kullanma](#_core_implementing_a_custom_font_property)  
  
##  <a name="_core_using_the_stock_font_property"></a> Stok Font özelliğini kullanma  
 Stok yazı tipi özellikleri sınıfı tarafından preimplemented [COleControl](../mfc/reference/colecontrol-class.md). Ayrıca, standart bir yazı tipi özellik sayfası kullanıcının yazı tipi nesnesinin adı, boyut ve stil gibi çeşitli özniteliklerini değiştirmesine izin, de kullanılabilir.  
  
 Yazı tipi nesnesi üzerinden erişim [GetFont](../mfc/reference/colecontrol-class.md#getfont), [SetFont](../mfc/reference/colecontrol-class.md#setfont), ve [InternalGetFont](../mfc/reference/colecontrol-class.md#internalgetfont) işlevlerini `COleControl`. Denetim kullanıcı yazı tipi nesnesi aracılığıyla erişecek `GetFont` ve `SetFont` herhangi bir Get/Set özelliği ile aynı şekilde işlevlerde. Yazı tipi nesnesine erişim denetimi içinde gelen gerekli olduğunda kullanın `InternalGetFont` işlevi.  
  
 ' Da anlatıldığı gibi [MFC ActiveX denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md), stok Özellikler ekleme ile kolay [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md). Font özelliği seçin ve Özellik Ekleme Sihirbazı'nı stok yazı tipi girişini denetimin gönderme harita içine otomatik olarak ekler.  
  
#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak stok Font özelliği eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde denetiminizin kitaplığı düğümünü genişletin.  
  
3.  Arabirim (kitaplık düğümünün İkinci düğüm) denetlemek için kısayol menüsünü açmak için düğümü.  
  
4.  Kısayol menüsünden tıklatın **Ekle** ve ardından **Özellik Ekle**.  
  
     Bu özellik Ekleme Sihirbazı'nı açar.  
  
5.  İçinde **özellik adı** kutusunda, **yazı tipi**.  
  
6.  **Son**'a tıklayın.  
  
 Özellik Ekleme Sihirbazı'nı denetimin gönderme Harita Denetim sınıf uygulama dosyasında bulunan, aşağıdaki satırı ekler:  
  
 [!code-cpp[NVC_MFC_AxFont#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]  
  
 Buna ek olarak, Özellik Ekleme Sihirbazı'nı aşağıdaki satırı denetimine ekler. IDL dosyası:  
  
 [!code-cpp[NVC_MFC_AxFont#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]  
  
 Stok resim yazısı özelliğini stok yazı tipi özellik bilgileri kullanarak çizilmiş bir metin özelliğini örneğidir. Resim yazısı özelliğini stok denetimine ekleme adımları stock Font özelliği için kullanılan benzer kullanır.  
  
#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak stok resim yazısı özelliğini eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde denetiminizin kitaplığı düğümünü genişletin.  
  
3.  Arabirim (kitaplık düğümünün İkinci düğüm) denetlemek için kısayol menüsünü açmak için düğümü.  
  
4.  Kısayol menüsünden tıklatın **Ekle** ve ardından **Özellik Ekle**.  
  
     Bu özellik Ekleme Sihirbazı'nı açar.  
  
5.  İçinde **özellik adı** kutusunda, **resim yazısı**.  
  
6.  **Son**'a tıklayın.  
  
 Özellik Ekleme Sihirbazı'nı denetimin gönderme Harita Denetim sınıf uygulama dosyasında bulunan, aşağıdaki satırı ekler:  
  
 [!code-cpp[NVC_MFC_AxFont#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]  
  
##  <a name="_core_modifying_the_ondraw_function"></a> OnDraw işlevi değiştirme  
 Varsayılan uygulaması `OnDraw` denetiminde gösterilen tüm metni için Windows sistem yazı tipi kullanır. Bu, değiştirmelisiniz anlamına gelir `OnDraw` cihaz bağlamına yazı tipi nesne seçerek kodu. Bunu yapmak için arama [COleControl::SelectStockFont](../mfc/reference/colecontrol-class.md#selectstockfont) ve aşağıdaki örnekte gösterildiği gibi denetimin cihaz bağlamı geçirin:  
  
 [!code-cpp[NVC_MFC_AxFont#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]  
  
 Sonra `OnDraw` işlevi, yazı tipi nesnesini kullanmak için değiştirildi, denetimin stok yazı tipi özelliğinden özelliklerle denetim içindeki herhangi bir metin görüntülenir.  
  
##  <a name="_core_using_custom_font_properties_in_your_control"></a> İçinde denetim özel yazı tipi özelliklerini kullanma  
 Stok Font özelliği yanı sıra ActiveX denetimini özel yazı tipi özelliklere sahip olabilir. Özel yazı tipi özellik eklemek için yapmanız gerekir:  
  
-   Özel yazı tipi özelliği uygulamak için Özellik Ekleme Sihirbazı'nı kullanın.  
  
-   [Yazı tipi bildirimleri işleme](#_core_processing_font_notifications).  
  
-   [Yeni bir yazı tipi bildirim arabirimini uygulayan](#_core_implementing_a_new_font_notification_interface).  
  
###  <a name="_core_implementing_a_custom_font_property"></a> Özel yazı tipi özellik uygulama  
 Özel yazı tipi özelliği uygulamak için özellik ekleyin ve ardından kod bazı değişiklikler yapmak için Özellik Ekleme Sihirbazı'nı kullanın. Aşağıdaki bölümlerde özel ekleme `HeadingFont` örnek denetimi özelliği.  
  
##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak özel yazı tipi özellik eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde denetiminizin kitaplığı düğümünü genişletin.  
  
3.  Arabirim (kitaplık düğümünün İkinci düğüm) denetlemek için kısayol menüsünü açmak için düğümü.  
  
4.  Kısayol menüsünden tıklatın **Ekle** ve ardından **Özellik Ekle**.  
  
     Bu özellik Ekleme Sihirbazı'nı açar.  
  
5.  İçinde **özellik adı** özellik için bir ad yazın. Bu örneğin **HeadingFont**.  
  
6.  İçin **uygulama türü**, tıklatın **Get/Set yöntemleri**.  
  
7.  İçinde **özellik türü** kutusunda **IDispatch\***  özelliğin türü.  
  
8.  **Son**'a tıklayın.  
  
 Özellik Ekleme Sihirbazı'nı eklemek için kod oluşturur `HeadingFont` özel özelliğine `CSampleCtrl` sınıf ve örnek. IDL dosyası. Çünkü `HeadingFont` Get/Set özellik türü Özellik Ekleme Sihirbazı'nı değiştirir `CSampleCtrl` sınıfının gönderme harita dahil etmek için bir `DISP_PROPERTY_EX_ID` [dısp_property_ex](../mfc/reference/dispatch-maps.md#disp_property_ex) makrosu girişi:  
  
 [!code-cpp[NVC_MFC_AxFont#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]  
  
 `DISP_PROPERTY_EX` Makrosu ilişkilendirir `HeadingFont` , karşılık gelen özellik adı `CSampleCtrl` sınıfı alma ve ayarlama yöntemleri `GetHeadingFont` ve `SetHeadingFont`. Özellik değeri türü de belirtilir; Bu durumda, **VT_FONT**.  
  
 Özellik Ekleme Sihirbazı'nı bir bildirim denetimi üstbilgi dosyasında da ekler. (. H) için `GetHeadingFont` ve `SetHeadingFont` işlevleri ve bunların işlev şablonları denetim uygulama dosyasında ekler (. CPP):  
  
 [!code-cpp[NVC_MFC_AxFont#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]  
  
 Son olarak, Özellik Ekleme Sihirbazı'nı Denetim değiştirir. IDL dosyası için bir giriş ekleyerek `HeadingFont` özelliği:  
  
 [!code-cpp[NVC_MFC_AxFont#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]  
  
### <a name="modifications-to-the-control-code"></a>Denetim kodu yapılan değişiklikler  
 Eklediğiniz göre `HeadingFont` denetimi özelliğine olmanız gerekir bazı değişiklikler yeni özellik tam olarak desteklemek için Denetim üstbilgi ve uygulama dosyaları.  
  
 Denetim üstbilgi dosyasında (. H), şu bildirimi korumalı üye değişkeni ekleyin:  
  
 [!code-cpp[NVC_MFC_AxFont#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]  
  
 Denetim uygulama dosyasında (. CPP), aşağıdakileri yapın:  
  
-   Initialize `m_fontHeading` denetim oluşturucuda.  
  
     [!code-cpp[NVC_MFC_AxFont#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]  
  
-   Statik bildirme **FONTDESC** varsayılan yazı tipi özniteliklerini içeren yapısı.  
  
     [!code-cpp[NVC_MFC_AxFont#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]  
  
-   Denetimdeki `DoPropExchange` üye işlev, bir çağrı ekleyin `PX_Font` işlevi. Bu, başlatma ve özel yazı tipi özelliğinizi kalıcılığını sağlar.  
  
     [!code-cpp[NVC_MFC_AxFont#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]  
  
-   Denetim uygulama son `GetHeadingFont` üye işlevi.  
  
     [!code-cpp[NVC_MFC_AxFont#12](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]  
  
-   Denetim uygulama son `SetHeadingFont` üye işlevi.  
  
     [!code-cpp[NVC_MFC_AxFont#13](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]  
  
-   Denetimi değiştirme `OnDraw` daha önce seçilen yazı tipi tutacak bir değişkeni tanımlamak için üye işlevi.  
  
     [!code-cpp[NVC_MFC_AxFont#14](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]  
  
-   Denetimi değiştirme `OnDraw` üye işlevi kullanılacak yazı tipini olduğu yerlerde aşağıdaki satırı ekleyerek cihaz bağlamına özel yazı tipi seçin.  
  
     [!code-cpp[NVC_MFC_AxFont#15](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]  
  
-   Denetimi değiştirme `OnDraw` üye işlevi yazı kullandıktan sonra aşağıdaki satırı ekleyerek cihaz bağlamına önceki yazı tipini seçin.  
  
     [!code-cpp[NVC_MFC_AxFont#16](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]  
  
 Özel yazı tipi Özellik uygulanmadı sonra denetimin geçerli yazı tipini değiştirmek denetim kullanıcıların standart yazı tipi özellik sayfası uygulanmalıdır. Standart yazı tipi özellik sayfası özellik sayfası kimliği eklemek için sonra aşağıdaki satırı ekleyin `BEGIN_PROPPAGEIDS` makrosu:  
  
 [!code-cpp[NVC_MFC_AxFont#17](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]  
  
 Sayısı parametresinin artırmanız gerekir, `BEGIN_PROPPAGEIDS` makrosu tek. Aşağıdaki satırı bu gösterilmektedir:  
  
 [!code-cpp[NVC_MFC_AxFont#18](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]  
  
 Bu değişiklikleri yaptıktan sonra ek işlevsellik içerecek şekilde tüm projeyi yeniden oluşturun.  
  
###  <a name="_core_processing_font_notifications"></a> Yazı tipi bildirimleri işleme  
 Çoğu durumda denetimi yazı tipi nesnesinin özelliklerini değiştirildiğinde bilmesi gerekir. Her bir yazı tipi nesne bir üye işlevini çağırarak değiştiğinde bildirim sağlama yeteneğine **IFontNotification** tarafından uygulanan arabirimi `COleControl`.  
  
 Denetim stok Font özelliği kullanıyorsa, kendi bildirimleri tarafından işlenen `OnFontChanged` üye işlevini `COleControl`. Özel yazı tipi özelliklerini eklediğinizde, bunları aynı uygulaması kullanmak olabilir. Önceki bölümdeki örnekte bu geçirerek gerçekleştirilmiştir &**m_xFontNotification** başlatırken **m_fontHeading** üye değişkeni.  
  
 ![Birden çok yazı tipi nesnesi arabirimleri uygulama](../mfc/media/vc373q1.gif "vc373q1")  
Birden çok yazı tipi nesnesi arabirimleri uygulama  
  
 Yukarıdaki şekilde düz satırları hem yazı tipi nesnelerini aynı uygulanması kullanıyorsanız Göster **IFontNotification**. Yazı tipi değiştirilen ayırt etmek istiyorsanız bu sorunlara neden olabilir.  
  
 Denetimin yazı tipi nesne bildirimler arasında ayrım yapmak için bir yoldur, ayrı bir uygulama oluşturmak için **IFontNotification** denetiminde yazı tipi nesneler için arabirim. Bu yöntem yalnızca dize veya yakın zamanda değiştirilmiş yazı tipi kullanan dizeleri, güncelleştirerek çizim kodunuzu en iyi duruma olanak tanır. Aşağıdaki bölümlerde, ikinci bir yazı tipi özellik için ayrı bildirim arabirimleri uygulamak için gerekli adımları gösterir. İkinci font özelliği olduğu varsayılır `HeadingFont` önceki bölümde eklenen özellik.  
  
###  <a name="_core_implementing_a_new_font_notification_interface"></a> Yeni bir yazı tipi bildirim arabirimi uygulama  
 İki veya daha fazla yazı tipleri bildirimler arasında ayrım yapmak için yeni bir bildirim arabirimi denetiminde kullanılan her yazı tipi için uygulanmalıdır. Aşağıdaki bölümlerde, Denetim üstbilgi ve uygulama dosyalarını değiştirerek yeni bir yazı tipi bildirim arabirimi uygulayan açıklar.  
  
### <a name="additions-to-the-header-file"></a>Üst bilgi dosyasını eklemeler  
 Denetim üstbilgi dosyasında (. H) için sınıf bildirimi aşağıdaki satırları ekleyin:  
  
 [!code-cpp[NVC_MFC_AxFont#19](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]  
  
 Bu uygulaması oluşturur `IPropertyNotifySink` adlı arabirim `HeadingFontNotify`. Bu yeni arabirim olarak adlandırılan bir yöntem içerir `OnChanged`.  
  
### <a name="additions-to-the-implementation-file"></a>Uygulama dosyasını eklemeler  
 Başlığın yazı tipi (Denetim oluşturucuda) başlatır kodda değişiklik `&m_xFontNotification` için `&m_xHeadingFontNotify`. Daha sonra aşağıdaki kodu ekleyin:  
  
 [!code-cpp[NVC_MFC_AxFont#20](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]  
  
 `AddRef` Ve `Release` yöntemleri `IPropertyNotifySink` arabirimi ActiveX denetim nesnesi için başvuru sayısı izlemek. Arabirim işaretçisi erişim denetimi aldığında, Denetim çağrıları `AddRef` başvuru sayısı artırılamıyor. Denetim işaretçisi ile sona erdiğinde çağırır `Release`, çok aynı şekilde bu **GlobalFree** genel bellek bloğu boşaltmak için çağrılabilir. Bu arabirim için başvuru sayısı sıfır olarak gittiğinde, arabirim uygulamasına serbest. Bu örnekte, `QueryInterface` işlevi döndürür gösteren bir işaretçi bir `IPropertyNotifySink` belirli bir nesne üzerinde arabirimi. Bu işlev, hangi arabirimlerin belirlemek için bir nesne sorgulamak bir ActiveX denetimi sağlar.  
  
 Projenize bu değişiklikler yapıldıktan sonra projeyi oluşturmak ve Test kapsayıcısı arabirimi sınamak için kullanın. Bkz: [test özellikleri ve olayları Test kapsayıcısı ile](../mfc/testing-properties-and-events-with-test-container.md) test kapsayıcısı erişim hakkında bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX denetimleri: ActiveX denetiminde resim kullanma](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)   
 [MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)

