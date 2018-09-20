---
title: ONIDLE üye işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnIdle
dev_langs:
- C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b334a4561af40b69bc367ab5b1129afa8fb29ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377306"
---
# <a name="onidle-member-function"></a>OnIdle Üye İşlevi

Windows ileti işlenmekte olan framework çağırır [CWinApp](../mfc/reference/cwinapp-class.md) üye işlevi [ONIDLE](../mfc/reference/cwinapp-class.md#onidle) (MFC Kitaplığı Başvurusu içinde açıklanmıştır).

Geçersiz kılma `OnIdle` arka plan görevleri gerçekleştirmek için. Varsayılan sürüm araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerinin durumunu güncelleştirir ve temizleme işlemlerini sırasında framework tarafından oluşturulan geçici nesnelerin gerçekleştirir. İleti döngüsünden çağırması aşağıdaki şekilde gösterilmiştir `OnIdle` kuyrukta ileti olduğunda.

![İleti döngüsü işlemi](../mfc/media/vc387c1.gif "vc387c1") ileti döngüsü

Boşta döngü içinde neler yapabileceğiniz hakkında daha fazla bilgi için bkz. [boşta döngü işleme](../mfc/idle-loop-processing.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
