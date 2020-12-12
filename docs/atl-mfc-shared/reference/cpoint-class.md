---
description: 'Daha fazla bilgi edinin: CPoint sınıfı'
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
ms.openlocfilehash: 9d1c6ecb628e4d47d80503bb7a441efc4deb1252
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166765"
---
# <a name="cpoint-class"></a>CPoint sınıfı

Windows `POINT` yapısına benzer.

## <a name="syntax"></a>Syntax

```
class CPoint : public tagPOINT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPoint:: CPoint](#cpoint)|Bir oluşturur `CPoint` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPoint:: kayması](#offset)|, `x` Ve üyelerine değer ekler `y` `CPoint` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CPoint:: operator-](#operator_-)|Bir ve boyutunun veya bir `CPoint` noktanın değilinin veya iki nokta arasındaki boyut farkının veya negatif bir boyuta göre farkın farkını döndürür.|
|[CPoint:: operator! =](#operator_neq)|İki punto arasındaki eşitsizlik için denetim gerçekleştirir.|
|[CPoint:: operator +](#operator_add)|Bir, bir `CPoint` boyut veya noktanın toplamını ya da bir `CRect` boyut ile bir konum döndürür.|
|[CPoint:: operator + =](#operator_add_eq)|`CPoint`Bir boyut veya nokta ekleyerek uzaklıkları.|
|[CPoint:: operator-=](#operator_-_eq)|`CPoint`Bir boyut veya noktayı çıkararak uzaklıkları.|
|[CPoint:: operator = =](#operator_eq_eq)|İki noktayla eşitlik olup olmadığını denetler.|

## <a name="remarks"></a>Açıklamalar

Ayrıca `CPoint` , işleme ve [işaret](/windows/win32/api/windef/ns-windef-point) yapılarına üye işlevleri de içerir.

Bir `CPoint` nesne, bir yapının kullanıldığı her yerde kullanılabilir `POINT` . Bu sınıfın "Boyut" ile etkileşime geçen işleçleri [CSize](../../atl-mfc-shared/reference/csize-class.md) nesneleri veya [Boyut](/windows/win32/api/windef/ns-windef-size) yapılarını kabul eder, çünkü ikisi birlikte değiştirilebilir.

> [!NOTE]
> Bu sınıf `tagPOINT` yapıdan türetilir. (Ad, `tagPOINT` Yapı için daha yaygın olarak kullanılan bir addır `POINT` .) Bu, yapının veri üyelerinin `POINT` `x` ve `y` ' nin erişilebilir veri üyeleri olduğu anlamına gelir `CPoint` .

> [!NOTE]
> Paylaşılan yardımcı sınıflar (gibi) hakkında daha fazla bilgi için `CPoint` bkz. [paylaşılan sınıflar](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagPOINT`

`CPoint`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltypes. h

## <a name="cpointcpoint"></a><a name="cpoint"></a> CPoint:: CPoint

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
Üyesinin değerini belirtir `x` `CPoint` .

*Çevre*<br/>
Üyesinin değerini belirtir `y` `CPoint` .

*ınitpt*<br/>
Başlangıç [noktası](/windows/win32/api/windef/ns-windef-point) yapısı veya `CPoint` başlatmak için kullanılan değerleri belirtir `CPoint` .

*initSize*<br/>
Başlatmak için kullanılan değerleri belirten [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) `CPoint` .

*dwPoint*<br/>
Üyeyi, `x` *dwPoint* 'in alt-sıra sözcüğünün ve `y` üyenin *dwPoint*'in üst-sıra sözcüğüne ayarlar.

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

## <a name="cpointoffset"></a><a name="offset"></a> CPoint:: kayması

, `x` Ve üyelerine değer ekler `y` `CPoint` .

```cpp
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>Parametreler

*Xsapmayı*<br/>
Üyesinin kaydırılacağı miktarı belirtir `x` `CPoint` .

*Rivın*<br/>
Üyesinin kaydırılacağı miktarı belirtir `y` `CPoint` .

*seçeneğinin*<br/>
Kaydırılacağı miktarı ( [nokta](/windows/win32/api/windef/ns-windef-point) veya `CPoint` ) belirtir `CPoint` .

*boyutla*<br/>
Kaydırılacağı miktarı ( [Boyut](/windows/win32/api/windef/ns-windef-size) veya [CSize](../../atl-mfc-shared/reference/csize-class.md)) belirtir `CPoint` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

## <a name="cpointoperator-"></a><a name="operator_eq_eq"></a> CPoint:: operator = =

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

## <a name="cpointoperator-"></a><a name="operator_neq"></a> CPoint:: operator! =

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

## <a name="cpointoperator-"></a><a name="operator_add_eq"></a> CPoint:: operator + =

İlk aşırı yükleme öğesine bir boyut ekler `CPoint` .

```cpp
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi içerir.

