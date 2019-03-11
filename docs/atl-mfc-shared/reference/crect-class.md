---
title: CRect sınıfı
ms.date: 11/06/2018
f1_keywords:
- CRect
- ATLTYPES/ATL::CRect
- ATLTYPES/ATL::CRect::CRect
- ATLTYPES/ATL::CRect::BottomRight
- ATLTYPES/ATL::CRect::CenterPoint
- ATLTYPES/ATL::CRect::CopyRect
- ATLTYPES/ATL::CRect::DeflateRect
- ATLTYPES/ATL::CRect::EqualRect
- ATLTYPES/ATL::CRect::Height
- ATLTYPES/ATL::CRect::InflateRect
- ATLTYPES/ATL::CRect::IntersectRect
- ATLTYPES/ATL::CRect::IsRectEmpty
- ATLTYPES/ATL::CRect::IsRectNull
- ATLTYPES/ATL::CRect::MoveToX
- ATLTYPES/ATL::CRect::MoveToXY
- ATLTYPES/ATL::CRect::MoveToY
- ATLTYPES/ATL::CRect::NormalizeRect
- ATLTYPES/ATL::CRect::OffsetRect
- ATLTYPES/ATL::CRect::PtInRect
- ATLTYPES/ATL::CRect::SetRect
- ATLTYPES/ATL::CRect::SetRectEmpty
- ATLTYPES/ATL::CRect::Size
- ATLTYPES/ATL::CRect::SubtractRect
- ATLTYPES/ATL::CRect::TopLeft
- ATLTYPES/ATL::CRect::UnionRect
- ATLTYPES/ATL::CRect::Width
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
ms.openlocfilehash: fadb430d570e516d915d520f06e4c247b131c3db
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739431"
---
# <a name="crect-class"></a>CRect sınıfı

