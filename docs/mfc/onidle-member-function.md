---
title: OnIdle Üye İşlevi
ms.date: 11/04/2016
f1_keywords:
- OnIdle
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
ms.openlocfilehash: 3d457c1675d5f5f3f88c67b1aac2d03509c21564
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662156"
---
# <a name="onidle-member-function"></a>OnIdle Üye İşlevi

Windows ileti işlenmekte olan framework çağırır [CWinApp](../mfc/reference/cwinapp-class.md) üye işlevi [ONIDLE](../mfc/reference/cwinapp-class.md#onidle) (MFC Kitaplığı Başvurusu içinde açıklanmıştır).

Geçersiz kılma `OnIdle` arka plan görevleri gerçekleştirmek için. Varsayılan sürüm araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerinin durumunu güncelleştirir ve temizleme işlemlerini sırasında framework tarafından oluşturulan geçici nesnelerin gerçekleştirir. İleti döngüsünden çağırması aşağıdaki şekilde gösterilmiştir `OnIdle` kuyrukta ileti olduğunda.

![İleti döngüsü işlemi](../mfc/media/vc387c1.gif "vc387c1") ileti döngüsü

Boşta döngü içinde neler yapabileceğiniz hakkında daha fazla bilgi için bkz. [boşta döngü işleme](../mfc/idle-loop-processing.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
