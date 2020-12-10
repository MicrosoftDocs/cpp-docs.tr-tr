---
title: Microsoft Foundation Sınıfları (MFC) uygulama mimarisi sınıfları
description: Microsoft Foundation Class (MFC) kitaplığı uygulama mimarisi sınıflarına genel bakış.
ms.date: 12/08/2020
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.openlocfilehash: 65aa9707d361c6d014c67c0f9ff1af86e19087de
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933202"
---
# <a name="mfc-application-architecture-classes"></a>MFC uygulama mimarisi sınıfları

Bu kategorideki Microsoft Foundation Class Library (MFC) sınıfları bir MFC uygulamasının mimarisine katkıda bulunur. Çoğu uygulama için ortak işlevsellik sağlar. Uygulamaya özgü işlevselliği eklemek için çerçeveyi doldurursunuz. Genellikle, mimari sınıflarından yeni sınıfları türeterek ve sonra yeni üyeler ekleyerek veya var olan üye işlevlerini geçersiz kılarak bunu yapabilirsiniz.

[Uygulama sihirbazları](reference/mfc-application-wizard.md) , hepsi uygulama çerçevesini farklı yollarla kullanan birkaç tür uygulama oluşturur. SDI (tek belge arabirimi) ve MDI (birden çok belge arabirimi) uygulamaları, Framework 'ün belge/görünüm bölümünü tam olarak kullanır. İletişim kutusu tabanlı uygulamalar, form tabanlı uygulamalar ve DLL 'Ler gibi diğer uygulama türleri yalnızca bazı belge/görünüm mimarisi özelliklerini kullanır.

Belge/görünüm uygulamaları bir veya daha fazla belge, görünüm ve çerçeve penceresi içerir. Bir belge-şablon nesnesi, sınıfları her belge/görünüm/çerçeve kümesi için ilişkilendirir.

MFC uygulamanızda belge/görünüm mimarisi kullanmanız gerekmez, ancak bunu yapmanın bazı avantajları vardır. MFC OLE kapsayıcısı ve sunucu desteği, yazdırma ve Baskı Önizleme desteği gibi belge/görünüm mimarisine dayalıdır.

Tüm MFC uygulamalarının en az iki nesnesi vardır: öğesinden türetilen bir uygulama nesnesi [`CWinApp`](reference/cwinapp-class.md) ve bir dizi ana pencere nesnesi (genellikle dolaylı olarak) öğesinden türetilir [`CWnd`](reference/cwnd-class.md) . (Çoğu zaman, ana pencere [`CFrameWnd`](reference/cframewnd-class.md) ,, [`CMDIFrameWnd`](reference/cmdiframewnd-class.md) veya ' den türetilir [`CDialog`](reference/cdialog-class.md) `CWnd` .)

Belge/görünüm mimarisi kullanan uygulamalar ek nesneler içerir. Ana nesneler şunlardır:

- Daha önce belirtildiği gibi sınıfından türetilmiş bir uygulama nesnesi [`CWinApp`](reference/cwinapp-class.md) .
- Sınıftan türetilmiş bir veya daha fazla belge sınıfı nesnesi [`CDocument`](reference/cdocument-class.md) . Belge sınıfı nesneleri, görünümde yönetilen verilerin iç gösteriminden sorumludur. Bu, bir veri dosyası ile ilişkilendirilebilir.
- Sınıftan türetilmiş bir veya daha fazla görünüm nesnesi [`CView`](reference/cview-class.md) . Her görünüm, bir belgeye iliştirilmiş ve bir çerçeve penceresiyle ilişkilendirilen bir penceredir. Görünümler bir belge sınıfı nesnesinde bulunan verileri görüntüler ve işleyebilir.

Belge/görünüm uygulamaları Ayrıca çerçeve pencerelerini (öğesinden türetilmiş [`CFrameWnd`](reference/cframewnd-class.md) ) ve belge şablonlarını (öğesinden türetilir [`CDocTemplate`](reference/cdoctemplate-class.md) ) içerir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)