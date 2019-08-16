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
ms.openlocfilehash: 2c84ce888e37b2a8985ca63cf3544205bc61f69f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491538"
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
|[CRect:: BottomRight](#bottomright)|Sağ alt noktasını `CRect`döndürür.|
|[CRect:: CenterPoint](#centerpoint)|Öğesinin `CRect`merkez noktasını döndürür.|
|[CRect:: CopyRect](#copyrect)|Kaynak dikdörtgenin boyutlarını öğesine `CRect`kopyalar.|
|[CRect::D eflateRect](#deflaterect)|Genişliğini ve yüksekliğini `CRect`düşürür.|
|[CRect:: EqualRect](#equalrect)|Verilen dikdörtgene `CRect` eşit olup olmadığını belirler.|
|[CRect:: Height](#height)|Yüksekliğini `CRect`hesaplar.|
|[CRect:: InflateRect](#inflaterect)|Genişliğini ve yüksekliğini `CRect`artırır.|
|[CRect:: IntersectRect](#intersectrect)|İki `CRect` dikdörtgenin kesişimine eşit olarak ayarlanır.|
|[CRect:: IsRectEmpty](#isrectempty)|Boş olup `CRect` olmadığını belirler. `CRect`Genişlik ve/veya Yükseklik 0 ise boştur.|
|[CRect:: IsRectNull](#isrectnull)|`top` `bottom`,, Ve`right` üye değişkenlerinin tümünün 0 ' aeşitolupolmadığınıbelirler.`left`|
|[CRect:: MoveToX](#movetox)|Belirtilen `CRect` x koordinatına gider.|
|[CRect:: MoveToXY](#movetoxy)|Belirtilen `CRect` x ve y koordinatlarına gider.|
|[CRect:: Moveoyunu](#movetoy)|Belirtilen `CRect` y koordinatıyla gider.|
|[CRect:: NormalizeRect](#normalizerect)|Yüksekliğini ve genişliğini `CRect`standartlaştırır.|
|[CRect:: OffsetRect](#offsetrect)|Belirtilen `CRect` uzaklıklara göre gider.|
|[CRect::P tInRect](#ptinrect)|Belirtilen noktanın içinde `CRect`olup olmadığını belirler.|
|[CRect:: SetRect](#setrect)|Boyutlarını `CRect`ayarlar.|
|[CRect:: SetRectEmpty](#setrectempty)|Boş `CRect` bir dikdörtgene (tüm koordinatlar 0 ' a eşit) ayarlar.|
|[CRect:: size](#size)|Boyutunu `CRect`hesaplar.|
|[CRect:: SubtractRect](#subtractrect)|Bir dikdörtgeni diğerinden çıkarır.|
|[CRect:: TopLeft](#topleft)|Sol üst noktasını `CRect`döndürür.|
|[CRect:: UnionRect](#unionrect)|İki `CRect` dikdörtgenin birleşimini eşit olarak ayarlar.|
|[CRect:: Width](#width)|Genişliğini `CRect`hesaplar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CRect:: operator-](#operator_-)|Verilen uzaklıkları `CRect` çıkarır veya `CRect` erteler ve sonucu `CRect`döndürür.|
|[CRect:: operator LPCRECT](#operator_lpcrect)|`CRect` Bir`LPCRECT`öğesine dönüştürür.|
|[CRect:: operator LPRECT](#operator_lprect)|`CRect` Bir`LPRECT`öğesine dönüştürür.|
|[CRect:: operator! =](#operator_neq)|Bir dikdörtgene `CRect` eşit olup olmadığını belirler.|
|[CRect:: işleci&amp;](#operator_amp)|`CRect` Ve dikdörtgeninin kesişimini oluşturur ve sonucu `CRect`döndürür.|
|[CRect:: işleci&amp;=](#operator_amp_eq)|, `CRect` `CRect` Ve dikdörtgeninin kesişimine eşit ayarlar.|
|[CRect:: işleci&#124;](#operator_or)|`CRect` Ve dikdörtgeninin birleşimini oluşturur ve sonucu `CRect`döndürür.|
|[CRect:: operator &#124;=](#operator_or_eq)|, `CRect` `CRect` Ve bir dikdörtgenin birleşimini eşit olarak ayarlar.|
|[CRect:: operator +](#operator_add)|Verilen uzaklıkları `CRect` veya `CRect` geri 'leri ekler ve sonucu `CRect`döndürür.|
|[CRect:: operator + =](#operator_add_eq)|Belirtilen uzaklıkları `CRect` veya `CRect`Flap ekler.|
|[CRect:: operator =](#operator_eq)|Bir dikdörtgenin boyutlarını öğesine `CRect`kopyalar.|
|[CRect:: operator-=](#operator_-_eq)|Belirtilen uzaklıkları `CRect` çıkarır veya `CRect`ertetir.|
|[CRect:: operator = =](#operator_eq_eq)|Bir dikdörtgene `CRect` eşit olup olmadığını belirler.|

## <a name="remarks"></a>Açıklamalar

`CRect`Ayrıca, nesneleri ve Windows `CRect` `RECT` yapılarını işlemek için üye işlevleri de içerir.

Bir `CRect` nesne, bir `RECT` yapının, `LPCRECT`veya `LPRECT` geçirilebileceğini bir işlev parametresi olarak geçirilebilir.

> [!NOTE]
> Bu sınıf `tagRECT` yapıdan türetilir. (Ad `tagRECT` , `RECT` yapı için daha yaygın olarak kullanılan bir addır.) Bu`left`, `RECT` yapının veri üyelerinin ( `right`, `top`, ve `bottom`) erişilebilir veri üyeleri `CRect`olduğu anlamına gelir.

Bir `CRect` dikdörtgenin sol üst ve sağ alt noktalarını tanımlayan üye değişkenlerini içerir.

Bir belirtirken, `CRect`diğer bir deyişle, sol koordinat değerinin doğru ve en alttan küçük olması gibi diğer bir deyişle, bunu normalleştirilemez şekilde oluşturmak için dikkatli olmanız gerekir. Örneğin, (10, 10) ve sağ alt (20, 20) sol üst bir, normalleştirilmiş bir dikdörtgen tanımlar, ancak (20, 20) ve sağ alt (10, 10) sol üst bir, Normalleştirilmemiş bir dikdörtgen tanımlar. Dikdörtgen normalleştirilmez değilse birçok `CRect` üye işlevi hatalı sonuçlar döndürebilir. (Bu işlevlerin listesi için bkz. [CRect:: NormalizeRect](#normalizerect) .) Normalleştirilmiş dikdörtgenler gerektiren bir işlevi çağırmadan önce `NormalizeRect` işlevi çağırarak normalleştirilmiş olmayan dikdörtgenleri normalleştirin.

`CRect` [CDC::D ptolp](../../mfc/reference/cdc-class.md#dptolp) ve [CDC:: LPtoDP](../../mfc/reference/cdc-class.md#lptodp) üye işlevleriyle işleme yaparken dikkatli olun. Bir görüntüleme bağlamının eşleme modu, içinde `MM_LOENGLISH` `CDC::DPtoLP` olduğu gibi y uzantısı negatif ise, en üst öğenin alt kısmından daha büyük olması için `CRect` öğesini dönüştürür. Ve gibi işlevler, dönüştürülen `CRect`yükseklik için negatif değerler döndürür ve dikdörtgen Normalleştirilmemiş olur. `Size` `Height`

Aşırı yüklenmiş `CRect` işleçler kullanılırken, ilk işlenen bir `CRect`olmalıdır; ikincisi ise bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı ya da bir `CRect` nesne olabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagRECT`

`CRect`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltypes. h

##  <a name="bottomright"></a>CRect:: BottomRight

Koordinatlar, içinde `CRect`bulunan bir [CPoint](cpoint-class.md) nesnesine başvuru olarak döndürülür.

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

Sol ve sağ değerleri ekleyerek `CRect` ve iki ile bölerek ve en üst ve alt değerleri ekleyerek ve iki olarak bölerek Centerpoint 'i hesaplar.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CPoint` Merkez`CRect`noktası olan bir nesne.

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

`lpSrcRect` Dikdörtgeni içine`CRect`kopyalar.

```
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>Parametreler

*lpSrcRect*<br/>
Kopyalanacak [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` nesnesine işaret eder.

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
Öğesinin `CRect`sol konumunu belirtir.

*şı*<br/>
Öğesinin `CRect`üst öğesini belirtir.

*r*<br/>
Öğesinin `CRect`doğru konumunu belirtir.

*b*<br/>
Öğesinin `CRect`alt öğesini belirtir.

*srcRect*<br/>
İçin`CRect`koordinatları olan [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvurur.

*lpSrcRect*<br/>
Koordinatlarıyla yapısına işaret eder. `CRect` `RECT`

*seçeneğinin*<br/>
Oluşturulacak dikdörtgenin kaynak noktasını belirtir. Sol üst köşeye karşılık gelir.

*boyutla*<br/>
Oluşturulacak dikdörtgenin sağ alt köşesine kadar sol üst köşeden yer değiştirme sayısını belirtir.

*Topsol*<br/>
Öğesinin `CRect`üst sol konumunu belirtir.

*bottomRight*<br/>
Öğesinin `CRect`sağ alt konumunu belirtir.

### <a name="remarks"></a>Açıklamalar

`left`Hiçbir bağımsız değişken verilmezse `top` `right`,,, ve `bottom` üyeleri başlatılmaz.

`CRect`( )Ve`CRect`()`LPCRECT`oluşturucuları bir [CopyRect gerçekleştirir.](#copyrect)`const RECT&` Diğer oluşturucular nesnenin üye değişkenlerini doğrudan başlatır.

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

##  <a name="deflaterect"></a>CRect::D eflateRect

`DeflateRect`yüzlerini merkezine doğru taşıyarak erteleyerek.`CRect`

```
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sol ve sağ taraflarını `CRect`söndür birim sayısını belirtir.

*Iz*<br/>
Üst ve alt kısmını `CRect`söndür birim sayısını belirtir.

*boyutla*<br/>
Söndür`CRect`birim sayısını belirten bir [Boyut](/windows/win32/api/windef/ns-windef-size) veya [CSize](csize-class.md) . Değer, sol ve sağ taraflarını söndür birim sayısını belirtir `cy` ve değer, üst ve alt değerlerini söndür birim sayısını belirtir. `cx`

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına işaret eder veya `CRect` her bir yüzü söndür birim sayısını belirtir.

*girişindeki*<br/>
Sol tarafının `CRect`söndür birim sayısını belirtir.

*şı*<br/>
En üstünü `CRect`söndür birim sayısını belirtir.

*r*<br/>
Sağ tarafının `CRect`söndür olacak birim sayısını belirtir.

*b*<br/>
Alt öğesinin `CRect`altı olarak söndür birim sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Bunu yapmak için, `DeflateRect` sol ve üst kısımdaki birimleri ekler ve birimleri sağ ve alttan çıkartır. Parametresi `DeflateRect` işaretli değerlerdir; pozitif değerler söndür `CRect` ve negatif değerler onu şişir.

İlk iki aşırı yükleme, toplam genişliğinin iki kez `CRect` *x* (veya `cx`) ile azaltılana ve toplam yüksekliğinin iki kez *y* (veya `cy`) ile azaltılmasını sağlamak için her iki karşıt çift çiftini söndür. Diğer iki aşırı yükleme diğerlerinden `CRect` bağımsız olarak her bir kenarı ikiye söndür.

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

Verilen dikdörtgene `CRect` eşit olup olmadığını belirler.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
Bir dikdörtgenin sol [](/windows/win32/api/windef/ns-windef-rect) üst ve sağ `CRect` alt köşe koordinatlarını içeren bir Rect yapısına veya nesnesine işaret eder.

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

Alt değerden en üstteki `CRect` değeri çıkararak yüksekliğini hesaplar.

```
int Height() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yüksekliği `CRect`.

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

`InflateRect`yüzlerini merkezinden `CRect` uzağa taşıyarak flatları.

```
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sol ve sağ taraflarından `CRect`şişiteedilecek birim sayısını belirtir.

*Iz*<br/>
Üst ve alt kısmını `CRect`şişiteden birim sayısını belirtir.

*boyutla*<br/>
Şişeedilecek birim sayısını belirten bir [Boyut](/windows/win32/api/windef/ns-windef-size) veya [CSize.](csize-class.md) `CRect` Değer, sol ve sağ taraflardan şişen birim sayısını belirtir `cy` ve değer, üst ve alt değerlerini şişiteedilecek birim sayısını belirtir. `cx`

*lpRect*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına işaret eder veya `CRect` her bir kenar için kullanılacak birim sayısını belirtir.

*girişindeki*<br/>
Sol tarafının `CRect`hangi birim sayısını ayırt etmek için belirtir.

*şı*<br/>
Üst öğesinin `CRect`üzerine inili edilecek birim sayısını belirtir.

*r*<br/>
Sağ tarafının `CRect`hangi birim sayısını ayırt etmek için belirtir.

*b*<br/>
Alt öğesinin `CRect`altına inili edilecek birim sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Bunu yapmak için, `InflateRect` sol ve üst kısımdaki birimleri çıkartır ve sağ ve alttaki birimleri ekler. Parametresi `InflateRect` işaretli değerlerdir; pozitif değerler ters Şişir `CRect` ve negatif değerler bu değeri söndür.

İlk iki aşırı yükleme, toplam genişliğinin iki kez *x* ( `cx`veya `CRect` ) ile artması ve toplam yüksekliğinin iki kez *y* (veya `cy`) ile artması için her iki çift tarafının de her ikisini de şişir. Diğer iki aşırı yükleme diğerlerinden bağımsız olarak her bir `CRect` tarafı şişir.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

##  <a name="intersectrect"></a>CRect:: IntersectRect

Varolan iki dikdörtgenin kesişimine eşithalegetirir.`CRect`

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRect1*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` kaynak dikdörtgeni içeren nesnesine işaret eder.

*lpRect2*<br/>
Kaynak dikdörtgeni içeren `RECT` bir yapıya `CRect` veya nesneye işaret eder.

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

Boş olup `CRect` olmadığını belirler.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Boşsa sıfır sıfır; boş değilse `CRect` 0. `CRect`

### <a name="remarks"></a>Açıklamalar

Genişlik ve/veya Yükseklik 0 veya negatif ise, bir dikdörtgen boştur. Dikdörtgenin tüm `IsRectNull`koordinatlarının sıfır olup olmadığını belirleyen öğesinden farklıdır.

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

Üst, sol, alt ve sağ değerlerinin `CRect` tümünün 0 ' a eşit olup olmadığını belirler.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`En üst, sol, alt ve sağ değerlerinin hepsi 0 ' a eşit; Aksi takdirde 0 ' dır.

### <a name="remarks"></a>Açıklamalar

Dikdörtgenin boş `IsRectEmpty`olup olmadığını belirleyen öğesinden farklıdır.

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
Dikdörtgenin `POINT` mutlak sol üst köşesini belirten bir yapı.

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

Her iki `CRect` yükseklik ve genişlik de pozitif olacak şekilde normalleştirir.

```
void NormalizeRect() throw();
```

### <a name="remarks"></a>Açıklamalar

Dikdörtgen, Windows 'un koordinatları için genellikle kullandığı dördüncü Çeyrekli konumlandırma için normalleştirilir. `NormalizeRect`üst ve alt değerleri karşılaştırır ve en alttan daha büyükse onları değiştirir. Benzer şekilde, sol ve sağ değerleri Solsa, sol ve sağ değerlerini değiştirir. Bu işlev, farklı eşleme modlarıyla ve ters dikdörtgenlerle ilgilenirken yararlıdır.

> [!NOTE]
> Aşağıdaki `CRect` üye işlevleri düzgün çalışması için normalleştirilmiş dikdörtgenler gerektirir: [Yükseklik](#height), [Genişlik](#width), [Boyut](#size), [isrectempty](#isrectempty), [pınrect](#ptinrect), [equalrect](#equalrect), [unionrect](#unionrect), [IntersectRect](#intersectrect), [SubtractRect](#subtractrect), [işleç = =](#operator_eq_eq), [işleç! =](#operator_neq), [işleç &#124; ](#operator_or), [operator &#124;=](#operator_or_eq), [işleç &](#operator_amp)ve [işleç & =](#operator_amp_eq).

### <a name="example"></a>Örnek

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

##  <a name="offsetrect"></a>CRect:: OffsetRect

Belirtilen `CRect` uzaklıklara göre gider.

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

X `CRect`birimini x ekseni ve *y* birimleri üzerinde y ekseni üzerinde kaydırır. *X* ve *y* parametreleri imzalı değerlerdir, bu nedenle `CRect` sol veya sağ ve yukarı veya aşağı taşınabilir.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

##  <a name="operator_lpcrect"></a>CRect:: operator lpcrect, bir `CRect` [lpcrect](../../mfc/reference/data-types-mfc.md)öğesine dönüştürür.

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullandığınızda, Address-of ( **&** ) işlecine gerek kalmaz. Bu işleç, bir `CRect` `LPCRECT`nesnesini bekleyen bir işleve geçirdiğinizde otomatik olarak kullanılacaktır.

##  <a name="operator_lprect"></a>CRect:: operator LPRECT

Bir `CRect` [lpRect](../../mfc/reference/data-types-mfc.md)öğesine dönüştürür.

```
operator LPRECT() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullandığınızda, Address-of ( **&** ) işlecine gerek kalmaz. Bu işleç, bir `CRect` `LPRECT`nesnesini bekleyen bir işleve geçirdiğinizde otomatik olarak kullanılacaktır.

### <a name="example"></a>Örnek

[CRect:: operator lpcrect](#operator_lpcrect)örneğine bakın.

##  <a name="operator_eq"></a>CRect:: operator =

' A *srcRect* `CRect`atar.

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

Sol üst `rect` ve sağ alt `CRect` köşelerin koordinatlarını karşılaştırarak eşit olup olmadığını belirler.

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

Sol üst ve sağ alt köşelerin `CRect` koordinatları karşılaştırılırken Rect 'in eşit olup olmadığını belirler.

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

İlk iki aşırı yükleme belirtilen `CRect` uzaklıkları taşır.

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
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` ' nin `CRect`her tarafında şişiteden birim sayısını içeren nesneye işaret eder.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` ve `cy`) değerleri öğesine `CRect`eklenir.

Üçüncü aşırı yükleme, parametrenin her `CRect` üyesinde belirtilen birim sayısına göre geçersiz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

##  <a name="operator_-_eq"></a>CRect:: operator-=

İlk iki aşırı yükleme belirtilen `CRect` uzaklıkları taşır.

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
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` her bir tarafını `CRect`söndür birim sayısını içeren nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (ya `cx` `cy`da) değerleri çıkarılır. `CRect`

Üçüncü aşırı yükleme, parametrenin `CRect` her üyesinde belirtilen birim sayısına göre ertetir. Bu aşırı yükleme ' nin [erteleme](#deflaterect)gibi işlevleri olduğunu unutmayın.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

##  <a name="operator_amp_eq"></a>CRect:: işleci&amp;=

Ve`CRect` kesişimine`CRect`eşitayarlar `rect`.

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

, `CRect` `CRect` Ve birleşiminieşitolarakayarlar.`rect`

```
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Or Rect içerir. [](/windows/win32/api/windef/ns-windef-rect) `CRect`

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

İlk iki aşırı yükleme, belirtilen `CRect` uzaklıklarıyla `CRect` aynı değere eşit bir nesne döndürüyor.

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
Dönüş değerinin her [](/windows/win32/api/windef/ns-windef-rect) tarafını almak için `CRect` birim sayısını içeren bir Rect yapısına veya nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Bu `CRect` , parametresinde belirtilen birim sayısına göre hareket `CRect` ettirmeden ya da flaktan elde edilir.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` `cy`ve) parametreleri konumuna eklenir. `CRect`

Üçüncü aşırı yükleme, parametrenin her `CRect` üyesinde belirtilen birim sayısına `CRect` eşit olan yeni bir döndürür.

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

İlk iki aşırı yükleme, belirtilen `CRect` uzaklıklarıyla `CRect` aynı değere eşit bir nesne döndürüyor.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Dönüş [](/windows/win32/api/windef/ns-windef-point) değerini taşıyacağınız `CPoint` birim sayısını belirten bir nokta yapısı veya nesnesi.

*boyutla*<br/>
Dönüş [](/windows/win32/api/windef/ns-windef-size) değerini taşıyacağınız `CSize` birim sayısını belirten bir boyut yapısı veya nesnesi.

*lpRect*<br/>
Dönüş değerinin her [](/windows/win32/api/windef/ns-windef-rect) tarafını söndür olan `CRect` birim sayısını içeren bir Rect yapısına veya nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

, `CRect` Parametresinde belirtilen birim sayısına `CRect` göre hareket ettirmeden veya erteleyerek elde edilir.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* (veya `cx` `cy`ve) parametreleri konumdan çıkarılır. `CRect`

Üçüncü aşırı yükleme, parametrenin her `CRect` üyesinde belirtilen birim sayısına `CRect` eşit olan yeni bir döndürür. Bu aşırı yükleme, [SubtractRect](#subtractrect)değil, [savunma](#deflaterect)gibi işlevlerin olduğunu unutmayın.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

##  <a name="operator_amp"></a>CRect:: işleci&amp;

Ve`CRect` *rect2*kesişimi olan bir `CRect` döndürür.

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>Parametreler

*rect2*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya `CRect`içerir.

### <a name="return-value"></a>Dönüş Değeri

Ve rect2 'in `CRect` kesişimi. `CRect`

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

Ve`CRect` *rect2*birleşimi olan bir `CRect` döndürür.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>Parametreler

*rect2*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veya `CRect`içerir.

### <a name="return-value"></a>Dönüş Değeri

`CRect`Ve rect2`CRect` birleşimi.

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

Belirtilen noktanın içinde `CRect`olup olmadığını belirler.

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi içerir.

### <a name="return-value"></a>Dönüş Değeri

Nokta içinde yer `CRect`alıyorsa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nokta, `CRect` sol veya üst tarafa Dayıya da dört tarafın içinde yer alıyorsa. Sağ veya alt taraftaki bir nokta dışarıda `CRect`.

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

Boyutlarını `CRect` belirtilen koordinatlara ayarlar.

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

Tüm `CRect` koordinatları sıfıra ayarlayarak boş bir dikdörtgen yapar.

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

Dönüş değerinin `cy`veüyeleri , yüksekliğini ve genişliğini `CRect`içerir. `cx`

```
CSize Size() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Boyutunu`CRect`içeren [CSize](csize-class.md) nesnesi.

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

`CRect` Değerine eşit olan boyut boyutunu ' `lpRectSrc2` dan `lpRectSrc1`çıkarma için yapar.

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRectSrc1*<br/>
[Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` dikdörtgenin çıkarılacak nesnesine işaret eder.

*lpRectSrc2*<br/>
LpRectSrc1 parametresi tarafından işaret edilen `CRect` dikdörtgenden çıkarılacak yapıyaveyanesneyeişareteder.`RECT`

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çıkarma, *lpRectScr1* içinde *lpRectScr1* ve *lpRectScr2*kesişimine olmayan tüm noktaları içeren en küçük dikdörtgendir.

*LpRectSrc2* tarafından belirtilen dikdörtgen, x veya y yönlerinin en az birinde *lpRectSrc1* tarafından belirtilen dikdörtgenden tamamen çakışmazsa, *lpRectSrc1* tarafından belirtilen dikdörtgen değiştirilmez.

Örneğin, *lpRectSrc1* (10, 10, 100.100) ve *lpRectSrc2* (50, 50, 150.150) Ise, işlev döndürüldüğünde *lpRectSrc1* tarafından işaret edilen dikdörtgen değiştirilmez. *LpRectSrc1* (10, 10, 100.100) ve *lpRectSrc2* ise (50, 10, 150.150), ancak *lpRectSrc1* tarafından işaret edilen dikdörtgen, işlev döndürüldüğünde (10, 10, 50.100) koordinatları içerir.

`SubtractRect`[işleç](#operator_-) -veya [operator-=](#operator_-_eq)ile aynı değildir. Bu işleçlerden hiçbiri asla çağrı `SubtractRect`gerçekleştirmez.

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

Koordinatlar, içinde `CRect`bulunan bir [CPoint](cpoint-class.md) nesnesine başvuru olarak döndürülür.

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

İki kaynak dikdörtgenin birleşimini eşithalegetirir.`CRect`

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRect1*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) 'e işaret eder `CRect` veya bir kaynak dikdörtgen içerir.

*lpRect2*<br/>
Kaynak dikdörtgeni içeren `RECT` bir `CRect` veya ' a işaret eder.

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

Sol değeri sağ değerden `CRect` çıkararak genişliğini hesaplar.

```
int Width() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Genişliği `CRect`.

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
