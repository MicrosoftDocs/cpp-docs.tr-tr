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
ms.openlocfilehash: f45090971e8dbb89ae281b408cc3a14e102ffe17
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502884"
---
# <a name="crect-class"></a>CRect sınıfı

Bir Windows [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına benzer.

## <a name="syntax"></a>Sözdizimi

```
class CRect : public tagRECT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRect:: CRect](#crect)|Bir `CRect` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRect:: BottomRight](#bottomright)|Sağ alt noktasını döndürür `CRect` .|
|[CRect:: CenterPoint](#centerpoint)|Öğesinin merkez noktasını döndürür `CRect` .|
|[CRect:: CopyRect](#copyrect)|Kaynak dikdörtgenin boyutlarını öğesine kopyalar `CRect` .|
|[CRect::D eflateRect](#deflaterect)|Genişliğini ve yüksekliğini düşürür `CRect` .|
|[CRect:: EqualRect](#equalrect)|`CRect`Verilen dikdörtgene eşit olup olmadığını belirler.|
|[CRect:: Height](#height)|Yüksekliğini hesaplar `CRect` .|
|[CRect:: InflateRect](#inflaterect)|Genişliğini ve yüksekliğini artırır `CRect` .|
|[CRect:: IntersectRect](#intersectrect)|`CRect`İki dikdörtgenin kesişimine eşit olarak ayarlanır.|
|[CRect:: IsRectEmpty](#isrectempty)|Boş olup olmadığını belirler `CRect` . `CRect` Genişlik ve/veya Yükseklik 0 ise boştur.|
|[CRect:: IsRectNull](#isrectnull)|`top`,, `bottom` `left` Ve `right` üye değişkenlerinin tümünün 0 ' a eşit olup olmadığını belirler.|
|[CRect:: MoveToX](#movetox)|`CRect`Belirtilen x koordinatına gider.|
|[CRect:: MoveToXY](#movetoxy)|`CRect`Belirtilen x ve y koordinatlarına gider.|
|[CRect:: Moveoyunu](#movetoy)|`CRect`Belirtilen y koordinatıyla gider.|
|[CRect:: NormalizeRect](#normalizerect)|Yüksekliğini ve genişliğini standartlaştırır `CRect` .|
|[CRect:: OffsetRect](#offsetrect)|`CRect`Belirtilen uzaklıklara göre gider.|
|[CRect::P tInRect](#ptinrect)|Belirtilen noktanın içinde olup olmadığını belirler `CRect` .|
|[CRect:: SetRect](#setrect)|Boyutlarını ayarlar `CRect` .|
|[CRect:: SetRectEmpty](#setrectempty)|`CRect`Boş bir dikdörtgene (tüm koordinatlar 0 ' a eşit) ayarlar.|
|[CRect:: size](#size)|Boyutunu hesaplar `CRect` .|
|[CRect:: SubtractRect](#subtractrect)|Bir dikdörtgeni diğerinden çıkarır.|
|[CRect:: TopLeft](#topleft)|Sol üst noktasını döndürür `CRect` .|
|[CRect:: UnionRect](#unionrect)|`CRect`İki dikdörtgenin birleşimini eşit olarak ayarlar.|
|[CRect:: Width](#width)|Genişliğini hesaplar `CRect` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CRect:: operator-](#operator_-)|Verilen uzaklıkları çıkarır `CRect` veya erteler `CRect` ve sonucu döndürür `CRect` .|
|[CRect:: operator LPCRECT](#operator_lpcrect)|Bir `CRect` öğesine dönüştürür `LPCRECT` .|
|[CRect:: operator LPRECT](#operator_lprect)|Bir `CRect` öğesine dönüştürür `LPRECT` .|
|[CRect:: operator! =](#operator_neq)|`CRect`Bir dikdörtgene eşit olup olmadığını belirler.|
|[CRect:: işleci &amp;](#operator_amp)|Ve dikdörtgeninin kesişimini oluşturur `CRect` ve sonucu döndürür `CRect` .|
|[CRect:: işleci &amp;=](#operator_amp_eq)|, `CRect` Ve dikdörtgeninin kesişimine eşit ayarlar `CRect` .|
|[CRect:: operator &#124;](#operator_or)|Ve dikdörtgeninin birleşimini oluşturur `CRect` ve sonucu döndürür `CRect` .|
|[CRect:: operator &#124;=](#operator_or_eq)|, `CRect` Ve bir dikdörtgenin birleşimini eşit olarak ayarlar `CRect` .|
|[CRect:: operator +](#operator_add)|Verilen uzaklıkları `CRect` veya geri 'leri ekler `CRect` ve sonucu döndürür `CRect` .|
|[CRect:: operator + =](#operator_add_eq)|Belirtilen uzaklıkları `CRect` veya Flap ekler `CRect` .|
|[CRect:: operator =](#operator_eq)|Bir dikdörtgenin boyutlarını öğesine kopyalar `CRect` .|
|[CRect:: operator-=](#operator_-_eq)|Belirtilen uzaklıkları çıkarır `CRect` veya ertetir `CRect` .|
|[CRect:: operator = =](#operator_eq_eq)|`CRect`Bir dikdörtgene eşit olup olmadığını belirler.|

## <a name="remarks"></a>Açıklamalar

`CRect` Ayrıca `CRect` , nesneleri ve Windows yapılarını işlemek için üye işlevleri de içerir `RECT` .

Bir `CRect` nesne, bir `RECT` yapının, `LPCRECT` veya geçirilebileceğini bir işlev parametresi olarak geçirilebilir `LPRECT` .

> [!NOTE]
> Bu sınıf `tagRECT` yapıdan türetilir. (Ad, `tagRECT` Yapı için daha yaygın olarak kullanılan bir addır `RECT` .) Bu, yapının veri üyelerinin ( `left` ,, `top` `right` ve `bottom` ) `RECT` erişilebilir veri üyeleri `CRect` olduğu anlamına gelir.

Bir `CRect` dikdörtgenin sol üst ve sağ alt noktalarını tanımlayan üye değişkenlerini içerir.

Bir belirtirken `CRect` , diğer bir deyişle, sol koordinat değerinin doğru ve en alttan küçük olması gibi diğer bir deyişle, bunu normalleştirilemez şekilde oluşturmak için dikkatli olmanız gerekir. Örneğin, (10, 10) ve sağ alt (20, 20) sol üst bir, normalleştirilmiş bir dikdörtgen tanımlar, ancak (20, 20) ve sağ alt (10, 10) sol üst bir, Normalleştirilmemiş bir dikdörtgen tanımlar. Dikdörtgen normalleştirilmez değilse birçok `CRect` üye işlevi hatalı sonuçlar döndürebilir. (Bu işlevlerin listesi için bkz. [CRect:: NormalizeRect](#normalizerect) .) Normalleştirilmiş dikdörtgenler gerektiren bir işlevi çağırmadan önce işlevi çağırarak normalleştirilmiş olmayan dikdörtgenleri normalleştirin `NormalizeRect` .

`CRect` [Cdc::D PtoLP](../../mfc/reference/cdc-class.md#dptolp) ve [CDC:: LPtoDP](../../mfc/reference/cdc-class.md#lptodp) üye işlevleriyle işleme yaparken dikkatli olun. Bir görüntüleme bağlamının eşleme modu, içinde olduğu gibi y uzantısı negatif ise, `MM_LOENGLISH` `CDC::DPtoLP` `CRect` en üst öğenin alt kısmından daha büyük olması için öğesini dönüştürür. Ve gibi işlevler `Height` `Size` , dönüştürülen yükseklik için negatif değerler döndürür `CRect` ve dikdörtgen Normalleştirilmemiş olur.

Aşırı yüklenmiş `CRect` işleçler kullanılırken, ilk işlenen bir olmalıdır `CRect` ; ikincisi Ise bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı ya da bir nesne olabilir `CRect` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagRECT`

`CRect`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltypes. h

## <a name="crectbottomright"></a><a name="bottomright"></a> CRect:: BottomRight

Koordinatlar, içinde bulunan bir [CPoint](cpoint-class.md) nesnesine başvuru olarak döndürülür `CRect` .

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin sağ alt köşesinin koordinatları.

### <a name="remarks"></a>Açıklamalar

Dikdörtgenin sağ alt köşesini almak veya ayarlamak için bu işlevi kullanabilirsiniz. Atama işlecinin sol tarafında bu işlevi kullanarak köşeyi ayarlayın.

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

## <a name="crectcenterpoint"></a><a name="centerpoint"></a> CRect:: CenterPoint

`CRect`Sol ve sağ değerleri ekleyerek ve iki ile bölerek ve en üst ve alt değerleri ekleyerek ve iki olarak bölerek Centerpoint 'i hesaplar.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CPoint`Merkez noktası olan bir nesne `CRect` .

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

## <a name="crectcopyrect"></a><a name="copyrect"></a> CRect:: CopyRect

`lpSrcRect`Dikdörtgeni içine kopyalar `CRect` .

```cpp
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>Parametreler

*lpSrcRect*<br/>
Kopyalanacak [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya nesnesine işaret eder `CRect` .

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

## <a name="crectcrect"></a><a name="crect"></a> CRect:: CRect

Bir `CRect` nesnesi oluşturur.

```
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();
```

### <a name="parameters"></a>Parametreler

*girişindeki*<br/>
Öğesinin sol konumunu belirtir `CRect` .

*şı*<br/>
Öğesinin üst öğesini belirtir `CRect` .

*sağ*<br/>
Öğesinin doğru konumunu belirtir `CRect` .

*kenarı*<br/>
Öğesinin alt öğesini belirtir `CRect` .

*srcRect*<br/>
İçin koordinatları olan [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvurur `CRect` .

*lpSrcRect*<br/>
`RECT`Koordinatlarıyla yapısına işaret eder `CRect` .

*seçeneğinin*<br/>
Oluşturulacak dikdörtgenin kaynak noktasını belirtir. Sol üst köşeye karşılık gelir.

*boyutla*<br/>
Oluşturulacak dikdörtgenin sağ alt köşesine kadar sol üst köşeden yer değiştirme sayısını belirtir.

*topLeft*<br/>
Öğesinin üst sol konumunu belirtir `CRect` .

*bottomRight*<br/>
Öğesinin sağ alt konumunu belirtir `CRect` .

### <a name="remarks"></a>Açıklamalar

Hiçbir bağımsız değişken verilmezse,, `left` , `top` `right` ve `bottom` üyeleri 0 olarak ayarlanır.

`CRect`( `const RECT&` ) Ve `CRect` ( `LPCRECT` ) oluşturucuları bir [CopyRect](#copyrect)gerçekleştirir. Diğer oluşturucular nesnenin üye değişkenlerini doğrudan başlatır.

### <a name="example"></a>Örnek

```cpp
// default constructor is equivalent to CRect(0, 0, 0, 0)
CRect emptyRect;

// four-integers are left, top, right, and bottom
CRect rect(0, 0, 100, 50);
ASSERT(rect.Width() == 100);
ASSERT(rect.Height() == 50);

// Initialize from RECT structure
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

## <a name="crectdeflaterect"></a><a name="deflaterect"></a> CRect::D eflateRect

`DeflateRect``CRect`yüzlerini merkezine doğru taşıyarak erteleyerek.

```cpp
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sol ve sağ taraflarını söndür birim sayısını belirtir `CRect` .

*Iz*<br/>
Üst ve alt kısmını söndür birim sayısını belirtir `CRect` .

*boyutla*<br/>
Söndür birim sayısını belirten bir [Boyut](/windows/win32/api/windef/ns-windef-size) veya [CSize](csize-class.md) `CRect` . `cx`Değer, sol ve sağ taraflarını söndür birim sayısını belirtir ve `cy` değer, üst ve alt değerlerini söndür birim sayısını belirtir.

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına işaret eder veya `CRect` her bir yüzü söndür birim sayısını belirtir.

*girişindeki*<br/>
Sol tarafının söndür birim sayısını belirtir `CRect` .

*şı*<br/>
En üstünü söndür birim sayısını belirtir `CRect` .

*sağ*<br/>
Sağ tarafının söndür olacak birim sayısını belirtir `CRect` .

*kenarı*<br/>
Alt öğesinin altı olarak söndür birim sayısını belirtir `CRect` .

### <a name="remarks"></a>Açıklamalar

Bunu yapmak için, `DeflateRect` sol ve üst kısımdaki birimleri ekler ve birimleri sağ ve alttan çıkartır. Parametresi `DeflateRect` işaretli değerlerdir; pozitif değerler söndür `CRect` ve negatif değerler onu şişir.

İlk iki aşırı yükleme, `CRect` toplam genişliğinin iki kez *x* (veya) ile azaltılana `cx` ve toplam yüksekliğinin iki kez *y* (veya) ile azaltılmasını sağlamak için her iki karşıt çift çiftini söndür `cy` . Diğer iki aşırı yükleme diğerlerinden bağımsız olarak her bir kenarı ikiye söndür `CRect` .

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

## <a name="crectequalrect"></a><a name="equalrect"></a> CRect:: EqualRect

`CRect`Verilen dikdörtgene eşit olup olmadığını belirler.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) `CRect` Bir dikdörtgenin sol üst ve sağ alt köşe koordinatlarını içeren bir Rect yapısına veya nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İki dikdörtgende aynı üst, sol, alt ve sağ değerler varsa sıfır dışında; Aksi takdirde 0.

> [!NOTE]
> Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

## <a name="crectheight"></a><a name="height"></a> CRect:: Height

`CRect`Alt değerden en üstteki değeri çıkararak yüksekliğini hesaplar.

```
int Height() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yüksekliği `CRect` .

### <a name="remarks"></a>Açıklamalar

Elde edilen değer negatif olabilir.

> [!NOTE]
> Dikdörtgen normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

## <a name="crectinflaterect"></a><a name="inflaterect"></a> CRect:: InflateRect

`InflateRect``CRect`yüzlerini merkezinden uzağa taşıyarak flatları.

```cpp
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sol ve sağ taraflarından şişiteedilecek birim sayısını belirtir `CRect` .

*Iz*<br/>
Üst ve alt kısmını şişiteden birim sayısını belirtir `CRect` .

*boyutla*<br/>
Şişeedilecek birim sayısını belirten bir [Boyut](/windows/win32/api/windef/ns-windef-size) veya [CSize](csize-class.md) `CRect` . `cx`Değer, sol ve sağ taraflardan şişen birim sayısını belirtir ve `cy` değer, üst ve alt değerlerini şişiteedilecek birim sayısını belirtir.

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına işaret eder veya `CRect` her bir kenar için kullanılacak birim sayısını belirtir.

*girişindeki*<br/>
Sol tarafının hangi birim sayısını ayırt etmek için belirtir `CRect` .

*şı*<br/>
Üst öğesinin üzerine inili edilecek birim sayısını belirtir `CRect` .

*sağ*<br/>
Sağ tarafının hangi birim sayısını ayırt etmek için belirtir `CRect` .

*kenarı*<br/>
Alt öğesinin altına inili edilecek birim sayısını belirtir `CRect` .

### <a name="remarks"></a>Açıklamalar

Bunu yapmak için, `InflateRect` sol ve üst kısımdaki birimleri çıkartır ve sağ ve alttaki birimleri ekler. Parametresi `InflateRect` işaretli değerlerdir; pozitif değerler ters Şişir `CRect` ve negatif değerler bu değeri söndür.

İlk iki aşırı yükleme, `CRect` toplam genişliğinin iki kez *x* (veya) ile artması `cx` ve toplam yüksekliğinin iki kez *y* (veya) ile artması için her iki çift tarafının de her ikisini de şişir `cy` . Diğer iki aşırı yükleme diğerlerinden bağımsız olarak her bir tarafı Şişir `CRect` .

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

## <a name="crectintersectrect"></a><a name="intersectrect"></a> CRect:: IntersectRect

`CRect`Varolan iki dikdörtgenin kesişimine eşit hale getirir.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRect1*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` kaynak dikdörtgeni içeren nesnesine işaret eder.

*lpRect2*<br/>
`RECT`Kaynak dikdörtgeni içeren bir yapıya veya nesneye işaret eder `CRect` .

### <a name="return-value"></a>Dönüş Değeri

Kesişim boş değilse sıfır dışı; kesişme boşsa 0.

### <a name="remarks"></a>Açıklamalar

Kesişim, hem varolan dikdörtgenlerde bulunan en büyük dikdörtgendir.

> [!NOTE]
> Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

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

## <a name="crectisrectempty"></a><a name="isrectempty"></a> CRect:: IsRectEmpty

Boş olup olmadığını belirler `CRect` .

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Boşsa sıfır sıfır `CRect` ; `CRect` boş değilse 0.

### <a name="remarks"></a>Açıklamalar

Genişlik ve/veya Yükseklik 0 veya negatif ise, bir dikdörtgen boştur. `IsRectNull`Dikdörtgenin tüm koordinatlarının sıfır olup olmadığını belirleyen öğesinden farklıdır.

> [!NOTE]
> Dikdörtgen normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
ASSERT(rectEmpty.IsRectEmpty());
```

## <a name="crectisrectnull"></a><a name="isrectnull"></a> CRect:: IsRectNull

Üst, sol, alt ve sağ değerlerinin `CRect` tümünün 0 ' a eşit olup olmadığını belirler.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`En üst, sol, alt ve sağ değerlerinin hepsi 0 ' a eşit; Aksi takdirde 0 ' dır.

### <a name="remarks"></a>Açıklamalar

`IsRectEmpty`Dikdörtgenin boş olup olmadığını belirleyen öğesinden farklıdır.

### <a name="example"></a>Örnek

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
ASSERT(!rectSome.IsRectNull());
// note that null means _all_ zeros

CRect rectNotNull(0, 0, 35, 50);
ASSERT(!rectNotNull.IsRectNull());
```

## <a name="crectmovetox"></a><a name="movetox"></a> CRect:: MoveToX

Dikdörtgeni *x*tarafından belirtilen mutlak x koordinatına taşımak için bu işlevi çağırın.

```cpp
void MoveToX(int x) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Dikdörtgenin sol üst köşesinin mutlak x koordinatı.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

// rect is now (10, 0, 110, 100);
ASSERT(rect == CRect(10, 0, 110, 100));
```

## <a name="crectmovetoxy"></a><a name="movetoxy"></a> CRect:: MoveToXY

Dikdörtgeni belirtilen mutlak x ve y koordinatlarına taşımak için bu işlevi çağırın.

```cpp
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Dikdörtgenin sol üst köşesinin mutlak x koordinatı.

*Iz*<br/>
Dikdörtgenin sol üst köşesinin mutlak y koordinatı.

*seçeneğinin*<br/>
`POINT`Dikdörtgenin mutlak sol üst köşesini belirten bir yapı.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
ASSERT(rect == CRect(10, 10, 110, 110));
```

## <a name="crectmovetoy"></a><a name="movetoy"></a> CRect:: Moveoyunu

Dikdörtgeni *y*tarafından belirtilen mutlak y koordinatına taşımak için bu işlevi çağırın.

```cpp
void MoveToY(int y) throw();
```

### <a name="parameters"></a>Parametreler

*Iz*<br/>
Dikdörtgenin sol üst köşesinin mutlak y koordinatı.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
ASSERT(rect == CRect(0, 10, 100, 110));
```

## <a name="crectnormalizerect"></a><a name="normalizerect"></a> CRect:: NormalizeRect

`CRect`Her iki yükseklik ve genişlik de pozitif olacak şekilde normalleştirir.

```cpp
void NormalizeRect() throw();
```

### <a name="remarks"></a>Açıklamalar

Dikdörtgen, Windows 'un koordinatları için genellikle kullandığı dördüncü Çeyrekli konumlandırma için normalleştirilir. `NormalizeRect` üst ve alt değerleri karşılaştırır ve en alttan daha büyükse onları değiştirir. Benzer şekilde, sol ve sağ değerleri Solsa, sol ve sağ değerlerini değiştirir. Bu işlev, farklı eşleme modlarıyla ve ters dikdörtgenlerle ilgilenirken yararlıdır.

> [!NOTE]
> Aşağıdaki `CRect` üye işlevleri düzgün çalışması için Normalleştirilmemiş dikdörtgenler gerektirir: [Height](#height), [Width](#width), [size](#size), [IsRectEmpty](#isrectempty), [ptinrect](#ptinrect), [equalrect](#equalrect), [unionrect](#unionrect), [IntersectRect](#intersectrect), [subtractrect](#subtractrect), [işleç = =](#operator_eq_eq), [operator! =](#operator_neq), [işleç &#124;](#operator_or), [işleç &#124;=](#operator_or_eq), [işleç &](#operator_amp)ve [işleç &=](#operator_amp_eq).

### <a name="example"></a>Örnek

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

## <a name="crectoffsetrect"></a><a name="offsetrect"></a> CRect:: OffsetRect

`CRect`Belirtilen uzaklıklara göre gider.

```cpp
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sol veya sağ taşınacak miktarı belirtir. Sola ilerlemek için negatif olmalıdır.

*Iz*<br/>
Yukarı veya aşağı taşınacak miktarı belirtir. Yukarı taşımak için negatif olmalıdır.

*seçeneğinin*<br/>
Her iki boyutu da taşımak için belirten bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi içerir.

*boyutla*<br/>
Her iki [boyutu](/windows/win32/api/windef/ns-windef-size) da taşımak için belirten bir boyut yapısı veya [CSize](csize-class.md) nesnesi içerir.

### <a name="remarks"></a>Açıklamalar

X `CRect` *x* birimini x ekseni ve *y* birimleri üzerinde y ekseni üzerinde kaydırır. *X* ve *y* parametreleri imzalı değerlerdir, bu nedenle `CRect` sol veya sağ ve yukarı veya aşağı taşınabilir.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

## <a name="crectoperator-lpcrect-converts-a-crect-to-an-lpcrect"></a><a name="operator_lpcrect"></a> CRect:: operator LPCRECT, bir `CRect` [lpcrect](../../mfc/reference/data-types-mfc.md)öğesine dönüştürür.

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullandığınızda, Address-of ( **&** ) işlecine gerek kalmaz. Bu işleç, bir nesnesini bekleyen bir işleve geçirdiğinizde otomatik olarak kullanılacaktır `CRect` `LPCRECT` .

## <a name="crectoperator-lprect"></a><a name="operator_lprect"></a> CRect:: operator LPRECT

Bir `CRect` [lpRect](../../mfc/reference/data-types-mfc.md)öğesine dönüştürür.

```
operator LPRECT() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullandığınızda, Address-of ( **&** ) işlecine gerek kalmaz. Bu işleç, bir nesnesini bekleyen bir işleve geçirdiğinizde otomatik olarak kullanılacaktır `CRect` `LPRECT` .

### <a name="example"></a>Örnek

[CRect:: operator lpcrect](#operator_lpcrect)örneğine bakın.

## <a name="crectoperator-"></a><a name="operator_eq"></a> CRect:: operator =

' A *srcRect* atar `CRect` .

```cpp
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>Parametreler

*srcRect*<br/>
Bir kaynak dikdörtgeni ifade eder. Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya olabilir `CRect` .

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 127, 168);
CRect rect2;

rect2 = rect;
ASSERT(rect2 == CRect(0, 0, 127, 168));
```

## <a name="crectoperator-"></a><a name="operator_eq_eq"></a> CRect:: operator = =

`rect` `CRect` Sol üst ve sağ alt köşelerin koordinatlarını karşılaştırarak eşit olup olmadığını belirler.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Bir kaynak dikdörtgeni ifade eder. Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya olabilir `CRect` .

### <a name="return-value"></a>Dönüş Değeri

Eşitse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

## <a name="crectoperator-"></a><a name="operator_neq"></a> CRect:: operator! =

*rect* `CRect` Sol üst ve sağ alt köşelerin koordinatları karşılaştırılırken Rect 'in eşit olup olmadığını belirler.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Bir kaynak dikdörtgeni ifade eder. Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya olabilir `CRect` .

### <a name="return-value"></a>Dönüş Değeri

Eşit değilse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

## <a name="crectoperator-"></a><a name="operator_add_eq"></a> CRect:: operator + =

İlk iki aşırı yükleme `CRect` belirtilen uzaklıkları taşır.

```cpp
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Dikdörtgenin taşınacağı birim sayısını belirten bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi.

*boyutla*<br/>
Dikdörtgenin taşınacağı birim sayısını belirten bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](csize-class.md) nesnesi.

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya ' `CRect` nin her tarafında şişiteden birim sayısını içeren nesneye işaret eder `CRect` .

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy` ) değerleri öğesine eklenir `CRect` .

Üçüncü aşırı yükleme, `CRect` parametrenin her üyesinde belirtilen birim sayısına göre geçersiz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-_eq"></a> CRect:: operator-=

İlk iki aşırı yükleme `CRect` belirtilen uzaklıkları taşır.

```cpp
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Dikdörtgenin taşınacağı birim sayısını belirten bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi.

*boyutla*<br/>
Dikdörtgenin taşınacağı birim sayısını belirten bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](csize-class.md) nesnesi.

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya her bir `CRect` tarafını söndür birim sayısını içeren nesnesine işaret eder `CRect` .

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (ya `cx` da `cy` ) değerleri çıkarılır `CRect` .

Üçüncü aşırı yükleme, `CRect` parametrenin her üyesinde belirtilen birim sayısına göre ertetir. Bu aşırı yükleme ' nin [erteleme](#deflaterect)gibi işlevleri olduğunu unutmayın.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp_eq"></a> CRect:: işleci &amp;=

`CRect`Ve kesişimine eşit ayarlar `CRect` `rect` .

```cpp
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya içerir `CRect` .

### <a name="remarks"></a>Açıklamalar

Kesişim, her iki dikdörtgende bulunan en büyük dikdörtgendir.

> [!NOTE]
> Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

[CRect:: IntersectRect](#intersectrect)örneğine bakın.

## <a name="crectoperator-124"></a><a name="operator_or_eq"></a> CRect:: operator &#124;=

, `CRect` Ve birleşimini eşit olarak ayarlar `CRect` `rect` .

```cpp
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
`CRect`Or [Rect](/windows/win32/api/windef/ns-windef-rect)içerir.

### <a name="remarks"></a>Açıklamalar

Birleşim, her iki kaynak dikdörtgeni içeren en küçük dikdörtgendir.

> [!NOTE]
> Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);

rect1 |= rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect1);
```

## <a name="crectoperator-"></a><a name="operator_add"></a> CRect:: operator +

İlk iki aşırı yükleme, `CRect` belirtilen uzaklıklarıyla aynı değere eşit bir nesne döndürüyor `CRect` .

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Dönüş değerini taşıyacağınız birim sayısını belirten bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi.

*boyutla*<br/>
Dönüş değerini taşıyacağınız birim sayısını belirten bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](csize-class.md) nesnesi.

*lpRect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) `CRect` Dönüş değerinin her tarafını almak için birim sayısını içeren bir Rect yapısına veya nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Bu, `CRect` `CRect` parametresinde belirtilen birim sayısına göre hareket ettirmeden ya da flaktan elde edilir.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy` ) parametreleri `CRect` konumuna eklenir.

Üçüncü aşırı yükleme, `CRect` `CRect` parametrenin her üyesinde belirtilen birim sayısına eşit olan yeni bir döndürür.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 + pt;
CRect   rectResult(135, 300, 235, 400);
ASSERT(rectResult == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-"></a> CRect:: operator-

İlk iki aşırı yükleme, `CRect` belirtilen uzaklıklarıyla aynı değere eşit bir nesne döndürüyor `CRect` .

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) `CPoint` Dönüş değerini taşıyacağınız birim sayısını belirten bir nokta yapısı veya nesnesi.

*boyutla*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size) `CSize` Dönüş değerini taşıyacağınız birim sayısını belirten bir boyut yapısı veya nesnesi.

*lpRect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) `CRect` Dönüş değerinin her tarafını söndür olan birim sayısını içeren bir Rect yapısına veya nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

, `CRect` `CRect` Parametresinde belirtilen birim sayısına göre hareket ettirmeden veya erteleyerek elde edilir.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy` ) parametreleri `CRect` konumdan çıkarılır.

