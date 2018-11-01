---
title: (C++) Toolbar düğmesi için araç ipucu oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor [C++], creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
ms.openlocfilehash: 9179dfcc47f69b9f5db131467f0216da6363085c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558018"
---
# <a name="creating-a-tool-tip-for-a-toolbar-button-c"></a>(C++) Toolbar düğmesi için araç ipucu oluşturma

### <a name="to-create-a-tool-tip"></a>Bir araç ipucu oluşturmak için

1. Araç çubuğu düğmesini seçin.

2. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), **istemi** özellik alanı, ileti sonra; durum çubuğunu düğmenin bir açıklama ekleyin, ekleme `\n` ve araç ipucu adı.

Ortak bir araç ipucu örneğidir **yazdırma** düğmesine **WordPad**:

1. Açık **WordPad**.

2. Fare işaretçinizi üzerine **yazdırma** araç çubuğu düğmesi.

3. Dikkat word `Print` fare işaretçinizi altında artık kayan noktalı.

4. Durum çubuğu Ara (çok altındaki **WordPad** pencere)-bu artık metin gösterdiğine dikkat edin `Prints the active document`.

`Print` İçinde **3. adım** "araç ipucu" adıdır ve `Prints the active document` gelen **4. adım** "açıklama için durum çubuğu düğmesinin."

Efekt kullanarak bu istiyorsanız **araç** Düzenleyicisi, ayarladığınız **istemi** özelliğini `Prints the active document\nPrint`.

> [!NOTE]
> İstem metnini kullanarak düzenleyebileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Araç Çubuğu Düğmelerini Oluşturma, Taşıma ve Düzenleme](../windows/creating-moving-and-editing-toolbar-buttons.md)<br/>
[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)