---
title: OnIdle Üye İşlevi
ms.date: 11/19/2018
f1_keywords:
- OnIdle
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
ms.openlocfilehash: 17595713f942c7fe7784fa2a12adbcc583cad418
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619842"
---
# <a name="onidle-member-function"></a>OnIdle Üye İşlevi

Hiçbir Windows iletisi işlenmediği zaman, çerçeve, [CWinApp](reference/cwinapp-class.md) üye Işlevini [OnIdle](reference/cwinapp-class.md#onidle) olarak çağırır (MFC kitaplık başvurusunda açıklanmıştır).

`OnIdle`Arka plan görevlerini gerçekleştirmek için geçersiz kılın. Varsayılan sürüm, araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerinin durumunu güncelleştirir ve işlemleri sırasında Framework tarafından oluşturulan geçici nesneleri temizlemeyi gerçekleştirir. Aşağıdaki şekilde, kuyrukta ileti olmadığında ileti döngüsünün nasıl çağırdığı gösterilmektedir `OnIdle` .

![İleti döngüsü işlemi](../mfc/media/vc387c1.gif "İleti döngüsü işlemi") <br/>
Ileti döngüsü

Boşta döngüsünde yapabilecekleriniz hakkında daha fazla bilgi için bkz. [boşta döngüsü işleme](idle-loop-processing.md).

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](cwinapp-the-application-class.md)
