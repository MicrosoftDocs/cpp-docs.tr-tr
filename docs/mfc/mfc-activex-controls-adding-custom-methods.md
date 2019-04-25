---
title: 'MFC ActiveX denetimleri: Özel yöntemler ekleme'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
ms.openlocfilehash: 4f5a7dc844d80ae94df8af7c0b2eea141376f9e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160152"
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC ActiveX denetimleri: Özel yöntemler ekleme

Bunlar zaten tarafından uygulanmaz ve o özel yöntemler farklı stok yöntemleri `COleControl`. Her özel yöntem denetiminize eklemek için uygulama sağlamanız gerekir.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

Bir ActiveX denetimi kullanıcı denetimine özgü eylemleri gerçekleştirmek için istediğiniz zaman özel bir yöntem çağırabilirsiniz. Özel metotlar için gönderme eşleme girişi dısp_functıon şeklidir.

##  <a name="_core_adding_a_custom_method_with_classwizard"></a> Özel yöntem ile ekleme yöntem Ekleme Sihirbazı

Aşağıdaki yordam, bir ActiveX denetiminin iskelet kodu Ptıncircle özel yöntemi ekleme göstermektedir. Ptıncircle denetime geçirilen koordinatları içinde veya dışında daire olup olmadığını belirler. Bu yordamı, özel diğer yöntemler eklemek için de kullanılabilir. Özel yöntem adınız ve Ptıncircle yöntem adı ve parametreler için parametrelerini değiştirin.

> [!NOTE]
>  Bu örnekte `InCircle` olayları makaleden işlevi. Bu işlev hakkında daha fazla bilgi için bkz [MFC ActiveX denetimleri: ActiveX denetimi için özel olaylar ekleme](../mfc/mfc-activex-controls-adding-custom-events.md).

#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>Yöntem Ekleme Sihirbazı'nı kullanarak Ptıncircle özel yöntemi eklemek için

1. Denetimin proje yükleyin.

1. Sınıf Görünümü'nde denetim kitaplığı düğümünü genişletin.

1. Arabirim (ikinci düğüm kitaplığı düğümünün) denetlemek için kısayol menüsünü açmak için düğümü.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Ekle yöntemi**.

   Bu yöntem Ekleme Sihirbazı'nı açar.

1. İçinde **yöntem adı** kutusuna *Ptıncircle*.

1. İçinde **iç adı** kutusunda yöntemin iç işlevin adını yazın veya varsayılan değeri kullanın (Bu durumda, *Ptıncircle*).

1. İçinde **dönüş türü** kutusunun **varıant_bool** yöntemin dönüş türü.

1. Kullanarak **parametre türü** ve **parametre adı** denetimleri ekleme adlı bir parametreyi *xCoord* (tür *OLE_XPOS_PIXELS*).

9. Kullanarak **parametre türü** ve **parametre adı** denetimleri ekleme adlı bir parametreyi *yCoord* (tür *OLE_YPOS_PIXELS*).

10. **Son**'a tıklayın.

##  <a name="_core_classwizard_changes_for_custom_methods"></a> Yöntem Sihirbazı değişiklikleri için özel yöntemler

Özel bir yönteme eklediğinizde, yöntem Ekleme Sihirbazı'nı bazı değişiklikler denetim sınıf başlığına yapar. (. H) ve uygulama (. Dosyaların CPP). Aşağıdaki satırı control sınıfı üst bilgisi gönderme harita bildiriminde eklenir (. H) dosyası:

[!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]

Bu kod adlı bir dağıtım yöntemi işleyicisi bildirir `PtInCircle`. Bu işlev dış adı kullanılarak denetiminin kullanıcı tarafından çağrılabilir `PtInCircle`.

Aşağıdaki satırı denetimin eklenir. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]

Bu satırı atar `PtInCircle` yöntemi belirli bir kimlik numarası, yöntem Ekleme Sihirbazı'nı yöntemler ve özellikler listesinde yöntemin konum. Yöntem Ekleme Sihirbazı'nı özel yöntem eklemek için kullanıldığından, bunu girişini otomatik olarak projenin eklendi. IDL dosyası.

Ayrıca, aşağıdaki satırı bulunan uygulamasında (. Denetim sınıfı, CPP) dosyası, denetimin dağıtım eşlemesi için eklenir:

[!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]

Dısp_functıon makrosu yöntemi eşleştirir `PtInCircle` denetimin işleyici işlevine `PtInCircle`, dönüş türü olarak bildirir **varıant_bool**ve iki parametre türü bildirir **vts_xpos_pıxels** ve **VTS_YPOSPIXELS** geçirilecek `PtInCircle`.

Son olarak, yöntem Ekleme Sihirbazı'nı saplama işlevi ekler `CSampleCtrl::PtInCircle` denetimin uygulama alt kısmına (. CPP) dosyası. İçin `PtInCircle` daha önce belirtildiği gibi çalışması için şu şekilde değiştirilmelidir:

[!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[Sınıf Görünümü ve Nesne Tarayıcısı Simgeleri](/visualstudio/ide/class-view-and-object-browser-icons)