Benzer şekilde bir Windows [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı.

## <a name="syntax"></a>Sözdizimi

```
class CRect : public tagRECT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRect::CRect](#crect)|Oluşturur bir `CRect` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRect::BottomRight](#bottomright)|Sağ alt noktasını döndürür `CRect`.|
|[CRect::CenterPoint](#centerpoint)|' In centerpoint döndürür `CRect`.|
|[CRect::CopyRect](#copyrect)|Kaynak dikdörtgenin boyutları kopyalar `CRect`.|
|[CRect::DeflateRect](#deflaterect)|Genişliği ve yüksekliği azalır `CRect`.|
|[CRect::EqualRect](#equalrect)|Belirler olmadığını `CRect` verilen dikdörtgene eşittir.|
|[CRect::Height](#height)|Yüksekliğini hesaplar `CRect`.|
|[CRect::InflateRect](#inflaterect)|Genişlik ve yüksekliğini artırır `CRect`.|
|[CRect::IntersectRect](#intersectrect)|Kümeleri `CRect` iki dikdörtgenler kesişimi eşittir.|
|[CRect::IsRectEmpty](#isrectempty)|Belirler olmadığını `CRect` boştur. `CRect` 0 ise genişlik ve yükseklik boştur.|
|[CRect::IsRectNull](#isrectnull)|Belirler olmadığını `top`, `bottom`, `left`, ve `right` üye değişkenleri tüm 0'a eşit.|
|[CRect::MoveToX](#movetox)|Taşır `CRect` için belirtilen x koordinatı.|
|[CRect::MoveToXY](#movetoxy)|Taşır `CRect` için belirlenen x ve y-koordinatlarının.|
|[CRect::MoveToY](#movetoy)|Taşır `CRect` için belirtilen y koordinatı.|
|[CRect::NormalizeRect](#normalizerect)|Yüksekliğini ve genişliğini standartlaştırır `CRect`.|
|[CRect::OffsetRect](#offsetrect)|Taşır `CRect` tarafından belirtilen uzaklık.|
|[CRect::PtInRect](#ptinrect)|Belirtilen nokta içinde kaynaklandığını olup olmadığını belirler `CRect`.|
|[CRect::SetRect](#setrect)|Boyutlarını ayarlar `CRect`.|
|[CRect::SetRectEmpty](#setrectempty)|Kümeleri `CRect` için boş bir dikdörtgen (tüm koordinatların eşit 0).|
|[CRect::Size](#size)|Boyutunu hesaplar `CRect`.|
|[CRect::SubtractRect](#subtractrect)|Başka bir bir dikdörtgen çıkarır.|
|[CRect::TopLeft](#topleft)|Sol üst noktasını döndürür `CRect`.|
|[CRect::UnionRect](#unionrect)|Kümeleri `CRect` iki dikdörtgenler birleşimi eşittir.|
|[CRect::Width](#width)|Genişliği hesaplar `CRect`.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CRect::operator-](#operator_-)|Öğesinden belirtilen uzaklık çıkarır `CRect` veya Söndür `CRect` ve sonuç döndüren `CRect`.|
|[LPCRECT CRect::operator](#operator_lpcrect)|Dönüştürür bir `CRect` için bir `LPCRECT`.|
|[LPRECT CRect::operator](#operator_lprect)|Dönüştürür bir `CRect` için bir `LPRECT`.|
|[CRect::operator! =](#operator_neq)|Belirler olmadığını `CRect` dikdörtgen eşit değil.|
|[CRect::operator &amp;](#operator_amp)|Kesişimi oluşturur `CRect` ve bir dikdörtgen ve sonuç döndüren `CRect`.|
|[CRect::operator &amp;=](#operator_amp_eq)|Kümeleri `CRect` kesişimi eşit `CRect` ve bir dikdörtgen.|
|[CRect::operator &#124;](#operator_or)|Birleşimini oluşturur `CRect` ve bir dikdörtgen ve sonuç döndüren `CRect`.|
|[CRect::operator &#124;=](#operator_or_eq)|Kümeleri `CRect` birleşimi eşit `CRect` ve bir dikdörtgen.|
|[CRect::operator +](#operator_add)|İçin belirtilen uzaklık ekler `CRect` veya Şişir `CRect` ve sonuç döndüren `CRect`.|
|[CRect::operator +=](#operator_add_eq)|İçin belirtilen uzaklık ekler `CRect` veya Şişir `CRect`.|
|[CRect::operator =](#operator_eq)|Bir dikdörtgene boyutlarını kopyalar `CRect`.|
|[CRect::operator-=](#operator_-_eq)|Öğesinden belirtilen uzaklık çıkarır `CRect` veya Söndür `CRect`.|
|[CRect::operator ==](#operator_eq_eq)|Belirler olmadığını `CRect` dikdörtgen eşittir.|

## <a name="remarks"></a>Açıklamalar

`CRect` Ayrıca yönlendirmek üzere öğe işlevleri içerir `CRect` nesneleri ve Windows `RECT` yapıları.

A `CRect` işlevi parametre olarak nesne geçirilebilir her yerde bir `RECT` yapısını `LPCRECT`, veya `LPRECT` geçirilebilir.

> [!NOTE]
> Bu sınıf türetilir `tagRECT` yapısı. (Adın `tagRECT` için daha az yaygın olarak kullanılan bir ad `RECT` yapısı.) Buna veri üyeleri (`left`, `top`, `right`, ve `bottom`), `RECT` yapısı erişilebilir veri üyeleri olan `CRect`.

A `CRect` bir dikdörtgenin sol üst ve sağ alt noktalarını tanımlayan üye değişkenleri içerir.

Belirtirken bir `CRect`, böylece bu normalleştirilmiş oluşturulacağına ilişkin dikkatli olmanız gerekir — diğer bir deyişle, sol koordinatını sağa ve en küçük değeri, alt değerinden küçük. Örneğin, (10,10) bir üst sol ve sağ alt köşesindeki (20,20) normalleştirilmiş bir dikdörtgen tanımlar ancak (20,20) bir üst sol ve sağ alt köşesindeki (10,10) Normalleştirilmemiş bir dikdörtgen tanımlar. Dikdörtgen Normalleştirilmemiş, birçok `CRect` üye işlevleri, hatalı sonuçlar döndürebilir. (Bkz [CRect::NormalizeRect](#normalizerect) bu işlevlerin listesi.) Normalleştirilmiş dikdörtgenler gerektiren bir işlevi çağırmadan önce çağırarak Normalleştirilmemiş dikdörtgenler normalleştirmek `NormalizeRect` işlevi.

Değiştirirken dikkatli bir `CRect` ile [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) ve [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) üye işlevleri. Y-uzantı olarak negatif güvenilecek şekilde görünen bağlam eşleme modunu olup olmadığını `MM_LOENGLISH`, ardından `CDC::DPtoLP` dönüştüren `CRect` en üst alt büyük olmasını sağlayın. Gibi işlevler `Height` ve `Size` ardından dönüştürülmüş yüksekliği için negatif değerler döndürür `CRect`, dikdörtgen Normalleştirilmemiş olacaktır.

Ne zaman kullanarak aşırı `CRect` operatörleri birinci işlenenin olmalıdır bir `CRect`; ikinci olabilir bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagRECT`

`CRect`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atltypes.h

##  <a name="bottomright"></a>  CRect::BottomRight

Koordinatları başvuru olarak döndürülen bir [CPoint](cpoint-class.md) bulunan nesne `CRect`.

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin sağ alt köşesinin koordinatlarını.

### <a name="remarks"></a>Açıklamalar

Alın ya da Dikdörtgen sağ alt köşesindeki ayarlamak için bu işlevi kullanabilirsiniz. Köşe atama işlecinin sol tarafında bu işlevi kullanarak ayarlayın.

### <a name="example"></a>Örnek

```cpp
// use BottomRight() to retrieve the bottom
// right POINT
CRect rect(210, 150, 350, 900);
CPoint ptDown;

ptDown = rect.BottomRight();

// ptDown is now set to (350, 900)
ASSERT(ptDown == CPoint(350, 900));

// or, use BottomRight() to set the bottom
// right POINT
CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);

CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);
rect2.BottomRight() = ptLow;

// rect2 is now (10, 10, 180, 180)
ASSERT(rect2 == CRect(10, 10, 180, 180));
```

##  <a name="centerpoint"></a>  CRect::CenterPoint

Hesaplar, centerpoint `CRect` sol ve sağ değerlerin ekleyerek ve iki ile bölme ve üst ve alt değer ekleme ve iki ile bölünüyor.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

A `CPoint` , centerpoint nesnesini `CRect`.

### <a name="example"></a>Örnek

```cpp
// Code from this OnPaint() implementation can be pasted into your own application
// to draw lines that would look like a letter "Y" within your dialog.
void CMyDlg::OnPaint()
{
    CPaintDC dc(this);

    // device context for painting

    // get the size and position of the client area of
    // your window

    CRect rect;
    GetClientRect(&rect);

    // Move the current pen to the top left of the window. We call the
    // TopLeft() member of CRect here and it returns a CPoint object we
    // pass to the override of CDC::MoveTo() that accepts a CPoint.

    dc.MoveTo(rect.TopLeft());

    // Draw a line from the top left to the center of the window.
    // CenterPoint() gives us the middle point of the window as a
    // CPoint, and since CDC::LineTo() has an override that accepts a
    // CPoint, we can just pass it along.

    dc.LineTo(rect.CenterPoint());

    // Now, draw a line to the top right of the window. There's no
    // CRect member which returns a CPoint for the top right of the
    // window, so we'll reference the CPoint members directly and call
    // the CDC::LineTo() override which takes two integers.

    dc.LineTo(rect.right, rect.top);

    // The top part of the "Y" is drawn. Now, we'll draw the stem. We
    // start from the center point.

    dc.MoveTo(rect.CenterPoint());

    // and then draw to the middle of the bottom edge of the window.
    // We'll get the x-coordinate from the x member of the CPOINT
    // returned by CenterPoint(), and the y value comes directly from
    // the rect.

    dc.LineTo(rect.CenterPoint().x, rect.bottom);
}
```

##  <a name="copyrect"></a>  CRect::CopyRect

Kopya `lpSrcRect` dikdörtgene `CRect`.

```
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>Parametreler

*lpSrcRect*<br/>
İşaret [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` kopyalanacak nesne.

### <a name="example"></a>Örnek

```cpp
CRect rectSource(35, 10, 125, 10);
CRect rectDest;

rectDest.CopyRect(&rectSource);

// rectDest is now set to (35, 10, 125, 10)

RECT rectSource2;
rectSource2.left = 0;
rectSource2.top = 0;
rectSource2.bottom = 480;
rectSource2.right = 640;

rectDest.CopyRect(&rectSource2);

// works against RECT structures, too!
// rectDest is now set to (0, 0, 640, 480)
```

##  <a name="crect"></a>  CRect::CRect

Oluşturur bir `CRect` nesne.

```
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();
```

### <a name="parameters"></a>Parametreler

*m*<br/>
Sol konumu belirtir `CRect`.

*T*<br/>
Üst belirtir `CRect`.

*r*<br/>
Doğru konumunu belirtir `CRect`.

*b*<br/>
Sonuna belirten `CRect`.

*srcRect*<br/>
Başvurduğu [RECT](/windows/desktop/api/windef/ns-windef-tagrect) koordinatları ile yapısı `CRect`.

*lpSrcRect*<br/>
İşaret `RECT` koordinatları ile yapısı `CRect`.

*Noktası*<br/>
Dikdörtgenin oluşturulması başlangıç noktasını belirtir. Sol üst köşesine karşılık gelir.

*Boyutu*<br/>
Sol üst köşedeki kendisinden oluşturulacağı dikdörtgenin öteleme sağ alt köşeye belirtir.

*Sol üst*<br/>
Sol üst konumunu belirtir `CRect`.

*BottomRight*<br/>
Sağ alt köşesinin konumunu belirtir `CRect`.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken olmadan verilirse `left`, `top`, `right`, ve `bottom` üyeleri başlatılmadı.

`CRect`(`const RECT&`) Ve `CRect`(`LPCRECT`) oluşturucular gerçekleştirmek bir [CopyRect](#copyrect). Diğer oluşturucular doğrudan üye değişkenleri nesnesinin başlatın.

### <a name="example"></a>Örnek

```cpp
// default constructor doesn't initialize!
CRect rectUnknown;

// four-integers are left, top, right, and bottom
CRect rect(0, 0, 100, 50);
ASSERT(rect.Width() == 100);
ASSERT(rect.Height() == 50);

// Initialize from RECT stucture
RECT sdkRect;
sdkRect.left = 0;
sdkRect.top = 0;
sdkRect.right = 100;
sdkRect.bottom = 50;

CRect rect2(sdkRect);
// by reference
CRect rect3(&sdkRect);

// by address
ASSERT(rect2 == rect);
ASSERT(rect3 == rect);

// from a point and a size
CPoint pt(0, 0);
CSize sz(100, 50);
CRect rect4(pt, sz);
ASSERT(rect4 == rect2);

// from two points
CPoint ptBottomRight(100, 50);
CRect rect5(pt, ptBottomRight);
ASSERT(rect5 == rect4);
```

##  <a name="deflaterect"></a>  CRect::DeflateRect

`DeflateRect` Söndür `CRect` alt kenarı alt merkezine taşıyarak.

```
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sol deflate için birim sayısını ve sağ tarafında belirtir `CRect`.

*Y*<br/>
Üst ve alt deflate için birim sayısını belirtir `CRect`.

*Boyutu*<br/>
A [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) veya [CSize](csize-class.md) deflate için birim sayısını belirten `CRect`. `cx` Değerini belirtir ve sol tarafında deflate için birim sayısını ve `cy` değeri üst ve alt deflate için birim sayısını belirtir.

*lpRect*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` her yan deflate için birim sayısını belirtir.

*m*<br/>
Sol tarafındaki deflate için birim sayısını belirtir `CRect`.

*T*<br/>
Üst deflate için birim sayısını belirtir `CRect`.

*r*<br/>
Sağ tarafında deflate için birim sayısını belirtir `CRect`.

*b*<br/>
Alt deflate için birim sayısını belirtir `CRect`.

### <a name="remarks"></a>Açıklamalar

Bunu yapmak için `DeflateRect` sol ve üst birimi ekler ve sağ ve alt birimleri çıkarır. Parametreleri `DeflateRect` imzalanmış değerleri; pozitif değerlere deflate `CRect` ve negatif değerler Şişir.

İlk iki aşırı yüklemeler iki zıt tarafına çiftlerini deflate `CRect` böylece toplam genişliğini iki kat azalır *x* (veya `cx`) ve toplam yükseklik iki kat azalır *y* () veya `cy`). Her iki tarafındaki diğer iki aşırı deflate `CRect` diğerlerinden.

### <a name="example"></a>Örnek

```cpp
   CRect rect(10, 10, 50, 50);
   rect.DeflateRect(1, 2);
   ASSERT(rect.left == 11 && rect.right == 49);
   ASSERT(rect.top == 12 && rect.bottom == 48);

   CRect rect2(10, 10, 50, 50);
   CRect rectDeflate(1, 2, 3, 4);
   rect2.DeflateRect(&rectDeflate);
   ASSERT(rect2.left == 11 && rect2.right == 47);
   ASSERT(rect2.top == 12 && rect2.bottom == 46);
```

##  <a name="equalrect"></a>  CRect::EqualRect

Belirler olmadığını `CRect` verilen dikdörtgene eşittir.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` bir dikdörtgenin sol ve sağ alt köşesinde koordinatları içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

İki dikdörtgenler aynı üst, sol, alt ve sağ değerlerin varsa sıfır; Aksi durumda 0.

> [!NOTE]
>  Her ikisi de dikdörtgenler normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgenler normalleştirmek için.

### <a name="example"></a>Örnek

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1.EqualRect(rect2));
ASSERT(!rect1.EqualRect(rect3));
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1.EqualRect(&test));
```

##  <a name="height"></a>  CRect::Height

Yüksekliğini hesaplar `CRect` alt üst değer çıkararak.

```
int Height() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yüksekliğini `CRect`.

### <a name="remarks"></a>Açıklamalar

Sonuç değerini, negatif olabilir.

> [!NOTE]
>  Dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgeni Normalleştir için.

### <a name="example"></a>Örnek

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

##  <a name="inflaterect"></a>  CRect::InflateRect

`InflateRect` Şişir `CRect` merkezinden uzakta, yüz taşıyarak.

```
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sol doldurmak için birim sayısını ve sağ tarafında belirtir `CRect`.

*Y*<br/>
Üst ve alt doldurmak için birim sayısını belirtir `CRect`.

*Boyutu*<br/>
A [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) veya [CSize](csize-class.md) doldurmak için birim sayısını belirten `CRect`. `cx` Değerini belirtir ve sol tarafında doldurmak için birim sayısını ve `cy` değeri üst ve alt doldurmak için birim sayısını belirtir.

*lpRect*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` her yan doldurmak için birim sayısını belirtir.

*m*<br/>
Sol tarafındaki doldurmak için birim sayısını belirtir `CRect`.

*T*<br/>
Üst doldurmak için birim sayısını belirtir `CRect`.

*r*<br/>
Sağ tarafında doldurmak için birim sayısını belirtir `CRect`.

*b*<br/>
Alt doldurmak için birim sayısını belirtir `CRect`.

### <a name="remarks"></a>Açıklamalar

Bunu yapmak için `InflateRect` üst ve sol birimlerinden çıkarır ve sağ ve alt birimleri ekler. Parametreleri `InflateRect` imzalanmış değerleri; pozitif değerleri Şişir `CRect` ve negatif değerler deflate.

İlk iki aşırı yüklemeler iki zıt tarafına çiftlerini Şişir `CRect` böylece toplam genişliğini iki sürelerine göre artırılır *x* (veya `cx`) ve toplam yükseklik iki kat daha fazla *y* () veya `cy`). Her iki tarafındaki diğer iki aşırı Şişir `CRect` diğerlerinden.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

##  <a name="intersectrect"></a>  CRect::IntersectRect

Yapar bir `CRect` iki mevcut dikdörtgenler kesişimi eşittir.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRect1*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` kaynak dikdörtgenin içeren nesne.

*lpRect2*<br/>
İşaret eden bir `RECT` yapısı veya `CRect` kaynak dikdörtgenin içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Kesişimi boş değilse, sıfır olmayan; kesişimi boş ise 0.

### <a name="remarks"></a>Açıklamalar

Her iki mevcut dikdörtgenler yer alan en büyük dikdörtgen kesişimi olur.

> [!NOTE]
>  Her ikisi de dikdörtgenler normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgenler normalleştirmek için.

### <a name="example"></a>Örnek

```cpp
CRect rectOne(125, 0, 150, 200);
CRect rectTwo(0, 75, 350,  95);
CRect rectInter;
```cpp
   CRect rectOne(125,  0, 150, 200);
   CRect rectTwo(0, 75, 350, 95);
   CRect rectInter;

   rectInter.IntersectRect(rectOne, rectTwo);
ASSERT(rectInter == CRect(125, 75, 150, 95));
// operator &= can do the same task:

CRect rectInter2 = rectOne;
rectInter2 &= rectTwo;
ASSERT(rectInter2 == CRect(125, 75, 150, 95));
```

##  <a name="isrectempty"></a>  CRect::IsRectEmpty

Belirler olmadığını `CRect` boştur.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yalnız `CRect` boş; 0 olduğundan, `CRect` boş değil.

### <a name="remarks"></a>Açıklamalar

Boş ise genişliği ve yüksekliği 0 veya negatif bir dikdörtgen. Farklıdır `IsRectNull`, tüm koordinatların dikdörtgenin sıfır olup olmadığını belirler.

> [!NOTE]
>  Dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgeni Normalleştir için.

### <a name="example"></a>Örnek

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
```cpp
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
   ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
   ASSERT(rectEmpty.IsRectEmpty());
```

##  <a name="isrectnull"></a>  CRect::IsRectNull

Üst, sol alt olup olmadığını, belirler ve değerlerini sağ `CRect` tüm 0'a eşit.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `CRect`kullanıcının üst, sol, alt ve sağ değerler tüm 0'a eşit; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Farklıdır `IsRectEmpty`, dikdörtgen boş olup olmadığını belirler.

### <a name="example"></a>Örnek

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
```cpp
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
   ASSERT(!rectSome.IsRectNull());
// note that null means _all_ zeros

CRect rectNotNull(0, 0, 35, 50);
ASSERT(!rectNotNull.IsRectNull());
```

##  <a name="movetox"></a>  CRect::MoveToX

Dikdörtgen tarafından belirtilen mutlak x koordinatı taşımak için bu işlevi çağırın *x*.

```
void MoveToX(int x) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Mutlak x koordinatını dikdörtgenin sol üst köşesinin.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);
```cpp
   CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

   // rect is now (10, 0, 110, 100);
   ASSERT(rect == CRect(10, 0, 110, 100));
```

