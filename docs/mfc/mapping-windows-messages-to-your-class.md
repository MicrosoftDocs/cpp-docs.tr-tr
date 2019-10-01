---
title: Windows Iletilerini sınıfınıza eşleme
ms.date: 09/06/2019
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
- Class Wizard [MFC]
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
ms.openlocfilehash: 0f1207faca56acd709db86478722eba85eeb284a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685613"
---
# <a name="mapping-windows-messages-to-your-class"></a>Windows Iletilerini sınıfınıza eşleme

Windows iletilerini işlemek için iletişim kutusuna ihtiyacınız varsa, uygun işleyici işlevlerini geçersiz kılın. Bunu yapmak için **Çözüm Gezgini** **sınıf görünümü** sekmesini seçin, iletişim kutusunu temsil eden sınıfa sağ tıklayın ve [sınıf Sihirbazı](reference/mfc-class-wizard.md)' nı seçin. İletileri iletişim kutusu sınıfına [eşlemek](../mfc/reference/mapping-messages-to-functions.md) için Sihirbazı kullanın. Bu, her ileti için bir ileti eşleme girişi yazar ve sınıfa ileti işleyici üye işlevlerini ekler. İleti işleyicilerinde kod yazmak için kod düzenleyicisini kullanın.

Ayrıca, [CDialog](../mfc/reference/cdialog-class.md) üye işlevlerini ve temel sınıflarını, özellikle de [CWnd](../mfc/reference/cwnd-class.md)' i geçersiz kılabilirsiniz.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md)

- [Yaygın olarak geçersiz kılınan üye işlevleri](../mfc/commonly-overridden-member-functions.md)

- [Yaygın olarak eklenen üye işlevleri](../mfc/commonly-added-member-functions.md)

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](../mfc/dialog-boxes.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
