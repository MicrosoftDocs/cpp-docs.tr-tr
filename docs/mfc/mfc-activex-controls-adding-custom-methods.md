---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: özel yöntemler ekleme'
title: 'MFC ActiveX Denetimleri: Özel Yöntemler Ekleme'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
ms.openlocfilehash: a7ac7ad1f1635976b3190c84b02b40bf73551e70
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202957"
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC ActiveX Denetimleri: Özel Yöntemler Ekleme

Özel yöntemler, tarafından henüz uygulanmadığından stok yöntemlerinden farklıdır `COleControl` . Denetime eklediğiniz her özel yöntem için uygulama sağlamalısınız.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Bir ActiveX denetimi kullanıcısı, denetimine özgü eylemler gerçekleştirmek için herhangi bir zamanda özel bir yöntem çağırabilir. Özel yöntemler için dağıtım Haritası girişi DISP_FUNCTION formundadır.

## <a name="adding-a-custom-method-with-the-add-method-wizard"></a><a name="_core_adding_a_custom_method_with_classwizard"></a> Yöntem Ekleme Sihirbazı Ile özel bir yöntem ekleme

Aşağıdaki yordamda, bir ActiveX denetiminin iskelet koduna özel bir PtInCircle yöntemi ekleme gösterilmektedir. PtInCircle, denetime geçirilen koordinatların dairenin içinde mi yoksa dışında mı olduğunu belirler. Aynı yordam, başka özel yöntemler eklemek için de kullanılabilir. PtInCircle yöntem adı ve parametreleri için özel yöntem adınızı ve parametrelerini değiştirin.

> [!NOTE]
> Bu örnek, `InCircle` Makale olaylarından işlevini kullanır. Bu işlev hakkında daha fazla bilgi için [MFC ActiveX denetimleri: ActiveX denetimine özel olaylar ekleme](mfc-activex-controls-adding-custom-events.md)makalesine bakın.

#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>Yöntem Ekleme Sihirbazı 'Nı kullanarak PtInCircle özel yöntemini eklemek için

1. Denetimin projesini yükleyin.

1. Sınıf Görünümü, denetiminizin kitaplık düğümünü genişletin.

1. Kısayol menüsünü açmak için denetiminizin arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Yöntem Ekle**' ye tıklayın.

   Bu, yöntem ekleme Sihirbazı ' nı açar.

1. **Yöntem adı** kutusuna *Ptincircle* yazın.

1. **Iç ad** kutusunda, metodun iç işlevinin adını yazın veya varsayılan değeri kullanın (Bu durumda *Ptincircle*).

1. **Dönüş türü** kutusunda, yöntemin dönüş türü için **VARIANT_BOOL** ' ye tıklayın.

1. **Parametre türü** ve **parametre adı** denetimlerini kullanarak *xcosip* adlı bir parametre ekleyin (tür *OLE_XPOS_PIXELS*).

1. **Parametre türü** ve **parametre adı** denetimlerini kullanarak, *yıkozı* adlı bir parametre ekleyin (tür *OLE_YPOS_PIXELS*).

1. **Finish (Son)** düğmesine tıklayın.

## <a name="add-method-wizard-changes-for-custom-methods"></a><a name="_core_classwizard_changes_for_custom_methods"></a> Özel yöntemler için yöntem ekleme Sihirbazı değişiklikleri

Özel bir yöntem eklediğinizde Yöntem Ekleme Sihirbazı denetim sınıfı üst bilgisinde bazı değişiklikler yapar (. H) ve uygulama (. CPP) dosyaları. Aşağıdaki satır, denetim sınıfı üstbilgisindeki (. H) dosyası:

[!code-cpp[NVC_MFC_AxUI#18](codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]

Bu kod, adlı bir dağıtım yöntemi işleyicisi bildirir `PtInCircle` . Bu işlev, dış adı kullanılarak denetim kullanıcısı tarafından çağrılabilir `PtInCircle` .

Aşağıdaki satır denetimin öğesine eklenir. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#19](codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]

Bu satır `PtInCircle` yönteme belirli BIR kimlik numarası, yöntemin yöntem ekleme Sihirbazı yöntemleri ve Özellikler listesinde konumunu atar. Yöntem Ekleme Sihirbazı özel yöntemi eklemek için kullanıldığından, bu giriş, proje için otomatik olarak eklenir. IDL dosyası.

Ayrıca, uygulamada bulunan aşağıdaki satırı (. CPP) denetim sınıfının dosyası, denetimin dağıtım eşlemesine eklenir:

[!code-cpp[NVC_MFC_AxUI#20](codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]

DISP_FUNCTION makro, yöntemi `PtInCircle` denetimin işleyici işlevi ile eşleştirir, `PtInCircle` dönüş türünü **VARIANT_BOOL** olarak bildirir ve **VTS_XPOS_PIXELS** türünde iki parametre ve geçirilecek **VTS_YPOSPIXELS** bildirir `PtInCircle` .

Son olarak, yöntem ekleme Sihirbazı, saplama işlevini `CSampleCtrl::PtInCircle` denetimin uygulamasının alt kısmına ekler (. CPP) dosyası. `PtInCircle`Daha önce belirtildiği gibi çalışması için, aşağıdaki şekilde değiştirilmelidir:

[!code-cpp[NVC_MFC_AxUI#21](codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[Sınıf Görünümü ve Nesne Tarayıcısı simgeleri](/visualstudio/ide/class-view-and-object-browser-icons)
