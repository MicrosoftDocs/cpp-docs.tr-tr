---
title: Denetimlerin sekme sırasını değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], tab order
- focus, tab order
- tab controls, tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls, tab order
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5f846244956687b73b6fc7272fe0c4d7d00d0e0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596347"
---
# <a name="changing-the-tab-order-of-controls"></a>Denetimlerin Sekme Sırasını Değiştirme

Sekme sırasını sırayı olan **sekmesini** anahtarı bir iletişim kutusu içindeki bir denetimden giriş odağını taşır. Genellikle sekme sırası, soldan sağa ve yukarıdan bir iletişim kutusunda devam eder. Her denetimin bir **sekme durağı** özelliği bir denetimin Girintiyi alıp almayacağını belirler.

### <a name="to-set-input-focus-for-a-control"></a>Bir denetim için giriş odağı ayarlamak için

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)seçin **True** veya **False** içinde **sekme durağı** özelliği.

Sahip olmadığınız bile denetimleri **sekme durağı** özelliğini **True** sekme sırasını bir parçası olmanız gerekir. Bu örneğin önemli olabilir, size [erişim tuşları (anımsatıcıları) tanımlamak](../windows/defining-mnemonics-access-keys.md) açıklamalı alt yazılar olmayan denetimler için. İlişkili bir denetim için bir erişim anahtarı içeren statik metin ilgili denetimin sekme sırasında hemen önce gelmelidir.

> [!NOTE]
> Sekme sırasını değiştirme, iletişim kutusu örtüşen denetimler içeriyorsa, denetimleri görüntülenme şeklini değiştirebilir. Daha sonra sekme sırasının gelen denetimler, her zaman sekme sırasının kendilerinden herhangi bir çakışan denetim üzerinde görüntülenir.

### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>Geçerli sekme sırasını tüm denetimleri için iletişim kutusunda görüntülemek için

1. Üzerinde **biçimi** menüsünde tıklatın **sekme sırasını**.

\- veya -

- Tuşuna **Ctrl**+**D**.

### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>İletişim kutusundaki tüm denetimlerin sekme sırasını değiştirmek için

1. Üzerinde **biçimi** menüsünde tıklatın **sekme sırasını**.

   Her denetimin sol üst köşedeki birkaç onun yerine geçerli sekme sırasının gösterir.

2. Her denetim, istediğiniz sırayla tıklayarak bir sekme sırasını ayarlama **sekmesini** izlemek için anahtar.

3. Tuşuna **Enter** çıkmak için **sekme sırasını** modu.

   > [!TIP]
   > Girdiğiniz sonra **sekme sırasını** modu basabilirsiniz **Esc** veya **Enter** sekme sırasını değiştirme özelliği devre dışı bırakmak için.

### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>İki veya daha fazla denetim için sekmesinde sırasını değiştirmek için

1. Gelen **biçimi** menüsünde seçin **sekme sırasını**.

2. Sırayla değişikliğin nerede başlayacağını belirtin. Bunu yapmak için basılı **Ctrl** basıp önce değiştirilen sırasını başlatmak için istediğiniz bir denetim tıklayın.

   Örneğin, denetimlerin sırasını değiştirmek istiyorsanız `7` aracılığıyla `9`, basılı **Ctrl**, sonra kumanda `6` ilk.

   > [!NOTE]
   > Belirli bir denetim numarası için ayarlamak için `1` (ilk sekme sırasında), denetimi çift tıklatın.

3. Yayın **Ctrl** anahtar ve ardından istediğiniz sırayla denetimleri tıklatın **sekmesini** o noktadan itibaren izlemek için anahtar.

4. Tuşuna **Enter** çıkmak için **sekme sırasını** modu.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimlerin Düzenlenmesi](../windows/arrangement-of-controls-on-dialog-boxes.md)  
[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)  
[Denetimler](../mfc/controls-mfc.md)