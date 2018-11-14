---
title: 'Nasıl yapılır: Şerit Denetimleri ve Olay İşleyicileri Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
ms.openlocfilehash: 356358e5fd5ac4f3f7511f178ca304e9ab7eff86
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518404"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>Nasıl yapılır: Şerit Denetimleri ve Olay İşleyicileri Ekleme

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

## <a name="see-also"></a>Ayrıca Bkz.

[RibbonGadgets örneği: Şerit araçları uygulaması](../visual-cpp-samples.md)<br/>
[Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)

