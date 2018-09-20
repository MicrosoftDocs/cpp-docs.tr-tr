---
title: Menü komutunu Hızlandırıcı tuşuyla (C++) ilişkilendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [C++], menu association
- commands [C++], associating menu commands with accelerator keys
- menu commands [C++], associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da9807e552590513116a7a09a58609b2b576efcc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379742"
---
# <a name="associating-a-menu-command-with-an-accelerator-key-c"></a>Menü komutunu Hızlandırıcı tuşuyla (C++) ilişkilendirme

Genellikle bir menü komutu ve klavye birleşimi aynı program komutu vermek istediğiniz durumlar da vardır. Kullanarak bunu **menü** aynı kaynak tanımlayıcısı menü komutunu ve uygulamanızın Hızlandırıcı tablosunda bir giriş atamak için düzenleyici. Ardından Düzenle [açıklamalı alt yazı](../windows/menu-command-properties.md) kısayol tuşunu adını göstermek için menü komutu.

### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>Bir menü komutunu Hızlandırıcı tuşuyla ilişkilendirme

1. İçinde **menü** Düzenleyicisi, istediğiniz komutu seçin.

2. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), hızlandırıcı anahtarı adını eklemek **açıklamalı alt yazı** özelliği:

   - Menü başlığı tüm menünün kısayol tuşları sola hizalanmış bir sekme (\t) kaçış sırası yazın.

   - Değiştirici tuş adını yazın (**Ctrl**, **Alt**, veya **Shift**) ve ardından bir artı işareti (**+**) ve ad, harf, veya İlave bir anahtar simgesi.

       Örneğin, atama için **Ctrl**+**O** için **açık** komutunu **dosya** menüsünde, menü komutunun değiştirme **Açıklamalı alt yazı** böylece şöyle görünür:

        ```
        &Open...\tCtrl+O
        ```

       Menü komutunu **menü** Düzenleyici siz yazarken yeni başlığı yansıtacak şekilde güncelleştirilir.

3. [Hızlandırıcı tablosu girişi oluşturmak](../windows/adding-an-entry-to-an-accelerator-table.md) içinde **hızlandırıcı** Düzenleyicisi ve menü komutunu aynı tanımlayıcıyı atayın. Kolay olacağını düşündüğünüz bir tuş bileşimini kullanın.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Menüye Komut Ekleme](../windows/adding-commands-to-a-menu.md)<br/>
[Menü Düzenleyicisi](../windows/menu-editor.md)