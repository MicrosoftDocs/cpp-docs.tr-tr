---
title: Csmartdockingınfo sınıfı | Microsoft Docs
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
ms.openlocfilehash: 653be2fb1847403436bccb86807da382ef09cc25
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018216"
---
# <a name="csmartdockinginfo-class"></a>Csmartdockingınfo sınıfı
Akıllı Yerleştirme işaretçilerinin görünümünü tanımlar.  
  
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
|[CSmartDockingInfo::CopyTo](#copyto)|Geçerli akıllı yerleştirme bilgisi parametrelerini sağlanan kopyalar [Csmartdockingınfo](../../mfc/reference/csmartdockinginfo-class.md) nesne.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Framework akıllı yerleştirme işaretçilerinin görüntülediğinde geçerli Tema rengi kullanılıp kullanılmayacağını belirtir.|  
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Akıllı Yerleştirme işaretçilerinin temel arka plan rengini belirtir.|  
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Değiştiren rengini belirtir `m_clrToneSrc` akıllı yerleştirme işaret bit eşlemler olarak.|  
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Akıllı Yerleştirme işaret bit eşlemler rengini belirtir.|  
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Saydam olduklarında akıllı yerleştirme işaret bit eşlemler rengini belirtir.|  
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Akıllı Yerleştirme işaretçilerinin sınırlarını merkezi grubu dikdörtgenin gelen yönetim grubunun uzaklığını belirtir.|  
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|Bir gruptaki tüm akıllı yerleştirme işaretçilerinin toplam boyutunu belirtir.|  
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Kaynak kimlikleri için değil vurgulanır akıllı yerleştirme işaretçilerinin framework kullanan bir bit eşlem tanımlar.|  
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Kaynak kimlikleri için vurgulanan akıllı yerleştirme işaretçilerinin framework kullanan bir bit eşlem tanımlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Framework tutamaçları yerleştirme işaretçilerinin dahili olarak akıllı. Aşağıdaki resimde, standart akıllı yerleştirme işaretçilerinin gösterilmektedir:  
  
 ![Akıllı yerleştirme için standart işaretçileri](../../mfc/reference/media/nextsdmarkers.png "nextsdmarkers")  
  
 Bu çizimde soldaki resim etkin sekmeye yerleşik olmayan bir yönetim grubu akıllı yerleştirme işaret gösterir. Ortada resmi bir sağ kenarı akıllı yerleştirme işaret gösterir. Sağdaki resimde etkin sekmeye yerleştirme sahip bir yönetim grubu akıllı yerleştirme işaret gösterilir. Beş yerleştirme işaret bit eşlemler Akıllı ve ana bir bit eşlem merkezi grubu akıllı yerleştirme işaret vardır.  
  
 Aşağıdaki parametreleri, akıllı yerleştirme işaretçilerinin özelleştirebilirsiniz:  
  
-   Renk. Örneğin, herhangi bir kullanıcı tarafından tanımlanan renk ile işaretlerinin şekilde mavi rengini değiştirebilirsiniz.  
  
-   Saydamlık rengi.  
  
-   Bir akıllı yerleştirme işaretinin merkezi sınır grubunda sınırlayıcı dikdörtgenin uzaklığı.  
  
-   Yönetim grubu temsil eden ana bit eşlem.  
  
-   Normal ve vurgulanan akıllı yerleştirme işaretçilerinin temsil eden bit eşlemler.  
  
 Aşağıdaki çizimde özelleştirilmiş akıllı yerleştirme işaretçilerinin örneği gösterilmektedir:  
  
 ![Akıllı yerleştirme için özel işaretçileri](../../mfc/reference/media/nextsdmarkerscustom.png "nextsdmarkerscustom")  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Csmartdockingınfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxDockingManager.h  
  
##  <a name="copyto"></a>  CSmartDockingInfo::CopyTo  
 Geçerli akıllı yerleştirme parametrelerini sağlanan kopyalar [Csmartdockingınfo](../../mfc/reference/csmartdockinginfo-class.md) nesne.  
  
```  
void CopyTo(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Parametreler  
*params*<br/>
[out] Bir nesne türü `CSmartDockingInfo` geçerli akıllı yerleştirme parametreleri ile doldurulur.  
  
##  <a name="m_busethemecolorinshading"></a>  CSmartDockingInfo::m_bUseThemeColorInShading  
 Framework akıllı yerleştirme işaretçilerinin görüntülediğinde geçerli Tema rengi kullanılıp kullanılmayacağını belirtir.  
  
```  
BOOL m_bUseThemeColorInShading;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise, geçerli Tema rengi kullanarak işaretçileri çizilir; Aksi takdirde işaretçileri, açık mavi renkle çizilir.  
  
 Varsayılan değer FALSE olur.  
  
##  <a name="m_clrbasebackground"></a>  CSmartDockingInfo::m_clrBaseBackground  
 Akıllı Yerleştirme işaretçilerinin temel arka plan rengini belirtir.  
  
```  
COLORREF m_clrBaseBackground;  
```  
  
##  <a name="m_clrtonedest"></a>  CSmartDockingInfo::m_clrToneDest  
 Yerini alacak rengini belirtir `m_clrToneSrc` akıllı yerleştirme işaret bit eşlemler olarak.  
  
```  
COLORREF m_clrToneDest;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Program aracılığıyla işaret bit eşlemler rengini değiştirmek için bu değeri ayarlayın. Örneğin, framework ile sağlanan standart işaretçileri rengini değiştirmek istiyorsanız, bu değeri istediğiniz renge ayarlayın. Varsayılan olarak, [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) RGB (61, 123, 241) olarak ayarlanır (mavimsi renk).  
  
 Özel işaretçileri rengini değiştirmek için her ikisini de belirtmelisiniz `m_clrToneDest` ve `m_clrToneSrc`.  
  
##  <a name="m_clrtonesrc"></a>  CSmartDockingInfo::m_clrToneSrc  
 Akıllı Yerleştirme işaret bit eşlemler rengini belirtir.  
  
```  
COLORREF m_clrToneSrc;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca başka bir rengi ile özel bir bit eşlem rengini değiştirmek istediğinizde bu değeri ayarlayın. Standart (framework tarafından sağlanan) rengini değiştiriyorsanız, bu değeri ayarlamak zorunda değilsiniz işaretçisi.  
  
 Kullanım `(COLORREF)-1` için akıllı yerleştirme grubunun bir üyesi boş bırakın.  
  
##  <a name="m_clrtransparent"></a>  CSmartDockingInfo::m_clrTransparent  
 Saydam olduklarında akıllı yerleştirme işaret bit eşlemler rengini belirtir.  
  
```  
COLORREF m_clrTransparent;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme grubuna özel işaretleri ve özel bit eşlemler görüntülediğinizde, bu değeri ayarlamanız gerekir.  
  
##  <a name="m_ncentralgroupoffset"></a>  CSmartDockingInfo::m_nCentralGroupOffset  
 Akıllı Yerleştirme işaretçilerinin merkezi grubu ve yönetim grubu dikdörtgenin sınırları arasındaki uzaklığı belirtir.  
  
```  
int m_nCentralGroupOffset;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özel işaretler ve akıllı yerleştirme işaretçilerinin merkezi grubu sınırları arasında varsayılan uzaklığı değiştirmek istiyorsanız bu değeri belirtin. Varsayılan uzaklığı 5 pikseldir.  
  
##  <a name="m_sizetotal"></a>  CSmartDockingInfo::m_sizeTotal  
 Yönetim grubundaki tüm akıllı yerleştirme işaretçilerinin kapsayan sınırlayıcı bir dikdörtgen toplam boyutunu belirtir.  
  
```  
CSize m_sizeTotal;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `m_sizeTotal` sınırlayıcı dikdörtgenini merkezi grubu işaret boyutu. Özel bit eşlemler işaretçileri için kullanıyorsanız, bu değeri belirtmek için gereklidir.  
  
##  <a name="m_uimarkerbmpresid"></a>  CSmartDockingInfo::m_uiMarkerBmpResID  
 Kaynak kimliklerini vurgulanmış özel akıllı yerleştirme işaretçilerinin için kullanılan bit eşlem tanımlar.  
  
```  
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu dizi, kaynak kimliklerini akıllı yerleştirme işaretçilerinin temsil eden bir bit eşlem ile doldurun. AFX_SD_MARKERS_NUM şu anda 5 tanımlanır. Dizi gibi doldurun:  
  
```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```
  
##  <a name="m_uimarkerlightbmpresid"></a>  CSmartDockingInfo::m_uiMarkerLightBmpResID  
 Kaynak kimliklerini vurgulanan özel akıllı yerleştirme işaretçilerinin için kullanılan bit eşlem tanımlar.  
  
```  
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu dizi, kaynak kimliklerini vurgulanan akıllı yerleştirme işaretçilerinin temsil eden bir bit eşlem ile doldurun. AFX_SD_MARKERS_NUM şu anda 5 tanımlanır. Dizi gibi doldurun:  
  
```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CObject Sınıfı](../../mfc/reference/cobject-class.md)
