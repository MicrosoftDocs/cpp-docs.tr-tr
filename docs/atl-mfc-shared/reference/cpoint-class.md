---
title: CPoint Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
ms.openlocfilehash: a806cfa18119df9beef3e070a65bc238a12580a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317729"
---
# <a name="cpoint-class"></a>CPoint Sınıfı

Windows `POINT` yapısına benzer.

## <a name="syntax"></a>Sözdizimi

```
class CPoint : public tagPOINT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPoint::CPoint](#cpoint)|Bir `CPoint`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPoint::Ofset](#offset)|Değerler ekler `x` ve `y` `CPoint`üyeleri.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CPoint::operatör -](#operator_-)|Bir `CPoint` ve boyut arasındaki farkı veya bir noktanın olumsuzlaması veya iki nokta arasındaki boyut farkını veya negatif bir boyutla mahsup noktasını döndürür.|
|[CPoint::operatör !=](#operator_neq)|İki nokta arasındaki eşitsizliği denetler.|
|[CPoint::operatör +](#operator_add)|Bir `CPoint` ve bir boyutun veya noktanın `CRect` toplamını veya bir boyutun ofsetini verir.|
|[CPoint::operatör +=](#operator_add_eq)|Boyut `CPoint` veya nokta ekleyerek uzaklar.|
|[CPoint::operatör -=](#operator_-_eq)|Bir `CPoint` boyutu veya noktayı çıkararak uzaklıklar.|
|[CPoint::işleç ==](#operator_eq_eq)|İki nokta arasındaki eşitliği denetler.|

## <a name="remarks"></a>Açıklamalar

Ayrıca işlemek `CPoint` için üye işlevleri ve [POINT](/windows/win32/api/windef/ns-windef-point) yapıları içerir.

Bir `CPoint` yapının kullanıldığı `POINT` her yerde nesne kullanılabilir. Bir "boyut" ile etkileşim edebilen bu sınıfın işleçleri, ikisi değiştirilebilir olduğundan [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnelerini veya [SIZE](/windows/win32/api/windef/ns-windef-size) yapılarını kabul eder.

> [!NOTE]
> Bu sınıf `tagPOINT` yapıdan türetilmiştir. (Ad `tagPOINT` `POINT` yapı için daha az kullanılan bir addır.) Bu, `POINT` `x` yapının veri üyelerinin ve `y` `CPoint`, .

> [!NOTE]
> Paylaşılan yardımcı program sınıfları `CPoint`hakkında daha fazla bilgi için (örneğin), [Bkz. Paylaşılan Sınıflar](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagPOINT`

`CPoint`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltypes.h

## <a name="cpointcpoint"></a><a name="cpoint"></a>CPoint::CPoint

Bir `CPoint` nesne inşa eder.

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>Parametreler

*initX*<br/>
`x` Üyenin değerini `CPoint`belirtir.

*initY*<br/>
`y` Üyenin değerini `CPoint`belirtir.

*initPt*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) yapısı `CPoint` veya başlaşış `CPoint`için kullanılan değerleri belirtir.

*initSize*<br/>
Başlatılmış `CPoint`olmak için kullanılan değerleri belirten [BOYUT](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize.](../../atl-mfc-shared/reference/csize-class.md)

*dwPoint*<br/>
Üyeyi `x` *dwPoint'in* düşük sıralı sözcüğüne, üyeyi `y` de *dwPoint'in*yüksek sıralı sözcüğüne ayarlar.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken ler `x` verilmezse ve `y` üyeler 0 olarak ayarlanırsa.

### <a name="example"></a>Örnek

```cpp
CPoint   ptTopLeft(0, 0);
// works from a POINT, too

POINT   ptHere;
ptHere.x = 35;
ptHere.y = 95;

CPoint   ptMFCHere(ptHere);

// works from a SIZE
SIZE   sHowBig;
sHowBig.cx = 300;
sHowBig.cy = 10;

CPoint ptMFCBig(sHowBig);
// or from a DWORD

DWORD   dwSize;
dwSize = MAKELONG(35, 95);

CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```

## <a name="cpointoffset"></a><a name="offset"></a>CPoint::Ofset

Değerler ekler `x` ve `y` `CPoint`üyeleri.

```
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>Parametreler

*xOffset*<br/>
Üyeyi `x` dengelemek için miktarı `CPoint`belirtir.

*yOffset*<br/>
Üyeyi `y` dengelemek için miktarı `CPoint`belirtir.

*Nokta*<br/>
Tutarı [(POINT](/windows/win32/api/windef/ns-windef-point) veya `CPoint`) dengelemek için `CPoint`belirtir.

*Boyutu*<br/>
Tutarı [(BOYUT](/windows/win32/api/windef/ns-windef-size) veya [CSize)](../../atl-mfc-shared/reference/csize-class.md)dengelemek `CPoint`için belirtir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

## <a name="cpointoperator-"></a><a name="operator_eq_eq"></a>CPoint::işleç ==

İki nokta arasındaki eşitliği denetler.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Point yapısı veya `CPoint` nesnesi içerir. [POINT](/windows/win32/api/windef/ns-windef-point)

### <a name="return-value"></a>Dönüş Değeri

Puanlar eşitse sıfırsız; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

## <a name="cpointoperator-"></a><a name="operator_neq"></a>CPoint::operatör !=

İki nokta arasındaki eşitsizliği denetler.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Point yapısı veya `CPoint` nesnesi içerir. [POINT](/windows/win32/api/windef/ns-windef-point)

### <a name="return-value"></a>Dönüş Değeri

Puanlar eşit değilse sıfırsız; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add_eq"></a>CPoint::operatör +=

İlk aşırı yük bir boyut `CPoint`ekler.

```
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize nesnesi](../../atl-mfc-shared/reference/csize-class.md) içerir.

