---
title: CDrawingManager sınıfı
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
ms.openlocfilehash: 1cc469b63e448e964dacc4d853905b22155dfe0e
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561641"
---
# <a name="cdrawingmanager-class"></a>CDrawingManager sınıfı

`CDrawingManager`Sınıfı karmaşık çizim algoritmaları uygular.

## <a name="syntax"></a>Syntax

```
class CDrawingManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDrawingManager:: CDrawingManager](#cdrawingmanager)|Bir `CDrawingManager` nesnesi oluşturur.|
|`CDrawingManager::~CDrawingManager`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDrawingManager:: CreateBitmap_32](#createbitmap_32)|Uygulamaların doğrudan yazabilmesi için 32 bitlik bir cihazdan bağımsız bit eşlem (DIB) oluşturur.|
|[CDrawingManager::D Rampapha](#drawalpha)|Saydam veya yarı saydam piksel olan bit eşlemleri görüntüler.|
|[CDrawingManager::D Rawdöndürülmüş](#drawrotated)|Verilen dikdörtgenin içindeki kaynak DC içeriğini +/-90 derece döndürür|
|[CDrawingManager::D rawEllipse](#drawellipse)|Sağlanan Fill ve Border renkleriyle bir elips çizer.|
|[CDrawingManager::D Rawgradiing](#drawgradientring)|Bir halka çizer ve renk degradeyle doldurur.|
|[CDrawingManager::D rawLine, CDrawingManager::D rawLineA](#drawline_cdrawingmanager__drawlinea)|Bir çizgi çizer.|
|[CDrawingManager::D rawRect](#drawrect)|Sağlanan Fill ve Border renkleriyle bir dikdörtgen çizer.|
|[CDrawingManager::D rawShadow](#drawshadow)|Dikdörtgen alan için bir gölge çizer.|
|[CDrawingManager:: Fill4ColorsGradient](#fill4colorsgradient)|Dikdörtgen bir alanı iki renk degradelerine doldurur.|
|[CDrawingManager:: FillGradient](#fillgradient)|Dikdörtgen bir alanı belirtilen renk degradeyle doldurur.|
|[CDrawingManager:: FillGradient2](#fillgradient2)|Dikdörtgen bir alanı belirtilen renk degradeyle doldurur. Degradenin renk değişikliğinin yönü de belirtilir.|
|[CDrawingManager:: Grirect](#grayrect)|Bir dikdörtgeni belirtilen gri renkle doldurur.|
|[CDrawingManager:: HighlightRect](#highlightrect)|Dikdörtgen bir alanı vurgular.|
|[CDrawingManager:: HLStoRGB_ONE](#hlstorgb_one)|Bir HLS gösteriminden bir rengi RGB gösterimine dönüştürür.|
|[CDrawingManager:: HLStoRGB_TWO](#hlstorgb_two)|Bir HLS gösteriminden bir rengi RGB gösterimine dönüştürür.|
|[CDrawingManager:: HSVtoRGB](#hsvtorgb)|Bir HSV gösteriminden bir rengi RGB gösterimine dönüştürür.|
|[CDrawingManager:: HuetoRGB](#huetorgb)|Bir ton değerini kırmızı, yeşil veya mavi bileşene dönüştüren yardımcı yöntemi.|
|[CDrawingManager:: MirrorRect](#mirrorrect)|Dikdörtgen bir alanı çevirir.|
|[CDrawingManager::P ıxelalpha](#pixelalpha)|Bir yarı saydam piksel için son rengi belirleyen yardımcı yöntemi.|
|[CDrawingManager::P repareShadowMask](#prepareshadowmask)|Gölge olarak kullanılabilecek bir bit eşlem oluşturur.|
|[CDrawingManager:: RGBtoHSL](#rgbtohsl)|Bir RGB gösteriminden bir rengi HSL gösterimine dönüştürür.|
|[CDrawingManager:: RGBtoHSV](#rgbtohsv)|Bir RGB gösteriminden bir HSV gösterimine bir renk dönüştürür.|
|[CDrawingManager:: Setharfler piksel](#setalphapixel)|Bit eşlemdeki kısmen saydam pikseli gösteren yardımcı yöntemi.|
|[CDrawingManager:: SetPixel](#setpixel)|Bit eşlemdeki tek bir pikseli belirtilen renge değiştiren yardımcı yöntemi.|
|[CDrawingManager:: SmartMixColors](#smartmixcolors)|İki rengi ağırlıklı oranına göre birleştirir.|

## <a name="remarks"></a>Açıklamalar

`CDrawingManager`Sınıfı, gölgeleri, renk degradelerini ve vurgulanan dikdörtgeni çizmek için işlevler sağlar. Ayrıca Alfa karışımı da gerçekleştirir. Bu sınıfı, uygulamanızın kullanıcı arabirimini doğrudan değiştirmek için kullanabilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)<br/>
`CDrawingManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdrawmanager. h

