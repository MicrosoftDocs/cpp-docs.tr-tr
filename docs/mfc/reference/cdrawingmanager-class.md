---
title: CDrawingManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52ded6eb4b6b757934bcdb62c280c6d57e1b171e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196066"
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
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|Oluşturur bir `CDrawingManager` nesne.|  
|`CDrawingManager::~CDrawingManager`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|Uygulamalar için doğrudan yazabilen bir 32-bit CİHAZDAN bağımsız bit eşlem (DIB) oluşturur.|  
|[CDrawingManager::DrawAlpha](#drawalpha)|Saydam veya yarı saydam fırçalarla piksel olan bit eşlemler görüntüler.|  
|[CDrawingManager::DrawRotated](#drawrotated)|Bir kaynak DC içeriği tarafından belirtilen dikdörtgen +/-90 derece döndürür|  
|[CDrawingManager::DrawEllipse](#drawellipse)|Sağlanan dolgu ve kenarlık renkleri bir elips çizer.|  
|[CDrawingManager::DrawGradientRing](#drawgradientring)|Bir halka çizer ve bir renk gradyanı ile doldurur.|  
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|Bir çizgi çizer.|  
|[CDrawingManager::DrawRect](#drawrect)|Sağlanan dolgu ve kenarlık renkleri bir dikdörtgen çizer.|  
|[CDrawingManager::DrawShadow](#drawshadow)|Bir dikdörtgen alan için bir gölge çizer.|  
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|Bir dikdörtgen alan iki rengi gradyanlar ile doldurur.|  
|[CDrawingManager::FillGradient](#fillgradient)|Belirtilen renk gradyan ile bir dikdörtgen alan doldurur.|  
|[CDrawingManager::FillGradient2](#fillgradient2)|Belirtilen renk gradyan ile bir dikdörtgen alan doldurur. Gradyan renk değişikliği yönünü ayrıca belirtilir.|  
|[CDrawingManager::GrayRect](#grayrect)|İle belirtilen bir gri renk dikdörtgeni doldurur.|  
|[CDrawingManager::HighlightRect](#highlightrect)|Bir dikdörtgen alan vurgular.|  
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|Bir renk HLS gösteriminden bir RGB gösterimine dönüştürür.|  
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|Bir renk HLS gösteriminden bir RGB gösterimine dönüştürür.|  
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|Bir renk HSV gösteriminden bir RGB gösterimine dönüştürür.|  
|[CDrawingManager::HuetoRGB](#huetorgb)|Kırmızı, yeşil ve mavi bileşene hue değeri dönüştürür yardımcı yöntemi.|  
|[CDrawingManager::MirrorRect](#mirrorrect)|Bir dikdörtgen döndürür.|  
|[CDrawingManager::PixelAlpha](#pixelalpha)|Yarı saydam bir pikselin son rengini belirler yardımcı yöntemi.|  
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|Bir gölge kullanılabilecek bir bit eşlem oluşturur.|  
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|Renk RGB gösteriminden bir HSL gösterimine dönüştürür.|  
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|Renk RGB gösteriminden bir HSV gösterimine dönüştürür.|  
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|Bir bit eşlem kısmen saydam bir piksel renk yardımcı yöntemi.|  
|[CDrawingManager::SetPixel](#setpixel)|Bir tek pikselli bir bit eşlem içinde belirtilen rengine değiştirir yardımcı yöntemi.|  
|[CDrawingManager::SmartMixColors](#smartmixcolors)|Ağırlıklı bir oranını bağlı olan iki renkten bir araya getirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDrawingManager` Sınıfı, gölgeler, renk ve vurgulu dikdörtgen çizmek için işlevler sağlar. Alfa karıştırma gerçekleştirir. Bu sınıf doğrudan uygulamanın kullanıcı Arabiriminde değiştirmek için kullanabilirsiniz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
 `CDrawingManager`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdrawmanager.h  
  
##  <a name="cdrawingmanager"></a>  CDrawingManager::CDrawingManager  
 Oluşturur bir [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) nesne.  
  
```  
CDrawingManager(CDC& dc);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dc*  
 Bir cihaz bağlamına başvuru. `CDrawingManager` Çizim için bu bağlamı kullanır.  
  
##  <a name="createbitmap_32"></a>  CDrawingManager::CreateBitmap_32  
 Uygulamalar için doğrudan yazabilen bir 32-bit CİHAZDAN bağımsız bit eşlem (DIB) oluşturur.  
  
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
|[in] *boyutu*|A [CSize](../../atl-mfc-shared/reference/csize-class.md) bit eşlem boyutunu belirten bir parametre.|  
|[out] *pBits*|Bir işaretçi DIB'ın yerini alan veri işaretçisi bit değerleri.|  
|*Bit eşlem*|Özgün bit eşlem işleyici|  
|*clrTransparent*|Özgün bit eşlem saydam rengini belirten bir RGB değeri.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa yeni oluşturulan DIB bitmap işleyici; bulunmazsa null değerini DÖNDÜRÜR.  
  
### <a name="remarks"></a>Açıklamalar  
 DIB bit eşlem oluşturma hakkında daha fazla bilgi için bkz. [CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibitmap).  
  
##  <a name="drawalpha"></a>  CDrawingManager::DrawAlpha  
 Saydam veya yarı saydam fırçalarla piksel olan bit eşlemler görüntüler.  
  
```  
void DrawAlpha(
    CDC* pDstDC,  
    const CRect& rectDst,  
    CDC* pSrcDC,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDstDC*  
 Hedef cihaz bağlamının bir işaretçi.  
  
 [in] *rectDst*  
 Hedef dikdörtgenin.  
  
 [in] *psrcdc &*  
 Kaynak için cihaz bağlamı için bir işaretçi.  
  
 [in] *rectSrc*  
 Kaynak dikdörtgenin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için iki bit eşlemler alfa karıştırma gerçekleştirir. Alfa karıştırma hakkında daha fazla bilgi için bkz: [AlphaBlend](/windows/desktop/api/wingdi/nf-wingdi-alphablend) Windows SDK.  
  
##  <a name="drawellipse"></a>  CDrawingManager::DrawEllipse  
 Sağlanan dolgu ve kenarlık renkleri bir elips çizer.  
  
```  
void DrawEllipse(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
 Dikdörtgen elipsin.  
  
 [in] *clrFill*  
 Renk elips doldurmak için bu yöntemi kullanır.  
  
 [in] *clrLine*  
 Renk bu yöntem, elips kenarlığını kullanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, her iki renkten -1 olarak ayarlanmışsa bir elips çizme döndürür. Ayrıca, ya da Dikdörtgen boyutunun 0 ise, bir elips çizme olmadan döndürür.  
  
##  <a name="drawgradientring"></a>  CDrawingManager::DrawGradientRing  
 Bir halka çizer ve bir renk gradyanı ile doldurur.  
  
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
 [in] *dikdörtgen*  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) parametresi gradyan halka sınırlarını belirtir.  
  
 [in] *colorStart*  
 Geçişin ilk rengi.  
  
 [in] *colorFinish*  
 Geçişin son rengi.  
  
 [in] *colorBorder*  
 Kenarlık rengi.  
  
 [in] *nAngle*  
 Gradyan ilk çizim açı belirten bir parametresi. Bu değer, 0-360 arasında olmalıdır.  
  
 [in] *nWidth*  
 Kademesi için bir kenarlık genişliği.  
  
 [in] *clrFace*  
 Halka iç rengi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından tanımlanan dikdörtgen *rect* en az 5 piksel genişliğinde ve 5 piksel yüksekliğinde olması gerekir.  
  
##  <a name="drawline_cdrawingmanager__drawlinea"></a>  CDrawingManager::DrawLine, CDrawingManager::DrawLineA  
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
|[in] *x1*|Çizginin başladığı x koordinatı.|  
|[in] *y1*|Çizginin başladığı y koordinatı.|  
|[in] *x2*|Satırı sona ereceği x koordinatı.|  
|[in] *y2*|Satırı sona ereceği y koordinatı.|  
|[in] *clrLine*|Çizginin rengi.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, başarısız *clrLine* -1'e eşittir.  
  
##  <a name="drawrect"></a>  CDrawingManager::DrawRect  
 Sağlanan dolgu ve kenarlık renkleri bir dikdörtgen çizer.  
  
```  
void DrawRect(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
 Dikdörtgen için sınırlar.  
  
 [in] *clrFill*  
 Renk dikdörtgeni doldurmak için bu yöntemi kullanır.  
  
 [in] *clrLine*  
 Bu yöntemde dikdörtgeninin kenarlık için renk.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, her iki renkten -1 olarak ayarlarsanız bir dikdörtgen çizme döndürür. Ayrıca, ya da Dikdörtgen boyutunun 0 olup olmadığını döndürür.  
  
##  <a name="drawshadow"></a>  CDrawingManager::DrawShadow  
 Bir dikdörtgen alan için bir gölge çizer.  
  
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
 [in] *dikdörtgen*  
 Uygulamanızdaki bir dikdörtgen alan. Çizim Yöneticisi altındaki Bu alan bir gölge çizer.  
  
 [in] *nDepth*  
 Genişlik ve yükseklik gölge.  
  
 [in] *iMinBrightness*  
 Gölge minimum planının parlaklığı.  
  
 [in] *iMaxBrightness*  
 Gölge maksimum parlaklık.  
  
 [in] *pBmpSaveBottom*  
 Gölge alt parçasının görüntüsünü içeren bir bit eşlem işaretçisi.  
  
 [in] *pBmpSaveRight*  
 Bir bit eşlem resmi için dikdörtgen sağ tarafında çizilmiş gölge içeren bir işaretçi.  
  
 [in] *clrBase*  
 Gölge rengi.  
  
 [in] *bRightShadow*  
 Gölge nasıl çizilmeden gösteren bir Boole parametresi. Varsa *bRightShadow* olduğu `TRUE`, `DrawShadow` gölge sağ tarafında bir dikdörtgen çizer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametreleri kullanarak alt ve sağ shadows için geçerli iki bit eşlemler sağlayabilirsiniz *pBmpSaveBottom* ve *pBmpSaveRight*. Bu, [CBitmap](../../mfc/reference/cbitmap-class.md) nesneler sahip bağlı bir GDI nesnesi `DrawShadow` bu bit eşlemler shadows kullanır. Varsa `CBitmap` parametreleri ekli bir GDI nesnesi yok `DrawShadow` gölge çizer ve bit eşlemler parametreleri ekler. Gelecekte çağrıları `DrawShadow`, çizim sürecini hızlandırmak için bu bit eşlemler sağlayabilir. Hakkında daha fazla bilgi için `CBitmap` sınıfı ve bkz GDI nesneleri [grafik nesneleri](../../mfc/graphic-objects.md).  
  
 Bu parametrelerden biri geçerli olduğunda `NULL`, `DrawShadow` gölge otomatik olarak çizer.  
  
 Ayarlarsanız *bRightShadow* altında ve dikdörtgen alan solundaki gölge FALSE olarak çizilecek.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `DrawShadow` yöntemi `CDrawingManager` sınıfı. Bu kod parçacığı parçasıdır [Prop sayfası gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]  
  
##  <a name="fill4colorsgradient"></a>  CDrawingManager::Fill4ColorsGradient  
 Bir dikdörtgen alan iki rengi gradyanlar ile doldurur.  
  
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
 [in] *dikdörtgen*  
 Doldurmak için dikdörtgen.  
  
 [in] *colorStart1*  
 İlk renk gradyan başlangıç rengi.  
  
 [in] *colorFinish1*  
 İlk renk gradyanı son rengi.  
  
 [in] *colorStart2*  
 İkinci rengi gradyan başlangıç rengi.  
  
 [in] *colorFinish2*  
 İkinci renk gradyanı son rengi.  
  
 [in] *bHorz*  
 Belirten bir Boole parametresi olmadığını `Fill4ColorsGradient` yatay veya dikey gradyan renk. TRUE, Yatay Gradyan gösterir.  
  
 [in] *nPercentage*  
 0-100 arasında bir tamsayı. Bu değer, ilk renk gradyanı ile doldurmak için dikdörtgen yüzdesini gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Değerine bağlı olarak, birbiriyle sonraki ya da birbirlerine yukarıda bulunan bir dikdörtgen iki rengi gradyanlar ile dolduğunda oldukları *bHorz*. Her renk gradyanı bağımsız olarak yöntemiyle hesaplanır [CDrawingManager::FillGradient](#fillgradient).  
  
 Bu yöntem, bir onaylama işlemi hatası oluşturur *nPercentage* 0'den küçük veya 100'den daha fazla.  
  
##  <a name="fillgradient"></a>  CDrawingManager::FillGradient  
 Belirtilen renk gradyan ile bir dikdörtgen alan doldurur.  
  
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
 [in] *dikdörtgen*  
 Doldurmak için dikdörtgen alan.  
  
 [in] *colorStart*  
 Geçişin ilk rengi.  
  
 [in] *colorFinish*  
 Geçişin son rengi.  
  
 [in] *bHorz*  
 Belirten bir Boole parametresi olmadığını `FillGradient` yatay veya dikey gradyan çizip.  
  
 [in] *nStartFlatPercentage*  
 Dikdörtgen yüzdesi, `FillGradient` doldurur *colorStart* gradyan başlatılmadan önce.  
  
 [in] *nEndFlatPercentage*  
 Dikdörtgen yüzdesi, `FillGradient` doldurur *colorFinish* gradyan bittikten sonra.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `FillGradient` yöntemi `CDrawingManager` sınıfı. Bu kod parçacığı parçasıdır [MS Office 2007 Demo örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]  
  
##  <a name="fillgradient2"></a>  CDrawingManager::FillGradient2  
 Belirtilen renk gradyan ile bir dikdörtgen alan doldurur.  
  
```  
void FillGradient2 (
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    int nAngle = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
 Doldurmak için dikdörtgen alan.  
  
 [in] *colorStart*  
 Gradyanın ilk rengi.  
  
 [in] *colorFinish*  
 Geçişin son rengi.  
  
 [in] *nAngle*  
 0 ila 360 arasında bir tamsayı. Bu parametre, renk gradyanı yönünü belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım *nAngle* renk gradyanı yönünü belirtmek için. Renk gradyanı yönünü belirttiğinizde, renk gradyanı başladığı de belirtin. Bir değer için 0 *nAngle* dikdörtgenin üst kısmından geçişin başladığını gösterir. Olarak *nAngle* artırır, başlangıç konumu için gradyan açısını göre saat yönünün tersi yönde taşır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `FillGradient2` yöntemi `CDrawingManager` sınıfı. Bu kod parçacığı parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]  
  
##  <a name="grayrect"></a>  CDrawingManager::GrayRect  
 İle belirtilen bir gri renk dikdörtgeni doldurur.  
  
```  
BOOL GrayRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    COLORREF clrDisabled = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
 Doldurmak için dikdörtgen alan.  
  
 [in] *nPercentage*  
 Gri dikdörtgende istediğiniz yüzdesi.  
  
 [in] *clrTransparent*  
 Saydam rengi.  
  
 [in] *clrDisabled*  
 Bu yöntem için devre dışı bırakma doygunluğu kullanıyorsa renk *nPercentage* -1 olarak ayarlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametresi için *nPercentage*, daha düşük bir değere koyu renk gösterir.  
  
 En yüksek değeri *nPercentage* 200'dür. 200 ' büyük bir değer dikdörtgen görünümünü değiştirmez. Değer -1 ise, bu yöntemde *clrDisabled* dikdörtgenin doygunluğu sınırlamak için.  
  
##  <a name="highlightrect"></a>  CDrawingManager::HighlightRect  
 Bir dikdörtgen alan vurgular.  
  
```  
BOOL HighlightRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    int nTolerance = 0,  
    COLORREF clrBlend = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
 Vurgulamak için bir dikdörtgen alan.  
  
 [in] *nPercentage*  
 Saydam vurgulama olmaması gerektiğini gösteren bir yüzdesi.  
  
 [in] *clrTransparent*  
 Saydam rengi.  
  
 [in] *nTolerance*  
 Renk dayanıklılık gösteren 0 ile 255 arasında bir tamsayı.  
  
 [in] *clrBlend*  
 Karıştırma temel rengi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *nPercentage* 0 ile 99 arasındadır, olan `HighlightRect` alfa karıştırma algoritması kullanır. Alfa karışım kullanma hakkında daha fazla bilgi için bkz. [alfa karıştırma çizgiler ve dolgular](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills). Varsa *nPercentage* -1, bu yöntem varsayılan vurgulama düzeyini kullanır. Varsa *nPercentage* 100, bu yöntem, hiçbir şey yapmaz ve true değer döndürür.  
  
 Parametre kullanmaktadır *nTolerance* Dikdörtgen alanı vurgulamak belirlemek için. Dikdörtgen, uygulamanızın arka plan rengi arasındaki farkı vurgulayın ve *clrTransparent* olmalıdır küçüktür *nTolerance* her renk bileşeni (kırmızı, yeşil ve mavi) içinde.  
  
##  <a name="hlstorgb_one"></a>  CDrawingManager::HLStoRGB_ONE  
 Bir renk HLS gösteriminden bir RGB gösterimine dönüştürür.  
  
```  
static COLORREF __stdcall HLStoRGB_ONE(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *H*  
 0 ve 1 arasında bir sayı ton rengi temsil eder.  
  
 [in] *m*  
 0 ve 1 arasında bir sayı renk parlaklığını belirtir.  
  
 [in] *S*  
 0 ve 1 arasında bir sayı için renk doygunluğu gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan HLS renk RGB gösterimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk HSV (ton, Doygunluk ve değer), HSL (ton, Doygunluk ve parlaklık) veya RGB (kırmızı, yeşil ve mavi) gösterilebilir. Farklı renk gösterimleri hakkında daha fazla bilgi için bkz. [renk](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Bu yöntem ve `CDrawingManager::HLStoRGB_TWO` yöntem aynı işlemi gerçekleştirmek, ancak için farklı değerler gerektiren *H* parametresi. Bu yöntemde, *H* dairenin bir yüzde değeri. İçinde `CDrawingManager::HLStoRGB_TWO` yöntemi *H* 0 ve hem de kırmızı temsil eden 360 arasında bir ölçüde değerdir. Örneğin, `HLStoRGB_ONE`, 0,25 için değeri *H* 90 değerine eşdeğerdir `HLStoRGB_TWO`.  
  
##  <a name="hlstorgb_two"></a>  CDrawingManager::HLStoRGB_TWO  
 Bir renk HLS gösteriminden bir RGB gösterimine dönüştürür.  
  
```  
static COLORREF __stdcall HLStoRGB_TWO(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *H*  
 Ton rengi temsil eden 0-360 arasında bir sayı.  
  
 [in] *m*  
 0 ve 1 arasında bir sayı renk parlaklığını belirtir.  
  
 [in] *S*  
 0 ve 1 arasında bir sayı için renk doygunluğu gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan HLS renk RGB gösterimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk HSV (ton, Doygunluk ve değer), HSL (ton, Doygunluk ve parlaklık) veya RGB (kırmızı, yeşil ve mavi) gösterilebilir. Farklı renk gösterimleri hakkında daha fazla bilgi için bkz. [renk](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Bu yöntem ve [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) yöntem aynı işlemi gerçekleştirmek, ancak için farklı değerler gerektiren *H* parametresi. Bu yöntemde, *H* 0 ve hem de kırmızı temsil eden 360 arasında bir ölçüde değerdir. İçinde [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) yöntemi *H* dairenin bir yüzde değeri. Örneğin, `HLStoRGB_ONE`, 0,25 için değeri *H* 90 değerine eşdeğerdir `HLStoRGB_TWO`.  
  
##  <a name="hsvtorgb"></a>  CDrawingManager::HSVtoRGB  
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
|[in] *H*|Ton rengi için belirten 0-360 arasında bir sayı.|  
|[in] *S*|0 ve 1 arasında bir sayı için renk doygunluğu gösterir.|  
|[in] *V*|Renk değeri 0 ve 1 arasında bir sayı gösterir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan HSV renk RGB gösterimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk HSV (ton, Doygunluk ve değer), HSL (ton, Doygunluk ve parlaklık) veya RGB (kırmızı, yeşil ve mavi) gösterilebilir. Farklı renk gösterimleri hakkında daha fazla bilgi için bkz. [renk](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
##  <a name="huetorgb"></a>  CDrawingManager::HuetoRGB  
 Hue değeri bir kırmızı, yeşil ve mavi bileşeni dönüştürür.  
  
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
 [in] *m1*  
 Açıklamalara bakın.  
  
 [in] *m2*  
 Açıklamalara bakın.  
  
 [in] *h*  
 Açıklamalara bakın.  
  
 [in] *rm1*  
 Açıklamalara bakın.  
  
 [in] *rm2*  
 Açıklamalara bakın.  
  
 [in] *rh*  
 Açıklamalara bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek tek kırmızı, yeşil ve mavi bileşeni için sağlanan ton.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir yardımcı yöntemdir, `CDrawingManager` sınıf HSV veya HSL gösteriminde bir renk bireysel kırmızı, yeşil ve mavi bileşenlerinin hesaplamakta kullanır. Bu yöntem doğrudan Programcı tarafından çağrılmak üzere tasarlanmamıştır. Giriş parametrelerini dönüştürme algoritmasına bağımlı değerlerdir.  
  
 Bir RGB gösterimine HSV veya HSL bir rengi dönüştürmek için aşağıdaki yöntemlerden birini çağırın:  
  
- [CDrawingManager::HSVtoRGB](#hsvtorgb)  
  
- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)  
  
- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)  
  
##  <a name="mirrorrect"></a>  CDrawingManager::MirrorRect  
 Bir dikdörtgen döndürür.  
  
```  
void MirrorRect(
    CRect rect,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
 Çevrilecek alan sınırlayıcı dikdörtgenini.  
  
 [in] *bHorz*  
 Dikdörtgen yatay veya dikey çevirir olup olmadığını gösteren bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından sahip olunan cihaz bağlamının herhangi bir alan çevirebilirsiniz `CDrawingManager` sınıfı. Varsa *bHorz* olan TRUE olarak ayarlanırsa, yatay olarak alan bu yöntemi döndürür. Aksi takdirde, bu alanı düşey olarak döndürür.  
  
##  <a name="pixelalpha"></a>  CDrawingManager::PixelAlpha  
 Yarı saydam bir pikselin son rengini hesaplar.  
  
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
 [in] *srcPixel*  
 Piksel ilk rengi.  
  
 [in] *yüzde*  
 Saydamlık yüzdesini temsil eden 0 ile 100 arasında bir sayı. İlk renk tamamen saydamdır 100 değerini gösterir.  
  
 [in] *percentR*  
 Kırmızı bileşeni için saydamlığı yüzdesini temsil eden 0 ile 100 arasında bir sayı.  
  
 [in] *percentG*  
 Yeşil bileşeni için saydamlığı yüzdesini temsil eden 0 ile 100 arasında bir sayı.  
  
 [in] *percentB*  
 Mavi bileşeni için saydamlığı yüzdesini temsil eden 0 ile 100 arasında bir sayı.  
  
 [in] *dstPixel*  
 Piksel temel rengi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yarı saydam fırçalarla pikselin son rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, bir yardımcı sınıftır yarı saydam fırçalarla bit eşlemler renklendirme için ve doğrudan Programcı tarafından çağrılmak üzere tasarlanmamıştır.  
  
 Yöntemin sürümünü kullandığınızda *dstPixel*, son rengini birleşimidir *dstPixel* ve *srcPixel*. *SrcPixel* renktir kısmen saydam rengi temel rengi *dstPixel*.  
  
##  <a name="prepareshadowmask"></a>  CDrawingManager::PrepareShadowMask  
 Bir gölge kullanılabilecek bir bit eşlem oluşturur.  
  
```  
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,  
    COLORREF clrBase,  
    int iMinBrightness = 0,  
    int iMaxBrightness = 100);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nDepth*  
 Genişlik ve yükseklik gölge.  
  
 [in] *clrBase*  
 Gölge rengi.  
  
 [in] *iMinBrightness*  
 Gölge minimum planının parlaklığı.  
  
 [in] *iMaxBrightness*  
 Gölge maksimum parlaklık.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa oluşturulan bit eşlem işleyici; bulunmazsa null değerini DÖNDÜRÜR.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *nDepth* 0 olarak bu yöntem çıkar ve NULL döndürür. Varsa *nDepth* 3'ten az, genişlik ve yükseklik gölge 3 piksel olarak ayarlanır.  
  
##  <a name="rgbtohsl"></a>  CDrawingManager::RGBtoHSL  
 Bir renk ton, Doygunluk ve açıklık (HSL) gösterimi kırmızı, yeşil ve mavi (RGB) gösteriminden dönüştürür.  
  
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
|[in] *rgb*|Renk RGB değerleri.|  
|[out] *H*|Yöntem için renk tonu depoladığı double bir işaretçi.|  
|[out] *S*|Yöntem için renk doygunluğu depoladığı double bir işaretçi.|  
|[out] *m*|Yöntemi, renk için açıklık depoladığı double bir işaretçi.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk HSV (ton, Doygunluk ve değer), HSL (ton, Doygunluk ve parlaklık) veya RGB (kırmızı, yeşil ve mavi) gösterilebilir. Farklı renk gösterimleri hakkında daha fazla bilgi için bkz. [renk](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 İçin döndürülen değer *H* 0 ile 1 nerede hem 0 ve 1 temsil eden kırmızı arasında bir kesir olarak temsil edilir. Döndürülen değerleri *S* ve *L* numaraları 0 ile 1 arasında.  
  
##  <a name="rgbtohsv"></a>  CDrawingManager::RGBtoHSV  
 Renk RGB gösteriminden bir HSV gösterimine dönüştürür.  
  
```  
static void __stdcall RGBtoHSV(
    COLORREF rgb,  
    double* H,  
    double* S,  
    double* V);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rgb*  
 Bir RGB gösteriminde dönüştürmek için renk.  
  
 [out] *H*  
 Bu yöntem, sonuçta elde edilen ton rengi için depoladığı double bir işaretçi.  
  
 [out] *S*  
 Bu yöntem, renk için elde edilen doygunluğu depoladığı double bir işaretçi.  
  
 [out] *V*  
 Bu yöntem, renk için sonuç değerini depoladığı double bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk HSV (ton, Doygunluk ve değer), HSL (ton, Doygunluk ve parlaklık) veya RGB (kırmızı, yeşil ve mavi) gösterilebilir. Farklı renk gösterimleri hakkında daha fazla bilgi için bkz. [renk](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 İçin döndürülen değer *H* burada 0 hem 360 gösteren kırmızı 0-360 arasında bir sayı olan. Dönüş değerleri için *S* ve *V* numaraları 0 ile 1 arasında.  
  
##  <a name="setalphapixel"></a>  CDrawingManager::SetAlphaPixel  
 Bir bit eşlem saydam bir piksel renk.  
  
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
 [in] *pBits*  
 Bit eşlem bit değerleri için bir işaretçi.  
  
 [in] *dikdörtgen*  
 Uygulamanızdaki bir dikdörtgen alan. Çizim Yöneticisi altında ve bu alan sağındaki gölge çizer.  
  
 [in] *x*  
 Piksel renk yatay koordinatı.  
  
 [in] *y*  
 Piksel renk dikey koordinatı.  
  
 [in] *yüzde*  
 Saydamlık yüzdesi.  
  
 [in] *iShadowSize*  
 Genişlik ve yükseklik gölge.  
  
 [in] *clrBase*  
 Gölge rengi.  
  
 [in] *bIsRight*  
 Renk için hangi piksel gösteren bir Boole parametresi. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından kullanılan bir yardımcı yöntemdir [CDrawingManager::DrawShadow](#drawshadow) yöntemi. Bir gölge çizmek istiyorsanız çağrı öneririz `CDrawingManager::DrawShadow` yerine.  
  
 Varsa *bIsRight* olan TRUE olarak ayarlanırsa, renk piksel cinsinden ölçülen *x* sağ kenarından piksel *rect*. FALSE ise, renk piksel cinsinden ölçülen *x* sol kenarından piksel *rect*.  
  
##  <a name="setpixel"></a>  CDrawingManager::SetPixel  
 Bir tek pikselli bir bit eşlem içinde belirtilen rengine değiştirir.  
  
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
|[in] *pBits*|Bit eşlem bit değerleri için bir işaretçi.|  
|[in] *cx*|Bit eşlem toplam genişliği.|  
|[in] *cy*|Bit eşlem toplam yüksekliği.|  
|[in] *x*|X koordinatı değiştirmek için bit eşlemin piksel.|  
|[in] *y*|Y koordinatını değiştirmek için bit eşlemin piksel.|  
|[in] *rengi*|Yeni sağlanan koordinatları tarafından tanımlanan piksel rengi.|  
  
##  <a name="smartmixcolors"></a>  CDrawingManager::SmartMixColors  
 Ağırlıklı bir oranını bağlı olan iki renkten bir araya getirir.  
  
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
|[in] *Renk1*|Karıştırılacak ilk rengi.|  
|[in] *renk2*|Karıştırılacak ikinci rengi.|  
|[in] *dblLumRatio*|Yeni renk parlaklığını için oranı. `SmartMixColors` karma renk parlaklığını son rengini belirlemeden önce bu oran ile çarpar.|  
|[in] *k1*|İlk renk ağırlıklı sayısına oranı.|  
|[in] *k2*|İkinci rengi için ağırlıklı oranı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan renkleri ağırlıklı bir karışımını temsil eden bir renk.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ya da bir hata ile başarısız *k1* veya *k2* sıfırdan küçüktür. Bu parametrelerin her ikisini de 0 olarak ayarlıysa, yöntem döndürür `RGB(0, 0, 0)`.  
  
 Ağırlıklı oranı aşağıdaki formüle göre hesaplanır: (Renk1 \* k1 + renk2 \* k2) /(k1 + k2). Ağırlıklı oranı belirlendikten sonra yöntem için karma renk parlaklığını hesaplar. Ardından tarafından parlaklık çarpar *dblLumRatio*. Değer 1.0 daha büyük ise, yöntem karma renk parlaklığını yeni değere ayarlar. Aksi takdirde, parlaklık 1.0 için ayarlanır.  
  
##  <a name="drawrotated"></a>  CDrawingManager::DrawRotated  
 Bir kaynak DC içeriği belirtilen dikdörtgen içindeki 90 derece döndürür.  
  
```  
void DrawRotated(
    CRect rectDest,  
    CDC& dcSrc,  
    BOOL bClockWise);
```  
  
### <a name="parameters"></a>Parametreler  
 *rectDest*  
 Hedef dikdörtgenin.  
  
 *dcSrc*  
 Kaynak cihaz bağlamı.  
  
 *bClockWise*  
 TRUE, döndürme + 90 derece gösterir; FALSE-90 derece döndür gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
