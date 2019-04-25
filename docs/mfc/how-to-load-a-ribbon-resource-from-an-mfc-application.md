---
title: 'Nasıl yapılır: Bir MFC uygulamasından Şerit kaynağı yükleme'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: b7691d4168101209b0e2d2500012a2b4a8e47788
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160334"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Nasıl yapılır: Bir MFC uygulamasından Şerit kaynağı yükleme

Şerit kaynağını kullanmak için Şerit kaynağı yükleme için değiştirin.

### <a name="to-load-a-ribbon-resource"></a>Bir Şerit kaynağı yükleme için

1. Bildirme `Ribbon Control` nesnesine `CMainFrame` sınıfı.

```
    CMFCRibbonBar m_wndRibbonBar;
```

1. İçinde `CMainFrame::OnCreate`, oluşturun ve Şerit denetimi başlatılamıyor.

```
    if (!m_wndRibbonBar.Create (this))
{
    return -1;
}

    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))
{
    return -1;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)
