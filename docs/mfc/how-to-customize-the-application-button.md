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
ms.openlocfilehash: 828886e6a5c4891e1fd7e1d820ee00542e052cc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351370"
---
# <a name="how-to-customize-the-application-button"></a>Nasıl yapılır: Uygulama Düğmesini Özelleştirme
Uygulama Düğmeye tıkladığınızda, komutları menüsü görüntülenir. Genellikle, menüyü dosya ile ilgili komutları gibi içeren **açık**, **kaydetmek**, **yazdırma**, ve **çıkış**.  
  
 ![MFC Şerit uygulama düğmesi](../mfc/media/application_button.png "application_button")  
  
 Uygulama düğmesini özelleştirme için içinde açın **özellikleri** penceresinde özelliklerini değiştirin ve Şerit denetimi Önizleme.  
  
### <a name="to-open-the-application-button-in-the-properties-window"></a>Uygulama düğmesi özelliklerini açmak için  
  
1.  Visual Studio'da üzerinde **Görünüm** menüsünde tıklatın **kaynak görünümü**.  
  
2.  İçinde **kaynak görünümü**, tasarım yüzeyine görüntülemek için Şerit kaynağı çift tıklatın.  
  
3.  Tasarım yüzeyinde uygulama düğmesi menüsüne sağ tıklayın ve ardından **özellikleri**.  
  
## <a name="application-button-properties"></a>Uygulama düğmesi özellikleri  
 Aşağıdaki tabloda, uygulama düğmesi özelliklerini tanımlar.  
  
|Özellik|Tanım|  
|--------------|----------------|  
|**Düğmeler**|Uygulama menüsü sağ alt köşesinde görüntülenen en çok üç düğmeleri koleksiyonunu içerir.|  
|**Açıklamalı alt yazı**|Denetimin metni belirtir. Diğer Şerit öğelerinden farklı olarak, uygulama düğmesi başlık metni görüntülemez. Bunun yerine, metin erişilebilirlik için kullanılır.|  
|**HDPI görüntüsü**|Yüksek nokta / inç (HDPI) uygulama düğme simgesi tanımlayıcısını belirtir. Yüksek DPI monitörde, uygulama çalıştığında, **HDPI görüntü** yerine kullanılan **görüntü**.|  
|**HDPI büyük görüntüler**|Yüksek DPI büyük görüntüleri tanımlayıcısını belirtir. Yüksek DPI monitörde, uygulama çalıştığında, **HDPI büyük görüntüleri** yerine kullanılan **görüntülerin büyük**.|  
|**HDPI küçük resimleri**|Yüksek DPI küçük resimleri tanımlayıcısını belirtir. Yüksek DPI monitörde, uygulama çalıştığında, **HDPI küçük resimler** yerine kullanılan **küçük resimler**.|  
|**ID**|Denetim tanımlayıcısını belirtir.|  
|**Görüntü**|Uygulama düğmesi simgesi tanımlayıcısını belirtir. Alfa Saydamlığı olan 32-bit 26 x 26 bit eşlem simgedir. Uygulama düğmesi tıklanana ya da üzerinden üzerine getirildiği simgesi bölümlerini saydam vurgulanır.|  
|**Anahtarları**|Anahtar ipucu Gezinti etkinleştirildiğinde görüntülenen dizeyi belirtir. ALT tuşuna bastığınızda anahtar ipucu Gezinti etkinleştirilir.|  
|**Büyük görüntüler**|Bir dizi 32 x 32 simgeleri içeren görüntü tanımlayıcısını belirtir. Simgeler ana öğe koleksiyonunun düğmeleri tarafından kullanılır.|  
|**Ana öğeleri**|Uygulama menüsünde görünen menü öğeleri koleksiyonu içerir.|  
|**MRU açıklamalı alt yazı**|En son listesi panelinde görüntülenen metni belirtir.|  
|**Küçük resimleri**|Bir dizi 16 x 16 simgeleri içeren görüntü tanımlayıcısını belirtir. Simgeler düğmeleri koleksiyonundaki düğmeleri tarafından kullanılır.|  
|**Kullanın**|Etkinleştirir veya son listesi paneli devre dışı bırakır. Son kullanılan listesi paneli uygulama menüsünde görüntülenir.|  
|**Genişlik**|Son kullanılan listesi paneli piksel cinsinden genişliğini belirtir.|  
  
 Uygulama menüsü tasarım yüzeyine görünmez. Görüntülemek için Şerit önizlemek veya uygulamayı çalıştırın.  
  
#### <a name="to-preview-the-ribbon-control"></a>Şerit denetimi önizlemek için  
  
-   Üzerinde **Şerit Düzenleyicisi araç**, tıklatın **Test Şerit**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)

