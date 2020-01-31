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
ms.openlocfilehash: 13f86c411cca98f5817d1b3b2d9162ae8af8b734
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821375"
---
# <a name="crect-class"></a>CRect sınıfı

Bir Windows [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına benzer.

## <a name="syntax"></a>Sözdizimi

```
class CRect : public tagRECT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CRect:: CRect](#crect)|`CRect` nesnesi oluşturur.|

### <a name="public-methods"></a>Genel Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CRect:: BottomRight](#bottomright)|`CRect`sağ alt noktasını döndürür.|
|[CRect:: CenterPoint](#centerpoint)|`CRect`merkez noktasını döndürür.|
|[CRect:: CopyRect](#copyrect)|Kaynak dikdörtgenin boyutlarını `CRect`olarak kopyalar.|
|[CRect::D eflateRect](#deflaterect)|`CRect`genişliğini ve yüksekliğini azaltır.|
|[CRect:: EqualRect](#equalrect)|`CRect` verilen dikdörtgene eşit olup olmadığını belirler.|
|[CRect:: Height](#height)|`CRect`yüksekliğini hesaplar.|
|[CRect:: InflateRect](#inflaterect)|`CRect`genişliğini ve yüksekliğini artırır.|
|[CRect:: IntersectRect](#intersectrect)|İki dikdörtgenin kesişimine eşit `CRect` ayarlar.|
|[CRect:: IsRectEmpty](#isrectempty)|`CRect` boş olup olmadığını belirler. Genişlik ve/veya Yükseklik 0 ise `CRect` boştur.|
|[CRect:: IsRectNull](#isrectnull)|`top`, `bottom`, `left`ve `right` üye değişkenlerinin tümünün 0 ' a eşit olup olmadığını belirler.|
|[CRect:: MoveToX](#movetox)|`CRect` belirtilen x koordinatına kaydırır.|
|[CRect:: MoveToXY](#movetoxy)|`CRect` belirtilen x ve y koordinatlarına gider.|
|[CRect:: Moveoyunu](#movetoy)|`CRect` belirtilen y koordinatıyla kaydırır.|
|[CRect:: NormalizeRect](#normalizerect)|`CRect`yüksekliğini ve genişliğini standartlaştırır.|
|[CRect:: OffsetRect](#offsetrect)|`CRect` belirtilen uzaklıklara göre gider.|
|[CRect::P tInRect](#ptinrect)|Belirtilen noktanın `CRect`içinde olup olmadığını belirler.|
|[CRect:: SetRect](#setrect)|`CRect`boyutunu ayarlar.|
|[CRect:: SetRectEmpty](#setrectempty)|`CRect` boş bir dikdörtgene (tüm koordinatlar 0 ' a eşit) ayarlar.|
|[CRect:: size](#size)|`CRect`boyutunu hesaplar.|
|[CRect:: SubtractRect](#subtractrect)|Bir dikdörtgeni diğerinden çıkarır.|
|[CRect:: TopLeft](#topleft)|`CRect`sol üst noktasını döndürür.|
|[CRect:: UnionRect](#unionrect)|İki dikdörtgenin birleşime eşit `CRect` ayarlar.|
|[CRect:: Width](#width)|`CRect`genişliğini hesaplar.|

### <a name="public-operators"></a>Genel İşleçler

|Name|Açıklama|
|----------|-----------------|
|[CRect:: operator-](#operator_-)|Verilen uzaklıkları `CRect` çıkartır veya `CRect` erteler ve elde edilen `CRect`döndürür.|
|[CRect:: operator LPCRECT](#operator_lpcrect)|Bir `CRect` `LPCRECT`dönüştürür.|
|[CRect:: operator LPRECT](#operator_lprect)|Bir `CRect` `LPRECT`dönüştürür.|
|[CRect:: operator! =](#operator_neq)|`CRect` bir dikdörtgene eşit olup olmadığını belirler.|
|[CRect:: operator &amp;](#operator_amp)|`CRect` ve dikdörtgenin kesişimini oluşturur ve elde edilen `CRect`döndürür.|
|[CRect:: operator &amp;=](#operator_amp_eq)|`CRect` ve bir dikdörtgenin kesişimine eşit `CRect` ayarlar.|
|[CRect:: işleci&#124;](#operator_or)|`CRect` ve dikdörtgen birleşimini oluşturur ve elde edilen `CRect`döndürür.|
|[CRect:: operator &#124;=](#operator_or_eq)|`CRect` `CRect` ve bir dikdörtgenin birleşimini eşit olarak ayarlar.|
|[CRect:: operator +](#operator_add)|Verilen uzaklıkları `CRect` veya düzet `CRect` ekler ve elde edilen `CRect`döndürür.|
|[CRect:: operator + =](#operator_add_eq)|`CRect` veya düzet `CRect`için belirtilen uzaklıkları ekler.|
|[CRect:: operator =](#operator_eq)|Bir dikdörtgenin boyutlarını `CRect`olarak kopyalar.|
|[CRect:: operator-=](#operator_-_eq)|`CRect` belirtilen uzaklıkları çıkartır veya `CRect`ertetir.|
|[CRect:: operator = =](#operator_eq_eq)|`CRect` dikdörtgene eşit olup olmadığını belirler.|

## <a name="remarks"></a>Açıklamalar

`CRect` Ayrıca, `CRect` nesneleri ve Windows `RECT` yapılarını işlemek için üye işlevleri de içerir.

Bir `CRect` nesnesi, bir `RECT` yapısının, `LPCRECT`veya `LPRECT` geçirildiği her yerde işlev parametresi olarak geçirilebilir.

> [!NOTE]
> Bu sınıf `tagRECT` yapısından türetilir. (Ad `tagRECT` `RECT` yapısına yönelik daha yaygın olarak kullanılan bir addır.) Bu, `RECT` yapısının veri üyelerine (`left`, `top`, `right`ve `bottom`), `CRect`'nin erişilebilir veri üyelerine sahip olduğu anlamına gelir.

Bir `CRect` dikdörtgenin sol üst ve sağ alt noktalarını tanımlayan üye değişkenlerini içerir.

Bir `CRect`belirtirken, diğer bir deyişle, sol koordinat değerinin doğru ve en alttan küçük olması gibi, onu normalleştirilmeden oluşturmak için dikkatli olmanız gerekir. Örneğin, (10, 10) ve sağ alt (20, 20) sol üst bir, normalleştirilmiş bir dikdörtgen tanımlar, ancak (20, 20) ve sağ alt (10, 10) sol üst bir, Normalleştirilmemiş bir dikdörtgen tanımlar. Dikdörtgen normalleştirilmez değilse pek çok `CRect` üye işlevi hatalı sonuçlar döndürebilir. (Bu işlevlerin listesi için bkz. [CRect:: NormalizeRect](#normalizerect) .) Normalleştirilmiş dikdörtgenler gerektiren bir işlevi çağırmadan önce, `NormalizeRect` işlevini çağırarak normalleştirilmiş olmayan dikdörtgenleri normalleştirin.

[CDC::D PtoLP](../../mfc/reference/cdc-class.md#dptolp) ve [CDC:: LPtoDP](../../mfc/reference/cdc-class.md#lptodp) üye işlevleri ile bir `CRect` düzenleme yaparken dikkatli olun. Bir görüntüleme bağlamının eşleme modu, `MM_LOENGLISH`olduğu gibi y uzantısı negatif olduğunda, `CDC::DPtoLP`, `CRect` üst öğesinden daha büyük olacak şekilde dönüştürür. `Height` ve `Size` gibi işlevler, dönüştürülen `CRect`yüksekliği için negatif değerler döndürür ve dikdörtgen Normalleştirilmemiş olur.

Aşırı yüklenmiş `CRect` işleçleri kullanılırken, ilk işlenen bir `CRect`olmalıdır; İkincisi, bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı ya da bir `CRect` nesnesi olabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagRECT`

`CRect`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltypes. h

##  <a name="bottomright"></a>CRect:: BottomRight

Koordinatlar, `CRect`bulunan bir [CPoint](cpoint-class.md) nesnesine başvuru olarak döndürülür.

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

##  <a name="centerpoint"></a>CRect:: CenterPoint

Sol ve sağ değerleri ekleyerek ve ikiye ayırarak ve en üst ve alt değerleri ekleyerek ve iki olarak bölerek `CRect` Centerpoint noktasını hesaplar.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`merkez noktası olan `CPoint` nesne.

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

##  <a name="copyrect"></a>CRect:: CopyRect

`lpSrcRect` dikdörtgeni `CRect`içine kopyalar.

```
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>Parametreler

*lpSrcRect*<br/>
Görüntülenecek [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` nesnesine işaret eder.

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

##  <a name="crect"></a>CRect:: CRect

`CRect` nesnesi oluşturur.

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
`CRect`sol konumunu belirtir.

*şı*<br/>
`CRect`en üstünü belirtir.

*r*<br/>
`CRect`doğru konumunu belirtir.

*b*<br/>
`CRect`en altını belirtir.

*srcRect*<br/>
`CRect`koordinatlarıyla birlikte [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvurur.

*lpSrcRect*<br/>
`CRect`koordinatlarıyla `RECT` yapısına işaret eder.

*seçeneğinin*<br/>
Oluşturulacak dikdörtgenin kaynak noktasını belirtir. Sol üst köşeye karşılık gelir.

*boyutla*<br/>
Oluşturulacak dikdörtgenin sağ alt köşesine kadar sol üst köşeden yer değiştirme sayısını belirtir.

*Topsol*<br/>
`CRect`üst sol konumunu belirtir.

*bottomRight*<br/>
`CRect`sağ alt konumunu belirtir.

### <a name="remarks"></a>Açıklamalar

Hiçbir bağımsız değişken verilmezse, `left`, `top`, `right`ve `bottom` üyeleri başlatılmaz.

`CRect`(`const RECT&`) ve `CRect`(`LPCRECT`) oluşturucuları bir [CopyRect](#copyrect)gerçekleştirir. Diğer oluşturucular nesnenin üye değişkenlerini doğrudan başlatır.

### <a name="example"></a>Örnek

```cpp
// default constructor doesn't initialize!
CRect rectUnknown;

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

##  <a name="deflaterect"></a>CRect::D eflateRect

`DeflateRect`, yüzlerini merkezine doğru taşıyarak `CRect` erteleyerek.

```
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
`CRect`sol ve sağ taraflarını söndür birim sayısını belirtir.

*Iz*<br/>
`CRect`üst ve alt kısmını söndür birim sayısını belirtir.

*boyutla*<br/>
`CRect`söndür birim sayısını belirten bir [Boyut](/windows/win32/api/windef/ns-windef-size) veya [CSize](csize-class.md) . `cx` değeri, sol ve sağ taraflarını söndür birim sayısını belirtir ve `cy` değeri, üst ve alt değerlerini söndür birim sayısını belirtir.

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına işaret eder veya her bir yüzü söndür birim sayısını belirten `CRect`.

*girişindeki*<br/>
`CRect`sol tarafını söndür birim sayısını belirtir.

*şı*<br/>
`CRect`en üstünü söndür olan birim sayısını belirtir.

*r*<br/>
`CRect`sağ tarafını söndür birim sayısını belirtir.

*b*<br/>
`CRect`en altından söndür olan birim sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Bunu yapmak için `DeflateRect` sol ve üst kısımdaki birimleri ekler ve birimleri sağ ve alttan çıkartır. `DeflateRect` parametreler imzalı değerlerdir; pozitif değerler söndür `CRect` ve negatif değerler onu şişir.

İlk iki aşırı yükleme, toplam genişliğinin iki kez *x* (veya `cx`) azaltılana ve toplam yüksekliğinin iki kata *y* (veya `cy`) azaltılana kadar her iki çift yönlü `CRect` çiftini söndür. Diğer iki aşırı yükleme, `CRect` her tarafını diğerlerinden bağımsız olarak söndür.

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

##  <a name="equalrect"></a>CRect:: EqualRect

`CRect` verilen dikdörtgene eşit olup olmadığını belirler.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
Bir dikdörtgenin sol üst ve sağ alt köşe koordinatlarını içeren bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İki dikdörtgende aynı üst, sol, alt ve sağ değerler varsa sıfır dışında; Aksi takdirde 0.

> [!NOTE]
>  Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

##  <a name="height"></a>CRect:: Height

En üstteki değeri alt değerden çıkararak `CRect` yüksekliğini hesaplar.

```
int Height() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`yüksekliği.

### <a name="remarks"></a>Açıklamalar

Elde edilen değer negatif olabilir.

> [!NOTE]
>  Dikdörtgen normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

##  <a name="inflaterect"></a>CRect:: InflateRect

`InflateRect`, yüzlerini merkezinden uzağa taşıyarak `CRect`.

```
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
`CRect`sol ve sağ taraflarından şişiteedilecek birim sayısını belirtir.

*Iz*<br/>
`CRect`üst ve alt kısmını şişiteden birim sayısını belirtir.

*boyutla*<br/>
`CRect`şişiteden birim sayısını belirten bir [Boyut](/windows/win32/api/windef/ns-windef-size) veya [CSize](csize-class.md) . `cx` değeri, sol ve sağ taraflarındaki birim sayısını belirtir ve `cy` değeri üst ve alt değerlerini şişiteedilecek birim sayısını belirtir.

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına işaret eder veya her bir kenar için kullanılacak birim sayısını belirten `CRect`.

*girişindeki*<br/>
`CRect`sol tarafının hangi birim sayısını ayırt etmek için belirtir.

*şı*<br/>
`CRect`en üstünü içine almak için birim sayısını belirtir.

*r*<br/>
`CRect`sağ tarafının kaç birim sayısını belirtir.

*b*<br/>
`CRect`altına inen alt kısmını almak için birim sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Bunu yapmak için, `InflateRect` birimleri soldan ve üstten çıkartır ve sağ ve Alta birimler ekler. `InflateRect` parametreler imzalı değerlerdir; pozitif değerler `CRect` değer Şişir ve negatif değerler bu değeri söndür.

İlk iki aşırı yükleme, toplam genişliğinin iki kez *x* (veya `cx`) artması ve toplam yüksekliğinin iki kez *y* (veya `cy`) ile artması için her iki çift `CRect` çiftini ters şişir. Diğer iki aşırı yükleme, `CRect` her tarafını diğerlerinden bağımsız olarak şişir.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

##  <a name="intersectrect"></a>CRect:: IntersectRect

Bir `CRect` varolan iki dikdörtgenin kesişimine eşit hale getirir.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRect1*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya kaynak dikdörtgeni içeren `CRect` nesnesine işaret eder.

*lpRect2*<br/>
Bir `RECT` yapısına veya kaynak dikdörtgeni içeren `CRect` nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Kesişim boş değilse sıfır dışı; kesişme boşsa 0.

### <a name="remarks"></a>Açıklamalar

Kesişim, hem varolan dikdörtgenlerde bulunan en büyük dikdörtgendir.

> [!NOTE]
>  Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

##  <a name="isrectempty"></a>CRect:: IsRectEmpty

`CRect` boş olup olmadığını belirler.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect` boşsa sıfır dışı; `CRect` boş değilse 0.

### <a name="remarks"></a>Açıklamalar

Genişlik ve/veya Yükseklik 0 veya negatif ise, bir dikdörtgen boştur. Dikdörtgenin tüm koordinatlarının sıfır olup olmadığını belirleyen `IsRectNull`farklıdır.

> [!NOTE]
>  Dikdörtgen normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
ASSERT(rectEmpty.IsRectEmpty());
```

##  <a name="isrectnull"></a>CRect:: IsRectNull

`CRect` üst, sol, alt ve sağ değerlerinin tümünün 0 ' a eşit olup olmadığını belirler.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`üst, sol, alt ve sağ değerlerinin tümü 0 ' a eşit değilse sıfır; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Dikdörtgenin boş olup olmadığını belirleyen `IsRectEmpty`farklıdır.

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

##  <a name="movetox"></a>CRect:: MoveToX

Dikdörtgeni *x*tarafından belirtilen mutlak x koordinatına taşımak için bu işlevi çağırın.

```
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

##  <a name="movetoxy"></a>CRect:: MoveToXY

Dikdörtgeni belirtilen mutlak x ve y koordinatlarına taşımak için bu işlevi çağırın.

```
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Dikdörtgenin sol üst köşesinin mutlak x koordinatı.

*Iz*<br/>
Dikdörtgenin sol üst köşesinin mutlak y koordinatı.

*seçeneğinin*<br/>
Dikdörtgenin mutlak sol üst köşesini belirten `POINT` yapısı.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
ASSERT(rect == CRect(10, 10, 110, 110));
```

##  <a name="movetoy"></a>CRect:: Moveoyunu

Dikdörtgeni *y*tarafından belirtilen mutlak y koordinatına taşımak için bu işlevi çağırın.

```
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

##  <a name="normalizerect"></a>CRect:: NormalizeRect

Her iki yükseklik ve genişlik de pozitif olacak şekilde `CRect` normalleştirir.

```
void NormalizeRect() throw();
```

### <a name="remarks"></a>Açıklamalar

Dikdörtgen, Windows 'un koordinatları için genellikle kullandığı dördüncü Çeyrekli konumlandırma için normalleştirilir. `NormalizeRect` üst ve alt değerleri karşılaştırır ve en alttan daha büyükse onları değiştirir. Benzer şekilde, sol ve sağ değerleri Solsa, sol ve sağ değerlerini değiştirir. Bu işlev, farklı eşleme modlarıyla ve ters dikdörtgenlerle ilgilenirken yararlıdır.

> [!NOTE]
> Aşağıdaki `CRect` üye işlevleri, düzgün çalışmak için Normalleştirilmemiş dikdörtgenler gerektirir: [Height](#height), [Width](#width), [size](#size), [IsRectEmpty](#isrectempty), [ptinrect](#ptinrect), [equalrect](#equalrect), [unionrect](#unionrect), [IntersectRect](#intersectrect), [SubtractRect](#subtractrect), [operator = =](#operator_eq_eq), operator [! =](#operator_neq), [işleç &#124; ](#operator_or), [operator &#124;](#operator_or_eq)=, [işleç &](#operator_amp)ve [operator & =](#operator_amp_eq).

### <a name="example"></a>Örnek

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

##  <a name="offsetrect"></a>CRect:: OffsetRect

`CRect` belirtilen uzaklıklara göre gider.

```
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

X ve *y* birimlerinin yanı sıra y ekseni üzerinde `CRect`*x* birimini de yukarı kaydırır. *X* ve *y* parametreleri imzalı değerlerdir, bu nedenle `CRect` sol veya sağ ve yukarı veya aşağı taşınabilir.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

##  <a name="operator_lpcrect"></a>CRect:: operator LPCRECT bir `CRect` bir [lpcrect](../../mfc/reference/data-types-mfc.md)öğesine dönüştürür.

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullandığınızda, ( **&** ) işlecinin adresine ihtiyacınız yoktur. Bu işleç, bir `LPCRECT`bekleyen bir işleve `CRect` nesnesini geçirdiğinizde otomatik olarak kullanılacaktır.

##  <a name="operator_lprect"></a>CRect:: operator LPRECT

Bir `CRect` bir [lpRect](../../mfc/reference/data-types-mfc.md)öğesine dönüştürür.

```
operator LPRECT() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullandığınızda, ( **&** ) işlecinin adresine ihtiyacınız yoktur. Bu işleç, bir `LPRECT`bekleyen bir işleve `CRect` nesnesini geçirdiğinizde otomatik olarak kullanılacaktır.

### <a name="example"></a>Örnek

[CRect:: operator lpcrect](#operator_lpcrect)örneğine bakın.

##  <a name="operator_eq"></a>CRect:: operator =

`CRect`için *srcRect* atar.

```
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>Parametreler

*srcRect*<br/>
Bir kaynak dikdörtgeni ifade eder. Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya `CRect`olabilir.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 127, 168);
CRect rect2;

rect2 = rect;
ASSERT(rect2 == CRect(0, 0, 127, 168));
```

##  <a name="operator_eq_eq"></a>CRect:: operator = =

Sol üst ve sağ alt köşelerin koordinatlarını karşılaştırarak `rect` `CRect` eşit olup olmadığını belirler.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Bir kaynak dikdörtgeni ifade eder. Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya `CRect`olabilir.

### <a name="return-value"></a>Dönüş Değeri

Eşitse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

##  <a name="operator_neq"></a>CRect:: operator! =

Sol üst ve sağ alt köşelerin koordinatlarını karşılaştırarak *Rect* 'in `CRect` eşit olup olmadığını belirler.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Bir kaynak dikdörtgeni ifade eder. Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya `CRect`olabilir.

### <a name="return-value"></a>Dönüş Değeri

Eşit değilse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

##  <a name="operator_add_eq"></a>CRect:: operator + =

İlk iki aşırı yükleme `CRect` belirtilen uzaklıkları taşır.

```
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
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` nesnesine işaret eder ve `CRect`her bir tarafını almak için birim sayısını içerir.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy`) değerleri `CRect`eklenir.

Üçüncü aşırı yükleme, parametrenin her üyesinde belirtilen birim sayısına göre `CRect`.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

##  <a name="operator_-_eq"></a>CRect:: operator-=

İlk iki aşırı yükleme `CRect` belirtilen uzaklıkları taşır.

```
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
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına işaret eder veya `CRect`her tarafını söndür birim sayısını içeren `CRect` nesnesini gösterir.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy`) değerleri `CRect`çıkarılır.

Üçüncü aşırı yükleme, parametrenin her üyesinde belirtilen birim sayısına göre `CRect` erteleyerek. Bu aşırı yükleme ' nin [erteleme](#deflaterect)gibi işlevleri olduğunu unutmayın.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

##  <a name="operator_amp_eq"></a>CRect:: operator &amp;=

`CRect` ve `rect`kesişimine eşit `CRect` ayarlar.

```
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya `CRect`içerir.

### <a name="remarks"></a>Açıklamalar

Kesişim, her iki dikdörtgende bulunan en büyük dikdörtgendir.

> [!NOTE]
>  Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

[CRect:: IntersectRect](#intersectrect)örneğine bakın.

##  <a name="operator_or_eq"></a>CRect:: operator &#124;=

`CRect` ve `rect`birleşime eşit `CRect` ayarlar.

```
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
`CRect` veya [Rect](/windows/win32/api/windef/ns-windef-rect)içerir.

### <a name="remarks"></a>Açıklamalar

Birleşim, her iki kaynak dikdörtgeni içeren en küçük dikdörtgendir.

> [!NOTE]
>  Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);

rect1 |= rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect1);
```

##  <a name="operator_add"></a>CRect:: operator +

İlk iki aşırı yükleme, belirtilen uzaklıklara göre `CRect` eşit olan bir `CRect` nesnesi döndürüyor.

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
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına işaret eder veya dönüş değerinin her tarafını almak için birim sayısını içeren `CRect` nesnesini gösterir.

### <a name="return-value"></a>Dönüş Değeri

`CRect`, parametresinde belirtilen birim sayısına göre `CRect` hareket ettirmeden ya da flaktan elde edilir.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy`) parametreleri `CRect`konumuna eklenir.

Üçüncü aşırı yükleme, parametrenin her üyesinde belirtilen birim sayısı ile `CRect` eşit olan yeni bir `CRect` döndürür.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 + pt;
CRect   rectResult(135, 300, 235, 400);
ASSERT(rectResult == rect2);
```

##  <a name="operator_-"></a>CRect:: operator-

İlk iki aşırı yükleme, belirtilen uzaklıklara göre `CRect` eşit olan bir `CRect` nesnesi döndürüyor.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Dönüş değerini taşıyacağınız birim sayısını belirten bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya `CPoint` nesnesi.

*boyutla*<br/>
Dönüş değerini taşıyacağınız birim sayısını belirten bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı veya `CSize` nesnesi.

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya dönüş değerinin her tarafını söndür birim sayısını içeren `CRect` nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

`CRect`, `CRect`, parametresinde belirtilen birim sayısına göre hareket ettirmeden veya erteleyerek elde edilir.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy`) parametreleri `CRect`konumlarından çıkarılır.

Üçüncü aşırı yükleme, parametrenin her üyesinde belirtilen birim sayısına göre `CRect` eşit olan yeni bir `CRect` döndürür. Bu aşırı yükleme, [SubtractRect](#subtractrect)değil, [savunma](#deflaterect)gibi işlevlerin olduğunu unutmayın.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

##  <a name="operator_amp"></a>CRect:: operator &amp;

`CRect` ve *rect2*kesişimi olan bir `CRect` döndürür.

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>Parametreler

*rect2*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya `CRect`içerir.

### <a name="return-value"></a>Dönüş Değeri

`CRect` ve *rect2*kesişimi olan bir `CRect`.

### <a name="remarks"></a>Açıklamalar

Kesişim, her iki dikdörtgende bulunan en büyük dikdörtgendir.

> [!NOTE]
>  Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 & rect2;
CRect   rectResult(100, 100, 200, 200);
ASSERT(rectResult == rect3);
```

##  <a name="operator_or"></a>CRect:: işleci&#124;

`CRect` ve *rect2*birleşimi olan bir `CRect` döndürür.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>Parametreler

*rect2*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya `CRect`içerir.

### <a name="return-value"></a>Dönüş Değeri

`CRect` ve *rect2*birleşimi olan bir `CRect`.

### <a name="remarks"></a>Açıklamalar

Birleşim, her iki dikdörtgeni de içeren en küçük dikdörtgendir.

> [!NOTE]
>  Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 | rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

##  <a name="ptinrect"></a>CRect::P tInRect

Belirtilen noktanın `CRect`içinde olup olmadığını belirler.

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi içerir.

### <a name="return-value"></a>Dönüş Değeri

Nokta `CRect`yer alıyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nokta, sol veya üst tarafta yer alıyorsa veya dört tarafdayın içindeyse `CRect`. Sağ veya alt taraftaki bir nokta `CRect`dışındadır.

> [!NOTE]
>  Dikdörtgen normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

##  <a name="setrect"></a>CRect:: SetRect

`CRect` boyutlarını belirtilen koordinatlara ayarlar.

```
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

##  <a name="setrectempty"></a>CRect:: SetRectEmpty

Tüm koordinatları sıfıra ayarlayarak boş bir dikdörtgen `CRect` yapar.

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

##  <a name="size"></a>CRect:: SIZE

Dönüş değerinin `cx` ve `cy` üyeleri, `CRect`yüksekliğini ve genişliğini içerir.

```
CSize Size() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`boyutunu içeren [CSize](csize-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Yükseklik ya da Genişlik negatif olabilir.

> [!NOTE]
>  Dikdörtgen normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

##  <a name="subtractrect"></a>CRect:: SubtractRect

`CRect` boyutlarının `lpRectSrc1``lpRectSrc2` çıkarmasına eşit hale getirir.

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRectSrc1*<br/>
[Dikdörtgen yapısına veya](/windows/win32/api/windef/ns-windef-rect) dikdörtgenin çıkarılacak `CRect` nesnesine işaret eder.

*lpRectSrc2*<br/>
*LpRectSrc1* parametresi tarafından işaret edilen dikdörtgenden çıkarılacak `RECT` yapısına veya `CRect` nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çıkarma, *lpRectScr1* içinde *lpRectScr1* ve *lpRectScr2*kesişimine olmayan tüm noktaları içeren en küçük dikdörtgendir.

*LpRectSrc2* tarafından belirtilen dikdörtgen, x veya y yönlerinin en az birinde *lpRectSrc1* tarafından belirtilen dikdörtgenden tamamen çakışmazsa, *lpRectSrc1* tarafından belirtilen dikdörtgen değiştirilmez.

Örneğin, *lpRectSrc1* (10, 10, 100.100) ve *lpRectSrc2* (50, 50, 150.150) Ise, işlev döndürüldüğünde *lpRectSrc1* tarafından işaret edilen dikdörtgen değiştirilmez. *LpRectSrc1* (10, 10, 100.100) ve *lpRectSrc2* ise (50, 10, 150.150), ancak *lpRectSrc1* tarafından işaret edilen dikdörtgen, işlev döndürüldüğünde (10, 10, 50.100) koordinatları içerir.

`SubtractRect` [işleçle](#operator_-) veya [operator-=](#operator_-_eq)ile aynı değil. Bu işleçlerden hiçbiri asla `SubtractRect`çağırmaz.

> [!NOTE]
>  Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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

##  <a name="topleft"></a>CRect:: TopLeft

Koordinatlar, `CRect`bulunan bir [CPoint](cpoint-class.md) nesnesine başvuru olarak döndürülür.

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

##  <a name="unionrect"></a>CRect:: UnionRect

`CRect` boyutlarının iki kaynak dikdörtgenin birleşime eşit olmasını sağlar.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRect1*<br/>
Kaynak dikdörtgeni içeren bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya `CRect` işaret eder.

*lpRect2*<br/>
Kaynak dikdörtgeni içeren bir `RECT` veya `CRect` işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Birleşim boş değilse sıfır dışı; UNION boşsa 0.

### <a name="remarks"></a>Açıklamalar

Birleşim, her iki kaynak dikdörtgeni içeren en küçük dikdörtgendir.

Windows boş bir dikdörtgenin boyutlarını yoksayar; Yani, yüksekliği olmayan veya genişliği olmayan bir dikdörtgen.

> [!NOTE]
>  Dikdörtgenin her ikisi de normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3.UnionRect(&rect1, &rect2);
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

##  <a name="width"></a>CRect:: Width

Sağ değerden sol değeri çıkararak `CRect` genişliğini hesaplar.

```
int Width() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`genişliği.

### <a name="remarks"></a>Açıklamalar

Genişlik negatif olabilir.

> [!NOTE]
>  Dikdörtgen normalleştirilmeli veya bu işlev başarısız olabilir. Bu işlevi çağırmadan önce dikdörtgeni normalleştirmek için [NormalizeRect](#normalizerect) çağrısı yapabilirsiniz.

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
[RECT](/windows/win32/api/windef/ns-windef-rect)
