---
title: 'MFC ActiveX denetimleri: ActiveX denetiminde resim kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- LPPICTUREDISP
dev_langs:
- C++
helpviewer_keywords:
- OnDraw method, MFC ActiveX controls
- MFC ActiveX controls [MFC], pictures
- OnDraw method [MFC]
- OnResetState method [MFC]
- CLSID_CPicturePropPage [MFC]
ms.assetid: 2e49735c-21b9-4442-bb3d-c82ef258eec9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 313cbe53189a4a6e9b87b1723a166de83f56df05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-using-pictures-in-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetiminde Resim Kullanma
Bu makalede, ortak resim türünü ve ActiveX denetiminde uygulamak nasıl açıklanmaktadır. Konular şunlardır:  
  
-   [Özel Resim Özellikleri'ne genel bakış](#_core_overview_of_custom_picture_properties)  
  
-   [ActiveX denetiminde bir özel resim özellik uygulama](#_core_implementing_a_custom_picture_property_in_your_activex_control)  
  
-   [Denetim projenize ekleme](#_core_additions_to_your_control_project)  
  
##  <a name="_core_overview_of_custom_picture_properties"></a> Özel Resim Özellikleri'ne genel bakış  
 Türü resim türleri bazı ActiveX denetimleri için ortak bir grup biridir. Resim türünü meta dosyaları, bit eşlemler ve simgeler işler ve ActiveX denetiminde görüntülenecek resim belirtmesini sağlar. Özel Resim özellikleri, bir resim nesnesi ve resim özelliği denetim kullanıcı erişimine izin vermek Get/Set işlevleri kullanılarak uygulanır. Denetim kullanıcıları hisse senedi resim özellik sayfası kullanılarak özel resim özellik erişin.  
  
 Standart resim türünü ek olarak, yazı tipi ve renk türleri de mevcuttur. ActiveX denetiminde standart yazı tipi kullanma hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: yazı tiplerini kullanarak](../mfc/mfc-activex-controls-using-fonts.md).  
  
 ActiveX denetim sınıfları denetim içindeki resim özelliği uygulamak için kullanabileceğiniz çeşitli bileşenleri sağlar. Bu bileşenler şunlardır:  
  
-   [CPictureHolder](../mfc/reference/cpictureholder-class.md) sınıfı.  
  
     Bu sınıf özel resim özelliği tarafından görüntülenen öğesini işlevselliği ve resim nesnesi için kolay erişim sağlar.  
  
-   Tür özellikleri için destek **LPPICTUREDISP**, Get/Set işlevlerle uygulanan.  
  
     Sınıf özel bir özellik ya da özelliklerini kolayca ekleyebilirsiniz görünümünü kullanarak, resim türünü destekler. ActiveX denetimi özellikleri sınıf görünümü ile ekleme hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md).  
  
-   Bir denetimin resim özellik veya özellikleri yöneten bir özellik sayfası.  
  
     Bu özellik sayfasında stok özellik sayfalarını ActiveX denetimleri için kullanılabilir grubunun bir parçasıdır. ActiveX denetimi özellik sayfaları hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: stok özellik sayfalarını kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
##  <a name="_core_implementing_a_custom_picture_property_in_your_activex_control"></a> ActiveX denetiminde bir özel resim özellik uygulama  
 Bu bölümde açıklanan adımları tamamladıktan sonra denetimi, kullanıcı tarafından seçilen resimleri görüntüleyebilirsiniz. Kullanıcının geçerli resim gösterir ve select farklı resimleri kullanıcıya izin veren bir Gözat düğmesi olan bir özellik sayfası kullanılarak görüntülenen resmi değiştirebilirsiniz.  
  
 Özel bir resim özellik özel özellik türü resim desteklemelidir olmasına, diğer özellikleri, temel fark uygulamak için kullanılan benzer bir işlem kullanılarak uygulanır. ActiveX denetiminde resim özelliği öğesinin çizilmesi gerektiğinde çünkü tam olarak uygulanabilir önce bir dizi eklemeler ve değişiklikler özelliğine yapılması gerekir.  
  
 Özel bir resim özellik uygulamak için aşağıdakileri yapmanız gerekir:  
  
-   [Kod denetim projenize eklemek](#_core_additions_to_your_control_project).  
  
     Bir standart resim özellik sayfası kimliği türü veri üyesi `CPictureHolder`ve türünde bir özel özellik **LPPICTUREDISP** Get/Set ile uygulama eklenmesi gerekir.  
  
-   [Denetim sınıfınıza birkaç işlevlerde değiştirme](#_core_modifications_to_your_control_project).  
  
     Bu değişiklikler, ActiveX denetimi çizim için sorumlu olan çeşitli işlevleri için yapılır.  
  
##  <a name="_core_additions_to_your_control_project"></a> Denetim projenize ekleme  
 Standart resim özellik sayfası özellik sayfası kimliği eklemek için sonra aşağıdaki satırı ekleyin `BEGIN_PROPPAGEIDS` makrosu denetim uygulama dosyasında (. CPP):  
  
 [!code-cpp[NVC_MFC_AxPic#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_1.cpp)]  
  
 Sayısı parametresinin artırmanız gerekir, `BEGIN_PROPPAGEIDS` makrosu tek. Aşağıdaki satırı bu gösterilmektedir:  
  
 [!code-cpp[NVC_MFC_AxPic#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_2.cpp)]  
  
 Eklenecek `CPictureHolder` control sınıfı veri üyesi denetim üst bilgi dosyası'nda denetim sınıf bildiriminin korumalı bölümünde aşağıdaki satırı ekleyin (. H):  
  
 [!code-cpp[NVC_MFC_AxPic#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_3.h)]  
  
 Veri üye adı gerekli değildir `m_pic`; herhangi bir ad yeterli olacaktır.  
  
 Ardından, bir resim türünü destekleyen bir özel özellik ekleyin:  
  
#### <a name="to-add-a-custom-picture-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak bir özel resim özelliği eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde denetiminizin kitaplığı düğümünü genişletin.  
  
3.  Arabirim (kitaplık düğümünün İkinci düğüm) denetlemek için kısayol menüsünü açmak için düğümü.  
  
4.  Kısayol menüsünden **Ekle** ve ardından **Özellik Ekle**.  
  
5.  İçinde **özellik adı** özellik adı yazın. Örneğin amacıyla `ControlPicture` bu yordamda kullanılır.  
  
6.  İçinde **özellik türü** kutusunda **IPictureDisp\***  özellik türü.  
  
7.  İçin **uygulama türü**, tıklatın **Get/Set yöntemleri**.  
  
8.  Alma ve ayarlama işlevleri için benzersiz adlarını yazın veya varsayılan adı kabul edin. (Bu örnekte, varsayılan adları `GetControlPicture` ve `SetControlPicture` kullanılır.)  
  
9. **Son**'a tıklayın.  
  
 Aşağıdaki kod control üstbilgisinin gönderme harita açıklamalarda arasında Özellik Ekleme Sihirbazı'nı ekler (. H) dosyası:  
  
 [!code-cpp[NVC_MFC_AxPic#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_4.h)]  
  
 Ayrıca, aşağıdaki kodu denetimi uyarlamasını gönderme haritasını eklendi (. CPP) dosyası:  
  
 [!code-cpp[NVC_MFC_AxPic#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_5.cpp)]  
  
 Özellik Ekleme Sihirbazı'nı, ayrıca Denetim uygulama dosyasında aşağıdaki iki saplama işlevleri ekler:  
  
 [!code-cpp[NVC_MFC_AxPic#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_6.cpp)]  
  
> [!NOTE]
>  Denetim sınıfı ve işlev adları, yukarıdaki örnekten farklı olabilir.  
  
###  <a name="_core_modifications_to_your_control_project"></a> Denetim projenizi yapılan değişiklikler  
 Denetim projenize gerekli eklemeleri yaptıktan sonra ActiveX denetimi işlemeyi etkileyen çeşitli işlevleri değiştirmeniz gerekir. Bu işlevler `OnResetState`, `OnDraw`, ve özel bir resim özellik Get/Set işlevlerini denetim uygulama dosyasında bulunur. (Bu örnekte control sınıfı olarak adlandırılır Not `CSampleCtrl`, `CPictureHolder` veri üyesi çağrılır `m_pic`, ve özel resim özellik adı `ControlPicture`.)  
  
 Denetimdeki `OnResetState` işlev, çağrısından sonra aşağıdaki isteğe bağlı satırı ekleyin `COleControl::OnResetState`:  
  
 [!code-cpp[NVC_MFC_AxPic#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_7.cpp)]  
  
 Bu denetimin resim boş bir resme ayarlar.  
  
 Resim düzgün bir şekilde çizmek için çağırmaya [CPictureHolder::Render](../mfc/reference/cpictureholder-class.md#render) denetiminde `OnDraw` işlevi. Aşağıdaki örnek benzeyecek şekilde işlevinizi değiştirin:  
  
 [!code-cpp[NVC_MFC_AxPic#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_8.cpp)]  
  
 Denetimin özel resim özelliğini Al işlevinde aşağıdaki satırı ekleyin:  
  
 [!code-cpp[NVC_MFC_AxPic#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_9.cpp)]  
  
 Denetimin özel resim özelliği ayarlama işlevinde aşağıdaki satırları ekleyin:  
  
 [!code-cpp[NVC_MFC_AxPic#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_10.cpp)]  
  
 Tasarım zamanında eklenen bilgiler çalışma zamanında gösterecektir böylece resim özelliği kalıcı yapılması gerekir. Aşağıdaki satırı ekleyin `COleControl`-türetilmiş sınıf'ın `DoPropExchange` işlevi:  
  
 [!code-cpp[NVC_MFC_AxPic#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_11.cpp)]  
  
> [!NOTE]
>  Sınıf ve işlev adları, yukarıdaki örnekten farklı olabilir.  
  
 Değişiklikleri tamamladıktan sonra özel resim özelliğinin yeni işlevsellikler eklemek ve yeni özellik test etmek için Test kapsayıcısı kullanmak için projenizi yeniden derleyin. Bkz: [test özellikleri ve olayları Test kapsayıcısı ile](../mfc/testing-properties-and-events-with-test-container.md) test kapsayıcısı erişim hakkında bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX denetimleri: Yazı tiplerini kullanma](../mfc/mfc-activex-controls-using-fonts.md)   
 [MFC ActiveX Denetimleri: Özellik Sayfaları](../mfc/mfc-activex-controls-property-pages.md)

