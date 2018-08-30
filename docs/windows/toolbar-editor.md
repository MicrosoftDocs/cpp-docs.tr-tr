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
ms.openlocfilehash: b0f9c4977ff82bd3f4af40af657a4bfed3a90568
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197882"
---
# <a name="toolbar-editor"></a>Araç Çubuğu Düzenleyicisi

**Araç** Düzenleyicisi araç çubuğu kaynakları oluşturup bit eşlemleri araç çubuğu kaynakları dönüştürme sağlar. **Araç** Düzenleyicisi araç çubuğu ve tamamlanmış bir uygulamada nasıl görüneceğini yakın benzer düğmeleri göstermek için bir grafik görüntüsünü kullanır.

İle **araç** Düzenleyicisi, şunları yapabilirsiniz:

- [Yeni araç çubukları ve düğmeler](../windows/creating-new-toolbars.md)

- [Bit eşlemleri araç çubuğu kaynakları Dönüştür](../windows/converting-bitmaps-to-toolbars.md)

- [Oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri](../windows/creating-moving-and-editing-toolbar-buttons.md)

- [Araç ipuçları oluşturma](../windows/creating-a-tool-tip-for-a-toolbar-button.md)

**Araç** Düzenleyicisi penceresi iki düğme resmini, Resim Düzenleyicisi penceresi ile aynı görünümlerini gösterir. Bölünmüş çubuk iki bölmeyi ayırır. Bölmelerin göreli boyutlarını değiştirmek için bölme çubuğunu yanlara doğru sürükleyebilirsiniz. Etkin bölmede bir seçim kenarlığı görüntülenir. İki görünüm görüntünün konu araç çubuğudur.

![Araç çubuğu Düzenleyicisi](../mfc/media/vctoolbareditor.gif "vcToolbarEditor")  
Araç Çubuğu Düzenleyicisi

**Araç** Düzenleyicisi benzer **görüntü** işlevleri düzenleyicisinde. Menü öğeleri, grafik araçları ve bit eşlem kılavuz penceresindekilerle aynıdır **görüntü** Düzenleyici. Bir menü komutu yoktur **görüntü** arasında geçiş yapmanıza izin vermek için menü **araç** Düzenleyicisi ve **görüntü** Düzenleyici. Kullanma hakkında daha fazla bilgi için **grafik** araç **renkleri** paleti veya **görüntü** menüsünde görmek [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)  
[Menüler ve diğer kaynaklar](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)