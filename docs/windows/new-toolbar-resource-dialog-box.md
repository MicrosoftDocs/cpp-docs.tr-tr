---
title: Yeni araç çubuğu kaynağı iletişim kutusu (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.newtoolbarresource
dev_langs:
- C++
helpviewer_keywords:
- New Toolbar Resource dialog box [C++]
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc933905cf4056d2be6c692728c621913687a6fa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425543"
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