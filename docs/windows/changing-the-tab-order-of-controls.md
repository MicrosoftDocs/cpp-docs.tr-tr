---
title: "Denetimlerin sekme sırasını değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [C++], tab order
- focus, tab order
- tab controls, tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls, tab order
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dca6b1bb894aa2219a0352ba9c359e6f3c5a4677
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="changing-the-tab-order-of-controls"></a>Denetimlerin Sekme Sırasını Değiştirme
Sekme sırası içinde SEKME tuşuna giriş odağını bir denetimden bir iletişim kutusu içinde sonraki taşır sırasıdır. Genellikle sekme sırasını soldan sağa ve yukarıdan bir iletişim kutusunda devam eder. Her denetim sahip bir **Tabstop** denetim giriş odağını alıp almayacağını belirler özelliği.  
  
### <a name="to-set-input-focus-for-a-control"></a>Bir denetim için giriş odağını ayarlamak için  
  
1.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window)seçin **True** veya **False** içinde **Tabstop** özelliği.  
  
 Sekme sırasını parçası olarak doğru gerek ayarlanan Tabstop özelliği olmayan bile denetler. Bu örneğin önemli olabilir, ne zaman, [erişim tuşları (anımsatıcıları) tanımlamak](../windows/defining-mnemonics-access-keys.md) açıklamalı alt yazıları olduğu değil denetimleri için. İlgili bir denetim için erişim anahtarı içeren statik metin sekmesini sırayla ilgili denetim hemen önce gelmelidir.  
  
> [!NOTE]
>  İletişim kutusu çakışan denetimler içeriyorsa, sekme sırasını değiştirme denetimleri görüntülenme biçimini değiştirebilir. Daha sonra sekme sırası gelen denetimler sekme sırası öncesinde tüm çakışan denetimlerinin üstünde her zaman görüntülenir.  
  
#### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>Geçerli sekme sırası tüm denetimler için bir iletişim kutusu görüntülemek için  
  
1.  Üzerinde **biçimi** menüsünde tıklatın **sekme sırası**.  
  
 \-veya -  
  
-   CTRL + d'e basın.  
  
#### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>İletişim kutusundaki tüm denetimlerin sekme sırasını değiştirmek için  
  
1.  Üzerinde **biçimi** menüsünde tıklatın **sekme sırası**.  
  
     Her denetim, sol üst köşedeki birtakım onun yerine geçerli sekme sırasını gösterir.  
  
2.  Her denetim izlemek için SEKME tuşunu istediğiniz sırayla tıklayarak sekme sırasını ayarlayın.  
  
3.  Tuşuna **ENTER** çıkmak için **sekme sırası** modu.  
  
    > [!TIP]
    >  Sekme sırası modu girdikten sonra sekme sırasını değiştirme becerisini devre dışı bırakmak için ESC veya ENTER tuşuna basabilirsiniz.  
  
#### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>İki veya daha fazla denetimlerin sekme sırasını değiştirmek için  
  
1.  Gelen **biçimi** menüsünde seçin **sekme sırası**.  
  
2.  Sipariş değişikliği nerede başlayacağını belirtin. Bunu yapmak için basılı **CTRL** anahtar ve denetim başlamak için değiştirilmiş sırasını istediğiniz bir önce'ı tıklatın.  
  
     Örneğin, denetimleri ile 9 arasında 7 sırasını değiştirmek isterseniz, CTRL tuşunu basılı tutun, sonra Denetim 6 ilk seçin.  
  
    > [!NOTE]
    >  Belirli bir denetim numarası 1 (ilk olarak sekme sırası) ayarlamak için denetimi çift tıklatın.  
  
3.  CTRL tuşunu bırakın ve o noktadan itibaren izlemek için SEKME tuşunu istediğiniz sırayla denetimleri'i tıklatın.  
  
4.  Tuşuna **ENTER** çıkmak için **sekme sırası** modu.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimlerin düzenlenmesi](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [Denetimler](../mfc/controls-mfc.md)

