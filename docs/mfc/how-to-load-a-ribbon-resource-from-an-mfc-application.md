---
title: 'Nasıl yapılır: Bir MFC Uygulamasından Şerit Kaynağı Yükleme'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 14ba37952d6f8849c51b36901a6bc17404f938e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515160"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Nasıl yapılır: Bir MFC Uygulamasından Şerit Kaynağı Yükleme

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

## <a name="see-also"></a>Ayrıca Bkz.

[Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)

