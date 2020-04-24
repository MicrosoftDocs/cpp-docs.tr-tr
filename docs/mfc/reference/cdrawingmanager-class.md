---
title: CDrawingManager Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDrawingManager
- AFXDRAWMANAGER/CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CreateBitmap_32
- AFXDRAWMANAGER/CDrawingManager::DrawAlpha
- AFXDRAWMANAGER/CDrawingManager::DrawRotated
- AFXDRAWMANAGER/CDrawingManager::DrawEllipse
- AFXDRAWMANAGER/CDrawingManager::DrawGradientRing
- AFXDRAWMANAGER/CDrawingManager::DrawRect
- AFXDRAWMANAGER/CDrawingManager::DrawShadow
- AFXDRAWMANAGER/CDrawingManager::Fill4ColorsGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient2
- AFXDRAWMANAGER/CDrawingManager::GrayRect
- AFXDRAWMANAGER/CDrawingManager::HighlightRect
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_ONE
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_TWO
- AFXDRAWMANAGER/CDrawingManager::HSVtoRGB
- AFXDRAWMANAGER/CDrawingManager::HuetoRGB
- AFXDRAWMANAGER/CDrawingManager::MirrorRect
- AFXDRAWMANAGER/CDrawingManager::PixelAlpha
- AFXDRAWMANAGER/CDrawingManager::PrepareShadowMask
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSL
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSV
- AFXDRAWMANAGER/CDrawingManager::SetAlphaPixel
- AFXDRAWMANAGER/CDrawingManager::SetPixel
- AFXDRAWMANAGER/CDrawingManager::SmartMixColors
helpviewer_keywords:
- CDrawingManager [MFC], CDrawingManager
- CDrawingManager [MFC], CreateBitmap_32
- CDrawingManager [MFC], DrawAlpha
- CDrawingManager [MFC], DrawRotated
- CDrawingManager [MFC], DrawEllipse
- CDrawingManager [MFC], DrawGradientRing
- CDrawingManager [MFC], DrawRect
- CDrawingManager [MFC], DrawShadow
- CDrawingManager [MFC], Fill4ColorsGradient
- CDrawingManager [MFC], FillGradient
- CDrawingManager [MFC], FillGradient2
- CDrawingManager [MFC], GrayRect
- CDrawingManager [MFC], HighlightRect
- CDrawingManager [MFC], HLStoRGB_ONE
- CDrawingManager [MFC], HLStoRGB_TWO
- CDrawingManager [MFC], HSVtoRGB
- CDrawingManager [MFC], HuetoRGB
- CDrawingManager [MFC], MirrorRect
- CDrawingManager [MFC], PixelAlpha
- CDrawingManager [MFC], PrepareShadowMask
- CDrawingManager [MFC], RGBtoHSL
- CDrawingManager [MFC], RGBtoHSV
- CDrawingManager [MFC], SetAlphaPixel
- CDrawingManager [MFC], SetPixel
- CDrawingManager [MFC], SmartMixColors
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
ms.openlocfilehash: 73c5775c2cb83dea79401615b31f2194094fac8e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753231"
---
# <a name="cdrawingmanager-class"></a>CDrawingManager Sınıfı

Sınıf `CDrawingManager` karmaşık çizim algoritmaları uygular.

## <a name="syntax"></a>Sözdizimi