## <a name="cdrawingmanagercdrawingmanager"></a><a name="cdrawingmanager"></a> CDrawingManager:: CDrawingManager

Bir [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) nesnesi oluşturur.

```
CDrawingManager(CDC& dc);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
'ndaki Bir cihaz bağlamına başvuru. , `CDrawingManager` Çizim için bu bağlamı kullanır.

## <a name="cdrawingmanagercreatebitmap_32"></a><a name="createbitmap_32"></a> CDrawingManager:: CreateBitmap_32

Uygulamaların doğrudan yazabilmesi için 32 bitlik bir cihazdan bağımsız bit eşlem (DIB) oluşturur.

```
static HBITMAP __stdcall CreateBitmap_32(
    const CSize& size,
    void** pBits);

static HBITMAP __stdcall CreateBitmap_32(
    HBITMAP bitmap,
    COLORREF clrTransparent = -1);
```

### <a name="parameters"></a>Parametreler

*boyutla*\
'ndaki Bit eşlemin boyutunu gösteren bir [CSize](../../atl-mfc-shared/reference/csize-class.md) parametresi.

*pBits 'ler*\
dışı DIB 'nin bit değerlerinin konumunu alan bir veri işaretçisi işaretçisi.

*biteş*\
Özgün bit eşlem tanıtıcısı

*clrTransparent*\
Orijinal bit eşlemin saydam rengini belirten bir RGB değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa yeni oluşturulan DIB bit eşlemiyle bir tanıtıcı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

DIB bit eşlemi oluşturma hakkında daha fazla bilgi için bkz. [CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibitmap).

## <a name="cdrawingmanagerdrawalpha"></a><a name="drawalpha"></a> CDrawingManager::D Rampapha

Saydam veya yarı saydam piksel olan bit eşlemleri görüntüler.

```cpp
void DrawAlpha(
    CDC* pDstDC,
    const CRect& rectDst,
    CDC* pSrcDC,
    const CRect& rectSrc);
