---
title: Üye işlevini çalıştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 446b1b6fc2a5265e2c4eb8a608ff8b4f0028c57d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408238"
---
# <a name="run-member-function"></a>Üye İşlevini Çalıştırma

Çoğu, zaman içinde bir framework uygulamasına geçirdiği [çalıştırma](../mfc/reference/cwinapp-class.md#run) sınıfının üye işlevinde [CWinApp](../mfc/reference/cwinapp-class.md). Başlatma sonra `WinMain` çağrıları `Run` ileti döngüsü işlenecek.

`Run` mesaj kuyruğu kullanılabilir iletiler için denetimi bir ileti döngüsü arasında geçiş yapar. Bir ileti olup olmadığını `Run` eylemi için gönderir. İleti kullanılabilir değilse, genellikle true ise `Run` çağrıları `OnIdle` Bitti, veya framework gereken tüm boşta kalma süresi işleme yapmak için. Hiçbir iletiler ve boşta hiçbir işleme yapmak için varsa, uygulama bir şey kadar bekler. Uygulama sonlandırıldığında `Run` çağrıları `ExitInstance`. Aşağıdaki şekilde [ONIDLE üye işlevi](../mfc/onidle-member-function.md) ileti döngüsü eylemlerin sırasını gösterir.

İleti gönderme, ileti türüne bağlıdır. Daha fazla bilgi için [iletiler ve komutlar Framework](../mfc/messages-and-commands-in-the-framework.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
