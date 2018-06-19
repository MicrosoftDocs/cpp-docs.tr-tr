---
title: CSmartDockingInfo sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo::CopyTo
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_bUseThemeColorInShading
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrBaseBackground
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneDest
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneSrc
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrTransparent
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_nCentralGroupOffset
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_sizeTotal
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerBmpResID
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerLightBmpResID
dev_langs:
- C++
helpviewer_keywords:
- CSmartDockingInfo [MFC], CopyTo
- CSmartDockingInfo [MFC], m_bUseThemeColorInShading
- CSmartDockingInfo [MFC], m_clrBaseBackground
- CSmartDockingInfo [MFC], m_clrToneDest
- CSmartDockingInfo [MFC], m_clrToneSrc
- CSmartDockingInfo [MFC], m_clrTransparent
- CSmartDockingInfo [MFC], m_nCentralGroupOffset
- CSmartDockingInfo [MFC], m_sizeTotal
- CSmartDockingInfo [MFC], m_uiMarkerBmpResID
- CSmartDockingInfo [MFC], m_uiMarkerLightBmpResID
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3328eacb9789b892a271208193e82546eb73f7e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373673"
---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo sınıfı
Akıllı Yerleştirme işaretçileri görünümünü tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CSmartDockingInfo::CSmartDockingInfo`|Varsayılan Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSmartDockingInfo::CopyTo](#copyto)|Geçerli akıllı yerleştirme bilgisi parametrelerini sağlanan kopyalar [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) nesnesi.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Geçerli tema rengi framework akıllı yerleştirme işaretçileri görüntülediğinde kullanılıp kullanılmayacağını belirtir.|  
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Akıllı Yerleştirme işaretçileri temel arka plan rengini belirtir.|  
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Değiştirir rengini belirtir `m_clrToneSrc` akıllı yerleştirme işaret bit eşlemler içinde.|  
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Akıllı Yerleştirme işaret bit eşlemler rengini belirtir.|  
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Saydam olduklarında akıllı yerleştirme işaret bit eşlemler rengini belirtir.|  
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Merkezi Grup dikdörtgeni sınırlarının akıllı yerleştirme işaretçilerini Merkezi Grup uzaklığını belirtir.|  
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|Bir gruptaki tüm akıllı yerleştirme işaretçileri toplam boyutunu belirtir.|  
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Kaynak kimlikleri framework değil vurgulanmıştır akıllı yerleştirme işaretçileri için kullandığı bir bit eşlem tanımlar.|  
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Kaynak kimlikleri için vurgulanır akıllı yerleştirme işaretçileri çerçevesi kullanır bit eşlem tanımlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Framework tanıtıcıları yerleştirme işaretçileri dahili olarak akıllı. Standart akıllı yerleştirme işaretçileri aşağıda gösterilmiştir:  
  
 ![Akıllı yerleştirme için standart işaretçileri](../../mfc/reference/media/nextsdmarkers.png "nextsdmarkers")  
  
 Bu şekilde, sol taraftaki görüntü etkin bir sekmeye yerleştirme sahip olmayan bir yönetim grubu akıllı yerleştirme işaret gösterir. Ortadaki görüntü sağ kenarı akıllı yerleştirme işaret gösterir. Görüntünün sağdaki etkin bir sekmeye yerleştirme sahip bir yönetim grubu akıllı yerleştirme işaret gösterir. Ana bir bit eşlem Merkezi Grup akıllı yerleştirme işaret var ve beş takma işaret bit eşlemler akıllı.  
  
 Akıllı Yerleştirme işaretçileri aşağıdaki parametreleri özelleştirebilirsiniz:  
  
-   Renk. Örneğin, Şekil işaretlerinde mavi rengi ile herhangi bir kullanıcı tarafından tanımlanan rengi değiştirebilirsiniz.  
  
-   Saydamlık rengi.  
  
-   Bir akıllı yerleştirme işaretinin kenarlık merkezi grubundan sınırlayıcı dikdörtgenin uzaklık.  
  
-   Yönetim grubu temsil eden ana bitmap.  
  
-   Normal ve vurgulanan akıllı yerleştirme işaretçileri temsil eden bit eşlemler.  
  
 Aşağıdaki çizimde özelleştirilmiş akıllı yerleştirme işaretçileri örneği gösterilmektedir:  
  
 ![Akıllı yerleştirme için özel işaretçileri](../../mfc/reference/media/nextsdmarkerscustom.png "nextsdmarkerscustom")  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxDockingManager.h  
  
##  <a name="copyto"></a>  CSmartDockingInfo::CopyTo  
 Geçerli akıllı yerleştirme parametrelerini sağlanan kopyalar [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) nesnesi.  
  
```  
void CopyTo(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `params`  
 Türünde bir nesne `CSmartDockingInfo` geçerli akıllı yerleştirme parametreleri ile doldurulur.  
  
##  <a name="m_busethemecolorinshading"></a>  CSmartDockingInfo::m_bUseThemeColorInShading  
 Geçerli tema rengi framework akıllı yerleştirme işaretçileri görüntülediğinde kullanılıp kullanılmayacağını belirtir.  
  
```  
BOOL m_bUseThemeColorInShading;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, işaretlerinin geçerli Tema rengi kullanılarak çizilir; Aksi takdirde işaretlerinin açık mavi renkle çizilir.  
  
 Varsayılan değer `FALSE` şeklindedir.  
  
##  <a name="m_clrbasebackground"></a>  CSmartDockingInfo::m_clrBaseBackground  
 Akıllı Yerleştirme işaretçileri temel arka plan rengini belirtir.  
  
```  
COLORREF m_clrBaseBackground;  
```  
  
##  <a name="m_clrtonedest"></a>  CSmartDockingInfo::m_clrToneDest  
 Değiştirecek rengini belirtir `m_clrToneSrc` akıllı yerleştirme işaret bit eşlemler içinde.  
  
```  
COLORREF m_clrToneDest;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Program aracılığıyla işaret bit eşlemler rengini değiştirmek için bu değeri ayarlayın. Örneğin, framework ile sağlanan standart işaretlerinin rengini değiştirmek istiyorsanız, bu değer için istenen rengini ayarlayın. Varsayılan olarak, [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) (61, 123, 241) RGB ayarlayın (mavimsi renk).  
  
 Özel işaret rengini değiştirmek için her ikisini de belirtmelisiniz `m_clrToneDest` ve `m_clrToneSrc`.  
  
##  <a name="m_clrtonesrc"></a>  CSmartDockingInfo::m_clrToneSrc  
 Akıllı Yerleştirme işaret bit eşlemler rengini belirtir.  
  
```  
COLORREF m_clrToneSrc;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başka bir renkle özel bir bit eşlem rengini değiştirmek istediğinizde bu değeri ayarlayın. Standart (sağlanan çerçevesi) rengini değiştirirseniz, bu değeri ayarlayın gerekmez işaretçisi.  
  
 Kullanım `(COLORREF)-1` akıllı yerleştirme grubunun bir üyesi boş bırakmak için.  
  
##  <a name="m_clrtransparent"></a>  CSmartDockingInfo::m_clrTransparent  
 Saydam olduklarında akıllı yerleştirme işaret bit eşlemler rengini belirtir.  
  
```  
COLORREF m_clrTransparent;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme grubunda özel işaretleri ve özel bit eşlemler görüntülediğinizde, bu değer ayarlamanız gerekir.  
  
##  <a name="m_ncentralgroupoffset"></a>  CSmartDockingInfo::m_nCentralGroupOffset  
 Akıllı Yerleştirme işaretçileri merkezi grubudur ve merkezi grup dikdörtgeninin sınırları arasındaki uzaklığı belirtir.  
  
```  
int m_nCentralGroupOffset;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özel işaretçileri ve akıllı yerleştirme işaretçileri merkezi grubunun sınırlarını arasındaki varsayılan uzaklığı değiştirmek istiyorsanız, bu değeri belirtin. Varsayılan 5 piksel uzaklığı.  
  
##  <a name="m_sizetotal"></a>  CSmartDockingInfo::m_sizeTotal  
 Yönetim grubundaki tüm akıllı yerleştirme işaretçileri kapsayan bir sınırlayıcı dikdörtgenini toplam boyutunu belirtir.  
  
```  
CSize m_sizeTotal;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `m_sizeTotal` sınırlayıcı dikdörtgenini Merkezi Grup işaretin boyutunu. Özel bit eşlemler için işaretçileri kullanıyorsanız, bu değer belirtmeniz gerekir.  
  
##  <a name="m_uimarkerbmpresid"></a>  CSmartDockingInfo::m_uiMarkerBmpResID  
 Kaynak kimlikleri vurgulanmış olmayan özel akıllı yerleştirme işaretçileri için kullanılan bit eşlem tanımlar.  
  
```  
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu dizi kaynak kimlikleri akıllı yerleştirme işaretçileri temsil eden bit eşlem ile doldurun. `AFX_SD_MARKERS_NUM` şu anda %5 olarak tanımlandı. Dizi gibi doldurun:  
  
 `params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;`  
  
 `params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;`  
  
 `params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;`  
  
 `params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;`  
  
 `params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;`  
  
##  <a name="m_uimarkerlightbmpresid"></a>  CSmartDockingInfo::m_uiMarkerLightBmpResID  
 Kaynak kimlikleri vurgulanan özel akıllı yerleştirme işaretçileri için kullanılan bit eşlem tanımlar.  
  
```  
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu dizi kaynak kimlikleri vurgulanan akıllı yerleştirme işaretçileri temsil eden bit eşlem ile doldurun. `AFX_SD_MARKERS_NUM` şu anda %5 olarak tanımlandı. Dizi gibi doldurun:  
  
 `params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CObject Sınıfı](../../mfc/reference/cobject-class.md)
