---
title: Araç çubuğu Düzenleyicisi (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.toolbar.F1
helpviewer_keywords:
- resource editors [C++], Toolbar editor
- editors, toolbars
- toolbars [C++], editing
- Toolbar editor
ms.assetid: aa9f0adf-60f6-4f79-ab05-bc330f15ec43
ms.openlocfilehash: 7efff3d4d784de6ee3130c3481f3674351cc7463
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486065"
---
# <a name="toolbar-editor-c"></a>Araç çubuğu Düzenleyicisi (C++)

**Araç** Düzenleyici, C++ araç çubuğu kaynakları oluşturmak ve bit eşlemleri araç çubuğu kaynakları Dönüştür olanak tanır. **Araç** Düzenleyicisi araç çubuğu ve tamamlanmış bir uygulamada nasıl görüneceğini yakın benzer düğmeleri göstermek için bir grafik görüntüsünü kullanır.

İle **araç** Düzenleyicisi, şunları yapabilirsiniz:

- [Yeni araç çubukları ve düğmeler](../windows/creating-new-toolbars.md)

- [Bit eşlemleri araç çubuğu kaynakları Dönüştür](../windows/converting-bitmaps-to-toolbars.md)

- [Oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri](../windows/creating-moving-and-editing-toolbar-buttons.md)

- [Araç ipuçları oluşturma](../windows/creating-a-tool-tip-for-a-toolbar-button.md)

**Araç** Düzenleyicisi penceresi iki düğme resmini, Resim Düzenleyicisi penceresi ile aynı görünümlerini gösterir. Bölünmüş çubuk iki bölmeyi ayırır. Bölmelerin göreli boyutlarını değiştirmek için bölme çubuğunu yanlara doğru sürükleyebilirsiniz. Etkin bölmede bir seçim kenarlığı görüntülenir. İki görünüm görüntünün konu araç çubuğudur.

![Araç çubuğu Düzenleyicisi](../mfc/media/vctoolbareditor.gif "vcToolbarEditor") araç çubuğu Düzenleyicisi

**Araç** Düzenleyicisi benzer **görüntü** işlevleri düzenleyicisinde. Menü öğeleri, grafik araçları ve bit eşlem kılavuz penceresindekilerle aynıdır **görüntü** Düzenleyici. Bir menü komutu yoktur **görüntü** arasında geçiş yapmanıza izin vermek için menü **araç** Düzenleyicisi ve **görüntü** Düzenleyici. Kullanma hakkında daha fazla bilgi için **grafik** araç **renkleri** paleti veya **görüntü** menüsünde görmek [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Menüler ve diğer kaynaklar](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)