*Nokta*<br/>
[Point](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint nesnesi](../../atl-mfc-shared/reference/cpoint-class.md) içerir.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yük bir nokta `CPoint`ekler.

Her iki durumda da, ek `x` (veya) `cx` `x` sağ operand üyesi ekleyerek `CPoint` ve `y` (veya) `cy`sağ operand `y` üyesine ekleyerek yapılır . `CPoint`

Örneğin, değişkeni 'ye `CPoint(5, -7)` `CPoint(30, 40)` değdiren `CPoint(35, 33)`bir değişkene ekleme

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-_eq"></a>CPoint::operatör -=

İlk aşırı yük bir boyutu. `CPoint`

```
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize nesnesi](../../atl-mfc-shared/reference/csize-class.md) içerir.

*Nokta*<br/>
[Point](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint nesnesi](../../atl-mfc-shared/reference/cpoint-class.md) içerir.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı `CPoint`yük, .'dan bir nokta çıkarır.

Her iki durumda da çıkarma, sağ `x` operand'ın `cx`(veya) `x` üyesinin üyesini çıkararak `CPoint` ve sağ `y` operand'ın (veya) `cy`üyesinin `y` üyesinden `CPoint`çıkarılarak yapılır.

Örneğin, değişkeni `CPoint(5, -7)` içeren `CPoint(30, 40)` bir değişkenden `CPoint(25, 47)`çıkarma.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add"></a>CPoint::operatör +

Bu işleci, `CPoint` bir `CPoint` `CSize` veya nesne tarafından `CRect` dengelemek `CPoint`için veya bir .

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize nesnesi](../../atl-mfc-shared/reference/csize-class.md) içerir.

*Nokta*<br/>
[Point](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint nesnesi](../../atl-mfc-shared/reference/cpoint-class.md) içerir.

*Lprect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir `CPoint` boyutla dengelenir, `CPoint` bir noktayla dengelenir veya `CRect` bir nokta ile mahsup edilir.

### <a name="remarks"></a>Açıklamalar

Örneğin, `CPoint(25, -19)` noktayı bir `CPoint(15, 5)` nokta veya boyutla `CSize(15, 5)` dengelemek için ilk iki aşırı `CPoint(40, -14)`yükten birini kullanmak değeri döndürür.

Bir noktaya dikdörtgen eklemek, noktada belirtilen `x` değerlerve değerlerle `y` dengelendikten sonra dikdörtgeni döndürür. Örneğin, bir nokta `CRect(125, 219, 325, 419)` `CPoint(25, -19)` döner `CRect(150, 200, 350, 400)`tarafından bir dikdörtgen dengelemek için son aşırı yükleme kullanarak.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-"></a>CPoint::operatör -

Bir `CPoint` veya `CSize` nesneyi çıkarmak için ilk iki `CPoint`aşırı yüklemeden birini kullanın.

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Point [POINT](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

*Boyutu*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize nesnesi.](../../atl-mfc-shared/reference/csize-class.md)

*Lprect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A, `CSize` iki nokta arasındaki farktır, bir `CPoint` boyutun inkârı ile `CRect` dengelenir, bir noktanın inkârı `CPoint` veya bir noktanın inkârı ile dengelenir.

### <a name="remarks"></a>Açıklamalar

Üçüncü aşırı yük bir `CRect` inkâr ile `CPoint`dengeler . Son olarak, inkâr etmek `CPoint`için unary işleci kullanın.

Örneğin, iki nokta `CPoint(25, -19)` ve `CPoint(15, 5)` döner `CSize(10, -24)`arasındaki farkı bulmak için ilk aşırı yüklemeyi kullanarak.

A'yı `CSize` `CPoint` çıkarmak yukarıdakiyle aynı hesaplamayı `CPoint` yapar, ancak `CSize` nesne değil, bir nesneyi döndürür. Örneğin, nokta `CPoint(25, -19)` ve boyut `CSize(15, 5)` arasındaki farkı bulmak için ikinci `CPoint(10, -24)`aşırı yüklemeyi kullanarak.

Bir noktadan dikdörtgen çıkarma, noktada belirtilen değerlerin negatifleri `x` ile `y` dikdörtgen ofset döndürür. Örneğin, nokta döner `CRect(125, 200, 325, 400)` `CPoint(25, -19)` `CRect(100, 219, 300, 419)`tarafından dikdörtgen dengelemek için son aşırı yükleme kullanarak.

Bir noktayı inkâr etmek için unary işleci kullanın. Örneğin, nokta `CPoint(25, -19)` döner `CPoint(-25, 19)`ile unary işleci kullanarak.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[POINT Yapısı](/windows/win32/api/windef/ns-windef-point)<br/>
[CRect Sınıfı](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CSize Sınıfı](../../atl-mfc-shared/reference/csize-class.md)
