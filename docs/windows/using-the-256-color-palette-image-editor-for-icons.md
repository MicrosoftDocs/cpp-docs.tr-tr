---
title: 256-Renk Paletini Kullanma (Simgeler İçin Görüntü Düzenleyicisi)
ms.date: 11/04/2016
helpviewer_keywords:
- 256-color palette
- colors [C++], icons and cursors
- cursors [C++], color
- color palettes, 256-color
- palettes, 256-color
- icons, color
ms.assetid: 1506ed00-669b-4a21-b1a4-39b6a84a78bb
ms.openlocfilehash: f41ca69e7c13dfb722085648cefa11bfe43af819
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519268"
---
# <a name="using-the-256-color-palette-image-editor-for-icons"></a>256-Renk Paletini Kullanma (Simgeler İçin Görüntü Düzenleyicisi)

256-renk paletinden bir seçimle çizmek için renk seçmeniz gerekir **renkleri** palette [renkler penceresini](../windows/colors-window-image-editor-for-icons.md).

### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Büyük simgeler için 256-renk paletinden bir renk seçmek için

1. Büyük simgesi veya imleci seçin veya yeni büyük simgesi veya imleci oluşturma.

2. Görüntülenen 256 renkten bir renk seçin **renkleri** palette **renkleri** penceresi.

   Seçili renk geçerli rengi olur **renkleri** palette **renkleri** penceresi.

   > [!NOTE]
   > 256-renk görüntüler için kullanılan ilk paleti tarafından döndürülen palet eşleşen `CreateHalftonePalette` Windows API. Windows Kabuğu için hedeflenen tüm simgeleri palet gerçekleştirme sırasında titreşimini önlemek için bu paletin kullanmanız gerekir.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[256-renk simgesi veya imleci oluşturma](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)<br/>
[Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)