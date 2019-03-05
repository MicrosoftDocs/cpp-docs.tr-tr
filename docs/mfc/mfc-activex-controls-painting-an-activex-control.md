---
title: 'MFC ActiveX denetimleri: ActiveX denetimini boyama'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], painting
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
ms.openlocfilehash: b90aa331c289caf827785af2eeba037e70f686ab
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281936"
---
# <a name="mfc-activex-controls-painting-an-activex-control"></a>MFC ActiveX denetimleri: ActiveX denetimini boyama

Bu makalede, ActiveX denetimini boyama işleminin ve süreçlerini optimize etmek için Boya kod nasıl alter açıklanmaktadır. (Bkz [denetim çizim en iyi duruma getirme](../mfc/optimizing-control-drawing.md) teknikleri üzerinde çizim denetimleri ayrı ayrı zorunluluğunu ortadan kaldırarak en iyi duruma getirme, daha önce seçilen GDI nesneleri geri yüklemek için. Tüm denetimleri çizilmiş sonra kapsayıcı otomatik olarak özgün nesneleri geri yükleyebilirsiniz.)

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

Bu makaledeki örneklerde, varsayılan ayarlarla MFC ActiveX Denetim Sihirbazı tarafından oluşturulan denetim arasındadır. MFC ActiveX Denetim Sihirbazı'nı kullanarak bir çatı denetim uygulaması oluşturma hakkında daha fazla bilgi için bkz [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md).

Aşağıdaki konular ele alınmaktadır:

