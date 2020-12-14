---
description: 'Daha fazla bilgi edinin: Run member Function'
title: Üye İşlevini Çalıştırma
ms.date: 11/04/2016
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
ms.openlocfilehash: ae67c6b02344a65735ce06775b1d1788d1dabf2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217828"
---
# <a name="run-member-function"></a>Üye İşlevini Çalıştırma

Bir çerçeve uygulaması, bu sürenin çoğunu [CWinApp](../mfc/reference/cwinapp-class.md)sınıfından [Çalıştır işlevini çalıştırmak](../mfc/reference/cwinapp-class.md#run) için zaman harcadığını. Başlatmadan sonra `WinMain` `Run` ileti döngüsünü işlemek için çağırır.

`Run` ileti döngüsünde, kullanılabilir iletiler için ileti kuyruğunu denetleyerek bir ileti döngüsü boyunca geçiş yapar. Kullanılabilir bir ileti varsa, `Run` bunu eylem için dağıtır. Genellikle doğru olan herhangi bir ileti yoksa, `Run` `OnIdle` sizin veya Framework 'ün yapılması gerekebilecek herhangi bir boşta kalma süresi işlemini yapmak için çağırır. Hiçbir ileti yoksa ve herhangi bir boşta işleme yoksa, uygulama bir işlem gerçekleşene kadar bekler. Uygulama sonlandırıldığında, `Run` çağırır `ExitInstance` . [OnIdle üye işlevindeki](../mfc/onidle-member-function.md) şekil, ileti döngüsündeki eylemlerin sırasını gösterir.

İleti gönderme, ileti türüne bağlıdır. Daha fazla bilgi için bkz. [Framework Içindeki iletiler ve komutlar](../mfc/messages-and-commands-in-the-framework.md).

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: uygulama sınıfı](../mfc/cwinapp-the-application-class.md)
