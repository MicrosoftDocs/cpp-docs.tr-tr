---
title: Denetimleri hizalama
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], aligning
- controls [C++], positioning
- Space Evenly command
- dialog box controls [C++], placement
- Center in Dialog command
- Arrange Buttons command
- buttons, arranging push buttons in dialog boxes
- push buttons
ms.assetid: a4f49a73-4a17-44b3-8568-aa35f646b5cf
ms.openlocfilehash: abfae0f0146fa736a6427eb1180805717ce8a78e
ms.sourcegitcommit: 5270117dbecc4c49bca0cf10b927bae3c9930038
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/31/2019
ms.locfileid: "55484987"
---
# <a name="align-controls"></a>Denetimleri hizalama

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

Aşağıdaki yordamlar denetimleri eksene nasıl getireceğinizi gösterir:

## <a name="to-align-groups-of-controls"></a>Denetim gruplarını hizalama

1. [Denetimleri seçin](../windows/selecting-multiple-controls.md) hizalamak istiyorsanız. Baskın denetimi olmasını istediğiniz denetim seçtiğinizden emin olun veya hizalama yürütme ya da komut boyutlandırma önce baskın denetimi olacak şekilde ayarlayın.

   Denetim grubunun son konumunu baskın denetimi konumuna bağlıdır. Baskın denetimi seçme hakkında daha fazla bilgi için bkz. [baskın denetimi belirtme](../windows/specifying-the-dominant-control.md).

1. Gelen **biçimi** menüsünde seçin **Hizala**ve ardından aşağıdaki hizalamaları birini seçin:

   - `Lefts`: Seçili denetimleri, sol kenarı boyunca hizalar.

   - `Centers`: Seçili denetimleri yatay olarak kendi center noktalarını boyunca hizalar.

   - `Rights`: Seçili denetimleri kendi sağ kenarı boyunca hizalar.

   - `Tops`: Seçili denetimleri üst kenarları boyunca hizalar.

   - `Middles`: seçilen denetimleri dikey olarak kendi orta noktaları boyunca hizalar.

   - `Bottoms`: Seçili denetimleri alt kenarları boyunca hizalar.

## <a name="to-even-the-spacing-between-controls"></a>Denetimler arasındaki aralığı bile için

**İletişim** Düzenleyicisi eşit olarak seçilen en dıştaki denetimler arasındaki boşluk denetimlere, sağlar.

1. Yeniden düzenlemek istediğiniz denetimleri seçin.

1. Gelen **biçimi** menüsünde seçin **eşit**ve ardından aşağıdaki aralığı hizalamaları birini seçin:

   - `Across`: alanı en soldaki ve sağdaki denetimi seçili arasında eşit olarak denetimleri.

   - `Down`: alanı üstteki ve alttaki denetimi seçili arasında eşit olarak denetimleri.

## <a name="to-center-controls-in-a-dialog-box"></a>İletişim kutusundaki denetimlere ortalamak için

1. Denetim veya yeniden düzenlemek istediğiniz denetimleri seçin.

1. Gelen **biçimi** menüsünde seçin **Merkezi iletişim**ve ardından aşağıdaki düzenlemeleri birini seçin:

   - `Vertical`: iletişim kutusu denetimleri dikey olarak ortalayın.

   - `Horizontal`: yatay olarak iletişim kutusunda denetimleri ortalama.

## <a name="to-arrange-push-buttons-along-the-right-or-bottom-of-a-dialog-box"></a>Basma düğmelerini iletişim kutusunun alt ve sağ düzenlemek için

1. Bir veya daha fazla basma düğmelerini seçin.

1. Gelen **biçimi** menüsünde seçin **Düzenle düğmeler**ve ardından aşağıdaki düzenlemeleri birini seçin:

   - `Right`: basma düğmelerini iletişim kutusunun sağ kenarı hizalar.

   - `Bottom`: basma düğmelerini iletişim kutusunun alt kenarı hizalar.

       Bir denetimin bir itme düğmesi dışında seçerseniz konumuna etkilenmez.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimlerin Düzenlenmesi](../windows/arrangement-of-controls-on-dialog-boxes.md)<br/>
[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)