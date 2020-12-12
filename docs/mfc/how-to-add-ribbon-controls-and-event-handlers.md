---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: Şerit denetimleri ve olay Işleyicileri ekleme'
title: 'Nasıl yapılır: Şerit Denetimleri ve Olay İşleyicileri Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
ms.openlocfilehash: bffac6b27f809961e3ca7a4323f519c765526198
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290303"
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

1. **Olay Işleyicisi sihirbazında**, varsayılan ayarları onaylayın ve **Ekle ve Düzenle**' ye tıklayın. Daha fazla bilgi için bkz. [olay Işleyicisi Sihirbazı](../ide/adding-an-event-handler-visual-cpp.md#event-handler-wizard).

1. Kod Düzenleyicisi 'nde, aşağıdaki kodu işleyici işlevine ekleyin:

```
    MessageBox((LPCTSTR)L"Hello World");
```

## <a name="see-also"></a>Ayrıca bkz.

[Ribbonaraçları örneği: şerit araçları uygulaması](../overview/visual-cpp-samples.md)<br/>
[Şerit Tasarımcısı (MFC)](ribbon-designer-mfc.md)
