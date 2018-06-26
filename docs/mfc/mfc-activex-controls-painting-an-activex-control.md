---
title: 'MFC ActiveX denetimleri: ActiveX denetimini boyama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], painting
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de12a21c4b411f3cd1fe25d7d6badd8d26318351
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929818"
---
# <a name="mfc-activex-controls-painting-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetimini Boyama
Bu makalede, ActiveX denetimini boyama işleminin ve boyama kod işlemi iyileştirmek için nasıl alter açıklanır. (Bkz [denetim çizim en iyi duruma getirme](../mfc/optimizing-control-drawing.md) teknikleri denetimleri tek tek zorunluluğunu ortadan kaldırarak çizim iyileştirmek nasıl daha önce seçilen GDI nesneleri geri yüklemek için. Tüm denetimler çizilmiş sonra kapsayıcı otomatik olarak özgün nesneleri geri yükleyebilirsiniz.)  
  
 Bu makaledeki örneklerde varsayılan ayarlarla MFC ActiveX Denetim Sihirbazı tarafından oluşturulan bir denetim arasındadır. MFC ActiveX Denetim Sihirbazı'nı kullanarak bir iskelet denetim uygulaması oluşturma hakkında daha fazla bilgi için bkz: [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md).  
  
 Aşağıdaki konular ele alınmaktadır:  
  
