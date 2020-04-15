---
title: 'MFC ActiveX Denetimleri: ActiveX Denetimini Boyama'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], painting
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
ms.openlocfilehash: fd98af90e86b6b98a856e633e50c5bf266cc466a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364577"
---
# <a name="mfc-activex-controls-painting-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetimini Boyama

Bu makalede ActiveX denetim boyama işlemi ve işlemi optimize etmek için boya kodunu nasıl değiştirebileceğiniz açıklanmaktadır. (Denetimlerin önceden seçili GDI nesnelerini tek tek geri yüklemesine gerek kalmadan çizimi en iyi duruma getirme teknikleri için [Denetim Çizimini Optimize](../mfc/optimizing-control-drawing.md) Etme konusuna bakın. Tüm denetimler çizildikten sonra, kapsayıcı orijinal nesneleri otomatik olarak geri yükleyebilir.)

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

Bu makaledeki örnekler, Varsayılan ayarları olan MFC ActiveX Denetim Sihirbazı tarafından oluşturulan bir denetimden örneklerdir. MFC ActiveX Denetim Sihirbazı'nı kullanarak bir iskelet kontrol uygulaması oluşturma hakkında daha fazla bilgi için [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md)makalesine bakın.

Aşağıdaki konular ele alınmıştır:

- [Bir denetimi boyama için genel işlem ve ActiveX Denetim Sihirbazı tarafından boyamayı desteklemek için oluşturulan kod](#_core_the_painting_process_of_an_activex_control)

- [Boyama işlemi optimize etme](#_core_optimizing_your_paint_code)

- [Metadosyaları kullanarak denetiminizi boyama](#_core_painting_your_control_using_metafiles)

## <a name="the-painting-process-of-an-activex-control"></a><a name="_core_the_painting_process_of_an_activex_control"></a>ActiveX Kontrolünün Boyama İşlemi

ActiveX denetimleri başlangıçta görüntülendiğinde veya yeniden çizildiğinde, MFC kullanılarak geliştirilen diğer uygulamalara benzer bir boyama işlemini önemli bir ayrımla izlerler: ActiveX denetimleri etkin veya etkin olmayan bir durumda olabilir.

Etkin denetim, activex denetim kapsayıcısında bir alt pencere tarafından temsil edilir. Diğer pencereler gibi, WM_PAINT bir ileti aldığında kendisini boyama sorumludur. Denetimin taban sınıfı, [COleControl](../mfc/reference/colecontrol-class.md), `OnPaint` işlevinde bu iletiyi işler. Bu varsayılan uygulama `OnDraw` denetiminizin işlevini çağırır.

Etkin olmayan bir denetim farklı şekilde boyanmıştır. Denetim etkin olmadığında, penceresi görünmez veya yok olur, bu nedenle bir boya iletisi alamaz. Bunun yerine, denetim kapsayıcısı doğrudan denetim `OnDraw` işlevini çağırır. Bu, `OnPaint` etkin bir denetimin boyama işleminden farklıdır, çünkü üye işlev hiçbir zaman çağrılmaz.

Önceki paragraflarda tartışıldığı gibi, ActiveX denetiminin nasıl güncelleştirilen denetimin durumuna bağlıdır. Ancak, çerçeve her `OnDraw` iki durumda da üye işlevi aradığından, boyama kodunuzuzun çoğunluğunu bu üye işlevine eklersiniz.

`OnDraw` Üye işlev denetim boyama işler. Bir denetim etkin olmadığında, kontrol `OnDraw`kapsayıcısı, kontrol konteynerinin cihaz bağlamını ve denetim tarafından işgal edilen dikdörtgen alanın koordinatlarını geçerek çağırır.

Çerçeve tarafından `OnDraw` üye işlevine geçirilen dikdörtgen, denetimin işgal ettiği alanı içerir. Denetim etkinse, sol üst köşe (0, 0) ve geçirilen aygıt bağlamı denetimi içeren alt pencere içindir. Denetim etkin değilse, sol üst koordinat mutlaka (0, 0) değildir ve geçirilen aygıt bağlamı denetimi içeren denetim kapsayıcısı içindir.

> [!NOTE]
> Değişikliklerinizin `OnDraw` dikdörtgenin sol üst noktasının (0, 0) eşit olmasına bağlı olmaması ve yalnızca dikdörtgenin içini çizmeniz `OnDraw`önemlidir. Dikdörtgenin alanının ötesine çizerseniz beklenmeyen sonuçlar oluşabilir.

Kontrol uygulama dosyasında MFC ActiveX Denetim Sihirbazı tarafından sağlanan varsayılan uygulama (. CPP), aşağıda gösterildiği, beyaz bir fırça ile dikdörtgen boyalar ve geçerli arka plan rengi ile elips doldurur.

[!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/cpp/mfc-activex-controls-painting-an-activex-control_1.cpp)]

> [!NOTE]
> Denetim yapılırken, `OnDraw` işleve *pdc* parametresi olarak geçirilen aygıt bağlamının durumu hakkında varsayımlarda bulunmamalısınız. Bazen aygıt bağlamı kapsayıcı uygulaması tarafından sağlanır ve varsayılan duruma mutlaka başharfverilmeyecektir. Özellikle, çizim kodunuzuzun bağlı olduğu kalemleri, fırçaları, renkleri, yazı tiplerini ve diğer kaynakları açıkça seçin.

## <a name="optimizing-your-paint-code"></a><a name="_core_optimizing_your_paint_code"></a>Boya Kodunuzu Optimize Etme

Denetim başarılı bir şekilde kendini boyama sonra, bir `OnDraw` sonraki adım işlevi optimize etmektir.

ActiveX denetim boyamasının varsayılan uygulaması tüm denetim alanını boyar. Bu basit denetimler için yeterlidir, ancak çoğu durumda tüm denetim yerine yalnızca güncelleştirilmesi gereken kısmı yeniden boyanmış olsaydı denetimi yeniden boyama daha hızlı olacaktır.

İşlev `OnDraw` *rcInvalid*geçirerek optimizasyon kolay bir yöntem sağlar , yeniden çizilmesi gereken denetimin dikdörtgen alan. Boyama işlemini hızlandırmak için genellikle tüm kontrol alanından daha küçük olan bu alanı kullanın.

## <a name="painting-your-control-using-metafiles"></a><a name="_core_painting_your_control_using_metafiles"></a>Metafiles kullanarak Denetimboyama

Çoğu durumda işlevin `OnDraw` *pdc* parametresi bir ekran aygıtı bağlamını (DC) işaret eder. Ancak, denetimin görüntülerini yazdırırken veya yazdırma önizleme oturumu sırasında, işleme için alınan DC "metafile DC" adı verilen özel bir türdür. Gönderilen istekleri hemen işleyen bir ekran DC'nin aksine, bir metadosya DC daha sonra oynatılmak için isteklerde bulunur. Bazı kapsayıcı uygulamaları, tasarım modundayken bir metadosya DC kullanarak denetim görüntüsünü oluşturmayı da seçebilir.

Metadosya çizim istekleri iki arabirim işlevleri aracılığıyla `IViewObject::Draw` kapsayıcı tarafından yapılabilir: (bu işlev de `IDataObject::GetData`olmayan metadosya çizim için çağrılabilir) ve . Bir metadosya DC parametrelerden biri olarak geçirildiğinde, MFC çerçevesi COleControl için bir çağrı [yapar::OnDrawMetafile.](../mfc/reference/colecontrol-class.md#ondrawmetafile) Bu sanal bir üye işlev olduğundan, herhangi bir özel işleme yapmak için denetim sınıfında bu işlevi geçersiz kılın. Varsayılan davranış `COleControl::OnDraw`çağırır.

Denetimin hem ekran hem de metadosya aygıt bağlamlarında çizilediğinden emin olmak için, yalnızca hem ekranda hem de metadosya DC'de desteklenen üye işlevleri kullanmanız gerekir. Koordinat sisteminin piksel cinsinden ölçülemeyeceğini unutmayın.

Denetimin `OnDrawMetafile` `OnDraw` işlevini çağıran varsayılan uygulama olduğundan, geçersiz kılmadığınız `OnDrawMetafile`sürece yalnızca hem metadosya hem de ekran aygıtı bağlamı için uygun olan üye işlevleri kullanın. Aşağıda, hem metadosyahem de ekran aygıtı bağlamında kullanılabilecek `CDC` üye işlevlerin alt kümesi listelenir. Bu işlevler hakkında daha fazla bilgi için *MFC Başvurusu'ndaki* [CDC](../mfc/reference/cdc-class.md) sınıfına bakın.

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

Üye işlevlere `CDC` ek olarak, bir metadosya DC uyumlu birkaç diğer işlevleri vardır. Bu [CPalette şunlardır::AnimatePalette](../mfc/reference/cpalette-class.md#animatepalette), [CFont::CreateFontIndirect](../mfc/reference/cfont-class.md#createfontindirect) `CBrush`, ve üç üye işlevleri: [CreateBrushIndirect](../mfc/reference/cbrush-class.md#createbrushindirect), [CreateDIBPatternBrush](../mfc/reference/cbrush-class.md#createdibpatternbrush), ve [CreatePatternBrush](../mfc/reference/cbrush-class.md#createpatternbrush).

Metafilede kaydedilmez fonksiyonlar şunlardır: [DrawFocusRect](../mfc/reference/cdc-class.md#drawfocusrect), [DrawIcon](../mfc/reference/cdc-class.md#drawicon), [DrawText](../mfc/reference/cdc-class.md#drawtext), [ExcludeUpdateRgn](../mfc/reference/cdc-class.md#excludeupdatergn), [FillRect](../mfc/reference/cdc-class.md#fillrect), [FrameRect](../mfc/reference/cdc-class.md#framerect), [GrayString](../mfc/reference/cdc-class.md#graystring), [InvertRect](../mfc/reference/cdc-class.md#invertrect), [ScrollDC](../mfc/reference/cdc-class.md#scrolldc), ve [TabbedTextOut](../mfc/reference/cdc-class.md#tabbedtextout). Bir metadosya DC aslında bir aygıtla ilişkili olmadığından, bir metadosya DC ile SetDIBits, GetDIBits ve CreateDIBitmap kullanamazsınız. Hedef olarak bir metadosya DC ile SetDIBitsToDevice ve StretchDIBits kullanabilirsiniz. [CreateCompatibleDC](../mfc/reference/cdc-class.md#createcompatibledc), [CreateCompatibleBitmap](../mfc/reference/cbitmap-class.md#createcompatiblebitmap)ve [CreateDiscardableBitmap](../mfc/reference/cbitmap-class.md#creatediscardablebitmap) metadosya DC ile anlamlı değildir.

Bir metadosya DC kullanırken göz önünde bulundurulması gereken bir diğer nokta koordinat sistemi piksel cinsinden ölçülmeyebilir. Bu nedenle, tüm çizim kodunuz *rcBounds* parametresine geçirilen `OnDraw` dikdörtgenin sığacak şekilde ayarlanmalıdır. *RcBounds* denetim penceresinin boyutunu temsil eder, çünkü bu denetim dışında yanlışlıkla boyama önler.

Denetim için metadosya oluşturmayı uyguladıktan sonra, metadosyayı sınamak için Test Kapsayıcısı'nı kullanın. Test kapsayıcısına nasıl erişireceksiniz hakkında bilgi almak için [Test Kapsayıcısı ile Test Özellikleri ve Olayları'na](../mfc/testing-properties-and-events-with-test-container.md) bakın.

#### <a name="to-test-the-controls-metafile-using-test-container"></a>Test Kapsayıcısı kullanarak denetimin metadosyasını test etmek için

1. Test Kapsayıcısı'nın **Edit** menüsünde **Yeni Denetim Ekle'yi**tıklatın.

1. Yeni **Denetim Ekle** kutusunda denetimi seçin ve **Tamam'ı**tıklatın.

   Denetim Test kapsayıcısında görünür.

1. Denetimi **denetle** menüsünde **Metadosyayı Çiz'i**tıklatın.

   Metadosyanın görüntülendiği ayrı bir pencere görüntülenir. Ölçeklemenin denetimin meta dosyasını nasıl etkilediğini görmek için bu pencerenin boyutunu değiştirebilirsiniz. Bu pencereyi istediğiniz zaman kapatabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)
