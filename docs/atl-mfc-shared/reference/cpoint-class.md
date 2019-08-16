---
title: CPoint sınıfı
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
ms.openlocfilehash: b7c13ef8b9656c5c2fa6a90fefca0d9babbe1c84
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491224"
---
# <a name="cpoint-class"></a>CPoint sınıfı

Windows `POINT` yapısına benzer.

## <a name="syntax"></a>Sözdizimi

```
class CPoint : public tagPOINT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPoint:: CPoint](#cpoint)|Bir `CPoint`oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPoint:: kayması](#offset)|, `x` Ve `y` üyelerine değerekler.`CPoint`|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CPoint:: operator-](#operator_-)|Bir `CPoint` ve boyutunun veya bir noktanın değilinin veya iki nokta arasındaki boyut farkının veya negatif bir boyuta göre farkın farkını döndürür.|
|[CPoint:: operator! =](#operator_neq)|İki punto arasındaki eşitsizlik için denetim gerçekleştirir.|
|[CPoint:: operator +](#operator_add)|Bir `CPoint` , bir boyut veya noktanın toplamını `CRect` ya da bir boyut ile bir konum döndürür.|
|[CPoint:: operator + =](#operator_add_eq)|Bir `CPoint` boyut veya nokta ekleyerek uzaklıkları.|
|[CPoint:: operator-=](#operator_-_eq)|Bir `CPoint` boyut veya noktayı çıkararak uzaklıkları.|
|[CPoint:: operator = =](#operator_eq_eq)|İki noktayla eşitlik olup olmadığını denetler.|

## <a name="remarks"></a>Açıklamalar

Ayrıca, işleme `CPoint` ve [işaret](/windows/win32/api/windef/ns-windef-point) yapılarına üye işlevleri de içerir.

Bir `CPoint` nesne, bir `POINT` yapının kullanıldığı her yerde kullanılabilir. Bu sınıfın "Boyut" ile etkileşime geçen işleçleri [CSize](../../atl-mfc-shared/reference/csize-class.md) nesneleri veya [Boyut](/windows/win32/api/windef/ns-windef-size) yapılarını kabul eder, çünkü ikisi birlikte değiştirilebilir.

> [!NOTE]
>  Bu sınıf `tagPOINT` yapıdan türetilir. (Ad `tagPOINT` , `POINT` yapı için daha yaygın olarak kullanılan bir addır.) Bu, `POINT` `y`yapının veri üyelerinin `CPoint`ve ' nin erişilebilir veri üyeleri olduğu anlamına gelir. `x`

> [!NOTE]
>  Paylaşılan yardımcı sınıflar (gibi `CPoint`) hakkında daha fazla bilgi için bkz. [paylaşılan sınıflar](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagPOINT`

`CPoint`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltypes. h

##  <a name="cpoint"></a>CPoint:: CPoint

Bir `CPoint` nesnesi oluşturur.

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>Parametreler

*ınitx*<br/>
`x`Üyesinindeğerinibelirtir. `CPoint`

*Çevre*<br/>
`y`Üyesinindeğerinibelirtir. `CPoint`

*ınitpt*<br/>
Başlangıç [noktası](/windows/win32/api/windef/ns-windef-point) yapısı `CPoint` veya başlatmak `CPoint`için kullanılan değerleri belirtir.

*initSize*<br/>
Başlatmak`CPoint`için kullanılan değerleri belirten [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) .

*dwPoint*<br/>
Üyeyi, *dwPoint* 'in alt-sıra sözcüğünün ve üyenindwPoint'inüst-sırasözcüğüne`y`ayarlar. `x`

### <a name="remarks"></a>Açıklamalar

Hiçbir bağımsız değişken verilmezse `x` ve `y` Üyeler 0 olarak ayarlanır.

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

##  <a name="offset"></a>CPoint:: kayması

, `x` Ve `y` üyelerine değerekler.`CPoint`

```
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>Parametreler

*Xsapmayı*<br/>
`x` Üyesinin`CPoint`kaydırılacağı miktarı belirtir.

*Rivın*<br/>
`y` Üyesinin`CPoint`kaydırılacağı miktarı belirtir.

*seçeneğinin*<br/>
Kaydırılacağı miktarı ( [nokta](/windows/win32/api/windef/ns-windef-point) veya `CPoint` `CPoint`) belirtir.

*boyutla*<br/>
Kaydırılacağı [](/windows/win32/api/windef/ns-windef-size) `CPoint`miktarı (boyut veya [CSize](../../atl-mfc-shared/reference/csize-class.md)) belirtir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

##  <a name="operator_eq_eq"></a>CPoint:: operator = =

İki noktayla eşitlik olup olmadığını denetler.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya `CPoint` nesnesi içerir.

### <a name="return-value"></a>Dönüş Değeri

Noktaları eşitse sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

##  <a name="operator_neq"></a>CPoint:: operator! =

İki punto arasındaki eşitsizlik için denetim gerçekleştirir.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya `CPoint` nesnesi içerir.

### <a name="return-value"></a>Dönüş Değeri

Noktaları eşit değilse sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

##  <a name="operator_add_eq"></a>CPoint:: operator + =

İlk aşırı yükleme öğesine `CPoint`bir boyut ekler.

```
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi içerir.

