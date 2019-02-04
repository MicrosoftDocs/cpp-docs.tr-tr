---
title: Menü komutlarını (C++) ilişkilendirme
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [C++], menu association
- commands [C++], associating menu commands with accelerator keys
- menu commands [C++], associating with keyboard shortcuts
- status bars [C++], associating menu items
- menus [C++], status bar text
- access keys [C++], checking
- menus [C++], shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics [C++], adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics [C++], uniqueness checking
- Check Mnemonics command
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
ms.openlocfilehash: f72fe5de3ef29b9575ef1a3138d4d114d7470fee
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703044"
---
# <a name="associating-menu-commands-c"></a>Menü komutlarını (C++) ilişkilendirme

Genellikle bir menü komutu ve klavye birleşimi aynı program komutu vermek istediğiniz durumlar da vardır. Aynı komutları kullanarak yayımlanan **menü** aynı kaynak tanımlayıcısı menü komutunu ve uygulamanızın Hızlandırıcı tablosunda bir giriş atamak için düzenleyici. Ardından Düzenle [açıklamalı alt yazı](../windows/menu-command-properties.md) kısayol tuşunu adını göstermek için menü komutu.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>Bir menü komutunu Hızlandırıcı tuşuyla ilişkilendirme

1. İçinde **menü** Düzenleyicisi, istediğiniz komutu seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), hızlandırıcı anahtarı adını eklemek **açıklamalı alt yazı** özelliği:

   - Menü başlığı tüm menünün kısayol tuşları sola hizalanmış bir sekme (\t) kaçış sırası yazın.

   - Değiştirici tuş adını yazın (**Ctrl**, **Alt**, veya **Shift**) ve ardından bir artı işareti (**+**) ve ad, harf, veya İlave bir anahtar simgesi.

       Örneğin, atama için **Ctrl**+**O** için **açık** komutunu **dosya** menüsünde, menü komutunun değiştirme **Açıklamalı alt yazı** böylece şu metin gibi görünür:

        ```
        &Open...\tCtrl+O
        ```

       Menü komutunu **menü** Düzenleyici siz yazarken yeni başlığı yansıtacak şekilde güncelleştirilir.

1. [Hızlandırıcı tablosu girişi oluşturmak](../windows/adding-an-entry-to-an-accelerator-table.md) içinde **hızlandırıcı** Düzenleyicisi ve menü komutunu aynı tanımlayıcıyı atayın. Kolay olacağını düşündüğünüz bir tuş bileşimini kullanın.

## <a name="to-associate-a-menu-command-with-a-status-bar-text-string-in-mfc-applications"></a>Bir durum çubuğunda metin dizesi MFC uygulamalarında menü komutu ilişkilendirmek için

MFC uygulamanızı her bir kullanıcı seçebilir menü komutları için açıklayıcı metni görüntüleyebilirsiniz. Bir metin dizesi kullanarak her menü komut atayarak açıklayıcı metni görüntüler **istemi** özelliğinde **özellikleri** penceresi. Bir dize varsa [dize tablosu](../windows/string-editor.md) Kimliğine komutu ile aynıdır, bir kullanıcı bir menü öğesi geldiğinde bir MFC uygulaması otomatik olarak bu dize kaynağı çalışan uygulama durum çubuğunda görüntülenir.

1. İçinde **menü** Düzenleyicisi, menü komutunu seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), ilgili durum çubuğu metni yazın **istemi** kutusu.

> [!NOTE]
> Bu adım kümesini MFC gerektirir.

## <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>Bir menü komutu için bir erişim (kısayol) anahtarı atamak için

Bir C++ projesinde, menüleri ve menü komutlarını, bir erişim anahtarı (kullanıcının klavye menüsüyle seçmesine izin veren bir anımsatıcı) atayabilirsiniz.

Ve işareti yazın (`&`) menüsü adı veya harf karşılık gelen erişim anahtarı olarak belirtmek için komut adı bir harf önünde. Örneğin, "& dosya" kümeleri **Alt**+**F** için kısayol tuşu **dosya** menüsünde Microsoft Windows için yazılmış uygulamalar için.

   Menü öğesi bir harf kendisine atanmış bir kısayol tuşuna sahip görünür bir ipucu sağlar. Ve işareti görünür harf aşağıdaki altı çizili (işletim sistemi topolojideki).

   > [!NOTE]
   > Menünüzde sağ tıklayıp seçerek menüsündeki tüm erişim anahtarlarını benzersiz olduğundan emin olun **anımsatıcıları kontrol** kısayol menüsünden.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Menü Düzenleyicisi](../windows/menu-editor.md)<br/>
[Menüye Komut Ekleme](../windows/adding-commands-to-a-menu.md)<br/>
[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
