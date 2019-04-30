---
title: Standart Komut Yönlendirmeyi Geçersiz Kılma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
ms.openlocfilehash: 5383c1053894d44e23baf51b19ac3df4e60158e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410167"
---
# <a name="overriding-the-standard-command-routing"></a>Standart Komut Yönlendirmeyi Geçersiz Kılma

Standart framework yönlendirme bazı değişim uygulamalıdır, nadir durumlarda, bu kılabilirsiniz. Geçersiz kılarak bir veya daha fazla sınıflarda yönlendirme değiştirmek için fikirdir `OnCmdMsg` bu sınıflarda. Bunu yapın:

- Sınıfta, varsayılan olmayan bir nesneye geçirilecek sırasını ayırır.

- Yeni bir varsayılan olmayan nesne ya da komut hedefleri komutları sırayla geçirebilirsiniz.

Yönlendirme içine yeni bir nesne eklemek isterseniz, sınıfı komut hedef sınıf olmalıdır. Geçersiz kılma, sürümlerinde `OnCmdMsg`, geçersiz kılma sürümle çağırdığınızdan emin olun. Bkz: [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) sınıfının üye işlevinde `CCmdTarget` içinde *MFC başvurusu* ve bu tür sınıflar sürümlerinde `CView` ve `CDocument` örnekler için sağlanan kaynak kodunda.

## <a name="see-also"></a>Ayrıca bkz.

[Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)