##  <a name="movetoxy"></a>  CRect::MoveToXY

Dikdörtgeni mutlak x ve y-belirtilen koordinatları için taşımak için bu işlevi çağırın.

```
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Mutlak x koordinatını dikdörtgenin sol üst köşesinin.

*Y*<br/>
Mutlak y koordinatını dikdörtgenin sol üst köşesinin.

*Noktası*<br/>
A `POINT` yapısı mutlak dikdörtgenin sol üst köşesine belirtme.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
```cpp
   CRect rect(0, 0, 100, 100);
   rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
   ASSERT(rect == CRect(10, 10, 110, 110));
```

##  <a name="movetoy"></a>  CRect::MoveToY

Dikdörtgen tarafından belirtilen mutlak y koordinatı taşımak için bu işlevi çağırın *y*.

```
void MoveToY(int y) throw();
```

### <a name="parameters"></a>Parametreler

*Y*<br/>
Mutlak y koordinatını dikdörtgenin sol üst köşesinin.

### <a name="example"></a>Örnek

```cpp
   CRect rect(0, 0, 100, 100);
   rect.MoveToY(10);
   // rect is now (0, 10, 100, 110);
   ASSERT(rect == CRect(0, 10, 100, 110));
```

##  <a name="normalizerect"></a>  CRect::NormalizeRect

Normalleştirir `CRect` böylece yükseklik ve genişlik pozitif olur.

```
void NormalizeRect() throw();
```

### <a name="remarks"></a>Açıklamalar

Dikdörtgen dördüncü quadrant konumlandırma için Windows genellikle koordinatları kullanan normalleştirilmiştir. `NormalizeRect` üst ve alt değerlerini karşılaştırır ve üst, alt büyükse, bunları değiştirir. Benzer şekilde, sol, sağ büyükse, sol ve sağ değerlerin değiştirir. Bu işlev ve dikdörtgenler ters farklı eşleme modu ile ilgilenirken kullanışlıdır.

> [!NOTE]
> Aşağıdaki `CRect` üye işlevleri, düzgün çalışması için normalleştirilmiş dikdörtgenler gerektirir: [Yükseklik](#height), [genişliği](#width), [boyutu](#size), [IsRectEmpty](#isrectempty), [PtInRect](#ptinrect), [EqualRect](#equalrect), [UnionRect](#unionrect), [IntersectRect](#intersectrect), [SubtractRect](#subtractrect), [işleç ==](#operator_eq_eq), [işleç! =](#operator_neq), [işleci &#124; ](#operator_or), [işleci &#124;=](#operator_or_eq), [işleci &](#operator_amp), ve [işleci & =](#operator_amp_eq).

### <a name="example"></a>Örnek

```cpp
   CRect rect1(110, 100, 250, 310);
   CRect rect2(250, 310, 110, 100);
   rect1.NormalizeRect();
   rect2.NormalizeRect();
   ASSERT(rect1 == rect2);
