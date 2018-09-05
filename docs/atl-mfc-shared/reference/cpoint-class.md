---
title: CPoint sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc0506d5b4f264a2bdbecf30a7732c93c927bf18
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767988"
---
# <a name="cpoint-class"></a>CPoint sınıfı

Windows için benzer `POINT` yapısı.

## <a name="syntax"></a>Sözdizimi

```
class CPoint : public tagPOINT 
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPoint::CPoint](#cpoint)|Oluşturur bir `CPoint`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPoint::Offset](#offset)|Değerine ekler `x` ve `y` üyeleri `CPoint`.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CPoint::operator-](#operator_-)|Farkını döndürür bir `CPoint` ve bir boyut veya negation bir veya iki nokta veya negatif bir boyuta göre uzaklığını arasındaki boyut farkı.|
|[CPoint::operator! =](#operator_neq)|İki nokta arasındaki eşitsizliği denetler.|
|[CPoint::operator +](#operator_add)|Toplamını geri döndüren bir `CPoint` ve boyutu veya noktası veya bir `CRect` boyutuna göre uzaklığı.|
|[CPoint::operator +=](#operator_add_eq)|Uzaklıkları `CPoint` boyutu veya noktası ekleyerek.|
|[CPoint::operator-=](#operator_-_eq)|Uzaklıkları `CPoint` boyutu veya noktası çıkararak.|
|[CPoint::operator ==](#operator_eq_eq)|İki nokta arasındaki denetler.|

## <a name="remarks"></a>Açıklamalar

Ayrıca yönlendirmek üzere öğe işlevleri içerir `CPoint` ve [noktası](../../mfc/reference/point-structure1.md) yapıları.

A `CPoint` nesnesi olabilir yerde kullanılan bir `POINT` yapısı kullanılır. Bu sınıfın "boyutu" ile etkileşim işleçleri ya da kabul [CSize](../../atl-mfc-shared/reference/csize-class.md) nesneleri veya [BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) yapıları iki birbirinin yerine olduğundan.

> [!NOTE]
>  Bu sınıf türetilir `tagPOINT` yapısı. (Adın `tagPOINT` için daha az kullanılan addır `POINT` yapısı.) Veri üyeleri buna `POINT` yapısını `x` ve `y`, erişilebilir veri üyeleri `CPoint`.

> [!NOTE]
>  Daha fazla bilgi için paylaşılan yardımcı sınıflar (gibi `CPoint`), bkz: [paylaşılan sınıflar](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagPOINT`

`CPoint`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atltypes.h

##  <a name="cpoint"></a>  CPoint::CPoint

Oluşturur bir `CPoint` nesne.

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>Parametreler

*initX*  
Değerini belirtir `x` üyesi `CPoint`.

*initY*  
Değerini belirtir `y` üyesi `CPoint`.

*initPt*  
[NOKTASI](../../mfc/reference/point-structure1.md) yapısı veya `CPoint` başlatmak için kullanılan değerleri belirten `CPoint`.

*initSize*  
[BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) başlatmak için kullanılan değerleri belirten `CPoint`.

*dwPoint*  
Kümeleri `x` alt sıra sözcüğüne üye *dwPoint* ve `y` dwpoint üye *dwPoint*.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken olmadan verilirse `x` ve `y` üyeleri 0 olarak ayarlanır.

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

##  <a name="offset"></a>  CPoint::Offset

Değerine ekler `x` ve `y` üyeleri `CPoint`.

