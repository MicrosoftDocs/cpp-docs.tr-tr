---
title: ATL ileti işleyicisi ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
ms.openlocfilehash: 6d812c70e7cec4739ee9477d30ad9744b4fddc50
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565509"
---
# <a name="adding-an-atl-message-handler"></a>ATL ileti işleyicisi ekleme

Bir ileti işleyicisi (Windows iletilerini işleme bir üye işlevi) için bir denetim eklemek için ilk sınıf Görünümü'nde denetimi seçin. Açılacağını **özellikleri** penceresinde **iletileri** simgesi ve açılan denetim gerekli ileti ters kutusuna tıklayın. İleti işleyicisi için bir bildirim bu denetimin üst bilgi dosyası ve denetim .cpp dosyası işleyicisinde bir çatı uygulaması ekler. Ayrıca ileti eşlemesi eklemek ve işleyici için bir giriş ekleyin.

ATL ileti işleyicisi ekleme, bir MFC sınıfı için ileti işleyicisi ekleme ile benzerdir. Bkz: [MFC ileti işleyicisi ekleme](../mfc/reference/adding-an-mfc-message-handler.md) daha fazla bilgi için.

ATL ileti işleyicisi ekleme için yalnızca aşağıdaki koşullar geçerlidir:

- İleti işleyicileri MFC adlandırma kuralını uygulayın.

- Yeni ileti eşlemesi girişleri ana ileti eşlemesine eklenir. Sihirbaz, diğer ileti eşlemeleri ve zincirleme algılamaz.

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Uygulama](../atl/implementing-a-window.md)

