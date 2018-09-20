---
title: Standart komut yönlendirmeyi geçersiz kılma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33ee603f680919d69684ab94acfa0515d3ec6292
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439503"
---
# <a name="overriding-the-standard-command-routing"></a>Standart Komut Yönlendirmeyi Geçersiz Kılma

Standart framework yönlendirme bazı değişim uygulamalıdır, nadir durumlarda, bu kılabilirsiniz. Geçersiz kılarak bir veya daha fazla sınıflarda yönlendirme değiştirmek için fikirdir `OnCmdMsg` bu sınıflarda. Bunu yapın:

- Sınıfta, varsayılan olmayan bir nesneye geçirilecek sırasını ayırır.

- Yeni bir varsayılan olmayan nesne ya da komut hedefleri komutları sırayla geçirebilirsiniz.

Yönlendirme içine yeni bir nesne eklemek isterseniz, sınıfı komut hedef sınıf olmalıdır. Geçersiz kılma, sürümlerinde `OnCmdMsg`, geçersiz kılma sürümle çağırdığınızdan emin olun. Bkz: [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) sınıfının üye işlevinde `CCmdTarget` içinde *MFC başvurusu* ve bu tür sınıflar sürümlerinde `CView` ve `CDocument` örnekler için sağlanan kaynak kodunda.

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

