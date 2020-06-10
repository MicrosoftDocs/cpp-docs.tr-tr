---
title: 'MFC ActiveX Denetimleri: Gelişmiş Özellik Uygulama'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
ms.openlocfilehash: f5abef4db2f9c6d375428c0b0fd313198ce6283f
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621223"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX Denetimleri: Gelişmiş Özellik Uygulama

Bu makalede, ActiveX denetiminde gelişmiş özellikler uygulamayla ilgili konular açıklanmaktadır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

- [Salt okunurdur ve salt yazılır özellikler](#_core_read2donly_and_write2donly_properties)

- [Bir özellikten hata kodları döndürülüyor](#_core_returning_error_codes_from_a_property)

## <a name="read-only-and-write-only-properties"></a><a name="_core_read2donly_and_write2donly_properties"></a>Salt okunurdur ve salt yazılır özellikler

Özellik Ekleme Sihirbazı, denetimin salt okunurdur veya salt yazılır özelliklerini uygulamak için hızlı ve kolay bir yöntem sağlar.

#### <a name="to-implement-a-read-only-or-write-only-property"></a>Salt okunurdur veya salt yazılır bir özelliği uygulamak için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü, denetiminizin kitaplık düğümünü genişletin.

1. Kısayol menüsünü açmak için denetiminizin arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Özellik Ekle**' ye tıklayın.

   Bu, [Özellik Ekleme Sihirbazı](../ide/names-add-property-wizard.md)' nı açar.

1. **Özellik adı** kutusuna, özelliğin adını yazın.

1. **Uygulama türü**Için, **get/set yöntemleri**' ne tıklayın.

1. **Özellik türü** kutusunda, özellik için uygun türü seçin.

1. Salt okunurdur bir özelliği istiyorsanız, küme işlev adını temizleyin. Yalnızca bir salt yazılır özelliği istiyorsanız, Get işlev adını temizleyin.

1. **Son**'a tıklayın.

Bunu yaptığınızda Özellik Ekleme Sihirbazı, `SetNotSupported` `GetNotSupported` normal bir set veya Get işlevinin yerine, veya dağıtım eşleme girişinde işlevi ekler.

Varolan bir özelliği salt okunurdur veya salt yazılır olacak şekilde değiştirmek istiyorsanız, dağıtım haritasını el ile düzenleyebilir ve Denetim sınıfından gereksiz set veya Get işlevini kaldırabilirsiniz.

Bir özelliğin koşullu olarak salt okunurdur veya salt yazılır olmasını istiyorsanız (örneğin, yalnızca denetiminiz belirli bir modda çalışırken), set veya Get işlevini normal olarak sağlayabilir ve `SetNotSupported` `GetNotSupported` uygun yerlerde or işlevini çağırabilirsiniz. Örnek:

[!code-cpp[NVC_MFC_AxUI#29](codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]

Bu kod örneği `SetNotSupported` , `m_bReadOnlyMode` veri üyesi **true**ise çağırır. **Yanlışsa**, özelliği yeni değere ayarlanır.

## <a name="returning-error-codes-from-a-property"></a><a name="_core_returning_error_codes_from_a_property"></a>Bir özellikten hata kodları döndürülüyor

Bir özelliği almaya veya ayarlamaya çalışırken bir hata oluştuğunu göstermek için bir `COleControl::ThrowError` parametre olarak BIR SCODE (durum kodu) alan işlevini kullanın. Önceden tanımlanmış bir SCODE kullanabilir veya kendi kendinize birini tanımlayabilirsiniz. Önceden tanımlanmış SCODEs ve özel SCODEs tanımlama yönergelerinin bir listesi için bkz. ActiveX denetimlerinde [hataları işleme](mfc-activex-controls-advanced-topics.md) , ActiveX denetimleri: gelişmiş konular.

[Coelcontrol:: SetNotSupported](reference/colecontrol-class.md#setnotsupported), [Cohancontrol:: GetNotSupported](reference/colecontrol-class.md#getnotsupported)ve Cotacontrol:: [setnotizin verilen](reference/colecontrol-class.md#setnotpermitted)en yaygın önceden tanımlanmış SCODEs için yardımcı işlevler mevcuttur.

> [!NOTE]
> `ThrowError`, bir özelliğin get veya set işlevi ya da bir otomasyon yöntemi içinden bir hata döndürmesinin bir yolu olarak kullanılmak üzere tasarlanmıştır. Bunlar, uygun özel durum işleyicisinin yığında mevcut olacağı tek zamanlardır.

Kodun diğer alanlarındaki özel durumları raporlama hakkında daha fazla bilgi için, bkz. [COleControl:: FireError](reference/colecontrol-class.md#fireerror) ve ActiveX [denetimindeki hataları işleme](mfc-activex-controls-advanced-topics.md) başlıklı makale, ActiveX denetimleri: gelişmiş konular.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Özellikler](mfc-activex-controls-properties.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](mfc-activex-controls-methods.md)<br/>
[Coelcontrol sınıfı](reference/colecontrol-class.md)
