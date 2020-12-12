---
description: 'Daha fazla bilgi edinin: ATL Ileti Işleyicisi ekleme'
title: ATL Ileti Işleyicisi ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
ms.openlocfilehash: 263cbcb863ee287c9b3f4650263a3fac33d7ab7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166349"
---
# <a name="adding-an-atl-message-handler"></a>ATL Ileti Işleyicisi ekleme

Bir denetime bir ileti işleyicisi (Windows iletilerini işleyen bir üye işlevi) eklemek için önce Sınıf Görünümü denetimi seçin. Ardından **Özellikler** penceresini açın, **iletiler** simgesini seçin ve gerekli iletinin karşısındaki kutuda açılan denetime tıklayın. Bu, denetimin üstbilgi dosyasındaki ileti işleyicisi için bir bildirim ve denetimin. cpp dosyasındaki işleyicinin bir iskelet uygulaması ekler. Ayrıca, ileti haritasını ekler ve işleyici için bir giriş ekler.

ATL 'de bir ileti işleyicisi eklemek, bir MFC sınıfına ileti işleyicisi eklemekle benzerdir. Daha fazla bilgi için bkz. [MFC Ileti Işleyicisi ekleme](../mfc/reference/adding-an-mfc-message-handler.md) .

Aşağıdaki koşullar yalnızca bir ATL ileti işleyicisi eklemek için geçerlidir:

- İleti işleyicileri MFC ile aynı adlandırma kuralını izler.

- Yeni ileti eşleme girdileri, ana ileti eşlemesine eklenir. Sihirbaz alternatif ileti eşlemelerini ve zincirlemeyi tanımıyor.

## <a name="see-also"></a>Ayrıca bkz.

[Pencere uygulama](../atl/implementing-a-window.md)
