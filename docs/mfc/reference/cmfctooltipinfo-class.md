---
title: CMFCToolTipInfo sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb5cb4020b851f3522842951030c8155ee68516f
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037551"
---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo sınıfı
Araç ipuçları görsel görünümünü ilgili bilgileri depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCToolTipInfo  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolTipInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|Araç İpucu balon görünüm olup olmadığını belirten bir Boolean değişkeni.|  
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|Araç İpucu etiketleri kalın yazı tipiyle görüntülenip görüntülenmeyeceğini gösterir Boolean değişkeni.|  
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|Araç İpucu açıklamasını içerip içermediğini gösteren Boole değişkeni.|  
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|Araç İpucu simge içerip içermediğini gösterir Boolean değişkeni.|  
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|Ayırıcı araç ipucu etiketi ve araç ipucu açıklaması arasında görüntülenip görüntülenmeyeceğini gösterir Boolean değişkeni.|  
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|Araç İpucu yuvarlanmış köşeleri olup olmadığını belirten Boolean değişkeni.|  
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|Araç İpucu görünümünü visual Yöneticisi tarafından denetlenen olup olmadığını gösteren bir Boole değişken (bkz [CMFCVisualManager sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)).|  
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|Araç İpucu kenarlığın rengi.|  
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|Araç İpucu arka plan rengi.|  
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|Araç ipucunda Gradyan Dolgu rengi.|  
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|Araç ipucunda metin rengi.|  
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|Araç İpucu gradyan doldurun açı.|  
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|En fazla olası genişliği piksel cinsinden ipucunda açıklaması.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, ve [CTooltipManager sınıfı](../../mfc/reference/ctooltipmanager-class.md) birlikte, uygulamanızda özelleştirilmiş araç ipuçları uygulamak için. Bu araç ipucu sınıflarını kullanma örneği için bkz: [CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md) konu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli üye değişkenlerin değerleri ayarlamak gösterilmiştir `CMFCToolTipInfo` sınıfı.  
  
 [!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtooltipctrl.h  
  
##  <a name="m_bballoontooltip"></a>  CMFCToolTipInfo::m_bBalloonTooltip  
 Tüm araç ipuçlarını görüntüleme stilini belirtir.  
  
```  
BOOL m_bBalloonTooltip;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `TRUE` araç ipuçları balon stili kullanan gösterir `FALSE` araç ipuçları dikdörtgen stil kullandığını gösterir.  
  
##  <a name="m_bboldlabel"></a>  CMFCToolTipInfo::m_bBoldLabel  
 Araç ipucu metninin yazı tipini kalın olup olmadığını belirtir.  
  
```  
BOOL m_bBoldLabel;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye kümesine `TRUE` araç ipucu metni kalın yazı tipiyle görüntülenecek veya `FALSE` olmayan kalın yazı tipiyle araç ipucu etiketleri görüntülemek için.  
  
##  <a name="m_bdrawdescription"></a>  CMFCToolTipInfo::m_bDrawDescription  
 Her araç ipucu açıklama metnini görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
BOOL m_bDrawDescription;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye kümesine `TRUE` açıklamasını görüntülemek için veya `FALSE` açıklama gizlemek için. Çağırarak üzerinde bir araç ipucu açıklaması belirtebilirsiniz [CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)  
  
##  <a name="m_bdrawicon"></a>  CMFCToolTipInfo::m_bDrawIcon  
 Tüm araç ipuçları simgelerini görüntüleme olup olmadığını belirtir.  
  
```  
BOOL m_bDrawIcon;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye kümesine `TRUE` her araç ipucu üzerinde bir simge görüntülemek için veya `FALSE` simgeleri olmadan araç ipuçlarını görüntülemek için.  
  
##  <a name="m_bdrawseparator"></a>  CMFCToolTipInfo::m_bDrawSeparator  
 Her araç ipucu etiketini ve açıklamasını arasında ayırıcı sahip olup olmadığını belirtir.  
  
```  
BOOL m_bDrawSeparator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye kümesine `TRUE` araç ipucu etiket ve açıklama arasında ayırıcı görüntülenecek veya `FALSE` ayırıcı olmadan araç ipuçlarını görüntülemek için.  
  
##  <a name="m_broundedcorners"></a>  CMFCToolTipInfo::m_bRoundedCorners  
 Tüm araç ipuçları yuvarlanmış köşeleri olup olmadığını belirtir.  
  
```  
BOOL m_bRoundedCorners;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye kümesine `TRUE` araç ipuçları, yuvarlatılmış köşelerinde görüntülenecek veya `FALSE` dikdörtgen köşelerinde araç ipuçlarını görüntülemek için.  
  
##  <a name="m_clrborder"></a>  CMFCToolTipInfo::m_clrBorder  
 Tüm araç ipuçları üzerinde kenarlık rengini belirtir.  
  
```  
COLORREF m_clrBorder;  
```  
  
##  <a name="m_clrfill"></a>  CMFCToolTipInfo::m_clrFill  
 Araç İpucu arka plan rengini belirtir.  
  
```  
COLORREF m_clrFill;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) -1 ' dir araç ipucu arka plan rengi `m_clrFill`. Aksi takdirde, `m_clrFill` geçişin başlangıç rengini belirtir ve `m_clrFillGradient` gradyanının Bitiş rengini belirtir. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) gradyan yönünü belirler.  
  
