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
ms.openlocfilehash: 9bbd23fe793946dc0f081f4d19b9f6e26fcfda82
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178375"
---
# <a name="csize-class"></a>CSize sınıfı

Windows için benzer [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) göreli koordinat veya konum uygulayan yapısı.

## <a name="syntax"></a>Sözdizimi

```
class CSize : public tagSIZE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSize::CSize](#csize)|Oluşturur bir `CSize` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CSize::operator-](#operator_-)|İki boyutu çıkarır.|
|[CSize::operator! =](#operator_neq)|Denetimleri arasındaki eşitsizliği `CSize` ve boyutu.|
|[CSize::operator +](#operator_add)|İki boyutu ekler.|
|[CSize::operator +=](#operator_add_eq)|Bir boyuta ekler `CSize`.|
|[CSize::operator-=](#operator_-_eq)|Çıkarma listesinden bir boyut `CSize`.|
|[CSize::operator ==](#operator_eq_eq)|Denetimleri arasındaki eşitliği `CSize` ve boyutu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf türetilir `SIZE` yapısı. Bu, geçirebilirsiniz anlamına gelir. bir `CSize` için çağıran bir parametreye bir `SIZE` ve veri üyeleri `SIZE` yapısı erişilebilir veri üyeleri olan `CSize`.

`cx` Ve `cy` üyeleri `SIZE` (ve `CSize`) herkese açık. Ayrıca, `CSize` yönlendirmek üzere öğe işlevleri uygulayan `SIZE` yapısı.

> [!NOTE]
> Daha fazla bilgi için paylaşılan yardımcı sınıflar (gibi `CSize`), bkz: [paylaşılan sınıflar](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagSIZE`

`CSize`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atltypes.h

##  <a name="csize"></a>  CSize::CSize

Oluşturur bir `CSize` nesne.

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>Parametreler

*initCX*<br/>
Kümeleri `cx` üyesi için `CSize`.

*initCY*<br/>
Kümeleri `cy` üyesi için `CSize`.

*initSize*<br/>
[BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) yapısı veya `CSize` başlatmak için kullanılan nesne `CSize`.

*initPt*<br/>
[NOKTASI](/windows/desktop/api/windef/ns-windef-tagpoint) yapısı veya `CPoint` başlatmak için kullanılan nesne `CSize`.

*dwSize*<br/>
DWORD başlatmak için kullanılan `CSize`. Düşük düzey sözcük `cx` üyesi ve dwpoint `cy` üyesi.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken olmadan verilirse `cx` ve `cy` sıfır olarak başlatılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

##  <a name="operator_eq_eq"></a>  CSize::operator ==

İki boyutu arasındaki denetler.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Açıklamalar

0 otherwize boyutları eşitse, sıfır döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

##  <a name="operator_neq"></a>  CSize::operator! =

İki boyutu arasındaki eşitsizliği denetler.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Açıklamalar

Boyutları eşit değilse sıfır döndürür. Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

##  <a name="operator_add_eq"></a>  CSize::operator +=

Bir boyut için bunu ekler `CSize`.

```
void operator+=(SIZE size) throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

##  <a name="operator_-_eq"></a>  CSize::operator-=

Bu boyut çıkarır `CSize`.

```
void operator-=(SIZE size) throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

##  <a name="operator_add"></a>  CSize::operator +

Bu işleçler bu ekleme `CSize` parametresinin değeri için değer.

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>Açıklamalar

Tek tek işleçler aşağıdaki açıklamaları bakın:

- **operator + (** *boyutu* **)**

  Bu işlem iki ekler `CSize` değerleri.

- **operator + (** *noktası* **)**

  Bu işlem (taşıma) kaydırır bir [noktası](https://msdn.microsoft.com/library/windows/desktop/dd162805) (veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) bu değerle `CSize` değeri. `cx` Ve `cy` bu üyeleri `CSize` değer eklenir `x` ve `y` veri üyeleri `POINT` değeri. Sürümüne benzer [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) almayan bir [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) parametresi.

- **operator + (** *lpRect* **)**

   Bu işlem (taşıma) kaydırır bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) (veya [CRect](../../atl-mfc-shared/reference/crect-class.md)) bu değerle `CSize` değeri. `cx` Ve `cy` bu üyeleri `CSize` değer eklenir `left`, `top`, `right`, ve `bottom` veri üyeleri `RECT` değeri. Sürümüne benzer [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) almayan bir [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) parametresi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

##  <a name="operator_-"></a>  CSize::operator-

Bu işleçler, ilk üç bu çıkarma `CSize` parametresinin değeri için değer.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Açıklamalar

Tek işlenenli eksi işareti, dördüncü işleci işaretini değişiklikleri `CSize` değeri. Tek tek işleçler aşağıdaki açıklamaları bakın:

- **-işleci (** *boyutu* **)**

  Bu işlem iki çıkarır `CSize` değerleri.

- **-işleci (** *noktası* **)**

  Bu işlem (taşıma) kaydırır bir [noktası](https://msdn.microsoft.com/library/windows/desktop/dd162805) veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) değere göre bu eklenebilir tersini `CSize` değeri. `cx` Ve `cy` bu `CSize` değeri gelen çıkartılır `x` ve `y` veri üyeleri `POINT` değeri. Sürümüne benzer [CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) almayan bir [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) parametresi.

- **-işleci (** *lpRect* **)**

  Bu işlem (taşıma) kaydırır bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) veya [CRect](../../atl-mfc-shared/reference/crect-class.md) değere göre bu eklenebilir tersini `CSize` değeri. `cx` Ve `cy` bu üyeleri `CSize` değeri gelen çıkartılır `left`, `top`, `right`, ve `bottom` veri üyeleri `RECT` değeri. Sürümüne benzer [CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-) almayan bir [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) parametresi.

- **operator-)**

  Bu işlem, bu eklenebilir tersini döndürür `CSize` değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek MDI](../../visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRect Sınıfı](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CPoint Sınıfı](../../atl-mfc-shared/reference/cpoint-class.md)

