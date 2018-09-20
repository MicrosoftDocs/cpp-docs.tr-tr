---
title: 'MFC ActiveX denetimleri: Gelişmiş özellik uygulama | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4aa1116384ac9fd5212046f9a0b3354a3aa70d88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416090"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX Denetimleri: Gelişmiş Özellik Uygulama

Bu makalede, bir ActiveX denetimi özelliklerini Gelişmiş uygulama için ilgili konuları açıklanır.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerini modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

- [Salt okunur ve salt yazılır Özellikler](#_core_read2donly_and_write2donly_properties)

- [Bir özellikten hata kodları döndürme](#_core_returning_error_codes_from_a_property)

##  <a name="_core_read2donly_and_write2donly_properties"></a> Salt okunur ve salt yazılır Özellikler

Özellik Ekleme Sihirbazı'nı denetimi için salt okunur veya salt yazılır özellikler uygulamak için hızlı ve kolay bir yöntem sağlar.

#### <a name="to-implement-a-read-only-or-write-only-property"></a>Bir salt okunur veya salt yazılır özelliği uygulamak için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde denetim kitaplığı düğümünü genişletin.

1. Arabirim (ikinci düğüm kitaplığı düğümünün) denetlemek için kısayol menüsünü açmak için düğümü.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Özellik Ekle**.

     Bu açılır [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md).

1. İçinde **özellik adı** , özelliğin adını yazın.

1. İçin **uygulama türü**, tıklayın **Get/Set yöntemleri**.

1. İçinde **özellik türü** kutusunda, uygun türde bir özellik için seçin.

1. Salt okunur bir özellik kümesi işlevi adı temizleyin. Salt yazılır özellik Get işlev adı temizleyin.

9. **Son**'a tıklayın.

Bunu yaptığınızda, Özellik Ekleme Sihirbazı'nı işlevi ekler `SetNotSupported` veya `GetNotSupported` yerine normal bir dağıtım eşleme girişi ayarlayın veya alın işlevi.

Salt okunur veya sadece yazılabilir olması için var olan bir özelliği değiştirmek istiyorsanız, dağıtım eşlemesi el ile düzenlemeniz ve gereksiz ayarlama veya alma işlevi denetim sınıfından kaldırın.

Bir özellik koşullu olarak salt okunur veya salt yazılır (örneğin, yalnızca belirli bir modunda denetiminiz çalışırken) olmasını istiyorsanız, normal, ayarlama veya alma işlevi sağlar ve çağrı `SetNotSupported` veya `GetNotSupported` uygun yerlerde işlev. Örneğin:

[!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]

Bu kod örneği çağrıları `SetNotSupported` varsa `m_bReadOnlyMode` veri üyesi **TRUE**. Varsa **FALSE**, özelliği, yeni değere ayarlanır.

##  <a name="_core_returning_error_codes_from_a_property"></a> Bir özellikten hata kodları döndürme

Get veya özellik ayarlama girişimi sırasında bir hata oluştu belirtmek için kullanın `COleControl::ThrowError` işlevinin bir ' % s'SCODE (durum kodu) parametre olarak alır. Önceden tanımlanmış SCODE kullanabilir veya kendi tanımlayın. Önceden tanımlanmış SCODEs ve özel SCODEs tanımlamaya yönelik yönergeler listesi için bkz. [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) makale ActiveX denetimleri: Gelişmiş Konular.

Yardımcı işlevleri mevcut SCODEs, en yaygın gibi önceden tanımlanmış [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), ve [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

> [!NOTE]
>  `ThrowError` bir özelliğin Get veya Set içindeki bir hatadan döndüren yalnızca bir yol olarak kullanılmak üzere tasarlanmıştır işlevi veya Otomasyon yöntemi. Yalnızca bunlar uygun özel durum işleyicisi olacak kez yığında sunar.

Diğer alanlarda özel durumları kodun Raporlama ile ilgili daha fazla bilgi için [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) ve bölüm [bilgisayarınızı ActiveX denetiminde hata işleme](../mfc/mfc-activex-controls-advanced-topics.md) makalede ActiveX denetimleri: Gelişmiş Konuları.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