- [Denetim ve bir boyama desteklemek için ActiveX Denetim Sihirbazı tarafından oluşturulan kod boyama için genel işlem](#_core_the_painting_process_of_an_activex_control)

- [Boyama işleminin en iyi duruma getirme](#_core_optimizing_your_paint_code)

- [Nasıl meta dosyaları kullanarak denetim boyama](#_core_painting_your_control_using_metafiles)

##  <a name="_core_the_painting_process_of_an_activex_control"></a> Bir ActiveX denetimini boyama işlemi

ActiveX denetimleri, ilk olarak görüntülenen veya yeniden düzenlenmiş, bunlar, MFC ile önemli bir ayrım kullanılarak geliştirilen diğer uygulamalara yönelik benzer bir boyama işlem izleyin: ActiveX denetimleri, etkin veya etkin olmayan bir durumda olabilir.

Etkin bir denetim, bir ActiveX denetim kapsayıcısındaki bir alt pencere tarafından temsil edilir. Diğer windows gibi bir WM_PAINT iletisini aldığınızda kendisini boyama için sorumludur. Denetimin temel sınıf [COleControl](../mfc/reference/colecontrol-class.md), bu iletiyi işleyen kendi `OnPaint` işlevi. Bu varsayılan uygulama çağrıları `OnDraw` denetiminizin işlevi.

Etkin olmayan bir denetim farklı boyanır. Denetim etkin olduğunda, bir boyama iletisinin alabileceği değil, pencerenin görünmez ya da yok, olduğundan. Bunun yerine, Denetim kapsayıcısı doğrudan çağıran `OnDraw` işlevi denetimi. Bu etkin bir denetim boyama işlem farklıdır `OnPaint` üye işlev hiçbir zaman çağrılır.

Önceki paragrafta açıklandığı gibi bir ActiveX denetimini nasıl güncelleştirileceğini denetimin durumuna bağlıdır. Ancak, framework çağırdığı `OnDraw` üye işlevi her iki durumda da, bu üye işlevi boyama kodunuzu çoğunu ekleyin.

`OnDraw` Üye işlevi denetim boyama işler. Bir denetimi devre dışı olduğunda denetim kapsayıcısı çağırır `OnDraw`, Denetim kapsayıcısı cihaz bağlamı ve denetim tarafından dolu dikdörtgen alan koordinatlarını geçirme.

Dikdörtgen geçirilen için framework tarafından `OnDraw` üye işlevi denetim tarafından kapladığı alanı içerir. Denetimin etkin olursa, sol üst köşesinin olduğu (0, 0) ve geçirilen cihaz bağlamı denetimi içeren bir alt pencere için. Denetimin etkin değilse, sol üst koordinat olmak zorunda değildir (0, 0) ve geçirilen cihaz bağlamı denetimi içeren denetimi için kapsayıcıdır.

> [!NOTE]
>  Önemli olduğu, değişikliklerinizi `OnDraw` dikdörtgenin üst sol noktası eşit olan bağlı olmayan (0, 0) ve yalnızca içinde dikdörtgen çizmek için geçirilen `OnDraw`. Dikdörtgen alan çizerseniz beklenmedik sonuçlar oluşabilir.

MFC ActiveX Denetim Sihirbazı'nı Denetim uygulama dosyasında tarafından sağlanan varsayılan uygulama (. CPP) gösterilen aşağıda beyaz bir fırça dikdörtgen boyar ve üç nokta geçerli arka plan rengi ile doldurur.

[!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/cpp/mfc-activex-controls-painting-an-activex-control_1.cpp)]

> [!NOTE]
>  Bir denetim boyama, olarak geçirilen cihaz bağlamı durumuyla ilgili varsayımlar yapmamalısınız *pdc* parametresi `OnDraw` işlevi. Bazen bir cihaz bağlamı kapsayıcı uygulama tarafından sağlanan ve mutlaka varsayılan duruma başlatılmayacak. Özellikle, kalemler, Fırçalar, renkleri, yazı tipleri ve çizim kodunuz bağımlı diğer kaynaklar açıkça seçin.

##  <a name="_core_optimizing_your_paint_code"></a> Boyama kodunuzu iyileştirme

Denetim başarıyla kendisini boyama olan sonra iyileştirmek için sonraki adım olan `OnDraw` işlevi.

ActiveX denetimini boyama varsayılan uygulamasını tüm denetim alanı boyar. Bu basit denetimler için yeterlidir ancak güncelleştirilmesi gereken bölümü, tüm denetim yerine yeniden çizilmesini yalnızca çoğu durumda denetimi yeniden çizerken daha hızlı olacaktır.

`OnDraw` İşlevi geçirerek iyileştirme kolay bir yöntemini sağlar *rcInvalid*, yeniden gereken denetimin dikdörtgen alan. Bu alan boyama sürecini hızlandırmak için tüm denetim alanı genellikle daha küçük kullanın.

##  <a name="_core_painting_your_control_using_metafiles"></a> Meta dosyaları kullanarak denetim boyama

Çoğu durumda *pdc* parametresi `OnDraw` işlevi, bir ekran cihaz bağlamı (DC) işaret eder. Ancak, görüntüleri denetimi ya da yazdırma önizleme oturumu sırasında yazdırırken işleme için alınan DC bir "meta DC" adlı özel bir türü olur. Hemen buna gönderilen istekleri işleyen bir ekran DC, daha sonraki bir zamanda tekrarlanmasını istekleri bir DC meta depolar. Bazı kapsayıcı uygulamaları, Tasarım modunda DC bir meta dosyasını kullanan denetimi görüntüsünü işlemek de tercih edebilirsiniz.

İstekleri çizim meta dosyası, iki arabirim işlevleri aracılığıyla kapsayıcı tarafından yapılabilir: `IViewObject::Draw` (Bu işlev, aynı zamanda olmayan-çizim meta dosyası için çağrılabilir) ve `IDataObject::GetData`. DC parametrelerinden biri geçirilir meta dosyası, MFC çerçevesi çağrıda [COleControl::OnDrawMetafile](../mfc/reference/colecontrol-class.md#ondrawmetafile). Bu, bir sanal üye işlev olduğu için bu işlevi herhangi bir özel işlem yapmak için Denetim sınıfında geçersiz kılar. Varsayılan davranış çağrıları `COleControl::OnDraw`.

Denetimin ekranda hem meta dosyası cihaz bağlamlarında kurulabilir emin olmak için bir ekran ve bir meta dosyası DC desteklenen üye işlevleri kullanmanız gerekir. Koordinat sistemi piksel cinsinden mi ölçüleceğini değil olduğunu unutmayın.

Çünkü varsayılan uygulamasını `OnDrawMetafile` denetimin çağırır `OnDraw` işlevi, geçersiz kılmanız sürece, bir meta dosyası ve bir ekran cihaz bağlamı için uygun olan üye işlevlerini `OnDrawMetafile`. Aşağıdaki alt kümesini listeler `CDC` meta dosyası ve bir ekran cihaz bağlamı kullanılabilir üye işlevleri. Bu işlevler hakkında daha fazla bilgi için bkz. [CDC](../mfc/reference/cdc-class.md) içinde *MFC başvurusu*.

|Yay|BibBlt|Tel|
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

Ek olarak `CDC` üye işlevleri, meta dosyası DC uyumlu olan diğer birçok işlev vardır. Bunlar [CPalette::AnimatePalette](../mfc/reference/cpalette-class.md#animatepalette), [CFont::CreateFontIndirect](../mfc/reference/cfont-class.md#createfontindirect), üç üye işlevleri `CBrush`: [CreateBrushIndirect](../mfc/reference/cbrush-class.md#createbrushindirect), [CreateDIBPatternBrush](../mfc/reference/cbrush-class.md#createdibpatternbrush), ve [CreatePatternBrush](../mfc/reference/cbrush-class.md#createpatternbrush).

Bir meta dosyası içinde kaydedilen değil işlevler şunlardır: [DrawFocusRect](../mfc/reference/cdc-class.md#drawfocusrect), [DrawIcon](../mfc/reference/cdc-class.md#drawicon), [DrawText](../mfc/reference/cdc-class.md#drawtext), [ExcludeUpdateRgn](../mfc/reference/cdc-class.md#excludeupdatergn), [FillRect](../mfc/reference/cdc-class.md#fillrect), [FrameRect ](../mfc/reference/cdc-class.md#framerect), [GrayString](../mfc/reference/cdc-class.md#graystring), [InvertRect](../mfc/reference/cdc-class.md#invertrect), [ScrollDC](../mfc/reference/cdc-class.md#scrolldc), ve [TabbedTextOut](../mfc/reference/cdc-class.md#tabbedtextout). Bir meta dosyası DC aslında bir cihazla ilişkili olmadığı için bir meta dosyası DC SetDIBits GetDIBits ve CreateDIBitmap kullanamazsınız. Hedef olarak bir meta dosyası DC SetDIBitsToDevice ve StretchDIBits kullanabilirsiniz. [CreateCompatibleDC](../mfc/reference/cdc-class.md#createcompatibledc), [CreateCompatibleBitmap](../mfc/reference/cbitmap-class.md#createcompatiblebitmap), ve [CreateDiscardableBitmap](../mfc/reference/cbitmap-class.md#creatediscardablebitmap) bir meta dosyası DC anlamlı değildir.

Bir meta dosyası DC kullanırken dikkate alınması gereken başka bir koordinat sistemini piksel cinsinden mi ölçüleceğini değil, noktasıdır. Bu nedenle, tüm çizim kodunuz dikdörtgenine için belirlenebilir geçirilen `OnDraw` içinde *rcBounds* parametresi. Bu denetimin dışında kalan yanlışlıkla boyama çünkü engeller *rcBounds* denetimin pencere boyutunu temsil eder.

Denetimin meta dosyası işleme uyguladıysanız sonra Test kapsayıcı meta dosyası test etmek için kullanın. Bkz: [Test kapsayıcısı ile test etme özellikleri ve olayları](../mfc/testing-properties-and-events-with-test-container.md) test kapsayıcı erişim hakkında daha fazla bilgi için.

#### <a name="to-test-the-controls-metafile-using-test-container"></a>Denetimin meta dosyası test kapsayıcısı kullanarak test etmek için

1. Test kapsayıcının üzerinde **Düzenle** menüsünde tıklatın **yeni denetimi Ekle**.

1. İçinde **yeni denetimi Ekle** kutusunda, istediğiniz denetimi seçin ve tıklayın **Tamam**.

   Denetim Test kapsayıcısında görünür.

1. Üzerinde **denetimi** menüsünde tıklatın **çizmek meta**.

   Meta dosyası görüntülendiği ayrı bir pencerede görüntülenir. Ölçeklendirme denetimin meta nasıl etkilediğini görmek için bu pencere boyutunu değiştirebilirsiniz. Herhangi bir zamanda bu pencereyi kapatabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)
