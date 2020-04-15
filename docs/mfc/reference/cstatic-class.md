---
title: Cstatic Sınıfı
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
ms.openlocfilehash: e5c3705c0aa2fd90e73cb54ba5a97c252ed2cf83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371638"
---
# <a name="cstatic-class"></a>Cstatic Sınıfı

Windows statik denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CStatic : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Cstatic::cstatic](#cstatic)|Bir `CStatic` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStatic::Oluştur](#create)|Windows statik denetimini oluşturur ve `CStatic` nesneye bağlar.|
|[CStatic::DrawItem](#drawitem)|Sahibi tarafından çizilmiş statik denetim çizmek için geçersiz kılın.|
|[CStatic::GetBitmap](#getbitmap)|[SetBitmap](#setbitmap)ile daha önce ayarlanmış bit eşlemi nin tutamacını alır.|
|[CStatic::GetCursor](#getcursor)|[SetCursor](#setcursor)ile daha önce ayarlanmış imleç görüntüsünün tutamacını alır.|
|[CStatic::GetEnhMetaFile](#getenhmetafile)|[SetEnhMetaFile](#setenhmetafile)ile daha önce ayarlanmış gelişmiş metafilenin tutamacını alır.|
|[Cstatic::GetIcon](#geticon)|[SetIcon](#seticon)ile daha önce ayarlanmış simgenin tutamacını alır.|
|[CStatic::SetBitmap](#setbitmap)|Statik denetimde görüntülenecek bir bit eşlemi belirtir.|
|[CStatic::SetCursor](#setcursor)|Statik denetimde görüntülenecek bir imleç görüntüsünü belirtir.|
|[CStatic::SetEnhMetaFile](#setenhmetafile)|Statik denetimde görüntülenecek gelişmiş bir metadosya belirtir.|
|[Cstatic::Seticon](#seticon)|Statik denetimde görüntülenecek bir simge belirtir.|

## <a name="remarks"></a>Açıklamalar

Statik denetim, metin dizesi, kutu, dikdörtgen, simge, imleç, biteşveya gelişmiş metadosya görüntüler. Diğer denetimleri etiketlemek, kutulamak veya ayırmak için kullanılabilir. Statik denetim normalde hiçbir giriş alır ve hiçbir çıkış sağlar; ancak, SS_NOTIFY stiliyle oluşturulmuşsa fare tıklamalarının üst kısmını bildirebilir.

İki adımda statik denetim oluşturun. Önce `CStatic` nesneyi oluşturmak için oluşturucuyu çağırın, ardından statik denetimi oluşturmak ve `CStatic` nesneye bağlamak için [Üye Oluştur](#create) işlevini çağırın.

İletişim kutusu `CStatic` içinde (iletişim kaynağı aracılığıyla) bir nesne `CStatic` oluşturursanız, kullanıcı iletişim kutusunu kapattığında nesne otomatik olarak yok edilir.

Bir pencere `CStatic` içinde bir nesne oluşturursanız, onu yok etmek de gerekebilir. Bir `CStatic` pencere içindeki yığında oluşturulan bir nesne otomatik olarak yok edilir. Nesneyi `CStatic` **yeni** işlevi kullanarak yığında oluşturursanız, onunla iş bittiğinde onu yok etmek için nesneyi **sil'i** aramanız gerekir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cstaticcreate"></a><a name="create"></a>CStatic::Oluştur

Windows statik denetimini oluşturur ve `CStatic` nesneye bağlar.

```
virtual BOOL Create(
    LPCTSTR lpszText,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID = 0xffff);
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
Denetime yerleştirilecek metni belirtir. NULL ise, hiçbir metin görünür olacaktır.

*Dwstyle*<br/>
Statik denetimin pencere stilini belirtir. Statik kontrol [stillerinin](../../mfc/reference/styles-used-by-mfc.md#static-styles) herhangi bir birleşimini denetime uygulayın.

*Rect*<br/>
Statik denetimin konumunu ve boyutunu belirtir. Bir `RECT` yapı veya nesne `CRect` olabilir.

*pParentWnd*<br/>
Genellikle bir `CDialog` `CStatic` nesne olan ana pencereyi belirtir. NULL olmamalıdır.

*Nıd*<br/>
Statik denetimin denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir `CStatic` nesneyi iki adımda oluştur. İlk olarak, oluşturucuyu `CStatic`çağırın, sonra `Create`windows statik denetimini oluşturur `CStatic` ve nesneye bağlar.

Statik denetime aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) uygulayın:

- WS_CHILD Her Zaman

- WS_VISIBLE Genellikle

- WS_DISABLED Nadiren

Statik denetimde bir biteş, imleç, simge veya metadosya görüntülerseniz, aşağıdaki [statik stillerden](../../mfc/reference/styles-used-by-mfc.md#static-styles)birini uygulamanız gerekir:

- SS_BITMAP Bit eşlemler için bu stili kullanın.

- SS_ICON İmleçler ve simgeler için bu stili kullanın.

- SS_ENHMETAFILE Gelişmiş metadosyalar için bu stili kullanın.

İmleçler, bit eşlemler veya simgeler için aşağıdaki stili de kullanmak isteyebilirsiniz:

- SS_CENTERIMAGE Görüntüyü statik denetimde ortalamak için kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

## <a name="cstaticcstatic"></a><a name="cstatic"></a>Cstatic::cstatic

Bir `CStatic` nesne inşa eder.

```
CStatic();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

## <a name="cstaticdrawitem"></a><a name="drawitem"></a>CStatic::DrawItem

Bir sahibi tarafından çizilmiş statik kontrol çizmek için çerçeve tarafından çağrıldı.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
[DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına işaretçi. Yapı, çizilecek öğe ve gerekli çizim türü hakkında bilgi içerir.

### <a name="remarks"></a>Açıklamalar

Sahibitarafından çizilen `CStatic` bir nesne için çizim uygulamak için bu işlevi geçersiz kılın (denetim SS_OWNERDRAW stiline sahiptir).

## <a name="cstaticgetbitmap"></a><a name="getbitmap"></a>CStatic::GetBitmap

Bitmap' in tutamacını alır, daha önce [SetBitmap](#setbitmap)ile ayarlanmış , bu ile `CStatic`ilişkilidir .

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bit eşlemi için bir tanıtıcı veya bit eşlemi ayarlanmadıysa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

## <a name="cstaticgetcursor"></a><a name="getcursor"></a>CStatic::GetCursor

İmleç tutamacını alır, daha önce [SetCursor](#setcursor)ile `CStatic`ayarlanmış , ile ilişkili .

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli imlecin tutamacı veya imleç ayarlanmadıysa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

## <a name="cstaticgetenhmetafile"></a><a name="getenhmetafile"></a>CStatic::GetEnhMetaFile

Daha önce [SetEnhMetafile](#setenhmetafile)ile ayarlanmış gelişmiş metafile, işkolu `CStatic`alır , ile ilişkili .

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli geliştirilmiş metadosyaya bir tanıtıcı veya gelişmiş metadosya ayarlanmadıysa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

## <a name="cstaticgeticon"></a><a name="geticon"></a>Cstatic::GetIcon

Daha önce [SetIcon](#seticon)ile ayarlanmış simgenin tutamacını `CStatic`alır .

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli simgeye bir tanıtıcı veya simge ayarlanmadıysa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="cstaticsetbitmap"></a><a name="setbitmap"></a>CStatic::SetBitmap

Statik denetimle yeni bir bit eşlemi ilişkilendirer.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parametreler

*Hbıtmap*<br/>
Statik denetimde çizilecek bit eşlemi nin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce statik denetimle ilişkili bit eşlemi veya statik denetimle ilişkili bit eşlemi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bit eşlemi statik denetimde otomatik olarak çizilir. Varsayılan olarak, sol üst köşeye çizilir ve statik denetim bit eşlemi boyutuna yeniden boyutlandırılır.

Bunlar da dahil olmak üzere çeşitli pencere ve statik denetim stilleri kullanabilirsiniz:

- SS_BITMAP Biteşler için her zaman bu stili kullanın.

- SS_CENTERIMAGE Görüntüyü statik denetimde ortalamak için kullanın. Görüntü statik denetimden daha büyükse, kırpılır. Statik denetimden daha küçükse, görüntünün etrafındaki boş alan bit eşlenin sol üst köşesindeki pikselin rengiyle doldurulur.

- MFC sadece `CBitmap`Win32 fonksiyonu `LoadBitmap`aramak daha bir bitmap görüntü ile daha fazla yapmak zorunda kullanabileceğiniz sınıf sağlar. `CBitmap`, gdi nesnesi bir tür içeren, `CStatic`genellikle ile `CWnd` işbirliği içinde kullanılır , statik bir denetim olarak bir grafik nesnesi görüntülemek için kullanılan bir sınıftır.

`CImage`aygıtbağımsız bit eşlemleri (DIB) ile daha kolay çalışmanızı sağlayan bir ATL/MFC sınıfıdır. Daha fazla bilgi için [CImage Class'a](../../atl-mfc-shared/reference/cimage-class.md)bakın.

- Tipik kullanım, `CStatic::SetBitmap` bir `CBitmap` veya `CImage` nesnenin HBITMAP işleci tarafından döndürülen bir GDI nesnesi vermektir. Bunu yapmak için kod aşağıdaki satırı benzer.

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```

Aşağıdaki örnek, yığın `CStatic` üzerinde iki nesne oluşturur. Daha sonra kullanarak bir sistem `CBitmap::LoadOEMBitmap` bitmap ve diğer `CImage::Load`kullanarak bir dosyadan bir yükler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

## <a name="cstaticsetcursor"></a><a name="setcursor"></a>CStatic::SetCursor

Yeni bir imleç görüntüsünü statik denetimle ilişkilendirer.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Parametreler

*hCursor*<br/>
İmlecin tutamacı statik denetimde çizilecek.

### <a name="return-value"></a>Dönüş Değeri

İmleç daha önce statik denetim ile ilişkili veya null hiçbir imleç statik denetim ile ilişkili idi.

### <a name="remarks"></a>Açıklamalar

İmleç statik denetimde otomatik olarak çizilir. Varsayılan olarak, sol üst köşeye çizilir ve statik denetim imleç boyutuna yeniden boyutlandırılır.

Aşağıdakiler de dahil olmak üzere çeşitli pencere ve statik denetim stilleri kullanabilirsiniz:

- SS_ICON İmleçler ve simgeler için her zaman bu stili kullanın.

- SS_CENTERIMAGE Statik denetimi ortalamak için kullanın. Görüntü statik denetimden daha büyükse, kırpılır. Statik denetimden daha küçükse, görüntünün etrafındaki boş alan statik denetimin arka plan rengiyle doldurulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

## <a name="cstaticsetenhmetafile"></a><a name="setenhmetafile"></a>CStatic::SetEnhMetaFile

Yeni bir gelişmiş metadosya görüntüsünü statik denetimle ilişkilendirer.

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>Parametreler

*hMetaFile*<br/>
Statik denetimde çizilecek gelişmiş metadosyanın tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce statik denetimle ilişkili geliştirilmiş metadosyanın tutamacı veya statik denetimle ilişkili gelişmiş metadosya yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Geliştirilmiş metadosya statik denetimotomatik olarak çizilecektir. Geliştirilmiş metadosya statik denetim boyutuna uyacak şekilde ölçeklendirilir.

Aşağıdakiler de dahil olmak üzere çeşitli pencere ve statik denetim stilleri kullanabilirsiniz:

- SS_ENHMETAFILE Gelişmiş metadosyalar için her zaman bu stili kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

## <a name="cstaticseticon"></a><a name="seticon"></a>Cstatic::Seticon

Yeni bir simge görüntüsünü statik denetimle ilişkilendirer.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*Hıcon*<br/>
Statik denetimde çizilecek simgenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce statik denetimle ilişkili simgenin tutamacı veya statik denetimle ilişkili bir simge yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Simge statik denetimde otomatik olarak çizilir. Varsayılan olarak, sol üst köşeye çizilir ve statik denetim simgenin boyutuna yeniden boyutlandırılır.

Aşağıdakiler de dahil olmak üzere çeşitli pencere ve statik denetim stilleri kullanabilirsiniz:

- SS_ICON İmleçler ve simgeler için her zaman bu stili kullanın.

- SS_CENTERIMAGE Statik denetimi ortalamak için kullanın. Görüntü statik denetimden daha büyükse, kırpılır. Statik denetimden daha küçükse, görüntünün etrafındaki boş alan statik denetimin arka plan rengiyle doldurulur.

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
