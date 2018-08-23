---
title: Hızlandırıcı Düzenleyicisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.accelerator.F1
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [Visual Studio], accelerator key
- accelerator keys
- resource editors, Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
- Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81642132272b40229437c2be8bac32d160885600
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578100"
---
# <a name="accelerator-editor"></a>Hızlandırıcı Düzenleyicisi

Hızlandırıcı tablosunu hızlandırma tuşları (kısayol tuşları olarak da bilinir) bir listesini içeren bir Windows kaynağı ve bunlarla ilişkili komut tanımlayıcıları ' dir. Bir program, birden fazla Hızlandırıcı tablosu olabilir.

Normalde, Hızlandırıcıları klavye kısayolları da menü veya araç çubuğunda kullanılabilir program komutları için kullanılır. Ancak, Hızlandırıcı tablosu tuş bileşimleri için ilişkili bir kullanıcı arabirimi nesnesi olmayan komutları tanımlamak için kullanabilirsiniz.

Kullanabileceğiniz [sınıf görünümü](http://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925) kod anahtar komutlarını Hızlandırıcı yeteneklerinizi.

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