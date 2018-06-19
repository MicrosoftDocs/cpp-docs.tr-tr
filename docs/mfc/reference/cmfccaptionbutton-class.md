---
title: CMFCCaptionButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec36bfc82064272e165ea274cd127cc626731643
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368783"
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton sınıfı
`CMFCCaptionButton` Sınıfı bir takma bölmesi veya bir kısa çerçeve penceresi başlık çubuğunda görüntülenen bir düğme uygular. Genellikle, framework resim yazısı düğmeleri otomatik olarak oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|CMFCCaptionButton nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|Komut çubuğu ile temsil edilen döndürür.|  
|[CMFCCaptionButton::GetIconID](#geticonid)|İlişkili düğme görüntü kimliği döndürür.|  
|[CMFCCaptionButton::GetRect](#getrect)|Düğme tarafından Dolu Dikdörtgen döndürür.|  
|[CMFCCaptionButton::GetSize](#getsize)|Genişlik ve yükseklik düğmesinin döndürür.|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Başlık çubuğu yüksekliği mini boyutuna ayarlanmış olup olmadığını gösterir.|  
|[CMFCCaptionButton::Move](#move)|Düğme çizim konumu ve pencere Göster durumunu ayarlar.|  
|[CMFCCaptionButton::OnDraw](#ondraw)|Resim yazısı düğmesini çizer.|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Başlık çubuğu mini boyutunu ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Öğesinden bir sınıf türetin [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md) ve korumalı yöntem kullanmak `AddButton`, mini çerçeve penceresi için resim yazısı düğmeleri eklemek için.  
  
 Komut kimlikleri için resim yazısı düğmeleri iki tür CPaneFrameWnd.h tanımlar:  
  
- `AFX_CAPTION_BTN_PIN`, yerleştirme bölmesinde otomatik olarak Gizle modunu destekliyorsa, PIN düğmesi görüntüler.  
  
- `AFX_CAPTION_BTN_CLOSE`, görüntüleyen bir **Kapat** düğmesini bölmesi kapalı veya gizli.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCCaptionButton` nesne ve başlık çubuğunda mini boyutunu ayarlayın.  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcaptionbutton.h  
  
##  <a name="cmfccaptionbutton"></a>  CMFCCaptionButton::CMFCCaptionButton  
 Oluşturan bir `CMFCCaptionButton` nesnesi.  
  
```  
CMFCCaptionButton();

 
CMFCCaptionButton(
    UINT nHit,  
    BOOL bLeftAlign = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nHit`  
 İlişkili düğme komutu.  
  
 [in] `bLeftAlign`  
 Düğme sola hizalı olup olmadığını belirtir.  
  
 İçin olası değerler aşağıdaki tabloda listelenmektedir `nHit` parametresi.  
  
|Değer|Komut|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Kapat düğmesi.|  
|`HTMINBUTTON`|Simge Durumuna Küçült düğmesi.|  
|`HTMAXBUTTON`|Ekranı Kapla düğmesi.|  
|`AFX_HTLEFTBUTTON`|Sol ok düğmesine.|  
|`AFX_HTRIGHTBUTTON`|Sağ ok düğmesine.|  
|`AFX_HTMENU`|Aşağı ok menü düğmesi.|  
|`HTNOWHERE`|Varsayılan değer; bir komutu temsil eder.|  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, resim yazısını düğmeleri bir komutla ilişkili değildir.  
  
 Resim yazısı düğmeleri sağa veya sola hizalanır.  
  
##  <a name="gethit"></a>  CMFCCaptionButton::GetHit  
 Komut çubuğu ile temsil edilen döndürür.  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme tarafından temsil edilen komutu.  
  
 Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.  
  
|Değer|Komut|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Kapat düğmesi.|  
|`HTMINBUTTON`|Simge Durumuna Küçült düğmesi.|  
|`HTMAXBUTTON`|Ekranı Kapla düğmesi.|  
|`AFX_HTLEFTBUTTON`|Sol ok düğmesine.|  
|`AFX_HTRIGHTBUTTON`|Sağ ok düğmesine.|  
|`AFX_HTMENU`|Aşağı ok menü düğmesi.|  
|`HTNOWHERE`|Varsayılan değer; bir komutu temsil eder.|  
  
##  <a name="geticonid"></a>  CMFCCaptionButton::GetIconID  
 İlişkili düğme görüntü kimliği döndürür.  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bHorz`  
 `TRUE` Sol veya sağ ok resim kimlikleri için; `FALSE` için yukarı veya aşağı ok resim kimlikleri.  
  
 [in] `bMaximized`  
 `TRUE` Ekranı Kapla görüntü kimliği için; `FALSE` kimliği için bir simge durumuna küçült görüntü  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görüntü kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametreleri simge durumuna küçült resim kimlikleri belirtin veya resim yazısı düğmeleri en üst düzeye çıkarın.  
  
##  <a name="getrect"></a>  CMFCCaptionButton::GetRect  
 Düğme tarafından Dolu Dikdörtgen döndürür.  
  
```  
virtual CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmesinin konumunu temsil eden dikdörtgen.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme göremiyorsanız, döndürülen boyutu 0'dır.  
  
##  <a name="getsize"></a>  CMFCCaptionButton::GetSize  
 Genişlik ve yükseklik düğmesinin döndürür.  
  
```  
static CSize GetSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmenin dış boyutları.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen boyut düğmesi kenar boşluğu ve kenarlık içerir.  
  
##  <a name="isminiframebutton"></a>  CMFCCaptionButton::IsMiniFrameButton  
 Başlık çubuğu yüksekliği mini boyutuna ayarlanmış olup olmadığını gösterir.  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Resim yazısını mini boyutuna ayarlanır Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="move"></a>  CMFCCaptionButton::Move  
 Düğme çizim konumu ve pencere Göster durumunu ayarlar.  
  
```  
void Move(
    const CPoint& ptTo,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `ptTo`  
 Yeni konumu.  
  
 [in] `bHide`  
 Düğme görüntülenip görüntülenmeyeceğini belirtir.  
  
##  <a name="ondraw"></a>  CMFCCaptionButton::OnDraw  
 Resim yazısı düğmesini çizer.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    BOOL bActive,  
    BOOL bHorz = TRUE,  
    BOOL bMaximized = TRUE,  
    BOOL bDisabled = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Düğme için cihaz bağlamı işaretçi.  
  
 [in] `bActive`  
 Etkin düğmeye resim çizme görüntülenmeyeceğini belirtir.  
  
 [in] `bHorz`  
 Bir türetilmiş sınıfta kullanılmak üzere ayrılmıştır.  
  
 [in] `bMaximized`  
 Tam ekran düğmesi resim çizme görüntülenmeyeceğini belirtir.  
  
 [in] `bDisabled`  
 Etkin düğmesi resim çizme görüntülenmeyeceğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 `bMaximized` Parametresi Simge Durumuna Küçült düğmesi veya bir Ekranı Kapla düğmesi olduğunda kullanılır.  
  
##  <a name="setminiframebutton"></a>  CMFCCaptionButton::SetMiniFrameButton  
 Başlık çubuğu mini boyutunu ayarlar.  
  
```  
void SetMiniFramebutton(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bSet`  
 `TRUE` Mini başlık çubuğu yüksekliği için; `FALSE` varsayılan başlık çubuğu yükseklik.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)
