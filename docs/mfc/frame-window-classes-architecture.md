---
title: Çerçeve Penceresi Sınıfları (Mimari)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: affa217f481cc6d9e125d526f1b97be9120e0990
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392849"
---
# <a name="frame-window-classes-architecture"></a>Çerçeve Penceresi Sınıfları (Mimari)

Belge/görünüm mimarisi çerçeve pencereleri Görünümü penceresi içeren dizisidir. Bunlar da sahip denetim çubukları kendilerine iliştirilmiş destekler.

Ana pencereyi türetilir birden çok belge arabirimi (MDI) uygulamaları, `CMDIFrameWnd`. Olan belgelerin çerçeveler dolaylı olarak içerdiği `CMDIChildWnd` nesneleri. `CMDIChildWnd` Nesneleri, belge görünümleri içerir.

Tek Belgeli Arabirim (SDI) uygulamalar, ana penceresinde, türetilen `CFrameWnd`, geçerli belgenin görünümü içerir.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
Bir SDI uygulamanın ana çerçeve penceresi için taban sınıf. Ayrıca temel sınıf için tüm diğer çerçeve penceresi sınıfları.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
Bir MDI uygulamanın ana çerçeve penceresi için taban sınıf.

[Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md)<br/>
Bir MDI uygulamanın belge çerçeve pencereleri için temel sınıf.

[Coleıpframewnd](../mfc/reference/coleipframewnd-class.md)<br/>
Sunucu belgesinin yerinde düzenlenirken çerçeve penceresi için bir görünüm sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