```
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>Parametreler

*xOffset*  
Kaydırılacağı uzaklık belirtir `x` üyesi `CPoint`.

*yOffset*  
Kaydırılacağı uzaklık belirtir `y` üyesi `CPoint`.

*Noktası*  
Belirtir ( [noktası](../../mfc/reference/point-structure1.md) veya `CPoint`) dengelemek için `CPoint`.

*Boyutu*  
Belirtir ( [BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) veya [CSize](../../atl-mfc-shared/reference/csize-class.md)) dengelemek için `CPoint`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

##  <a name="operator_eq_eq"></a>  CPoint::operator ==

İki nokta arasındaki denetler.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*Noktası*  
İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya `CPoint` nesne.

### <a name="return-value"></a>Dönüş Değeri

Noktaları eşit olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

##  <a name="operator_neq"></a>  CPoint::operator! =

İki nokta arasındaki eşitsizliği denetler.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*Noktası*  
İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya `CPoint` nesne.

### <a name="return-value"></a>Dönüş Değeri

Noktaları eşit değilse, sıfır olmayan; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

##  <a name="operator_add_eq"></a>  CPoint::operator +=

İlk aşırı yükleme bir boyuta ekler `CPoint`.

```
void operator+=(SIZE size) throw(); 
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*Boyutu*  
İçeren bir [BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesne.

*Noktası*  
İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yüklemesi bir noktaya ekler `CPoint`.

Her iki durumda da ayrıca ekleyerek yapılır `x` (veya `cx`) sağ işleneni üyesi `x` üyesi `CPoint` ve ekleme `y` (veya `cy`) sağ işleneni üyesi `y` üyesi `CPoint`.

Örneğin, ekleme `CPoint(5, -7)` içeren bir değişkene `CPoint(30, 40)` değişkenine değişiklikleri `CPoint(35, 33)`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

##  <a name="operator_-_eq"></a>  CPoint::operator-=

İlk aşırı yükleme listesinden bir boyut çıkarır `CPoint`.

```
void operator-=(SIZE size) throw(); 
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*Boyutu*  
İçeren bir [BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesne.

*Noktası*  
İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yüklemesi bir noktasından çıkarır `CPoint`.

Her iki durumda da çıkarma çıkararak yapılır `x` (veya `cx`) atamada sağ işlenen üye `x` üyesi `CPoint` ve çıkarma `y` (veya `cy`) sağ üyesi işlenenden `y` üyesi `CPoint`.

Örneğin, çıkarma `CPoint(5, -7)` içeren bir değişkenden `CPoint(30, 40)` değişkenine değişiklikleri `CPoint(25, 47)`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

##  <a name="operator_add"></a>  CPoint::operator +

Kaydırmak için bu işleci kullanın `CPoint` tarafından bir `CPoint` veya `CSize` nesnesi veya dengelemek için bir `CRect` tarafından bir `CPoint`.

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*Boyutu*  
İçeren bir [BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesne.

*Noktası*  
İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesne.

*lpRect*  
Bir işaretçi içeren bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

A `CPoint` bir boyuta göre uzaklığı bir `CPoint` bir noktası tarafından uzaklığı veya `CRect` noktası tarafından uzaklığı.

### <a name="remarks"></a>Açıklamalar

Örneğin, ilk iki aşırı noktası dengelemek için kullanarak `CPoint(25, -19)` bir nokta `CPoint(15, 5)` veya boyutu `CSize(15, 5)` değeri döndürür `CPoint(40, -14)`.

Bir dikdörtgen bir noktaya ekleme döndürür dikdörtgen tarafından uzaklığı sonra `x` ve `y` noktasında belirtilen değerleri. Örneğin, bir dikdörtgen dengelemek için son aşırı yükü kullanarak `CRect(125, 219, 325, 419)` bir nokta `CPoint(25, -19)` döndürür `CRect(150, 200, 350, 400)`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

##  <a name="operator_-"></a>  CPoint::operator-

İlk iki aşırı çıkarılacak kullanmak bir `CPoint` veya `CSize` nesnesinden `CPoint`.

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>Parametreler

*Noktası*  
A [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesne.

*Boyutu*  
A [BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesne.

*lpRect*  
Bir işaretçi bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir `CSize` diğer bir deyişle iki nokta arasındaki fark bir `CPoint` bir boyut olumsuzlama göre uzaklığı bir `CRect` bir noktanın olumsuzlama göre uzaklığı veya `CPoint` diğer bir deyişle olumsuzlama noktası.

### <a name="remarks"></a>Açıklamalar

Üçüncü aşırı uzaklıkları bir `CRect` negation tarafından `CPoint`. Son olarak, negatif yapılacak birli işleç kullanın `CPoint`.

Örneğin, iki nokta arasındaki farkı bulmak için ilk aşırı yükleme kullanarak `CPoint(25, -19)` ve `CPoint(15, 5)` döndürür `CSize(10, -24)`.

Çıkarma bir `CSize` gelen `CPoint` yukarıdakilerle aynı olan hesaplamayı yapar ancak döndürür bir `CPoint` nesnesi değil, bir `CSize` nesne. Örneğin, noktası arasındaki fark bulmak için ikinci aşırı yüklemesi kullanarak `CPoint(25, -19)` ve boyutu `CSize(15, 5)` döndürür `CPoint(10, -24)`.

Bir dikdörtgen bir noktasından çıkararak dikdörtgen uzaklığı negatif tarafından döndürür `x` ve `y` noktasında belirtilen değerleri. Örneğin, dikdörtgen dengelemek için son aşırı yükü kullanarak `CRect(125, 200, 325, 400)` noktası tarafından `CPoint(25, -19)` döndürür `CRect(100, 219, 300, 419)`.

Bir noktası negatif yapılacak birli işlecini kullanın. Örneğin, noktasıyla birli işleç kullanılarak `CPoint(25, -19)` döndürür `CPoint(-25, 19)`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek MDI](../../visual-cpp-samples.md)   
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
[POINT yapısı](../../mfc/reference/point-structure1.md)   
[CRect sınıfı](../../atl-mfc-shared/reference/crect-class.md)   
[CSize Sınıfı](../../atl-mfc-shared/reference/csize-class.md)

