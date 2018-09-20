---
title: İleti işleyicileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22dde243bb6d8e8a283e670804d4b8b6cad9082c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406756"
---
# <a name="message-handlers"></a>İleti İşleyicileri

MFC'de, ayrılmış bir *işleyici* işlevi her ayrı ileti işler. İleti işleyicisi, bir sınıfın üye işlevleri işlevlerdir. Bu belgede koşulları kullanılır *ileti işleyicisi üye işlevi*, *ileti işleyicisi işlevi*, *ileti işleyicisi*, ve *işleyici*birbirinin yerine. İleti işleyicileri bazı tür "komut işleyicileri" olarak da adlandırılır

İleti işleyicileri hesapları iş büyük bir kısmı için bir framework uygulaması yazma yazma. Bu makalede ailesi, ileti işleme mekanizması nasıl çalıştığını açıklar.

Bunu bir ileti işleyicisini yaptığı bu iletiye yanıt olarak yapılan istediğiniz yapar. Sınıf Özellikler penceresini kullanarak işleyicileri oluşturabilir ve ardından kaynak kod Düzenleyicisi'ni kullanarak işleyicinin kodunu doldurun.

Microsoft Visual C++ ve MFC akreditasyonlu tümünün İşleyicileriniz yazmak için kullanabilirsiniz. Tüm sınıflar listesi için bkz. [sınıf kitaplığına genel bakış](../mfc/class-library-overview.md) içinde *MFC başvurusu*.

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

