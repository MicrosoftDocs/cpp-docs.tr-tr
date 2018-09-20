---
title: 'Nasıl yapılır: bir MFC uygulamasından Şerit kaynağı yükleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1643989a96a9003847fb53de624bff12cd51cd88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434303"
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

