---
title: 'MFC ActiveX Denetimleri: Gelişmiş Özellik Uygulama'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
ms.openlocfilehash: d4f1265e6540e9f84bdb680e7948a4e308d31bb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364645"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX Denetimleri: Gelişmiş Özellik Uygulama

Bu makalede, activex denetiminde gelişmiş özelliklerin uygulanmasıyla ilgili konular açıklanmaktadır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

- [Salt okunur ve yalnızca yazma özellikleri](#_core_read2donly_and_write2donly_properties)

- [Bir özellikten hata kodlarını döndürme](#_core_returning_error_codes_from_a_property)

## <a name="read-only-and-write-only-properties"></a><a name="_core_read2donly_and_write2donly_properties"></a>Salt Okunur ve Yalnızca Yazma Özellikleri

Özellik Ekle Sihirbazı, denetim için salt okunur veya yalnızca yazma özelliklerini uygulamak için hızlı ve kolay bir yöntem sağlar.

#### <a name="to-implement-a-read-only-or-write-only-property"></a>Salt okunur veya yalnızca yazma özelliğini uygulamak için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü'nde, denetiminizin kitaplık düğümunu genişletin.

1. Kısayol menüsünü açmak için denetiminiz için arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Özellik Ekle'yi**tıklatın.

   Bu Özellik [Ekle Sihirbazı'nı](../ide/names-add-property-wizard.md)açar.

1. Özellik **Adı** kutusuna, mülkünuzun adını yazın.

1. **Uygulama Türü** **için, Yöntemleri Al/Ayarla'yı**tıklatın.

1. Özellik **Türü** kutusunda, özellik için uygun türü seçin.

1. Salt okunur bir özellik istiyorsanız, Set işlev adını temizleyin. Yalnızca yazma özelliği istiyorsanız, İşlev adını al'ı temizleyin.

1. **Son**'a tıklayın.

Bunu yaptığınızda, Özellik Ekle Sihirbazı işlevi `SetNotSupported` `GetNotSupported` ekler veya normal bir Küme veya Get işlevi yerine sevk haritası girişine.

Varolan bir özelliği salt okunur veya yalnızca yazacak şekilde değiştirmek istiyorsanız, gönderim eşlebini el ile değiştirebilir ve gereksiz Ayar veya Al işlevini denetim sınıfından kaldırabilirsiniz.

Bir özelliğin koşullu olarak salt okunur veya yalnızca yazma olmasını istiyorsanız (örneğin, denetiminiz yalnızca belirli bir modda çalışıyorsa), Normal `SetNotSupported` olarak `GetNotSupported` Ayarla veya Al işlevini sağlayabilir ve uygun olduğu durumlarda veya işlevi arayabilirsiniz. Örneğin:

[!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]

Veri üyesi **TRUE**ise bu kod örneği çağırır. `SetNotSupported` `m_bReadOnlyMode` **FALSE**ise, özellik yeni değere ayarlanır.

## <a name="returning-error-codes-from-a-property"></a><a name="_core_returning_error_codes_from_a_property"></a>Bir Özellikten Hata Kodlarını Döndürme

Bir özelliği almaya veya ayarlamaya çalışırken bir hata oluştuğunu belirtmek `COleControl::ThrowError` için, parametre olarak Bir SCODE (durum kodu) alan işlevi kullanın. Önceden tanımlanmış bir SCODE kullanabilir veya kendi kodunuzu tanımlayabilirsiniz. Önceden tanımlanmış SCOD'ların listesi ve özel SCOD'ları tanımlama yönergeleri için ActiveX denetimleri: Gelişmiş Konular makalesinde [ActiveX Denetiminizdeki İşlem Hataları'na](../mfc/mfc-activex-controls-advanced-topics.md) bakın.

Yardımcı işlevler [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported)ve [COleControl::SetNotAllowed](../mfc/reference/colecontrol-class.md#setnotpermitted)gibi en yaygın önceden tanımlanmış SCODEs için var .

> [!NOTE]
> `ThrowError`yalnızca bir mülkün Get or Set işlevi veya bir otomasyon yöntemi içinden bir hatayı döndürmek için kullanılır. Bunlar, yığında uygun özel durum işleyicisinin bulunacağı tek zamanlardır.

Kodun diğer alanlarındaki özel durumları raporlama hakkında daha fazla bilgi için [Bkz.](../mfc/reference/colecontrol-class.md#fireerror) [Handling Errors in Your ActiveX Control](../mfc/mfc-activex-controls-advanced-topics.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
