---
title: Yeni araç çubuğu kaynağı iletişim kutusu (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.newtoolbarresource
helpviewer_keywords:
- New Toolbar Resource dialog box [C++]
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
ms.openlocfilehash: 7c45daeb2c07426918f1a636f4230c1c07026ca2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595929"
---
# <a name="new-toolbar-resource-dialog-box-c"></a>Yeni araç çubuğu kaynağı iletişim kutusu (C++)

**Yeni araç çubuğu kaynağı** iletişim kutusu, genişlik ve yükseklik bir C++ projesini bir araç çubuğu kaynağı eklemekte olduğunuz düğmelerinin belirtmenize olanak sağlar. Varsayılan değer 16 × 15 pikseldir.

Araç çubuğu oluşturmak için kullanılan bir bit eşlem 2048 maksimum genişliği sahiptir. Bunu yaparsanız **düğmesi genişliği** 512, yalnızca dört düğme olabilir. Genişliği için 513 ayarlarsanız, yalnızca üç düğme olabilir.

### <a name="button-width"></a>Düğme genişliği

Araç çubuğu kaynak bit eşlem kaynağı dönüştürme araç çubuğu düğmeleri genişliğini girmek bir alan sağlar. Resimleri belirtilen yükseklik ve genişlik kırpılmış ve renkleri (16 renk) standart araç çubuğu renklerini kullanmak için ayarlanır.

### <a name="button-height"></a>Düğme yüksekliği

Araç çubuğu kaynak bit eşlem kaynağı dönüştürme araç çubuğu düğmeleri yüksekliği girmek bir alan sağlar. Resimleri belirtilen yükseklik ve genişlik kırpılmış ve renkleri (16 renk) standart araç çubuğu renklerini kullanmak için ayarlanır.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Araç Çubuğu Düğmesi Özellikleri](../windows/toolbar-button-properties.md)<br/>
[Bit Eşlemleri Araç Çubuklarına Dönüştürme](../windows/converting-bitmaps-to-toolbars.md)<br/>
[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)