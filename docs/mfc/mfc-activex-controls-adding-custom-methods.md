---
title: 'MFC ActiveX Denetimleri: Özel Yöntemler Ekleme'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
ms.openlocfilehash: 88d486248eab5d980463764db34bf40b05b830dc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364709"
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC ActiveX Denetimleri: Özel Yöntemler Ekleme

Özel yöntemler, stok yöntemlerinden zaten uygulanmamış `COleControl`olması açısından farklıdır. Denetiminize eklediğiniz her özel yöntem için uygulama sağlamanız gerekir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

ActiveX denetim kullanıcısı, denetime özel eylemleri gerçekleştirmek için istediği zaman özel bir yöntem çağırabilir. Özel yöntemler için sevk haritası girişi DISP_FUNCTION formundandır.

## <a name="adding-a-custom-method-with-the-add-method-wizard"></a><a name="_core_adding_a_custom_method_with_classwizard"></a>Ekle Yöntemi Sihirbazı ile Özel Yöntem Ekleme

Aşağıdaki yordam, ActiveX denetiminin iskelet koduna özel yöntem PtInCircle'ın eklediğini gösterir. PtInCircle, denetime geçirilen koordinatların dairenin içinde mi yoksa dışında mı olduğunu belirler. Bu aynı yordam, diğer özel yöntemler eklemek için de kullanılabilir. Özel yöntem adınızı ve parametrelerini PtInCircle yöntem adı ve parametreleri ile değiştirin.

> [!NOTE]
> Bu örnek, `InCircle` olaylar makalesindeki işlevi kullanır. Bu işlev hakkında daha fazla bilgi için [MFC ActiveX Denetimleri makalesine bakın: ActiveX Denetimine Özel Olaylar Ekleme.](../mfc/mfc-activex-controls-adding-custom-events.md)

#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>Ekle Yöntemi Sihirbazı'nı kullanarak PtInCircle özel yöntemini eklemek için

1. Denetimin projesini yükleyin.

1. Sınıf Görünümü'nde, denetiminizin kitaplık düğümunu genişletin.

1. Kısayol menüsünü açmak için denetiminiz için arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Yöntem Ekle'yi**tıklatın.

   Bu, Yöntem Ekle Sihirbazı'nı açar.

1. Yöntem **Adı** kutusuna *PtInCircle*yazın.

1. İç **Ad** kutusunda, yöntemin iç işlevinin adını yazın veya varsayılan değeri kullanın (bu durumda, *PtInCircle).*

1. İade **Türü** kutusunda, yöntemin dönüş türü için **VARIANT_BOOL** tıklatın.

1. **Parametre Türü** ve **Parametre Adı** denetimlerini *kullanarak, xCoord* (tip *OLE_XPOS_PIXELS)* adlı bir parametre ekleyin.

1. **Parametre Türü** ve **Parametre Adı** denetimlerini kullanarak, *yCoord* (tip *OLE_YPOS_PIXELS)* adlı bir parametre ekleyin.

1. **Son**'a tıklayın.

## <a name="add-method-wizard-changes-for-custom-methods"></a><a name="_core_classwizard_changes_for_custom_methods"></a>Özel Yöntemler için Yöntem Sihirbazı Değişiklikleri Ekle

Özel bir yöntem eklediğinizde, Yöntem Ekle Sihirbazı denetim sınıfı üstbilgide (. H) ve uygulama (. CPP) dosyaları. Denetim sınıfı üstbilgisinde sevk haritası bildirimine aşağıdaki satır eklenir (. H) dosya:

[!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]

Bu kod, bir gönderme yöntemi `PtInCircle`işleyicisi adlı bildirir. Bu işlev dış ad `PtInCircle`kullanılarak kontrol kullanıcısı tarafından çağrılabilir.

Aşağıdaki satır denetimin. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]

Bu satır yönteme belirli bir kimlik numarası, yöntemin konumunu Yöntem Sihirbazı yöntemleri ve özellikleri listesinde atar. `PtInCircle` Özel yöntemi eklemek için Ekle Yöntemi Sihirbazı kullanıldığından, bunun girişi projenin . IDL dosyası.

Buna ek olarak, aşağıdaki satır, uygulamada bulunan (. CPP) denetim sınıfının dosyası, denetimin sevk haritasına eklenir:

[!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]

DISP_FUNCTION makro, yöntemi `PtInCircle` denetimin işleyicisi `PtInCircle`işleviyle eşler, döndürme türünü **VARIANT_BOOL**olarak bildirir ve **VTS_XPOS_PIXELS** ve `PtInCircle` **VTS_YPOSPIXELS** iki parametresini ileder.

Son olarak, Yöntem Ekle Sihirbazı `CSampleCtrl::PtInCircle` denetimin uygulamasının altına saplama işlevini ekler (. CPP) dosyası. Daha `PtInCircle` önce belirtildiği gibi çalışması için aşağıdaki gibi değiştirilmesi gerekir:

[!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[Sınıf Görünümü ve Nesne Tarayıcı Simgeleri](/visualstudio/ide/class-view-and-object-browser-icons)
