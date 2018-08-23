---
title: Yeni araç çubuğu düğmesi oluşturma | Microsoft Docs
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
- Toolbar editor, creating buttons
- toolbar buttons (in Toolbar editor), button image
- toolbar buttons (in Toolbar editor), creating
- toolbar buttons (in Toolbar editor)
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 737c517a2c92d07a6d5110b0bcc08f0d9a290f5e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603178"
---
# <a name="creating-a-new-toolbar-button"></a>Yeni Araç Çubuğu Düğmesi Oluşturma

### <a name="to-create-a-new-toolbar-button"></a>Yeni araç çubuğu düğmesi oluşturma

1. İçinde [kaynak görünümü](../windows/resource-view-window.md) kaynak klasörü (örneğin, Project1.rc) genişletin.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. Genişletin **araç** klasörü ve düzenlemek için bir araç çubuğunu seçin.

3. Boş düğme araç çubuğunun sağ ucunda bir kimliği atayın. Düzenleyerek bunu yapabilirsiniz **kimliği** özelliğinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Örneğin, aynı menü seçeneği Kimliğine araç çubuğu düğmesi vermek isteyebilirsiniz. Bu durumda, seçmek için aşağı açılan liste kutusunu kullanın **kimliği** menü seçeneğinin.

   veya

   Araç çubuğunun sağ ucunda boş düğmeyi seçin (içinde **araç çubuğu görünümü** bölmesinde) ve çizim başlayın. Varsayılan düğme komut kimliği atanır (ID_BUTTON\<n >).

Ayrıca, kopyalayın ve bir görüntüyü yeni bir düğme olarak bir araç çubuğu üzerine yapıştırın.

### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>Görüntüyü bir araç çubuğuna bir düğme olarak eklemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), araç çift tıklayarak açın.

2. Ardından, araç için eklemek istediğiniz görüntü açın.

   > [!NOTE]
   > Görüntüyü Visual Studio'da açın, içinde açılır **görüntü** Düzenleyici. Diğer grafik programında görüntü de açabilirsiniz.

3. Gelen **Düzenle** menüsünde seçin **kopyalama**.

4. Araç için kaynak penceresinin üst kısmındaki kendi sekmesine tıklayarak geçin.

5. Gelen **Düzenle** menüsünde seçin **Yapıştır**.

   Görüntü, araç çubuğunda yeni bir düğme olarak görünür.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Araç Çubuğu Düğmesi Özellikleri](../windows/toolbar-button-properties.md)  
[Araç Çubuğu Düğmelerini Oluşturma, Taşıma ve Düzenleme](../windows/creating-moving-and-editing-toolbar-buttons.md)  
[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)