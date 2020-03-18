---
title: CStatic sınıfı
ms.date: 11/04/2016
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
helpviewer_keywords:
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
ms.openlocfilehash: fc0164b2d0046ca2d36291696dd6137a9fcef069
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447422"
---
# <a name="cstatic-class"></a>CStatic sınıfı

Windows statik denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CStatic : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CStatic:: CStatic](#cstatic)|`CStatic` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStatic:: Create](#create)|Windows statik denetimini oluşturur ve `CStatic` nesnesine iliştirir.|
|[CStatic::D rawItem](#drawitem)|Sahip tarafından çizilmiş bir statik denetim çizmek için geçersiz kılın.|
|[CStatic:: GetBitmap](#getbitmap)|Daha önce [SetBitmap](#setbitmap)ile ayarlanan bit eşlemin tanıtıcısını alır.|
|[CStatic:: GetCursor](#getcursor)|Daha önce [SetCursor](#setcursor)ile ayarlanmış imleç resminin tanıtıcısını alır.|
|[CStatic:: GetEnhMetaFile](#getenhmetafile)|Daha önce [SetEnhMetaFile](#setenhmetafile)ile ayarlanmış olan gelişmiş meta dosyası tanıtıcısını alır.|
|[CStatic:: GetIcon](#geticon)|Daha önce [setIcon](#seticon)ile ayarlanan simgenin tanıtıcısını alır.|
|[CStatic:: SetBit eşlem](#setbitmap)|Statik denetimde görüntülenecek bir bit eşlem belirtir.|
|[CStatic:: SetCursor](#setcursor)|Statik denetimde görüntülenecek imleç resmini belirtir.|
|[CStatic:: SetEnhMetaFile](#setenhmetafile)|Statik denetimde görüntülenecek bir gelişmiş meta dosyası belirtir.|
|[CStatic:: SetIcon](#seticon)|Statik denetimde görüntülenecek bir simge belirtir.|

## <a name="remarks"></a>Açıklamalar

Statik denetim bir metin dizesi, kutu, dikdörtgen, simge, imleç, bit eşlem veya geliştirilmiş meta dosya görüntüler. Diğer denetimleri etiketlemek, kutuyu veya ayırmak için kullanılabilir. Statik bir denetim normalde giriş gerçekleşmez ve çıkış vermez; Ancak, SS_NOTIFY stille oluşturulduysa fare tıklamasının üst öğesine bildirimde bulunabilir.

İki adımda statik denetim oluşturun. İlk olarak, `CStatic` nesnesini oluşturmak için oluşturucuyu çağırın, ardından statik denetimi oluşturmak ve `CStatic` nesnesine eklemek için üye [Oluştur](#create) işlevini çağırın.

İletişim kutusu içinde bir `CStatic` nesnesi oluşturursanız (bir iletişim kutusu kaynağı aracılığıyla), Kullanıcı iletişim kutusunu kapattığında `CStatic` nesnesi otomatik olarak yok edilir.

Bir pencere içinde bir `CStatic` nesnesi oluşturursanız, bunu yok etmeniz de gerekebilir. Bir pencere içindeki yığında oluşturulan `CStatic` nesnesi otomatik olarak yok edilir. **Yeni** işlevi kullanarak yığında `CStatic` nesnesi oluşturursanız, bununla işiniz bittiğinde yok etmek için nesneyi **silme** çağrısı yapmanız gerekir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="create"></a>CStatic:: Create

Windows statik denetimini oluşturur ve `CStatic` nesnesine iliştirir.

```
virtual BOOL Create(
    LPCTSTR lpszText,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID = 0xffff);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Denetime yerleştirilecek metni belirtir. NULL ise, hiçbir metin görünür olmaz.

*dwStyle*<br/>
Statik denetimin pencere stilini belirtir. Denetim için herhangi bir [statik denetim stilleri](../../mfc/reference/styles-used-by-mfc.md#static-styles) birleşimini uygulayın.

*Rect*<br/>
Statik denetimin konumunu ve boyutunu belirtir. Bir `RECT` yapısı veya bir `CRect` nesnesi olabilir.

*pParentWnd*<br/>
Genellikle bir `CDialog` nesnesi olan `CStatic` üst pencereyi belirtir. NULL olmaması gerekir.

*NID*<br/>
Statik denetimin denetim KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda `CStatic` nesnesi oluşturun. İlk olarak, oluşturucuyu `CStatic`çağırın ve sonra Windows statik denetimini oluşturan ve `CStatic` nesnesine ekleyen `Create`çağırın.

Statik denetime aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) uygulayın:

- WS_CHILD her zaman

- Genellikle WS_VISIBLE

- WS_DISABLED nadiren

Statik denetimde bir bit eşlem, imleç, simge veya meta dosya görüntüleyecekseniz, aşağıdaki [statik stillerden](../../mfc/reference/styles-used-by-mfc.md#static-styles)birini uygulamanız gerekir:

- SS_BITMAP bit eşlemler için bu stili kullanın.

- SS_ICON imleçler ve simgeler için bu stili kullanın.

- SS_ENHMETAFILE gelişmiş meta dosyalar için bu stili kullanın.

İmleçler, bit eşlemler veya simgeler için aşağıdaki stili de kullanmak isteyebilirsiniz:

- SS_CENTERIMAGE statik denetimdeki görüntüyü ortalamak için kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

##  <a name="cstatic"></a>CStatic:: CStatic

`CStatic` nesnesi oluşturur.

```
CStatic();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

##  <a name="drawitem"></a>CStatic::D rawItem

Sahip tarafından çizilmiş bir statik denetim çizmek için Framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
[Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına yönelik bir işaretçi. Yapı, çizilecek öğe ve çizim türü hakkında bilgiler içerir.

### <a name="remarks"></a>Açıklamalar

Sahip tarafından çizilmiş bir `CStatic` nesnesine çizim uygulamak için bu işlevi geçersiz kılın (denetim, SS_OWNERDRAW stiline sahiptir).

##  <a name="getbitmap"></a>CStatic:: GetBitmap

`CStatic`ile ilişkili daha önce [SetBitmap](#setbitmap)ile ayarlanan bit eşlemin tanıtıcısını alır.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bit eşlem için bir tanıtıcı veya bit eşlem ayarlanmamışsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="getcursor"></a>CStatic:: GetCursor

`CStatic`ile ilişkili, daha önce [SetCursor](#setcursor)ile ayarlanan imlecin tanıtıcısını alır.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli imlecin bir tutamacı veya imleç ayarlanmamışsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="getenhmetafile"></a>CStatic:: GetEnhMetaFile

`CStatic`ile ilişkili olan, daha önce [SetEnhMetaFile](#setenhmetafile)ile ayarlanmış olan gelişmiş meta dosyası tanıtıcısını alır.

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Gelişmiş Meta dosyası için bir tanıtıcı veya gelişmiş bir dosya ayarlanmamışsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="geticon"></a>CStatic:: GetIcon

`CStatic`ile ilişkili olan, daha önce [setIcon](#seticon)ile ayarlanan simgenin tanıtıcısını alır.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli simgeye yönelik bir tanıtıcı veya hiçbir simge ayarlanmamışsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

##  <a name="setbitmap"></a>CStatic:: SetBit eşlem

Statik denetimle yeni bir bit eşlem ilişkilendirir.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parametreler

*HBITMAP*<br/>
Statik denetimde çizilecek bit eşlemin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Statik denetimle daha önce ilişkilendirilmiş olan bit eşlem tutamacı veya statik denetimle ilişkili bir bit eşlem yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bit eşlem, statik denetimde otomatik olarak çizilecektir. Varsayılan olarak, sol üst köşede çizilir ve statik denetim, bit eşlemin boyutuna yeniden boyutlandırılır.

Aşağıdakiler de dahil olmak üzere çeşitli pencere ve statik denetim stilleri kullanabilirsiniz:

- SS_BITMAP bu stili her zaman bitmapler için kullanın.

- SS_CENTERIMAGE statik denetimdeki görüntüyü ortalamak için kullanın. Görüntü statik denetimden büyükse kırpılacak. Statik denetimden daha küçükse, görüntünün çevresindeki boş alan, bit eşlemin sol üst köşesindeki pikselin rengi ile doldurulur.

- MFC, bir bit eşlem görüntüsü ile daha fazla yapmanız gerektiğinde kullanabileceğiniz sınıfı `CBitmap`sağlar `LoadBitmap`. bir tür GDI nesnesi içeren `CBitmap`, genellikle bir grafik nesnesini statik bir denetim olarak görüntülemek için kullanılan `CWnd` bir sınıf olan `CStatic`birlikte ortak işlem içinde kullanılır.

`CImage`, cihazdan bağımsız bit eşlemlerle (DIB) daha kolay çalışabilmenizi sağlayan bir ATL/MFC sınıfıdır. Daha fazla bilgi için bkz. [CImage sınıfı](../../atl-mfc-shared/reference/cimage-class.md).

- Tipik kullanım, bir `CBitmap` veya `CImage` nesnesinin HBıX operatörü tarafından döndürülen bir GDI nesnesi `CStatic::SetBitmap` vermektir. Bunu yapmak için kod aşağıdaki satıra benzer.

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```

Aşağıdaki örnek yığında iki `CStatic` nesnesi oluşturur. Daha sonra, `CImage::Load`kullanarak bir dosya `CBitmap::LoadOEMBitmap` ve diğeri kullanarak bir sistem bit eşlemiyle yükler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="setcursor"></a>CStatic:: SetCursor

Yeni bir imleç görüntüsünü statik denetimle ilişkilendirir.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Parametreler

*hCursor*<br/>
Statik denetimde çizilecek imlecin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce statik denetimle ilişkilendirilen imlecin tutamacı veya statik denetimle ilişkili imleç yoksa NULL.

### <a name="remarks"></a>Açıklamalar

İmleç, statik denetimde otomatik olarak çizilecektir. Varsayılan olarak, sol üst köşede çizilir ve statik denetim imlecin boyutuna yeniden boyutlandırılır.

Aşağıdakiler de dahil olmak üzere çeşitli pencere ve statik denetim stilleri kullanabilirsiniz:

- SS_ICON bu stili her zaman imleçler ve simgeler için kullanın.

- SS_CENTERIMAGE statik denetimde ortalamak için kullanın. Görüntü statik denetimden büyükse kırpılacak. Statik denetimden daha küçükse, görüntünün çevresindeki boş alan statik denetimin arka plan rengiyle doldurulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="setenhmetafile"></a>CStatic:: SetEnhMetaFile

Yeni bir geliştirilmiş meta dosyası görüntüsünü statik denetimle ilişkilendirir.

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>Parametreler

*hMetaFile*<br/>
Statik denetimde çizilecek gelişmiş meta dosyası tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce statik denetimle ilişkili olan gelişmiş meta dosyası tutamacı veya statik denetimle gelişmiş bir dosya ilişkilendirilmediği takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Gelişmiş Meta dosyası otomatik olarak statik denetimde çizilecektir. Gelişmiş Meta dosyası statik denetimin boyutuna uyacak şekilde ölçeklendirilir.

Aşağıdakiler de dahil olmak üzere çeşitli pencere ve statik denetim stilleri kullanabilirsiniz:

- SS_ENHMETAFILE gelişmiş meta dosyalar için her zaman bu stili kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="seticon"></a>CStatic:: SetIcon

Yeni bir simge görüntüsünü statik denetimle ilişkilendirir.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*HICON*<br/>
Statik denetimde çizilecek simgenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Statik denetimle daha önce ilişkilendirilmiş simgenin tutamacı veya statik denetimle ilişkili bir simge yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Simge, statik denetimde otomatik olarak çizilecektir. Varsayılan olarak, sol üst köşede çizilir ve statik denetim simgenin boyutuna yeniden boyutlandırılır.

Aşağıdakiler de dahil olmak üzere çeşitli pencere ve statik denetim stilleri kullanabilirsiniz:

- SS_ICON bu stili her zaman imleçler ve simgeler için kullanın.

- SS_CENTERIMAGE statik denetimde ortalamak için kullanın. Görüntü statik denetimden büyükse kırpılacak. Statik denetimden daha küçükse, görüntünün çevresindeki boş alan statik denetimin arka plan rengiyle doldurulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CButton Sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar Sınıfı](../../mfc/reference/cscrollbar-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