```

##  <a name="offsetrect"></a>  CRect::OffsetRect

Taşır `CRect` tarafından belirtilen uzaklık.

```
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sola taşı için ya da sağ belirtir. Sola Taşı negatif olmalıdır.

*Y*<br/>
Yukarı veya aşağı taşımak için belirtir. Yukarı taşımak için negatif olmalıdır.

*Noktası*<br/>
İçeren bir [noktası](/windows/desktop/api/windef/ns-windef-tagpoint) yapısı veya [CPoint](cpoint-class.md) nesne taşımak, her iki boyutu belirtme.

*Boyutu*<br/>
İçeren bir [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) yapısı veya [CSize](csize-class.md) nesne taşımak, her iki boyutu belirtme.

### <a name="remarks"></a>Açıklamalar

Taşır `CRect` *x* birim x ekseni boyunca ve *y* birim y ekseni boyunca. *x* ve *y* parametreleri olan imzalı değerler, bu nedenle `CRect` taşınıp sola veya sağa ve yukarı veya aşağı doğru.

### <a name="example"></a>Örnek

```cpp
   CRect rect(0, 0, 35, 35);
   rect.OffsetRect(230, 230);

   // rect is now (230, 230, 265, 265)
   ASSERT(rect == CRect(230, 230, 265, 265));
```

