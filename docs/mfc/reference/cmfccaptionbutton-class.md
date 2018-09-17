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
ms.openlocfilehash: c3e9c9e5122e4bef7007a767fb3225483984e11d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711691"
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton sınıfı
`CMFCCaptionButton` Sınıfı için yerleştirme bölmesinin veya mini çerçevenin başlık çubuğunda görüntülenen bir düğme uygular. Genellikle, framework resim yazılı düğmelerini otomatik olarak oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|CMFCCaptionButton bir nesne oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|Düğme tarafından temsil edilen komut döndürür.|  
|[CMFCCaptionButton::GetIconID](#geticonid)|Düğme ile ilişkili görüntü kimliği döndürür.|  
|[CMFCCaptionButton::GetRect](#getrect)|Düğme tarafından Dolu Dikdörtgen döndürür.|  
|[CMFCCaptionButton::GetSize](#getsize)|Genişlik ve yükseklik düğmenin döndürür.|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Başlık çubuğu yüksekliği mini boyutuna ayarlanmış olup olmadığını gösterir.|  
|[CMFCCaptionButton::Move](#move)|Düğme çizim konumunu ve durumunu göster penceresi ayarlar.|  
|[CMFCCaptionButton::OnDraw](#ondraw)|Başlık düğmesi çizer.|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Başlık çubuğunda mini boyutunu ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Öğesinden bir sınıf türetebilirsiniz [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md) ve korumalı yöntem `AddButton`, resim yazılı düğmelerini bir mini çerçeve penceresine eklemek için.  
  
 CPaneFrameWnd.h komut kimlikleri için resim yazılı düğmelerini iki tür tanımlar:  
  
- Pin düğmesini yerleştirme bölmesi otomatik gizleme modu desteklediğinde görüntüleyen AFX_CAPTION_BTN_PIN.  
  
- Görüntüleyen AFX_CAPTION_BTN_CLOSE bir **Kapat** düğme bölmesi kapalı veya gizli.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCCaptionButton` nesne ve başlık çubuğunda mini boyutunu ayarlayın.  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcaptionbutton.h  
  
##  <a name="cmfccaptionbutton"></a>  CMFCCaptionButton::CMFCCaptionButton  
 Oluşturur bir `CMFCCaptionButton` nesne.  
  
```  
CMFCCaptionButton();

 
CMFCCaptionButton(
    UINT nHit,  
    BOOL bLeftAlign = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
*nHit*<br/>
[in] İlişkili düğme komutu.  
  
*bLeftAlign*<br/>
[in] Düğmenin soluna hizalanıp hizalanmayacağını belirtir.  
  
 İçin olası değerler aşağıdaki tabloda *nHit* parametresi.  
  
|Değer|Komut|  
|-----------|-------------|  
|AFX_HTCLOSE|Kapat düğmesi.|  
|HTMINBUTTON|Simge Durumuna Küçült düğmesi.|  
|HTMAXBUTTON|Ekranı Kapla düğmesi.|  
|AFX_HTLEFTBUTTON|Sol Ok düğmesi.|  
|AFX_HTRIGHTBUTTON|Sağ ok düğmesi.|  
|AFX_HTMENU|Aşağı ok menüsü düğmesi.|  
|HTNOWHERE|Varsayılan değer; herhangi bir komutu temsil eder.|  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, resim yazılı düğmelerini bir komut ile ilişkili değildir.  
  
 Resim yazılı düğmelerini sağa veya sola hizalanır.  
  
##  <a name="gethit"></a>  CMFCCaptionButton::GetHit  
 Düğme tarafından temsil edilen komut döndürür.  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme tarafından temsil edilen komutu.  
  
 Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.  
  
|Değer|Komut|  
|-----------|-------------|  
|AFX_HTCLOSE|Kapat düğmesi.|  
|HTMINBUTTON|Simge Durumuna Küçült düğmesi.|  
|HTMAXBUTTON|Ekranı Kapla düğmesi.|  
|AFX_HTLEFTBUTTON|Sol Ok düğmesi.|  
|AFX_HTRIGHTBUTTON|Sağ ok düğmesi.|  
|AFX_HTMENU|Aşağı ok menüsü düğmesi.|  
|HTNOWHERE|Varsayılan değer; herhangi bir komutu temsil eder.|  
  
##  <a name="geticonid"></a>  CMFCCaptionButton::GetIconID  
 Düğme ile ilişkili görüntü kimliği döndürür.  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*bHorz*<br/>
[in] Sol veya sağ ok görüntü kimlikleri için TRUE; Yukarı veya aşağı ok görüntü kimliği yanlış için.  
  
*bMaximized*<br/>
[in] Ekranı Kapla görüntü kimliği için TRUE; Bir simge durumuna küçült görüntüsü kimliği için FALSE  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görüntü Kimliği  
  
### <a name="remarks"></a>Açıklamalar  
 Parametreler için simge durumuna küçült görüntü kimliklerini belirtin veya resim yazılı düğmelerini en üst düzeye çıkarın.  
  
##  <a name="getrect"></a>  CMFCCaptionButton::GetRect  
 Düğme tarafından Dolu Dikdörtgen döndürür.  
  
```  
virtual CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmenin konumu temsil eden dikdörtgen.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğmeyi göremiyorsanız, döndürülen boyutu 0'dır.  
  
##  <a name="getsize"></a>  CMFCCaptionButton::GetSize  
 Genişlik ve yükseklik düğmenin döndürür.  
  
```  
static CSize GetSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmenin dış boyutları.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen boyutla düğmesi kenar boşluğu bırakma ve kenarlık içerir.  
  
##  <a name="isminiframebutton"></a>  CMFCCaptionButton::IsMiniFrameButton  
 Başlık çubuğu yüksekliği mini boyutuna ayarlanmış olup olmadığını gösterir.  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Mini boyutuna açıklamalı alt yazı ayarlanmışsa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="move"></a>  CMFCCaptionButton::Move  
 Düğme çizim konumunu ve durumunu göster penceresi ayarlar.  
  
```  
void Move(
    const CPoint& ptTo,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
*ptTo*<br/>
[in] Yeni konumu.  
  
*bHide*<br/>
[in] Düğme gösterilip gösterilmeyeceğini belirtir.  
  
##  <a name="ondraw"></a>  CMFCCaptionButton::OnDraw  
 Başlık düğmesi çizer.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    BOOL bActive,  
    BOOL bHorz = TRUE,  
    BOOL bMaximized = TRUE,  
    BOOL bDisabled = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] Düğme için bir cihaz bağlamı işaretçisi.  
  
*bActive*<br/>
[in] Etkin düğmesine görüntü çizme verilmeyeceğini belirtir.  
  
*bHorz*<br/>
[in] Türetilen bir sınıfta kullanılmak üzere ayrılmıştır.  
  
*bMaximized*<br/>
[in] Tam ekran düğmesi bir görüntü çizin verilmeyeceğini belirtir.  
  
*bDevre Dışı*<br/>
[in] Etkinleştirildi düğmesi bir görüntü çizin verilmeyeceğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 *BMaximized* parametresi Simge Durumuna Küçült düğmesi veya bir Ekranı Kapla düğmesi olduğunda kullanılır.  
  
##  <a name="setminiframebutton"></a>  CMFCCaptionButton::SetMiniFrameButton  
 Başlık çubuğunda mini boyutunu ayarlar.  
  
```  
void SetMiniFramebutton(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
*bInternet*<br/>
[in] Mini başlık çubuğu yüksekliği için TRUE; Varsayılan başlık çubuğu yüksekliği için FALSE.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)
