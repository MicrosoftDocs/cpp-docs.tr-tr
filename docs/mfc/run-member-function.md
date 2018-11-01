---
title: Üye İşlevini Çalıştırma
ms.date: 11/04/2016
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
ms.openlocfilehash: 8e6e74b8f0fd62f96d6d846bbba867f9189550ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666862"
---
# <a name="run-member-function"></a>Üye İşlevini Çalıştırma

Çoğu, zaman içinde bir framework uygulamasına geçirdiği [çalıştırma](../mfc/reference/cwinapp-class.md#run) sınıfının üye işlevinde [CWinApp](../mfc/reference/cwinapp-class.md). Başlatma sonra `WinMain` çağrıları `Run` ileti döngüsü işlenecek.

`Run` mesaj kuyruğu kullanılabilir iletiler için denetimi bir ileti döngüsü arasında geçiş yapar. Bir ileti olup olmadığını `Run` eylemi için gönderir. İleti kullanılabilir değilse, genellikle true ise `Run` çağrıları `OnIdle` Bitti, veya framework gereken tüm boşta kalma süresi işleme yapmak için. Hiçbir iletiler ve boşta hiçbir işleme yapmak için varsa, uygulama bir şey kadar bekler. Uygulama sonlandırıldığında `Run` çağrıları `ExitInstance`. Aşağıdaki şekilde [ONIDLE üye işlevi](../mfc/onidle-member-function.md) ileti döngüsü eylemlerin sırasını gösterir.

İleti gönderme, ileti türüne bağlıdır. Daha fazla bilgi için [iletiler ve komutlar Framework](../mfc/messages-and-commands-in-the-framework.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