##  <a name="operator_lpcrect"></a>  CRect::operator LPCRECT dönüştürür bir `CRect` için bir [LPCRECT](../../mfc/reference/data-types-mfc.md).

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev kullandığınızda address-of gerekmez (**&**) işleci. Bu işleç, başarılı olduğunda otomatik olarak kullanılacak bir `CRect` bekliyor bir işlev nesnesine bir `LPCRECT`.

##  <a name="operator_lprect"></a>  LPRECT CRect::operator

Dönüştürür bir `CRect` için bir [LPRECT](../../mfc/reference/data-types-mfc.md).

```
operator LPRECT() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev kullandığınızda address-of gerekmez (**&**) işleci. Bu işleç, başarılı olduğunda otomatik olarak kullanılacak bir `CRect` bekliyor bir işlev nesnesine bir `LPRECT`.

### <a name="example"></a>Örnek

Örneğin bakın [CRect::operator LPCRECT](#operator_lpcrect).

##  <a name="operator_eq"></a>  CRect::operator =

Atar *srcRect* için `CRect`.

```
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>Parametreler

*srcRect*<br/>
Kaynak dikdörtgen ifade eder. Olabilir bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) veya `CRect`.

### <a name="example"></a>Örnek

```cpp
   CRect rect(0, 0, 127, 168);
   CRect rect2;

   rect2 = rect;
   ASSERT(rect2 == CRect(0, 0, 127, 168));
```

