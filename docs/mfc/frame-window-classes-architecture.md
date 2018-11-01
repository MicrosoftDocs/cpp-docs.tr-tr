---
title: Çerçeve Penceresi Sınıfları (Mimari)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: d1022d9a49e12585a6588e7b3202155f533e4706
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431713"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

