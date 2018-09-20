---
title: 'Nasıl yapılır: uygulama düğmesini özelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application button [MFC], customizing
ms.assetid: ebb11180-ab20-43df-a234-801feca9eb38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef82904a5c84847f3f0064cba6dee171c960f135
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401478"
---
# <a name="how-to-customize-the-application-button"></a>Nasıl yapılır: Uygulama Düğmesini Özelleştirme

Uygulama Düğmeye tıkladığınızda, komutları içeren bir menü görüntülenir. Genellikle, menü gibi dosya ile ilgili komutları içeren **açık**, **Kaydet**, **yazdırma**, ve **çıkış**.

![MFC Şerit uygulama düğmesi](../mfc/media/application_button.png "application_button")

Uygulama düğmesini özelleştirme için projeyi açın **özellikleri** penceresinde, özelliklerini değiştirin ve sonra da Şerit denetiminin önizlemesini görüntüleyin.

### <a name="to-open-the-application-button-in-the-properties-window"></a>Özellikler penceresinde Uygulama düğmesini açmak için

1. Visual Studio'da üzerinde **görünümü** menüsünde tıklatın **kaynak görünümü**.

1. İçinde **kaynak görünümü**, tasarım yüzeyinde görüntülemek için Şerit kaynağını çift tıklayın.

1. Tasarım yüzeyinde, uygulama düğmesini menüsü sağ tıklayın ve ardından **özellikleri**.

## <a name="application-button-properties"></a>Uygulama düğmesi özellikleri

Aşağıdaki tabloda, uygulama düğmesini özelliklerini tanımlar.

|Özellik|Tanım|
|--------------|----------------|
|**Düğmeler**|Uygulama menüsü sağ alt köşesinde görüntülenen en fazla üç düğmelerinin koleksiyonunu içerir.|
|**Resim yazısı**|Denetimin metnini belirtir. Diğer bir Şerit öğesinin aksine, uygulama düğmesini açıklamalı alt yazı metni görüntülemez. Bunun yerine, metin erişilebilirlik için kullanılır.|
|**HDPI görüntüsü**|Yüksek nokta / inç (HDPI) uygulama düğmesinin simgesi tanımlayıcısını belirtir. Uygulamanın yüksek bir DPI monitörde çalıştığında **HDPI görüntüsü** yerine kullanılan **görüntü**.|
|**HDPI büyük görüntüleri**|Yüksek DPI büyük resimler tanımlayıcısını belirtir. Uygulamanın yüksek bir DPI monitörde çalıştığında **HDPI büyük görüntüleri** yerine kullanılan **büyük resimler**.|
|**HDPI küçük görüntüleri**|Yüksek DPI küçük resimler tanımlayıcısını belirtir. Uygulamanın yüksek bir DPI monitörde çalıştığında **HDPI küçük görüntüleri** yerine kullanılan **küçük resimler**.|
|**ID**|Denetimin tanımlayıcısını belirtir.|
|**Görüntü**|Uygulama düğmesi simgesi tanımlayıcısını belirtir. Alfa Saydamlığı olan 32-bit 26 x 26 bit eşlem simgesi bulunuyor. Uygulama düğmesine tıklandığında ya da üzerine gelindiğinde simgesi saydam kısımları vurgulanır.|
|**anahtarları**|Anahtar ipucu gezinmesi etkinleştirildiğinde görüntülenen dizeyi belirtir. ALT tuşuna bastığınızda anahtar ipucu gezinmesi etkinleştirilir.|
|**Büyük resimler**|Bir dizi 32 x 32 simgeleri içeren görüntünün tanımlayıcısını belirtir. Simge düğmeleri ana öğe koleksiyonunun tarafından kullanılır.|
|**Ana öğeler**|Uygulama menüsünde görüntülenen menü öğelerinin bir koleksiyonunu içerir.|
|**MRU başlığı**|Son liste Panoda görüntülenen metni belirtir.|
|**Küçük resimler**|Bir dizi 16 x 16 simgeleri içeren görüntünün tanımlayıcısını belirtir. Simge düğmeleri koleksiyondaki düğmeleri tarafından kullanılır.|
|**Kullanın**|Etkinleştirir veya yeni liste bölmesi devre dışı bırakır. Uygulama menüsünde Yeni liste bölmesi görünür.|
|**Genişlik**|Yeni liste bölmesi piksel cinsinden genişliğini belirtir.|

Uygulama menüsünde tasarım yüzeyinde görünmüyor. Bunu görüntülemek için şeridi önizlemenizi veya uygulamayı çalıştırın.

#### <a name="to-preview-the-ribbon-control"></a>Şerit denetiminin önizlemesini görüntülemek için

- Üzerinde **Şerit Düzenleyici araç çubuğu**, tıklayın **şeridi Sına**.

## <a name="see-also"></a>Ayrıca Bkz.

[Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)

