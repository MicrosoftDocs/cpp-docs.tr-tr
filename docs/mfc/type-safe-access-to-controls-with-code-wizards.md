---
description: 'Hakkında daha fazla bilgi edinin: kod sihirbazları Ile denetimlere erişim Type-Safe'
title: Kod Sihirbazları Kullanarak Denetimlere Tür Kullanımı Uyumlu Erişim
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: b68331df61c1586f4cc63413f162ac1af107ce88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263809"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>Kod Sihirbazları Kullanarak Denetimlere Tür Kullanımı Uyumlu Erişim

DDX özelliklerine alışkın değilseniz, tür kullanımı uyumlu erişim oluşturmak için [üye değişkeni Ekleme Sihirbazı](../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard) ' nda denetim özelliğini kullanabilirsiniz. Bu yaklaşım, kod sihirbazları olmadan denetim oluşturmaktan daha kolay.

Yalnızca bir denetimin değerine erişmek istiyorsanız, DDX bunu sağlar. Bir denetimin değerine erişimi daha fazla yapmak istiyorsanız, iletişim sınıfınızın uygun sınıfının üye değişkenini eklemek için üye değişkeni Ekleme Sihirbazı ' nı kullanın. Bu üye değişkenini denetim özelliğine iliştirin.

Üye değişkenlerinin bir değer özelliği yerine bir denetim özelliği olabilir. Value özelliği, denetimden döndürülen verilerin türünü (veya gibi) gösterir `CString` **`int`** . Denetim özelliği, türü MFC 'deki denetim sınıflarından biri olan veya gibi bir veri üyesi aracılığıyla denetime doğrudan erişim sağlar `CButton` `CEdit` .

> [!NOTE]
> Belirli bir denetim için, isterseniz değer özelliğine sahip birden çok üye değişkeni ve denetim özelliğiyle en fazla bir üye değişkeni kullanabilirsiniz. Bir denetime bağlanmış birden fazla nesne veya başka bir pencere, ileti eşlemesindeki bir belirsizliğe yol açacağından, bir denetimle eşlenmiş yalnızca bir MFC nesneniz olabilir.

Denetim nesnesi için herhangi bir üye işlevi çağırmak üzere bu nesneyi kullanabilirsiniz. Bu tür çağrılar iletişim kutusundaki denetimi etkiler. Örneğin, türünde bir değişken *m_Checkbox* temsil eden bir onay kutusu denetimi için şunu `CButton` çağırabilirsiniz:

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

Burada *m_Checkbox* üye değişkeni, `GetMyCheckbox` [kod sihirbazları olmayan denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-without-code-wizards.md)bölümünde gösterilen üye işleviyle aynı amaca hizmet eder. Onay kutusu bir otomatik onay kutusu değilse, düğmeye tıklandığında BN_CLICKED Control-Notification iletisi için iletişim sınıfınızın bir işleyicisine ihtiyacınız vardır.

Denetimler hakkında daha fazla bilgi için bkz. [denetimler](../mfc/controls-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Iletişim kutusundaki denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Kod sihirbazları olmadan denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-without-code-wizards.md)
