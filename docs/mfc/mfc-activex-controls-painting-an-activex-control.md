---
title: 'MFC ActiveX Denetimleri: ActiveX Denetimini Boyama'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], painting
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
ms.openlocfilehash: a01a66402471b295a6e57af8af265c50685b4a1f
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618217"
---
# <a name="mfc-activex-controls-painting-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetimini Boyama

Bu makalede, ActiveX denetim boyama süreci ve işlemi iyileştirmek için boyama kodu nasıl değiştirileceği açıklanır. (Denetimlerin en iyi duruma getirilmesi için bkz. [Denetim çizimini iyileştirme](optimizing-control-drawing.md) , denetimleri önceden seçilmiş GDI nesnelerini tek tek geri yükleme. Tüm denetimler çizildikten sonra kapsayıcı özgün nesneleri otomatik olarak geri yükleyebilir.)

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Bu makaledeki örnekler, varsayılan ayarlarla MFC ActiveX denetimi Sihirbazı tarafından oluşturulan bir denetimdir. MFC ActiveX Denetim Sihirbazı 'Nı kullanarak bir iskelet denetim uygulaması oluşturma hakkında daha fazla bilgi için [MFC ActiveX Denetim Sihirbazı](reference/mfc-activex-control-wizard.md)makalesine bakın.

Aşağıdaki konular ele alınmıştır:

