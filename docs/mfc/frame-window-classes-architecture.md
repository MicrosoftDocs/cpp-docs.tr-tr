---
title: Çerçeve Penceresi Sınıfları (Mimari)
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: e3ae432c1adc881a5c67d6a6c292dc1f6a583ab3
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441259"
---
# <a name="frame-window-classes-architecture"></a>Çerçeve Penceresi Sınıfları (Mimari)

Belge/görünüm mimarisinde, çerçeve pencereleri bir görünüm penceresi içeren Windows ' dir. Ayrıca, bunlara eklenmiş denetim çubuklarının olmasını da destekler.

Birden çok belge arabirimi (MDI) uygulamasında ana pencere `CMDIFrameWnd`türetilir. Bu, dolaylı olarak `CMDIChildWnd` nesneler olan belgelerin çerçevelerini içerir. `CMDIChildWnd` nesneler, sırasıyla belgelerin görünümlerini içerir.

Tek belge arabirimi (SDI) uygulamalarında, `CFrameWnd`türetilen ana pencere, geçerli belgenin görünümünü içerir.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
SDI uygulamasının ana çerçeve penceresi için temel sınıf. Ayrıca tüm diğer çerçeve pencere sınıfları için temel sınıf.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
MDI uygulamasının ana çerçeve penceresi için temel sınıf.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
MDI uygulamasının belge çerçeve pencereleri için temel sınıf.

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
Bir sunucu belgesi yerinde düzenlenirken bir görünüm için çerçeve penceresi sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