*seçeneğinin*<br/>
Bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi içerir.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yükleme öğesine `CPoint`bir işaret ekler.

Her iki durumda da, `x` sağ işlenen `x` `CPoint` öğesinin üyesine eklenerek `cx`ve `y` sağ işleneninin (veya `cy`) üyesini öğesine ekleyerek toplama işlemi yapılır. `y` üyesi .`CPoint`

Örneğin, değişkenini içeren `CPoint(5, -7)` `CPoint(30, 40)` bir değişkene ekleme, değişkenini olarak `CPoint(35, 33)`değiştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

##  <a name="operator_-_eq"></a>CPoint:: operator-=

İlk aşırı yükleme bir boyutu öğesinden `CPoint`çıkarır.

```
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi içerir.

*seçeneğinin*<br/>
Bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi içerir.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yükleme bir noktayı öğesinden `CPoint`çıkarır.

Her iki durumda da çıkarma, `x` sağ işlenenin `x` `CPoint` üyesi olan (veya `cx`) üyesini çıkararak ve `y` sağ taraftaki bir üyesinin (veya `cy`) üyesini çıkararak yapılır `y` öğesinin`CPoint`üyesinden işleneni.

Örneğin, öğesini içeren `CPoint(5, -7)` `CPoint(30, 40)` bir değişkenden çıkarma, değişkenini olarak `CPoint(25, 47)`değiştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

##  <a name="operator_add"></a>CPoint:: operator +

`CPoint` Bu işleci bir `CPoint` veya `CSize` nesnesinegöre`CRect` kaydırmak ya da a ile kaydırmak için kullanın. `CPoint`

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi içerir.

*seçeneğinin*<br/>
Bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi içerir.

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine yönelik bir işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir `CPoint` boyut, bir `CPoint` nokta veya `CRect` bir noktaya göre bir uzaklığa göre denkleştirilen bir.

### <a name="remarks"></a>Açıklamalar

Örneğin `CPoint(25, -19)` , noktayı bir nokta `CPoint(15, 5)` veya boyutla `CSize(15, 5)` kaydırmak için ilk iki aşırı yüklemeden birini kullanmak değeri `CPoint(40, -14)`döndürür.

Bir noktaya dikdörtgen eklemek, noktasında belirtilen `x` ve `y` değerleri ile kaydırıldıktan sonra dikdörtgeni döndürür. Örneğin, bir `CRect(125, 219, 325, 419)` `CPoint(25, -19)`noktanınbir dikdörtgeni kaydırmak için son aşırı yüklemeyi kullanma. `CRect(150, 200, 350, 400)`

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

##  <a name="operator_-"></a>CPoint:: operator-

Bir `CPoint` veya `CSize` nesnesini öğesinden`CPoint`çıkarmak için ilk iki aşırı yüklemeden birini kullanın.

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
[Nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

*boyutla*<br/>
[Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İki nokta `CPoint` arasındaki fark olan, bir boyutun `CRect` olumsuzlaştırılarak, bir noktanın olumsuzlaştırılarak kaydırılarak veya `CPoint` bir noktanın değilde olmadığı bir değer olan. `CSize`

### <a name="remarks"></a>Açıklamalar

Üçüncü aşırı yükleme, ' `CRect` nin `CPoint`değilleme yaptığı uzaklıkları. Son olarak, Newgate `CPoint`için birli işlecini kullanın.

Örneğin, iki punto `CPoint(25, -19)` arasındaki farkı bulmak için ilk tekrar yüklemeyi kullanma ve `CPoint(15, 5)` döndürür `CSize(10, -24)`.

İçinden çıkarma, `CSize` Yukarıdaki`CPoint` gibi aynı hesaplamayı yapar, ancak nesne değil bir nesne döndürür. `CPoint` `CSize` Örneğin, nokta `CPoint(25, -19)` ile `CSize(15, 5)` boyut arasındaki farkı bulmak için ikinci aşırı yüklemeyi kullanma. `CPoint(10, -24)`

Bir noktadan dikdörtgeni çıkarmak, noktada belirtilen `x` ve değerlerinin negatiflerini ve `y` dikdörtgen sapmasını döndürür. Örneğin, dikdörtgeni `CRect(125, 200, 325, 400)` `CPoint(25, -19)`noktaile kaydırmak için son aşırı yüklemeyi kullanma. `CRect(100, 219, 300, 419)`

Bir noktayı iç içe aktarmak için birli işleci kullanın. Örneğin, nokta `CPoint(25, -19)` `CPoint(-25, 19)`ile birli işleci kullanmak.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[NOKTA yapısı](/windows/win32/api/windef/ns-windef-point)<br/>
[CRect Sınıfı](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CSize Sınıfı](../../atl-mfc-shared/reference/csize-class.md)
