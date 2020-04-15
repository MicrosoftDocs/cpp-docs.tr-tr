---
title: CSmartDockingInfo Sınıfı
ms.date: 11/19/2018
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
ms.openlocfilehash: c0ccb9f728add37230cbfd88cc8f6c9b1696fa2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318233"
---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo Sınıfı

Akıllı yerleştirme işaretlerinin görünümünü tanımlar.

## <a name="syntax"></a>Sözdizimi

```
class CSmartDockingInfo : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CSmartDockingInfo::CSmartDockingInfo`|Varsayılan oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSmartDockingInfo::CopyTo](#copyto)|Geçerli akıllı yerleştirme bilgi parametrelerini sağlanan [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) nesnesine kopyalar.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Çerçeve akıllı yerleştirme işaretleri görüntülendiğinde geçerli tema renginin kullanılıp kullanılmayacağını belirtir.|
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Akıllı yerleştirme işaretçilerin temel arka plan rengini belirtir.|
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Akıllı yerleştirme işaretçisi `m_clrToneSrc` bit eşlemlerinde değiştirilen rengi belirtir.|
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Akıllı yerleştirme işaretçisi bit eşlemlerinin rengini belirtir.|
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Saydam olduklarında akıllı yerleştirme işaretçisi bit eşlemlerinin rengini belirtir.|
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Merkezi grup dikdörtgeninin sınırlarından akıllı yerleştirme işaretçileri merkezi grubun ofset belirtir.|
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|Bir gruptaki tüm akıllı yerleştirme işaretçilerinin toplam boyutunu belirtir.|
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Çerçevenin vurgulanmamış akıllı yerleştirme işaretçileri için kullandığı bit eşlemlerinin kaynak tanımlarını tanımlar.|
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Çerçevenin vurgulanan akıllı yerleştirme işaretçileri için kullandığı bit eşlemlerinin kaynak tanımlarını tanımlar.|

## <a name="remarks"></a>Açıklamalar

Çerçeve, akıllı yerleştirme işaretlerini dahili olarak işler. Aşağıdaki resimde standart akıllı yerleştirme işaretleri gösterilmektedir:

![Akıllı yerleştirme için standart işaretler](../../mfc/reference/media/nextsdmarkers.png "Akıllı yerleştirme için standart işaretler")

Bu şekilde, soldaki resimde, etkin bir sekmeye yerleştirme olmayan merkezi bir grup akıllı yerleştirme işaretçisi gösterilmektedir. Ortadaki görüntü, sağ kenarlı akıllı yerleştirme işaretçisini gösterir. Sağdaki görüntü, etkin bir sekmeye yerleştirme özelliğine sahip merkezi bir grup akıllı yerleştirme işaretçisini gösterir. Merkezi grup akıllı yerleştirme işaretçisi bir ana bit eşlemi ve beş akıllı yerleştirme işaretçisi bit eşlemi vardır.

Akıllı yerleştirme işaretçilerinin aşağıdaki parametrelerini özelleştirebilirsiniz:

- Renk. Örneğin, şekildeki işaretçilerin mavi rengini kullanıcı tanımlı herhangi bir renkle değiştirebilirsiniz.

- Saydamlık rengi.

- Sınırlayan dikdörtgenin sınırından merkezi gruptaki akıllı yerleştirme işaretinin mahsup uyruşturu.

- Merkezi grubu temsil eden ana bit eşlemi.

- Normal ve vurgulanan akıllı yerleştirme işaretçilerini temsil eden bit eşlemleri.

Aşağıdaki resimde, özelleştirilmiş akıllı yerleştirme işaretlerinin bir örneği gösterilmektedir:

![Akıllı yerleştirme için özel işaretler](../../mfc/reference/media/nextsdmarkerscustom.png "Akıllı yerleştirme için özel işaretler")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDockingManager.h

## <a name="csmartdockinginfocopyto"></a><a name="copyto"></a>CSmartDockingInfo::CopyTo

Geçerli akıllı yerleştirme parametrelerini sağlanan [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) nesnesine kopyalar.

```
void CopyTo(CSmartDockingInfo& params);
```

### <a name="parameters"></a>Parametreler

*params*<br/>
[çıkış] Geçerli akıllı `CSmartDockingInfo` yerleştirme parametreleriyle doldurulan türde bir nesne.

## <a name="csmartdockinginfom_busethemecolorinshading"></a><a name="m_busethemecolorinshading"></a>CSmartDockingInfo::m_bUseThemeColorInShading

Çerçeve akıllı yerleştirme işaretleri görüntülendiğinde geçerli tema renginin kullanılıp kullanılmayacağını belirtir.

```
BOOL m_bUseThemeColorInShading;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, işaretçiler geçerli tema rengi kullanılarak çizilir; aksi takdirde işaretleri açık mavi bir renk ile çizilir.

Varsayılan değer FALSE'dur.

## <a name="csmartdockinginfom_clrbasebackground"></a><a name="m_clrbasebackground"></a>CSmartDockingInfo::m_clrBaseBackground

Akıllı yerleştirme işaretçilerin temel arka plan rengini belirtir.

```
COLORREF m_clrBaseBackground;
```

## <a name="csmartdockinginfom_clrtonedest"></a><a name="m_clrtonedest"></a>CSmartDockingInfo::m_clrToneDest

Akıllı yerleştirme işaretçisi `m_clrToneSrc` bit eşlemlerinde yerini alacak rengi belirtir.

```
COLORREF m_clrToneDest;
```

### <a name="remarks"></a>Açıklamalar

İşaretleyici biteşlerinin rengini programlı olarak değiştirmek için bu değeri ayarlayın. Örneğin, çerçeveyle sağlanan standart işaretçilerin rengini değiştirmek istiyorsanız, bu değeri istenen renge ayarlayın. Varsayılan olarak, [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) RGB (61, 123, 241) (mavimsi bir renk) olarak ayarlanır.

Özel işaretçilerin rengini değiştirmek için hem `m_clrToneDest` `m_clrToneSrc`de .

## <a name="csmartdockinginfom_clrtonesrc"></a><a name="m_clrtonesrc"></a>CSmartDockingInfo::m_clrToneSrc

Akıllı yerleştirme işaretçisi bit eşlemlerinin rengini belirtir.

```
COLORREF m_clrToneSrc;
```

### <a name="remarks"></a>Açıklamalar

Bu değeri yalnızca özel bir bit eşleminin rengini başka bir renkle değiştirmek istediğinizde ayarlayın. Standart (çerçeve sağlanan) işaretçisinin rengini değiştiriyorsanız, bu değeri ayarlamanız gerekmez.

Akıllı `(COLORREF)-1` yerleştirme grubunun bir üyesini boş bırakmak için kullanın.

## <a name="csmartdockinginfom_clrtransparent"></a><a name="m_clrtransparent"></a>CSmartDockingInfo::m_clrTransparent

Saydam olduklarında akıllı yerleştirme işaretçisi bit eşlemlerinin rengini belirtir.

```
COLORREF m_clrTransparent;
```

### <a name="remarks"></a>Açıklamalar

Yerleştirme grubunda özel işaretçileri ve özel bit eşlemleri görüntülerken bu değeri ayarlamanız gerekir.

## <a name="csmartdockinginfom_ncentralgroupoffset"></a><a name="m_ncentralgroupoffset"></a>CSmartDockingInfo::m_nCentralGroupOffset

Akıllı yerleştirme işaretçileri merkezi grup ve merkezi grup dikdörtgen sınırları arasındaki ofset belirtir.

```
int m_nCentralGroupOffset;
```

### <a name="remarks"></a>Açıklamalar

Özel işaretçiler ve akıllı yerleştirme işaretleri merkezi grubun sınırları arasında varsayılan ofset değiştirmek istiyorsanız bu değeri belirtin. Varsayılan ofset 5 pikseldir.

## <a name="csmartdockinginfom_sizetotal"></a><a name="m_sizetotal"></a>CSmartDockingInfo::m_sizeTotal

Merkezi gruptaki tüm akıllı yerleştirme işaretlerini içine alan sınırlayıcı bir dikdörtgenin toplam boyutunu belirtir.

```
CSize m_sizeTotal;
```

### <a name="remarks"></a>Açıklamalar

Merkezi `m_sizeTotal` grup işaretçisinin sınırlayıcı dikdörtgenboyutuna ayarlayın. İşaretçiler için özel bit eşlemleri kullanıyorsanız, bu değeri belirtmeniz gerekir.

## <a name="csmartdockinginfom_uimarkerbmpresid"></a><a name="m_uimarkerbmpresid"></a>CSmartDockingInfo::m_uiMarkerBmpResID

Vurgusuz özel akıllı yerleştirme işaretleri için kullanılan bit eşlemlerinin kaynak tanımlarını tanımlar.

```
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>Açıklamalar

Bu diziyi, akıllı yerleştirme işaretçilerini temsil eden bit eşlemlerinin kaynak işlemileriyle doldurun. AFX_SD_MARKERS_NUM şu anda 5 olarak tanımlanır. Diziyi aşağıdaki gibi doldurursunuz:

```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```

## <a name="csmartdockinginfom_uimarkerlightbmpresid"></a><a name="m_uimarkerlightbmpresid"></a>CSmartDockingInfo::m_uiMarkerLightBmpResID

Vurgulanan özel akıllı yerleştirme işaretleri için kullanılan bit eşlemlerinin kaynak tanımlarını tanımlar.

```
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>Açıklamalar

Bu diziyi, vurgulanan akıllı yerleştirme işaretçilerini temsil eden bit eşlemlerinin kaynak işlemileriyle doldurun. AFX_SD_MARKERS_NUM şu anda 5 olarak tanımlanır. Diziyi aşağıdaki gibi doldurursunuz:

```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)