*seçeneğinin*<br/>
Bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi içerir.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yükleme öğesine bir işaret ekler `CPoint` .

Her iki durumda da, sağ işlenen öğesinin üyesine eklenerek `x` `cx` `x` `CPoint` ve `y` `cy` sağ işleneninin (veya) üyesini `y` öğesinin `CPoint` üyesine ekleyerek ek bir şekilde yapılır.

Örneğin, `CPoint(5, -7)` değişkenini içeren bir değişkene ekleme, `CPoint(30, 40)` değişkenini olarak değiştirir `CPoint(35, 33)` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-_eq"></a> CPoint:: operator-=

İlk aşırı yükleme bir boyutu öğesinden çıkarır `CPoint` .

```cpp
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi içerir.

*seçeneğinin*<br/>
Bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi içerir.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yükleme bir noktayı öğesinden çıkarır `CPoint` .

Her iki durumda da çıkarma, sağ işleneninin üyesi olan (veya) üyesini çıkararak `x` `cx` ve öğesinin üyesi olan `x` `CPoint` `y` sağ işlenenin üyesini çıkararak yapılır `cy` `y` `CPoint` .

Örneğin, öğesini `CPoint(5, -7)` içeren bir değişkenden çıkarma, `CPoint(30, 40)` değişkenini olarak değiştirir `CPoint(25, 47)` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add"></a> CPoint:: operator +

Bu işleci bir `CPoint` veya nesnesine göre kaydırmak `CPoint` `CSize` ya da a ile kaydırmak için kullanın `CRect` `CPoint` .

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

Bir `CPoint` boyut, bir nokta veya bir noktaya göre bir uzaklığa göre denkleştirilen bir `CPoint` `CRect` .

### <a name="remarks"></a>Açıklamalar

Örneğin, noktayı bir nokta veya boyutla kaydırmak için ilk iki aşırı yüklemeden birini kullanmak `CPoint(25, -19)` `CPoint(15, 5)` `CSize(15, 5)` değeri döndürür `CPoint(40, -14)` .

Bir noktaya dikdörtgen eklemek, `x` noktasında belirtilen ve değerleri ile kaydırıldıktan sonra dikdörtgeni döndürür `y` . Örneğin, bir noktanın bir dikdörtgeni kaydırmak için son aşırı yüklemeyi kullanma `CRect(125, 219, 325, 419)` `CPoint(25, -19)` `CRect(150, 200, 350, 400)` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-"></a> CPoint:: operator-

Bir `CPoint` veya nesnesini öğesinden çıkarmak için ilk iki aşırı yüklemeden birini kullanın `CSize` `CPoint` .

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

İki nokta arasındaki fark olan, bir boyutun olumsuzlaştırılarak, bir `CSize` `CPoint` `CRect` noktanın olumsuzlaştırılarak kaydırılarak veya bir `CPoint` noktanın değilde olmadığı bir değer olan.

### <a name="remarks"></a>Açıklamalar

Üçüncü aşırı yükleme, ' `CRect` nin değilleme yaptığı uzaklıkları `CPoint` . Son olarak, Newgate için birli işlecini kullanın `CPoint` .

Örneğin, iki punto arasındaki farkı bulmak için ilk tekrar yüklemeyi kullanma `CPoint(25, -19)` ve `CPoint(15, 5)` döndürür `CSize(10, -24)` .

İçinden çıkarma `CSize` , `CPoint` yukarıdaki gibi aynı hesaplamayı yapar `CPoint` , ancak nesne değil bir nesne döndürür `CSize` . Örneğin, nokta ile boyut arasındaki farkı bulmak için ikinci aşırı yüklemeyi kullanma `CPoint(25, -19)` `CSize(15, 5)` `CPoint(10, -24)` .

Bir noktadan dikdörtgeni çıkarmak, `x` noktada belirtilen ve değerlerinin negatiflerini ve dikdörtgen sapmasını döndürür `y` . Örneğin, dikdörtgeni nokta ile kaydırmak için son aşırı yüklemeyi kullanma `CRect(125, 200, 325, 400)` `CPoint(25, -19)` `CRect(100, 219, 300, 419)` .

Bir noktayı iç içe aktarmak için birli işleci kullanın. Örneğin, nokta ile birli işleci kullanmak `CPoint(25, -19)` `CPoint(-25, 19)` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[NOKTA yapısı](/windows/win32/api/windef/ns-windef-point)<br/>
[CRect sınıfı](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CSize sınıfı](../../atl-mfc-shared/reference/csize-class.md)
