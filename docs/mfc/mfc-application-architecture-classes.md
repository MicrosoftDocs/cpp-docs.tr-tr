---
title: MFC Uygulama Mimarisi Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
ms.openlocfilehash: 1e09447623b32e9b10063af5bc91ac9589f45e44
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447726"
---
# <a name="mfc-application-architecture-classes"></a>MFC Uygulama Mimarisi Sınıfları

Bu kategorideki sınıflar, bir çerçeve uygulamasının mimarisine katkıda bulunur. Çoğu uygulama için ortak işlevsellik sağlar. Uygulamaya özgü işlevselliği eklemek için çerçeveyi doldurursunuz. Genellikle, mimari sınıflarından yeni sınıfları türeterek ve sonra yeni üyeler ekleyerek veya var olan üye işlevlerini geçersiz kılarak bunu yapabilirsiniz.

[Uygulama sihirbazları](../mfc/reference/mfc-application-wizard.md) , hepsi uygulama çerçevesini farklı yollarla kullanan birkaç tür uygulama oluşturur. SDI (tek belge arabirimi) ve MDI (birden çok belge arabirimi) uygulamaları, Framework 'ün belge/görünüm mimarisi adlı bir parçasını tam olarak kullanır. İletişim kutusu tabanlı uygulamalar, form tabanlı uygulamalar ve DLL 'Ler gibi diğer uygulama türleri yalnızca bazı belge/görünüm mimarisi özelliklerini kullanır.

Belge/görünüm uygulamaları bir veya daha fazla belge, görünüm ve çerçeve penceresi içerir. Bir belge-şablon nesnesi, sınıfları her belge/görünüm/çerçeve kümesi için ilişkilendirir.

MFC uygulamanızda belge/görünüm mimarisi kullanmanız gerekmese de, bunu yapmanın birkaç avantajı vardır. MFC OLE kapsayıcısı ve sunucu desteği, yazdırma ve Baskı Önizleme desteği gibi belge/görünüm mimarisine dayalıdır.

Tüm MFC uygulamalarının en az iki nesnesi vardır: [CWinApp](../mfc/reference/cwinapp-class.md)'dan türetilmiş bir uygulama nesnesi ve bir dizi ana pencere nesnesi (genellikle dolaylı olarak) [CWnd](../mfc/reference/cwnd-class.md)'den türetilir. (Çoğu zaman, ana pencere [CFrameWnd](../mfc/reference/cframewnd-class.md), [cmdiframewnd](../mfc/reference/cmdiframewnd-class.md)veya [CDialog](../mfc/reference/cdialog-class.md)'dan türetilir, hepsi `CWnd`türetilir.)

Belge/görünüm mimarisi kullanan uygulamalar ek nesneler içerir. Asıl nesneler şunlardır:

- Daha önce bahsedildiği gibi, [CWinApp](../mfc/reference/cwinapp-class.md)sınıfından türetilmiş bir uygulama nesnesi.

- [CDocument](../mfc/reference/cdocument-class.md)sınıfından türetilmiş bir veya daha fazla belge sınıfı nesnesi. Belge sınıfı nesneleri, görünümde yönetilen verilerin iç gösteriminden sorumludur. Bu, bir veri dosyası ile ilişkilendirilebilir.

- [CView](../mfc/reference/cview-class.md)sınıfından türetilen bir veya daha fazla görünüm nesnesi. Her görünüm, bir belgeye iliştirilmiş ve bir çerçeve penceresiyle ilişkilendirilen bir penceredir. Görünümler bir belge sınıfı nesnesinde bulunan verileri görüntüler ve işleyebilir.

Belge/görünüm uygulamaları Ayrıca çerçeve pencerelerini ( [CFrameWnd](../mfc/reference/cframewnd-class.md)'den türetilmiş) ve belge şablonlarını ( [CDocTemplate](../mfc/reference/cdoctemplate-class.md)'ten türetilmiş) içerir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