-   [Boyama için genel işlem bir denetim ve kodu ActiveX denetimini boyama desteklemek için sihirbaz tarafından oluşturulan](#_core_the_painting_process_of_an_activex_control)  
  
-   [Boyama işleminin en iyi duruma getirme](#_core_optimizing_your_paint_code)  
  
-   [Meta dosyaları kullanarak denetim boyamak nasıl](#_core_painting_your_control_using_metafiles)  
  
##  <a name="_core_the_painting_process_of_an_activex_control"></a> Bir ActiveX denetimini boyama işlemi  
 ActiveX denetimleri başlangıçta görüntülenir veya yeniden düzenlenmiş, bunlar MFC, önemli bir ayrımdır ile kullanılarak geliştirilen diğer uygulamalar için benzer bir boyama süreci izleyin: ActiveX denetimlerini etkin veya etkin olmayan bir durumda olabilir.  
  
 Etkin bir denetimi alt pencere olarak bir ActiveX denetim kapsayıcısındaki temsil edilir. Diğer windows gibi WM_PAINT iletisi alındığında kendisini boyama için sorumludur. Denetimin temel sınıfı olan [COleControl](../mfc/reference/colecontrol-class.md), bu iletiyi işleyen kendi `OnPaint` işlevi. Bu varsayılan uygulama çağırır `OnDraw` denetiminizin işlevi.  
  
 Etkin olmayan denetimi farklı boyanır. Denetim etkin olduğunda, bir boyama ileti alabilir olmayan şekilde onun penceresi görünmez ya da var olmayan, değil. Bunun yerine, denetimi kapsayıcısı doğrudan çağıran `OnDraw` denetiminin işlevi. Bu etkin bir denetimin boyama işlem farklıdır `OnPaint` üye işlevi hiçbir zaman çağrılır.  
  
 Önceki paragrafta anlatıldığı gibi bir ActiveX denetimini nasıl güncelleştirileceğini denetiminin durumuna bağlıdır. Ancak, framework çağırdığı için `OnDraw` üye işlevi her iki durumda da, bu üye işlevi boyama kodunuzda çoğunluğu ekleyin.  
  
 `OnDraw` Üye işlevi denetim boyama işler. Bir denetim etkin olduğunda, denetimi kapsayıcısı çağırır `OnDraw`, Denetim kapsayıcısının cihaz bağlamı ve denetim tarafından Dolu Dikdörtgen koordinatlarını geçirme.  
  
 Dikdörtgen geçirilen framework tarafından `OnDraw` üye işlevi denetim tarafından kapladığı alanı içerir. Denetim etkin sol üst köşesindeki ise, (0, 0) ve geçirilen cihaz bağlamı için denetimi içeren alt pencere. Denetim etkin değilse, sol üst koordinat olmak zorunda değildir (0, 0) ve geçirilen cihaz bağlamı denetimi içeren denetimi için kapsayıcıdır.  
  
> [!NOTE]
>  Önemlidir, yaptığınız değişiklikler `OnDraw` dikdörtgenin üst sol noktasında eşit olan dayanmayan (0, 0) ve yalnızca dikdörtgende çizmek için geçirilen `OnDraw`. Dikdörtgenin alanı çizme beklenmedik sonuçlar oluşabilir.  
  
 MFC ActiveX Denetim Sihirbazı'nı Denetim dosyasında yer alan uygulama tarafından sağlanan varsayılan uygulama (. CPP) gösterilen aşağıda beyaz fırça dikdörtgen boyar ve üç nokta geçerli arka plan rengiyle doldurur.  
  
 [!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/cpp/mfc-activex-controls-painting-an-activex-control_1.cpp)]  
  
> [!NOTE]
>  Bir denetim boyama yaparken olarak geçirilen cihaz bağlamı durumu hakkındaki varsayımları yapmamalısınız *pdc* parametresi `OnDraw` işlevi. Bazen cihaz bağlamı kapsayıcı uygulama tarafından sağlanan ve mutlaka varsayılan durumuna başlatılmayacak. Özellikle, kalemler, Fırçalar, renkleri, yazı tipleri ve çizim kodunuzu bağımlı diğer kaynaklar açıkça seçin.  
  
##  <a name="_core_optimizing_your_paint_code"></a> Paint kodunuzu iyileştirme  
 Denetimi başarıyla kendisini boyama olduğu sonra sonraki en iyi duruma getirme adımdır `OnDraw` işlevi.  
  
 ActiveX denetimini boyama varsayılan uygulaması tüm denetim alanı boyar. Bu basit denetimler için yeterli olmakla birlikte, güncelleştirme gerekli bölümü, tüm denetim yerine yeniden çizilmiş yalnızca çoğu durumda denetimi yeniden çizerken daha hızlı olacaktır.  
  
 `OnDraw` İşlevi geçirerek en iyi duruma getirme kolay bir yöntemini sağlar *rcInvalid*, yeniden ihtiyacı olan denetim dikdörtgen. Bu alan boyama işlemi hızlandırmak için tüm denetim alanı genellikle daha küçük kullanın.  
  
##  <a name="_core_painting_your_control_using_metafiles"></a> Meta dosyaları kullanarak denetim boyama  
 Çoğu durumda *pdc* parametresi `OnDraw` işlevi bir ekran cihaz bağlamı (DC) işaret eder. Ancak, denetim veya Baskı Önizleme oturumu sırasında görüntülerini yazdırırken, işleme için alınan DC bir "meta DC" adlı bir özel türüdür. Hemen kendisine gönderilen istekleri işler, bir ekran DC, daha sonraki bir zamanda tekrarlanmasını istekleri meta dosyası DC depolar. Bazı kapsayıcı uygulamaları meta dosyası Tasarım modunda DC kullanarak denetim görüntüsü oluşturmak de seçebilirsiniz.  
  
 İstekleri çizim meta dosyası, iki arabirim işlevleri aracılığıyla kapsayıcı tarafından yapılabilir: `IViewObject::Draw` (Bu işlev, aynı zamanda olmayan-çizim meta dosyası için çağrılabilir) ve `IDataObject::GetData`. DC geçirilen parametrelerden biri meta dosyası, MFC çerçevesi için bir çağrı yapar [COleControl::OnDrawMetafile](../mfc/reference/colecontrol-class.md#ondrawmetafile). Bu sanal üye işlevi olduğundan, bu işlev herhangi bir özel işlem yapmak için Denetim sınıfında geçersiz kılar. Varsayılan davranış çağrıları `COleControl::OnDraw`.  
  
 Denetim ekran ve meta dosyası cihaz bağlamlarında çizilebilir emin olmak için bir ekran hem meta dosyası DC desteklenen üye işlevlerini kullanmanız gerekir. Koordinat sistemi piksel cinsinden mi ölçüleceğini değil olduğunu unutmayın.  
  
 Çünkü varsayılan uygulaması `OnDrawMetafile` denetimin çağırır `OnDraw` işlev, kılmanız sürece, meta dosyası ve bir ekran cihaz bağlamı için uygun olan üye işlevlerini `OnDrawMetafile`. Aşağıdaki alt kümesini listeler `CDC` meta dosyası ve bir ekran cihaz bağlamı içinde kullanılabilir üye işlevleri. Bu işlevler hakkında daha fazla bilgi için bkz [CDC](../mfc/reference/cdc-class.md) içinde *MFC başvurusu*.  
  
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
  
 Ek olarak `CDC` üye işlevleri meta dosyası DC uyumlu olan çeşitli işlevleri vardır. Bunlar [CPalette::AnimatePalette](../mfc/reference/cpalette-class.md#animatepalette), [CFont::CreateFontIndirect](../mfc/reference/cfont-class.md#createfontindirect)ve üç üye işlevlerini `CBrush`: [CreateBrushIndirect](../mfc/reference/cbrush-class.md#createbrushindirect), [CreateDIBPatternBrush](../mfc/reference/cbrush-class.md#createdibpatternbrush), ve [CreatePatternBrush](../mfc/reference/cbrush-class.md#createpatternbrush).  
  
 Bir meta kayıtlı olmayan işlevlerdir: [DrawFocusRect](../mfc/reference/cdc-class.md#drawfocusrect), [DrawIcon](../mfc/reference/cdc-class.md#drawicon), [DrawText](../mfc/reference/cdc-class.md#drawtext), [ExcludeUpdateRgn](../mfc/reference/cdc-class.md#excludeupdatergn), [FillRect](../mfc/reference/cdc-class.md#fillrect), [FrameRect](../mfc/reference/cdc-class.md#framerect), [GrayString](../mfc/reference/cdc-class.md#graystring), [InvertRect](../mfc/reference/cdc-class.md#invertrect), [ScrollDC](../mfc/reference/cdc-class.md#scrolldc)ve [TabbedTextOut](../mfc/reference/cdc-class.md#tabbedtextout). Meta dosyası DC gerçekte bir aygıtla ilişkili olmadığından bir meta dosyası DC SetDIBits, GetDIBits ve CreateDIBitmap kullanamazsınız. Hedef olarak bir meta dosyası DC SetDIBitsToDevice ve StretchDIBits kullanabilirsiniz. [CreateCompatibleDC](../mfc/reference/cdc-class.md#createcompatibledc), [CreateCompatibleBitmap](../mfc/reference/cbitmap-class.md#createcompatiblebitmap), ve [CreateDiscardableBitmap](../mfc/reference/cbitmap-class.md#creatediscardablebitmap) bir meta dosyası DC anlamlı değildir.  
  
 Meta dosyası DC kullanırken dikkate alınması gereken başka bir koordinat sistemi piksel cinsinden mi ölçüleceğini değil, noktasıdır. Bu nedenle, tüm çizim kodunuzu ayarlanmış dikdörtgende sığması için geçirilen `OnDraw` içinde *rcBounds* parametresi. Bu denetimi dışında kalan yanlışlıkla boyama çünkü engeller *rcBounds* denetimin pencere boyutunu temsil eder.  
  
 Meta dosyası işleme denetimi için uyguladıktan sonra Test kapsayıcısı meta dosyası sınamak için kullanın. Bkz: [test özellikleri ve olayları Test kapsayıcısı ile](../mfc/testing-properties-and-events-with-test-container.md) test kapsayıcısı erişim hakkında bilgi için.  
  
#### <a name="to-test-the-controls-metafile-using-test-container"></a>Denetimin meta dosyası test kapsayıcısı kullanarak test etmek için  
  
1.  Test kapsayıcısı üzerinde **Düzenle** menüsünde tıklatın **yeni denetimi Ekle**.  
  
2.  İçinde **yeni denetimi Ekle** kutusuna denetimi seçin ve tıklatın **Tamam**.  
  
     Denetimi Test kapsayıcısı içinde görüntülenir.  
  
3.  Üzerinde **denetim** menüsünde tıklatın **çizin meta dosyası**.  
  
     Meta dosyası görüntülendiği ayrı bir pencerede görüntülenir. Denetimin meta ölçeklendirme nasıl etkilediğini görmek için bu pencere boyutunu değiştirebilirsiniz. Herhangi bir anda bu pencereyi kapatabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

