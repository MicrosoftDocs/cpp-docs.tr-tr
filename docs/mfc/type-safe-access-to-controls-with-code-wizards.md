---
title: Kod Sihirbazları Kullanarak Denetimlere Tür Kullanımı Uyumlu Erişim
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: b49c1b6f21dfe5270e40649241812320303ad411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370912"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>Kod Sihirbazları Kullanarak Denetimlere Tür Kullanımı Uyumlu Erişim

DDX özelliklerini biliyorsanız, üye [değişken ilerle](../ide/add-member-variable-wizard.md) sihirbazındaki Denetim özelliğini kullanarak tür için güvenli erişim oluşturabilirsiniz. Bu yaklaşım, kod sihirbazları olmadan denetimoluşturmaktan daha kolaydır.

Yalnızca bir denetimin değerine erişmek istiyorsanız, DDX bunu sağlar. Bir denetimin değerine erişmekten daha fazlasını yapmak istiyorsanız, iletişim sınıfınıza uygun sınıfın üye değişkenini eklemek için Üye Değişken Ekle Sihirbazı'nı kullanın. Bu üye değişkeni Denetim özelliğine takın.

Üye değişkenler, Değer özelliği yerine denetim özelliğine sahip olabilir. Değer özelliği, denetimden döndürülen veri türünü ifade `CString` eder, **örneğin.** Denetim özelliği, türü MFC'deki kontrol sınıflarından biri olan bir veri üyesi aracılığıyla `CButton` `CEdit`denetime doğrudan erişim sağlar, örneğin.

> [!NOTE]
> Belirli bir denetim için, isterseniz, Değer özelliğine sahip birden çok üye değişkene ve Denetim özelliğine sahip en fazla bir üye değişkene sahip olabilirsiniz. Denetime veya başka bir pencereye bağlı birden çok nesne ileti haritasında belirsizliğe yol açacağından, denetime eşlenen yalnızca bir MFC nesnesi olabilir.

Denetim nesnesi için herhangi bir üye işlevleri çağırmak için bu nesneyi kullanabilirsiniz. Bu tür çağrılar iletişim kutusundaki denetimi etkiler. Örneğin, bir değişken *m_Checkbox*ile temsil edilen bir onay `CButton`kutusu denetimi için, türü , arayabilirsiniz:

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

Burada üye değişken *m_Checkbox* Kod `GetMyCheckbox` [Sihirbazları Olmadan Denetimlere Giriş-Güvenli Erişim'de](../mfc/type-safe-access-to-controls-without-code-wizards.md)gösterilen üye işlevle aynı amaca hizmet eder. Onay kutusu otomatik onay kutusu değilse, düğme tıklatıldığında BN_CLICKED denetim bildirimi iletisi için iletişim sınıfınızda yine de bir işleyicigerekir.

Denetimler hakkında daha fazla bilgi için [Denetimler'e](../mfc/controls-mfc.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Bir İletişim Kutusundaki Denetimlere Tür Kullanımı Uyumlu Erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Kod Sihirbazları Olmadan Denetimlere Tür Kullanımı Uyumlu Erişim](../mfc/type-safe-access-to-controls-without-code-wizards.md)
