---
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
ms.openlocfilehash: 26bb43355f4dff3f77a905068bea83dd1ceaf79c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491649"
---
# <a name="csize-class"></a>CSize sınıfı

Göreli bir koordinat veya konum uygulayan Windows [Boyut](/windows/win32/api/windef/ns-windef-size) yapısına benzer.

## <a name="syntax"></a>Sözdizimi

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
|[CSize:: operator! =](#operator_neq)|Ve arasında `CSize` eşitsizlik olup olmadığını denetler.|
|[CSize:: operator +](#operator_add)|İki boyut ekler.|
|[CSize:: operator + =](#operator_add_eq)|Bir boyut `CSize`ekler.|
|[CSize:: operator-=](#operator_-_eq)|Bir boyutu `CSize`çıkartır.|
|[CSize:: operator = =](#operator_eq_eq)|Ve boyutu arasında `CSize` eşitlik olup olmadığını denetler.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf `SIZE` yapıdan türetilir. Bu, bir `SIZE` ' a çağrı `CSize` yapan bir parametreye geçirebilmeniz ve `SIZE` yapının veri üyelerinin erişilebilir veri üyeleri `CSize`olması anlamına gelir.

`cx` Ve `SIZE` (ve )`CSize`üyeleri geneldir. `cy` Ayrıca, `CSize` `SIZE` yapıyı işlemek için üye işlevleri uygular.

> [!NOTE]
> Paylaşılan yardımcı sınıflar (gibi `CSize`) hakkında daha fazla bilgi için bkz. [paylaşılan sınıflar](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagSIZE`

`CSize`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltypes. h

##  <a name="csize"></a>CSize:: CSize

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
İçin üyesini ayarlar. `CSize` `cx`

*ınitcy*<br/>
İçin üyesini ayarlar. `CSize` `cy`

*initSize*<br/>
[](/windows/win32/api/windef/ns-windef-size) `CSize` Başlatmak için`CSize`kullanılan boyut yapısı veya nesne.

*ınitpt*<br/>
[](/windows/win32/api/windef/ns-windef-point) `CPoint` Başlatmak için`CSize`kullanılan nokta yapısı veya nesnesi.

*dwSize*<br/>
Başlatmak `CSize`için kullanılan DWORD. Düşük sıralı sözcük `cx` üyedir ve yüksek sıralı kelime `cy` üye olur.

### <a name="remarks"></a>Açıklamalar

Herhangi bir bağımsız değişken verilmezse `cx` ve `cy` sıfıra başlatıluyorsa.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

##  <a name="operator_eq_eq"></a>CSize:: operator = =

İki boyut arasında eşitlik olup olmadığını denetler.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Açıklamalar

Boyutlar eşitse, diğerwize 0 olan sıfır dışı döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

##  <a name="operator_neq"></a>CSize:: operator! =

İki boyut arasında eşitsizlik olup olmadığını denetler.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Açıklamalar

Boyutlar eşit değilse sıfır dışında bir değer döndürür, aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

##  <a name="operator_add_eq"></a>CSize:: operator + =

Buna `CSize`bir boyut ekler.

```
void operator+=(SIZE size) throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

##  <a name="operator_-_eq"></a>CSize:: operator-=

Bir boyutu bundan `CSize`çıkartır.

```
void operator-=(SIZE size) throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

##  <a name="operator_add"></a>CSize:: operator +

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

  Bu işlem bir [nokta](/previous-versions/dd162805\(v=vs.85\)) (veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) değerini bu değere kaydırır (ya da `CSize` bu değeri gider). `cy` `x` Bu `cx` değerin`CSize` ve üyeleri, değerin`POINT` ve veriüyelerineeklenir`y` . Bir [Boyut](/windows/win32/api/windef/ns-windef-size) parametresi alan [CPoint:: operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) sürümüne benzerdir.

- **operator + (** *lpRect* **)**

   Bu işlem, bu `CSize` değere göre bir [Rect](/previous-versions/dd162897\(v=vs.85\)) (veya [CRect](../../atl-mfc-shared/reference/crect-class.md)) değeri kaydırır (gider). `cy` `left`Bu `cx` değerinve`top`üyeleri değerin ,`right`, ve`bottom` veri üyelerine eklenir. `RECT` `CSize` Bir [Boyut](/windows/win32/api/windef/ns-windef-size) parametresi alan [CRect:: operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) sürümüne benzerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

##  <a name="operator_-"></a>CSize:: operator-

Bu operatörlerin ilk üçü, bu `CSize` değeri parametre değerine çıkarır.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Açıklamalar

Birli eksi olan dördüncü operatör, `CSize` değerin işaretini değiştirir. Ayrı işleçlerin aşağıdaki açıklamalarına bakın:

- **işleç-(** *Boyut* **)**

  Bu işlem iki `CSize` değeri çıkartır.

- **işleç-(** *nokta* **)**

  Bu işlem, bu `CSize` değerin Toplamsal tersini yaparak bir [nokta](/previous-versions/dd162805\(v=vs.85\)) veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) değeri kaydırır (gider). `cy` Bu `cx` değerinve`y` veri üyelerinden çıkarılan`x` ve değeri.`POINT` `CSize` Bir [Boyut](/windows/win32/api/windef/ns-windef-size) parametresi alan [CPoint:: operator](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) sürümüne benzerdir.

- **operator-(** *lpRect* **)**

  Bu işlem, bu `CSize` değerin Toplamsal tersini yaparak bir [Rect](/previous-versions/dd162897\(v=vs.85\)) veya [CRect](../../atl-mfc-shared/reference/crect-class.md) değeri kaydırır (taşımalar). `cy` `right` `top` `left`Bu `cx` değerinveüyeleri`RECT` değerin,, ve`bottom` veri üyelerinden çıkarılır. `CSize` Bir [Boyut](/windows/win32/api/windef/ns-windef-size) parametresi alan [CRect:: operator](../../atl-mfc-shared/reference/crect-class.md#operator_-) sürümüne benzerdir.

- **operator-()**

  Bu işlem, bu `CSize` değerin Toplamsal tersini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRect Sınıfı](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CPoint Sınıfı](../../atl-mfc-shared/reference/cpoint-class.md)
