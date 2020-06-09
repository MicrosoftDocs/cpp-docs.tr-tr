---
title: Çerçeve Pencere Stilleri (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
ms.openlocfilehash: 3c22944537370a44aee1af1cf71281264ed4969b
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626450"
---
# <a name="frame-window-styles-c"></a>Çerçeve Pencere Stilleri (C++)

Framework ile aldığınız çerçeve pencereleri çoğu program için uygundur, ancak gelişmiş işlevler [ön penceresi](reference/cwnd-class.md#precreatewindow) ve MFC genel Işlevi [AfxRegisterWndClass](reference/application-information-and-management.md#afxregisterwndclass)kullanarak ek esneklik elde edebilirsiniz. `PreCreateWindow`, öğesinin bir üye işlevidir `CWnd` .

Ana çerçeve penceresine **ws_hscroll** ve **ws_vscroll** stilleri uygularsanız, kullanıcıların **MDICLIENT** alanını kaydırabilmesi için bunların **MDICLIENT** penceresine uygulanması gerekir.

Pencerenin **FWS_ADDTOTITLE** stil biti ayarlandıysa (varsayılan olarak), görünüm çerçeve penceresine, görünümün belge adına göre pencerenin başlık çubuğunda hangi başlığın gösterileceğini söyler.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- MDI alt Windows [(MDICLIENT)](managing-mdi-child-windows.md), MDI alt pencerelerini IÇEREN bir MDI çerçevesi Içindeki pencereyi yönetme

- [MFC tarafından oluşturulan pencerenin stillerini değiştirme](changing-the-styles-of-a-window-created-by-mfc.md)

- [Pencere stilleri](reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve pencereleri](frame-windows.md)
