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
ms.openlocfilehash: c7cdd5cd2327be1b90e7fdb3694353acf8adcafe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394560"
---
# <a name="onidle-member-function"></a>OnIdle Üye İşlevi

Windows ileti işlenmekte olan framework çağırır [CWinApp](../mfc/reference/cwinapp-class.md) üye işlevi [ONIDLE](../mfc/reference/cwinapp-class.md#onidle) (MFC Kitaplığı Başvurusu içinde açıklanmıştır).

Geçersiz kılma `OnIdle` arka plan görevleri gerçekleştirmek için. Varsayılan sürüm araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerinin durumunu güncelleştirir ve temizleme işlemlerini sırasında framework tarafından oluşturulan geçici nesnelerin gerçekleştirir. İleti döngüsünden çağırması aşağıdaki şekilde gösterilmiştir `OnIdle` kuyrukta ileti olduğunda.

![İleti döngüsü işlemi](../mfc/media/vc387c1.gif "ileti döngüsü işlemi") <br/>
İleti döngüsü

Boşta döngü içinde neler yapabileceğiniz hakkında daha fazla bilgi için bkz. [boşta döngü işleme](../mfc/idle-loop-processing.md).

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
