---
description: 'Hakkında daha fazla bilgi edinin: Windows Iletilerini sınıfınıza eşleme'
title: Windows İletilerini Sınıfınıza Eşleme
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
ms.openlocfilehash: cca13c4b262c6373fa3d968438331d5e0ce5f7d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280787"
---
# <a name="mapping-windows-messages-to-your-class"></a>Windows İletilerini Sınıfınıza Eşleme

Windows iletilerini işlemek için iletişim kutusuna ihtiyacınız varsa, uygun işleyici işlevlerini geçersiz kılın. Bunu yapmak için **Çözüm Gezgini** **sınıf görünümü** sekmesini seçin, iletişim kutusunu temsil eden sınıfa sağ tıklayın ve [sınıf Sihirbazı](reference/mfc-class-wizard.md)' nı seçin. İletileri iletişim kutusu sınıfına [eşlemek](reference/mapping-messages-to-functions.md) için Sihirbazı kullanın. Bu, her ileti için bir ileti eşleme girişi yazar ve sınıfa ileti işleyici üye işlevlerini ekler. İleti işleyicilerinde kod yazmak için kod düzenleyicisini kullanın.

Ayrıca, [CDialog](reference/cdialog-class.md) üye işlevlerini ve temel sınıflarını, özellikle de [CWnd](reference/cwnd-class.md)' i geçersiz kılabilirsiniz.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [İleti işleme ve eşleme](message-handling-and-mapping.md)

- [Yaygın olarak geçersiz kılınan üye işlevleri](commonly-overridden-member-functions.md)

- [Yaygın olarak eklenen üye işlevleri](commonly-added-member-functions.md)

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](dialog-boxes.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
