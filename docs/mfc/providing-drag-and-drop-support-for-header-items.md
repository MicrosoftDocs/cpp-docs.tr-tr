---
title: Üstbilgi öğeleri için sürükle ve bırak desteği sağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2eaa5040d34a442868a8fa6cb9f2aae08b0a6f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407705"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Üstbilgi Öğeleri için Sürükle ve Bırak Desteği Sağlama

Üstbilgi öğeleri için sürükle ve bırak desteği sağlamak için HDS_DRAGDROP stili belirtin. Üstbilgi öğeleri için sürükle ve bırak desteği, kullanıcı bir üst bilgi denetiminin üst öğeleri yeniden sıralamak olanağı sağlar. Üstbilgi öğesi kesilirse varsayılan davranışı sürüklenen üstbilgi öğesi yarı saydam fırçalarla Sürükle görüntüsü ve yeni konumu, görsel bir gösterge sağlar.

Olarak ortak sürükle ve bırak işleviyle, sürükle ve bırak davranışı HDN_BEGINDRAG ve HDN_ENDDRAG bildirimleri işleyerek genişletebilirsiniz. Geçersiz kılarak görüntüyü Sürükle görünümünü özelleştirebilirsiniz [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) üye işlevi.

> [!NOTE]
>  Liste denetimi bir katıştırılmış üstbilgi denetimindeki için sürükle ve bırak desteği sağlama, genişletilmiş stili bölümüne bakın. [liste denetim stillerini değiştirme](../mfc/changing-list-control-styles.md) konu.

## <a name="see-also"></a>Ayrıca Bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)

