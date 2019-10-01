---
title: Kod sihirbazları Ile denetimlere tür kullanımı uyumlu erişim
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: fefa722209d37e2612201c4471e5764f9d71f27a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685042"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>Kod sihirbazları Ile denetimlere tür kullanımı uyumlu erişim

DDX özelliklerine alışkın değilseniz, tür kullanımı uyumlu erişim oluşturmak için [üye değişkeni Ekleme Sihirbazı](../ide/add-member-variable-wizard.md) ' nda denetim özelliğini kullanabilirsiniz. Bu yaklaşım, kod sihirbazları olmadan denetim oluşturmaktan daha kolay.

Yalnızca bir denetimin değerine erişmek istiyorsanız, DDX bunu sağlar. Bir denetimin değerine erişimi daha fazla yapmak istiyorsanız, iletişim sınıfınızın uygun sınıfının üye değişkenini eklemek için üye değişkeni Ekleme Sihirbazı ' nı kullanın. Bu üye değişkenini denetim özelliğine iliştirin.

Üye değişkenlerinin bir değer özelliği yerine bir denetim özelliği olabilir. Value özelliği, `CString` veya **int**gibi denetimden döndürülen verilerin türünü ifade eder. Denetim özelliği, türü MFC 'deki denetim sınıflarından biri olan `CButton` veya `CEdit` gibi bir veri üyesi aracılığıyla denetime doğrudan erişim sağlar.

> [!NOTE]
>  Belirli bir denetim için, isterseniz değer özelliğine sahip birden çok üye değişkeni ve denetim özelliğiyle en fazla bir üye değişkeni kullanabilirsiniz. Bir denetime bağlanmış birden fazla nesne veya başka bir pencere, ileti eşlemesindeki bir belirsizliğe yol açacağından, bir denetimle eşlenmiş yalnızca bir MFC nesneniz olabilir.

Denetim nesnesi için herhangi bir üye işlevi çağırmak üzere bu nesneyi kullanabilirsiniz. Bu tür çağrılar iletişim kutusundaki denetimi etkiler. Örneğin, `CButton` türünde bir *m_Checkbox*değişkeni tarafından temsil edilen bir onay kutusu denetimi için şunu çağırabilirsiniz:

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

Burada *m_Checkbox* üye değişkeni, [kod sihirbazları olmayan denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-without-code-wizards.md)bölümünde gösterilen `GetMyCheckbox` üye işleviyle aynı amaca hizmet eder. Onay kutusu bir otomatik onay kutusu değilse, düğmeye tıklandığında BN_CLICKED Control-Notification iletisi için iletişim sınıfınızın bir işleyicisine ihtiyacınız vardır.

Denetimler hakkında daha fazla bilgi için bkz. [denetimler](../mfc/controls-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Iletişim kutusundaki denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Kod sihirbazları olmadan denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-without-code-wizards.md)