##  <a name="operator_eq_eq"></a>  CRect::operator ==

Belirler olmadığını `rect` eşittir `CRect` karşılaştırarak, sol ve sağ alt köşe koordinatları.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Kaynak dikdörtgen ifade eder. Olabilir bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) veya `CRect`.

### <a name="return-value"></a>Dönüş Değeri

Eşit olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Her ikisi de dikdörtgenler normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgenler normalleştirmek için.

### <a name="example"></a>Örnek

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1 == rect2);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1 == test);
```

##  <a name="operator_neq"></a>  CRect::operator! =

Belirler olmadığını *rect* eşit değildir `CRect` karşılaştırarak, sol ve sağ alt köşe koordinatları.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Kaynak dikdörtgen ifade eder. Olabilir bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) veya `CRect`.

### <a name="return-value"></a>Dönüş Değeri

Eşit değil olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Her ikisi de dikdörtgenler normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgenler normalleştirmek için.

### <a name="example"></a>Örnek

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999,  6,  3);
ASSERT(rect1 != rect3);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect3 != test);
```

##  <a name="operator_add_eq"></a>  CRect::operator +=

İlk iki aşırı taşıma `CRect` tarafından belirtilen uzaklık.

```
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
A [noktası](/windows/desktop/api/windef/ns-windef-tagpoint) yapısı veya [CPoint](cpoint-class.md) dikdörtgeni taşımak için birim sayısını belirten bir nesne.

*Boyutu*<br/>
A [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) yapısı veya [CSize](csize-class.md) dikdörtgeni taşımak için birim sayısını belirten bir nesne.

*lpRect*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` her iki tarafındaki doldurmak için birim sayısını içeren nesne `CRect`.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy`) değerleri eklenir `CRect`.

Üçüncü aşırı yükleme Şişir `CRect` birimleri belirtilen her üyesi, parametre sayısı.

### <a name="example"></a>Örnek

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint  pt(35, 65);
   CRect   rect2(135, 300, 235, 400);

   rect1 += pt;
   ASSERT(rect1 == rect2);
```

##  <a name="operator_-_eq"></a>  CRect::operator-=

İlk iki aşırı taşıma `CRect` tarafından belirtilen uzaklık.

```
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
A [noktası](/windows/desktop/api/windef/ns-windef-tagpoint) yapısı veya [CPoint](cpoint-class.md) dikdörtgeni taşımak için birim sayısını belirten bir nesne.

*Boyutu*<br/>
A [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) yapısı veya [CSize](csize-class.md) dikdörtgeni taşımak için birim sayısını belirten bir nesne.

*lpRect*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` her iki tarafındaki deflate için birim sayısını içeren nesne `CRect`.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy`) değerleri, gelen çıkartılır `CRect`.

Üçüncü aşırı yükleme Söndür `CRect` birimleri belirtilen her üyesi, parametre sayısı. Bu aşırı yükleme gibi işlevleri Not [DeflateRect](#deflaterect).

### <a name="example"></a>Örnek

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);

   rect1 -= pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect1 == rectResult);
```

##  <a name="operator_amp_eq"></a>  CRect::operator &amp;=

Kümeleri `CRect` kesişimi eşit `CRect` ve `rect`.

```
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
İçeren bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) veya `CRect`.

### <a name="remarks"></a>Açıklamalar

Her iki dikdörtgenler bulunan büyük dikdörtgen kesişimi olur.

> [!NOTE]
>  Her ikisi de dikdörtgenler normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgenler normalleştirmek için.

### <a name="example"></a>Örnek

Örneğin bakın [CRect::IntersectRect](#intersectrect).

##  <a name="operator_or_eq"></a>  CRect::operator &#124;=

Kümeleri `CRect` birleşimi eşit `CRect` ve `rect`.

```
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
İçeren bir `CRect` veya [RECT](/windows/desktop/api/windef/ns-windef-tagrect).

### <a name="remarks"></a>Açıklamalar

Her iki kaynak dikdörtgenler içeren küçük dikdörtgen birleşimdir.

> [!NOTE]
>  Her ikisi de dikdörtgenler normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgenler normalleştirmek için.

### <a name="example"></a>Örnek

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);

   rect1 |= rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect1);
```

##  <a name="operator_add"></a>  CRect::operator +

İlk iki aşırı dönüş bir `CRect` eşittir nesne `CRect` tarafından belirtilen uzaklık gördüğümüz şey de.

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
A [noktası](/windows/desktop/api/windef/ns-windef-tagpoint) yapısı veya [CPoint](cpoint-class.md) dönüş değeri taşımak için birim sayısını belirten bir nesne.

*Boyutu*<br/>
A [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) yapısı veya [CSize](csize-class.md) dönüş değeri taşımak için birim sayısını belirten bir nesne.

*lpRect*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` döndürülen değer her iki tarafındaki doldurmak için birim sayısını içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

