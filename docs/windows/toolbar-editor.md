---
title: Araç çubuğu Düzenleyicisi (C++) | Microsoft Docs
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
- resource editors [C++], Toolbar editor
- editors, toolbars
- toolbars [C++], editing
- Toolbar editor
ms.assetid: aa9f0adf-60f6-4f79-ab05-bc330f15ec43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0bb329b60b72aae268252ae3ddbcc2c63d4a18f6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389701"
---
# <a name="toolbar-editor-c"></a>Araç çubuğu Düzenleyicisi (C++)

**Araç** Düzenleyici, C++ araç çubuğu kaynakları oluşturmak ve bit eşlemleri araç çubuğu kaynakları Dönüştür olanak tanır. **Araç** Düzenleyicisi araç çubuğu ve tamamlanmış bir uygulamada nasıl görüneceğini yakın benzer düğmeleri göstermek için bir grafik görüntüsünü kullanır.

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

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Menüler ve diğer kaynaklar](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)