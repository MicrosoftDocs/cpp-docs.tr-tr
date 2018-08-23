---
title: Yeni araç çubukları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.toolbar
dev_langs:
- C++
helpviewer_keywords:
- toolbars [C++], creating
- Toolbar editor, creating new toolbars
- Insert Resource
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c737d048289074bcac948ad5eb5b27fac515b042
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596579"
---
# <a name="creating-new-toolbars"></a>Yeni Araç Çubukları Oluşturma

### <a name="to-create-a-new-toolbar"></a>Yeni bir araç çubuğu oluşturmak için

1. İçinde **kaynak** görüntüleyebilir, .rc dosyasına sağ tıklayın ve ardından **kaynak Ekle** kısayol menüsünden. (Var olan bir araç çubuğu, bir .rc dosyasında varsa, sadece ne sağ tıklayarak **araç** klasörü ve select **araç çubuğu ekleme** kısayol menüsünden.)

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde **kaynak Ekle** iletişim kutusunda **araç** içinde **kaynak türü** listesinde'a tıklayın **yeni**.

   Bir artı işareti (**+**) yanında görünen **araç** kaynak türü geldiğini araç şablonları kullanılabilir. Şablonlar listesinde genişletin, bir şablon seçin ve tıklayın artı işaretine tıklayın **yeni**.

   \- veya -

3. [Bir araç çubuğu için mevcut bir bit eşlemi dönüştürme](../windows/converting-bitmaps-to-toolbars.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)