##  <a name="m_clrfillgradient"></a>  CMFCToolTipInfo::m_clrFillGradient  
 Araç ipuçları için gradyan arka planı için Bitiş rengini belirtir.  
  
```  
COLORREF m_clrFillGradient;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `m_clrFillGradient` -1 ' dir gradyan yok yok. Gradyan ilk rengi tarafından aksi halde, belirtilen [CMFCToolTipInfo::m_clrFill](#m_clrfill) ve gradyanı bitiş rengi tarafından belirtilen `m_clrFillGradient`. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) gradyan yönünü belirler.  
  
##  <a name="m_clrtext"></a>  CMFCToolTipInfo::m_clrText  
 Tüm araç ipuçları metin rengini belirtir.  
  
```  
COLORREF m_clrText;  
```  
  
##  <a name="m_ngradientangle"></a>  CMFCToolTipInfo::m_nGradientAngle  
 Gradyan araç ipuçları arka plan üzerinde çizilmiş açıyı belirtir.  
  
```  
int m_nGradientAngle;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_nGradientAngle` araç ipuçları arka planı gradyan yatay uzaklığını derece cinsinden açı belirtir. Varsa `m_nGradientAngle` 0'dır, geçişin soldan sağa çizilir. Varsa `m_nGradientAngle` olan 1 ile 360 arasında geçişin derece bu sayısına göre saat yönünde döndürme. Varsa `m_nGradientAngle` varsayılan değerdir, -1'dir gradyan üstten alta çizilir. Bu ayar aynıdır `m_nGradientAngle` 90.  
  
 [CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` geçişin başlangıç rengini belirtir ve [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` gradyanının Bitiş rengini belirtir. Varsa `m_clrFillGradient` -1 ' dir gradyan yok yok.  
  
##  <a name="m_nmaxdescrwidth"></a>  CMFCToolTipInfo::m_nMaxDescrWidth  
 Her ipucunda görüntülenen açıklama en büyük genişliğini belirtir. Açıklama genişliği belirtilen değeri aşarsa, metin paketlenir.  
  
```  
int m_nMaxDescrWidth;  
```  
  
##  <a name="m_bvislmanagertheme"></a>  CMFCToolTipInfo::m_bVislManagerTheme  
 Uygulamasının visual Yöneticisi tüm araç ipuçları görünümünü denetler olup olmadığını belirtir.  
  
```  
BOOL m_bVislManagerTheme;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `m_bVislManagerTheme` olan `TRUE`, her araç ipucu yeni istekleri [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) ekranda görünen ve değerleri o nesnenin görünümlerini belirlemek için kullanır. önce uygulamanın visual yöneticisinden. Diğer üyeleriyle, [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) göz ardı edilir.  
  
##  <a name="operator_eq"></a>  CMFCToolTipInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *src*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CTooltipManager sınıfı](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipCtrl Sınıfı](../../mfc/reference/cmfctooltipctrl-class.md)