```

### <a name="parameters"></a>Parametreler

*pDstDC*<br/>
'ndaki Hedef için cihaz bağlamına yönelik bir işaretçi.

*rectDst*<br/>
'ndaki Hedef dikdörtgen.

*pSrcDC*<br/>
'ndaki Kaynak için cihaz bağlamına yönelik bir işaretçi.

*rectSrc*<br/>
'ndaki Kaynak dikdörtgeni.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iki bit eşlem için alfa karışımı gerçekleştirir. Alfa Blend hakkında daha fazla bilgi için Windows SDK bkz. [harflerden Blend](/windows/win32/api/wingdi/nf-wingdi-alphablend) .

## <a name="cdrawingmanagerdrawellipse"></a><a name="drawellipse"></a> CDrawingManager::D rawEllipse

Sağlanan Fill ve Border renkleriyle bir elips çizer.

```cpp
void DrawEllipse(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
'ndaki Elips için sınırlayıcı dikdörtgen.

*clrFill*<br/>
'ndaki Bu yöntemin elipsi dolduracak şekilde kullandığı renk.

*clrLine*<br/>
'ndaki Bu yöntemin elips kenarlığı olarak kullandığı renk.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, herhangi bir rengin-1 olarak ayarlanmış olması halinde bir elips çizmeksizin döndürür. Ayrıca, sınırlayıcı dikdörtgenin herhangi bir boyutu 0 ise, elips çizmeksizin de döndürür.

## <a name="cdrawingmanagerdrawgradientring"></a><a name="drawgradientring"></a> CDrawingManager::D Rawgradiing

Bir halka çizer ve renk degradeyle doldurur.

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
'ndaki Gradyan halkasının sınırını belirten bir [CRect](../../atl-mfc-shared/reference/crect-class.md) parametresi.

*colorStart*<br/>
'ndaki Gradyanın ilk rengi.

*Colorson*<br/>
'ndaki Degradenin son rengi.

*colorBorder*<br/>
'ndaki Kenarlığın rengi.

*Naçı*<br/>
'ndaki İlk gradyan çizimi açısını belirten bir parametre. Bu değer 0 ile 360 arasında olmalıdır.

*nWidth*<br/>
'ndaki Halka için kenarlığın genişliği.

*clrFace*<br/>
'ndaki Halka iç kısmının rengi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*Rect* tarafından tanımlanan dikdörtgen en az 5 piksel genişliğinde ve 5 piksel yüksekliğinde olmalıdır.

## <a name="cdrawingmanagerdrawline-cdrawingmanagerdrawlinea"></a><a name="drawline_cdrawingmanager__drawlinea"></a> CDrawingManager::D rawLine, CDrawingManager::D rawLineA

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

*x1*\
'ndaki Satırın başladığı x koordinatı.

*Y1*\
'ndaki Satırın başladığı y koordinatı.

*x2*\
'ndaki Çizginin bittiği x koordinatı.

*Y2*\
'ndaki Çizginin bittiği y koordinatı.

*clrLine*\
'ndaki Çizginin rengi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *clrLine* eşittir-1 olduğunda başarısız olur.

## <a name="cdrawingmanagerdrawrect"></a><a name="drawrect"></a> CDrawingManager::D rawRect

Sağlanan Fill ve Border renkleriyle bir dikdörtgen çizer.

```cpp
void DrawRect(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
'ndaki Dikdörtgenin sınırları.

*clrFill*<br/>
'ndaki Bu yöntemin dikdörtgeni dolduracak şekilde kullandığı renk.

*clrLine*<br/>
'ndaki Bu yöntemin dikdörtgenin kenarlığı için kullandığı renk.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Color-1 olarak ayarlandıysa bir dikdörtgen çizmeden geri döner. Dikdörtgenin herhangi bir boyutu 0 ise de döndürür.

## <a name="cdrawingmanagerdrawshadow"></a><a name="drawshadow"></a> CDrawingManager::D rawShadow

Dikdörtgen alan için bir gölge çizer.

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
'ndaki Uygulamanızdaki dikdörtgen bir alan. Çizim Yöneticisi bu alanın altına bir gölge çizecek.

*nDepth*<br/>
'ndaki Gölgenin genişliği ve yüksekliği.

*ımınparlaklık*<br/>
'ndaki Gölgenin minimum parlaklığı.

*ımaxparlaklık*<br/>
'ndaki Gölgenin maksimum parlaklığı.

*pBmpSaveBottom*<br/>
'ndaki Gölgenin alt bölümünün görüntüsünü içeren bir bit eşlem işaretçisi.

*Pbmpsaverisağ*<br/>
'ndaki Dikdörtgenin sağ tarafında çizilen gölge görüntüsünü içeren bir bit eşlem işaretçisi.

*clrBase*<br/>
'ndaki Gölgenin rengi.

*Parlak gölge*<br/>
'ndaki Gölgenin nasıl çizildiğini gösteren bir Boolean parametresi. En *parlamsa* `TRUE` , `DrawShadow` dikdörtgenin sağ tarafında bir gölge çizer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*PBmpSaveBottom* ve *Pbmpsaveriright*parametrelerini kullanarak aşağıdan ve sağ gölgelerdeki iki geçerli bit eşlem sağlayabilirsiniz. Bu [CBitmap](../../mfc/reference/cbitmap-class.md) nesnelerinde eklı bir GDI nesnesi varsa, `DrawShadow` Bu bit eşlemler gölgeler olarak kullanacaktır. `CBitmap`Parametrelerde eklenmiş BIR GDI nesnesi yoksa, `DrawShadow` Gölgeyi çizer ve bit eşlemleri parametrelere ekler. Sonraki çağrılarında `DrawShadow` , çizim işlemini hızlandırmak için bu bit eşlemleri sağlayabilirsiniz. Sınıf ve GDI nesneleri hakkında daha fazla bilgi için `CBitmap` bkz. [grafik nesneleri](../../mfc/graphic-objects.md).

Bu parametrelerden biri ise `NULL` `DrawShadow` otomatik olarak gölgeyi çizecek.

En *PARLAMSıNı* false olarak ayarlarsanız, gölge dikdörtgen alanının altına ve soluna çizilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının yönteminin nasıl kullanılacağını gösterir `DrawShadow` `CDrawingManager` . Bu kod parçacığı, [Prop Sheet tanıtım örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]

## <a name="cdrawingmanagerfill4colorsgradient"></a><a name="fill4colorsgradient"></a> CDrawingManager:: Fill4ColorsGradient

Dikdörtgen bir alanı iki renk degradelerine doldurur.

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
'ndaki Doldurulacak dikdörtgen.

*colorStart1*<br/>
'ndaki İlk renk gradyanının başlangıç rengi.

*colorFinish1*<br/>
'ndaki İlk renk gradyanının son rengi.

*colorStart2*<br/>
'ndaki İkinci renk gradyanının başlangıç rengi.

*colorFinish2*<br/>
'ndaki İkinci renk gradyanının son rengi.

*bHorz*<br/>
'ndaki `Fill4ColorsGradient` Renklerin yatay veya dikey degradeyle ilgili olduğunu belirten bir Boole parametresi. TRUE, yatay degradeyi gösterir.

*Nyüzde*<br/>
'ndaki 0-100 'den bir tamsayı. Bu değer, ilk renk degradesiyle doldurulacak dikdörtgenin yüzdesini gösterir.

### <a name="remarks"></a>Açıklamalar

Bir dikdörtgen iki renk gradyanına göre dolduğunda, *bHorz*değerine bağlı olarak, bunlar birbirlerinin üzerinde veya yanında bulunur. Her renk gradyanı, [CDrawingManager:: FillGradient](#fillgradient)yöntemiyle bağımsız olarak hesaplanır.

Bu yöntem, *nPercentage* 0 ' dan küçükse veya 100 ' den büyükse bir onaylama hatası oluşturur.

## <a name="cdrawingmanagerfillgradient"></a><a name="fillgradient"></a> CDrawingManager:: FillGradient

Dikdörtgen bir alanı belirtilen renk degradeyle doldurur.

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
'ndaki Doldurulacak dikdörtgen alan.

*colorStart*<br/>
'ndaki Gradyanın ilk rengi.

*Colorson*<br/>
'ndaki Degradenin son rengi.

*bHorz*<br/>
'ndaki `FillGradient` Yatay veya dikey gradyan çizip çizmeyeceğini belirten bir Boolean parametresi.

*nStartFlatPercentage*<br/>
'ndaki `FillGradient` Degradenin *başlamasından önce colorStart* ile başlayan dikdörtgenin yüzdesi.

*Nendyatayyüzdesi*<br/>
'ndaki `FillGradient` Degradeyi tamamladıktan sonra *colorbitle* birlikte dolduran dikdörtgenin yüzdesi.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının yönteminin nasıl kullanılacağını gösterir `FillGradient` `CDrawingManager` . Bu kod parçacığı, [MS Office 2007 demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]

## <a name="cdrawingmanagerfillgradient2"></a><a name="fillgradient2"></a> CDrawingManager:: FillGradient2

Dikdörtgen bir alanı belirtilen renk degradeyle doldurur.

```cpp
void FillGradient2 (
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    int nAngle = 0);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
'ndaki Doldurulacak dikdörtgen alan.

*colorStart*<br/>
'ndaki Gradyanın ilk rengi.

*Colorson*<br/>
'ndaki Degradenin son rengi.

*Naçı*<br/>
'ndaki 0 ile 360 arasında bir tamsayı. Bu parametre, renk gradyanının yönünü belirtir.

### <a name="remarks"></a>Açıklamalar

Renk gradyanının yönünü belirtmek için *naçısını* kullanın. Renk gradyanının yönünü belirttiğinizde, renk gradyanının nerede başlayacağını de belirtirsiniz. *Naçılı* için 0 değeri, degradenin dikdörtgenin en üstünden başladığını gösterir. *Naçılı* arttıkça, degradenin başlangıç konumu, açıya göre saat yönünde bir yönde gider.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının yönteminin nasıl kullanılacağını gösterir `FillGradient2` `CDrawingManager` . Bu kod parçacığı, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]

