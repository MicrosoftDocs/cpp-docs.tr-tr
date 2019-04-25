---
title: Üye İşlevini Çalıştırma
ms.date: 11/04/2016
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
ms.openlocfilehash: 8271a10ad7439d2795dcc45d667b23b0932a0486
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308556"
---
# <a name="run-member-function"></a>Üye İşlevini Çalıştırma

Çoğu, zaman içinde bir framework uygulamasına geçirdiği [çalıştırma](../mfc/reference/cwinapp-class.md#run) sınıfının üye işlevinde [CWinApp](../mfc/reference/cwinapp-class.md). Başlatma sonra `WinMain` çağrıları `Run` ileti döngüsü işlenecek.

`Run` mesaj kuyruğu kullanılabilir iletiler için denetimi bir ileti döngüsü arasında geçiş yapar. Bir ileti olup olmadığını `Run` eylemi için gönderir. İleti kullanılabilir değilse, genellikle true ise `Run` çağrıları `OnIdle` Bitti, veya framework gereken tüm boşta kalma süresi işleme yapmak için. Hiçbir iletiler ve boşta hiçbir işleme yapmak için varsa, uygulama bir şey kadar bekler. Uygulama sonlandırıldığında `Run` çağrıları `ExitInstance`. Aşağıdaki şekilde [ONIDLE üye işlevi](../mfc/onidle-member-function.md) ileti döngüsü eylemlerin sırasını gösterir.

İleti gönderme, ileti türüne bağlıdır. Daha fazla bilgi için [iletiler ve komutlar Framework](../mfc/messages-and-commands-in-the-framework.md).

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)
