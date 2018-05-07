---
title: CRenderTarget sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRenderTarget
- AFXRENDERTARGET/CRenderTarget
- AFXRENDERTARGET/CRenderTarget::CRenderTarget
- AFXRENDERTARGET/CRenderTarget::Attach
- AFXRENDERTARGET/CRenderTarget::BeginDraw
- AFXRENDERTARGET/CRenderTarget::Clear
- AFXRENDERTARGET/CRenderTarget::COLORREF_TO_D2DCOLOR
- AFXRENDERTARGET/CRenderTarget::CreateCompatibleRenderTarget
- AFXRENDERTARGET/CRenderTarget::Destroy
- AFXRENDERTARGET/CRenderTarget::Detach
- AFXRENDERTARGET/CRenderTarget::DrawBitmap
- AFXRENDERTARGET/CRenderTarget::DrawEllipse
- AFXRENDERTARGET/CRenderTarget::DrawGeometry
- AFXRENDERTARGET/CRenderTarget::DrawGlyphRun
- AFXRENDERTARGET/CRenderTarget::DrawLine
- AFXRENDERTARGET/CRenderTarget::DrawRectangle
- AFXRENDERTARGET/CRenderTarget::DrawRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::DrawText
- AFXRENDERTARGET/CRenderTarget::DrawTextLayout
- AFXRENDERTARGET/CRenderTarget::EndDraw
- AFXRENDERTARGET/CRenderTarget::FillEllipse
- AFXRENDERTARGET/CRenderTarget::FillGeometry
- AFXRENDERTARGET/CRenderTarget::FillMesh
- AFXRENDERTARGET/CRenderTarget::FillOpacityMask
- AFXRENDERTARGET/CRenderTarget::FillRectangle
- AFXRENDERTARGET/CRenderTarget::FillRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::Flush
- AFXRENDERTARGET/CRenderTarget::GetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetDpi
- AFXRENDERTARGET/CRenderTarget::GetMaximumBitmapSize
- AFXRENDERTARGET/CRenderTarget::GetPixelFormat
- AFXRENDERTARGET/CRenderTarget::GetPixelSize
- AFXRENDERTARGET/CRenderTarget::GetRenderTarget
- AFXRENDERTARGET/CRenderTarget::GetSize
- AFXRENDERTARGET/CRenderTarget::GetTags
- AFXRENDERTARGET/CRenderTarget::GetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::GetTransform
- AFXRENDERTARGET/CRenderTarget::IsSupported
- AFXRENDERTARGET/CRenderTarget::IsValid
- AFXRENDERTARGET/CRenderTarget::PopAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PopLayer
- AFXRENDERTARGET/CRenderTarget::PushAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PushLayer
- AFXRENDERTARGET/CRenderTarget::RestoreDrawingState
- AFXRENDERTARGET/CRenderTarget::SaveDrawingState
- AFXRENDERTARGET/CRenderTarget::SetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetDpi
- AFXRENDERTARGET/CRenderTarget::SetTags
- AFXRENDERTARGET/CRenderTarget::SetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::SetTransform
- AFXRENDERTARGET/CRenderTarget::VerifyResource
- AFXRENDERTARGET/CRenderTarget::m_lstResources
- AFXRENDERTARGET/CRenderTarget::m_pRenderTarget
- AFXRENDERTARGET/CRenderTarget::m_pTextFormatDefault
dev_langs:
- C++
helpviewer_keywords:
- CRenderTarget [MFC], CRenderTarget
- CRenderTarget [MFC], Attach
- CRenderTarget [MFC], BeginDraw
- CRenderTarget [MFC], Clear
- CRenderTarget [MFC], COLORREF_TO_D2DCOLOR
- CRenderTarget [MFC], CreateCompatibleRenderTarget
- CRenderTarget [MFC], Destroy
- CRenderTarget [MFC], Detach
- CRenderTarget [MFC], DrawBitmap
- CRenderTarget [MFC], DrawEllipse
- CRenderTarget [MFC], DrawGeometry
- CRenderTarget [MFC], DrawGlyphRun
- CRenderTarget [MFC], DrawLine
- CRenderTarget [MFC], DrawRectangle
- CRenderTarget [MFC], DrawRoundedRectangle
- CRenderTarget [MFC], DrawText
- CRenderTarget [MFC], DrawTextLayout
- CRenderTarget [MFC], EndDraw
- CRenderTarget [MFC], FillEllipse
- CRenderTarget [MFC], FillGeometry
- CRenderTarget [MFC], FillMesh
- CRenderTarget [MFC], FillOpacityMask
- CRenderTarget [MFC], FillRectangle
- CRenderTarget [MFC], FillRoundedRectangle
- CRenderTarget [MFC], Flush
- CRenderTarget [MFC], GetAntialiasMode
- CRenderTarget [MFC], GetDpi
- CRenderTarget [MFC], GetMaximumBitmapSize
- CRenderTarget [MFC], GetPixelFormat
- CRenderTarget [MFC], GetPixelSize
- CRenderTarget [MFC], GetRenderTarget
- CRenderTarget [MFC], GetSize
- CRenderTarget [MFC], GetTags
- CRenderTarget [MFC], GetTextAntialiasMode
- CRenderTarget [MFC], GetTextRenderingParams
- CRenderTarget [MFC], GetTransform
- CRenderTarget [MFC], IsSupported
- CRenderTarget [MFC], IsValid
- CRenderTarget [MFC], PopAxisAlignedClip
- CRenderTarget [MFC], PopLayer
- CRenderTarget [MFC], PushAxisAlignedClip
- CRenderTarget [MFC], PushLayer
- CRenderTarget [MFC], RestoreDrawingState
- CRenderTarget [MFC], SaveDrawingState
- CRenderTarget [MFC], SetAntialiasMode
- CRenderTarget [MFC], SetDpi
- CRenderTarget [MFC], SetTags
- CRenderTarget [MFC], SetTextAntialiasMode
- CRenderTarget [MFC], SetTextRenderingParams
- CRenderTarget [MFC], SetTransform
- CRenderTarget [MFC], VerifyResource
- CRenderTarget [MFC], m_lstResources
- CRenderTarget [MFC], m_pRenderTarget
- CRenderTarget [MFC], m_pTextFormatDefault
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c7550e3e3d8bf7e49f9f93ea6e9a931d6567ef0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="crendertarget-class"></a>CRenderTarget sınıfı
ID2D1RenderTarget için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CRenderTarget : public CObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRenderTarget::CRenderTarget](#crendertarget)|CRenderTarget nesnesi oluşturur.|  
|[CRenderTarget:: ~ CRenderTarget](#crendertarget__~crendertarget)|Yok Edicisi. Bir işleme hedef nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRenderTarget::Attach](#attach)|Hedef arabirimini nesneye ekler varolan oluşturmak|  
|[CRenderTarget::BeginDraw](#begindraw)|Bu işleme hedefte çizim başlatır.|  
|[CRenderTarget::Clear](#clear)|Belirtilen renk çizim alana temizler.|  
|[CRenderTarget::COLORREF_TO_D2DCOLOR](#colorref_to_d2dcolor)|GDI renk ve alfa değerleri D2D1_COLOR_F nesnesine dönüştürür.|  
|[CRenderTarget::CreateCompatibleRenderTarget](#createcompatiblerendertarget)|Geçerli işleme hedefiyle uyumlu Ara ekran dışında çizim sırasında kullanmak için yeni bir bit eşlem oluşturma hedef oluşturur.|  
|[CRenderTarget::Destroy](#destroy)|Bir veya daha fazla kaynakları siler|  
|[CRenderTarget::Detach](#detach)|İşleme hedef arabirimi nesneden çıkarır|  
|[CRenderTarget::DrawBitmap](#drawbitmap)|Belirtilen IDWriteTextLayout nesnesi tarafından açıklanan biçimlendirilmiş metin çizer.|  
|[CRenderTarget::DrawEllipse](#drawellipse)|Belirtilen vuruş stili kullanılarak belirtilen elips anahat çizer.|  
|[CRenderTarget::DrawGeometry](#drawgeometry)|Belirtilen vuruş stili kullanılarak belirtilen geometri anahat çizer.|  
|[CRenderTarget::DrawGlyphRun](#drawglyphrun)|Belirtilen karakterlerin çizer.|  
|[CRenderTarget::DrawLine](#drawline)|Belirtilen vuruş stili kullanılarak belirtilen noktaları arasında bir çizgi çizer.|  
|[CRenderTarget::DrawRectangle](#drawrectangle)|Belirtilen boyut ve vuruş stili sahip dikdörtgen anahat çizer.|  
|[CRenderTarget::DrawRoundedRectangle](#drawroundedrectangle)|Belirtilen vuruş stili kullanılarak belirtilen yuvarlak dikdörtgen anahat çizer.|  
|[CRenderTarget::DrawText](#drawtext)|Belirtilen metni IDWriteTextFormat nesne tarafından sağlanan biçimi bilgileri kullanarak çizer.|  
|[CRenderTarget::DrawTextLayout](#drawtextlayout)|Belirtilen IDWriteTextLayout nesnesi tarafından açıklanan biçimlendirilmiş metin çizer.|  
|[CRenderTarget::EndDraw](#enddraw)|İşleme hedefte çizim işlemleri sonlandırır ve geçerli hata durumu ve ilişkili etiketleri gösterir.|  
|[CRenderTarget::FillEllipse](#fillellipse)|Belirtilen elips iç boyar.|  
|[CRenderTarget::FillGeometry](#fillgeometry)|Belirtilen geometri iç boyar.|  
|[CRenderTarget::FillMesh](#fillmesh)|Belirtilen kafes iç boyar.|  
|[CRenderTarget::FillOpacityMask](#fillopacitymask)|Fırça için belirtilen bit eşlem tarafından açıklanan opaklık maskesi uygular ve o Fırça oluşturma hedef bölgesi boyamak için kullanır.|  
|[CRenderTarget::FillRectangle](#fillrectangle)|Belirtilen dikdörtgenin iç boyar.|  
|[CRenderTarget::FillRoundedRectangle](#fillroundedrectangle)|Belirtilen yuvarlak dikdörtgen iç boyar.|  
|[CRenderTarget::Flush](#flush)|Tüm bekleyen çizim komutları yürütür.|  
|[CRenderTarget::GetAntialiasMode](#getantialiasmode)|Metin çizme işlemleri için geçerli düzgünleştirme modunu alır.|  
|[CRenderTarget::GetDpi](#getdpi)|Hedefin nokta / inç (DPI) işleme döndürür|  
|[CRenderTarget::GetMaximumBitmapSize](#getmaximumbitmapsize)|En büyük boyutu işleme hedefi tarafından desteklenen herhangi bir bit eşlem boyutunun aygıta bağımlı birimler (piksel cinsinden) alır|  
|[CRenderTarget::GetPixelFormat](#getpixelformat)|İşleme hedefi piksel biçimi ve alfa modunu alır.|  
|[CRenderTarget::GetPixelSize](#getpixelsize)|İşleme hedef boyutunu aygıt piksel cinsinden döndürür|  
|[CRenderTarget::GetRenderTarget](#getrendertarget)|Döndürür ID2D1RenderTarget arabirimi|  
|[CRenderTarget::GetSize](#getsize)|CİHAZDAN bağımsız piksel cinsinden işleme hedef boyutunu döndürür|  
|[CRenderTarget::GetTags](#gettags)|Sonraki çizim işlemleri için etiketini alır.|  
|[CRenderTarget::GetTextAntialiasMode](#gettextantialiasmode)|Metin ve işlemleri çizim simge için geçerli düzgünleştirme modunu alır.|  
|[CRenderTarget::GetTextRenderingParams](#gettextrenderingparams)|İşleme hedefin geçerli metin işleme seçenekleri alır.|  
|[CRenderTarget::GetTransform](#gettransform)|Belirtilen dönüşüm varolan dönüştürme değiştirme işleme hedef için geçerlidir. Tüm sonraki çizim işlemleri dönüştürülmüş alanı oluşur.|  
|[CRenderTarget::IsSupported](#issupported)|İşleme hedefi belirtilen özellikleri destekleyip desteklemediğini belirtir|  
|[CRenderTarget::IsValid](#isvalid)|Denetimleri kaynak geçerlilik|  
|[CRenderTarget::PopAxisAlignedClip](#popaxisalignedclip)|Son eksen hizalı klibi işleme hedef kaldırır. Bu yöntemi çağrıldıktan sonra aşağıdaki klip artık sonraki çizim işlemleri için uygulanır.|  
|[CRenderTarget::PopLayer](#poplayer)|Çizim işlemleri tarafından son PushLayer belirtilen bir katmana yeniden yönlendirme durakları çağırın.|  
|[CRenderTarget::PushAxisAlignedClip](#pushaxisalignedclip)|Son eksen hizalı klibi işleme hedef kaldırır. Bu yöntemi çağrıldıktan sonra aşağıdaki klip artık sonraki çizim işlemleri için uygulanır.|  
|[CRenderTarget::PushLayer](#pushlayer)|Belirtilen katman işleme hedef ekler, böylece PopLayer çağrılıncaya kadar tüm sonraki çizim işlemleri alır.|  
|[CRenderTarget::RestoreDrawingState](#restoredrawingstate)|İşleme hedefin çizim durumu, belirtilen ID2D1DrawingStateBlock ayarlar.|  
|[CRenderTarget::SaveDrawingState](#savedrawingstate)|Geçerli çizim durumu için belirtilen ID2D1DrawingStateBlock kaydeder.|  
|[CRenderTarget::SetAntialiasMode](#setantialiasmode)|İşleme hedefi düzgünleştirme modunu ayarlar. Düzgünleştirme modu metin ve işlemleri çizim simge hariç tüm sonraki çizim işlemleri için geçerlidir.|  
|[CRenderTarget::SetDpi](#setdpi)|Nokta / inç (DPI) işleme hedef ayarlar.|  
|[CRenderTarget::SetTags](#settags)|Sonraki çizim işlemleri için bir etiket belirtir.|  
|[CRenderTarget::SetTextAntialiasMode](#settextantialiasmode)|Sonraki metni ve karakter çizim işlemleri için kullanılacak düzgünleştirme modunu belirtir.|  
|[CRenderTarget::SetTextRenderingParams](#settextrenderingparams)|Tüm sonraki metin ve işlemleri çizim karakter uygulanacak metin işleme seçeneklerini belirtir.|  
|[CRenderTarget::SetTransform](#settransform)|Fazla Yüklendi. Belirtilen dönüşüm varolan dönüştürme değiştirme işleme hedef için geçerlidir. Tüm sonraki çizim işlemleri dönüştürülmüş alanı oluşur.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRenderTarget::VerifyResource](#verifyresource)|CD2DResource nesnenin geçerliliğini doğrular; varsa kaydetmedi nesnesi oluşturur.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRenderTarget::operator ID2D1RenderTarget *](#operator_id2d1rendertarget_star)|Döndürür ID2D1RenderTarget arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRenderTarget::m_lstResources](#m_lstresources)|CD2DResource nesnelerine işaretçiler listesi.|  
|[CRenderTarget::m_pRenderTarget](#m_prendertarget)|ID2D1RenderTarget nesneyi gösteren bir işaretçi.|  
|[CRenderTarget::m_pTextFormatDefault](#m_ptextformatdefault)|Varsayılan metin biçimi içeren CD2DTextFormat nesne için bir işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="_dtorcrendertarget"></a>  CRenderTarget:: ~ CRenderTarget  
 Yok Edicisi. Bir işleme hedef nesnesi yok çağrılır.  
  
```  
virtual ~CRenderTarget();
```  
  
##  <a name="attach"></a>  CRenderTarget::Attach  
 Hedef arabirimini nesneye ekler varolan oluşturmak  
  
```  
void Attach(ID2D1RenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRenderTarget`  
 Varolan işleme hedefi arabirimi. NULL olamaz  
  
##  <a name="begindraw"></a>  CRenderTarget::BeginDraw  
 Bu işleme hedefte çizim başlatır.  
  
```  
void BeginDraw();
```  
  
##  <a name="clear"></a>  CRenderTarget::Clear  
 Belirtilen renk çizim alana temizler.  
  
```  
void Clear(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>Parametreler  
 `color`  
 Çizim alanı temizlenmiş olduğundan rengi.  
  
##  <a name="colorref_to_d2dcolor"></a>  CRenderTarget::COLORREF_TO_D2DCOLOR  
 GDI renk ve alfa değerleri D2D1_COLOR_F nesnesine dönüştürür.  
  
```  
static D2D1_COLOR_F COLORREF_TO_D2DCOLOR(
    COLORREF color,  
    int nAlpha = 255);
```  
  
### <a name="parameters"></a>Parametreler  
 `color`  
 RGB değeri.  
  
 `nAlpha`  
  
### <a name="return-value"></a>Dönüş Değeri  
 D2D1_COLOR_F değeri.  
  
##  <a name="createcompatiblerendertarget"></a>  CRenderTarget::CreateCompatibleRenderTarget  
 Geçerli işleme hedefiyle uyumlu Ara ekran dışında çizim sırasında kullanmak için yeni bir bit eşlem oluşturma hedef oluşturur.  
  
```  
BOOL CreateCompatibleRenderTarget(
    CBitmapRenderTarget& bitmapTarget,  
    CD2DSizeF sizeDesired = CD2DSizeF(0., 0.), 
    CD2DSizeU sizePixelDesired = CD2DSizeU(0, 0), 
    D2D1_PIXEL_FORMAT* desiredFormat = NULL,  
    D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS options = D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bitmapTarget`  
 Bu yöntem döndürüldüğünde, yeni bir bit eşlem oluşturma hedefi için bir işaretçi adresini içerir. Bu parametre, başlatılmamış olarak geçirilir.  
  
 `sizeDesired`  
 İstenen boyut orijinal olandan farklı olacaksa, aygıttan bağımsız piksel cinsinden yeni işleme hedef hedef oluşturmak veya NULL. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 `sizePixelDesired`  
 İstenen boyut orijinal olandan farklı olacaksa, piksel cinsinden yeni işleme hedef hedef oluşturmak veya NULL. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 `desiredFormat`  
 İstenen piksel biçimi ve yeni alfa modu hedef oluşturmak ya da NULL. Özgün işlemek gibi hedef piksel biçimi için DXGI_FORMAT_UNKNOWN ayarladıysanız ya da bu parametre null ise yeni işleme hedefi aynı piksel biçimi kullanır. Alfa modu D2D1_ALPHA_MODE_UNKNOWN ya bu parametre NULL ise yeni işleme hedefi alfa modunu D2D1_ALPHA_MODE_PREMULTIPLIED için varsayılan olarak. Desteklenen piksel biçimleri ve alfa modları desteklenen piksel biçimleri hakkında daha fazla bilgi için bkz.  
  
 `options`  
 Yeni hedef işlenip işlenmeyeceğini belirten bir değer GDI ile uyumlu olması gerekir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="crendertarget"></a>  CRenderTarget::CRenderTarget  
 CRenderTarget nesnesi oluşturur.  
  
```  
CRenderTarget();
```  
  
##  <a name="destroy"></a>  CRenderTarget::Destroy  
 Bir veya daha fazla kaynakları siler  
  
```  
BOOL Destroy(BOOL bDeleteResources = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bDeleteResources`  
 BDeleteResources TRUE ise, m_lstResources içinde bulunan tüm kaynakları otomatik olarak yok.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür  
  
##  <a name="detach"></a>  CRenderTarget::Detach  
 İşleme hedef arabirimi nesneden çıkarır  
  
```  
ID2D1RenderTarget* Detach ();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi ayrılmış hedef arabirimi işleyebilir.  
  
##  <a name="drawbitmap"></a>  CRenderTarget::DrawBitmap  
 Belirtilen IDWriteTextLayout nesnesi tarafından açıklanan biçimlendirilmiş metin çizer.  
  
```  
void DrawBitmap(
    CD2DBitmap* pBitmap,  
    const CD2DRectF& rectDest,  
    float fOpacity = 1.0,  
    D2D1_BITMAP_INTERPOLATION_MODE interpolationMode = D2D1_BITMAP_INTERPOLATION_MODE_LINEAR,  
    const CD2DRectF* pRectSrc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBitmap`  
 İşlenecek bitmap.  
  
 `rectDest`  
 Aygıttan bağımsız piksel cinsinden işleme hedefin koordinat, bit eşlem çizilen alanın konumu ve boyutu. Dikdörtgen iyi sıralı değil hiçbir şey çizilir, ancak işleme hedefi bir hata durumuna geçmiyor.  
  
 `fOpacity`  
 Bit eşlem için uygulanacak bir geçirgenlik değeri belirten bir değeri 0 .0f ile 1.0f, (dahil) arasında; Bu değer, bit eşlem'in içeriği alfa değerleri karşı çarpılır.  
  
 `interpolationMode`  
 Bit eşlem ölçeklendirilmiş ya da çizim işlem tarafından döndürülen kullanmak için ilişkilendirme modunu.  
  
 `pRectSrc`  
 Boyutunu ve konumunu aygıttan bağımsız piksel cinsinden bit eşlem'ın koordinat, alanın çizmek için bit eşlem içinde.  
  
##  <a name="drawellipse"></a>  CRenderTarget::DrawEllipse  
 Belirtilen vuruş stili kullanılarak belirtilen elips anahat çizer.  
  
```  
void DrawEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `ellipse`  
 Konum ve RADIUS çizileceğini aygıttan bağımsız piksel cinsinden elipsin.  
  
 `pBrush`  
 Elips 's anahat boyamak için kullanılan fırça.  
  
 `fStrokeWidth`  
 Elips 's vuruş kalınlığı. Vuruşun elips 's çerçevesinde ortalanır.  
  
 `strokeStyle`  
 Elips 's anahat, veya bir düz vuruş boyamak için NULL uygulamak için vuruş stili.  
  
##  <a name="drawgeometry"></a>  CRenderTarget::DrawGeometry  
 Belirtilen vuruş stili kullanılarak belirtilen geometri anahat çizer.  
  
```  
void DrawGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pGeometry`  
 Çizmek için geometri.  
  
 `pBrush`  
 Geometri 's vuruş boyamak için kullanılan fırça.  
  
 `fStrokeWidth`  
 Geometri 's vuruş kalınlığı. Vuruşun geometri 's çerçevesinde ortalanır.  
  
 `strokeStyle`  
 Geometri 's anahat, veya bir düz vuruş boyamak için NULL uygulamak için vuruş stili.  
  
##  <a name="drawglyphrun"></a>  CRenderTarget::DrawGlyphRun  
 Belirtilen karakterlerin çizer.  
  
```  
void DrawGlyphRun(
    const CD2DPointF& ptBaseLineOrigin,  
    const DWRITE_GLYPH_RUN& glyphRun,  
    CD2DBrush* pForegroundBrush,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptBaseLineOrigin`  
 CİHAZDAN bağımsız piksel cinsinden karakterlerin temel başlangıcı.  
  
 `glyphRun`  
 İşlenecek karakterlerin.  
  
 `pForegroundBrush`  
 Belirtilen karakterlerin boyamak için kullanılan fırça.  
  
 `measuringMode`  
 Karakter ölçümü biçimlendirildiğinde metin ölçmek için nasıl kullanılacağını gösteren bir değer. DWRITE_MEASURING_MODE_NATURAL varsayılan değerdir.  
  
##  <a name="drawline"></a>  CRenderTarget::DrawLine  
 Belirtilen vuruş stili kullanılarak belirtilen noktaları arasında bir çizgi çizer.  
  
```  
void DrawLine(
    const CD2DPointF& ptFrom,  
    const CD2DPointF& ptTo,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptFrom`  
 CİHAZDAN bağımsız piksel cinsinden satırının başlangıç noktası.  
  
 `ptTo`  
 CİHAZDAN bağımsız piksel cinsinden satırının bitiş noktası.  
  
 `pBrush`  
 Satırın vuruş boyamak için kullanılan fırça.  
  
 `fStrokeWidth`  
 Vuruşun genişliğini belirtir 0.0f eşit veya daha büyük değer. Bu parametre belirtilmezse, 1.0f için varsayılan olarak ayarlanır. Vuruşun satırında ortalanır.  
  
 `strokeStyle`  
 Paint veya düz bir çizgi boyamak için NULL vuruş stili.  
  
##  <a name="drawrectangle"></a>  CRenderTarget::DrawRectangle  
 Belirtilen boyut ve vuruş stili sahip dikdörtgen anahat çizer.  
  
```  
void DrawRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 CİHAZDAN bağımsız piksel cinsinden çizileceğini dikdörtgenin boyutları  
  
 `pBrush`  
 Dikdörtgenin vuruş boyamak için kullanılan fırça  
  
 `fStrokeWidth`  
 Dikdörtgenin vuruşun genişliğini belirtir 0.0f eşit veya daha büyük değer. Vuruşun dikdörtgenin çerçevesinde ortalanır.  
  
 `strokeStyle`  
 Paint ya da bir düz vuruş boyamak için NULL vuruş stili.  
  
##  <a name="drawroundedrectangle"></a>  CRenderTarget::DrawRoundedRectangle  
 Belirtilen vuruş stili kullanılarak belirtilen yuvarlak dikdörtgen anahat çizer.  
  
```  
void DrawRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `rectRounded`  
 CİHAZDAN bağımsız piksel cinsinden çizileceğini yuvarlak dikdörtgen boyutları.  
  
 `pBrush`  
 Yuvarlak dikdörtgen anahat boyamak için kullanılan fırça.  
  
 `fStrokeWidth`  
 Yuvarlak dikdörtgen vuruş kalınlığı. Vuruşun yuvarlak dikdörtgen çerçevesinde ortalanır. 1.0f varsayılan değerdir.  
  
 `strokeStyle`  
 Yuvarlak dikdörtgen vuruş ya da bir düz vuruş boyamak için NULL stili. Varsayılan değer NULL olur.  
  
##  <a name="drawtext"></a>  CRenderTarget::DrawText  
 Belirtilen metni IDWriteTextFormat nesne tarafından sağlanan biçimi bilgileri kullanarak çizer.  
  
```  
void DrawText(
    const CString& strText,  
    const CD2DRectF& rect,  
    CD2DBrush* pForegroundBrush,  
    CD2DTextFormat* textFormat = NULL,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>Parametreler  
 `strText`  
 Unicode karakterler çizmek için bir dizi için bir işaretçi.  
  
 `rect`  
 Boyutunu ve konumunu metni çizilen alanının.  
  
 `pForegroundBrush`  
 Metin boyamak için kullanılan fırça.  
  
 `textFormat`  
 Bir nesne, yani ayrıntıları çizmek için metin, yazı tipi, yazı tipi boyutunu ve akış yönünü biçimlendirmeyi açıklar.  
  
 `options`  
 Metin piksel sınırları eşlemeden ve düzeni dikdörtgene metin kırpılmış belirten bir değer. Metin piksel sınırları unsuruna tutturulmuş ve bu düzen dikdörtgenin kırpılacağını değil gösterir D2D1_DRAW_TEXT_OPTIONS_NONE varsayılan değerdir.  
  
 `measuringMode`  
 Karakter ölçümü biçimlendirildiğinde metin ölçmek için nasıl kullanılacağını gösteren bir değer. DWRITE_MEASURING_MODE_NATURAL varsayılan değerdir.  
  
##  <a name="drawtextlayout"></a>  CRenderTarget::DrawTextLayout  
 Belirtilen IDWriteTextLayout nesnesi tarafından açıklanan biçimlendirilmiş metin çizer.  
  
```  
void DrawTextLayout(
    const CD2DPointF& ptOrigin,  
    CD2DTextLayout* textLayout,  
    CD2DBrush* pBrushForeground,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptOrigin`  
 TextLayout tarafından açıklanan metnin sol üst köşesinin çizileceğini aygıttan bağımsız piksel cinsinden açıklanan noktası.  
  
 `textLayout`  
 Biçimlendirilmiş metin çizmek için. ID2D1Resource devralmayan çizim tüm etkilerinin göz ardı edilir. Fırçalar olmayan ID2D1Resource devralan çizim etkileri varsa, bu yöntem başarısız olur ve işleme hedefi bir hata durumuna sokar.  
  
 `pBrushForeground`  
 Zaten bir çizim efekti (IDWriteTextLayout::SetDrawingEffect yöntemi tarafından belirtilen) olarak ilişkili fırça yok textLayout herhangi bir metin boyamak için kullanılan fırça.  
  
 `options`  
 Metin piksel sınırları eşlemeden ve düzeni dikdörtgene metin kırpılmış belirten bir değer. Metin piksel sınırları unsuruna tutturulmuş ve bu düzen dikdörtgenin kırpılacağını değil gösterir D2D1_DRAW_TEXT_OPTIONS_NONE varsayılan değerdir.  
  
##  <a name="enddraw"></a>  CRenderTarget::EndDraw  
 İşleme hedefte çizim işlemleri sonlandırır ve geçerli hata durumu ve ilişkili etiketleri gösterir.  
  
```  
HRESULT EndDraw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="fillellipse"></a>  CRenderTarget::FillEllipse  
 Belirtilen elips iç boyar.  
  
```  
void FillEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parametreler  
 `ellipse`  
 Konum ve RADIUS aygıttan bağımsız piksel cinsinden boyamak için üç nokta.  
  
 `pBrush`  
 Elipsin iç kısmını boyamak için kullanılan fırça.  
  
##  <a name="fillgeometry"></a>  CRenderTarget::FillGeometry  
 Belirtilen geometri iç boyar.  
  
```  
void FillGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    CD2DBrush* pOpacityBrush = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pGeometry`  
 Boyama geometri.  
  
 `pBrush`  
 Geometri boyamak için kullanılan fırça iç.  
  
 `pOpacityBrush`  
 Geometriye uygulamak için geçirgenlik maskesi; Opaklık maskesi için NULL. Geçirgenlik maskesi (opacityBrush parametre) belirtilen fırça D2D1_EXTEND_MODE_CLAMP için ayarlanmış x ve y genişletmek modlarından sahip bir ID2D1BitmapBrush olması gerekir. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
##  <a name="fillmesh"></a>  CRenderTarget::FillMesh  
 Belirtilen kafes iç boyar.  
  
```  
void FillMesh(
    CD2DMesh* pMesh,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMesh`  
 Boyama kafes.  
  
 `pBrush`  
 Mesh boyamak için kullanılan fırça.  
  
##  <a name="fillopacitymask"></a>  CRenderTarget::FillOpacityMask  
 Fırça için belirtilen bit eşlem tarafından açıklanan opaklık maskesi uygular ve o Fırça oluşturma hedef bölgesi boyamak için kullanır.  
  
```  
void FillOpacityMask(
    CD2DBitmap* pOpacityMask,  
    CD2DBrush* pBrush,  
    D2D1_OPACITY_MASK_CONTENT content,  
    const CD2DRectF& rectDest,  
    const CD2DRectF& rectSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `pOpacityMask`  
 Konum ve RADIUS aygıttan bağımsız piksel cinsinden boyamak için üç nokta.  
  
 `pBrush`  
 DestinationRectangle tarafından belirtilen işleme hedef bölgesini boyamak için kullanılan fırça.  
  
 `content`  
 İçerik geçirgenlik maskesi türü içerir. Değer geçirgenlik maskesi karıştırılan renk alanını belirlemek için kullanılır.  
  
 `rectDest`  
 CİHAZDAN bağımsız piksel cinsinden boyamak için işleme hedef bölgesi.  
  
 `rectSrc`  
 CİHAZDAN bağımsız piksel cinsinden geçirgenlik maskesi olarak kullanılacak bit eşlem bölgesi.  
  
##  <a name="fillrectangle"></a>  CRenderTarget::FillRectangle  
 Belirtilen dikdörtgenin iç boyar.  
  
```  
void FillRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Dikdörtgen boyamak, aygıttan bağımsız piksel cinsinden boyutu.  
  
 `pBrush`  
 Dikdörtgen boyamak için kullanılan fırça iç.  
  
##  <a name="fillroundedrectangle"></a>  CRenderTarget::FillRoundedRectangle  
 Belirtilen yuvarlak dikdörtgen iç boyar.  
  
```  
void FillRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parametreler  
 `rectRounded`  
 Cihaz bağımsız piksel cinsinden boyamak için yuvarlak dikdörtgen boyutları.  
  
 `pBrush`  
 İç yuvarlak dikdörtgen kısmını boyamak için kullanılan fırça.  
  
##  <a name="flush"></a>  CRenderTarget::Flush  
 Tüm bekleyen çizim komutları yürütür.  
  
```  
void Flush(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `tag1`  
 Herhangi bir hata varsa, hatalar veya 0 neden işlemleri çizim etiketi içeriyor. Bu parametre, başlatılmamış olarak geçirilir.  
  
 `tag2`  
 Herhangi bir hata varsa, hatalar veya 0 neden işlemleri çizim etiketi içeriyor. Bu parametre, başlatılmamış olarak geçirilir.  
  
##  <a name="getantialiasmode"></a>  CRenderTarget::GetAntialiasMode  
 Metin çizme işlemleri için geçerli düzgünleştirme modunu alır.  
  
```  
D2D1_ANTIALIAS_MODE GetAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin çizim işlemleri için geçerli düzgünleştirme modu.  
  
##  <a name="getdpi"></a>  CRenderTarget::GetDpi  
 Hedefin nokta / inç (DPI) işleme döndürür  
  
```  
CD2DSizeF GetDpi() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleme hedefin nokta / inç (DPI).  
  
##  <a name="getmaximumbitmapsize"></a>  CRenderTarget::GetMaximumBitmapSize  
 En büyük boyutu işleme hedefi tarafından desteklenen herhangi bir bit eşlem boyutunun aygıta bağımlı birimler (piksel cinsinden) alır  
  
```  
UINT32 GetMaximumBitmapSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Piksel cinsinden işleme hedef tarafından desteklenen herhangi bir bit eşlem boyutu en büyük boyutu  
  
##  <a name="getpixelformat"></a>  CRenderTarget::GetPixelFormat  
 İşleme hedefi piksel biçimi ve alfa modunu alır.  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleme hedefi piksel biçimi ve alfa modu  
  
##  <a name="getpixelsize"></a>  CRenderTarget::GetPixelSize  
 İşleme hedef boyutunu aygıt piksel cinsinden döndürür  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleme hedef aygıt piksel cinsinden boyutu  
  
##  <a name="getrendertarget"></a>  CRenderTarget::GetRenderTarget  
 Döndürür ID2D1RenderTarget arabirimi  
  
```  
ID2D1RenderTarget* GetRenderTarget();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1RenderTarget arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getsize"></a>  CRenderTarget::GetSize  
 CİHAZDAN bağımsız piksel cinsinden işleme hedef boyutunu döndürür  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleme hedef aygıttan bağımsız piksel cinsinden geçerli boyutu  
  
##  <a name="gettags"></a>  CRenderTarget::GetTags  
 Sonraki çizim işlemleri için etiketini alır.  
  
```  
void GetTags(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `tag1`  
 Sonraki çizim işlemleri için ilk etiket içerir. Bu parametre, başlatılmamış olarak geçirilir. NULL belirtilirse, hiçbir değer bu parametre için alınır.  
  
 `tag2`  
 Sonraki çizim işlemleri için ikinci etiket içerir. Bu parametre, başlatılmamış olarak geçirilir. NULL belirtilirse, hiçbir değer bu parametre için alınır.  
  
##  <a name="gettextantialiasmode"></a>  CRenderTarget::GetTextAntialiasMode  
 Metin ve işlemleri çizim simge için geçerli düzgünleştirme modunu alır.  
  
```  
D2D1_TEXT_ANTIALIAS_MODE GetTextAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin ve işlemleri çizim simge için geçerli düzgünleştirme modu.  
  
##  <a name="gettextrenderingparams"></a>  CRenderTarget::GetTextRenderingParams  
 İşleme hedefin geçerli metin işleme seçenekleri alır.  
  
```  
void GetTextRenderingParams(IDWriteRenderingParams** textRenderingParams);
```  
  
### <a name="parameters"></a>Parametreler  
 `textRenderingParams`  
 Bu yöntem döndürüldüğünde, textRenderingParamscontains işleme hedefi için bir işaretçi adresini geçerli metin işleme seçenekleri.  
  
##  <a name="gettransform"></a>  CRenderTarget::GetTransform  
 Belirtilen dönüşüm varolan dönüştürme değiştirme işleme hedef için geçerlidir. Tüm sonraki çizim işlemleri dönüştürülmüş alanı oluşur.  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Parametreler  
 `transform`  
 İşleme hedefe uygulanacak dönüşüm.  
  
##  <a name="issupported"></a>  CRenderTarget::IsSupported  
 İşleme hedefi belirtilen özellikleri destekleyip desteklemediğini belirtir  
  
```  
BOOL IsSupported(const D2D1_RENDER_TARGET_PROPERTIES& renderTargetProperties) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `renderTargetProperties`  
 Test etmek için işleme hedef özellikleri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu işleme hedefi tarafından belirtilen işleme hedef özellikleri destekleniyorsa TRUE; Aksi takdirde FALSE  
  
##  <a name="isvalid"></a>  CRenderTarget::IsValid  
 Denetimleri kaynak geçerlilik  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynağın geçerli ise TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_lstresources"></a>  CRenderTarget::m_lstResources  
 CD2DResource nesnelerine işaretçiler listesi.  
  
```  
CObList m_lstResources;  
```  
  
##  <a name="m_prendertarget"></a>  CRenderTarget::m_pRenderTarget  
 ID2D1RenderTarget nesneyi gösteren bir işaretçi.  
  
```  
ID2D1RenderTarget* m_pRenderTarget;  
```  
  
##  <a name="m_ptextformatdefault"></a>  CRenderTarget::m_pTextFormatDefault  
 Varsayılan metin biçimi içeren CD2DTextFormat nesne için bir işaretçi.  
  
```  
CD2DTextFormat* m_pTextFormatDefault;  
```  
  
##  <a name="operator_id2d1rendertarget_star"></a>  CRenderTarget::operator ID2D1RenderTarget *  
 Döndürür ID2D1RenderTarget arabirimi  
  
```  
operator ID2D1RenderTarget*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1RenderTarget arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="popaxisalignedclip"></a>  CRenderTarget::PopAxisAlignedClip  
 Son eksen hizalı klibi işleme hedef kaldırır. Bu yöntemi çağrıldıktan sonra aşağıdaki klip artık sonraki çizim işlemleri için uygulanır.  
  
```  
void PopAxisAlignedClip();
```  
  
##  <a name="poplayer"></a>  CRenderTarget::PopLayer  
 Çizim işlemleri tarafından son PushLayer belirtilen bir katmana yeniden yönlendirme durakları çağırın.  
  
```  
void PopLayer();
```  
  
##  <a name="pushaxisalignedclip"></a>  CRenderTarget::PushAxisAlignedClip  
 Son eksen hizalı klibi işleme hedef kaldırır. Bu yöntemi çağrıldıktan sonra aşağıdaki klip artık sonraki çizim işlemleri için uygulanır.  
  
```  
void PushAxisAlignedClip(
    const CD2DRectF& rectClip,  
    D2D1_ANTIALIAS_MODE mode = D2D1_ANTIALIAS_MODE_PER_PRIMITIVE);
```  
  
### <a name="parameters"></a>Parametreler  
 `rectClip`  
 Boyutunu ve konumunu kırpma alanının aygıttan bağımsız piksel cinsinden.  
  
 `mode`  
 Piksel sınırları olan küçük rects kenarlarına çizmek için ve küçük Sahne içeriğiyle karıştırmak için kullanılan düzgünleştirme modu. Ne zaman PopAxisAlignedClip yöntemi olarak adlandırılır ve her ilkel katman içinde uygulanmaz sonra karıştırma gerçekleştirilir.  
  
##  <a name="pushlayer"></a>  CRenderTarget::PushLayer  
 Belirtilen katman işleme hedef ekler, böylece PopLayer çağrılıncaya kadar tüm sonraki çizim işlemleri alır.  
  
```  
void PushLayer(
    const D2D1_LAYER_PARAMETERS& layerParameters,  
    CD2DLayer& layer);
```  
  
### <a name="parameters"></a>Parametreler  
 `layerParameters`  
 İçerik sınırları, geometrik maske, opaklık, geçirgenlik maskesi ve düzgünleştirme seçeneklerini.  
  
 `layer`  
 Sonraki çizim işlemleri alır katmanı.  
  
##  <a name="restoredrawingstate"></a>  CRenderTarget::RestoreDrawingState  
 İşleme hedefin çizim durumu, belirtilen ID2D1DrawingStateBlock ayarlar.  
  
```  
void RestoreDrawingState(ID2D1DrawingStateBlock& drawingStateBlock);
```  
  
### <a name="parameters"></a>Parametreler  
 `drawingStateBlock`  
 Yeni Çizim durumunu işleme hedefi.  
  
##  <a name="savedrawingstate"></a>  CRenderTarget::SaveDrawingState  
 Geçerli çizim durumu için belirtilen ID2D1DrawingStateBlock kaydeder.  
  
```  
void SaveDrawingState(ID2D1DrawingStateBlock& drawingStateBlock) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `drawingStateBlock`  
 Bu yöntem döndürüldüğünde, işleme hedefi geçerli çizim durumunu içerir. Bu parametre, yönteme geçirmeden önce başlatılmalıdır.  
  
##  <a name="setantialiasmode"></a>  CRenderTarget::SetAntialiasMode  
 İşleme hedefi düzgünleştirme modunu ayarlar. Düzgünleştirme modu metin ve işlemleri çizim simge hariç tüm sonraki çizim işlemleri için geçerlidir.  
  
```  
void SetAntialiasMode(D2D1_ANTIALIAS_MODE antialiasMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `antialiasMode`  
 Gelecekteki çizim işlemleri için Düzgünleştirme modu.  
  
##  <a name="setdpi"></a>  CRenderTarget::SetDpi  
 Nokta / inç (DPI) işleme hedef ayarlar.  
  
```  
void SetDpi(const CD2DSizeF& sizeDPI);
```  
  
### <a name="parameters"></a>Parametreler  
 `sizeDPI`  
 Değerinden büyük veya sıfıra işleme hedefi yatay/verticalDPI belirten değer.  
  
##  <a name="settags"></a>  CRenderTarget::SetTags  
 Sonraki çizim işlemleri için bir etiket belirtir.  
  
```  
void SetTags(
    D2D1_TAG tag1,  
    D2D1_TAG tag2);
```  
  
### <a name="parameters"></a>Parametreler  
 `tag1`  
 Sonraki çizim işlemleri uygulamak için etiket.  
  
 `tag2`  
 Sonraki çizim işlemleri uygulamak için etiket.  
  
##  <a name="settextantialiasmode"></a>  CRenderTarget::SetTextAntialiasMode  
 Sonraki metni ve karakter çizim işlemleri için kullanılacak düzgünleştirme modunu belirtir.  
  
```  
void SetTextAntialiasMode(D2D1_TEXT_ANTIALIAS_MODE textAntialiasMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `textAntialiasMode`  
 Sonraki metni ve işlemleri çizim simge için kullanılacak düzgünleştirme modu.  
  
##  <a name="settextrenderingparams"></a>  CRenderTarget::SetTextRenderingParams  
 Tüm sonraki metin ve işlemleri çizim karakter uygulanacak metin işleme seçeneklerini belirtir.  
  
```  
void SetTextRenderingParams(IDWriteRenderingParams* textRenderingParams = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `textRenderingParams`  
 Tüm sonraki metin ve işlemleri çizim karakter uygulanacak metin işleme seçenekleri; Geçerli metin işleme seçenekleri temizlemek için NULL.  
  
##  <a name="settransform"></a>  CRenderTarget::SetTransform  
 Belirtilen dönüşüm varolan dönüştürme değiştirme işleme hedef için geçerlidir. Tüm sonraki çizim işlemleri dönüştürülmüş alanı oluşur.  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);  
void SetTransform(const D2D1_MATRIX_3X2_F& transform);
```  
  
### <a name="parameters"></a>Parametreler  
 `transform`  
 İşleme hedefe uygulanacak dönüşüm.  
  
##  <a name="verifyresource"></a>  CRenderTarget::VerifyResource  
 CD2DResource nesnenin geçerliliğini doğrular; varsa kaydetmedi nesnesi oluşturur.  
  
```  
BOOL VerifyResource(CD2DResource* pResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `pResource`  
 CD2DResource nesnesine işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesnenin geçerli ise TRUE; Aksi takdirde FALSE.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
