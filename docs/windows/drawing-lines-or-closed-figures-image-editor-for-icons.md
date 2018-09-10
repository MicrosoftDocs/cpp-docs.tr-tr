---
title: Çizgi veya kapalı şekiller (simgeler için görüntü Düzenleyicisi) çizim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], drawing lines
- shapes, drawing
ms.assetid: 7edd86db-77b1-451f-8001-bbfed9c6304f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c6c5652f61211ebd4d33de6f2dce07bd49b4f0a0
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313246"
---
# <a name="drawing-lines-or-closed-figures-image-editor-for-icons"></a>Çizgi veya Kapalı Şekiller Çizme (Simgeler İçin Görüntü Düzenleyicisi)

Resim Düzenleyicisi araçları için satırlar çizme ve tüm kapalı şekiller aynı şekilde çalışır: bir noktada ekleme noktasını yerleştirin ve diğerine sürükleyin. Satırlar için bu uç noktalardır. Kapalı şekiller için bu, Şekil sınırlayıcı bir dikdörtgen zıt köşe noktalarıdır.

Geçerli fırça seçim tarafından belirlenen bir genişliği çizgileri çizilir ve Çerçeveli rakamları genişliği seçilen tarafından belirlenen bir genişliği çizilir. Sağ fare düğmesine basarsanız satırları ve Çerçeveli hem doludur ve tüm şekilleri, farenin sol düğmesine basarsanız geçerli ön plan rengini veya arka plan rengi geçerli çizilir.

### <a name="to-draw-a-line"></a>Bir çizgi çizmek için

1. Üzerinde [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md) (veya **görüntü** menüsünde **Araçları** komut), tıklayın **satırı** aracı.

2. Gerekirse, renk ve fırça seçin:

   - İçinde [renkler paleti](../windows/colors-window-image-editor-for-icons.md), ön plan rengi seçmesini farenin sol düğmesine veya arka plan rengi seçmesini sağ fare düğmesine tıklayın.

   - İçinde [seçenekleri Seçici](../windows/toolbar-image-editor-for-icons.md), kullanmak istediğiniz fırça temsil eden bir şekle tıklayın.

3. İşaretçiyi çizginin başlangıç noktasına yerleştirin.

4. Çizginin bitiş noktasına sürükleyin.

### <a name="to-draw-a-closed-figure"></a>Kapalı şekle çizmek için

1. Üzerinde **görüntü Düzenleyicisi** araç çubuğu (veya **görüntü** menüsünde **Araçları** komut),'a tıklayın bir **kapalı şekil çizme** aracı.

   **Kapalı şekil çizme** araçları ilgili kendi düğmelerini belirtildiği gibi şekiller oluşturun.

2. Gerekirse, renk ve çizgi genişliği seçin.

3. İşaretçiyi bir şekil Çiz istediğiniz Dikdörtgen alanı köşeye taşıyın.

4. Çapraz zıt köşe için işaretçiyi sürükleyin.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)  
[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)  
[Renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md)