```
class CDrawingManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|Bir `CDrawingManager` nesne inşa eder.|
|`CDrawingManager::~CDrawingManager`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|Uygulamaların doğrudan yazabileceği 32 bit aygıtbağımsız bit eşlemi (DIB) oluşturur.|
|[CDrawingManager::DrawAlpha](#drawalpha)|Saydam veya yarı saydam piksellere sahip bit eşlemleri görüntüler.|
|[CDrawingManager::DrawRotated](#drawrotated)|Kaynak DC içeriğini verilen dikdörtgenin içinde +/- 90 derece döndürür|
|[CDrawingManager::DrawEllipse](#drawellipse)|Verilen dolgu ve kenarlık renkleri ile bir elips çizer.|
|[CDrawingManager::DrawGradientRing](#drawgradientring)|Bir halka çizer ve bir renk degradesi ile doldurur.|
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|Bir çizgi çizer.|
|[CDrawingManager::DrawRect](#drawrect)|Verilen dolgu ve kenarlık renkleriyle bir dikdörtgen çizer.|
|[CDrawingManager::DrawShadow](#drawshadow)|Dikdörtgen bir alan için gölge çizer.|
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|Dikdörtgen bir alanı iki renk degradesiyle doldurur.|
|[CDrawingManager::FillGradient](#fillgradient)|Dikdörtgen bir alanı belirli bir renk degradesiyle doldurur.|
|[CDrawingManager::FillGradient2](#fillgradient2)|Dikdörtgen bir alanı belirli bir renk degradesiyle doldurur. Degradenin renk değişiminin yönü de belirtilir.|
|[CDrawingManager::GrayRect](#grayrect)|Dikdörtgeni belirtilen gri renkle doldurur.|
|[CDrawingManager::HighlightRect](#highlightrect)|Dikdörtgen bir alanı vurgular.|
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|Bir rengi HLS gösteriminden RGB temsiline dönüştürür.|
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|Bir rengi HLS gösteriminden RGB temsiline dönüştürür.|
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|Bir rengi HSV gösteriminden RGB gösterimine dönüştürür.|
|[CDrawingManager::HuetoRGB](#huetorgb)|Ton değerini kırmızı, yeşil veya mavi bileşene dönüştüren yardımcı yöntem.|
|[CDrawingManager::MirrorRect](#mirrorrect)|Dikdörtgen bir alanı çevirir.|
|[CDrawingManager::PixelAlpha](#pixelalpha)|Yarı saydam bir pikselin son rengini belirleyen yardımcı yöntem.|
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|Gölge olarak kullanılabilecek bir bit eşlemi oluşturur.|
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|Bir rengi RGB gösteriminden HSL gösterimine dönüştürür.|
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|Bir rengi RGB gösteriminden HSV temsiline dönüştürür.|
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|Bitmap'te kısmen saydam bir pikseli renklendiren yardımcı yöntem.|
|[CDrawingManager::SetPixel](#setpixel)|Biteş'teki tek bir pikseli belirtilen renge değiştiren yardımcı yöntem.|
|[CDrawingManager::SmartMixColors](#smartmixcolors)|Ağırlıklı orana göre iki rengi birleştirir.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CDrawingManager` gölgeler, renk degradeleri ve vurgulanmış dikdörtgenler çizmek için işlevler sağlar. Ayrıca alfa karıştırma gerçekleştirir. Uygulamanızın Kullanıcı GKullanımını doğrudan değiştirmek için bu sınıfı kullanabilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)<br/>
`CDrawingManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdrawmanager.h

## <a name="cdrawingmanagercdrawingmanager"></a><a name="cdrawingmanager"></a>CDrawingManager::CDrawingManager

[CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) nesnesi oluşturuyor.

```
CDrawingManager(CDC& dc);
```

### <a name="parameters"></a>Parametreler

*Dc*<br/>
[içinde] Aygıt bağlamına başvuru. Çizim `CDrawingManager` için bu bağlamı kullanır.

## <a name="cdrawingmanagercreatebitmap_32"></a><a name="createbitmap_32"></a>CDrawingManager::CreateBitmap_32

Uygulamaların doğrudan yazabileceği 32 bit aygıtbağımsız bit eşlemi (DIB) oluşturur.

```
static HBITMAP __stdcall CreateBitmap_32(
    const CSize& size,
    void** pBits);

static HBITMAP __stdcall CreateBitmap_32(
    HBITMAP bitmap,
    COLORREF clrTransparent = -1);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*Boyutu*|[içinde] Bit eşboyutunu gösteren bir [CSize](../../atl-mfc-shared/reference/csize-class.md) parametresi.|
|*pBits*|[çıkış] DIB bit değerlerinin konumunu alan bir veri işaretçisi için bir işaretçi.|
|*Bitmap*|Özgün bit eşlemi için bir tutamaç|
|*clrŞeffaf*|Özgün bit eşleminin saydam rengini belirten bir RGB değeri.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa, yeni oluşturulan DIB bit eşlemi için bir tutamaç; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

DIB bit eşlemi nasıl oluşturulacak hakkında daha fazla bilgi için [CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibitmap)bölümüne bakın.

## <a name="cdrawingmanagerdrawalpha"></a><a name="drawalpha"></a>CDrawingManager::DrawAlpha

Saydam veya yarı saydam piksellere sahip bit eşlemleri görüntüler.

```cpp
void DrawAlpha(
    CDC* pDstDC,
    const CRect& rectDst,
    CDC* pSrcDC,
    const CRect& rectSrc);
```

### <a name="parameters"></a>Parametreler

*pDstDC*<br/>
[içinde] Hedef için aygıt bağlamına bir işaretçi.

*rektDst*<br/>
[içinde] Hedef dikdörtgen.

*pSrcDC*<br/>
[içinde] Kaynak için aygıt bağlamına bir işaretçi.

*rectSrc*<br/>
[içinde] Kaynak dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iki bit eşlem için alfa karıştırma gerçekleştirir. Alfa karıştırma hakkında daha fazla bilgi için Windows SDK'daki [AlphaBlend'e](/windows/win32/api/wingdi/nf-wingdi-alphablend) bakın.

## <a name="cdrawingmanagerdrawellipse"></a><a name="drawellipse"></a>CDrawingManager::DrawEllipse

Verilen dolgu ve kenarlık renkleri ile bir elips çizer.

