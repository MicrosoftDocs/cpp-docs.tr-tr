---
title: MFC Uygulama Mimarisi Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
ms.openlocfilehash: 47feeb056d02b81bb88ccf3c5fd49bc983583ee7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62239311"
---
# <a name="mfc-application-architecture-classes"></a>MFC Uygulama Mimarisi Sınıfları

Sınıfları bu kategoriye giren bir framework uygulamasının mimariye katkıda bulunur. Bunlar, çoğu uygulama için ortak işlevselliği sağlar. Uygulamaya özgü işlevselliği eklemek için framework doldurun. Genellikle, yeni sınıflar mimarisi sınıflardan türetme ve ardından yeni üyeler eklemek veya var olan üye işlevleri geçersiz kılma bunu.

[Uygulama sihirbazları](../mfc/reference/mfc-application-wizard.md) çeşitli uygulama türleri farklı şekillerde tümü kullanan uygulama çerçevesi oluşturun. (Tek Belgeli Arabirim) SDI ve MDI (birden çok belge arabirimi) uygulamaları tam kullanımını belge/görünüm mimarisi olarak adlandırılan framework'ün bir parçası olun. İletişim tabanlı uygulamalar, form tabanlı uygulamalar ve DLL'ler gibi uygulamalarının diğer türleri yalnızca belge/görünüm mimarisi özelliklerden bazıları kullanın.

Belge/görünüm uygulamaları bir veya daha fazla kümesi belgeler, görünümler ve çerçeve pencereleri içerir. Bir belge şablonu nesnesi, her bir belge/görünüm/çerçeve kümesi sınıflarını ilişkilendirir.

Belge/görünüm mimarisi MFC uygulamanızda kullanmak zorunda değil ancak bunun yapılması avantajları sayısı vardır. Yazdırma ve yazdırma önizleme desteği gibi MFC OLE kapsayıcı ve sunucu desteği belge/görünüm mimarisini temel alır.

Tüm MFC uygulamaları en az iki nesne vardır: uygulama nesnesi türetilen [CWinApp](../mfc/reference/cwinapp-class.md)ve ana pencere nesnesi, (genellikle dolaylı olarak) türetilen tür [CWnd](../mfc/reference/cwnd-class.md). (Çoğu zaman ana pencerenin türetilir [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), veya [CDialog](../mfc/reference/cdialog-class.md), her biri türetilmiştir `CWnd`.)

Belge/görünüm mimarisini kullanan uygulamalar, ek nesneler içerir. Asıl nesneleri şunlardır:

- Uygulama nesnesi sınıfından türetilmiş [CWinApp](../mfc/reference/cwinapp-class.md), daha önce belirtildiği gibi.

- Bir veya daha fazla belge sınıfı nesneleri sınıfından türetilmiş [CDocument](../mfc/reference/cdocument-class.md). Belge sınıfı nesneleri, veri görünümü'nde yönetilen iç gösterimine sorumludur. Bunlar, bir veri dosyası ile ilişkili olabilir.

- Bir veya daha fazla görünüm nesneleri sınıfından türetilmiş [CView](../mfc/reference/cview-class.md). Her görünüm, bir belgeye ekli ve bir çerçeve penceresi ile ilişkili bir penceredir. Görünümleri görüntüleyebilir ve bir belge sınıf nesnesinde yer alan verileri.

Belge/görünüm uygulamaları da içeren çerçeve pencereleri (türetilen [CFrameWnd](../mfc/reference/cframewnd-class.md)) ve belge şablonları (türetilen [CDocTemplate](../mfc/reference/cdoctemplate-class.md)).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
