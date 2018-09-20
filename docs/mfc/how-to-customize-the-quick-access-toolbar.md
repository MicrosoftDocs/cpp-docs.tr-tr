---
title: 'Nasıl yapılır: hızlı erişim araç çubuğunu özelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- quick access toolbar [MFC], customization
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f3ec14971b69788892690c26ef2759f3b35d55f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419112"
---
# <a name="how-to-customize-the-quick-access-toolbar"></a>Nasıl yapılır: Hızlı Erişim Araç Çubuğunu Özelleştirme

Hızlı Erişim Araç çubuğu (QAT) ya da uygulama düğmesinin yanındaki veya kategori sekmeleri altında görüntülenen komutları kümesini içeren özelleştirilebilir bir araç çubuğudur. Aşağıdaki çizim, tipik bir hızlı erişim araç çubuğu gösterir.

![MFC Şerit hızlı erişim araç çubuğu](../mfc/media/quick_access_toolbar.png "quick_access_toolbar")

Hızlı Erişim Araç çubuğu özelleştirmek için açılır **özellikleri** penceresinde, alt komutları değiştirebilir ve ardından Şerit denetiminin önizlemesini.

### <a name="to-open-the-quick-access-toolbar-in-the-properties-window"></a>Özellikler penceresinde hızlı erişim araç çubuğunu açmak için

1. Visual Studio'da üzerinde **görünümü** menüsünde tıklatın **kaynak görünümü**.

1. İçinde **kaynak görünümü**, tasarım yüzeyinde görüntülemek için Şerit kaynağını çift tıklayın.

1. Tasarım yüzeyinde, hızlı erişim araç çubuğu menüsü sağ tıklayın ve ardından **özellikleri**.

## <a name="quick-access-toolbar-properties"></a>Hızlı Erişim Araç çubuğu özellikleri

Aşağıdaki tabloda, hızlı erişim araç özelliklerini tanımlar.

|Özellik|Tanım|
|--------------|----------------|
|QAT konumu|Uygulama başladığında hızlı erişim araç çubuğu konumunu belirtir. Konumu olabilir **yukarıda** veya **aşağıda** Şerit denetimi.|
|QAT öğeleri|Hızlı Erişim Araç çubuğu için mevcut olan komutları belirtir.|

#### <a name="to-add-or-remove-commands-on-the-quick-access-toolbar"></a>Ekleme veya hızlı erişim araç çubuğundaki komutları kaldırma

1. İçinde **özellikleri** penceresinde tıklayın **QAT öğeleri**ve ardından üç nokta düğmesine **(...)** .

1. İçinde **QAT öğe Düzenleyicisi** iletişim kutusunda **Ekle** ve **Kaldır** hızlı erişim araç çubuğu üzerinde komutların listesini değiştirmek için düğmeler.

1. Bir komut hem hızlı erişim araç çubuğu ve hızlı erişim araç çubuğu menüsünde görünmesini istiyorsanız, komut yanındaki kutuyu seçin. Komutun yalnızca menüde görünmesini istiyorsanız, kutunun işaretini kaldırın.

## <a name="previewing-the-ribbon"></a>Önizleme şeridi

Hızlı Erişim Araç çubuğu komutlarını tasarım yüzeyinde görünmez. Bunları görüntülemek için şeridi önizlemenizi veya uygulamayı çalıştırın.

#### <a name="to-preview-the-ribbon-control"></a>Şerit denetiminin önizlemesini görüntülemek için

- Üzerinde **Şerit Düzenleyici araç çubuğu**, tıklayın **şeridi Sına**.

## <a name="see-also"></a>Ayrıca Bkz.

[Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)

