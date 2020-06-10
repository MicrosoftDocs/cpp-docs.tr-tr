---
title: 'Nasıl yapılır: Şerit Denetimleri ve Olay İşleyicileri Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
ms.openlocfilehash: 560524c36dbf57faec3b4b6372cade047f9fe7de
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618480"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>Nasıl yapılır: Şerit Denetimleri ve Olay İşleyicileri Ekleme

Şerit denetimleri, panellere eklediğiniz düğmeler ve Birleşik giriş kutuları gibi öğelerdir. Paneller, bir ilişkili denetimler grubunu görüntüleyen şerit çubuğunun alanlarıdır.

Bu konu başlığında, Şerit Tasarımcısını açacak, bir düğme ekleyecek ve ardından "Merhaba Dünya" görüntüleyen bir olayı bağlayacaksınız.

### <a name="to-open-the-ribbon-designer"></a>Şerit tasarımcısını açmak için

1. Visual Studio 'da, **Görünüm** menüsünde **kaynak görünümü**' a tıklayın.

1. **Kaynak görünümü**, şerit kaynağına çift tıklayarak tasarım yüzeyinde görüntüleyin.

### <a name="to-add-a-button-and-an-event-handler"></a>Bir düğme ve olay Işleyicisi eklemek için

1. **Araç çubuğundan** **düğme** ' ye tıklayın ve tasarım yüzeyinde bir panele sürükleyin.

1. Düğmeye sağ tıklayın ve **olay Işleyicisi Ekle**' ye tıklayın.

1. **Olay Işleyicisi sihirbazında**, varsayılan ayarları onaylayın ve **Ekle ve Düzenle**' ye tıklayın. Daha fazla bilgi için bkz. [olay Işleyicisi Sihirbazı](../ide/event-handler-wizard.md).

1. Kod Düzenleyicisi 'nde, aşağıdaki kodu işleyici işlevine ekleyin:

```
    MessageBox((LPCTSTR)L"Hello World");
```

## <a name="see-also"></a>Ayrıca bkz.

[Ribbonaraçları örneği: şerit araçları uygulaması](../overview/visual-cpp-samples.md)<br/>
[Şerit Tasarımcısı (MFC)](ribbon-designer-mfc.md)
