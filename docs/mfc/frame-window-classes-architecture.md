---
title: Çerçeve penceresi sınıfları (Mimari) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 117554b2c34853aa166c12d80b4821d3721e5992
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394133"
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

