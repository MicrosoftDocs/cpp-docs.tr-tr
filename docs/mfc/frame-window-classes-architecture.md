---
title: Çerçeve Penceresi Sınıfları (Mimari)
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: 483112d197b7c7211989ecda8b774deb9f30d49e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624601"
---
# <a name="frame-window-classes-architecture"></a>Çerçeve Penceresi Sınıfları (Mimari)

Belge/görünüm mimarisinde, çerçeve pencereleri bir görünüm penceresi içeren Windows ' dir. Ayrıca, bunlara eklenmiş denetim çubuklarının olmasını da destekler.

Birden çok belge arabirimi (MDI) uygulamasında ana pencere öğesinden türetilir `CMDIFrameWnd` . Dolaylı olarak, nesneler olan belgelerin çerçevelerini içerir `CMDIChildWnd` . `CMDIChildWnd`Nesneler, sırasıyla belgelerin görünümlerini içerir.

Tek belge arabirimi (SDI) uygulamalarında, öğesinden türetilen ana pencere, `CFrameWnd` geçerli belgenin görünümünü içerir.

[CFrameWnd](reference/cframewnd-class.md)<br/>
SDI uygulamasının ana çerçeve penceresi için temel sınıf. Ayrıca tüm diğer çerçeve pencere sınıfları için temel sınıf.

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
MDI uygulamasının ana çerçeve penceresi için temel sınıf.

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
MDI uygulamasının belge çerçeve pencereleri için temel sınıf.

[COleIPFrameWnd](reference/coleipframewnd-class.md)<br/>
Bir sunucu belgesi yerinde düzenlenirken bir görünüm için çerçeve penceresi sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
