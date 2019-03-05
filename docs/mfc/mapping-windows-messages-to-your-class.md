---
title: Windows İletilerini Sınıfınıza Eşleme
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
ms.openlocfilehash: 7e15f52e41d4ac91a839629342258128db86e2d5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326679"
---
# <a name="mapping-windows-messages-to-your-class"></a>Windows İletilerini Sınıfınıza Eşleme

Windows iletilerini işlemek için iletişim kutusu gerekiyorsa, uygun bir işleyici işlevleri geçersiz kılar. Bunu yapmak için için Özellikler penceresini kullanın. [ileti eşlemesi](../mfc/reference/mapping-messages-to-functions.md) iletişim kutusu sınıfı için. Bu, her ileti için bir ileti eşleme girişi yazar ve sınıfa ileti işleyicisi üye işlevleri ekler. İleti işleyicileri kod yazmak için Visual C++ kaynak kod Düzenleyicisi'ni kullanın.

Ayrıca, üye işlevlerinin geçersiz kılabilirsiniz [CDialog](../mfc/reference/cdialog-class.md) ve temel sınıfları, özellikle [CWnd](../mfc/reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md)

- [Yaygın olarak geçersiz kılınan üye işlevleri](../mfc/commonly-overridden-member-functions.md)

- [Yaygın olarak eklenen üye işlevleri](../mfc/commonly-added-member-functions.md)

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)
