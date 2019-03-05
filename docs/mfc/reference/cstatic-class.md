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
ms.openlocfilehash: 02e2f20cc568e8846923f7189da3ea45478fc289
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284443"
---
# <a name="cstatic-class"></a>CStatic sınıfı

Windows statik denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CStatic : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStatic::CStatic](#cstatic)|Oluşturur bir `CStatic` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStatic::Create](#create)|Windows statik denetimi oluşturur ve ona ekler `CStatic` nesne.|
|[CStatic::DrawItem](#drawitem)|Sahip tarafından çizilmiş bir statik denetimi çizmek için geçersiz kılın.|
|[CStatic::GetBitmap](#getbitmap)|Bit eşlem ile önceden ayarlanan tanıtıcısını alır [SetBitmap](#setbitmap).|
|[CStatic::GetCursor](#getcursor)|İmleç görüntü tanıtıcısı ile önceden ayarlanan alır [SetCursor](#setcursor).|
|[CStatic::GetEnhMetaFile](#getenhmetafile)|Gelişmiş Meta dosyası ile önceden ayarlanan tanıtıcısını alır [SetEnhMetaFile](#setenhmetafile).|
|[CStatic::GetIcon](#geticon)|İle önceden ayarlanan simgesi tanıtıcısını alır [SetIcon](#seticon).|
|[CStatic::SetBitmap](#setbitmap)|Statik Denetimde görüntülenecek bir bit eşlem belirtir.|
|[CStatic::SetCursor](#setcursor)|Statik Denetimde görüntülenecek imleç resmi belirtir.|
|[CStatic::SetEnhMetaFile](#setenhmetafile)|Statik Denetimde görüntülenecek bir Gelişmiş Meta dosyası belirtir.|
|[CStatic::SetIcon](#seticon)|Statik Denetimde görüntülenecek bir simge belirtir.|

## <a name="remarks"></a>Açıklamalar

Bir metin dizesi, kutusu, dikdörtgen, simge, imleç, bit eşlem veya Gelişmiş Meta dosyası statik bir denetimi gösterir. Etiket, kutu veya diğer denetimleri ayırmak için kullanılabilir. Statik bir denetimi, normalde giriş yok alır ve çıktı sağlar; Ancak, ss_notıfy stiliyle oluşturduysanız fare tıklama üst bildirimde bulunabilir.

Statik bir denetimi iki adımda oluşturun. İlk olarak oluşturmak için oluşturucu çağrısı `CStatic` nesnesi ve ardından arama [Oluştur](#create) statik denetim oluşturma ve buna eklemek için üye işlevini `CStatic` nesne.

Oluşturursanız, bir `CStatic` nesnesi içinde bir iletişim kutusu (iletişim kaynak) aracılığıyla `CStatic` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.

Oluşturursanız, bir `CStatic` nesnesi bir pencere içinde de gerekebilir, yok. A `CStatic` yığında bir pencere içinde oluşturulan nesne otomatik olarak yok. Oluşturursanız `CStatic` kullanarak yığında nesne **yeni** işlevini çağırmalıdır **Sil** ile işiniz bittiğinde yok etmek için nesne üzerinde.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="create"></a>  CStatic::Create

Windows statik denetimi oluşturur ve ona ekler `CStatic` nesne.

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
Denetimde yerleştirmek için metni belirtir. NULL ise, hiçbir metin görünür olur.

*dwStyle*<br/>
Statik denetimin pencere stilini belirtir. Herhangi bir birleşimini uygulamak [statik denetim stilleri](../../mfc/reference/styles-used-by-mfc.md#static-styles) denetimi.

*Rect*<br/>
Statik denetimin boyutunu ve konumunu belirtir. Ya da olabilir bir `RECT` yapısı veya `CRect` nesne.

*pParentWnd*<br/>
Belirtir `CStatic` üst penceresine, genellikle bir `CDialog` nesne. NULL olmamalıdır.

*nID*<br/>
Statik denetimin denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CStatic` iki adımda nesne. İlk olarak, oluşturucusunu `CStatic`ve sonra çağrı `Create`, Windows statik denetimi oluşturur ve ona ekler `CStatic` nesne.

Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) statik denetlemek için:

- WS_CHILD her zaman

- Ws_vısıble genellikle

- Ws_dısabled nadiren

Bir bit eşlem, imleç, simge veya meta dosyası statik denetimi görüntüleme kullanacaksanız, aşağıdakilerden birini geçerli gerekecektir [statik stiller](../../mfc/reference/styles-used-by-mfc.md#static-styles):

- Ss_bıtmap bu stil için bit eşlemler kullanın.

- Ss_ıcon, simgeler ve imleçler bu stil kullanın.

- Ss_enhmetafıle Gelişmiş Meta dosyası için bu stil kullanın.

İmleçler, bit eşlemler veya simgeler, ayrıca şu stilini kullanmak isteyebilirsiniz:

- Ss_centerımage statik denetiminde görüntü merkezi için kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

##  <a name="cstatic"></a>  CStatic::CStatic

Oluşturur bir `CStatic` nesne.

```
CStatic();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

##  <a name="drawitem"></a>  CStatic::DrawItem

Sahip tarafından çizilmiş bir statik denetimi çizmek için framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Bir işaretçi bir [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) yapısı. Yapı çizilecek öğesi ve gerekli çizim türü hakkında bilgi içerir.

### <a name="remarks"></a>Açıklamalar

Çizim için bir sahip tarafından çizilmiş uygulamak için bu işlevi geçersiz kılma `CStatic` nesne (Denetim SS_OWNERDRAW stili vardır).

##  <a name="getbitmap"></a>  CStatic::GetBitmap

Daha önce kümesi, bit eşlem tanıtıcısını alır [SetBitmap](#setbitmap), yani ilişkili `CStatic`.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tanıtıcı geçerli bir bit eşlem ya da hiçbir bit eşlem ayarlarsanız NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="getcursor"></a>  CStatic::GetCursor

İle önceden ayarlanan imleci tanıtıcısını alır [SetCursor](#setcursor), yani ilişkili `CStatic`.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Dönüş Değeri

Tanıtıcı geçerli imleç ya da hiçbir imleç ayarlarsanız NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="getenhmetafile"></a>  CStatic::GetEnhMetaFile

Daha önce kümesi Gelişmiş Meta dosyası tanıtıcısını alır [SetEnhMetafile](#setenhmetafile), yani ilişkili `CStatic`.

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tanıtıcı geçerli gelişmiş meta dosyası ya da hiçbir Gelişmiş Meta dosyası ayarlarsanız NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="geticon"></a>  CStatic::GetIcon

İle önceden ayarlanan simgesi tanıtıcısını alır [SetIcon](#seticon), yani ilişkili `CStatic`.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tanıtıcı geçerli simge ya da herhangi bir simge ayarlarsanız NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

##  <a name="setbitmap"></a>  CStatic::SetBitmap

Yeni bir bit eşlem statik denetimi ile ilişkilendirir.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parametreler

*Hbıtmap*<br/>
Bit eşlem statik denetimi çizilecek tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Hiçbir bit eşlem statik denetimle ilişkili olduysa, daha önce statik denetim ya da NULL ile ilişkili bit eşlemi tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bit eşlem statik denetimi otomatik olarak çizilir. Varsayılan olarak, sol üst köşede çizilecek ve statik denetim, bit eşlem boyutuna boyutlandırılır.

Çeşitli pencere ve statik denetim stilleri, aşağıdakiler dahil olmak üzere kullanabilirsiniz:

- Ss_bıtmap bu stil her zaman için bit eşlemler kullanın.

- Ss_centerımage statik denetiminde görüntü merkezi için kullanın. Görüntü statik denetimi büyükse, kırpılır. Statik denetim küçükse, görüntünün çevresine boş alanı bit eşlem sol üst köşesindeki piksel rengi tarafından doldurulur.

- MFC sağlar sınıfını `CBitmap`, bit eşlem görüntüsüne ile de çağırabilirsiniz Win32 daha fazla işlev gerektiğinde kullanabileceğiniz `LoadBitmap`. `CBitmap`, GDI nesnesi, bir tür içeren Sık kullanılan birlikte `CStatic`, olduğu bir `CWnd` grafik nesnesi statik denetim olarak görüntülemek için kullanılan sınıf.

`CImage` Daha fazla cihaz bağımsız bit eşlemler (DIB) kolayca çalışmanıza olanak sağlayan bir ATL/MFC sınıftır. Daha fazla bilgi için [Cımage sınıfı](../../atl-mfc-shared/reference/cimage-class.md).

- Tipik kullanımdır vermek `CStatic::SetBitmap` HBITMAP işleci tarafından döndürülen bir GDI nesnesi bir `CBitmap` veya `CImage` nesne. Bunu yapmak için kodu, aşağıdaki satırı benzer.

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```
Aşağıdaki örnek iki oluşturur `CStatic` yığını üzerindeki nesneler. Ardından bir bit eşlem kullanarak bir sistem yükler `CBitmap::LoadOEMBitmap` kullanarak dosyanın öğesinden alınan `CImage::Load`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="setcursor"></a>  CStatic::SetCursor

Yeni bir imleç görüntü statik denetimi ile ilişkilendirir.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Parametreler

*hCursor*<br/>
Statik denetimi çizilecek imleç tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce hiçbir imleç statik denetimle ilişkili olduysa statik denetim ya da NULL ile ilişkili imleci tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

İmleç statik denetimi otomatik olarak çizilir. Varsayılan olarak, sol üst köşede çizilecek ve statik denetimi imleç boyutu için yeniden boyutlandırılır.

Çeşitli pencere ve statik denetim stilleri, aşağıdakiler dahil olmak üzere kullanabilirsiniz:

- Ss_ıcon kullanın Bu stil her zaman işaretçiler ve simgeler.

- Ss_centerımage statik denetimi merkezi için kullanın. Görüntü statik denetimi büyükse, kırpılır. Statik denetim küçükse, görüntünün çevresine boş alanı statik denetimin arka plan rengi ile doldurulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="setenhmetafile"></a>  CStatic::SetEnhMetaFile

Yeni gelişmiş meta dosyası görüntüsünü statik denetimi ile ilişkilendirir.

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>Parametreler

*hMetaFile*<br/>
Statik denetimi çizilecek Gelişmiş Meta dosyası işleyicisi.

### <a name="return-value"></a>Dönüş Değeri

Daha önce hiç Gelişmiş Meta dosyası statik denetimle ilişkili olduysa statik denetim ya da NULL ile ilişkili Gelişmiş Meta dosyası tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Gelişmiş Meta dosyası statik denetimi otomatik olarak çizilir. Gelişmiş Meta dosyası statik denetimin boyutuna sığacak şekilde ölçeklendirilir.

Çeşitli pencere ve statik denetim stilleri, aşağıdakiler dahil olmak üzere kullanabilirsiniz:

- Ss_enhmetafıle kullanmak her zaman bu stil meta dosyaları için Gelişmiş sağlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="seticon"></a>  CStatic::SetIcon

Yeni bir simge görüntüsü statik denetimi ile ilişkilendirir.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*hIcon*<br/>
Statik denetimi çizilecek simge tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir simge statik denetimle ilişkili olduysa daha önce statik denetim ya da NULL ile ilişkili simgeyi tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Simge statik denetimi otomatik olarak çizilir. Varsayılan olarak, sol üst köşede çizilecek ve statik denetimin simgesi boyutu için yeniden boyutlandırılır.

Çeşitli pencere ve statik denetim stilleri, aşağıdakiler dahil olmak üzere kullanabilirsiniz:

- Ss_ıcon kullanın Bu stil her zaman işaretçiler ve simgeler.

- Ss_centerımage statik denetimi merkezi için kullanın. Görüntü statik denetimi büyükse, kırpılır. Statik denetim küçükse, görüntünün çevresine boş alanı statik denetimin arka plan rengi ile doldurulur.

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
