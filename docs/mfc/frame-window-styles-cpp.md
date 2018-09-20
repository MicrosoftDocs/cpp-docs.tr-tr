---
title: Çerçeve pencere stilleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f0e4bde874fc563535b661108cb68edefd8d977
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385020"
---
# <a name="frame-window-styles-c"></a>Çerçeve Pencere Stilleri (C++)

Framework ile alma çerçeve pencereleri programlarının çoğu için uygundur, ancak gelişmiş işlevleri kullanarak daha fazla esneklik elde edebilirsiniz [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) ve MFC genel işlev [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` bir üye işlevidir `CWnd`.

Uygularsanız, **WS_HSCROLL** ve **WS_VSCROLL** stilleri ana çerçeve penceresine, bunun yerine uygulanır **MDICLIENT** kullanıcıların kaydırabileceğişekildepenceresi**MDICLIENT** alan.

Varsa pencerenin **fws_addtotıtle** stili biti ayarlanmış (Bu varsayılan olarak etkindir), görünüm çerçeve penceresi pencerenin başlık çubuğunda Görünüm'ün belge adına göre görüntülemek için hangi başlık söyler.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [MDI alt pencereleri (MDICLIENT) yönetme](../mfc/managing-mdi-child-windows.md), içinde içeren MDI alt pencereleri bir MDI çerçeve penceresi

- [MFC tarafından oluşturulan pencerenin stillerini değiştirme](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

- [Pencere stilleri](../mfc/reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>Ayrıca Bkz.

[Çerçeve Pencereleri](../mfc/frame-windows.md)