- [Bir denetimi boyama için genel işlem ve ActiveX Denetim Sihirbazı tarafından boyama desteği için oluşturulan kod](#_core_the_painting_process_of_an_activex_control)

- [Boyama işlemini iyileştirme](#_core_optimizing_your_paint_code)

- [Meta dosyaları kullanarak denetiminizi boyama](#_core_painting_your_control_using_metafiles)

## <a name="the-painting-process-of-an-activex-control"></a><a name="_core_the_painting_process_of_an_activex_control"></a>ActiveX denetiminin boyama Işlemi

ActiveX denetimleri başlangıçta görüntülenirken veya yeniden çizildiklerinde, MFC kullanılarak geliştirilen diğer uygulamalarla benzer bir boyama sürecini izleyerek önemli bir ayrım vardır: ActiveX denetimleri etkin veya etkin olmayan bir durumda olabilir.

Etkin denetim bir ActiveX denetim kapsayıcısında bir alt pencere tarafından temsil edilir. Diğer pencereler gibi, WM_PAINT bir ileti alındığında kendisini boyamaktan sorumludur. Denetimin temel sınıfı, [Coelcontrol](reference/colecontrol-class.md), bu iletiyi `OnPaint` işlevinde işler. Bu varsayılan uygulama `OnDraw` denetiminizin işlevini çağırır.

Etkin olmayan bir denetim farklı şekilde boyanmıştır. Denetim etkin olmadığında, penceresi görünmez ya da yok olur, bu nedenle bir Paint iletisi alamaz. Bunun yerine, Denetim kapsayıcısı doğrudan `OnDraw` denetimin işlevini çağırır. Bu, `OnPaint` üye işlevin hiçbir şekilde çağrılmayacağı etkin bir denetimin boyama sürecinden farklıdır.

Önceki paragraflarda açıklandığı gibi, ActiveX denetiminin nasıl güncelleştirildiği, denetimin durumuna bağlıdır. Ancak Framework `OnDraw` her iki durumda da üye işlevini çağırdığı için, bu üye işlevindeki boyama kodunuzun çoğunluğunu eklersiniz.

`OnDraw`Üye işlevi denetim boyamayı işler. Bir denetim etkin olmadığında Denetim kapsayıcısı, Denetim `OnDraw` kapsayıcısının cihaz bağlamını ve denetimin kapladığı dikdörtgen alanın koordinatlarını geçirerek çağırır.

Çerçeve tarafından üye işlevine geçirilen dikdörtgen, `OnDraw` denetimin kapladığı alanını içerir. Denetim etkinse, sol üst köşe (0, 0) ve geçirilen cihaz bağlamı, denetimi içeren alt pencere içindir. Denetim etkin değilse, sol üst koordinat gerekli değildir (0, 0) ve geçirilen cihaz bağlamı, denetimi içeren denetim kapsayıcısı içindir.

> [!NOTE]
> Yaptığınız değişikliklerin `OnDraw` dikdörtgenin sol üst noktasına eşit olması önemlidir (0, 0) ve yalnızca öğesine geçirilen dikdörtgenin içinde çizim yapabilirsiniz `OnDraw` . Dikdörtgenin alanından daha fazla çizim yaparsanız beklenmedik sonuçlar oluşabilir.

Denetim uygulama dosyasında MFC ActiveX denetimi Sihirbazı tarafından belirtilen varsayılan uygulama (. CPP) aşağıda gösterildiği gibi, dikdörtgeni beyaz fırçayla boyar ve elipsi geçerli arka plan rengiyle doldurur.

[!code-cpp[NVC_MFC_AxUI#1](codesnippet/cpp/mfc-activex-controls-painting-an-activex-control_1.cpp)]

> [!NOTE]
> Bir denetimi boyadığınızda, işleve *PDC* parametresi olarak geçirilen cihaz bağlamının durumu hakkında varsayımınızın olması gerekmez `OnDraw` . Bazen cihaz bağlamı kapsayıcı uygulama tarafından sağlanır ve varsayılan duruma başlatılmayabilir. Özellikle, çizim kodunuzun bağlı olduğu kalemleri, fırçaları, renkleri, yazı tiplerini ve diğer kaynakları açık bir şekilde seçin.

## <a name="optimizing-your-paint-code"></a><a name="_core_optimizing_your_paint_code"></a>Boyama kodunuzu iyileştirme

Denetim, kendisini başarıyla boyadıktan sonra, bir sonraki adım işlevi en iyileştirmek için kullanılır `OnDraw` .

Varsayılan ActiveX denetimi boyama uygulamasının tüm denetim alanını boyar. Bu basit denetimler için yeterlidir, ancak çoğu durumda, yalnızca güncelleştirme gereken bölümü, tüm denetim yerine yeniden boyandıysa, denetimin yeniden boyanması daha hızlı olur.

`OnDraw`İşlevi, yeniden çizilmesi gereken denetimin dikdörtgen alanını *rcgeçersiz*geçirerek kolay bir iyileştirme yöntemi sağlar. Boyama sürecini hızlandırmak için genellikle tüm denetim alanından daha küçük olan bu alanı kullanın.

## <a name="painting-your-control-using-metafiles"></a><a name="_core_painting_your_control_using_metafiles"></a>Meta dosyaları kullanarak denetiminizi boyama

Çoğu durumda, işlev için *PDC* parametresi `OnDraw` bir ekran CIHAZ bağlamına (DC) işaret eder. Ancak, denetimin görüntülerini yazdırırken veya baskı önizleme oturumu sırasında, işleme için alınan DC, "Metafile DC" adlı özel bir türdür. Kendisine gönderilen istekleri hemen işleyen bir ekran DC 'nin aksine, bir meta dosyası DC, istekleri daha sonraki bir zamanda kayıttan yürütülmesi için depolar. Bazı kapsayıcı uygulamaları, tasarım modundayken bir meta dosyası DC kullanarak denetim görüntüsünü işlemeyi da seçebilir.

Meta dosya çizim istekleri iki arabirim işlevi aracılığıyla kapsayıcı tarafından yapılabilir: `IViewObject::Draw` (Bu işlev, meta dosya olmayan çizim için de çağrılabilir) ve `IDataObject::GetData` . Bir meta dosya DC 'si parametrelerden biri olarak geçirildiğinde, MFC çerçevesi [Copacontrol:: OnDrawMetafile](reference/colecontrol-class.md#ondrawmetafile)öğesine bir çağrı yapar. Bu bir sanal üye işlevi olduğundan, özel bir işlem yapmak için denetim sınıfındaki bu işlevi geçersiz kılın. Varsayılan davranış çağırır `COleControl::OnDraw` .

Denetimin hem ekranda hem de meta dosyası cihaz bağlamlarında çizilip çizilmeyeceğini doğrulamak için, yalnızca bir ekranda ve bir meta dosyası DC 'de desteklenen üye işlevlerini kullanmanız gerekir. Koordinat sisteminin piksel cinsinden ölçüldüğüne dikkat edin.

Varsayılan uygulama, `OnDrawMetafile` denetimin işlevini çağırdığı için `OnDraw` , geçersiz kılmadığınız müddetçe yalnızca bir meta dosyası ve ekran cihaz bağlamı için uygun olan üye işlevlerini kullanın `OnDrawMetafile` . Aşağıda, `CDC` hem meta dosyası hem de ekran cihaz bağlamında kullanılabilen üye işlevlerinin alt kümesi listelenmektedir. Bu işlevler hakkında daha fazla bilgi için bkz. *MFC başvurusunda* [CDC](reference/cdc-class.md) sınıfı.

|Arc|BibBlt|Chord|
|---------|------------|-----------|
|`Ellipse`|`Escape`|`ExcludeClipRect`|
|`ExtTextOut`|`FloodFill`|`IntersectClipRect`|
|`LineTo`|`MoveTo`|`OffsetClipRgn`|
|`OffsetViewportOrg`|`OffsetWindowOrg`|`PatBlt`|
|`Pie`|`Polygon`|`Polyline`|
|`PolyPolygon`|`RealizePalette`|`RestoreDC`|
|`RoundRect`|`SaveDC`|`ScaleViewportExt`|
|`ScaleWindowExt`|`SelectClipRgn`|`SelectObject`|
|`SelectPalette`|`SetBkColor`|`SetBkMode`|
|`SetMapMode`|`SetMapperFlags`|`SetPixel`|
|`SetPolyFillMode`|`SetROP2`|`SetStretchBltMode`|
|`SetTextColor`|`SetTextJustification`|`SetViewportExt`|
|`SetViewportOrg`|`SetWindowExt`|`SetWindowORg`|
|`StretchBlt`|`TextOut`||

`CDC`Üye işlevlerine ek olarak, bir meta dosyası DC 'de uyumlu olan birkaç başka işlev de vardır. Bunlar şunlardır: createbrüsdolaylı, createdibpatternbrush ve CreatePatternBrush ' nin [CPalette:: Animatepalet](reference/cpalette-class.md#animatepalette), [CFont:: CreateFontIndirect](reference/cfont-class.md#createfontindirect)ve üç üye işlevi `CBrush` . [CreateBrushIndirect](reference/cbrush-class.md#createbrushindirect) [CreateDIBPatternBrush](reference/cbrush-class.md#createdibpatternbrush) [CreatePatternBrush](reference/cbrush-class.md#createpatternbrush)

Bir meta dosyasında kayıtlı olmayan işlevler şunlardır: [DrawFocusRect](reference/cdc-class.md#drawfocusrect), [DrawIcon](reference/cdc-class.md#drawicon), [DrawText](reference/cdc-class.md#drawtext), [ExcludeUpdateRgn](reference/cdc-class.md#excludeupdatergn), [FillRect](reference/cdc-class.md#fillrect), [FrameRect](reference/cdc-class.md#framerect), [gristring](reference/cdc-class.md#graystring), [evirtrect](reference/cdc-class.md#invertrect), [ScrollDC](reference/cdc-class.md#scrolldc)ve [TabbedTextOut](reference/cdc-class.md#tabbedtextout). Bir meta dosyası DC 'si gerçekten bir cihazla ilişkili olmadığından, SetDIBits, GetDIBits ve Createdibit bir meta dosya DC ile birlikte kullanamazsınız. Hedef olarak bir meta dosya DC 'si ile SetDIBitsToDevice ve lıageler kullanabilirsiniz. [Createuyumluluk Bledc](reference/cdc-class.md#createcompatibledc), [CreateCompatibleBitmap](reference/cbitmap-class.md#createcompatiblebitmap)ve [CREATEDISCARDABLEBITMAP](reference/cbitmap-class.md#creatediscardablebitmap) , bir meta dosyası DC ile anlamlı değildir.

Bir meta dosyası DC kullanırken göz önünde bulundurmanız gereken başka bir nokta de koordinat sisteminin piksel cinsinden ölçülmeyebilir. Bu nedenle, tüm çizim kodunuzun `OnDraw` *rcsınır* parametresinde geçirilen dikdörtgene sığacak şekilde ayarlanması gerekir. Bu, *Rclimitleri* denetim penceresinin boyutunu temsil ettiğinden denetimin dışında yanlışlıkla boyamayı önler.

Denetim için meta dosya oluşturmayı uyguladıktan sonra, meta dosyasını sınamak için test kapsayıcısını kullanın. Test kapsayıcısına erişme hakkında bilgi için bkz. test [kapsayıcı Ile özellikleri ve olayları test etme](testing-properties-and-events-with-test-container.md) .

#### <a name="to-test-the-controls-metafile-using-test-container"></a>Test kapsayıcısını kullanarak denetimin meta dosyasını test etmek için

1. Test kapsayıcısının **düzenleme** menüsünde **Yeni Denetim Ekle**' ye tıklayın.

1. **Yeni Denetim Ekle** kutusunda, denetimi seçin ve **Tamam**' ı tıklatın.

   Denetim test kapsayıcısında görüntülenir.

1. **Denetim** menüsünde **meta dosya çiz**' e tıklayın.

   Meta dosyasının görüntülendiği ayrı bir pencere görüntülenir. Ölçeklendirmenin denetimin meta dosyasını nasıl etkilediğini görmek için bu pencerenin boyutunu değiştirebilirsiniz. Bu pencereyi dilediğiniz zaman kapatabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
