---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: bir MFC uygulamasından şerit kaynağı yükleme'
title: 'Nasıl yapılır: Bir MFC Uygulamasından Şerit Kaynağı Yükleme'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 231acbd475bf84b2623eb44f9a3500ab94145d06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330195"
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
