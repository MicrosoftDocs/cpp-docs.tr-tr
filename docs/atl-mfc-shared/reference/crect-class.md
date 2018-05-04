---
title: CRect sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a819cfc95588dc9225570a82b8a359d90a8f6b9f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="crect-class"></a>CRect sınıfı
Benzer şekilde bir Windows [RECT](../../mfc/reference/rect-structure1.md) yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CRect : public tagRECT  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRect::CRect](#crect)|Oluşturan bir `CRect` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRect::BottomRight](#bottomright)|Sağ alt noktası döndürür `CRect`.|  
|[CRect::CenterPoint](#centerpoint)|Centerpoint döndürür `CRect`.|  
|[CRect::CopyRect](#copyrect)|Kaynak dikdörtgen boyutlarını kopyalar `CRect`.|  
|[CRect::DeflateRect](#deflaterect)|Genişlik ve yüksekliğini azaltır `CRect`.|  
|[CRect::EqualRect](#equalrect)|Belirler olup olmadığını `CRect` verilen dikdörtgenin eşittir.|  
|[CRect::Height](#height)|Yüksekliğini hesaplar `CRect`.|  
|[CRect::InflateRect](#inflaterect)|Yüksekliğini ve genişliğini artırır `CRect`.|  
|[CRect::IntersectRect](#intersectrect)|Ayarlar `CRect` iki dikdörtgen kesişimi eşittir.|  
|[CRect::IsRectEmpty](#isrectempty)|Belirler olup olmadığını `CRect` boş. `CRect` Genişlik ve/veya yüksekliği 0 ise boştur.|  
|[CRect::IsRectNull](#isrectnull)|Belirler olup olmadığını **üst**, **alt**, **sol**, ve **sağ** üye değişkenleri tüm 0'a eşit.|  
|[CRect::MoveToX](#movetox)|Taşır `CRect` için belirtilen x koordinatı.|  
|[CRect::MoveToXY](#movetoxy)|Taşır `CRect` için belirlenen x ve y-koordinatlarının.|  
|[CRect::MoveToY](#movetoy)|Taşır `CRect` için belirtilen y koordinatı.|  
|[CRect::NormalizeRect](#normalizerect)|Yüksekliğini ve genişliğini standartlaştıran `CRect`.|  
|[CRect::OffsetRect](#offsetrect)|Taşır `CRect` tarafından belirtilen uzaklık.|  
|[CRect::PtInRect](#ptinrect)|Belirtilen nokta içinde kaynaklandığını olup olmadığını belirler `CRect`.|  
|[CRect::SetRect](#setrect)|Boyutlarını ayarlar `CRect`.|  
|[CRect::SetRectEmpty](#setrectempty)|Ayarlar `CRect` (tüm koordinatların eşit 0) boş bir dikdörtgen için.|  
|[CRect::Size](#size)|Boyutunu hesaplar `CRect`.|  
|[CRect::SubtractRect](#subtractrect)|Başka bir bir dikdörtgen çıkarır.|  
|[CRect::TopLeft](#topleft)|Sol üst noktası döndürür `CRect`.|  
|[CRect::UnionRect](#unionrect)|Ayarlar `CRect` iki dikdörtgen birleşimi eşittir.|  
|[CRect::Width](#width)|Genişliğini hesaplar `CRect`.|  
  
### <a name="public-operators"></a>Ortak İşleçler    
|Ad|Açıklama|  
|----------|-----------------|  
|[CRect::operator-](#operator_-)|Öğesinden belirtilen uzaklıkları çıkarır `CRect` veya Söndür `CRect` ve elde edilen döndürür `CRect`.|  
|[CRect::operator LPCRECT](#operator_lpcrect)|Dönüştüren bir `CRect` için bir **LPCRECT**.|  
|[CRect::operator LPRECT](#operator_lprect)|Dönüştüren bir `CRect` için bir `LPRECT`.|  
|[CRect::operator! =](#operator_neq)|Belirler olup olmadığını `CRect` dikdörtgen eşit değil.|  
|[CRect::operator &amp;](#operator_amp)|Kesişimi oluşturur `CRect` ve bir dikdörtgen ve elde edilen döndürür `CRect`.|  
|[CRect::operator &amp;=](#operator_amp_eq)|Ayarlar `CRect` kesişimi eşit `CRect` ve bir dikdörtgen.|  
|[CRect::operator |](#operator_or)|Birleşimini oluşturur `CRect` ve bir dikdörtgen ve elde edilen döndürür `CRect`.|  
|[CRect::operator |=](#operator_or_eq)|Ayarlar `CRect` birleşimi eşit `CRect` ve bir dikdörtgen.|  
|[CRect::operator +](#operator_add)|Verilen uzaklıkları ekler `CRect` veya Şişir `CRect` ve elde edilen döndürür `CRect`.|  
|[CRect::operator +=](#operator_add_eq)|Belirtilen uzaklık ekler `CRect` veya Şişir `CRect`.|  
|[CRect::operator =](#operator_eq)|Dikdörtgen boyutlarını kopyalar `CRect`.|  
|[CRect::operator-=](#operator_-_eq)|Öğesinden belirtilen uzaklıkları çıkarır `CRect` veya Söndür `CRect`.|  
|[CRect::operator ==](#operator_eq_eq)|Belirler olup olmadığını `CRect` dikdörtgen eşittir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CRect` Ayrıca işlemek için üye işlevlerini içerir `CRect` nesneleri ve Windows `RECT` yapıları.  
  
 A `CRect` nesne işlevi parametre olarak geçirilebilir her yerde bir `RECT` yapısı, **LPCRECT**, veya `LPRECT` geçirilebilir.  
  
> [!NOTE]
>  Bu sınıfın türetildiği **tagRECT** yapısı. (Adı **tagRECT** için daha az yaygın olarak kullanılan bir ad `RECT` yapısı.) Veri üyeleri buna (**sol**, **üst**, **sağ**, ve **alt**), `RECT` olan erişilebilir veri yapısı üyeleri `CRect`.  
  
 A `CRect` dikdörtgenin sol üst ve sağ alt noktaları tanımlamak üye değişkenleri içerir.  
  
 Belirtirken bir `CRect`, böylece bu normalleştirilmiş oluşturmak dikkatli olmanız gerekir — sol koordinat değerini sağa ve en az olacak şekilde, diğer bir deyişle, alt küçüktür. Örneğin, top (10,10) sol ve sağ alt köşesindeki (20,20) normalleştirilmiş dikdörtgen tanımlar ancak (20,20) bir üst sol ve sağ alt köşesindeki (10,10) Normalleştirilmemiş bir dikdörtgen tanımlar. Dikdörtgen Normalleştirilmemiş, birçok `CRect` üye işlevleri hatalı sonuçlar döndürebilir. (Bkz [CRect::NormalizeRect](#normalizerect) bu işlevlerin listesi için.) Normalleştirilmiş dikdörtgenler gerektiren bir işlev çağırmadan önce çağırarak Normalleştirilmemiş dikdörtgenler normalleştirmek `NormalizeRect` işlevi.  
  
 Değiştirirken dikkatli bir `CRect` ile [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) ve [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) üye işlevleri. Y-ölçüde negatif olarak olacak şekilde, bir görüntü bağlamı eşleme modunu olup olmadığını `MM_LOENGLISH`, ardından `CDC::DPtoLP` dönüştüren `CRect` kendi üst alt büyük olmasını sağlayın. Gibi işlevleri **yükseklik** ve **boyutu** sonra dönüştürülmüş yüksekliği için negatif değerler döndürülecek `CRect`, ve dikdörtgen Normalleştirilmemiş olacaktır.  

  
 Ne zaman kullanarak aşırı `CRect` işleçleri, ilk işlenen olmalıdır bir `CRect`; ikinci ya da olabilir bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` nesnesi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `tagRECT`  
  
 `CRect`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atltypes.h  
  
##  <a name="bottomright"></a>  CRect::BottomRight  
 Bir başvuru olarak koordinatları döndürülen bir [CPoint](cpoint-class.md) bulunan nesne `CRect`.  
  
```  
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dikdörtgen sağ alt köşesindeki koordinatları.  
  
### <a name="remarks"></a>Açıklamalar  
 Almak veya dikdörtgen sağ alt köşesindeki ayarlamak için bu işlevi kullanabilirsiniz. Köşe atama işlecinin sol tarafındaki bu işlevi kullanarak ayarlayın.  
  
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
 Centerpoint, hesaplar `CRect` sol ve sağ değerlerin ekleme ve iki tarafından bölme ve üst ve alt değerleri ekleyerek ve iki göre bölme.  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CPoint` centerpoint, nesne `CRect`.  
  
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
 Kopya `lpSrcRect` dikdörtgen `CRect`.  
  
```  
void CopyRect(LPCRECT lpSrcRect) throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 `lpSrcRect`  
 İşaret [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` kopyalanacak nesne.  
  
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
 Oluşturan bir `CRect` nesnesi.  
  
```  
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *m*  
 Sol konumunu belirtir `CRect`.  
  
 *T*  
 Üst belirtir `CRect`.  
  
 *r*  
 Sağ konumunu belirtir `CRect`.  
  
 *b*  
 Alt belirtir `CRect`.  
  
 *srcRect*  
 Başvurduğu [RECT](../../mfc/reference/rect-structure1.md) koordinatlarını yapısıyla `CRect`.  
  
 `lpSrcRect`  
 İşaret `RECT` koordinatlarını yapısıyla `CRect`.  
  
 `point`  
 Dikdörtgen oluşturulması için başlangıç noktasını belirler. Sol üst köşede karşılık gelir.  
  
 `size`  
 Sol üst köşeden oluşturulması için dikdörtgenin öteleme sağ alt köşe için belirtir.  
  
 *Sol üst*  
 Sol üst konumunu belirtir `CRect`.  
  
 *bottomRight*  
 Sağ alt konumunu belirtir `CRect`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişkenler verilirse, **sol**, **üst**, **sağ**, ve **alt** üyeleri başlatılmadı.  
  
 `CRect`(**Const RECT &**) ve `CRect`(**LPCRECT**) oluşturucular gerçekleştirmek bir [CopyRect](#copyrect). Diğer oluşturucular nesnenin üye değişkenleri doğrudan başlatır.  
  
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
 `DeflateRect` Söndür `CRect` kendi merkezine kendi kenara taşıyarak.  
  
```  
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Sol deflate birim sayısını ve sağ kenarlarının belirtir `CRect`.  
  
 *Y*  
 Üst ve alt deflate birim sayısını belirtir `CRect`.  
  
 `size`  
 A [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) veya [CSize](csize-class.md) deflate birim sayısını belirtir `CRect`. `cx` Değerini belirtir ve sol tarafında deflate birim sayısını ve `cy` değeri üst ve alt deflate birim sayısını belirtir.  
  
 `lpRect`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` her iki yanına deflate birim sayısını belirtir.  
  
 *m*  
 Sol tarafındaki deflate birim sayısını belirtir `CRect`.  
  
 *T*  
 Üst deflate birim sayısını belirtir `CRect`.  
  
 *r*  
 Sağ tarafındaki deflate birim sayısını belirtir `CRect`.  
  
 *b*  
 Alt deflate birim sayısını belirtir `CRect`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bunu yapmak için `DeflateRect` üst ve sol birimleri ekler ve alt ve sağ birimlerinden çıkarır. Parametreleri `DeflateRect` imzalanmış değerleri; deflate pozitif değerler `CRect` ve negatif değerler Şişir.  
  
 İlk iki aşırı hem çiftleri ters tarafının deflate `CRect` toplam eni tarafından iki kez azalır böylece *x* (veya `cx`) ve toplam yüksekliği tarafından iki kez azalır *y* ( veya `cy`). Her iki tarafındaki diğer iki aşırı deflate `CRect` diğer bağımsız olarak.  
  
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
 Belirler olup olmadığını `CRect` verilen dikdörtgenin eşittir.  
  
```  
BOOL EqualRect(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` dikdörtgen sol üst ve sağ alt köşe koordinatlarını içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İki dikdörtgen aynı üst, sol, alt ve sağ değerlerin varsa sıfır olmayan; Aksi takdirde 0.  
  
> [!NOTE]
>  Her iki dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgenler normalleştirmek için.  
  
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
 Yüksekliğini hesaplar `CRect` alt değerden üst değer çıkarılmasıyla tarafından.  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yüksekliğini `CRect`.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuç değeri negatif olabilir.  
  
> [!NOTE]
>  Dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgen normalleştirmek için.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect(20, 30, 80, 70);
 int nHt = rect.Height();

```cpp  
   CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

   // nHt is now 40
   ASSERT(nHt == 40);   
```

  
##  <a name="inflaterect"></a>  CRect::InflateRect  
 `InflateRect` Şişir `CRect` kendi merkezinden kendi kenara taşıyarak.  
  
```  
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Sol Şişir birim sayısını ve sağ kenarlarının belirtir `CRect`.  
  
 *Y*  
 Üst ve alt Şişir birim sayısını belirtir `CRect`.  
  
 `size`  
 A [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) veya [CSize](csize-class.md) Şişir birim sayısını belirtir `CRect`. `cx` Değerini belirtir ve sol tarafında Şişir birim sayısını ve `cy` değeri üst ve alt Şişir birim sayısını belirtir.  
  
 `lpRect`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` her iki yanına Şişir birim sayısını belirtir.  
  
 *m*  
 Sol tarafındaki Şişir birim sayısını belirtir `CRect`.  
  
 *T*  
 Üst Şişir birim sayısını belirtir `CRect`.  
  
 *r*  
 Sağ tarafındaki Şişir birim sayısını belirtir `CRect`.  
  
 *b*  
 Alt Şişir birim sayısını belirtir `CRect`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bunu yapmak için `InflateRect` üst ve sol birimlerinden çıkarır ve sağ ve alt birimleri ekler. Parametreleri `InflateRect` imzalanmış değerleri; değerleri Şişir pozitif `CRect` ve negatif değerler deflate.  
  
 İlk iki aşırı hem çiftleri ters tarafının Şişir `CRect` toplam eni tarafından iki kez artırılır böylece *x* (veya `cx`) ve toplam yüksekliği iki kat daha fazla *y* ( veya `cy`). Her iki tarafındaki diğer iki aşırı Şişir `CRect` diğer bağımsız olarak.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect(0, 0, 300, 300);
 rect.InflateRect(50, 200);

 // rect is now (-50, -200, 350, 500)
 ASSERT(rect == CRect(-50, -200, 350, 500));  
```
  
##  <a name="intersectrect"></a>  CRect::IntersectRect  
 Yapar bir `CRect` var olan iki dikdörtgen kesişimi eşittir.  
  
```  
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect1`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` kaynak dikdörtgen içeren nesne.  
  
 `lpRect2`  
 İşaret eden bir `RECT` yapısı veya `CRect` kaynak dikdörtgen içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kesişimi boş değilse, sıfır olmayan; kesişimi boşsa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kesişimi içinde varolan her iki dikdörtgen bulunan büyük dikdörtgen ' dir.  
  
> [!NOTE]
>  Her iki dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgenler normalleştirmek için.  
  
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
 Belirler olup olmadığını `CRect` boş.  
  
```  
BOOL IsRectEmpty() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CRect` olan boş; 0 ise `CRect` boş değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Dikdörtgene genişlik ve/veya yüksekliği 0 ise boş veya negatif değil. Farklı `IsRectNull`, tüm koordinatların dikdörtgenin sıfır olup olmadığını belirler.  
  
> [!NOTE]
>  Dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgen normalleştirmek için.  
  
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
 , Sol üst, alt olup olmadığını, belirler ve sağ değerlerini `CRect` tüm 0'a eşit.  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CRect`kullanıcının, sol üst, alt ve sağ değerlerin tüm 0 değerine eşit; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Farklı `IsRectEmpty`, dikdörtgen boş olup olmadığını belirler.  
  
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
 Dikdörtgen tarafından belirtilen mutlak x koordinatı taşımak için bu işlevi çağırmak *x*.  
  
```  
void MoveToX(int x) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Mutlak x koordinatını dikdörtgenin sol üst köşe için.  
  
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
 Mutlak x ve y-belirtilen koordinatları için dikdörtgen taşımak için bu işlevini çağırın.  
  
```  
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Mutlak x koordinatını dikdörtgenin sol üst köşe için.  
  
 *Y*  
 Mutlak y koordinatını dikdörtgenin sol üst köşe için.  
  
 `point`  
 A **noktası** yapısı dikdörtgen mutlak sol üst köşesindeki belirtme.  
  
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
 Dikdörtgen tarafından belirtilen mutlak y koordinatını taşımak için bu işlevi çağırmak *y*.  
  
```  
void MoveToY(int y) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *Y*  
 Mutlak y koordinatını dikdörtgenin sol üst köşe için.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToY(10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
   ASSERT(rect == CRect(0, 10, 100, 110));   
```

  
##  <a name="normalizerect"></a>  CRect::NormalizeRect  
 Normalleştirir `CRect` yükseklik ve genişlik pozitif; böylece.  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dikdörtgen dördüncü çeyrekli konumlandırma için Windows genellikle koordinatları kullanan normalleştirilmiş. `NormalizeRect` üst ve alt değerlerini karşılaştırır ve üst alt büyükse, bunları değiştirir. Benzer şekilde, soldan sağa büyükse, sol ve sağ değerlerin değiştirir. Bu işlev, farklı eşleme modlarıyla ilgilenirken yararlıdır ve dikdörtgenler ters.  
  
> [!NOTE]
>  Aşağıdaki `CRect` üye işlevleri düzgün çalışması için normalleştirilmiş dikdörtgenler gerektirir: [yükseklik](#height), [genişliği](#width), [boyutu](#size), [ IsRectEmpty](#isrectempty), [PtInRect](#ptinrect), [EqualRect](#equalrect), [UnionRect](#unionrect), [IntersectRect](#intersectrect), [ SubtractRect](#subtractrect), [işleç ==](#operator_eq_eq), [işleç! =](#operator_neq), [işleci &#124; ](#operator_or), [işleci &#124;=](#operator_or_eq), [işleci &](#operator_amp), ve [işleci & =](#operator_amp_eq).  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect1(110, 100, 250, 310);
 CRect rect2(250, 310, 110, 100);

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
 *x*  
 Sol taşımak için veya sağa belirtir. Sola Taşı negatif olmalıdır.  
  
 *Y*  
 Yukarı veya aşağı gitme belirtir. Yukarı Taşı negatif olmalıdır.  
  
 `point`  
 İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](cpoint-class.md) nesne taşımak, her iki boyutları belirleme.  
  
 `size`  
 İçeren bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](csize-class.md) nesne taşımak, her iki boyutları belirleme.  
  
### <a name="remarks"></a>Açıklamalar  
 Taşır `CRect` *x* birim x ekseni boyunca ve *y* birim y ekseni boyunca. *x* ve *y* parametreleridir imzalı değerler, bu nedenle `CRect` sol taşınabilir sağ ve yukarı veya aşağı.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect(0, 0, 35, 35);
 rect.OffsetRect(230, 230);

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
 Bu işlev kullandığınızda, adresini, gerekmez (**&**) işleci. Bu işleç, geçirdiğiniz olduğunda otomatik olarak kullanılacak bir `CRect` bekliyor işlevi nesnesine bir **LPCRECT**.  
  

##  <a name="operator_lprect"></a>  CRect::operator LPRECT  
 Dönüştüren bir `CRect` için bir [LPRECT](../../mfc/reference/data-types-mfc.md).  

  
```
operator LPRECT() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev kullandığınızda, adresini, gerekmez (**&**) işleci. Bu işleç, geçirdiğiniz olduğunda otomatik olarak kullanılacak bir `CRect` bekliyor işlevi nesnesine bir `LPRECT`.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CRect::operator LPCRECT](#operator_lpcrect).  
  
##  <a name="operator_eq"></a>  CRect::operator =  
 Atar *srcRect* için `CRect`.  
  
```  
void operator=(const RECT& srcRect) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *srcRect*  
 Kaynak dikdörtgen başvuruyor. Olabilir bir [RECT](../../mfc/reference/rect-structure1.md) veya `CRect`.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect(0, 0, 127, 168);
 CRect rect2;

```cpp  
   CRect rect(0, 0, 127, 168);
   CRect rect2;

   rect2 = rect;
   ASSERT(rect2 == CRect(0, 0, 127, 168));   
```

  
##  <a name="operator_eq_eq"></a>  CRect::operator ==  
 Belirler olup olmadığını `rect` eşittir `CRect` karşılaştırarak, sol üst ve sağ alt köşe koordinatları.  
  
```  
BOOL operator==(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Kaynak dikdörtgen başvuruyor. Olabilir bir [RECT](../../mfc/reference/rect-structure1.md) veya `CRect`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşit değilse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Her iki dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgenler normalleştirmek için.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect1(35, 150, 10, 25);
 CRect rect2(35, 150, 10, 25);
 CRect rect3(98, 999,  6,  3);

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
 Belirler olup olmadığını `rect` eşit değil `CRect` karşılaştırarak, sol üst ve sağ alt köşe koordinatları.  
  
```  
BOOL operator!=(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Kaynak dikdörtgen başvuruyor. Olabilir bir [RECT](../../mfc/reference/rect-structure1.md) veya `CRect`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşit değil, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Her iki dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgenler normalleştirmek için.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect1(35, 150, 10, 25);
 CRect rect2(35, 150, 10, 25);
 CRect rect3(98, 999,  6,  3);

```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
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
 `point`  
 A [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](cpoint-class.md) nesne dikdörtgeni taşımak için kullanılacak birim sayısını belirtir.  
  
 `size`  
 A [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](csize-class.md) nesne dikdörtgeni taşımak için kullanılacak birim sayısını belirtir.  
  
 `lpRect`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` her iki tarafındaki Şişir birim sayısını içeren nesne `CRect`.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametrenin *x* ve *y* (veya `cx` ve `cy`) değerleri eklenir `CRect`.  
  
 Üçüncü aşırı Şişir `CRect` birimleri belirtilen her bir üyesi parametre sayısı.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect1(100, 235, 200, 335);
 CPoint pt(35, 65);
 CRect rect2(135, 300, 235, 400);

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
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
 `point`  
 A [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](cpoint-class.md) nesne dikdörtgeni taşımak için kullanılacak birim sayısını belirtir.  
  
 `size`  
 A [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](csize-class.md) nesne dikdörtgeni taşımak için kullanılacak birim sayısını belirtir.  
  
 `lpRect`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` her iki tarafındaki deflate birim sayısını içeren nesne `CRect`.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametrenin *x* ve *y* (veya `cx` ve `cy`) değerleri çıkarılır `CRect`.  
  
 Üçüncü aşırı Söndür `CRect` birimleri belirtilen her bir üyesi parametre sayısı. Bu aşırı gibi işlevleri Not [DeflateRect](#deflaterect).  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect1(100, 235, 200, 335);
 CPoint pt(35, 65);
 rect1 -= pt;

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);

   rect1 -= pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect1 == rectResult);   
```
  
##  <a name="operator_amp_eq"></a>  CRect::operator &amp;=  
 Ayarlar `CRect` kesişimi eşit `CRect` ve `rect`.  
  
```  
void operator&=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 İçeren bir [RECT](../../mfc/reference/rect-structure1.md) veya `CRect`.  
  
### <a name="remarks"></a>Açıklamalar  
 Her iki dikdörtgen bulunan büyük dikdörtgen kesişimi olur.  
  
> [!NOTE]
>  Her iki dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgenler normalleştirmek için.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CRect::IntersectRect](#intersectrect).  
  
##  <a name="operator_or_eq"></a>  CRect::operator &#124;=  
 Ayarlar `CRect` birleşimi eşit `CRect` ve `rect`.  
  
```  
void operator|=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 İçeren bir `CRect` veya [RECT](../../mfc/reference/rect-structure1.md).  
  
### <a name="remarks"></a>Açıklamalar  
 UNION hem kaynak dikdörtgenler içeren en küçük dikdörtgen ' dir.  
  
> [!NOTE]
>  Her iki dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgenler normalleştirmek için.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect1(100,   0, 200, 300);
 CRect rect2( 0, 100, 300, 200);
 rect1 |= rect2;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);

   rect1 |= rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect1);   
```

  
##  <a name="operator_add"></a>  CRect::operator +  
 İlk iki aşırı dönüş bir `CRect` eşittir nesne `CRect` tarafından belirtilen uzaklıkları hatalı yerleştirilen.  
  
```  
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `point`  
 A [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](cpoint-class.md) nesne dönüş değeri taşımak için kullanılacak birim sayısını belirtir.  
  
 `size`  
 A [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](csize-class.md) nesne dönüş değeri taşımak için kullanılacak birim sayısını belirtir.  
  
 `lpRect`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` dönüş değeri her iki tarafındaki Şişir birim sayısını içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `CRect` Taşıma veya inflating kaynaklanan `CRect` parametresinde belirtilen birimlerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametrenin *x* ve *y* (veya `cx` ve `cy`) parametreleri eklenir `CRect`kullanıcının getirin.  
  
 Üçüncü aşırı yeni döndürür `CRect` eşit olan `CRect` parametresi her bir üyesi birimleri belirtilen sayıda tarafından şişirileceğini.  
  
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
 İlk iki aşırı dönüş bir `CRect` eşittir nesne `CRect` tarafından belirtilen uzaklıkları hatalı yerleştirilen.  
  
```  
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `point`  
 A [noktası](../../mfc/reference/point-structure1.md) yapısı veya `CPoint` nesne dönüş değeri taşımak için kullanılacak birim sayısını belirtir.  
  
 `size`  
 A [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya `CSize` nesne dönüş değeri taşımak için kullanılacak birim sayısını belirtir.  
  
 `lpRect`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` dönüş değeri her iki tarafındaki deflate birim sayısını içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `CRect` Taşıma veya deflating kaynaklanan `CRect` parametresinde belirtilen birimlerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametrenin *x* ve *y* (veya `cx` ve `cy`) parametreleri çıkarılır `CRect`kullanıcının getirin.  
  
 Üçüncü aşırı yeni döndürür `CRect` eşit olan `CRect` parametresi her bir üyesi birimleri belirtilen sayıda tarafından deflated. Bu aşırı gibi işlevleri Not [DeflateRect](#deflaterect)değil [SubtractRect](#subtractrect).  
  
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
 Döndürür bir `CRect` diğer bir deyişle kesişimi `CRect` ve *rect2*.  
  
```  
CRect operator&(const RECT& rect2) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *rect2*  
 İçeren bir [RECT](../../mfc/reference/rect-structure1.md) veya `CRect`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CRect` diğer bir deyişle kesişimi `CRect` ve *rect2*.  
  
### <a name="remarks"></a>Açıklamalar  
 Her iki dikdörtgen bulunan büyük dikdörtgen kesişimi olur.  
  
> [!NOTE]
>  Her iki dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgenler normalleştirmek için.  
  
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
 *rect2*  
 İçeren bir [RECT](../../mfc/reference/rect-structure1.md) veya `CRect`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CRect` diğer bir deyişle birleşimi `CRect` ve *rect2*.  
  
### <a name="remarks"></a>Açıklamalar  
 UNION iki dikdörtgen içeren en küçük dikdörtgen ' dir.  
  
> [!NOTE]
>  Her iki dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgenler normalleştirmek için.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect1(100,   0, 200, 300);
 CRect rect2( 0, 100, 300, 200);
 CRect rect3;

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
 `point`  
 İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](cpoint-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Noktası içinde yer alıyorsa sıfır olmayan `CRect`; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde noktasıdır `CRect` sol veya üst tarafında arasındadır veya dört kenara içinde olduğu durumunda. Bir noktasını sağ veya alt tarafında dışında `CRect`.  
  
> [!NOTE]
>  Dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgen normalleştirmek için.  
  
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
 Boyutlarını ayarlar `CRect` belirtilen koordinatlarına.  
  
```   
void SetRect(int x1, int y1, int x2, int y2) throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 `x1`  
 Sol üst köşenin x koordinatını belirtir.  
  
 `y1`  
 Sol üst köşesindeki y koordinatını belirtir.  
  
 `x2`  
 Sağ alt köşedeki x koordinatını belirtir.  
  
 `y2`  
 Sağ alt köşedeki y koordinatını belirtir.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect;
 rect.SetRect(256, 256, 512, 512);

```cpp  
   CRect rect;
   rect.SetRect(256, 256, 512, 512);
   ASSERT(rect == CRect(256, 256, 512, 512));   
```

  
##  <a name="setrectempty"></a>  CRect::SetRectEmpty  
 Yapar `CRect` tüm koordinatları sıfır olarak ayarlayarak bir dikdörtgen null.  
  
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
 Yükseklik veya genişliği negatif olabilir.  
  
> [!NOTE]
>  Dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgen normalleştirmek için.  
  
### <a name="example"></a>Örnek  
```cpp  
 CRect rect(10, 10, 50, 50);
 CSize sz = rect.Size();
 ASSERT(sz.cx == 40 && sz.cy == 40);  
```

##  <a name="subtractrect"></a>  CRect::SubtractRect  
 Boyutlarını yapar **CRect** çıkarma eşit `lpRectSrc2` gelen `lpRectSrc1`.  
  
```  
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRectSrc1`  
 İşaret [RECT](../../mfc/reference/rect-structure1.md) yapısı veya `CRect` içinden bir dikdörtgen çıkarılır için nesnesi.  
  
 `lpRectSrc2`  
 İşaret `RECT` yapısı veya `CRect` tarafından için dikdörtgen çıkarılır olan nesne işaret `lpRectSrc1` parametresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm noktaları içerir en küçük dikdörtgen çıkarma olan `lpRectScr1` kesişimi içinde olmayan `lpRectScr1` ve *lpRectScr2*.  
  
 Tarafından belirtilen dikdörtgen `lpRectSrc1` dikdörtgen belirtilen değişmeden kalacaktır `lpRectSrc2` tarafından belirtilen dikdörtgen tamamen örtüşmeyecek *lpRectSrc1* birinde en az biri x - veya y-yönergeleri.  
  
 Örneğin, varsa `lpRectSrc1` olan (10,10, 100,100) ve `lpRectSrc2` olan (50,50, 150,150) tarafından için dikdörtgen işaret `lpRectSrc1` işlevi döndürüldüğünde değişmeden olacaktır. Varsa `lpRectSrc1` olan (10,10, 100,100) ve `lpRectSrc2` olan (50,10, 150,150), ancak dikdörtgen işaret için tarafından `lpRectSrc1` (10,10, 50,100) koordinatları içerecektir işlevi döndürdü.  
  
 `SubtractRect` aynı değil [işleci -](#operator_-) ya da [operator-=](#operator_-_eq). Bu işleçlere hiçbiri hiç çağırır `SubtractRect`.  
  
> [!NOTE]
>  Her iki dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgenler normalleştirmek için.  
  
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
 Bir başvuru olarak koordinatları döndürülen bir [CPoint](cpoint-class.md) bulunan nesne `CRect`.  
  
```  
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dikdörtgeninin sol üst köşesinin koordinatlarını.  
  
### <a name="remarks"></a>Açıklamalar  
 Almak veya dikdörtgen sol üst köşesindeki ayarlamak için bu işlevi kullanabilirsiniz. Köşe atama işlecinin sol tarafındaki bu işlevi kullanarak ayarlayın.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CRect::CenterPoint](#centerpoint).  
  
##  <a name="unionrect"></a>  CRect::UnionRect  
 Boyutlarını yapar `CRect` iki kaynak dikdörtgenler birleşimi eşittir.  
  
```  
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect1`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) veya `CRect` kaynak dikdörtgen içerir.  
  
 `lpRect2`  
 İşaret eden bir `RECT` veya `CRect` kaynak dikdörtgen içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 UNION boş değilse, sıfır olmayan; UNION boşsa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 UNION hem kaynak dikdörtgenler içeren en küçük dikdörtgen ' dir.  
  
 Windows boş bir dikdörtgen boyutlarını göz ardı eder; diğer bir deyişle, hiçbir yükseklik veya genişliği bir dikdörtgen.  
  
> [!NOTE]
>  Her iki dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgenler normalleştirmek için.  
  
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
 Genişliğini hesaplar `CRect` sol sağ değer değerinden çıkarılmasıyla tarafından.  
  
```  
int Width() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Genişliğini `CRect`.  
  
### <a name="remarks"></a>Açıklamalar  
 Genişlik negatif olabilir.  
  
> [!NOTE]
>  Dikdörtgen normalleştirilmiş veya bu işlevi başarısız olabilir. Çağırabilirsiniz [NormalizeRect](#normalizerect) bu işlevi çağrılmadan önce dikdörtgen normalleştirmek için.  
  
### <a name="example"></a>Örnek  

```cpp  
   CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
   // nWid is now 60
   ASSERT(nWid == 60);   
```
## <a name="see-also"></a>Ayrıca Bkz.  
 [CPoint sınıfı](cpoint-class.md)   
 [CSize sınıfı](csize-class.md)   
 [RECT](../../mfc/reference/rect-structure1.md)