```cpp
void DrawEllipse(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Elips için sınırlayıcı dikdörtgen.

*clrDoldur*<br/>
[içinde] Bu yöntemin elipsi doldurmak için kullandığı renk.

*clrLine*<br/>
[içinde] Bu yöntemin elips kenarlığı olarak kullandığı renk.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, her iki renk -1 olarak ayarlanmışsa bir elips çizmeden döndürür. Ayrıca, sınırlayan dikdörtgenin her iki boyutu da 0 ise elips çizmeden geri döner.

## <a name="cdrawingmanagerdrawgradientring"></a><a name="drawgradientring"></a>CDrawingManager::DrawGradientRing

Bir halka çizer ve bir renk degradesi ile doldurur.

```
BOOL DrawGradientRing(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    COLORREF colorBorder,
    int nAngle,
    int nWidth,
    COLORREF clrFace = (COLORREF)-1);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Degrade halkasının sınırını belirten bir [CRect](../../atl-mfc-shared/reference/crect-class.md) parametresi.

*colorStart*<br/>
[içinde] Degrade için ilk renk.

*colorFinish*<br/>
[içinde] Degrade için son renk.

*colorBorder*<br/>
[içinde] Sınırın rengi.

*nAçı*<br/>
[içinde] İlk degrade çizim açısını belirten bir parametre. Bu değer 0 ile 360 arasında olmalıdır.

*Nwidth*<br/>
[içinde] Halka için kenarlık genişliği.

*clrYüz*<br/>
[içinde] Yüzüğün iç rengi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*Dikdörtgen* tarafından tanımlanan dikdörtgen en az 5 piksel genişliğinde ve 5 piksel yüksekliğinde olmalıdır.

## <a name="cdrawingmanagerdrawline-cdrawingmanagerdrawlinea"></a><a name="drawline_cdrawingmanager__drawlinea"></a>CDrawingManager::DrawLine, CDrawingManager::DrawLineA

Bir çizgi çizer.

