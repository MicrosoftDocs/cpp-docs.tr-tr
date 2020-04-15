---
title: CSize Sınıfı
ms.date: 10/18/2018
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
ms.openlocfilehash: 6d1b82e3f60428e3a778709dc69de983a7f886bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317670"
---
# <a name="csize-class"></a>CSize Sınıfı

Göreceli bir koordinat veya konum uygulayan Windows [SIZE](/windows/win32/api/windef/ns-windef-size) yapısına benzer.

## <a name="syntax"></a>Sözdizimi

```
class CSize : public tagSIZE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSize::CSize](#csize)|Bir `CSize` nesne inşa eder.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CSize::operatör -](#operator_-)|İki boyutu çıkarır.|
|[CSize::operatör !=](#operator_neq)|Bir boyut arasındaki `CSize` eşitsizliği denetler.|
|[CSize::operatör +](#operator_add)|İki boyut ekler.|
|[CSize::operatör +=](#operator_add_eq)|Bir boyut `CSize`ekler.|
|[CSize::operatör -=](#operator_-_eq)|Bir boyutu `CSize`çıkarır.|
|[CSize::işleç ==](#operator_eq_eq)|Bir boyut arasında `CSize` eşitlik için denetler.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf `SIZE` yapıdan türetilmiştir. Bu, `CSize` bir parametrede bir `SIZE` parametreyi geçebileceğiniz ve yapının `SIZE` veri üyelerinin `CSize`erişilebilir veri üyeleri olduğu anlamına gelir.

(ve) `cx` `cy` `SIZE` `CSize`üyeleri kamuya açıktır. Buna ek `CSize` olarak, `SIZE` yapıişlemek için üye işlevleri uygular.

> [!NOTE]
> Paylaşılan yardımcı program sınıfları `CSize`hakkında daha fazla bilgi için (örneğin), [Bkz. Paylaşılan Sınıflar](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagSIZE`

`CSize`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltypes.h

## <a name="csizecsize"></a><a name="csize"></a>CSize::CSize

Bir `CSize` nesne inşa eder.

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>Parametreler

*initCX*<br/>
Üyeyi `cx` . `CSize`

*initCY*<br/>
Üyeyi `cy` . `CSize`

*initSize*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size) yapısı `CSize` veya nesnesini `CSize`başlatmaiçin kullanılır.

*initPt*<br/>
[Başlangıç](/windows/win32/api/windef/ns-windef-point) için `CPoint` kullanılan POINT `CSize`yapısı veya nesnesi.

*dwSize*<br/>
DWORD, ilk `CSize`olarak kullanılır. Düşük sıralı sözcük `cx` üyedir ve üst düzey `cy` sözcük üyedir.

### <a name="remarks"></a>Açıklamalar

Hiçbir bağımsız değişken `cx` verilirse ve `cy` sıfıra başlatIf.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

## <a name="csizeoperator-"></a><a name="operator_eq_eq"></a>CSize::işleç ==

İki boyut arasındaki eşitliği denetler.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Açıklamalar

Boyutlar eşitse sıfırsız döndürür, otherwize 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

## <a name="csizeoperator-"></a><a name="operator_neq"></a>CSize::operatör !=

İki boyut arasındaki eşitsizliği denetler.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Açıklamalar

Boyutlar eşit değilse sıfırsız döndürür, aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add_eq"></a>CSize::operatör +=

Bu `CSize`bir boyut ekler.

```
void operator+=(SIZE size) throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-_eq"></a>CSize::operatör -=

Bu `CSize`bir boyut çıkarır.

```
void operator-=(SIZE size) throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add"></a>CSize::operatör +

Bu işleçler bu `CSize` değeri parametre değerine ekler.

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>Açıklamalar

Tek tek işleçlerin aşağıdaki açıklamalarına bakın:

- **operatör +(** *boyut* **)**

  Bu işlem `CSize` iki değer ekler.

- **işleç +(** *nokta)* **)**

  Bu işlem, bir [POINT](/previous-versions/dd162805\(v=vs.85\)) (veya [CPoint)](../../atl-mfc-shared/reference/cpoint-class.md)değerini `CSize` bu değere göre dengeler (taşır). Bu `cx` `CSize` `cy` değerin üyeleri ve `POINT` üyeleri, `y` değerin veri üyelerine `x` eklenir. Bir [SIZE](/windows/win32/api/windef/ns-windef-size) parametresi alan [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) sürümüne benzer.

- **operatör +(** *lpRect* **)**

   Bu işlem, bir [RECT](/previous-versions/dd162897\(v=vs.85\)) (veya [CRect)](../../atl-mfc-shared/reference/crect-class.md)değerini `CSize` bu değerle dengeler (taşır). Bu `cx` `CSize` `cy` değerin üyeleri ve `left`üyeleri, `top` `right` `RECT` , `bottom` , ve değerin veri üyelerine eklenir. [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) bir [SIZE](/windows/win32/api/windef/ns-windef-size) parametresi alan sürümüne benzer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-"></a>CSize::operatör -

Bu işleçlerin ilk üçü `CSize` bu değeri parametre nin değerine çıkarır.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Açıklamalar

Dördüncü işleç, unary eksi, `CSize` değerişareti değiştirir. Tek tek işleçlerin aşağıdaki açıklamalarına bakın:

- **işleç -(** *boyutu* **)**

  Bu işlem iki `CSize` değer çıkarır.

- **işleç -(** *nokta)* **)**

  Bu işlem, bir [POINT](/previous-versions/dd162805\(v=vs.85\)) veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) değerini bu `CSize` değerin tersi olan katkı maddesiyle dengeler (taşır). Bu `cx` `CSize` `cy` değerin `x` ve değerin `y` veri üyeleri `POINT` çıkarılır. Bir [SIZE](/windows/win32/api/windef/ns-windef-size) parametresi alır [CPoint:operator sürümüne](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) benzer.

- **işleç -(** *lpRect* **)**

  Bu işlem, bir [RECT](/previous-versions/dd162897\(v=vs.85\)) veya [CRect](../../atl-mfc-shared/reference/crect-class.md) değerini bu `CSize` değerin tersi olan katkı maddesi yle dengeler (taşır). Bu `cx` `CSize` `cy` değerin üyeleri ve `left` `top`üyeleri, `RECT` , `right`, `bottom` ve değerin veri üyelerinden çıkarılır. Bir [SIZE](/windows/win32/api/windef/ns-windef-size) parametresi alır [CRect sürümüne benzer::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-) .

- **işleç -()**

  Bu işlem, bu `CSize` değerin ters katkı sını döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRect Sınıfı](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CPoint Sınıfı](../../atl-mfc-shared/reference/cpoint-class.md)
