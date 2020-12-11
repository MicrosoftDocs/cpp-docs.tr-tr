---
description: 'Daha fazla bilgi edinin: OnIdle üye Işlevi'
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
ms.openlocfilehash: a094b72f78db75d9f0f93ffa840d1d90cc96294c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112264"
---
# <a name="onidle-member-function"></a>OnIdle Üye İşlevi

Hiçbir Windows iletisi işlenmediği zaman, çerçeve, [CWinApp](reference/cwinapp-class.md) üye Işlevini [OnIdle](reference/cwinapp-class.md#onidle) olarak çağırır (MFC kitaplık başvurusunda açıklanmıştır).

`OnIdle`Arka plan görevlerini gerçekleştirmek için geçersiz kılın. Varsayılan sürüm, araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerinin durumunu güncelleştirir ve işlemleri sırasında Framework tarafından oluşturulan geçici nesneleri temizlemeyi gerçekleştirir. Aşağıdaki şekilde, kuyrukta ileti olmadığında ileti döngüsünün nasıl çağırdığı gösterilmektedir `OnIdle` .

![İleti döngüsü işlemi](../mfc/media/vc387c1.gif "İleti döngüsü işlemi") <br/>
Ileti döngüsü

Boşta döngüsünde yapabilecekleriniz hakkında daha fazla bilgi için bkz. [boşta döngüsü işleme](idle-loop-processing.md).

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: uygulama sınıfı](cwinapp-the-application-class.md)
