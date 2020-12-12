---
description: 'Daha fazla bilgi edinin: CSize sınıfı'
title: CSize sınıfı
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
ms.openlocfilehash: 0a63a7e0c48948406bf5650a1b095713f701a325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166648"
---
# <a name="csize-class"></a>CSize sınıfı

Göreli bir koordinat veya konum uygulayan Windows [Boyut](/windows/win32/api/windef/ns-windef-size) yapısına benzer.

## <a name="syntax"></a>Syntax

```
class CSize : public tagSIZE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSize:: CSize](#csize)|Bir `CSize` nesnesi oluşturur.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CSize:: operator-](#operator_-)|İki boyutu çıkartır.|
|[CSize:: operator! =](#operator_neq)|Ve arasında eşitsizlik olup olmadığını denetler `CSize` .|
|[CSize:: operator +](#operator_add)|İki boyut ekler.|
|[CSize:: operator + =](#operator_add_eq)|Bir boyut ekler `CSize` .|
|[CSize:: operator-=](#operator_-_eq)|Bir boyutu çıkartır `CSize` .|
|[CSize:: operator = =](#operator_eq_eq)|Ve boyutu arasında eşitlik olup olmadığını denetler `CSize` .|

## <a name="remarks"></a>Açıklamalar

Bu sınıf `SIZE` yapıdan türetilir. Bu, bir `CSize` ' a çağrı yapan bir parametreye geçirebilmeniz `SIZE` ve yapının veri üyelerinin `SIZE` erişilebilir veri üyeleri olması anlamına gelir `CSize` .

`cx`Ve `cy` `SIZE` (ve `CSize` ) üyeleri geneldir. Ayrıca, `CSize` yapıyı işlemek için üye işlevleri uygular `SIZE` .

> [!NOTE]
> Paylaşılan yardımcı sınıflar (gibi) hakkında daha fazla bilgi için `CSize` bkz. [paylaşılan sınıflar](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagSIZE`

`CSize`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltypes. h

## <a name="csizecsize"></a><a name="csize"></a> CSize:: CSize

Bir `CSize` nesnesi oluşturur.

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>Parametreler

*ınitcx*<br/>
`cx`İçin üyesini ayarlar `CSize` .

*ınitcy*<br/>
`cy`İçin üyesini ayarlar `CSize` .

*initSize*<br/>
[](/windows/win32/api/windef/ns-windef-size) `CSize` Başlatmak için kullanılan boyut yapısı veya nesne `CSize` .

*ınitpt*<br/>
[](/windows/win32/api/windef/ns-windef-point) `CPoint` Başlatmak için kullanılan nokta yapısı veya nesnesi `CSize` .

*dwSize*<br/>
Başlatmak için kullanılan DWORD `CSize` . Düşük sıralı sözcük `cx` üyedir ve yüksek sıralı kelime `cy` üye olur.

### <a name="remarks"></a>Açıklamalar

Herhangi bir bağımsız değişken verilmezse `cx` ve `cy` sıfıra başlatıluyorsa.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

## <a name="csizeoperator-"></a><a name="operator_eq_eq"></a> CSize:: operator = =

İki boyut arasında eşitlik olup olmadığını denetler.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Açıklamalar

Boyutlar eşitse, diğerwize 0 olan sıfır dışı döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

## <a name="csizeoperator-"></a><a name="operator_neq"></a> CSize:: operator! =

İki boyut arasında eşitsizlik olup olmadığını denetler.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Açıklamalar

Boyutlar eşit değilse sıfır dışında bir değer döndürür, aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add_eq"></a> CSize:: operator + =

Buna bir boyut ekler `CSize` .

```cpp
void operator+=(SIZE size) throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-_eq"></a> CSize:: operator-=

Bir boyutu bundan çıkartır `CSize` .

```cpp
void operator-=(SIZE size) throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add"></a> CSize:: operator +

Bu işleçler, bu `CSize` değeri parametresinin değerine ekler.

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrı işleçlerin aşağıdaki açıklamalarına bakın:

- **işleç + (** *Boyut* **)**

  Bu işlem iki `CSize` değer ekler.

- **işleç + (** *nokta* **)**

  Bu işlem bir [nokta](/windows/win32/api/windef/ns-windef-point) (veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) değerini bu değere kaydırır (ya da bu değeri gider) `CSize` . `cx` `cy` Bu değerin ve üyeleri, `CSize` `x` `y` değerin ve veri üyelerine eklenir `POINT` . Bir [Boyut](/windows/win32/api/windef/ns-windef-size) parametresi alan [CPoint:: operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) sürümüne benzerdir.

- **operator + (** *lpRect* **)**

   Bu işlem, bu değere göre bir [Rect](/windows/win32/api/windef/ns-windef-rect) (veya [CRect](../../atl-mfc-shared/reference/crect-class.md)) değeri kaydırır (gider) `CSize` . `cx` `cy` Bu değerin ve üyeleri `CSize` `left` değerin,, `top` `right` ve `bottom` veri üyelerine eklenir `RECT` . Bir [Boyut](/windows/win32/api/windef/ns-windef-size) parametresi alan [CRect:: operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) sürümüne benzerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-"></a> CSize:: operator-

Bu operatörlerin ilk üçü, bu `CSize` değeri parametre değerine çıkarır.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Açıklamalar

Birli eksi olan dördüncü operatör, değerin işaretini değiştirir `CSize` . Ayrı işleçlerin aşağıdaki açıklamalarına bakın:

- **işleç-(** *Boyut* **)**

  Bu işlem iki `CSize` değeri çıkartır.

- **işleç-(** *nokta* **)**

  Bu işlem, bu değerin Toplamsal tersini yaparak bir [nokta](/windows/win32/api/windef/ns-windef-point) veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) değeri kaydırır (gider) `CSize` . `cx` `cy` Bu `CSize` değerin ve `x` veri üyelerinden çıkarılan ve `y` `POINT` değeri. Bir [Boyut](/windows/win32/api/windef/ns-windef-size) parametresi alan [CPoint:: operator](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) sürümüne benzerdir.

- **operator-(** *lpRect* **)**

  Bu işlem, bu değerin Toplamsal tersini yaparak bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya [CRect](../../atl-mfc-shared/reference/crect-class.md) değeri kaydırır (taşımalar) `CSize` . `cx` `cy` Bu değerin ve üyeleri değerin,, `CSize` `left` `top` `right` ve `bottom` veri üyelerinden çıkarılır `RECT` . Bir [Boyut](/windows/win32/api/windef/ns-windef-size) parametresi alan [CRect:: operator](../../atl-mfc-shared/reference/crect-class.md#operator_-) sürümüne benzerdir.

- **operator-()**

  Bu işlem, bu değerin Toplamsal tersini döndürür `CSize` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRect sınıfı](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CPoint sınıfı](../../atl-mfc-shared/reference/cpoint-class.md)
