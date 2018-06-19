---
title: Kısayol tuşları (simgeler için görüntü Düzenleyicisi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2b19fb16410f7d720d11e8b8560cde4cadf10b1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861538"
---
# <a name="accelerator-keys-image-editor-for-icons"></a>Hızlandırma Tuşları (Simgeler İçin Görüntü Düzenleyicisi)
Anahtarlar için varsayılan olarak bağlı görüntü düzenleyici komutlarını Hızlandırıcı tuşları altındadır. Hızlandırıcı tuşları değiştirmek için tıklatın. **seçenekleri** üzerinde **Araçları** menüsünde ve ardından **klavye** altında **ortam** klasör. Daha fazla bilgi için bkz: [tanımlama ve özelleştirme klavye kısayolları](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).  
  
> [!NOTE]
>  İletişim kutuları, adları ve menü komutlarını, gördüğünüz konumlarını Seçenekleri Yardımı'nda etkin ayarlarınıza veya sürümünüze bağlı olarak açıklanan nedir alanından farklı olabilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
|Komut|Anahtarları|Açıklama|  
|-------------|----------|-----------------|  
|Image.AirBrushTool|CTRL + A|Seçili boyutu ve rengi ile bir havalı fırça kullanma çizer.|  
|Image.BrushTool|CTRL + B|Seçilen şekil, boyutu ve rengi fırça kullanma çizer.|  
|Image.CopyAndOutlineSelection|CTRL + SHIFT + U|Geçerli seçim bir kopyasını oluşturur ve bunu özetler. Arka plan rengi geçerli seçim içeriyorsa, varsa onu dışlanıp [saydam](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) seçili.|  
|Image.DrawOpaque|CTRL + J|Geçerli seçimi ya da yapar [donuk veya saydam](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).|  
|Image.EllipseTool|CTRL + P|Seçili çizgi genişliğini ve renk elips çizer.|  
|Image.EraserTool|CTRL + SHIFT + I|Görüntünün (geçerli arka plan rengiyle) bir kısmı siler.|  
|Image.FilledEllipseTool|CTRL + SHIFT + ALT + P|Doldurulmuş elips çizer.|  
|Image.FilledRectangleTool|CTRL + SHIFT + ALT + R|Doldurulmuş dikdörtgen çizer.|  
|Image.FilledRoundRectangleTool|CTRL + SHIFT + ALT + W|Dolu bir yuvarlak dikdörtgen çizer.|  
|Image.FillTool|CTRL + F|Bir alanı doldurur.|  
|Image.FlipHorizontal|CTRL + H|Görüntüyü veya seçimi yatay olarak döndürür.|  
|Image.FlipVertical|SHIFT + ALT + H|Görüntüyü veya seçimi düşey olarak döndürür.|  
|Image.LargerBrush|CTRL + =|Her yönde bir piksel tarafından Fırça boyutu artar. Fırça boyutunu azaltmak için bu tabloda Image.SmallerBrush bakın.|  
|Image.LineTool|CTRL + L|Seçilen şekil, boyutu ve rengi düz bir çizgi çizer.|  
|Image.MagnificationTool|CTRL + M|Etkinleştirir **Magnıfy** görüntünüzü belirli bölümlerine büyütmek olanak tanıyan aracı.|  
|Image.Magnify|CTRL + SHIFT + M|Geçerli büyütme ve 1:1 büyütme arasında geçiş yapar.|  
|Image.NewImageType|EKLE|Başlatır [yeni \<aygıt > görüntü türü iletişim kutusu](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md) ile farklı görüntü türü için bir görüntü oluşturabilirsiniz.|  
|Image.NextColor|CTRL +]<br /><br /> - veya -<br /><br /> CTRL + SAĞ OK|Çizim ön plan rengini sonraki palet renge dönüşür.|  
|Image.NextRightColor|CTRL + SHIFT +]<br /><br /> - veya -<br /><br /> SHIFT + CTRL + SAĞ OK|Çizim arka plan rengi sonraki palet rengi değişir.|  
|Image.OutlinedEllipseTool|SHIFT + ALT + P|Anahat ile doldurulmuş elips çizer.|  
|Image.OutlinedRectangleTool|SHIFT + ATL + R|Anahat ile doldurulmuş dikdörtgen çizer|  
|Image.OutlinedRoundRectangleTool|SHIFT + ALT + W|Anahat ile doldurulmuş yuvarlak dikdörtgen çizer.|  
|Image.PencilTool|CTRL + I|Bir tek pikselli kalem kullanarak çizer.|  
|Image.PreviousColor|CTRL + [<br /><br /> - veya -<br /><br /> CTRL + SOL OK|Çizim ön plan rengini önceki palet renge dönüşür.|  
|Image.PreviousRightColor|CTRL + SHIFT + [<br /><br /> - veya -<br /><br /> SHIFT + CTRL + SOL OK|Çizim arka plan rengi önceki palet rengi değişir.|  
|Image.RectangleSelectionTool|SHIFT + ALT + S|Taşıma, kopyalama veya düzenlemek için Görüntü dikdörtgen bir kısmı seçer.|  
|Image.RectangleTool|ATL + R|Seçili çizgi genişliğini ve renk ile bir dikdörtgen çizer.|  
|Image.Rotate90Degrees|CTRL + SHIFT + H|Görüntüyü veya seçimi 90 derece döndürür.|  
|Image.RoundedRectangleTool|ALT + W|Seçili çizgi genişliğini ve renk yuvarlak dikdörtgen çizer.|  
|Image.ShowGrid|CTRL + ALT + S|Piksel kılavuzunu geçiş yapar (seçer veya temizler **piksel kılavuzunu** seçeneğini [kılavuz Ayarları iletişim kutusu](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|  
|Image.ShowTileGrid|CTRL + SHIFT + ALT + S|Döşeme geçiş yapar (seçer veya temizler **döşeme** seçeneğini [kılavuz Ayarları iletişim kutusu](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|  
|Image.SmallBrush|CTRL +. (nokta)|Azaltır **fırça** bir piksel boyutunda. (Ayrıca Image.LargerBrush ve Image.SmallerBrush bu tabloya bakın.)|  
|Image.SmallerBrush|CTRL + - (eksi)|Her yönde bir piksel tarafından fırça boyutunu azaltır. Fırça boyutunu yeniden genişletmek için bu tabloda Image.LargerBrush bakın.|  
|Image.TextTool|CTRL + T|Açılır [metin aracı iletişim kutusu](../windows/text-tool-dialog-box-image-editor-for-icons.md).|  
|Image.UseSelectionAsBrush|CTRL + U|Geçerli seçim fırça olarak kullanarak çizer.|  
|Image.ZoomIn|CTRL + SHIFT +. (nokta)<br /><br /> - veya -<br /><br /> CTRL + YUKARI OK|Geçerli Görünüm için büyütme artırır.|  
|Image.ZoomOut|CTRL +, (virgül)<br /><br /> - veya -<br /><br /> CTRL + AŞAĞI OK|Geçerli görünümün büyütme azaltır.|  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)

