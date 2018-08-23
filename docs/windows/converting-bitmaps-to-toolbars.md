---
title: Bit eşlemleri araç çubuklarına dönüştürme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bitmaps [C++], converting to toolbars
- Toolbar editor, converting bitmaps
- toolbars [C++], converting bitmaps
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d5524b1d5ecb3fa4de38f46706f26d2a318fe5ef
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602406"
---
# <a name="converting-bitmaps-to-toolbars"></a>Bit Eşlemleri Araç Çubuklarına Dönüştürme

Yeni bir araç çubuğu bit eşlem dönüştürerek oluşturabilirsiniz. Bit eşlem Grafik araç çubuğu düğmesi görüntülerde dönüştürür. Genellikle her düğme için bir görüntü ile birkaç düğme resimlerini üzerinde tek bir bit eşlem bit eşlem içerir. Görüntüleri, herhangi bir boyutta olabilir; 16 piksel genişliğinde ve resmin yüksekliğini varsayılan değerdir. Düğme görüntüleri boyutunu belirtebilirsiniz [yeni araç çubuğu kaynağı iletişim kutusu](../windows/new-toolbar-resource-dialog-box.md) seçtiğinizde **araç çubuğu Düzenleyicisi** gelen **görüntü** Resim Düzenleyicisi sırada menüsünde.

### <a name="to-convert-bitmaps-to-a-toolbar"></a>Bit eşlemleri araç çubuğuna dönüştürmek için

1. Mevcut bir bit eşlem kaynağındaki açın [Resim Düzenleyicisi](../windows/image-editor-for-icons.md). (Bit eşlem .rc dosyanız yoksa, .rc dosyasına sağ tıklayın, seçin **alma** kısayol menüsünden, .rc dosyasına eklemek istediğiniz bit eşlem gidin ve ardından **açık**.)

2. Gelen **görüntü** menüsünde seçin **araç çubuğu Düzenleyicisi**.

   [Yeni araç çubuğu kaynağı iletişim kutusu](../windows/new-toolbar-resource-dialog-box.md) görünür. Genişlik ve yükseklik simgesi görüntülerin bit eşlem eşleşecek şekilde değiştirebilirsiniz. Araç çubuğu görüntüsü, ardından araç çubuğu Düzenleyicisi'nde görüntülenir.

3. Dönüştürme işlemini tamamlamak için komutu değiştirmek **kimliği** düğmesini kullanarak [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Yeni tür **kimliği** veya bir **kimliği** aşağı açılan listeden.

   > [!TIP]
   > **Özellikleri** pencere bir başlık çubuğundaki Raptiye düğme içerir. Bu düğmeye tıklandığında etkinleştirir veya devre dışı bırakır **Otomatik Gizle** penceresi. Tek tek özellik windows yeniden gerek kalmadan hızla tüm araç çubuğu düğmesi özellikleri geçiş yapmak için kapatma **Otomatik Gizle** kapalı böylece **özellikleri** penceresi sabit kalır.

Yeni araç çubuğundaki düğmeler komut kimlikleri kullanarak da değiştirebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Yeni araç çubuğu düzenleme hakkında daha fazla bilgi için bkz. [oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri](../windows/creating-moving-and-editing-toolbar-buttons.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Yeni Araç Çubukları Oluşturma](../windows/creating-new-toolbars.md)  
[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)