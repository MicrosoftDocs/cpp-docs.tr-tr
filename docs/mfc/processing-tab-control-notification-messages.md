---
title: Sekme denetimi bildirim iletilerini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b43bd125c43a11703f020951464fdf97f0ab374c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215030"
---
# <a name="processing-tab-control-notification-messages"></a>Sekme Denetimi Bildirim İletilerini İşleme
Kullanıcıları gibi sekmeler veya düğmeler, sekme denetiminin ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) üst pencereye bildirim iletileri gönderir. Yanıt bir şey yapmak istiyorsanız, bu iletileri işler. Örneğin, kullanıcı bir sekmeye tıkladığında denetim verilerini görüntülemeden önce sayfasında önceden isteyebilirsiniz.  
  
 Sekme denetimi, görünümü veya iletişim kutusu sınıfında gelen işlem wm_notıfy iletileri. Oluşturmak için Özellikler penceresini kullanın. bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch deyimi işleyicisi işlevini temel hangi bildirim iletisi ele alınır. Sekme denetimi üst pencereye gönderebilir bildirimler listesi için bkz. **bildirimleri** bölümünü [sekme denetim başvurusu](https://msdn.microsoft.com/library/windows/desktop/bb760548) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTabCtrl kullanma](../mfc/using-ctabctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