`CRect` Taşıma veya inflating `CRect` parametresinde belirtilen birimleri sayısı.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy`) parametreleri eklenir `CRect`kullanıcının getirin.

Üçüncü aşırı yükleme yeni döndürür `CRect` eşit olan `CRect` birimleri belirtilen her üyesi, parametre sayısına göre şişirileceğini.

### <a name="example"></a>Örnek

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 + pt;
   CRect   rectResult(135, 300, 235, 400);
   ASSERT(rectResult == rect2);
```

##  <a name="operator_-"></a>  CRect::operator-

İlk iki aşırı dönüş bir `CRect` eşittir nesne `CRect` tarafından belirtilen uzaklık gördüğümüz şey de.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
A [noktası](/windows/desktop/api/windef/ns-windef-tagpoint) yapısı veya `CPoint` dönüş değeri taşımak için birim sayısını belirten bir nesne.

*Boyutu*<br/>
A [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) yapısı veya `CSize` dönüş değeri taşımak için birim sayısını belirten bir nesne.

*lpRect*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` döndürülen değer her iki tarafındaki deflate için birim sayısını içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

`CRect` Taşıma veya deflating `CRect` parametresinde belirtilen birimleri sayısı.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy`) parametreleri çıkartılır `CRect`kullanıcının getirin.

Üçüncü aşırı yükleme yeni döndürür `CRect` eşit olan `CRect` birimleri belirtilen her üyesi, parametre sayısına göre çarpanını. Bu aşırı yükleme gibi işlevleri Not [DeflateRect](#deflaterect)değil [SubtractRect](#subtractrect).

### <a name="example"></a>Örnek

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 - pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect2 == rectResult);
```

##  <a name="operator_amp"></a>  CRect::operator &amp;

Döndürür bir `CRect` kesişimi diğer bir deyişle `CRect` ve *rect2*.

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>Parametreler

*rect2*<br/>
İçeren bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) veya `CRect`.

### <a name="return-value"></a>Dönüş Değeri

A `CRect` kesişimi diğer bir deyişle `CRect` ve *rect2*.

### <a name="remarks"></a>Açıklamalar

Her iki dikdörtgenler bulunan büyük dikdörtgen kesişimi olur.

> [!NOTE]
>  Her ikisi de dikdörtgenler normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgenler normalleştirmek için.

### <a name="example"></a>Örnek

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 & rect2;
   CRect   rectResult(100, 100, 200, 200);
   ASSERT(rectResult == rect3);
```

##  <a name="operator_or"></a>  CRect::operator&#124;

Döndürür bir `CRect` diğer bir deyişle birleşimi `CRect` ve *rect2*.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>Parametreler

*rect2*<br/>
İçeren bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) veya `CRect`.

### <a name="return-value"></a>Dönüş Değeri

A `CRect` diğer bir deyişle birleşimi `CRect` ve *rect2*.

### <a name="remarks"></a>Açıklamalar

Hem dikdörtgenler içeren küçük bir dikdörtgen birleşimdir.

> [!NOTE]
>  Her ikisi de dikdörtgenler normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgenler normalleştirmek için.

### <a name="example"></a>Örnek

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 | rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);
```

##  <a name="ptinrect"></a>  CRect::PtInRect

Belirtilen nokta içinde kaynaklandığını olup olmadığını belirler `CRect`.

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
İçeren bir [noktası](/windows/desktop/api/windef/ns-windef-tagpoint) yapısı veya [CPoint](cpoint-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan noktası içinde yer alıyorsa `CRect`; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İçinde noktasıdır `CRect` üst veya sol üst tarafında bulunan veya dört dışlamada içinde olduğundan. Bir noktasını sağ veya alt tarafında dışında `CRect`.

> [!NOTE]
>  Dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgeni Normalleştir için.

### <a name="example"></a>Örnek

```cpp
CRect rect(5, 5, 100, 100);
CPoint pt1(35, 50);
CPoint pt2(125, 298);

// this is true, because pt1 is inside the rectangle
ASSERT(rect.PtInRect(pt1));

// this is NOT true, because pt2 is outside the rectangle
ASSERT(!rect.PtInRect(pt2));

// note that the right and the bottom aren't inside
ASSERT(!rect.PtInRect(CPoint(35, 100)));
ASSERT(!rect.PtInRect(CPoint(100, 98)));

// but the top and the left are inside
ASSERT(rect.PtInRect(CPoint(5, 65)));
ASSERT(rect.PtInRect(CPoint(88, 5)));

// and that PtInRect() works against a POINT, too
POINT pt;
pt.x = 35;
pt.y = 50;
ASSERT(rect.PtInRect(pt));
```

##  <a name="setrect"></a>  CRect::SetRect

Boyutlarını ayarlar `CRect` belirtilen koordinatlara.

```
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Sol üst köşesinin x koordinatını belirtir.

*y1*<br/>
Sol üst köşesinin y koordinatını belirtir.

*x2*<br/>
Sağ alt köşesinin x koordinatını belirtir.

*y2*<br/>
Sağ alt köşesinin y koordinatını belirtir.

### <a name="example"></a>Örnek

```cpp
   CRect rect;
   rect.SetRect(256, 256, 512, 512);
   ASSERT(rect == CRect(256, 256, 512, 512));
```

##  <a name="setrectempty"></a>  CRect::SetRectEmpty

Yapar `CRect` tüm koordinatların sıfır olarak ayarlayarak bir dikdörtgen null.

```
void SetRectEmpty() throw();
```

### <a name="example"></a>Örnek

```cpp
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());
```

