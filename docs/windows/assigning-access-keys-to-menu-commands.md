---
title: Menü komutlarına (C++) erişim tuşları atama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80a3480039330e85f468cfd46ba3901dd1c15dee
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318778"
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