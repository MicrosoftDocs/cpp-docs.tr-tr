---
title: CRect Sınıfı
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
ms.openlocfilehash: b99eca7fe3a9c84f8b79ef3d694e27b6dd74dcd9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747059"
---
# <a name="crect-class"></a>CRect Sınıfı

Windows [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına benzer.

## <a name="syntax"></a>Sözdizimi

```
class CRect : public tagRECT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRect::CRect](#crect)|Bir `CRect` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRect::BottomRight](#bottomright)|Sağ alt noktasını döndürür. `CRect`|
|[CRect::CenterPoint](#centerpoint)|`CRect`'nin merkez noktasını verir.|
|[CRect::CopyRect](#copyrect)|Kaynak dikdörtgenin boyutlarını `CRect`kopyalar.|
|[CRect::DeflateRect](#deflaterect)|Genişliği ve yüksekliğini `CRect`azaltır.|
|[CRect::EqualRect](#equalrect)|Verilen dikdörtgenin eşit olup olmadığını `CRect` belirler.|
|[CRect::Yükseklik](#height)|Yüksekliği `CRect`hesaplar.|
|[CRect::ŞişirmeRect](#inflaterect)|Genişliği ve yüksekliğini `CRect`artırır.|
|[CRect::KesişmeRect](#intersectrect)|İki `CRect` dikdörtgenin kesişme sine eşit ayarlar.|
|[CRect::IsRectEmpty](#isrectempty)|Boş olup `CRect` olmadığını belirler. `CRect`genişlik ve/veya yükseklik 0 ise boştur.|
|[CRect::IsRectNull](#isrectnull)|`top`, , `bottom` `left`ve `right` üye değişkenlerin hepsinin 0'a eşit olup olmadığını belirler.|
|[CRect::MoveToX](#movetox)|Belirtilen `CRect` x-koordinatına taşınır.|
|[CRect::MoveToXY](#movetoxy)|Belirtilen `CRect` x- ve y koordinatlarına taşınır.|
|[CRect::MoveToY](#movetoy)|Belirtilen `CRect` y-koordinatına taşınır.|
|[CRect::NormalizeRect](#normalizerect)|yüksekliği ve genişliğini `CRect`standartlaştırır.|
|[CRect::OfsetRect](#offsetrect)|Belirtilen `CRect` uzaklıklara göre hareket eder.|
|[CRect::PtInRect](#ptinrect)|Belirtilen noktanın içinde `CRect`olup olmadığını belirler.|
|[CRect::SetRect](#setrect)|`CRect`Boyutlarını ayarlar.|
|[CRect::SetRectEmpty](#setrectempty)|Boş `CRect` bir dikdörtgen (tüm koordinatlar 0'a eşit) ayarlar.|
|[CRect::Boyut](#size)|Boyutunu `CRect`hesaplar.|
|[CRect::ÇıkarmaRect](#subtractrect)|Bir dikdörtgeni diğerinden çıkarır.|
|[CRect::TopLeft](#topleft)|Sol üst noktasını döndürür. `CRect`|
|[CRect::UnionRect](#unionrect)|İki `CRect` dikdörtgenin birleşimine eşit ayarlar.|
|[CRect::Genişlik](#width)|'nin `CRect`genişliğini hesaplar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CRect::operatör -](#operator_-)|Verilen uzaklıkları çıkarır `CRect` veya söndürür `CRect` ve elde `CRect`edilen imiş arıyı döndürür.|
|[CRect::operatör LPCRECT](#operator_lpcrect)|A'yı `CRect` bir `LPCRECT`'e dönüştürür.|
|[CRect::operatör LPRECT](#operator_lprect)|A'yı `CRect` bir `LPRECT`'e dönüştürür.|
|[CRect::operatör !=](#operator_neq)|Dikdörtgenin `CRect` eşit olup olmadığını belirler.|
|[CRect::operatör&amp;](#operator_amp)|Kesişim `CRect` ve dikdörtgen oluşturur ve elde edilen. `CRect`|
|[CRect::operatör&amp;=](#operator_amp_eq)|Kesişim `CRect` `CRect` ve dikdörtgen eşit ayarlar.|
|[CRect::operatör &#124;](#operator_or)|Birleşim `CRect` ve bir dikdörtgen oluşturur ve elde `CRect`edilen.|
|[CRect::operatör &#124;=](#operator_or_eq)|Birleşim `CRect` `CRect` ve dikdörtgen eşit ayarlar.|
|[CRect::operatör +](#operator_add)|Verilen uzaklıkları `CRect` ekler veya `CRect` şişirir ve `CRect`elde edilen leri döndürür.|
|[CRect::operatör +=](#operator_add_eq)|Belirtilen uzaklıkları `CRect` ekler veya `CRect`şişirir.|
|[CRect::operatör =](#operator_eq)|Dikdörtgenin boyutlarını `CRect`kopyalar.|
|[CRect::operatör -=](#operator_-_eq)|Belirtilen uzaklıkları çıkarır `CRect` veya söndürür. `CRect`|
|[CRect::işleç ==](#operator_eq_eq)|Dikdörtgenin `CRect` eşit olup olmadığını belirler.|

## <a name="remarks"></a>Açıklamalar

`CRect``CRect` nesneleri ve Windows `RECT` yapılarını işlemek için üye işlevleri de içerir.

Bir `CRect` nesne, bir `RECT` yapının `LPCRECT`olduğu her yerde `LPRECT` işlev parametresi olarak geçirilebilir veya geçirilebilir.

> [!NOTE]
> Bu sınıf `tagRECT` yapıdan türetilmiştir. (Ad `tagRECT` `RECT` yapı için daha az kullanılan bir addır.) Bu, yapının`left` `top` `right` `bottom` `RECT` veri üyelerinin ( , , , ve `CRect`) erişilebilir veri üyeleri olduğu anlamına gelir.

A, `CRect` dikdörtgenin sol üst ve alt sağ noktalarını tanımlayan üye değişkenler içerir.

Bir `CRect`, normalleştirilmiş olması için inşa etmek için dikkatli olmalısınız — diğer bir deyişle, sol koordinatın değeri sağdan daha az, üst kısmı ise alttan daha azdır. Örneğin, (10,10) ve (20,20) sağ alt sol üst normalleştirilmiş bir dikdörtgen tanımlar, ancak üst sol (20,20) ve alt sağ (10,10) normalleştirilmiş olmayan bir dikdörtgen tanımlar. Dikdörtgen normalleştirilemezse, birçok `CRect` üye işlev yanlış sonuçlar döndürebilir. [(Bkz. CRect::Bu](#normalizerect) işlevlerin bir listesi için NormalizeRect.) Normalleştirilmiş dikdörtgenler gerektiren bir işlevi çağırmadan önce, `NormalizeRect` işlevi çağırarak normalleştirilmeyen dikdörtgenleri normalleştirebilirsiniz.

`CRect` [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) ve [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) üye işlevleri ile bir manipüle ederken dikkatli olun. Bir ekran bağlamının eşleme modu y-ölçüde negatif olacak `MM_LOENGLISH`şekilde `CDC::DPtoLP` ise, `CRect` o zaman üst alt daha büyük olacak şekilde dönüştürecektir. Dönüştürülmüş yükseklik `Height` `CRect` `Size` için negatif değerler döndürür ve bu tür işlevler döndürülür ve dikdörtgen normalleştirilmez.

Aşırı yüklü `CRect` operatörleri kullanırken, ilk operand olmalıdır; `CRect` ikincisi [bir RECT](/windows/win32/api/windef/ns-windef-rect) yapısı veya `CRect` bir nesne olabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagRECT`

`CRect`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltypes.h

## <a name="crectbottomright"></a><a name="bottomright"></a>CRect::BottomRight

Koordinatlar, 'de `CRect`bulunan bir [CPoint](cpoint-class.md) nesnesine başvuru olarak döndürülür.

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin sağ alt köşesinin koordinatları.

### <a name="remarks"></a>Açıklamalar

Dikdörtgenin sağ alt köşesini almak veya ayarlamak için bu işlevi kullanabilirsiniz. Atama işlecinin sol tarafında ki bu işlevi kullanarak köşeyi ayarlayın.

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

## <a name="crectcenterpoint"></a><a name="centerpoint"></a>CRect::CenterPoint

Sol ve sağ `CRect` değerleri ekleyerek ve ikiye bölerek, üst ve alt değerleri ekleyerek ve ikiye bölerek merkez noktasını hesaplar.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`'nin `CPoint` merkez noktası olan bir nesne

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

## <a name="crectcopyrect"></a><a name="copyrect"></a>CRect::CopyRect

Dikdörtgeni `lpSrcRect` `CRect`.

```cpp
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>Parametreler

*lpSrcRect*<br/>
[Kopyalanacak RECT](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` nesneye işaret ediyor.

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

## <a name="crectcrect"></a><a name="crect"></a>CRect::CRect

Bir `CRect` nesne inşa eder.

```
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();
```

### <a name="parameters"></a>Parametreler

*L*<br/>
'nin `CRect`sol konumunu belirtir.

*T*<br/>
Üst `CRect`belirtir.

*R*<br/>
Doğru konumu `CRect`belirtir.

*B*<br/>
Alt `CRect`belirtir.

*Srcrect*<br/>
Koordinatları ile [RECT](/windows/win32/api/windef/ns-windef-rect) yapısını ifade `CRect`eder.

*lpSrcRect*<br/>
Koordinatları `RECT` ile yapıyı işaret `CRect`eder.

*Nokta*<br/>
Dikdörtgenin oluşturulacak başlangıç noktasını belirtir. Sol üst köşeye karşılık gelir.

*Boyutu*<br/>
Yapılacak dikdörtgenin sol üst köşesinden sağ alt köşesine doğru yer değiştirmeyi belirtir.

*topLeft*<br/>
'nin `CRect`sol üst konumunu belirtir.

*bottomRight*<br/>
'nin `CRect`sağ alt konumunu belirtir.

### <a name="remarks"></a>Açıklamalar

Hiçbir bağımsız değişken `left`verilirse, , , `top` `right`, ve `bottom` üyeler başharfe harfle başharfe getirilmeyecektir.

( `CRect``const RECT&`) `CRect`ve`LPCRECT`( ) yapıcılar bir [CopyRect](#copyrect)gerçekleştirirler. Diğer kurucular nesnenin üye değişkenlerini doğrudan başharfe ait hale gelir.

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

## <a name="crectdeflaterect"></a><a name="deflaterect"></a>CRect::DeflateRect

`DeflateRect`kenarlarını `CRect` merkezine doğru hareket ettirerek söner.

```cpp
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>Parametreler

*X*<br/>
`CRect`'nin sol ve sağ taraflarını söndürmek için birim sayısını belirtir.

*Y*<br/>
`CRect`'nin üst ve alt kısmını söndürmek için birim sayısını belirtir.

*Boyutu*<br/>
Söndürülecek birim sayısını belirten bir [BOYUT](/windows/win32/api/windef/ns-windef-size) veya `CRect` [CSize.](csize-class.md) Değer, `cx` sol ve sağ tarafları söndürmek için birim `cy` sayısını belirtir ve değer üst ve alt yıkacak birim sayısını belirtir.

*Lprect*<br/>
[Bir RECT](/windows/win32/api/windef/ns-windef-rect) yapısına `CRect` veya her iki tarafı söndürmek için birim sayısını belirten noktalar.

*L*<br/>
`CRect`'nin sol tarafını söndürmek için birim sayısını belirtir.

*T*<br/>
Üst söndürmek için birim sayısını `CRect`belirtir.

*R*<br/>
Sağ tarafı söndürmek için birim sayısını `CRect`belirtir.

*B*<br/>
Alt deflate birim sayısını `CRect`belirtir.

### <a name="remarks"></a>Açıklamalar

Bunu yapmak `DeflateRect` için, sol ve üst birimleri ekler ve sağ ve alt birimleri çıkarır. İmzalanan `DeflateRect` değerlerin parametreleri; pozitif değerler `CRect` söndürülür ve negatif değerler onu şişirer.

İlk iki aşırı yük, toplam genişliği iki `CRect` kat *x* (veya) `cx`azalır ve toplam yüksekliği iki kat *y* (veya) `cy`azalır böylece zıt tarafların her iki çifti söndürülür. Diğer iki aşırı yükler diğerlerinden `CRect` bağımsız olarak her iki tarafı söndürülür.

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

## <a name="crectequalrect"></a><a name="equalrect"></a>CRect::EqualRect

Verilen dikdörtgenin eşit olup olmadığını `CRect` belirler.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
[Dikdörtgenin](/windows/win32/api/windef/ns-windef-rect) üst-sol `CRect` ve sağ alt köşe koordinatlarını içeren bir RECT yapısına veya nesneye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İki dikdörtgen aynı üst, sol, alt ve sağ değerlere sahipse sıfır sızma; aksi takdirde 0.

> [!NOTE]
> Dikdörtgenlerin her ikisi de normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgenleri normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

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

## <a name="crectheight"></a><a name="height"></a>CRect::Yükseklik

En üst değerden en üst değeri `CRect` çıkararak yüksekliği hesaplar.

```
int Height() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yüksekliği `CRect`.

### <a name="remarks"></a>Açıklamalar

Ortaya çıkan değer negatif olabilir.

> [!NOTE]
> Dikdörtgen normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgeni normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

## <a name="crectinflaterect"></a><a name="inflaterect"></a>CRect::ŞişirmeRect

`InflateRect`kenarlarını `CRect` merkezinden uzaklaştırarak şişirilir.

```cpp
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>Parametreler

*X*<br/>
'nin sol ve sağ taraflarını şişirmek için `CRect`birim sayısını belirtir.

*Y*<br/>
Üst ve alt şişirmek için birim sayısını `CRect`belirtir.

*Boyutu*<br/>
Şişirmek için birim sayısını belirten bir [BOYUT](/windows/win32/api/windef/ns-windef-size) veya `CRect` [CSize.](csize-class.md) Değer, `cx` sol ve sağ tarafları şişirmek için birim sayısını `cy` belirtir ve değer üst ve alt şişirmek için birim sayısını belirtir.

*Lprect*<br/>
[Bir RECT](/windows/win32/api/windef/ns-windef-rect) yapısına `CRect` veya her iki tarafı şişirecek birim sayısını belirten noktalar.

*L*<br/>
'nin sol tarafını şişirmek için birim sayısını `CRect`belirtir.

*T*<br/>
Üst şişirmek için birimlerin sayısını `CRect`belirtir.

*R*<br/>
Sağ tarafı şişirmek için birim sayısını `CRect`belirtir.

*B*<br/>
Alt şişirmek için birim sayısını `CRect`belirtir.

### <a name="remarks"></a>Açıklamalar

Bunu yapmak `InflateRect` için, birimleri soldan ve üstten çıkarır ve sağ ve alt birimler ekler. İmzalanan `InflateRect` değerlerin parametreleri; pozitif değerler şişirmek `CRect` ve negatif değerler söndürmek.

İlk iki aşırı yük, toplam genişliği iki `CRect` kat *x* (veya) `cx`artırılır ve toplam yüksekliği iki kat *y* (veya) `cy`artırılır, böylece zıt tarafların her iki çifti şişirmek. Diğer iki aşırı yükler diğerlerinden `CRect` bağımsız olarak her iki tarafı şişirmek.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

## <a name="crectintersectrect"></a><a name="intersectrect"></a>CRect::KesişmeRect

Varolan `CRect` iki dikdörtgenin kesişme sine eşit yapar.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRect1*<br/>
[Bir RECT](/windows/win32/api/windef/ns-windef-rect) yapısına `CRect` veya kaynak dikdörtgen içeren nesneye işaret edin.

*lpRect2*<br/>
Kaynak dikdörtgen `RECT` içeren `CRect` bir yapıveya nesneyi işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Kesişim boş değilse sıfırsız; Kavşak boşsa 0.

### <a name="remarks"></a>Açıklamalar

Kesişim, varolan her iki dikdörtgende de bulunan en büyük dikdörtgendir.

> [!NOTE]
> Dikdörtgenlerin her ikisi de normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgenleri normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

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

## <a name="crectisrectempty"></a><a name="isrectempty"></a>CRect::IsRectEmpty

Boş olup `CRect` olmadığını belirler.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Boşsa `CRect` sıfır olmayan; `CRect` Boş değilse 0.

### <a name="remarks"></a>Açıklamalar

Genişlik ve/veya yükseklik 0 veya negatifse dikdörtgen boştur. Dikdörtgenin `IsRectNull`tüm koordinatlarının sıfır olup olmadığını belirleyen, farklı olan.

> [!NOTE]
> Dikdörtgen normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgeni normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
ASSERT(rectEmpty.IsRectEmpty());
```

## <a name="crectisrectnull"></a><a name="isrectnull"></a>CRect::IsRectNull

Üst, sol, alt ve sağ değerlerinin `CRect` hepsinin 0'a eşit olup olmadığını belirler.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`'Üst, sol, alt ve sağ değerlerin tüm 0 eşitse sıfır; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Dikdörtgenin `IsRectEmpty`boş olup olmadığını belirleyen, farklı.

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

## <a name="crectmovetox"></a><a name="movetox"></a>CRect::MoveToX

Dikdörtgeni *x*tarafından belirtilen mutlak x koordinatına taşımak için bu işlevi çağırın.

```cpp
void MoveToX(int x) throw();
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Dikdörtgenin sol üst köşesi için mutlak x-koordinatı.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

// rect is now (10, 0, 110, 100);
ASSERT(rect == CRect(10, 0, 110, 100));
```

## <a name="crectmovetoxy"></a><a name="movetoxy"></a>CRect::MoveToXY

Dikdörtgeni belirtilen mutlak x- ve y koordinatlarına taşımak için bu işlevi çağırın.

```cpp
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Dikdörtgenin sol üst köşesi için mutlak x-koordinatı.

*Y*<br/>
Dikdörtgenin sol üst köşesi için mutlak y-koordinatı.

*Nokta*<br/>
Dikdörtgenin mutlak üst-sol köşesini belirten bir `POINT` yapı.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
ASSERT(rect == CRect(10, 10, 110, 110));
```

## <a name="crectmovetoy"></a><a name="movetoy"></a>CRect::MoveToY

Dikdörtgeni *y*tarafından belirtilen mutlak y-koordinatına taşımak için bu işlevi çağırın.

```cpp
void MoveToY(int y) throw();
```

### <a name="parameters"></a>Parametreler

*Y*<br/>
Dikdörtgenin sol üst köşesi için mutlak y-koordinatı.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
ASSERT(rect == CRect(0, 10, 100, 110));
```

## <a name="crectnormalizerect"></a><a name="normalizerect"></a>CRect::NormalizeRect

`CRect` Normalleştirir, böylece hem yükseklik hem de genişlik pozitiftir.

```cpp
void NormalizeRect() throw();
```

### <a name="remarks"></a>Açıklamalar

Dikdörtgen, Windows'un genellikle koordinatlar için kullandığı dördüncü dörtlü konumlandırma için normale döndürülmedir. `NormalizeRect`üst ve alt değerleri karşılaştırır ve üst alttan büyükse bunları değiştirir. Benzer şekilde, sol sağdan büyükse, sol ve sağ değerleri değiştirir. Bu işlev, farklı eşleme modları ve ters dikdörtgenler ile uğraşırken yararlıdır.

> [!NOTE]
> `CRect` Aşağıdaki üye işlevler düzgün çalışabilmek için normalleştirilmiş dikdörtgenler gerektirir: [Yükseklik](#height), [Genişlik](#width), [Boyut](#size), [IsRectEmpty](#isrectempty), [PtInRect](#ptinrect), EqualRect , [UnionRect](#unionrect), [IntersectRecrect](#intersectrect), [SubtractRect](#subtractrect), [operatör ==](#operator_eq_eq), [işleç !=](#operator_neq), [operatör &#124;](#operator_or), [işleç &#124;= ,](#operator_or_eq)operatör [&](#operator_amp), ve [operatör &=](#operator_amp_eq). [EqualRect](#equalrect)

### <a name="example"></a>Örnek

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

## <a name="crectoffsetrect"></a><a name="offsetrect"></a>CRect::OfsetRect

Belirtilen `CRect` uzaklıklara göre hareket eder.

```cpp
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Sola veya sağa hareket etmek için miktarı belirtir. Sola dönmek negatif olmalı.

*Y*<br/>
Yukarı veya aşağı hareket etmek için miktarı belirtir. Yükselmek negatif olmalı.

*Nokta*<br/>
Hareket etmek için her iki boyutu belirten bir [POINT](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi içerir.

*Boyutu*<br/>
Hareket etmek için her iki boyutu belirten bir [SIZE](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](csize-class.md) nesnesi içerir.

### <a name="remarks"></a>Açıklamalar

`CRect` *X* birimlerini x ekseni boyunca hareket ettirir ve *y-ekseni* boyunca y birimleri taşır. *X* ve *y* parametreleri imzalı `CRect` değerlerdir, bu nedenle sola veya sağa ve yukarı ya da aşağı hareket ettirilebilir.

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

## <a name="crectoperator-lpcrect-converts-a-crect-to-an-lpcrect"></a><a name="operator_lpcrect"></a>CRect::operatör LPCRECT bir `CRect` [LPCRECT](../../mfc/reference/data-types-mfc.md)a dönüştürür.

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullandığınızda, adres-of ( )**&** işleci gerekmez. Bu işleç, bir `CRect` nesneyi bir . `LPCRECT`

## <a name="crectoperator-lprect"></a><a name="operator_lprect"></a>CRect::operatör LPRECT

A'yı `CRect` [LPRECT'ye](../../mfc/reference/data-types-mfc.md)dönüştürür.

```
operator LPRECT() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullandığınızda, adres-of ( )**&** işleci gerekmez. Bu işleç, bir `CRect` nesneyi bir . `LPRECT`

### <a name="example"></a>Örnek

CRect örneğine [bakın:operatör LPCRECT](#operator_lpcrect).

## <a name="crectoperator-"></a><a name="operator_eq"></a>CRect::operatör =

*SrcRect'i* `CRect`.

```cpp
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>Parametreler

*Srcrect*<br/>
Kaynak dikdörtgeni ifade eder. [Bir RECT](/windows/win32/api/windef/ns-windef-rect) veya `CRect`olabilir .

### <a name="example"></a>Örnek

```cpp
CRect rect(0, 0, 127, 168);
CRect rect2;

rect2 = rect;
ASSERT(rect2 == CRect(0, 0, 127, 168));
```

## <a name="crectoperator-"></a><a name="operator_eq_eq"></a>CRect::işleç ==

Üst-sol `rect` ve `CRect` sağ alt köşelerinin koordinatlarını karşılaştırarak eşit olup olmadığını belirler.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Kaynak dikdörtgeni ifade eder. [Bir RECT](/windows/win32/api/windef/ns-windef-rect) veya `CRect`olabilir .

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız ise eşit; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Dikdörtgenlerin her ikisi de normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgenleri normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

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

## <a name="crectoperator-"></a><a name="operator_neq"></a>CRect::operatör !=

Üst-sol ve alt-sağ `CRect` köşelerinin koordinatlarını karşılaştırarak *rekt'in* eşit olup olmadığını belirler.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Kaynak dikdörtgeni ifade eder. [Bir RECT](/windows/win32/api/windef/ns-windef-rect) veya `CRect`olabilir .

### <a name="return-value"></a>Dönüş Değeri

Eşit değilse sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Dikdörtgenlerin her ikisi de normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgenleri normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

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

## <a name="crectoperator-"></a><a name="operator_add_eq"></a>CRect::operatör +=

İlk iki aşırı `CRect` yük, belirtilen uzaklıklarla hareket eder.

```cpp
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Dikdörtgeni hareket ettirecek birim sayısını belirten bir [POINT](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi.

*Boyutu*<br/>
Dikdörtgeni hareket ettirecek birim sayısını belirten [bir SIZE](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](csize-class.md) nesnesi.

*Lprect*<br/>
[Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya `CRect` nesnesinin her iki tarafını `CRect`şişirecek birim sayısını içeren bir nesneye işaret etmesi

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* `cx` (veya ve) `cy` `CRect`değerleri eklenir.

Üçüncü aşırı yük, `CRect` parametrenin her bir üyesinde belirtilen birim sayısına göre şişirir.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-_eq"></a>CRect::operatör -=

İlk iki aşırı `CRect` yük, belirtilen uzaklıklarla hareket eder.

```cpp
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Dikdörtgeni hareket ettirecek birim sayısını belirten bir [POINT](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi.

*Boyutu*<br/>
Dikdörtgeni hareket ettirecek birim sayısını belirten [bir SIZE](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](csize-class.md) nesnesi.

*Lprect*<br/>
[Bir RECT](/windows/win32/api/windef/ns-windef-rect) yapısına `CRect` veya nesnesinin her iki tarafını söndürecek birim sayısını içeren bir nesneye işaret `CRect`eder.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* `cx` (veya ve) `cy`değerleri `CRect`.

Üçüncü aşırı yük, `CRect` parametrenin her bir üyesinde belirtilen birim sayısına göre söner. [DeflateRect](#deflaterect)gibi bu aşırı yükleme fonksiyonları unutmayın.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp_eq"></a>CRect::operatör&amp;=

Kesişim `CRect` `CRect` ve `rect`.

```cpp
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) veya `CRect`.

### <a name="remarks"></a>Açıklamalar

Kesişim, her iki dikdörtgende de bulunan en büyük dikdörtgendir.

> [!NOTE]
> Dikdörtgenlerin her ikisi de normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgenleri normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

### <a name="example"></a>Örnek

CRect örneğine [bakın:IntersectRect](#intersectrect).

## <a name="crectoperator-124"></a><a name="operator_or_eq"></a>CRect::operatör &#124;=

Birliğe eşit `CRect` ayarlar `CRect` `rect`ve .

```cpp
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Bir `CRect` veya [RECT](/windows/win32/api/windef/ns-windef-rect)içerir.

### <a name="remarks"></a>Açıklamalar

Birleşim, her iki kaynak dikdörtgeni de içeren en küçük dikdörtgendir.

> [!NOTE]
> Dikdörtgenlerin her ikisi de normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgenleri normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);

rect1 |= rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect1);
```

## <a name="crectoperator-"></a><a name="operator_add"></a>CRect::operatör +

İlk iki aşırı yük, belirtilen uzaklıklar tarafından `CRect` `CRect` yerinden eşit bir nesne döndürer.

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
İade değerini taşımak için birim sayısını belirten bir [POINT](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint](cpoint-class.md) nesnesi.

*Boyutu*<br/>
İade değerini taşımak için birim sayısını belirten bir [SIZE](/windows/win32/api/windef/ns-windef-size) yapısı veya [CSize](csize-class.md) nesnesi.

*Lprect*<br/>
İade değerinin her iki `CRect` tarafını şişirecek birim sayısını içeren bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına veya nesneye işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Parametrede belirtilen birim sayısına göre hareket veya şişirme `CRect` `CRect` sonucu.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* `cx` (veya ve) `cy` `CRect`parametreleri 'nin konumuna eklenir.

Üçüncü aşırı yük, `CRect` parametrenin `CRect` her üyesinde belirtilen birim sayısına eşit yeni bir yeni döndürür.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 + pt;
CRect   rectResult(135, 300, 235, 400);
ASSERT(rectResult == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-"></a>CRect::operatör -

İlk iki aşırı yük, belirtilen uzaklıklar tarafından `CRect` `CRect` yerinden eşit bir nesne döndürer.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
İade [POINT](/windows/win32/api/windef/ns-windef-point) değerini `CPoint` taşımak için birim sayısını belirten bir POINT yapısı veya nesnesi.

*Boyutu*<br/>
İade değerini `CSize` taşımak için birim sayısını belirten bir [SIZE](/windows/win32/api/windef/ns-windef-size) yapısı veya nesnesi.

*Lprect*<br/>
İade değerinin her iki `CRect` tarafını söndürecek birim sayısını içeren bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına veya nesneye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Parametrede belirtilen birim sayısına `CRect` `CRect` göre hareket veya söndürme sonucu ortaya çıkan.

### <a name="remarks"></a>Açıklamalar

Parametrenin *x* ve *y* `cx` (veya ve) `cy`parametreleri `CRect`'nin konumundan çıkarılır.

Üçüncü aşırı yük, `CRect` parametrenin `CRect` her üyesinde belirtilen birim sayısına eşit bir yeni döndürür. [DeflateRect](#deflaterect)gibi bu aşırı yükleme fonksiyonları , [Değil SubtractRect](#subtractrect).

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp"></a>CRect::operatör&amp;

Bir `CRect` kesişim `CRect` ve *rect2*verir.

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>Parametreler

*rekt2*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) veya `CRect`.

### <a name="return-value"></a>Dönüş Değeri

A `CRect` bu kesişim `CRect` ve *rect2*olduğunu .

### <a name="remarks"></a>Açıklamalar

Kesişim, her iki dikdörtgende de bulunan en büyük dikdörtgendir.

> [!NOTE]
> Dikdörtgenlerin her ikisi de normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgenleri normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 & rect2;
CRect   rectResult(100, 100, 200, 200);
ASSERT(rectResult == rect3);
```

## <a name="crectoperator-124"></a><a name="operator_or"></a>CRect::operatör &#124;

Bir `CRect` birleşimi `CRect` ve *rect2*verir.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>Parametreler

*rekt2*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) veya `CRect`.

### <a name="return-value"></a>Dönüş Değeri

A `CRect` bu birlik `CRect` ve *rect2*.

### <a name="remarks"></a>Açıklamalar

Birleşim, her iki dikdörtgeni de içeren en küçük dikdörtgendir.

> [!NOTE]
> Dikdörtgenlerin her ikisi de normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgenleri normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 | rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectptinrect"></a><a name="ptinrect"></a>CRect::PtInRect

Belirtilen noktanın içinde `CRect`olup olmadığını belirler.

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
[Point](/windows/win32/api/windef/ns-windef-point) yapısı veya [CPoint nesnesi](cpoint-class.md) içerir.

### <a name="return-value"></a>Dönüş Değeri

Nokta içinde `CRect`yatıyorsa nonzero ; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nokta, `CRect` sol veya üst tarafta veya dört tarafın içinde yatıyorsa içindedir. Sağ veya alt tarafta bir `CRect`nokta dışındadır.

> [!NOTE]
> Dikdörtgen normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgeni normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

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

## <a name="crectsetrect"></a><a name="setrect"></a>CRect::SetRect

Boyutlarını belirtilen `CRect` koordinatlara ayarlar.

```cpp
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Sol üst köşenin x-koordinatını belirtir.

*y1*<br/>
Sol üst köşenin y-koordinatını belirtir.

*x2*<br/>
Sağ alt köşenin x-koordinatını belirtir.

*y2*<br/>
Sağ alt köşenin y-koordinatını belirtir.

### <a name="example"></a>Örnek

```cpp
CRect rect;
rect.SetRect(256, 256, 512, 512);
ASSERT(rect == CRect(256, 256, 512, 512));
```

## <a name="crectsetrectempty"></a><a name="setrectempty"></a>CRect::SetRectEmpty

Tüm `CRect` koordinatları sıfıra ayarlayarak null dikdörtgen yapar.

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

## <a name="crectsize"></a><a name="size"></a>CRect::BOYUT

İade `cx` `cy` değerinin ve üyeleri. `CRect`

```
CSize Size() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Boyut boyutunu içeren bir [CSize](csize-class.md) nesnesi `CRect`

### <a name="remarks"></a>Açıklamalar

Yükseklik veya genişlik negatif olabilir.

> [!NOTE]
> Dikdörtgen normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgeni normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

## <a name="crectsubtractrect"></a><a name="subtractrect"></a>CRect::ÇıkarmaRect

Çıkarma dan çıkarma `CRect` `lpRectSrc2` eşit boyutları `lpRectSrc1`yapar.

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRectSrc1*<br/>
[Dikdörtgenin](/windows/win32/api/windef/ns-windef-rect) çıkarılabilmek `CRect` için RECT yapısına veya nesneye işaret edilir.

*lpRectSrc2*<br/>
`RECT` *lpRectSrc1* parametresi tarafından işaret edilen dikdörtgenden çıkarılacak yapı veya `CRect` nesneye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çıkarma *lpRectScr1* ve *lpRectScr2*kesiştiği olmayan *lpRectScr1* tüm noktaları içeren en küçük dikdörtgendir.

*lpRectSrc2* tarafından belirtilen dikdörtgen, *lpRectSrc1* tarafından x veya y-yönlerden en az birinde belirtilen dikdörtgenle tamamen örtüşmüyorsa, *lpRectSrc1* tarafından belirtilen dikdörtgen değişmez.

Örneğin, *lpRectSrc1* (10,10, 100,100) ve *lpRectSrc2* (50,50, 150,150) olsaydı, *lpRectSrc1* tarafından işaret edilen dikdörtgen işlev döndürüldüğünde değişmezdi. *LpRectSrc1* (10,10, 100,100) ve *lpRectSrc2* (50,10, 150,150) olsaydı, *lpRectSrc1* tarafından işaret edilen dikdörtgen, işlev geri döndüğünde koordinatları (10,10, 50,100) içerecektir.

`SubtractRect`[işleci](#operator_-) ile aynı değildir - ne de [operatör -=](#operator_-_eq). Bu operatörlerin hiçbiri `SubtractRect`hiç çağırır .

> [!NOTE]
> Dikdörtgenlerin her ikisi de normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgenleri normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

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

## <a name="crecttopleft"></a><a name="topleft"></a>CRect::TopLeft

Koordinatlar, 'de `CRect`bulunan bir [CPoint](cpoint-class.md) nesnesine başvuru olarak döndürülür.

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin sol üst köşesinin koordinatları.

### <a name="remarks"></a>Açıklamalar

Dikdörtgenin sol üst köşesini almak veya ayarlamak için bu işlevi kullanabilirsiniz. Atama işlecinin sol tarafında ki bu işlevi kullanarak köşeyi ayarlayın.

### <a name="example"></a>Örnek

CRect örneğine [bakın:CenterPoint](#centerpoint).

## <a name="crectunionrect"></a><a name="unionrect"></a>CRect::UnionRect

İki kaynak `CRect` dikdörtgenin birleşimine eşit boyutlar yapar.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parametreler

*lpRect1*<br/>
[Bir RECT'ye](/windows/win32/api/windef/ns-windef-rect) `CRect` veya kaynak dikdörtgeniçerene işaret edin.

*lpRect2*<br/>
Kaynak dikdörtgen `RECT` `CRect` içeren veya bir işaret eden nokta.

### <a name="return-value"></a>Dönüş Değeri

Birlik boş değilse sıfırsız; Sendika boşsa 0.

### <a name="remarks"></a>Açıklamalar

Birleşim, her iki kaynak dikdörtgeni de içeren en küçük dikdörtgendir.

Windows boş bir dikdörtgenin boyutlarını yok sayar; diğer bir şey, yüksekliği olmayan veya genişliği olmayan bir dikdörtgendir.

> [!NOTE]
> Dikdörtgenlerin her ikisi de normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgenleri normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

### <a name="example"></a>Örnek

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3.UnionRect(&rect1, &rect2);
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectwidth"></a><a name="width"></a>CRect::Genişlik

Sol değeri sağ `CRect` değerden çıkararak genişliğini hesaplar.

```
int Width() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`Genişliği.

### <a name="remarks"></a>Açıklamalar

Genişlik negatif olabilir.

> [!NOTE]
> Dikdörtgen normalleştirilmelidir veya bu işlev başarısız olabilir. Bu işlevi aramadan önce dikdörtgeni normalleştirmek için [NormalizeRect'i](#normalizerect) arayabilirsiniz.

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
[Rect](/windows/win32/api/windef/ns-windef-rect)