##  <a name="size"></a>  CRect::SIZE

`cx` Ve `cy` dönüş değeri üyeleri içeren yüksekliğini ve genişliğini `CRect`.

```
CSize Size() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

A [CSize](csize-class.md) boyutunu içeren nesne `CRect`.

### <a name="remarks"></a>Açıklamalar

Yükseklik veya Genişlik negatif olabilir.

> [!NOTE]
>  Dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgeni Normalleştir için.

### <a name="example"></a>Örnek

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

##  <a name="subtractrect"></a>  CRect::SubtractRect

Boyutlarını yapar `CRect` çıkarılmasının eşit `lpRectSrc2` gelen `lpRectSrc1`.

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRectSrc1*<br/>
İşaret [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya `CRect` içinden bir dikdörtgen çıkarılsın için nesne.

*lpRectSrc2*<br/>
İşaret `RECT` yapısı veya `CRect` dikdörtgenden çıkarılsın için nesne tarafından işaret edilen *lpRectSrc1* parametresi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Tüm noktaları içeren küçük dikdörtgen çıkarma olan *lpRectScr1* kesişimi içinde olmayan *lpRectScr1* ve *lpRectScr2*.

Tarafından belirtilen dikdörtgen *lpRectSrc1* dikdörtgen belirtilen değişmeden kalacaktır *lpRectSrc2* tarafından belirtilen dikdörtgen tamamen çakışmayacak *lpRectSrc1*en az bir, x - veya y-yönergeleri.

Örneğin, varsa *lpRectSrc1* olan (10,10, 100,100) ve *lpRectSrc2* olan (50,50, 150,150) dikdörtgen tarafından işaret edilen *lpRectSrc1* ne zaman değişmedi döndürülen işlev. Varsa *lpRectSrc1* olan (10,10, 100,100) ve *lpRectSrc2* olan (50,10, 150,150), ancak dikdörtgen tarafından işaret edilen *lpRectSrc1* (10,10, koordinatlarını içerir işlev döndürüldüğünde 50,100).

`SubtractRect` aynı değil [işleci -](#operator_-) ya da [-= işleci](#operator_-_eq). Bu işleçler hiçbiri hiç olmadığı kadar çağıran `SubtractRect`.

> [!NOTE]
>  Her ikisi de dikdörtgenler normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgenler normalleştirmek için.

### <a name="example"></a>Örnek

```cpp
   RECT   rectOne;
   RECT   rectTwo;

   rectOne.left = 10;
   rectOne.top = 10;
   rectOne.bottom = 100;
   rectOne.right = 100;

   rectTwo.left = 50;
   rectTwo.top = 10;
   rectTwo.bottom = 150;
   rectTwo.right = 150;

   CRect   rectDiff;

   rectDiff.SubtractRect(&rectOne, &rectTwo);
CRect   rectResult(10, 10, 50, 100);

   ASSERT(rectDiff == rectResult);

   // works for CRect, too, since there is
   // implicit CRect -> LPCRECT conversion

   CRect rect1(10, 10, 100, 100);
   CRect rect2(50, 10, 150, 150);
   CRect rectOut;

   rectOut.SubtractRect(rect1, rect2);
   ASSERT(rectResult == rectOut);
```

##  <a name="topleft"></a>  CRect::TopLeft

Koordinatları başvuru olarak döndürülen bir [CPoint](cpoint-class.md) bulunan nesne `CRect`.

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin sol üst köşesinin koordinatlarını.

### <a name="remarks"></a>Açıklamalar

Alın ya da dikdörtgenin sol üst köşedeki ayarlamak için bu işlevi kullanabilirsiniz. Köşe atama işlecinin sol tarafında bu işlevi kullanarak ayarlayın.

### <a name="example"></a>Örnek

Örneğin bakın [CRect::CenterPoint](#centerpoint).

##  <a name="unionrect"></a>  CRect::UnionRect

Boyutlarını yapar `CRect` UNION iki kaynak dikdörtgenin eşittir.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRect1*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) veya `CRect` kaynak dikdörtgenin içeren.

*lpRect2*<br/>
İşaret eden bir `RECT` veya `CRect` kaynak dikdörtgenin içeren.

### <a name="return-value"></a>Dönüş Değeri

Birleşim boş değilse, sıfır olmayan; birleşim boşsa 0.

### <a name="remarks"></a>Açıklamalar

Her iki kaynak dikdörtgenler içeren küçük dikdörtgen birleşimdir.

Windows, boş bir dikdörtgen boyutlarını yoksayar; diğer bir deyişle, hiçbir yükseklik veya genişliği olan bir dikdörtgen.

> [!NOTE]
>  Her ikisi de dikdörtgenler normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgenler normalleştirmek için.

### <a name="example"></a>Örnek

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3.UnionRect(&rect1, &rect2);
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);
```

##  <a name="width"></a>  CRect::Width

Genişliği hesaplar `CRect` doğru sol değer çıkararak.

```
int Width() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Genişliği `CRect`.

### <a name="remarks"></a>Açıklamalar

Genişliği negatif olabilir.

> [!NOTE]
>  Dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağırmadan önce dikdörtgeni Normalleştir için.

### <a name="example"></a>Örnek

```cpp
   CRect rect(20, 30, 80, 70);
   int nWid = rect.Width();
   // nWid is now 60
   ASSERT(nWid == 60);
```

## <a name="see-also"></a>Ayrıca bkz.

[CPoint Sınıfı](cpoint-class.md)<br/>
[CSize Sınıfı](csize-class.md)<br/>
[RECT](/windows/desktop/api/windef/ns-windef-tagrect)
