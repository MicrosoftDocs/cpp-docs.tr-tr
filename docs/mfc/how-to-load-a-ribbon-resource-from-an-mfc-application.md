---
title: 'Nasıl yapılır: Bir MFC Uygulamasından Şerit Kaynağı Yükleme'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 47a3b94bbcb14c6c2923524db1f6a83b687e50e8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626410"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Nasıl yapılır: Bir MFC Uygulamasından Şerit Kaynağı Yükleme

Uygulamanızda şerit kaynağını kullanmak için, şerit kaynağını yüklemek üzere uygulamayı değiştirin.

### <a name="to-load-a-ribbon-resource"></a>Şerit kaynağı yüklemek için

1. `Ribbon Control`Sınıfında nesnesini bildirin `CMainFrame` .

```
    CMFCRibbonBar m_wndRibbonBar;
```

1. İçinde `CMainFrame::OnCreate` , şerit denetimini oluşturun ve başlatın.

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

[Şerit Tasarımcısı (MFC)](ribbon-designer-mfc.md)
