---
title: Kod Sihirbazları Kullanarak Denetimlere Tür Kullanımı Uyumlu Erişim
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: bf3ecf3016fcc15bd4ada7a15208acd9a04ca0a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180869"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>Kod Sihirbazları Kullanarak Denetimlere Tür Kullanımı Uyumlu Erişim

DDX özelliklerle bilginiz varsa, denetim özelliği kullanabileceğiniz [ekleme üye değişkeni Sihirbazı](../ide/add-member-variable-wizard.md) tür kullanımı uyumlu erişim oluşturmak için. Bu yaklaşım, kod sihirbazları olmadan denetimlere oluşturmaktan daha kolaydır.

Yalnızca bir denetimin değerini erişmek istiyorsanız, bunu DDX sağlar. Bir denetimin değerini birden fazla erişmek istiyorsanız, uygun sınıf üyesi değişkeninin iletişim sınıfınızı eklemek için üye değişkeni Ekleme Sihirbazı'nı kullanın. Bu üye değişkeni denetimi özelliğine ekleyin.

Üye değişkenleri Value özelliği yerine bir denetim özelliğine sahip olabilir. Value özelliği gibi denetiminden döndürdüğü veri türü başvurduğu `CString` veya **int**. Denetim özelliği denetim türü biridir, MFC denetim sınıfları gibi bir veri üyesi üzerinden doğrudan erişim sağlayan `CButton` veya `CEdit`.

> [!NOTE]
>  İsterseniz, belirli bir denetim için birden çok üye değişkenleri Value özelliği ve en fazla denetimi özelliğine sahip bir üye değişkeni olabilir. Bir denetim için birden çok nesne eklenmiş bir denetimi veya başka herhangi bir pencere ileti eşlemesi bir belirsizlik olmasına neden olur çünkü eşlenmiş yalnızca bir MFC nesne olabilir.

Herhangi bir üye işlevleri için denetim nesnesi çağırmak için bu nesneyi kullanabilirsiniz. Böyle çağrılar iletişim kutusu denetiminde etkiler. Örneğin, bir onay kutusu denetimi değişkeni tarafından temsil *m_Checkbox*, türü `CButton`, çağırabilirsiniz:

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

Burada bir üye değişkeni *m_Checkbox* üye işlevi aynı amaca hizmet eder `GetMyCheckbox` gösterilen [tür kullanımı uyumlu erişim için kod sihirbazları olmadan denetimleri](../mfc/type-safe-access-to-controls-without-code-wizards.md). Onay kutusunun seçilmiş bir otomatik onay kutusunu değilse düğmesine tıklandığında, yine de bir işleyici iletişim sınıfınızı BN_CLICKED denetimi bildirim iletileri için gerekir.

Denetimleri hakkında daha fazla bilgi için bkz. [denetimleri](../mfc/controls-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bir İletişim Kutusundaki Denetimlere Tür Kullanımı Uyumlu Erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Kod Sihirbazları Olmadan Denetimlere Tür Kullanımı Uyumlu Erişim](../mfc/type-safe-access-to-controls-without-code-wizards.md)