## <a name="cdrawingmanagergrayrect"></a><a name="grayrect"></a> CDrawingManager:: Grirect

Bir dikdörtgeni belirtilen gri renkle doldurur.

```
BOOL GrayRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    COLORREF clrDisabled = (COLORREF)-1);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
'ndaki Doldurulacak dikdörtgen alan.

*Nyüzde*<br/>
'ndaki Dikdörtgende istediğiniz gri yüzdesi.

*clrTransparent*<br/>
'ndaki Saydam renk.

*clrDisabled*<br/>
'ndaki *NPercentage* değeri-1 olarak ayarlandığında, bu yöntemin de serbest doyma için kullandığı renk.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

*NPercentage*parametresi için, daha küçük bir değer daha koyu bir renk gösterir.

*NPercentage* için maksimum değer 200 ' dir. 200 değerinden büyük bir değer dikdörtgenin görünümünü değiştirmez. Değer-1 ise, bu yöntem dikdörtgenin doygunluğunu sınırlamak için *clrDisabled* kullanır.

## <a name="cdrawingmanagerhighlightrect"></a><a name="highlightrect"></a> CDrawingManager:: HighlightRect

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
'ndaki Vurgulanacak dikdörtgen bir alan.

*Nyüzde*<br/>
'ndaki Vurgulamanın saydam olduğunu gösteren bir yüzde.

*clrTransparent*<br/>
'ndaki Saydam renk.

*ntoleransı*<br/>
'ndaki Renk toleransını gösteren 0 ile 255 arasında bir tamsayı.

*clrBlend*<br/>
'ndaki Karıştırma için temel renk.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

*NPercentage* değeri 0 ile 99 arasında ise `HighlightRect` Alfa karıştırma algoritmasını kullanır. Alfa karıştırma hakkında daha fazla bilgi için bkz. [Alfa karıştırma çizgileri ve dolguları](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills). Eğer *nPercentage* değeri-1 ise, bu yöntem varsayılan vurgulama düzeyini kullanır. Eğer *nPercentage* 100 ise, bu yöntem hiçbir şey yapmaz ve true değerini döndürür.

Yöntemi, dikdörtgen alanın vurgulanmasını öğrenmek için *ntoleransı* parametresini kullanır. Dikdörtgeni vurgulamak için, uygulamanızın arka plan rengi ile *clrTransparent* arasındaki fark her bir renk bileşeni (kırmızı, yeşil ve mavi) Için *ntoleranstan* az olmalıdır.

## <a name="cdrawingmanagerhlstorgb_one"></a><a name="hlstorgb_one"></a> CDrawingManager:: HLStoRGB_ONE

Bir HLS gösteriminden bir rengi RGB gösterimine dönüştürür.

```
static COLORREF __stdcall HLStoRGB_ONE(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
'ndaki Rengin tonunu temsil eden 0 ile 1 arasında bir sayı.

*L*<br/>
'ndaki Rengin parlaklığını gösteren 0 ile 1 arasında bir sayı.

*S*<br/>
'ndaki Renge yönelik doygunluğu gösteren 0 ile 1 arasında bir sayı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen HLS renginin RGB temsili.

### <a name="remarks"></a>Açıklamalar

Bir renk HSV (ton, doygunluk ve değer), HSL (ton, doygunluk, ve parlaklık) ya da RGB (kırmızı, yeşil ve mavi) olarak temsil edilebilir. Rengin farklı gösterimleri hakkında daha fazla bilgi için bkz. [Color](/windows/win32/uxguide/vis-color).

Bu yöntem ve `CDrawingManager::HLStoRGB_TWO` yöntemi aynı işlemi gerçekleştirir, ancak *H* parametresi için farklı değerler gerektirir. Bu yöntemde *H* , dairenin bir yüzdesidir. `CDrawingManager::HLStoRGB_TWO`Yönteminde, *H* , her ikisi de Red temsil eden 0 ile 360 arasında bir derece değeridir. Örneğin, ile `HLStoRGB_ONE` *H* için 0,25 değeri, 90 değerine eşdeğerdir `HLStoRGB_TWO` .

## <a name="cdrawingmanagerhlstorgb_two"></a><a name="hlstorgb_two"></a> CDrawingManager:: HLStoRGB_TWO

Bir HLS gösteriminden bir rengi RGB gösterimine dönüştürür.

```
static COLORREF __stdcall HLStoRGB_TWO(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
'ndaki Renk için tonu temsil eden 0 ile 360 arasında bir sayı.

*L*<br/>
'ndaki Rengin parlaklığını gösteren 0 ile 1 arasında bir sayı.

*S*<br/>
'ndaki Renge yönelik doygunluğu gösteren 0 ile 1 arasında bir sayı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen HLS renginin RGB temsili.

### <a name="remarks"></a>Açıklamalar

Bir renk HSV (ton, doygunluk ve değer), HSL (ton, doygunluk, ve parlaklık) ya da RGB (kırmızı, yeşil ve mavi) olarak temsil edilebilir. Rengin farklı gösterimleri hakkında daha fazla bilgi için bkz. [Color](/windows/win32/uxguide/vis-color).

Bu yöntem ve [CDrawingManager:: HLStoRGB_ONE](#hlstorgb_one) yöntemi aynı işlemi gerçekleştirir, ancak *H* parametresi için farklı değerler gerektirir. Bu yöntemde *H* , her ikisi de Red temsil eden 0 ile 360 arasında bir derece değeridir. [CDrawingManager:: HLStoRGB_ONE](#hlstorgb_one) yönteminde *H* , dairenin bir yüzdesidir. Örneğin, ile `HLStoRGB_ONE` *H* için 0,25 değeri, 90 değerine eşdeğerdir `HLStoRGB_TWO` .

## <a name="cdrawingmanagerhsvtorgb"></a><a name="hsvtorgb"></a> CDrawingManager:: HSVtoRGB

Bir HSV gösteriminden bir rengi RGB gösterimine dönüştürür.

```
static COLORREF __stdcall HSVtoRGB(
    double H,
    double S,
    double V);
```

### <a name="parameters"></a>Parametreler

*Olsun*\
'ndaki Rengin tonunu gösteren 0 ile 360 arasında bir sayı.

*Malar*\
'ndaki Renge yönelik doygunluğu gösteren 0 ile 1 arasında bir sayı.

*Yönetim*\
'ndaki Rengin değerini gösteren 0 ile 1 arasında bir sayı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen HSV renginin RGB temsili.

### <a name="remarks"></a>Açıklamalar

Bir renk HSV (ton, doygunluk ve değer), HSL (ton, doygunluk, ve parlaklık) ya da RGB (kırmızı, yeşil ve mavi) olarak temsil edilebilir. Rengin farklı gösterimleri hakkında daha fazla bilgi için bkz. [Color](/windows/win32/uxguide/vis-color).

## <a name="cdrawingmanagerhuetorgb"></a><a name="huetorgb"></a> CDrawingManager:: HuetoRGB

Bir ton değerini kırmızı, yeşil veya mavi bir bileşene dönüştürür.

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

*M1*<br/>
'ndaki Bkz. açıklamalar.

*m2*<br/>
'ndaki Bkz. açıklamalar.

*olsun*<br/>
'ndaki Bkz. açıklamalar.

*rm1*<br/>
'ndaki Bkz. açıklamalar.

*rm2*<br/>
'ndaki Bkz. açıklamalar.

*RH*<br/>
'ndaki Bkz. açıklamalar.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen ton için tek bir kırmızı, yeşil veya mavi bileşen.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CDrawingManager` BIR HSV veya HSL gösteriminde bir rengin tek tek kırmızı, yeşil ve mavi bileşenlerini hesaplamak için sınıfın kullandığı yardımcı bir yöntemdir. Bu yöntem, programcı tarafından doğrudan çağrılacak şekilde tasarlanmamıştır. Giriş parametreleri, dönüştürme algoritmasına bağlı değerlerdir.

Bir HSV veya HSL rengini bir RGB gösterimine dönüştürmek için aşağıdaki yöntemlerden birini çağırın:

- [CDrawingManager:: HSVtoRGB](#hsvtorgb)

- [CDrawingManager:: HLStoRGB_ONE](#hlstorgb_one)

- [CDrawingManager:: HLStoRGB_TWO](#hlstorgb_two)

## <a name="cdrawingmanagermirrorrect"></a><a name="mirrorrect"></a> CDrawingManager:: MirrorRect

Dikdörtgen bir alanı çevirir.

```cpp
void MirrorRect(
    CRect rect,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
'ndaki Ters çevrilecek alanın sınırlayıcı dikdörtgeni.

*bHorz*<br/>
'ndaki Dikdörtgenin yatay mı yoksa dikey mi çevrileceğini belirten bir Boole parametresi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, sınıf tarafından sahip olunan cihaz bağlamının herhangi bir alanını çevirebilir `CDrawingManager` . *BHorz* doğru olarak ayarlandıysa, bu yöntem alanı yatay olarak çevirir. Aksi takdirde, alanı dikey olarak çevirir.

## <a name="cdrawingmanagerpixelalpha"></a><a name="pixelalpha"></a> CDrawingManager::P ıxelalpha

Yarı saydam piksel için son rengi hesaplar.

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
'ndaki Pikselin ilk rengi.

*yüzdeyi*<br/>
'ndaki Saydamlığın yüzdesini temsil eden 0 ile 100 arasında bir sayı. 100 değeri, ilk rengin tamamen saydam olduğunu gösterir.

*Yüztr*<br/>
'ndaki Kırmızı bileşen için saydamlık yüzdesini temsil eden 0 ile 100 arasında bir sayı.

*percentG*<br/>
'ndaki Yeşil bileşen için saydamlık yüzdesini temsil eden 0 ile 100 arasında bir sayı.

*Yüztb*<br/>
'ndaki Mavi bileşenin saydamlık yüzdesini temsil eden 0 ile 100 arasında bir sayı.

*dstPixel*<br/>
'ndaki Pikselin taban rengi.

### <a name="return-value"></a>Dönüş Değeri

Yarı saydam piksel için son renk.

### <a name="remarks"></a>Açıklamalar

Bu, yarı saydam bit eşlemler renklendirmesi için yardımcı sınıftır ve doğrudan programcı tarafından çağrılacak şekilde tasarlanmamıştır.

*DstPixel*içeren yöntemin sürümünü kullandığınızda, son renk *dstPixel* ve *srcPixel*'in bir birleşimidir. *SrcPixel* rengi, *dstPixel*'in temel rengi üzerinde kısmen saydam bir renktir.

## <a name="cdrawingmanagerprepareshadowmask"></a><a name="prepareshadowmask"></a> CDrawingManager::P repareShadowMask

Gölge olarak kullanılabilecek bir bit eşlem oluşturur.

```
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,
    COLORREF clrBase,
    int iMinBrightness = 0,
    int iMaxBrightness = 100);
```

### <a name="parameters"></a>Parametreler

*nDepth*<br/>
'ndaki Gölgenin genişliği ve yüksekliği.

*clrBase*<br/>
'ndaki Gölgenin rengi.

*ımınparlaklık*<br/>
'ndaki Gölgenin minimum parlaklığı.

*ımaxparlaklık*<br/>
'ndaki Gölgenin maksimum parlaklığı.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa oluşturulan bit eşlem için bir tanıtıcı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Eğer *nDepth* değeri 0 olarak ayarlandıysa, bu yöntem çıkar ve null döndürür. *NDepth* 3 ' ten küçükse, gölgenin genişliği ve yüksekliği 3 piksel olarak ayarlanır.

## <a name="cdrawingmanagerrgbtohsl"></a><a name="rgbtohsl"></a> CDrawingManager:: RGBtoHSL

Kırmızı, yeşil ve mavi (RGB) gösteriminden bir rengi bir ton, doygunluk ve açıklık (HSL) gösterimine dönüştürür.

```
static void __stdcall RGBtoHSL(
    COLORREF rgb,
    double* H,
    double* S,
    double* L);
```

### <a name="parameters"></a>Parametreler

*'ye*\
'ndaki RGB değerlerinde renk.

*Olsun*\
dışı Yöntemin renk için tonu depoladığı bir Double için işaretçi.

*Malar*\
dışı Yöntemin, renk için doygunluğu depoladığı bir Double işaretçisi.

*Girişindeki*\
dışı Yöntemin rengin açıklık sakladığı bir Double için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir renk HSV (ton, doygunluk ve değer), HSL (ton, doygunluk, ve parlaklık) ya da RGB (kırmızı, yeşil ve mavi) olarak temsil edilebilir. Rengin farklı gösterimleri hakkında daha fazla bilgi için bkz. [Color](/windows/win32/uxguide/vis-color).

*H* için döndürülen değer 0 ile 1 arasında, her ikisi de 0 ve 1 arasında bir kesir olarak temsil edilir. *S* ve *L* için döndürülen değerler 0 ile 1 arasında sayılardır.

## <a name="cdrawingmanagerrgbtohsv"></a><a name="rgbtohsv"></a> CDrawingManager:: RGBtoHSV

Bir RGB gösteriminden bir HSV gösterimine bir renk dönüştürür.

```
static void __stdcall RGBtoHSV(
    COLORREF rgb,
    double* H,
    double* S,
    double* V);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
'ndaki Bir RGB gösteriminde dönüştürülecek renk.

*H*<br/>
dışı Bu yöntemin renk için elde edilen tonu depoladığı bir Double işaretçisi.

*S*<br/>
dışı Bu yöntemin, renk için elde edilen doygunluğu depoladığı bir Double işaretçisi.

*Yönetim*<br/>
dışı Bu yöntemin, renk için elde edilen değeri depoladığı bir Double işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir renk HSV (ton, doygunluk ve değer), HSL (ton, doygunluk, ve parlaklık) ya da RGB (kırmızı, yeşil ve mavi) olarak temsil edilebilir. Rengin farklı gösterimleri hakkında daha fazla bilgi için bkz. [Color](/windows/win32/uxguide/vis-color).

*H* için döndürülen değer 0 ile 360 arasında her ikisi de 0 ve 360 ' nin kırmızı olduğunu belirten bir sayıdır. *S* ve *V* için dönüş değerleri 0 ile 1 arasında sayılardır.

## <a name="cdrawingmanagersetalphapixel"></a><a name="setalphapixel"></a> CDrawingManager:: Setharfler piksel

Bit eşlemdeki saydam bir piksel renkler.

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

*pBits 'ler*<br/>
'ndaki Bit eşlem için bit değerlerine yönelik bir işaretçi.

*Rect*<br/>
'ndaki Uygulamanızdaki dikdörtgen bir alan. Çizim Yöneticisi bu alanın sağ altına ve sağına bir gölge çizer.

*x*<br/>
'ndaki Pikselin renge yatay koordinatı.

*Iz*<br/>
'ndaki Pikselin renge göre dikey koordinatı.

*yüzdeyi*<br/>
'ndaki Saydamlığın yüzdesi.

*iShadowSize*<br/>
'ndaki Gölgenin genişliği ve yüksekliği.

*clrBase*<br/>
'ndaki Gölgenin rengi.

*bIsRight*<br/>
'ndaki Hangi pikselin renge işaret edildiğini belirten bir Boole parametresi. Daha fazla bilgi için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CDrawingManager::D rawShadow](#drawshadow) yöntemi tarafından kullanılan bir yardımcı yöntemdir. Bunun yerine bir gölge çizmek istiyorsanız, çağrısı yapmanız önerilir `CDrawingManager::DrawShadow` .

*Bıright* doğru olarak ayarlandıysa, rengin piksel sağ kenarından *x* piksel olarak *ölçülür.* YANLıŞ ise, rengin piksel sol kenarından *x* piksel *ölçülür.*

## <a name="cdrawingmanagersetpixel"></a><a name="setpixel"></a> CDrawingManager:: SetPixel

Bit eşlemdeki tek bir pikseli belirtilen renge dönüştürür.

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

*pBits 'ler*\
'ndaki Bit eşlemin bit değerlerine yönelik bir işaretçi.

*yazmaç*\
'ndaki Bit eşlemin toplam genişliği.

*lı*\
'ndaki Bit eşlemin toplam yüksekliği.

*sayı*\
'ndaki Bit eşlemdeki, değiştirilecek pikselin x koordinatı.

*Iz*\
'ndaki Bit eşlemdeki, değiştirilecek pikselin y koordinatı.

*Renk*\
'ndaki Sağlanan koordinatlar tarafından tanımlanan pikselin yeni rengi.

## <a name="cdrawingmanagersmartmixcolors"></a><a name="smartmixcolors"></a> CDrawingManager:: SmartMixColors

İki rengi ağırlıklı oranına göre birleştirir.

```
static COLORREF __stdcall SmartMixColors(
    COLORREF color1,
    COLORREF color2,
    double dblLumRatio = 1.,
    int k1 = 1,
    int k2 = 1);
```

### <a name="parameters"></a>Parametreler

*color1*\
'ndaki Karıştırılacak ilk renk.

*color2*\
'ndaki Karıştırılacak ikinci renk.

*dblLumRatio*\
'ndaki Yeni rengin parlaklık oranı. `SmartMixColors` son rengi belirlemekten önce, karışık rengin parlaklığını bu orandan çarpar.

*K1*\
'ndaki İlk rengin ağırlıklı oranı.

*K2*\
'ndaki İkinci rengin ağırlıklı oranı.

### <a name="return-value"></a>Dönüş Değeri

Sağlanan renklerin ağırlıklı karışımını temsil eden bir renk.

### <a name="remarks"></a>Açıklamalar

*K1* veya *K2* sıfırdan küçükse bu yöntem hata ile başarısız olur. Bu parametrelerin her ikisi de 0 olarak ayarlandıysa, yöntemi döndürür `RGB(0, 0, 0)` .

Ağırlıklı oran şu formül ile hesaplanır: (color1 \* K1 + COLOR2 \* K2)/(K1 + K2). Ağırlıklı oran saptandıktan sonra yöntem, karışık rengin parlaklığını hesaplar. Daha sonra, parlaklığı *dblLumRatio*ile çarpar. Değer 1,0 ' den büyükse, yöntemi karışık rengin parlaklığını yeni değere ayarlar. Aksi takdirde, parlaklık 1,0 olarak ayarlanır.

## <a name="cdrawingmanagerdrawrotated"></a><a name="drawrotated"></a> CDrawingManager::D Rawdöndürülmüş

Verilen dikdörtgen içindeki kaynak DC içeriğini 90 derece döndürür.

```cpp
void DrawRotated(
    CRect rectDest,
    CDC& dcSrc,
    BOOL bClockWise);
```

### <a name="parameters"></a>Parametreler

*rectDest*<br/>
Hedef dikdörtgen.

*dcSrc*<br/>
Kaynak cihaz bağlamı.

*bClockWise*<br/>
TRUE, Döndür + 90 derece; FALSE, döndürme-90 derece gösterir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
