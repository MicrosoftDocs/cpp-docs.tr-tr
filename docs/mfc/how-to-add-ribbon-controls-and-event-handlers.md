---
title: 'Nasıl yapılır: Şerit denetimleri ve olay işleyicileri ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
ms.openlocfilehash: c21e8b86962ebf37ca1a06bae056d09b9a9dbb2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389521"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>Nasıl yapılır: Şerit denetimleri ve olay işleyicileri ekleme

Şerit öğeleri, düğmeler ve panel için eklediğiniz birleşik giriş kutuları gibi denetimleridir. Panel bir ilgili denetimlerin grubunu görüntüleyen Şerit çubuğu alanlardır.

Bu konu başlığında, Şerit Tasarımcısını açmanın, bir düğme ekleyin ve "Hello World iletisini" gösteren bir olay bağlayın.

### <a name="to-open-the-ribbon-designer"></a>Şerit Tasarımcısını açmak için

1. Visual Studio'da üzerinde **görünümü** menüsünde tıklatın **kaynak görünümü**.

1. İçinde **kaynak görünümü**, tasarım yüzeyinde görüntülemek için Şerit kaynağını çift tıklayın.

### <a name="to-add-a-button-and-an-event-handler"></a>Bir düğme ve bir olay işleyicisi eklemek için

1. Gelen **araç**, tıklayın **düğmesi** ve tasarım yüzeyine panelinde açın sürükleyin.

1. Düğme sağ tıklayın ve **olay işleyici Ekle**.

1. İçinde **olay işleyici Sihirbazı**, varsayılan ayarları onaylayın ve tıklayın **ekleme ve düzenleme**. Daha fazla bilgi için [olay işleyici Sihirbazı](../ide/event-handler-wizard.md).

1. Kod Düzenleyicisi'nde aşağıdaki kodu işleyici işleve ekleyin:

```
    MessageBox((LPCTSTR)L"Hello World");
```

## <a name="see-also"></a>Ayrıca bkz.

[RibbonGadgets örneği: Şerit araçları uygulaması](../overview/visual-cpp-samples.md)<br/>
[Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)
