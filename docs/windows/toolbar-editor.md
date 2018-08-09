---
title: Araç çubuğu Düzenleyicisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.toolbar.F1
dev_langs:
- C++
helpviewer_keywords:
- resource editors, Toolbar editor
- editors, toolbars
- toolbars [C++], editing
- Toolbar editor
ms.assetid: aa9f0adf-60f6-4f79-ab05-bc330f15ec43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe9c73a09e2a0f220ee4454baefb07b7e65fcafa
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641653"
---
# <a name="toolbar-editor"></a>Araç Çubuğu Düzenleyicisi
Araç çubuğu Düzenleyicisi araç çubuğu kaynakları oluşturmak ve bit eşlemleri araç çubuğu kaynakları dönüştürmek sağlar. Araç çubuğu Düzenleyicisi araç çubuğu ve tamamlanmış bir uygulamada nasıl görüneceğini yakın benzer düğmeleri göstermek için bir grafik görüntüsünü kullanır.  
  
 Araç çubuğu Düzenleyicisi ile şunları yapabilirsiniz:  
  
-   [Yeni araç çubukları ve düğmeler](../windows/creating-new-toolbars.md)  
  
-   [Bit eşlemleri araç çubuğu kaynakları Dönüştür](../windows/converting-bitmaps-to-toolbars.md)  
  
-   [Oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri](../windows/creating-moving-and-editing-toolbar-buttons.md)  
  
-   [Araç ipuçları oluşturma](../windows/creating-a-tool-tip-for-a-toolbar-button.md)  
  
 Araç çubuğu Düzenleyicisi penceresi iki düğme resmini, Resim Düzenleyicisi penceresi ile aynı görünümünü gösterir. Bölünmüş çubuk iki bölmeyi ayırır. Bölmelerin göreli boyutlarını değiştirmek için bölme çubuğunu yanlara doğru sürükleyebilirsiniz. Etkin bölmede bir seçim kenarlığı görüntülenir. İki görünüm görüntünün konu araç çubuğudur.  
  
 ![Araç çubuğu Düzenleyicisi](../mfc/media/vctoolbareditor.gif "vcToolbarEditor")  
Araç Çubuğu Düzenleyicisi  
  
 İşlev Resim Düzenleyicisi araç çubuğu Düzenleyicisi benzer. Menü öğeleri, grafik araçları ve bit eşlem kılavuz Resim Düzenleyicisi penceresindekilerle aynıdır. Görüntü menüsü, Resim Düzenleyicisi araç çubuğu Düzenleyicisi arasında geçiş yapmanıza izin vermek için bir menü komutu yoktur. Grafik araç çubuğu, renkler paleti veya görüntü menüsü kullanma hakkında daha fazla bilgi için bkz. [Resim Düzenleyicisi](../windows/image-editor-for-icons.md).  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 MFC veya ATL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak düzenleyicileri](../windows/resource-editors.md)   
 [Menüler ve diğer kaynaklar](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)