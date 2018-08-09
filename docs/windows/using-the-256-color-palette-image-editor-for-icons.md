---
title: 256-renk paletini (simgeler için görüntü Düzenleyicisi) kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 256-color palette
- colors, icons and cursors
- cursors, color
- color palettes, 256-color
- palettes, 256-color
- icons, color
ms.assetid: 1506ed00-669b-4a21-b1a4-39b6a84a78bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0287d27d975ce93e88a7a4b70a683188901ca958
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011822"
---
# <a name="using-the-256-color-palette-image-editor-for-icons"></a>256-Renk Paletini Kullanma (Simgeler İçin Görüntü Düzenleyicisi)
256-renk paletinden bir seçimle çizmek için renk seçmeniz gerekir **renkleri** palette [renkler penceresini](../windows/colors-window-image-editor-for-icons.md).  
  
### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Büyük simgeler için 256-renk paletinden bir renk seçmek için  
  
1.  Büyük simgesi veya imleci seçin veya yeni büyük simgesi veya imleci oluşturma.  
  
2.  Görüntülenen 256 renkten bir renk seçin **renkleri** palette **renkleri** penceresi.  
  
     Seçili renk geçerli rengi olur **renkleri** palette **renkleri** penceresi.  
  
    > [!NOTE]
    >  256-renk görüntüler için kullanılan ilk paleti tarafından döndürülen palet eşleşen `CreateHalftonePalette` Windows API. Windows Kabuğu için hedeflenen tüm simgeleri palet gerçekleştirme sırasında titreşimini önlemek için bu paletin kullanmanız gerekir.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [256-renk simgesi veya imleci oluşturma](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)   
 [Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)