---
title: Yeni araç çubuğu kaynağı iletişim kutusu | Microsoft Docs
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
- New Toolbar Resource dialog box
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33c63357f0816fbf0d89058d4151ea5785f6f35a
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015026"
---
# <a name="new-toolbar-resource-dialog-box"></a>Yeni Araç Çubuğu Kaynağı İletişim Kutusu
**Yeni araç çubuğu kaynağı** iletişim kutusu, genişlik ve yükseklik bir araç çubuğu kaynağı için eklediğiniz düğmelerinin belirtmenize olanak sağlar. Varsayılan değer 16 × 15 pikseldir.  
  
 Araç çubuğu oluşturmak için kullanılan bir bit eşlem 2048 maksimum genişliği sahiptir. Bunu yaparsanız **düğmesi genişliği** 512, yalnızca dört düğme olabilir. Genişliği için 513 ayarlarsanız, yalnızca üç düğme olabilir.  
  
### <a name="button-width"></a>Düğme genişliği  
 Araç çubuğu kaynak bit eşlem kaynağı dönüştürme araç çubuğu düğmeleri genişliğini girmek bir alan sağlar. Resimleri belirtilen yükseklik ve genişlik kırpılmış ve renkleri (16 renk) standart araç çubuğu renklerini kullanmak için ayarlanır.  
  
### <a name="button-height"></a>Düğme yüksekliği  
 Araç çubuğu kaynak bit eşlem kaynağı dönüştürme araç çubuğu düğmeleri yüksekliği girmek bir alan sağlar. Resimleri belirtilen yükseklik ve genişlik kırpılmış ve renkleri (16 renk) standart araç çubuğu renklerini kullanmak için ayarlanır.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 MFC veya ATL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araç çubuğu düğmesi özellikleri](../windows/toolbar-button-properties.md)   
 [Bit eşlemleri araç çubuklarına dönüştürme](../windows/converting-bitmaps-to-toolbars.md)   
 [Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)