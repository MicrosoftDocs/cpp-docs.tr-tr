---
title: "CDrawingManager sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73b8adbff021a179f3bd3185fa85ee18c84a441a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdrawingmanager-class"></a>CDrawingManager sınıfı
`CDrawingManager` Sınıfı karmaşık çizim algoritmaları uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDrawingManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|Oluşturan bir `CDrawingManager` nesnesi.|  
|`CDrawingManager::~CDrawingManager`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|Uygulamalar için doğrudan yazabilen bir 32 bit CİHAZDAN bağımsız bit eşlem (DIB) oluşturur.|  
|[CDrawingManager::DrawAlpha](#drawalpha)|Saydam veya yarı saydam piksel sahip bit eşlemler görüntüler.|  
|[CDrawingManager::DrawRotated](#drawrotated)|Bir kaynak tarafından verilen dikdörtgen 90 derece +/-DC içeriğini döndürür|  
|[CDrawingManager::DrawEllipse](#drawellipse)|Elips sağlanan dolgu ve kenarlık renklerle çizer.|  
|[CDrawingManager::DrawGradientRing](#drawgradientring)|Halka çizer ve renk gradyan ile doldurur.|  
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|Bir çizgi çizer.|  
|[CDrawingManager::DrawRect](#drawrect)|Sağlanan dolgu ve kenarlık renklerle bir dikdörtgen çizer.|  
|[CDrawingManager::DrawShadow](#drawshadow)|Dikdörtgen bir gölgeyi çizer.|  
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|Dikdörtgen bir iki rengi gradyanlar ile doldurur.|  
|[CDrawingManager::FillGradient](#fillgradient)|Dikdörtgen bir belirtilen renk gradyan ile doldurur.|  
|[CDrawingManager::FillGradient2](#fillgradient2)|Dikdörtgen bir belirtilen renk gradyan ile doldurur. Gradyan rengi değiştirme yönünü da belirtilmiş.|  
|[CDrawingManager::GrayRect](#grayrect)|Dikdörtgene belirtilen bir gri renge ile doldurur.|  
|[CDrawingManager::HighlightRect](#highlightrect)|Dikdörtgen bir vurgular.|  
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|Bir renk HLS gösteriminden bir RGB gösterimine dönüştürür.|  
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|Bir renk HLS gösteriminden bir RGB gösterimine dönüştürür.|  
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|Bir renk HSV gösteriminden bir RGB gösterimine dönüştürür.|  
|[CDrawingManager::HuetoRGB](#huetorgb)|Kırmızı, yeşil veya mavi bileşenine ton değeri dönüştürür yardımcı yöntemi.|  
|[CDrawingManager::MirrorRect](#mirrorrect)|Dikdörtgen bir çevirir.|  
|[CDrawingManager::PixelAlpha](#pixelalpha)|Yarı saydam piksel son rengini belirler yardımcı yöntemi.|  
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|Gölge kullanılabilir bir bit eşlem oluşturur.|  
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|Bir renk RGB gösteriminden bir HSL gösterimine dönüştürür.|  
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|Bir renk RGB gösteriminden bir HSV gösterimine dönüştürür.|  
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|Bir bit eşlem kısmen saydam bir piksel renkleri yardımcı yöntemi.|  
|[CDrawingManager::SetPixel](#setpixel)|Bir tek pikselli bir bit eşlem için belirtilen rengi değişir yardımcı yöntemi.|  
|[CDrawingManager::SmartMixColors](#smartmixcolors)|İki renkten bir ağırlıklı oranını göre birleştirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDrawingManager` Sınıfı gölge, renk gradyan ve vurgulanan dikdörtgenler çizme işlevleri sağlar. Alfa karıştırma gerçekleştirir. Bu sınıf doğrudan uygulama kullanıcı Arabirimi değiştirmek için kullanabilirsiniz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
 `CDrawingManager`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdrawmanager.h  
  
##  <a name="cdrawingmanager"></a>CDrawingManager::CDrawingManager  
 Oluşturan bir [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) nesnesi.  
  
```  
CDrawingManager(CDC& dc);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dc`  
 Bir cihaz bağlamı referansı. `CDrawingManager` Bu bağlamda çizim için kullanır.  
  
##  <a name="createbitmap_32"></a>CDrawingManager::CreateBitmap_32  
 Uygulamalar için doğrudan yazabilen bir 32 bit CİHAZDAN bağımsız bit eşlem (DIB) oluşturur.  
  
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
|[in]`size`|A [CSize](../../atl-mfc-shared/reference/csize-class.md) bit eşlem boyutunu gösterir parametresi.|  
|[out]`pBits`|Bir işaretçi DIB'ın yerini alan bir veri işaretçi değerleri bit.|  
|`bitmap`|Özgün bit eşlem için bir tanıtıcı|  
|`clrTransparent`|Özgün bit eşlem saydam rengini belirten bir RGB değeri.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa yeni oluşturulan DIB bit eşlem için bir tanıtıcı; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 DIB bit eşlem oluşturma hakkında daha fazla bilgi için bkz: [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183491).  
  
##  <a name="drawalpha"></a>CDrawingManager::DrawAlpha  
 Saydam veya yarı saydam piksel sahip bit eşlemler görüntüler.  
  
```  
void DrawAlpha(
    CDC* pDstDC,  
    const CRect& rectDst,  
    CDC* pSrcDC,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDstDC`  
 Hedef cihaz bağlamı için bir işaretçi.  
  
 [in]`rectDst`  
 Hedef dikdörtgen.  
  
 [in]`pSrcDC`  
 Kaynağı için cihaz bağlamı için bir işaretçi.  
  
 [in]`rectSrc`  
 Kaynak dikdörtgen.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için iki bit eşlemler Alfa karışım gerçekleştirir. Alfa karıştırma hakkında daha fazla bilgi için bkz: [AlphaBlend](http://msdn.microsoft.com/library/windows/desktop/dd183351) Windows SDK'sındaki.  
  
##  <a name="drawellipse"></a>CDrawingManager::DrawEllipse  
 Elips sağlanan dolgu ve kenarlık renklerle çizer.  
  
```  
void DrawEllipse(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 Elips sınırlayıcı dikdörtgenini.  
  
 [in]`clrFill`  
 Renk elips doldurmak için bu yöntemi kullanır.  
  
 [in]`clrLine`  
 Renk bu yöntem Elips kenarlık olarak kullanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, her iki renkten -1 olarak ayarlanırsa elips çizme olmadan döndürür. Sınırlayıcı dikdörtgenini ya da boyutunun 0 ise elips çizme olmadan döndürür.  
  
##  <a name="drawgradientring"></a>CDrawingManager::DrawGradientRing  
 Halka çizer ve renk gradyan ile doldurur.  
  
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
 [in]`rect`  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) gradyan halkası sınır belirten parametre.  
  
 [in]`colorStart`  
 Geçişin ilk rengi.  
  
 [in]`colorFinish`  
 Geçişin son rengi.  
  
 [in]`colorBorder`  
 Kenarlığın rengi.  
  
 [in]`nAngle`  
 İlk gradyan çizim açı belirten bir parametre. Bu değer, 0-360 arasında olmalıdır.  
  
 [in]`nWidth`  
 Halka kenarlığın kalınlığı.  
  
 [in]`clrFace`  
 İç halkanın rengi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından tanımlanan dikdörtgen `rect` en az 5 piksel genişliğinde ve 5 pikselden yüksek olması gerekir.  
  
##  <a name="drawline_cdrawingmanager__drawlinea"></a>CDrawingManager::DrawLine, CDrawingManager::DrawLineA  
 Bir çizgi çizer.  
  
```  
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
|[in]`x1`|Satır başladığı x koordinatı.|  
|[in]`y1`|Satır başladığı y koordinatı.|  
|[in]`x2`|Satır sona ereceği x koordinatı.|  
|[in]`y2`|Satır sona ereceği y koordinatı.|  
|[in]`clrLine`|Çizginin rengi.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem başarısız olursa `clrLine` -1'e eşittir.  
  
##  <a name="drawrect"></a>CDrawingManager::DrawRect  
 Sağlanan dolgu ve kenarlık renklerle bir dikdörtgen çizer.  
  
```  
void DrawRect(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 Dikdörtgen sınırları.  
  
 [in]`clrFill`  
 Renk dikdörtgen doldurmak için bu yöntemi kullanır.  
  
 [in]`clrLine`  
 Renk Dikdörtgen kenarlık için bu yöntemi kullanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, her iki renkten -1 olarak ayarlanırsa bir dikdörtgen çizme olmadan döndürür. Ayrıca, her iki dikdörtgen boyutunun 0 olup olmadığını döndürür.  
  
##  <a name="drawshadow"></a>CDrawingManager::DrawShadow  
 Dikdörtgen bir gölgeyi çizer.  
  
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
 [in]`rect`  
 Dikdörtgen bir uygulamanızda. Çizim Yöneticisi gölge altındaki bu alanı çizer.  
  
 [in]`nDepth`  
 Genişlik ve yükseklik gölgenin.  
  
 [in]`iMinBrightness`  
 Gölge minimum parlaklığını.  
  
 [in]`iMaxBrightness`  
 Gölge maksimum parlaklığını.  
  
 [in]`pBmpSaveBottom`  
 Gölge alt kısmı için görüntüsünü içeren bir bit eşlem için bir işaretçi.  
  
 [in]`pBmpSaveRight`  
 Dikdörtgen sağ tarafta çizilmiş gölge görüntüsünü içeren bir bit eşlem için bir işaretçi.  
  
 [in]`clrBase`  
 Gölge rengi.  
  
 [in]`bRightShadow`  
 Gölge nasıl çizilir gösteren Boole parametresi. Varsa `bRightShadow` olan `TRUE`, `DrawShadow` dikdörtgen sağ tarafta bir gölge çizer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametreleri kullanarak alt ve sağ gölge için iki geçerli bit eşlemler sağlayabilirsiniz `pBmpSaveBottom` ve `pBmpSaveRight`. Bu, [CBitmap](../../mfc/reference/cbitmap-class.md) nesneler sahip ekli GDI nesneyi `DrawShadow` bu bit eşlemler gölgeleri kullanır. Varsa `CBitmap` parametreleri ekli GDI nesneyi yok `DrawShadow` gölge çizer ve bit eşlemler parametrelerini ekler. Gelecekte çağrıları `DrawShadow`, çizim işlemi hızlandırmak için bu bit eşlemler sağlayabilir. Hakkında daha fazla bilgi için `CBitmap` sınıfı ve bkz GDI nesneleri [grafik nesneleri](../../mfc/graphic-objects.md).  
  
 Bu parametrelerden birini ise `NULL`, `DrawShadow` gölge otomatik olarak çizer.  
  
 Ayarlarsanız `bRightShadow` için `FALSE`, gölge altında ve dikdörtgen solundaki çizileceğini.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `DrawShadow` yöntemi `CDrawingManager` sınıfı. Bu kod parçacığını parçası olan [Prop sayfası gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]  
  
##  <a name="fill4colorsgradient"></a>CDrawingManager::Fill4ColorsGradient  
 Dikdörtgen bir iki rengi gradyanlar ile doldurur.  
  
```  
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
 [in]`rect`  
 Doldurmak için dikdörtgen.  
  
 [in]`colorStart1`  
 İlk Renk Gradyan ilk rengi.  
  
 [in]`colorFinish1`  
 İlk renk geçişin son rengi.  
  
 [in]`colorStart2`  
 İkinci renk gradyan ilk rengi.  
  
 [in]`colorFinish2`  
 İkinci renk geçişin son rengi.  
  
 [in]`bHorz`  
 Gösteren bir Boolean parametresiyle olup olmadığını `Fill4ColorsGradient` yatay veya dikey gradyan renkleri. `TRUE`yatay bir gradyan gösterir.  
  
 [in]`nPercentage`  
 0-100 arasında bir tamsayı. Bu değer ilk renk gradyan ile doldurmak için dikdörtgen yüzdesini gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Birbirine yukarıda bulunduğu veya değerine bağlı olarak birbirleriyle, sonraki iki rengi gradyanlar ile bir dikdörtgen dolduğunda olmalarından `bHorz`. Her renk gradyan yöntemiyle bağımsız olarak hesaplanır [CDrawingManager::FillGradient](#fillgradient).  
  
 Bu yöntem, bir onaylama işlemi hatasına oluşturur `nPercentage` 0'den küçük ya da 100'den fazla olan.  
  
##  <a name="fillgradient"></a>CDrawingManager::FillGradient  
 Dikdörtgen bir belirtilen renk gradyan ile doldurur.  
  
```  
void FillGradient(
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    BOOL bHorz = TRUE,  
    int nStartFlatPercentage = 0,  
    int nEndFlatPercentage = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 Doldurmak için dikdörtgen.  
  
 [in]`colorStart`  
 Geçişin ilk rengi.  
  
 [in]`colorFinish`  
 Geçişin son rengi.  
  
 [in]`bHorz`  
 Belirten bir Boolean parametresiyle olup olmadığını `FillGradient` yatay veya dikey gradyan çizin.  
  
 [in]`nStartFlatPercentage`  
 Dikdörtgen yüzdesi, `FillGradient` doldurur `colorStart` gradyan başlamadan önce.  
  
 [in]`nEndFlatPercentage`  
 Dikdörtgen yüzdesi, `FillGradient` doldurur `colorFinish` gradyan bittikten sonra.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `FillGradient` yöntemi `CDrawingManager` sınıfı. Bu kod parçacığını parçası olan [MS Office 2007 Demo örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]  
  
##  <a name="fillgradient2"></a>CDrawingManager::FillGradient2  
 Dikdörtgen bir belirtilen renk gradyan ile doldurur.  
  
```  
void FillGradient2 (
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    int nAngle = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 Doldurmak için dikdörtgen.  
  
 [in]`colorStart`  
 Geçişin ilk rengi.  
  
 [in]`colorFinish`  
 Geçişin son rengi.  
  
 [in]`nAngle`  
 0 ile 360 arasında bir tamsayı. Bu parametre renk gradyan yönünü belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `nAngle` renk gradyan yönünü belirtmek için. Renk Gradyan yönünü belirttiğinizde, renk gradyan başladığı de belirtin. İçin 0 değerini `nAngle` geçişin başladığını dikdörtgenin üst kısmından gösterir. Olarak `nAngle` artırır, başlangıç konumu için gradyan açısını dayalı yönünün yönde taşır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `FillGradient2` yöntemi `CDrawingManager` sınıfı. Bu kod parçacığını parçası olan [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]  
  
##  <a name="grayrect"></a>CDrawingManager::GrayRect  
 Dikdörtgene belirtilen bir gri renge ile doldurur.  
  
```  
BOOL GrayRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    COLORREF clrDisabled = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 Doldurmak için dikdörtgen.  
  
 [in]`nPercentage`  
 Gri dikdörtgende istediğiniz yüzdesi.  
  
 [in]`clrTransparent`  
 Saydam rengi.  
  
 [in]`clrDisabled`  
 Bu yöntem için devre dışı bırakma Doygunluk kullanıyorsa renk `nPercentage` -1 olarak ayarlayın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametresi için `nPercentage`, daha düşük bir değere koyu renkli gösterir.  
  
 En büyük değeri `nPercentage` 200'dür. 200'den büyük bir değer dikdörtgen görünümünü değiştirmez. Değer -1 ise, bu yöntemi kullanır `clrDisabled` dikdörtgen doygunluğunu sınırlamak için.  
  
##  <a name="highlightrect"></a>CDrawingManager::HighlightRect  
 Dikdörtgen bir vurgular.  
  
```  
BOOL HighlightRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    int nTolerance = 0,  
    COLORREF clrBlend = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 Vurgulamak için dikdörtgen bir.  
  
 [in]`nPercentage`  
 Saydam Vurgu olmaması gerektiğini gösteren yüzdesi.  
  
 [in]`clrTransparent`  
 Saydam rengi.  
  
 [in]`nTolerance`  
 Renk tolerans gösteren 0 ile 255 arasında bir tamsayı.  
  
 [in]`clrBlend`  
 Karıştırma temel rengi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `nPercentage` 0 ile 99, arasında `HighlightRect` algoritması karıştırma alfa kullanır. Alfa karıştırma hakkında daha fazla bilgi için bkz: [Alfa karışım çizgiler ve dolgular](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills). Varsa `nPercentage` -1 ' dir varsayılan vurgulama düzeyi bu yöntemi kullanır. Varsa `nPercentage` 100, bu yöntem, hiçbir şey yapmaz ve döndürür `TRUE`.  
  
 Parametresi yöntemini kullanır `nTolerance` dikdörtgen vurgulamak karar vermek için. Dikdörtgen, uygulamanızın arka plan rengini arasındaki farkı vurgulamak için ve `clrTransparent` olmalıdır değerinden `nTolerance` her renk bileşeninde (kırmızı, yeşil ve mavi).  
  
##  <a name="hlstorgb_one"></a>CDrawingManager::HLStoRGB_ONE  
 Bir renk HLS gösteriminden bir RGB gösterimine dönüştürür.  
  
```  
static COLORREF __stdcall HLStoRGB_ONE(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`H`  
 0 ve 1 arasında bir sayı ton rengi temsil eder.  
  
 [in]`L`  
 0 ve 1 arasında bir sayı renk parlaklığını belirtir.  
  
 [in]`S`  
 0 ve 1 arasında bir sayı Doygunluk rengi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan HLS renk RGB gösterimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk HSV (ton, Doygunluk ve değer), HSL (ton, Doygunluk ve parlaklığını) ya da RGB (kırmızı, yeşil ve mavi) gösterilebilir. Renk farklı sunumu hakkında daha fazla bilgi için bkz: [renk](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Bu yöntem ve `CDrawingManager::HLStoRGB_TWO` yöntemi aynı işlemi gerçekleştirir, ancak için farklı değerler gerektiren `H` parametresi. Bu yöntemde `H` daireye yüzdesidir. İçinde `CDrawingManager::HLStoRGB_TWO` yöntemi, `H` 0 ile hem de kırmızı temsil 360 arasında derece değerdir. Örneğin, `HLStoRGB_ONE`, bir değeri için 0,25 `H` 90 değerine denktir `HLStoRGB_TWO`.  
  
##  <a name="hlstorgb_two"></a>CDrawingManager::HLStoRGB_TWO  
 Bir renk HLS gösteriminden bir RGB gösterimine dönüştürür.  
  
```  
static COLORREF __stdcall HLStoRGB_TWO(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`H`  
 Ton rengi temsil eden 0 ile 360 arasında bir sayı.  
  
 [in]`L`  
 0 ve 1 arasında bir sayı renk parlaklığını belirtir.  
  
 [in]`S`  
 0 ve 1 arasında bir sayı Doygunluk rengi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan HLS renk RGB gösterimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk HSV (ton, Doygunluk ve değer), HSL (ton, Doygunluk ve parlaklığını) ya da RGB (kırmızı, yeşil ve mavi) gösterilebilir. Renk farklı sunumu hakkında daha fazla bilgi için bkz: [renk](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Bu yöntem ve [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) yöntemi aynı işlemi gerçekleştirir, ancak için farklı değerler gerektiren `H` parametresi. Bu yöntemde, `H` 0 ile hem de kırmızı temsil 360 arasında derece değerdir. İçinde [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) yöntemi, `H` daireye yüzdesidir. Örneğin, `HLStoRGB_ONE`, bir değeri için 0,25 `H` 90 değerine denktir `HLStoRGB_TWO`.  
  
##  <a name="hsvtorgb"></a>CDrawingManager::HSVtoRGB  
 Bir renk HSV gösteriminden bir RGB gösterimine dönüştürür.  
  
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
|[in]`H`|Rengi ton gösteren 0 ile 360 arasında bir sayı.|  
|[in]`S`|0 ve 1 arasında bir sayı Doygunluk rengi belirtir.|  
|[in]`V`|0 ve 1 arasında bir sayı rengi değeri belirtir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan HSV renk RGB gösterimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk HSV (ton, Doygunluk ve değer), HSL (ton, Doygunluk ve parlaklığını) ya da RGB (kırmızı, yeşil ve mavi) gösterilebilir. Renk farklı sunumu hakkında daha fazla bilgi için bkz: [renk](http://go.microsoft.com/fwlink/linkid=119126).  
  
##  <a name="huetorgb"></a>CDrawingManager::HuetoRGB  
 Hue değeri bir kırmızı, yeşil veya mavi bileşenine dönüştürür.  
  
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
 [in]`m1`  
 Açıklamalar bakın.  
  
 [in]`m2`  
 Açıklamalar bakın.  
  
 [in]`h`  
 Açıklamalar bakın.  
  
 [in]`rm1`  
 Açıklamalar bakın.  
  
 [in]`rm2`  
 Açıklamalar bakın.  
  
 [in]`rh`  
 Açıklamalar bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek tek kırmızı, yeşil veya mavi bileşeni için sağlanan ton.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir yardımcı yöntemdir, `CDrawingManager` sınıfı bir renk HSV veya HSL gösteriminde tek tek kırmızı, yeşil ve mavi bileşenlerini hesaplamak için kullanır. Bu yöntem, doğrudan Programcı tarafından çağrılması için tasarlanmamıştır. Giriş parametreleri dönüştürme algoritmasına bağımlı değerlerdir.  
  
 Bir RGB gösterimine HSV veya HSL bir rengi dönüştürmek için aşağıdaki yöntemlerden birini arayın:  
  
- [CDrawingManager::HSVtoRGB](#hsvtorgb)  
  
- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)  
  
- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)  
  
##  <a name="mirrorrect"></a>CDrawingManager::MirrorRect  
 Dikdörtgen bir çevirir.  
  
```  
void MirrorRect(
    CRect rect,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 Ters çevirmek için alan sınırlayıcı dikdörtgenini.  
  
 [in]`bHorz`  
 Dikdörtgen yatay veya dikey olarak çevirir olup olmadığını gösteren bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından sahip olunan cihaz bağlamı, herhangi bir alan çevirebilirsiniz `CDrawingManager` sınıfı. Varsa `bHorz` ayarlanır `TRUE`, bu yöntem alanı yatay olarak döndürür. Aksi takdirde, bu alanda düşey olarak döndürür.  
  
##  <a name="pixelalpha"></a>CDrawingManager::PixelAlpha  
 Yarı saydam piksel son rengini hesaplar.  
  
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
 [in]`srcPixel`  
 Piksel ilk rengi.  
  
 [in]`percent`  
 Saydamlık yüzdesini temsil eden 0 ile 100 arasında bir sayı. İlk renk tamamen saydamdır 100 değerini gösterir.  
  
 [in]`percentR`  
 Kırmızı bileşeni için saydamlık yüzdesini temsil eden 0 ile 100 arasında bir sayı.  
  
 [in]`percentG`  
 Yeşil bileşeni için saydamlık yüzdesini temsil eden 0 ile 100 arasında bir sayı.  
  
 [in]`percentB`  
 Mavi bileşeni için saydamlık yüzdesini temsil eden 0 ile 100 arasında bir sayı.  
  
 [in]`dstPixel`  
 Piksel temel rengi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yarı saydam piksel son rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yarı saydam bit eşlemler renklendirme için bir yardımcı sınıf olan ve doğrudan Programcı tarafından çağrılması için tasarlanmamıştır.  
  
 Sahip yöntemi sürümünü kullandığınızda, `dstPixel`, son renk birleşimidir `dstPixel` ve `srcPixel`. `srcPixel` Renkte kısmen saydam rengi temel rengi `dstPixel`.  
  
##  <a name="prepareshadowmask"></a>CDrawingManager::PrepareShadowMask  
 Gölge kullanılabilir bir bit eşlem oluşturur.  
  
```  
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,  
    COLORREF clrBase,  
    int iMinBrightness = 0,  
    int iMaxBrightness = 100);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nDepth`  
 Genişlik ve yükseklik gölgenin.  
  
 [in]`clrBase`  
 Gölge rengi.  
  
 [in]`iMinBrightness`  
 Gölge minimum parlaklığını.  
  
 [in]`iMaxBrightness`  
 Gölge maksimum parlaklığını.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa oluşturulan bit eşlem için bir tanıtıcı; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `nDepth` 0 ise, bu yöntem kümesine çıkar ve döndürür `NULL`. Varsa `nDepth` 3'ten az olan, genişlik ve yükseklik gölgenin 3 piksel olarak ayarlanır.  
  
##  <a name="rgbtohsl"></a>CDrawingManager::RGBtoHSL  
 Bir renk kırmızı, yeşil ve mavi (RGB) gösteriminden ton, Doygunluk ve açıklık (HSL) gösterimine dönüştürür.  
  
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
|[in]`rgb`|RGB değerleri rengi.|  
|[out]`H`|Yöntem ton rengi için depoladığı bir çift için bir işaretçi.|  
|[out]`S`|Yöntem rengi Doygunluk depoladığı bir çift için bir işaretçi.|  
|[out]`L`|Yöntem rengi açıklık depoladığı bir çift için bir işaretçi.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk HSV (ton, Doygunluk ve değer), HSL (ton, Doygunluk ve parlaklığını) ya da RGB (kırmızı, yeşil ve mavi) gösterilebilir. Renk farklı sunumu hakkında daha fazla bilgi için bkz: [renk](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Döndürülen değeri `H` 0, 0 ve 1 temsil eden kırmızı 1 arasında bir kesir olarak temsil edilir. Döndürülen değerlerini `S` ve `L` numaraları 0 ile 1 arasında.  
  
##  <a name="rgbtohsv"></a>CDrawingManager::RGBtoHSV  
 Bir renk RGB gösteriminden bir HSV gösterimine dönüştürür.  
  
```  
static void __stdcall RGBtoHSV(
    COLORREF rgb,  
    double* H,  
    double* S,  
    double* V);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rgb`  
 Bir RGB gösterimi dönüştürmek için renk.  
  
 [out]`H`  
 Bu yöntem renk için sonuçta elde edilen ton depoladığı bir çift için bir işaretçi.  
  
 [out]`S`  
 Bu yöntem renk için sonuçta elde edilen Doygunluk depoladığı bir çift için bir işaretçi.  
  
 [out]`V`  
 Bu yöntem rengi sonuç değeri depoladığı bir çift için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk HSV (ton, Doygunluk ve değer), HSL (ton, Doygunluk ve parlaklığını) ya da RGB (kırmızı, yeşil ve mavi) gösterilebilir. Renk farklı sunumu hakkında daha fazla bilgi için bkz: [renk](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Döndürülen değeri `H` burada 0 ile 360 belirtmek kırmızı 0-360 arasında bir sayı değil. Dönüş değerleri için `S` ve `V` numaraları 0 ile 1 arasında.  
  
##  <a name="setalphapixel"></a>CDrawingManager::SetAlphaPixel  
 Saydam bir piksel için bit eşlemde renk.  
  
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
 [in]`pBits`  
 Bit eşlem bit değerlerini gösteren bir işaretçi.  
  
 [in]`rect`  
 Dikdörtgen bir uygulamanızda. Çizim manager altında ve bu alanda sağındaki gölge çizer.  
  
 [in]`x`  
 Renk piksel yatay koordinatı.  
  
 [in]`y`  
 Renk piksel dikey koordinatı.  
  
 [in]`percent`  
 Saydamlık yüzdesi.  
  
 [in]`iShadowSize`  
 Genişlik ve yükseklik gölgenin.  
  
 [in]`clrBase`  
 Gölge rengi.  
  
 [in]`bIsRight`  
 Renk için hangi piksel gösteren Boole parametresi. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından kullanılan bir yardımcı yöntemdir [CDrawingManager::DrawShadow](#drawshadow) yöntemi. Bir gölge çizmek istiyorsanız çağrı öneririz `CDrawingManager::DrawShadow` yerine.  
  
 Varsa `bIsRight` ayarlanır `TRUE`, renk piksel cinsinden ölçülen `x` sağ kenarından piksel `rect`. Eğer öyleyse `FALSE`, renk piksel cinsinden ölçülen `x` sol kenarından piksel `rect`.  
  
##  <a name="setpixel"></a>CDrawingManager::SetPixel  
 Bir tek pikselli bir bit eşlem belirtilen renge dönüşür.  
  
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
|[in]`pBits`|Bit eşlem bit değerlerini gösteren bir işaretçi.|  
|[in]`cx`|Bit eşlem toplam genişliği.|  
|[in]`cy`|Bit eşlem toplam yüksekliği.|  
|[in]`x`|X koordinatını değiştirmek için bit eşlemde piksel.|  
|[in]`y`|Y koordinatını değiştirmek için bit eşlemde piksel.|  
|[in]`color`|Sağlanan koordinatlarıyla tanımlanan piksel yeni rengi.|  
  
##  <a name="smartmixcolors"></a>CDrawingManager::SmartMixColors  
 İki renkten bir ağırlıklı oranını göre birleştirir.  
  
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
|[in]`color1`|Karıştırmak için ilk rengi.|  
|[in]`color2`|Karıştırmak için ikinci rengi.|  
|[in]`dblLumRatio`|Yeni rengin parlaklığını için oranı. `SmartMixColors`karma renk parlaklığını son renk belirlemeden önce bu oran tarafından çarpar.|  
|[in]`k1`|İlk rengi ağırlıklı oranı.|  
|[in]`k2`|İkinci rengi ağırlıklı oranı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan renkleri ağırlıklı karışımını temsil eden rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ile bir hata ya da başarısız olur `k1` veya `k2` sıfırdan küçüktür. Bu parametrelerin her ikisini de 0 olarak ayarlanmış ise, yöntem `RGB(0, 0, 0)`.  
  
 Ağırlıklı oranı aşağıdaki formüle göre hesaplanır: (Renk1 * k1 + renk2 \* k2) /(k1 + k2). Ağırlıklı oranı belirlendikten sonra yöntem karma renk parlaklığını hesaplar. Ardından tarafından parlaklığını çarpar `dblLumRatio`. Değeri 1.0 büyükse yöntemi karma renk parlaklığını yeni değere ayarlar. Aksi halde, parlaklığını 1.0 ayarlanır.  
  
##  <a name="drawrotated"></a>CDrawingManager::DrawRotated  
 Kaynak DC içerik verilen dikdörtgenin içindeki 90 derece döndürür.  
  
```  
void DrawRotated(
    CRect rectDest,  
    CDC& dcSrc,  
    BOOL bClockWise);
```  
  
### <a name="parameters"></a>Parametreler  
 `rectDest`  
 Hedef dikdörtgen.  
  
 `dcSrc`  
 Kaynak cihaz bağlamı.  
  
 `bClockWise`  
 `TRUE`döndürme + 90 derece gösterir; `FALSE` döndürme-90 derece gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)
