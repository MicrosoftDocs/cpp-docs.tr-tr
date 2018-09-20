---
title: Bir CStatusBarCtrl nesnesinin modunu ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b398fedb8637ae6ce539a876410222485054919b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409551"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl Nesnesinin Modunu Ayarlama

İçin iki mod vardır bir `CStatusBarCtrl` nesne: Basit ve basit olmayan. Çoğu durumda, bir veya daha fazla parça, metin ve belki simge veya simgeler yanı sıra, durum çubuğu denetimi olacaktır. Bu basit olmayan mod adı verilir. Bu mod hakkında daha fazla bilgi için bkz. [bir CStatusBarCtrl nesnesinin bölümlerini başlatma](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).

Ancak, yalnızca tek satırlık metin görüntülemek için gerek duyduğunuz durumlar vardır. Bu durumda, basit mod gereksinimleriniz için yeterli olur. Modunu değiştirmek için `CStatusBarCtrl` nesne için basit, çağrı yapmak [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) üye işlevi. Durum çubuğu denetimi basit modda olduğunda, metni çağırarak ayarlama `SetText` üye işlevi, 255 değeri olarak geçirerek *nPane* parametresi.

Kullanabileceğiniz [Issimple](../mfc/reference/cstatusbarctrl-class.md#issimple) hangi modu belirlemek için işlevi `CStatusBarCtrl` nesne olur.

> [!NOTE]
>  Nonsimple basit durum çubuğuna nesnesinin değiştiriliyor veya tam tersi penceresi hemen yeniden ve, varsa, tanımlanan tüm bölümleri otomatik olarak geri yüklenir.

## <a name="see-also"></a>Ayrıca Bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

