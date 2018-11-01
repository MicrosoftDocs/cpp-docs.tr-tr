---
title: Hızlandırıcı Düzenleyicisi (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.accelerator.F1
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [C++], accelerator key
- accelerator keys [C++]
- resource editors [C++], Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
ms.openlocfilehash: fdb2d9cf0954142da990a0a9f995cb482060345d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621500"
---
# <a name="accelerator-editor-c"></a>Hızlandırıcı Düzenleyicisi (C++)

Hızlandırıcı tablosunu hızlandırma tuşları (kısayol tuşları olarak da bilinir) bir listesini içeren bir C++ Windows kaynak ve bunlarla ilişkili komut tanımlayıcıları ' dir. Bir program, birden fazla Hızlandırıcı tablosu olabilir.

Normalde, Hızlandırıcıları klavye kısayolları da menü veya araç çubuğunda kullanılabilir program komutları için kullanılır. Ancak, Hızlandırıcı tablosu tuş bileşimleri için ilişkili bir kullanıcı arabirimi nesnesi olmayan komutları tanımlamak için kullanabilirsiniz.

Kullanabileceğiniz [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code) kod anahtar komutlarını Hızlandırıcı yeteneklerinizi.

İle **hızlandırıcı** Düzenleyicisi, şunları yapabilirsiniz:

- [Hızlandırıcı özelliklerini ayarlama](../windows/setting-accelerator-properties.md)

- [Hızlandırıcı tuşunu Menü öğesiyle ilişkilendirme](../windows/associating-an-accelerator-key-with-a-menu-item.md)

- [Hızlandırıcı tablolarını düzenleme](../windows/editing-accelerator-tables.md)

- [Önceden tanımlanmış Hızlandırıcı tuşları kullanın](../windows/predefined-accelerator-keys.md)

   > [!TIP]
   > Kullanırken **hızlandırıcı** Düzenleyicisi sağ sık kullanılan komutlar bir kısayol menüsünü görüntülemek için. Kullanılabilir komutlar ne işaretçinin işaret ettiği üzerinde bağlıdır.

   > [!NOTE]
   > Windows, boş bir Hızlandırıcı tabloları oluşturmak izin vermez. Hızlandırıcı tablosunu giriş yok oluşturursanız, tabloyu kaydettiğinizde otomatik olarak silinir.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)