Üçüncü aşırı yükleme, `CRect` `CRect` parametrenin her üyesinde belirtilen birim sayısına eşit olan yeni bir döndürür. Bu aşırı yükleme, [SubtractRect](#subtractrect)değil, [savunma](#deflaterect)gibi işlevlerin olduğunu unutmayın.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp"></a> CRect:: işleci &amp;

`CRect`Ve rect2 kesişimi olan bir döndürür `CRect` . *rect2*

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>Parametreler

*rect2*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya içerir `CRect` .

### <a name="return-value"></a>Dönüş Değeri

`CRect` `CRect` Ve *rect2*'in kesişimi.

### <a name="remarks"></a>Açıklamalar

Kesişim, her iki dikdörtgende bulunan en büyük dikdörtgendir.

> [!NOTE]
> Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 & rect2;
CRect   rectResult(100, 100, 200, 200);
ASSERT(rectResult == rect3);
```

## <a name="crectoperator-124"></a><a name="operator_or"></a> CRect:: operator &#124;

`CRect`Ve rect2 birleşimi olan bir döndürür `CRect` . *rect2*

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>Parametreler

*rect2*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya içerir `CRect` .

### <a name="return-value"></a>Dönüş Değeri

`CRect` `CRect` Ve *rect2*birleşimi.

### <a name="remarks"></a>Açıklamalar

Birleşim, her iki dikdörtgeni de içeren en küçük dikdörtgendir.

> [!NOTE]
> Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 | rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectptinrect"></a><a name="ptinrect"></a> CRect::P tInRect

Belirtilen noktanın içinde olup olmadığını belirler `CRect` .

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi içerir.

### <a name="return-value"></a>Dönüş Değeri

Nokta içinde yer alıyorsa sıfır dışında `CRect` ; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nokta, `CRect` sol veya üst tarafa Dayıya da dört tarafın içinde yer alıyorsa. Sağ veya alt taraftaki bir nokta dışarıda `CRect` .

> [!NOTE]
> Dikdörtgen normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

## <a name="crectsetrect"></a><a name="setrect"></a> CRect:: SetRect

Boyutlarını `CRect` belirtilen koordinatlara ayarlar.

```cpp
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Sol üst köşenin x koordinatını belirtir.

*Y1*<br/>
Sol üst köşenin y koordinatını belirtir.

*x2*<br/>
Sağ alt köşenin x koordinatını belirtir.

*Y2*<br/>
Sağ alt köşenin y koordinatını belirtir.

### <a name="example"></a>Örnek

```cpp
CRect rect;
rect.SetRect(256, 256, 512, 512);
ASSERT(rect == CRect(256, 256, 512, 512));
```

## <a name="crectsetrectempty"></a><a name="setrectempty"></a> CRect:: SetRectEmpty

`CRect`Tüm koordinatları sıfıra ayarlayarak boş bir dikdörtgen yapar.

```cpp
void SetRectEmpty() throw();
```

### <a name="example"></a>Örnek

```cpp
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());
```

## <a name="crectsize"></a><a name="size"></a> CRect:: SIZE

`cx` `cy` Dönüş değerinin ve üyeleri, yüksekliğini ve genişliğini içerir `CRect` .

```
CSize Size() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Boyutunu içeren [CSize](csize-class.md) nesnesi `CRect` .

### <a name="remarks"></a>Açıklamalar

Yükseklik ya da Genişlik negatif olabilir.

> [!NOTE]
> Dikdörtgen normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

## <a name="crectsubtractrect"></a><a name="subtractrect"></a> CRect:: SubtractRect

Değerine eşit olan boyut boyutunu ' `CRect` dan çıkarma için yapar `lpRectSrc2` `lpRectSrc1` .

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRectSrc1*<br/>
[Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` dikdörtgenin çıkarılacak nesnesine işaret eder.

*lpRectSrc2*<br/>
`RECT` `CRect` *LpRectSrc1* parametresi tarafından işaret edilen dikdörtgenden çıkarılacak yapıya veya nesneye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çıkarma, *lpRectScr1* içinde *lpRectScr1* ve *lpRectScr2*kesişimine olmayan tüm noktaları içeren en küçük dikdörtgendir.

*LpRectSrc2* tarafından belirtilen dikdörtgen, x veya y yönlerinin en az birinde *lpRectSrc1* tarafından belirtilen dikdörtgenden tamamen çakışmazsa, *lpRectSrc1* tarafından belirtilen dikdörtgen değiştirilmez.

Örneğin, *lpRectSrc1* (10, 10, 100.100) ve *lpRectSrc2* (50, 50, 150.150) Ise, işlev döndürüldüğünde *lpRectSrc1* tarafından işaret edilen dikdörtgen değiştirilmez. *LpRectSrc1* (10, 10, 100.100) ve *lpRectSrc2* ise (50, 10, 150.150), ancak *lpRectSrc1* tarafından işaret edilen dikdörtgen, işlev döndürüldüğünde (10, 10, 50.100) koordinatları içerir.

`SubtractRect`[işleç](#operator_-) -veya [operator-=](#operator_-_eq)ile aynı değildir. Bu işleçlerden hiçbiri asla çağrı gerçekleştirmez `SubtractRect` .

> [!NOTE]
> Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

## <a name="crecttopleft"></a><a name="topleft"></a> CRect:: TopLeft

Koordinatlar, içinde bulunan bir [CPoint](cpoint-class.md) nesnesine başvuru olarak döndürülür `CRect` .

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin sol üst köşesinin koordinatları.

### <a name="remarks"></a>Açıklamalar

Dikdörtgenin sol üst köşesini almak veya ayarlamak için bu işlevi kullanabilirsiniz. Atama işlecinin sol tarafında bu işlevi kullanarak köşeyi ayarlayın.

### <a name="example"></a>Örnek

[CRect:: CenterPoint](#centerpoint)örneğine bakın.

## <a name="crectunionrect"></a><a name="unionrect"></a> CRect:: UnionRect

`CRect`İki kaynak dikdörtgenin birleşimini eşit hale getirir.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRect1*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) 'e işaret eder veya `CRect` bir kaynak dikdörtgen içerir.

*lpRect2*<br/>
`RECT`Kaynak dikdörtgeni içeren bir veya ' a işaret eder `CRect` .

### <a name="return-value"></a>Dönüş Değeri

Birleşim boş değilse sıfır dışı; UNION boşsa 0.

### <a name="remarks"></a>Açıklamalar

Birleşim, her iki kaynak dikdörtgeni içeren en küçük dikdörtgendir.

Windows boş bir dikdörtgenin boyutlarını yoksayar; Yani, yüksekliği olmayan veya genişliği olmayan bir dikdörtgen.

> [!NOTE]
> Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3.UnionRect(&rect1, &rect2);
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectwidth"></a><a name="width"></a> CRect:: Width

`CRect`Sol değeri sağ değerden çıkararak genişliğini hesaplar.

```
int Width() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Genişliği `CRect` .

### <a name="remarks"></a>Açıklamalar

Genişlik negatif olabilir.

> [!NOTE]
> Dikdörtgen normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
// nWid is now 60
ASSERT(nWid == 60);
```

## <a name="see-also"></a>Ayrıca bkz.

[CPoint sınıfı](cpoint-class.md)<br/>
[CSize sınıfı](csize-class.md)<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)
