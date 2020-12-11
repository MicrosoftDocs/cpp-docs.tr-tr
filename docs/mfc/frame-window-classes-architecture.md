---
description: 'Daha fazla bilgi edinin: çerçeve pencere sınıfları (mimari)'
title: Çerçeve Penceresi Sınıfları (Mimari)
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: 045108cd1e45325cf6069b5d8259ffab9abb0c2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155039"
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
