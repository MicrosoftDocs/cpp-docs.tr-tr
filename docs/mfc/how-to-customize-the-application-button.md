---
title: 'Nasıl yapılır: Uygulama Düğmesini Özelleştirme'
ms.date: 09/07/2019
helpviewer_keywords:
- application button [MFC], customizing
ms.assetid: ebb11180-ab20-43df-a234-801feca9eb38
ms.openlocfilehash: 9160e602848adf8dc95c840d702e0b1a1b2f9049
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620036"
---
# <a name="how-to-customize-the-application-button"></a>Nasıl yapılır: Uygulama Düğmesini Özelleştirme

Uygulama düğmesine tıkladığınızda bir komut menüsü görüntülenir. Genellikle, menü **açma**, **kaydetme**, **yazdırma**ve **Çıkış**gibi dosyayla ilgili komutlar içerir.

![MFC Şerit uygulaması düğmesi](../mfc/media/application_button.png "MFC Şerit uygulaması düğmesi")

Uygulama düğmesini özelleştirmek için, **özellikleri Özellikler** penceresinde açın ( **kaynak görünümü**), özelliklerini değiştirin ve ardından şerit denetimini önizleyin.

### <a name="to-open-the-application-button-in-the-properties-window"></a>Özellikler penceresi uygulama düğmesini açmak için

1. Visual Studio 'da, **Görünüm** menüsünde **kaynak görünümü**' a tıklayın.

1. **Kaynak görünümü**, şerit kaynağına çift tıklayarak tasarım yüzeyinde görüntüleyin.

1. Tasarım yüzeyinde, uygulama düğmesi menüsüne sağ tıklayıp **Özellikler**' e tıklayın.

## <a name="application-button-properties"></a>Uygulama düğmesi özellikleri

Aşağıdaki tablo, uygulama düğmesinin özelliklerini tanımlar.

|Özellik|Tanım|
|--------------|----------------|
|**Düğmeler**|Uygulama menüsünün sağ alt köşesinde görüntülenen en fazla üç düğme koleksiyonunu içerir.|
|**Başlık**|Denetimin metnini belirtir. Diğer şerit öğelerinden farklı olarak, uygulama düğmesi açıklamalı alt yazı metnini görüntülemez. Bunun yerine, metin erişilebilirlik için kullanılır.|
|**HDPı resmi**|İnç başına yüksek nokta (HDPı) uygulaması düğme simgesinin tanımlayıcısını belirtir. Uygulama yüksek DPı monitörde çalıştığında, **görüntü**yerine **HDPI görüntüsü** kullanılır.|
|**HDPI büyük görüntüler**|Yüksek DPı büyük görüntülerinin tanımlayıcısını belirtir. Uygulama yüksek DPı bir monitörde çalıştırıldığında, **büyük görüntüler**yerine **hdpi büyük görüntüleri** kullanılır.|
|**HDPI küçük görüntüler**|Yüksek DPı küçük görüntülerinin tanımlayıcısını belirtir. Uygulama yüksek DPı monitörde çalıştığında, **küçük görüntüler**yerine **hdpi küçük görüntüler** kullanılır.|
|**ID**|Denetimin tanımlayıcısını belirtir.|
|**Görüntüyle**|Uygulama düğmesi simgesinin tanımlayıcısını belirtir. Simge, Alfa saydamlığına sahip 32 bitlik bir 26x26 bit eşlemdir. Simgenin saydam kısımları, uygulama düğmesine tıklandığında veya üzerine gelindiğinde vurgulanacaktır.|
|**Anahtarlar**|Anahtar ipucu gezintisi etkinleştirildiğinde görüntülenen dizeyi belirtir. ALT tuşuna bastığınızda anahtar ipucu gezintisi etkinleştirilir.|
|**Büyük görüntüler**|Bir dizi 32x32 simgesini içeren görüntünün tanımlayıcısını belirtir. Simgeler, ana öğeler koleksiyonundaki düğmeler tarafından kullanılır.|
|**Ana öğeler**|Uygulama menüsünde görünen bir menü öğeleri koleksiyonu içerir.|
|**MRU başlığı**|Son kullanılan liste panelinde görüntülenen metni belirtir.|
|**Küçük görüntüler**|Bir dizi 16x16 simgesini içeren görüntünün tanımlayıcısını belirtir. Simgeler, düğmeler koleksiyonundaki düğmeler tarafından kullanılır.|
|**Kullanma**|Son kullanılan liste panelini etkinleştirilir veya devre dışı bırakır. En son liste paneli uygulama menüsünde görünür.|
|**Genişlik**|Son kullanılan liste panelinin piksel cinsinden genişliğini belirtir.|

Uygulama menüsü tasarım yüzeyinde görünmez. Bunu görüntülemek için, şeridin önizlemesini ya da uygulamayı çalıştırmanız gerekir.

#### <a name="to-preview-the-ribbon-control"></a>Şerit denetimini önizlemek için

- **Şerit Düzenleyicisi araç çubuğunda**, **test şeridi**' ne tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Şerit Tasarımcısı (MFC)](ribbon-designer-mfc.md)