```cpp
void DrawLine(
    int x1,
    int y1,
    int x2,
    int y2,
    COLORREF clrLine);

void DrawLineA(
    double x1,
    double y1,
    double x2,
    double y2,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*x1*|[içinde] X, çizginin başladığı yeri koordine edin.|
|*y1*|[içinde] Çizginin başladığı y koordinatı.|
|*x2*|[içinde] X, çizginin bittiği yerde koordinat ı.|
|*y2*|[içinde] Çizginin bittiği yerin y koordinatı.|
|*clrLine*|[içinde] Çizginin rengi.|

### <a name="remarks"></a>Açıklamalar

*ClrLine* -1'e eşitse bu yöntem başarısız olur.

## <a name="cdrawingmanagerdrawrect"></a><a name="drawrect"></a>CDrawingManager::DrawRect

Verilen dolgu ve kenarlık renkleriyle bir dikdörtgen çizer.

```cpp
void DrawRect(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Dikdörtgenin sınırları.

*clrDoldur*<br/>
[içinde] Bu yöntemin dikdörtgeni doldurmak için kullandığı renk.

*clrLine*<br/>
[içinde] Bu yöntemin dikdörtgenin kenarlığı için kullandığı renk.

### <a name="remarks"></a>Açıklamalar

Her iki renk de -1 olarak ayarlanmışsa, bu yöntem dikdörtgen çizmeden döndürür. Dikdörtgenin her iki boyutu 0 ise de döndürür.

## <a name="cdrawingmanagerdrawshadow"></a><a name="drawshadow"></a>CDrawingManager::DrawShadow

Dikdörtgen bir alan için gölge çizer.

```
BOOL DrawShadow(
    CRect rect,
    int nDepth,
    int iMinBrightness = 100,
    int iMaxBrightness = 50,
    CBitmap* pBmpSaveBottom = NULL,
    CBitmap* pBmpSaveRight = NULL,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bRightShadow = TRUE);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Uygulamanızda dikdörtgen bir alan. Çizim yöneticisi bu alanın altına bir gölge çizer.

*nDerinlik*<br/>
[içinde] Gölgenin genişliği ve yüksekliği.

*iMinParlaklık*<br/>
[içinde] Gölgenin minimum parlaklığı.

*iMaxParlaklık*<br/>
[içinde] Gölgenin maksimum parlaklığı.

*pBmpSaveBottom*<br/>
[içinde] Gölgenin alt kısmının görüntüsünü içeren bir bit eşlemi için işaretçi.

*pBmpSaveRight*<br/>
[içinde] Dikdörtgenin sağ tarafında çizilen gölge için görüntü içeren bir bit eşlemi işaretçisi.

*clrBase*<br/>
[içinde] Gölgenin rengi.

*bRightShadow*<br/>
[içinde] Gölgenin nasıl çizildiğini gösteren bir Boolean parametresi. *bRightShadow* `TRUE`ise, `DrawShadow` dikdörtgenin sağ tarafına bir gölge çizer.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*PBmpSaveBottom* ve *pBmpSaveRight*parametrelerini kullanarak alt ve sağ gölgeler için iki geçerli bit eşlem sağlayabilirsiniz. Bu [CBitmap](../../mfc/reference/cbitmap-class.md) nesnelerinde ekli bir GDI `DrawShadow` nesnesi varsa, bu bit eşlemleri gölgeler olarak kullanır. Parametrelerekli `CBitmap` bir GDI nesnesi yoksa, `DrawShadow` gölgeçizer ve parametreye bit eşlemleri bağlar. Gelecekteki `DrawShadow`aramalarda, çizim işlemini hızlandırmak için bu bit eşlemlerini sağlayabilirsiniz. `CBitmap` Sınıf ve GDI nesneleri hakkında daha fazla bilgi için [Bkz. Grafik Nesneler.](../../mfc/graphic-objects.md)

Bu parametrelerden biri `NULL` `DrawShadow` varsa, otomatik olarak gölge çizecektir.

*bRightShadow'u* FALSE olarak ayarlarsanız, gölge dikdörtgen alanın altına ve soluna çizilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın yönteminin `DrawShadow` nasıl `CDrawingManager` kullanılacağını göstermektedir. Bu kod parçacığı Prop Levha [Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]

## <a name="cdrawingmanagerfill4colorsgradient"></a><a name="fill4colorsgradient"></a>CDrawingManager::Fill4ColorsGradient

Dikdörtgen bir alanı iki renk degradesiyle doldurur.

```cpp
void Fill4ColorsGradient(
    CRect rect,
    COLORREF colorStart1,
    COLORREF colorFinish1,
    COLORREF colorStart2,
    COLORREF colorFinish2,
    BOOL bHorz = TRUE,
    int nPercentage = 50);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Dolması gereken dikdörtgen.

*colorBaşlangıç1*<br/>
[içinde] İlk renk degradesi için ilk renk.

*colorFinish1*<br/>
[içinde] İlk renk degradesi için son renk.

*colorBaşlangıç2*<br/>
[içinde] İkinci renk degradesinin başlangıç rengi.

*colorFinish2*<br/>
[içinde] İkinci renk degradesi için son renk.

*bHorz*<br/>
[içinde] Yatay veya dikey degrade `Fill4ColorsGradient` renklendirilip renklendirmediğini gösteren boolean parametresi. TRUE yatay bir degradegösterir.

*nYüzde*<br/>
[içinde] 0-100 arası bir sonda. Bu değer, ilk renk degradesi ile doldurmak için dikdörtgenin yüzdesini gösterir.

### <a name="remarks"></a>Açıklamalar

Bir dikdörtgen iki renk degradesi ile doldurulduğunda, *bHorz*değerine bağlı olarak, ya birbiri ya da yan yana yer alır. Her renk degradesi [CDrawingManager::FillGradient](#fillgradient)yöntemi ile bağımsız olarak hesaplanır.

Bu yöntem, *nYüzde* 0'dan az veya 100'den fazlaysa bir sedama hatası oluşturur.

## <a name="cdrawingmanagerfillgradient"></a><a name="fillgradient"></a>CDrawingManager::FillGradient

Dikdörtgen bir alanı belirtilen renk degradesiyle doldurur.

```cpp
void FillGradient(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    BOOL bHorz = TRUE,
    int nStartFlatPercentage = 0,
    int nEndFlatPercentage = 0);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Doldurulacak dikdörtgen alan.

*colorStart*<br/>
[içinde] Degrade için ilk renk.

*colorFinish*<br/>
[içinde] Degrade için son renk.

*bHorz*<br/>
[içinde] Yatay veya dikey degrade çizip `FillGradient` çizmemesi gerektiğini belirten bir Boolean parametresi.

*nStartFlatPercentage*<br/>
[içinde] Degradeyi başlatmadan önce `FillGradient` *colorStart* ile dolan dikdörtgenyüzdesi.

*nEndFlatPercentage*<br/>
[içinde] Degradeyi bitirdikten sonra `FillGradient` *colorFinish* ile dolan dikdörtgenyüzdesi.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın yönteminin `FillGradient` nasıl `CDrawingManager` kullanılacağını göstermektedir. Bu kod parçacığı MS Office [2007 Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]

## <a name="cdrawingmanagerfillgradient2"></a><a name="fillgradient2"></a>CDrawingManager::FillGradient2

Dikdörtgen bir alanı belirli bir renk degradesiyle doldurur.

```cpp
void FillGradient2 (
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    int nAngle = 0);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Doldurulacak dikdörtgen alan.

*colorStart*<br/>
[içinde] Degradenin ilk rengi.

*colorFinish*<br/>
[içinde] Degradenin son rengi.

*nAçı*<br/>
[içinde] 0 ile 360 arasında bir sonda. Bu parametre renk degradesinin yönünü belirtir.

### <a name="remarks"></a>Açıklamalar

Renk degradesinin yönünü belirtmek için *nAngle'yi* kullanın. Renk degradesinin yönünü belirttiğiniz zaman, renk degradesinin nerede başlayacağını da belirtirsiniz. *nAngle* için 0 değeri, degradenin dikdörtgenin üstünden başladığını gösterir. *nAngle* arttıkça, degradenin başlangıç konumu açıya göre saat yönünün tersine hareket eder.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın yönteminin `FillGradient2` nasıl `CDrawingManager` kullanılacağını göstermektedir. Bu kod snippet [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]

## <a name="cdrawingmanagergrayrect"></a><a name="grayrect"></a>CDrawingManager::GrayRect

Dikdörtgeni belirtilen gri renkle doldurur.

```
BOOL GrayRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    COLORREF clrDisabled = (COLORREF)-1);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Doldurulacak dikdörtgen alan.

*nYüzde*<br/>
[içinde] Dikdörtgende istediğiniz gri yüzdesi.

*clrŞeffaf*<br/>
[içinde] Saydam renk.

*clrDevre dışı*<br/>
[içinde] *nPercentage* -1 olarak ayarlanmışsa, bu yöntemin doygunluk için kullandığı renk.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

parametre *nPercentage*için, daha düşük bir değer daha koyu bir rengi gösterir.

*nPercentage* için maksimum değer 200'dür. 200'den büyük bir değer dikdörtgenin görünümünü değiştirmez. Değer -1 ise, bu yöntem dikdörtgenin doygunluğu sınırlamak için *clrDisabled* kullanır.

## <a name="cdrawingmanagerhighlightrect"></a><a name="highlightrect"></a>CDrawingManager::HighlightRect

Dikdörtgen bir alanı vurgular.

```
BOOL HighlightRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    int nTolerance = 0,
    COLORREF clrBlend = (COLORREF)-1);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Vurgulanması gereken dikdörtgen bir alan.

*nYüzde*<br/>
[içinde] Vurgunun ne kadar saydam olması gerektiğini gösteren bir yüzde.

*clrŞeffaf*<br/>
[içinde] Saydam renk.

*nHoşgörü*<br/>
[içinde] Renk toleransını gösteren 0 ile 255 arasında bir arayış.

*clrBlend*<br/>
[içinde] Karıştırma için temel renk.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

*nPercentage* 0 ile 99 `HighlightRect` arasındaysa, alfa karıştırma algoritmasını kullanır. Alfa karıştırma hakkında daha fazla bilgi için [Alfa Karıştırma Çizgileri ve Dolgular'a](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills)bakın. *nPercentage* -1 ise, bu yöntem varsayılan vurgu düzeyini kullanır. *nPercentage* 100 ise, bu yöntem hiçbir şey yapmaz ve TRUE döndürür.

Yöntem, dikdörtgen alanı vurgulamak için olup olmadığını belirlemek için parametre *nTolerance* kullanır. Dikdörtgeni vurgulamak için, uygulamanızın arka plan rengi ile *clrTransparent* arasındaki fark, her renk bileşenindeki (kırmızı, yeşil ve mavi) *nTolerance'dan* daha az olmalıdır.

## <a name="cdrawingmanagerhlstorgb_one"></a><a name="hlstorgb_one"></a>CDrawingManager::HLStoRGB_ONE

Bir rengi HLS gösteriminden RGB temsiline dönüştürür.

```
static COLORREF __stdcall HLStoRGB_ONE(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
[içinde] Rengin tonunu temsil eden 0 ile 1 arasındaki bir sayı.

*L*<br/>
[içinde] 0 ile 1 arasındaki renk parlaklığını gösteren bir sayı.

*S*<br/>
[içinde] Renk doygunluğu gösteren 0 ve 1 arasındaki bir sayı.

### <a name="return-value"></a>Dönüş Değeri

HLS renginin RGB temsili sağlanmıştır.

### <a name="remarks"></a>Açıklamalar

Bir renk HSV (ton, doygunluk ve değer), HSL (ton, doygunluk ve parlaklık) veya RGB (kırmızı, yeşil ve mavi) olarak temsil edilebilir. Rengin farklı gösterimleri hakkında daha fazla bilgi için [Bkz. Renk.](/windows/win32/uxguide/vis-color)

Bu yöntem `CDrawingManager::HLStoRGB_TWO` ve yöntem aynı işlemi gerçekleştirmek, ancak *H* parametresi için farklı değerler gerektirir. Bu yöntemde, *H* dairenin bir yüzdesidir. `CDrawingManager::HLStoRGB_TWO` Yöntemde, *H* 0 ve 360 arasında bir derece değeri, her ikisi de kırmızı temsil ediyor. Örneğin, `HLStoRGB_ONE` *, H* için 0,25 değeri 90 ile 90 `HLStoRGB_TWO`değerine eşdeğerdir.

## <a name="cdrawingmanagerhlstorgb_two"></a><a name="hlstorgb_two"></a>CDrawingManager::HLStoRGB_TWO

Bir rengi HLS gösteriminden RGB temsiline dönüştürür.

```
static COLORREF __stdcall HLStoRGB_TWO(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
[içinde] Rengin tonunu temsil eden 0 ile 360 arasındaki bir sayı.

*L*<br/>
[içinde] 0 ile 1 arasındaki renk parlaklığını gösteren bir sayı.

*S*<br/>
[içinde] Renk doygunluğu gösteren 0 ve 1 arasındaki bir sayı.

### <a name="return-value"></a>Dönüş Değeri

HLS renginin RGB temsili sağlanmıştır.

### <a name="remarks"></a>Açıklamalar

Bir renk HSV (ton, doygunluk ve değer), HSL (ton, doygunluk ve parlaklık) veya RGB (kırmızı, yeşil ve mavi) olarak temsil edilebilir. Rengin farklı gösterimleri hakkında daha fazla bilgi için [Bkz. Renk.](/windows/win32/uxguide/vis-color)

Bu yöntem ve [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) yöntemi aynı işlemi gerçekleştirir, ancak *H* parametresi için farklı değerler gerektirir. Bu yöntemde, *H* 0 ve 360 arasında bir derece değeri, her ikisi de kırmızı temsil ediyor. [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) yönteminde, *H* dairenin yüzdesidir. Örneğin, `HLStoRGB_ONE` *, H* için 0,25 değeri 90 ile 90 `HLStoRGB_TWO`değerine eşdeğerdir.

## <a name="cdrawingmanagerhsvtorgb"></a><a name="hsvtorgb"></a>CDrawingManager::HSVtoRGB

Bir rengi HSV gösteriminden RGB gösterimine dönüştürür.

```
static COLORREF __stdcall HSVtoRGB(
    double H,
    double S,
    double V);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*H*|[içinde] Rengin tonunu gösteren 0 ile 360 arasındaki bir sayı.|
|*S*|[içinde] Renk doygunluğu gösteren 0 ve 1 arasındaki bir sayı.|
|*V*|[içinde] Rengin değerini gösteren 0 ile 1 arasındaki bir sayı.|

### <a name="return-value"></a>Dönüş Değeri

HSV renginin RGB gösterimi sağlanmıştır.

### <a name="remarks"></a>Açıklamalar

Bir renk HSV (ton, doygunluk ve değer), HSL (ton, doygunluk ve parlaklık) veya RGB (kırmızı, yeşil ve mavi) olarak temsil edilebilir. Rengin farklı gösterimleri hakkında daha fazla bilgi için [Bkz. Renk.](/windows/win32/uxguide/vis-color)

## <a name="cdrawingmanagerhuetorgb"></a><a name="huetorgb"></a>CDrawingManager::HuetoRGB

Ton değerini kırmızı, yeşil veya mavi bileşene dönüştürür.

```
static double __stdcall HuetoRGB(
    double m1,
    double m2,
    double h);

static BYTE __stdcall HueToRGB(
    float rm1,
    float rm2,
    float rh);
```

### <a name="parameters"></a>Parametreler

*m1*<br/>
[içinde] Bkz. Açıklamalar.

*m2*<br/>
[içinde] Bkz. Açıklamalar.

*H*<br/>
[içinde] Bkz. Açıklamalar.

*rm1*<br/>
[içinde] Bkz. Açıklamalar.

*rm2*<br/>
[içinde] Bkz. Açıklamalar.

*Rh*<br/>
[içinde] Bkz. Açıklamalar.

### <a name="return-value"></a>Dönüş Değeri

Sağlanan ton için tek tek kırmızı, yeşil veya mavi bileşen.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CDrawingManager` sınıfın hsv veya HSL gösterimindeki bir rengin tek tek kırmızı, yeşil ve mavi bileşenlerini hesaplamak için kullandığı yardımcı yöntemdir. Bu yöntem, doğrudan programcı tarafından çağrılacak şekilde tasarlanmaz. Giriş parametreleri dönüştürme algoritması bağlı değerlerdir.

HSV veya HSL rengini RGB gösterimine dönüştürmek için aşağıdaki yöntemlerden birini arayın:

- [CDrawingManager::HSVtoRGB](#hsvtorgb)

- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)

- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)

## <a name="cdrawingmanagermirrorrect"></a><a name="mirrorrect"></a>CDrawingManager::MirrorRect

Dikdörtgen bir alanı çevirir.

```cpp
void MirrorRect(
    CRect rect,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Çevirmek için alanın sınırlayıcı dikdörtgen.

*bHorz*<br/>
[içinde] Dikdörtgenin yatay veya dikey olarak mı takla attığını gösteren boolean parametresi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CDrawingManager` sınıfın sahip olduğu aygıt bağlamının herhangi bir alanını çevirebilir. *bHorz* TRUE olarak ayarlanmışsa, bu yöntem alanı yatay olarak çevirir. Aksi takdirde, alanı dikey olarak çevirir.

## <a name="cdrawingmanagerpixelalpha"></a><a name="pixelalpha"></a>CDrawingManager::PixelAlpha

Yarı saydam bir pikseliçin son rengi hesaplar.

```
static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    int percent);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    double percentR,
    double percentG,
    double percentB);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    COLORREF dstPixel,
    int percent);
```

### <a name="parameters"></a>Parametreler

*srcPixel*<br/>
[içinde] Pikselin ilk rengi.

*Yüzde*<br/>
[içinde] Saydamlık yüzdesini temsil eden 0 ile 100 arasındaki bir sayı. 100 değeri, ilk rengin tamamen saydam olduğunu gösterir.

*yüzdeR*<br/>
[içinde] Kırmızı bileşen için saydamlık yüzdesini temsil eden 0 ile 100 arasındaki bir sayı.

*yüzdeG*<br/>
[içinde] Yeşil bileşen için saydamlık yüzdesini temsil eden 0 ile 100 arasındaki bir sayı.

*yüzdeB*<br/>
[içinde] Mavi bileşen için saydamlık yüzdesini temsil eden 0 ile 100 arasındaki bir sayı.

*dstPiksel*<br/>
[içinde] Pikselin temel rengi.

### <a name="return-value"></a>Dönüş Değeri

Yarı saydam piksel için son renk.

### <a name="remarks"></a>Açıklamalar

Bu, yarı saydam bit eşlemlerini boyamak için yardımcı bir sınıftır ve doğrudan programcı tarafından çağrılacak şekilde tasarlanmamıştır.

*DstPixel*olan yöntemin sürümünü kullandığınızda, son renk *dstPixel* ve *srcPixel*bir arada . *SrcPixel* renk *dstPixel*temel renk üzerinde kısmen saydam renktir.

## <a name="cdrawingmanagerprepareshadowmask"></a><a name="prepareshadowmask"></a>CDrawingManager::PrepareShadowMask

Gölge olarak kullanılabilecek bir bit eşlemi oluşturur.

```
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,
    COLORREF clrBase,
    int iMinBrightness = 0,
    int iMaxBrightness = 100);
```

### <a name="parameters"></a>Parametreler

*nDerinlik*<br/>
[içinde] Gölgenin genişliği ve yüksekliği.

*clrBase*<br/>
[içinde] Gölgenin rengi.

*iMinParlaklık*<br/>
[içinde] Gölgenin minimum parlaklığı.

*iMaxParlaklık*<br/>
[içinde] Gölgenin maksimum parlaklığı.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa oluşturulan bit eşlemi için bir tutamaç; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

*nDepth* 0 olarak ayarlanırsa, bu yöntem çıkar ve NULL döndürür. *nDepth* 3'ten küçükse, gölgenin genişliği ve yüksekliği 3 piksel olarak ayarlanır.

## <a name="cdrawingmanagerrgbtohsl"></a><a name="rgbtohsl"></a>CDrawingManager::RGBtoHSL

Kırmızı, yeşil ve mavi (RGB) gösteriminden rengi ton, doygunluk ve hafiflik (HSL) gösterimine dönüştürür.

```
static void __stdcall RGBtoHSL(
    COLORREF rgb,
    double* H,
    double* S,
    double* L);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*Rgb*|[içinde] RGB değerlerindeki renk.|
|*H*|[çıkış] Yöntemin rengin tonunu depoladığı bir çift işaretçi.|
|*S*|[çıkış] Yöntemin renk doygunluğu depoladığı bir çift için işaretçi.|
|*L*|[çıkış] Yöntemin renk için açıklığı depoladığı bir çift işaretçi.|

### <a name="remarks"></a>Açıklamalar

Bir renk HSV (ton, doygunluk ve değer), HSL (ton, doygunluk ve parlaklık) veya RGB (kırmızı, yeşil ve mavi) olarak temsil edilebilir. Rengin farklı gösterimleri hakkında daha fazla bilgi için [Bkz. Renk.](/windows/win32/uxguide/vis-color)

*H* için döndürülen değer, 0 ile 1 arasında bir kesir olarak temsil edilir ve hem 0 hem de 1 kırmızıyı temsil edilir. *S* ve *L* için döndürülen değerler 0 ile 1 arasındaki sayılardır.

## <a name="cdrawingmanagerrgbtohsv"></a><a name="rgbtohsv"></a>CDrawingManager::RGBtoHSV

Bir rengi RGB gösteriminden HSV temsiline dönüştürür.

```
static void __stdcall RGBtoHSV(
    COLORREF rgb,
    double* H,
    double* S,
    double* V);
```

### <a name="parameters"></a>Parametreler

*Rgb*<br/>
[içinde] RGB gösteriminde dönüştürülecek renk.

*H*<br/>
[çıkış] Bu yöntemin renk için ortaya çıkan tonunu depoladığı bir çift işaretçi.

*S*<br/>
[çıkış] Bu yöntemin renk için ortaya çıkan doygunluğu depoladığı bir çift işaretçi.

*V*<br/>
[çıkış] Bu yöntemin renk için ortaya çıkan değeri depoladığı bir çift işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir renk HSV (ton, doygunluk ve değer), HSL (ton, doygunluk ve parlaklık) veya RGB (kırmızı, yeşil ve mavi) olarak temsil edilebilir. Rengin farklı gösterimleri hakkında daha fazla bilgi için [Bkz. Renk.](/windows/win32/uxguide/vis-color)

*H* için döndürülen değer, 0 ve 360 arasında 0 ve 360 arasında bir sayıdır. *S* ve *V'nin* dönüş değerleri 0 ile 1 arasındaki sayılardır.

## <a name="cdrawingmanagersetalphapixel"></a><a name="setalphapixel"></a>CDrawingManager::SetAlphaPixel

Saydam pikseli bit eşlemi renklendirin.

```
static void __stdcall SetAlphaPixel(
    COLORREF* pBits,
    CRect rect,
    int x,
    int y,
    int percent,
    int iShadowSize,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bIsRight = TRUE);
```

### <a name="parameters"></a>Parametreler

*pBits*<br/>
[içinde] Bit eşlemi için bit değerlerine işaretçi.

*Rect*<br/>
[içinde] Uygulamanızda dikdörtgen bir alan. Çizim yöneticisi bu alanın altına ve sağına bir gölge çizer.

*X*<br/>
[içinde] Pikselin yatay koordinatı renk.

*Y*<br/>
[içinde] Pikselin renk dikey koordinatı.

*Yüzde*<br/>
[içinde] Şeffaflık yüzdesi.

*iShadowSize*<br/>
[içinde] Gölgenin genişliği ve yüksekliği.

*clrBase*<br/>
[içinde] Gölgenin rengi.

*bIsRight*<br/>
[içinde] Hangi pikselin renklendirdiğini gösteren boolean parametresi. Daha fazla bilgi için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CDrawingManager::DrawShadow](#drawshadow) yöntemi tarafından kullanılan bir yardımcı yöntemdir. Bir gölge çizmek istiyorsanız, bunun yerine `CDrawingManager::DrawShadow` aramanızı öneririz.

*bIsRight* TRUE olarak ayarlanmışsa, renk *pikseli rektsağ*kenarından *x* piksel ölçülür. FALSE ise, renk *pikseli rekt*sol kenarından *x* piksel ölçülür.

## <a name="cdrawingmanagersetpixel"></a><a name="setpixel"></a>CDrawingManager::SetPixel

Bit eşlemindeki tek bir pikseli belirtilen renge değiştirir.

```
static void __stdcall SetPixel(
    COLORREF* pBits,
    int cx,
    int cy,
    int x,
    int y,
    COLORREF color);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pBits*|[içinde] Bit eşleminin bit değerlerine işaretçi.|
|*Cx*|[içinde] Bit eşleminin toplam genişliği.|
|*Cy*|[içinde] Bit haritasının toplam yüksekliği.|
|*X*|[içinde] Değiştirmek için bit eşönündepikselin x-koordinatı.|
|*Y*|[içinde] Değiştirmek için bit eşlemindeki pikselin y-koordinatı.|
|*color*|[içinde] Sağlanan koordinatlar tarafından tanımlanan piksel için yeni renk.|

## <a name="cdrawingmanagersmartmixcolors"></a><a name="smartmixcolors"></a>CDrawingManager::SmartMixColors

Ağırlıklı orana göre iki rengi birleştirir.

```
static COLORREF __stdcall SmartMixColors(
    COLORREF color1,
    COLORREF color2,
    double dblLumRatio = 1.,
    int k1 = 1,
    int k2 = 1);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*renk1*|[içinde] İlk renk karışır.|
|*renk2*|[içinde] Karıştırılacak ikinci renk.|
|*dblLumRatio*|[içinde] Yeni rengin parlaklığı oranı. `SmartMixColors`son rengi belirlemeden önce karışık rengin parlaklığını bu oran ile çarpar.|
|*k1*|[içinde] İlk renk için ağırlıklı oran.|
|*k2*|[içinde] İkinci renk için ağırlıklı oran.|

### <a name="return-value"></a>Dönüş Değeri

Verilen renklerin ağırlıklı bir karışımını temsil eden bir renk.

### <a name="remarks"></a>Açıklamalar

*K1* veya *k2* sıfırdan küçükse bu yöntem bir hata ile başarısız olur. Bu parametrelerin her ikisi de 0 `RGB(0, 0, 0)`olarak ayarlanırsa, yöntem döndürür.

Ağırlıklı oran aşağıdaki formülle hesaplanır: (color1 \* k1 \* + color2 k2)/(k1 + k2). Ağırlıklı oran belirlendikten sonra, yöntem karışık renk için parlaklık hesaplar. Daha sonra *dblLumRatio*ile parlaklık çarpar. Değer 1,0'dan büyükse, yöntem karışık rengin parlaklığını yeni değere ayarlar. Aksi takdirde, parlaklık 1.0 olarak ayarlanır.

## <a name="cdrawingmanagerdrawrotated"></a><a name="drawrotated"></a>CDrawingManager::DrawRotated

Verilen dikdörtgenin içindeki kaynak DC içeriğini 90 derece döndürür.

```cpp
void DrawRotated(
    CRect rectDest,
    CDC& dcSrc,
    BOOL bClockWise);
```

### <a name="parameters"></a>Parametreler

*rektDest*<br/>
Hedef dikdörtgen.

*dcSrc*<br/>
Kaynak aygıt bağlamı.

*bClockWise*<br/>
TRUE +90 derece döndürdüğünü gösterir; FALSE -90 derece döndürdüğünü gösterir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
