---
description: 'Daha fazla bilgi edinin: CSmartDockingInfo sınıfı'
title: CSmartDockingInfo sınıfı
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
ms.openlocfilehash: 290f9eef208ceed425739ab26e7811c04309e057
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345140"
---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo sınıfı

Akıllı yerleştirme işaretlerinin görünümünü tanımlar.

## <a name="syntax"></a>Syntax

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
|[CSmartDockingInfo:: CopyTo](#copyto)|Geçerli akıllı yerleştirme bilgileri parametrelerini, belirtilen [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) nesnesine kopyalar.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CSmartDockingInfo:: m_bUseThemeColorInShading](#m_busethemecolorinshading)|Framework akıllı yerleştirme işaretçilerini görüntülediğinde geçerli Tema renginin kullanılıp kullanılmayacağını belirtir.|
|[CSmartDockingInfo:: m_clrBaseBackground](#m_clrbasebackground)|Akıllı yerleştirme işaretlerinin temel arka plan rengini belirtir.|
|[CSmartDockingInfo:: m_clrToneDest](#m_clrtonedest)|`m_clrToneSrc`Akıllı yerleştirme işaretçisi bit eşlemlerinin yerini alan rengi belirtir.|
|[CSmartDockingInfo:: m_clrToneSrc](#m_clrtonesrc)|Akıllı yerleştirme işaretçisi bit eşlemlerinin rengini belirtir.|
|[CSmartDockingInfo:: m_clrTransparent](#m_clrtransparent)|Saydam olduklarında akıllı yerleştirme işaretçisi bit eşlemlerinin rengini belirtir.|
|[CSmartDockingInfo:: m_nCentralGroupOffset](#m_ncentralgroupoffset)|Merkezi grup dikdörtgeninin sınırlarından, akıllı yerleştirme işaretçileri grubunun sapmasını belirtir.|
|[CSmartDockingInfo:: m_sizeTotal](#m_sizetotal)|Bir gruptaki tüm akıllı yerleştirme işaretlerinin toplam boyutunu belirtir.|
|[CSmartDockingInfo:: m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Çerçevenin vurgulanmayan akıllı yerleştirme işaretçileri için kullandığı Bit eşlemlerin kaynak kimliklerini tanımlar.|
|[CSmartDockingInfo:: m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Çerçevenin vurgulanan akıllı yerleştirme işaretçileri için kullandığı Bit eşlemlerin kaynak kimliklerini tanımlar.|

## <a name="remarks"></a>Açıklamalar

Çerçeve, akıllı yerleştirme işaretleyicilerini dahili olarak işler. Aşağıdaki çizimde standart akıllı yerleştirme işaretçileri gösterilmektedir:

![Akıllı yerleştirme için standart işaretçiler](../../mfc/reference/media/nextsdmarkers.png "Akıllı yerleştirme için standart işaretçiler")

Bu şekilde, sol taraftaki görüntüde, etkin bir sekmeye takma özelliği olmayan bir merkezi grup akıllı yerleştirme işaretleyicisi gösterilmektedir. Ortadaki görüntüde sağ kenar akıllı yerleştirme işaretleyicisi gösterilmektedir. Sağdaki görüntüde, etkin bir sekmeye takma özelliği olan bir merkezi grup akıllı yerleştirme işaretleyicisi gösterilmektedir. Merkezi Grup akıllı yerleştirme işaretleyicisi, ana bit eşlem ve beş akıllı yerleştirme işaretçisi bit eşlemiyle bulunur.

Akıllı yerleştirme işaretlerinin aşağıdaki parametrelerini özelleştirebilirsiniz:

- Renk. Örneğin, şekildeki işaretçilerin mavi rengini Kullanıcı tanımlı herhangi bir renkle değiştirebilirsiniz.

- Saydamlık rengi.

- Bir akıllı yerleştirme işaretçisinin, sınırlayıcı dikdörtgenin kenarlarından itibaren merkezi grupta yer aldığı konum.

- Merkezi grubu temsil eden ana bit eşlem.

- Normal ve vurgulanmış akıllı yerleştirme işaretleyicilerini temsil eden bit eşlemler.

Aşağıdaki çizimde, özelleştirilmiş bir akıllı yerleştirme işaretçileri örneği gösterilmektedir:

![Akıllı yerleştirme için özel işaretçiler](../../mfc/reference/media/nextsdmarkerscustom.png "Akıllı yerleştirme için özel işaretçiler")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDockingManager. h

## <a name="csmartdockinginfocopyto"></a><a name="copyto"></a> CSmartDockingInfo:: CopyTo

Geçerli akıllı yerleştirme parametrelerini, belirtilen [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) nesnesine kopyalar.

```cpp
void CopyTo(CSmartDockingInfo& params);
```

### <a name="parameters"></a>Parametreler

*params*<br/>
dışı `CSmartDockingInfo` Geçerli akıllı yerleştirme parametreleriyle doldurulan türünde bir nesne.

## <a name="csmartdockinginfom_busethemecolorinshading"></a><a name="m_busethemecolorinshading"></a> CSmartDockingInfo:: m_bUseThemeColorInShading

Framework akıllı yerleştirme işaretçilerini görüntülediğinde geçerli Tema renginin kullanılıp kullanılmayacağını belirtir.

```
BOOL m_bUseThemeColorInShading;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, işaretçiler geçerli Tema rengi kullanılarak çizilir; Aksi halde işaretçiler açık mavi renkle çizilir.

Varsayılan değer FALSE 'dur.

## <a name="csmartdockinginfom_clrbasebackground"></a><a name="m_clrbasebackground"></a> CSmartDockingInfo:: m_clrBaseBackground

Akıllı yerleştirme işaretlerinin temel arka plan rengini belirtir.

```
COLORREF m_clrBaseBackground;
```

## <a name="csmartdockinginfom_clrtonedest"></a><a name="m_clrtonedest"></a> CSmartDockingInfo:: m_clrToneDest

`m_clrToneSrc`Akıllı yerleştirme işaretçisi bit eşlemlerinin yerini alacak rengi belirtir.

```
COLORREF m_clrToneDest;
```

### <a name="remarks"></a>Açıklamalar

İşaretçi bit eşlemlerinin rengini programlı olarak değiştirmek için bu değeri ayarlayın. Örneğin, çerçevesiyle birlikte sunulan standart işaretleyicilerin rengini değiştirmek istiyorsanız, bu değeri istenen renge ayarlayın. Varsayılan olarak, [CSmartDockingInfo:: M_CLRTONESRC](#m_clrtonesrc) RGB (61, 123, 241) (mavimsi rengi) olarak ayarlanır.

Özel işaretlerin rengini değiştirmek için, hem hem de belirtmeniz gerekir `m_clrToneDest` `m_clrToneSrc` .

## <a name="csmartdockinginfom_clrtonesrc"></a><a name="m_clrtonesrc"></a> CSmartDockingInfo:: m_clrToneSrc

Akıllı yerleştirme işaretçisi bit eşlemlerinin rengini belirtir.

```
COLORREF m_clrToneSrc;
```

### <a name="remarks"></a>Açıklamalar

Bu değeri yalnızca özel bir bit eşlemin rengini başka bir renkle değiştirmek istediğinizde ayarlayın. Standart (çerçeve tarafından belirtilen) işaretin rengini değiştiriyorsanız, bu değeri ayarlamanız gerekmez.

`(COLORREF)-1`Akıllı yerleştirme grubunun bir üyesini boş bırakmak için kullanın.

## <a name="csmartdockinginfom_clrtransparent"></a><a name="m_clrtransparent"></a> CSmartDockingInfo:: m_clrTransparent

Saydam olduklarında akıllı yerleştirme işaretçisi bit eşlemlerinin rengini belirtir.

```
COLORREF m_clrTransparent;
```

### <a name="remarks"></a>Açıklamalar

Yerleştirme grubunda özel işaretleyiciler ve özel bit eşlemler görüntülerken bu değeri ayarlamanız gerekir.

## <a name="csmartdockinginfom_ncentralgroupoffset"></a><a name="m_ncentralgroupoffset"></a> CSmartDockingInfo:: m_nCentralGroupOffset

Akıllı yerleştirme işaretlerinin merkezi grubu ve merkezi grup dikdörtgeninin sınırları arasındaki sapmayı belirtir.

```
int m_nCentralGroupOffset;
```

### <a name="remarks"></a>Açıklamalar

Özel işaretleyiciler arasındaki varsayılan sapmayı ve akıllı yerleştirme işaretçileri merkezi grubunun sınırlarını değiştirmek istiyorsanız bu değeri belirtin. Varsayılan konum 5 pikseldir.

## <a name="csmartdockinginfom_sizetotal"></a><a name="m_sizetotal"></a> CSmartDockingInfo:: m_sizeTotal

Merkezi grupta tüm akıllı yerleştirme işaretleyicilerini kapsayan bir sınırlayıcı dikdörtgenin toplam boyutunu belirtir.

```
CSize m_sizeTotal;
```

### <a name="remarks"></a>Açıklamalar

`m_sizeTotal`Merkezi Grup işaretçisinin sınırlayıcı dikdörtgeninin boyutuna ayarlayın. İşaretçiler için özel bit eşlemler kullanıyorsanız bu değeri belirtmeniz gerekir.

## <a name="csmartdockinginfom_uimarkerbmpresid"></a><a name="m_uimarkerbmpresid"></a> CSmartDockingInfo:: m_uiMarkerBmpResID

Vurgulanmayan özel akıllı yerleştirme işaretçileri için kullanılan bit eşlemlerin kaynak kimliklerini tanımlar.

```
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>Açıklamalar

Bu diziyi, akıllı yerleştirme işaretleyicilerini temsil eden bit eşlemlerin kaynak kimlikleriyle doldurur. AFX_SD_MARKERS_NUM Şu anda 5 olarak tanımlanmıştır. Diziyi şu şekilde doldurursunuz:

```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```

## <a name="csmartdockinginfom_uimarkerlightbmpresid"></a><a name="m_uimarkerlightbmpresid"></a> CSmartDockingInfo:: m_uiMarkerLightBmpResID

Vurgulanan özel akıllı yerleştirme işaretçileri için kullanılan bit eşlemlerin kaynak kimliklerini tanımlar.

```
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>Açıklamalar

Bu diziyi, vurgulanan akıllı yerleştirme işaretleyicilerini temsil eden bit eşlemlerin kaynak kimlikleriyle doldurur. AFX_SD_MARKERS_NUM Şu anda 5 olarak tanımlanmıştır. Diziyi şu şekilde doldurursunuz:

```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)
