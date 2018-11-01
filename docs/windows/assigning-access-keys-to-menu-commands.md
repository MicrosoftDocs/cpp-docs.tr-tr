---
title: Menü komutlarına (C++) erişim tuşları atama
ms.date: 11/04/2016
helpviewer_keywords:
- access keys [C++], checking
- menus [C++], shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics [C++], adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics [C++], uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
ms.openlocfilehash: 7a3302f7744bf5c3a0cbaac96de04d9f649fac10
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587336"
---
# <a name="assigning-access-keys-to-menu-commands-c"></a>Menü komutlarına (C++) erişim tuşları atama

Bir C++ projesinde, menüleri ve menü komutlarını, bir erişim anahtarı (kullanıcının klavye menüsüyle seçmesine izin veren bir anımsatıcı) atayabilirsiniz.

### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>Bir menü komutu için bir erişim (kısayol) anahtarı atamak için

1. Ve işareti yazın (`&`) menüsü adı veya harf karşılık gelen erişim anahtarı olarak belirtmek için komut adı bir harf önünde. Örneğin "& dosya" kümeleri **Alt**+**F** için kısayol tuşu **dosya** menüsünde Microsoft Windows için yazılmış uygulamalar için.

   Menü öğesi bir harf kendisine atanmış bir kısayol tuşuna sahip görünür bir ipucu sağlar. Ve işareti görünür harf aşağıdaki altı çizili (işletim sistemi topolojideki).

   > [!NOTE]
   > Menünüzde sağ tıklayıp seçerek menüsündeki tüm erişim anahtarlarını benzersiz olduğundan emin olun **anımsatıcıları kontrol** kısayol menüsünden.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Menü Düzenleyicisi](../windows/menu-editor.md)