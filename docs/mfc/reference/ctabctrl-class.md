---
title: CTabCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cfbcdf03a5c527d27d9bff8b37322011cba60bb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063516"
---
# <a name="ctabctrl-class"></a>CTabCtrl sınıfı

Windows ortak sekme denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CTabCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTabCtrl::CTabCtrl](#ctabctrl)|Oluşturur bir `CTabCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTabCtrl::AdjustRect](#adjustrect)|Bir pencere dikdörtgeni verilen bir sekme denetim görüntüleme alanı hesaplar veya belirli görüntüleme alanına karşılık gelir Pencere dikdörtgeni hesaplar.|
|[CTabCtrl::Create](#create)|Sekme denetimi oluşturur ve bunu örneğine ekler bir `CTabCtrl` nesne.|
|[CTabCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir sekme denetimi oluşturur ve bunu örneğine ekler bir `CTabCtrl` nesne.|
|[CTabCtrl::DeleteAllItems](#deleteallitems)|Bir sekme denetimi tüm öğeleri kaldırır.|
|[CTabCtrl::DeleteItem](#deleteitem)|Bir sekme denetiminden bir öğeyi kaldırır.|
|[CTabCtrl::DeselectAll](#deselectall)|Basılan tüm temizleyerek bir sekme denetimindeki öğeleri sıfırlar.|
|[CTabCtrl::DrawItem](#drawitem)|Bir sekme denetimi belirtilen bir öğeyi çizer.|
|[CTabCtrl::GetCurFocus](#getcurfocus)|Sekme denetimine geçerli odak noktası içeren sekmeye alır.|
|[CTabCtrl::GetCurSel](#getcursel)|Şu anda seçilen sekmesi bir sekme denetimindeki belirler.|
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Şu anda kullanılmakta olan sekme denetimi için genişletilmiş stiller alır.|
|[CTabCtrl::GetImageList](#getimagelist)|Sekme denetimiyle ilişkili görüntü listesini alır.|
|[CTabCtrl::GetItem](#getitem)|Bir sekme denetimindeki sekme hakkındaki bilgileri alır.|
|[CTabCtrl::GetItemCount](#getitemcount)|Sekme denetimine sekmeler sayısını alır.|
|[CTabCtrl::GetItemRect](#getitemrect)|Bir sekme denetimindeki sekme için sınırlayıcı dikdörtgeni alır.|
|[CTabCtrl::GetItemState](#getitemstate)|Belirtilen sekme denetim öğesi durumunu alır.|
|[CTabCtrl::GetRowCount](#getrowcount)|Geçerli bir sekme denetimindeki sekme satır sayısını alır.|
|[CTabCtrl::GetToolTips](#gettooltips)|Sekme denetimiyle ilişkili araç ipucunu denetimini tanıtıcısını alır.|
|[CTabCtrl::HighlightItem](#highlightitem)|Sekme öğesi vurgulama durumunu ayarlar.|
|[CTabCtrl::HitTest](#hittest)|Hangi sekme varsa, belirtilen ekran konumda olduğunu belirler.|
|[CTabCtrl::InsertItem](#insertitem)|Yeni bir sekme içinde Sekme denetimine ekler.|
|[CTabCtrl::RemoveImage](#removeimage)|Bir sekme denetiminin görüntü listesinden görüntü kaldırır.|
|[CTabCtrl::SetCurFocus](#setcurfocus)|Belirtilen bir sekme denetimindeki sekme odağı ayarlar.|
|[CTabCtrl::SetCurSel](#setcursel)|Bir sekme içinde Sekme denetimini seçer.|
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Genişletilmiş stiller sekme denetimi için ayarlar.|
|[CTabCtrl::SetImageList](#setimagelist)|Görüntü listesi Sekme denetimine atar.|
|[CTabCtrl::SetItem](#setitem)|Bazılarını veya tümünü bir sekmenin öznitelikleri ayarlar.|
|[CTabCtrl::SetItemExtra](#setitemextra)|Uygulama tanımlı bir sekme denetimindeki veri için rezerve sekme başına bayt sayısını ayarlar.|
|[CTabCtrl::SetItemSize](#setitemsize)|Öğenin yüksekliğini ve genişliğini ayarlar.|
|[CTabCtrl::SetItemState](#setitemstate)|Belirtilen sekme denetim öğesi durumunu ayarlar.|
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|Bir sekme denetiminde öğelerin minimum genişliğini ayarlar.|
|[CTabCtrl::SetPadding](#setpadding)|(Her sekmenin simgesini ve bir sekme denetimindeki etiket doldurma) boşluk miktarını belirler.|
|[CTabCtrl::SetToolTips](#settooltips)|Sekme denetimine bir araç ipucunu denetimini atar.|

## <a name="remarks"></a>Açıklamalar

"Sekme denetimi" Bölücü içinde bir not defteri veya dosya dolabı etiketleri benzer. Sekme denetimi kullanarak, bir uygulama bir pencerede veya iletişim kutusunda, aynı alan için birden çok sayfa tanımlayabilirsiniz. Her sayfanın bilgilerini veya bir grup kullanıcı ilgili sekmeye seçtiğinde uygulama görüntüleyen denetimlerin bir kümesinden oluşur. Özel türde bir sekme denetimine sekmeler, düğmeler gibi görünen görüntüler. Bir düğmeye tıklandığında, hemen bir sayfa görüntüleme yerine bir komut gerçekleştirmeniz gerekir.

Bu denetimi (ve bu nedenle `CTabCtrl` sınıfı) ve üzeri yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programlar için kullanılabilir.

Kullanma hakkında daha fazla bilgi için `CTabCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CTabCtrl](../../mfc/using-ctabctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="adjustrect"></a>  CTabCtrl::AdjustRect

Bir pencere dikdörtgeni verilen bir sekme denetim görüntüleme alanı hesaplar veya belirli görüntüleme alanına karşılık gelir Pencere dikdörtgeni hesaplar.

```
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*bLarger*<br/>
Hangi işleminin gerçekleştiğini gösterir. Bu parametre TRUE ise *lpRect* görünen dikdörtgen belirtir ve karşılık gelen Pencere dikdörtgeni alır. Bu parametre FALSE ise *lpRect* Pencere dikdörtgeni belirtir ve karşılık gelen görüntü dikdörtgeni alır.

*lpRect*<br/>
İşaretçi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) belirtilen dikdörtgen belirtir ve hesaplanan dikdörtgen alan yapısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

##  <a name="create"></a>  CTabCtrl::Create

Sekme denetimi oluşturur ve bunu örneğine ekler bir `CTabCtrl` nesne.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Sekme denetiminin stilini belirtir. Herhangi bir birleşimini uygulamak [sekme denetim stilleri](/windows/desktop/Controls/tab-control-styles)Windows SDK içinde açıklandığı gibi. Bkz: **açıklamalar** denetimlere de uygulayabilirsiniz pencere stilleri listesi.

*Rect*<br/>
Sekme denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı.

*pParentWnd*<br/>
Sekme denetiminin üst penceresine, genellikle belirtir bir `CDialog`. NULL olmamalıdır.

*nID*<br/>
Sekme denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin başlatma başarılı olduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CTabCtrl` iki adımda nesne. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, sekme denetimi oluşturur ve ona ekler `CTabCtrl` nesne.

Sekme denetim stilleri ek olarak, aşağıdaki pencere stilleri Sekme denetimine uygulayabilirsiniz:

- WS_CHILD Sekme denetimini temsil eden bir alt pencere oluşturur. WS_POPUP stiliyle kullanılamaz.

- Ws_vısıble başlangıçta görünen bir sekme denetimi oluşturur.

- Ws_dısabled başlangıçta devre dışı olan bir pencere oluşturur.

- WS_GROUP hangi kullanıcının bir denetimden yanındaki ok tuşlarıyla taşıyabilirsiniz Denetim grubunun ilk denetimi belirtir. İlk kontrolden sonra aynı gruba WS_GROUP stiliyle tanımlanan tüm denetimler. WS_GROUP stili sonraki denetim stili grubun sona erer ve (sonraki başladığı diğer bir deyişle, bir grubun bittiği) sonraki grubu başlatır.

- WS_TABSTOP birini belirtir tüm denetimleri yoluyla kullanıcının TAB tuşunu kullanarak taşıyabilirsiniz. Sekme tuşunu kullanıcı WS_TABSTOP stili tarafından belirtilen sonraki denetime gider.

Genişletilmiş pencere stilleri ile bir sekme denetimi oluşturmak için arama [CTabCtrl::CreateEx](#createex) yerine `Create`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

##  <a name="createex"></a>  CTabCtrl::CreateEx

Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CTabCtrl` nesne.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK.

*dwStyle*<br/>
Sekme denetiminin stilini belirtir. Herhangi bir birleşimini uygulamak [sekme denetim stilleri](/windows/desktop/Controls/tab-control-styles)Windows SDK içinde açıklandığı gibi. Bkz: **açıklamalar** içinde [Oluştur](#create) denetimlere de uygulayabilirsiniz pencere stilleri listesi.

*Rect*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.

*pParentWnd*<br/>
Denetimin ana penceresine bir işaretçi.

*nID*<br/>
Denetimin alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanım `CreateEx` yerine [Oluştur](#create) Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.

`CreateEx` tarafından belirtilen Genişletilmiş Windows stillerle denetimi oluşturur *dwExStyle*. Genişletilmiş stiller kullanarak bir denetimi belirli kümesi [SetExtendedStyle](#setextendedstyle). Örneğin, `CreateEx` böyle stilleri WS_EX_CONTEXTHELP ayarlandı, ancak kullanmak için `SetExtendedStyle` böyle stilleri TCS_EX_FLATSEPARATORS ayarlanacak. Daha fazla bilgi için bkz. bölümünde açıklanan stilleri [sekme denetim stilleri Genişletilmiş](/windows/desktop/Controls/tab-control-extended-styles) Windows SDK.

##  <a name="ctabctrl"></a>  CTabCtrl::CTabCtrl

Oluşturur bir `CTabCtrl` nesne.

```
CTabCtrl();
```

##  <a name="deleteallitems"></a>  CTabCtrl::DeleteAllItems

Bir sekme denetimi tüm öğeleri kaldırır.

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="deleteitem"></a>  CTabCtrl::DeleteItem

Belirtilen öğeyi bir sekme denetiminden kaldırır.

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
Silinecek öğenin sıfır tabanlı değer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

##  <a name="deselectall"></a>  CTabCtrl::DeselectAll

Basılan tüm temizleyerek bir sekme denetimindeki öğeleri sıfırlar.

```
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>Parametreler

*fExcludeFocus*<br/>
Öğe deselection kapsamını belirten bayrak. Bu parametre FALSE olarak ayarlarsanız, tüm sekme düğmelerinin sıfırlanır. Tüm öğeleri şu anda seçili dışında sekmesinde bunu TRUE olarak ayarlanırsa sıfırlanır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [TCM_DESELECTALL](/windows/desktop/Controls/tcm-deselectall)Windows SDK içinde açıklandığı gibi.

##  <a name="drawitem"></a>  CTabCtrl::DrawItem

Görsel bir özelliği bir özelleştirilmiş çizimli sekme denetim değişiklikleri, framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Bir işaretçi bir [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) boyanacak öğesini açıklayan yapısı.

### <a name="remarks"></a>Açıklamalar

`itemAction` Üyesi `DRAWITEMSTRUCT` gerçekleştirilecek çizim eylemi yapısını tanımlar.

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Sahip çizim için çizim uygulamak için bu üye işlevi geçersiz kılma `CTabCtrl` nesne.

Uygulama görünen bağlam sağlanan için seçilen tüm grafik cihaz arabirimi (GDI) nesneleri geri yüklemeniz gerekir *lpDrawItemStruct* önce bu üye işlevi sonlandırır.

##  <a name="getcurfocus"></a>  CTabCtrl::GetCurFocus

Geçerli odak ile sekmesindeki dizinini alır.

```
int GetCurFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli odak ile sekmesindeki sıfır tabanlı dizini.

##  <a name="getcursel"></a>  CTabCtrl::GetCurSel

Şu anda seçilen sekmesi bir sekme denetimindeki alır.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili bir sekme başarılı olursa veya - 1 hiçbir sekmesi seçili değilse sıfır tabanlı dizini.

##  <a name="getextendedstyle"></a>  CTabCtrl::GetExtendedStyle

Şu anda kullanılmakta olan sekme denetimi için genişletilmiş stiller alır.

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimi için kullanılmakta genişletilmiş stiller temsil eder. Bu değer, bir bileşimidir [sekme denetimi genişletilmiş stiller](/windows/desktop/Controls/tab-control-extended-styles)Windows SDK içinde açıklandığı gibi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [TCM_GETEXTENDEDSTYLE](/windows/desktop/Controls/tcm-getextendedstyle)Windows SDK içinde açıklandığı gibi.

##  <a name="getimagelist"></a>  CTabCtrl::GetImageList

Sekme denetimiyle ilişkili görüntü listesini alır.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sekme görüntüsü listesine bir işaretçi denetler; Aksi takdirde NULL.

##  <a name="getitem"></a>  CTabCtrl::GetItem

Bir sekme denetimindeki sekme hakkındaki bilgileri alır.

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
Sekme sıfır tabanlı dizini.

*pTabCtrlItem*<br/>
İşaretçi bir [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) yapısı, alınacak bilgilerini belirtmek için kullanılır. Sekmesi hakkında bilgi almak için de kullanılır. Bu yapı kullanılır `InsertItem`, `GetItem`, ve `SetItem` üye işlevleri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sahipse TRUE değerini döndürür; FALSE Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

İleti gönderildiğinde `mask` üye döndürülecek öznitelikleri belirtir. Varsa `mask` üye TCIF_TEXT değeri belirtir `pszText` üye öğesi metni alan arabellek adresi içermelidir ve `cchTextMax` üyesi arabellek boyutu belirtin.

- `mask`

   Hangi belirten değeri `TCITEM` Yapı üyeleri alınamıyor veya ayarlanamıyor. Bu üye, sıfır veya bir birleşimi aşağıdaki değerlerden biri olabilir:

   - TCIF_TEXT `pszText` üye geçerlidir.

   - TCIF_IMAGE `iImage` üye geçerlidir.

   - TCIF_PARAM `lParam` üye geçerlidir.

   - TCIF_RTLREADING metin, `pszText` İbranice ve Arapça sistemlerinde sağdan sola okuma düzeni kullanılarak görüntülenir.

   - TCIF_STATE `dwState` üye geçerlidir.

- `pszText`

   Yapı bir sekmesi hakkında bilgi içeriyorsa sekmesini metni içeren null ile sonlandırılmış bir dize işaretçisi. Yapı bilgileri alıyorsa, bu üye sekme metnine alan arabellek adresi belirtir.

- `cchTextMax`

   Arabellek boyutu tarafından işaret edilen `pszText`. Bu üye yapısı bilgi almadığını yoksayılır.

- `iImage` Hiçbir görüntü için sekmesinde ise, sekme denetiminin resim listesi veya 1 - dizin.

- `lParam`

   Sekme ile ilişkili uygulama tanımlı veri. Sekme başına uygulama tanımlı veri dört bayttan daha fazla varsa, uygulamanın yapı tanımlamak ve yerine bunu kullanmanız gerekir `TCITEM` yapısı. Uygulama tanımlı yapısı ilk üye olmalıdır bir [TCITEMHEADER](/windows/desktop/api/commctrl/ns-commctrl-tagtcitemheadera)yapısı. `TCITEMHEADER` Yapısıdır aynı `TCITEM` olmadan, yapı `lParam` üyesi. Yapınız boyutu ve boyutu arasındaki fark `TCITEMHEADER` yapısı sekme başına ek bayt sayısına eşit.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

##  <a name="getitemcount"></a>  CTabCtrl::GetItemCount

Sekme denetimine sekmeler sayısını alır.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimi öğe sayısı.

### <a name="example"></a>Örnek

  Örneğin bakın [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="getitemrect"></a>  CTabCtrl::GetItemRect

Belirtilen bir sekme denetimindeki sekme için sınırlayıcı dikdörtgeni alır.

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
Sekme öğesi sıfır tabanlı dizini.

*lpRect*<br/>
İşaretçi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) sekmesinin dikdörtgen alan yapısı. Bu koordinatları görünüm penceresinin'ın geçerli eşleme modunu kullan.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

  Örneğin bakın [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="getitemstate"></a>  CTabCtrl::GetItemState

Sekme denetim öğesi tarafından tanımlanan durumunu alır *nItem*.

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
Durum bilgilerini almak istediğiniz öğenin sıfır tabanlı dizin numarası.

*dwMask*<br/>
Döndürülecek öğenin durumu hangisinin bayrakları belirtme maskesi. Maskesi üye değerlerinin bir listesi için bkz [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Windows SDK içinde anlatıldığı gibi yapılandırın.

### <a name="return-value"></a>Dönüş Değeri

Durum bilgileri alan bir DWORD değeri bir başvuru. Aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Sekme denetimi öğe seçilidir.|
|TCIS_HIGHLIGHTED|Sekme denetim öğesi vurgulanır ve geçerli vurgulama rengini kullanarak sekme ve metin çizilir. Vurgu rengi kullanırken, bu gerçek bir ilişkilendirme, bir Titremeli renk olacaktır.|

### <a name="remarks"></a>Açıklamalar

Bir öğenin durum tarafından belirtilen `dwState` üyesi `TCITEM` yapısı.

##  <a name="getrowcount"></a>  CTabCtrl::GetRowCount

Bir sekme denetimindeki satırları geçerli sayısını alır.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimine sekmeler satırların sayısı.

### <a name="remarks"></a>Açıklamalar

TCS_MULTILINE stili olan sekme denetimleri sekmelerin çoklu satırları olabilir.

##  <a name="gettooltips"></a>  CTabCtrl::GetToolTips

Sekme denetimiyle ilişkili araç ipucunu denetimini tanıtıcısını alır.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç İpucu denetimi başarılı olursa tanıtıcısı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bir TCS_TOOLTIPS stile sahipse Sekme denetimine bir araç ipucu denetimi oluşturur. Kullanarak bir sekme denetimine bir araç ipucunu denetimini atayabilirsiniz `SetToolTips` üye işlevi.

##  <a name="highlightitem"></a>  CTabCtrl::HighlightItem

Sekme öğesi vurgulama durumunu ayarlar.

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>Parametreler

*idItem*<br/>
Sekme denetim öğesi sıfır tabanlı dizini.

*fHighlight*<br/>
Ayarlanacak vurgulama durumunu belirten değer. Bu değer TRUE ise, sekme vurgulanır. FALSE ise sekmesi varsayılan durumuna ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti uygulayan [TCM_HIGHLIGHTITEM](/windows/desktop/Controls/tcm-highlightitem)Windows SDK içinde açıklandığı gibi.

##  <a name="hittest"></a>  CTabCtrl::HitTest

Hangi sekme varsa, belirtilen ekran konumda olduğunu belirler.

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>Parametreler

*pHitTestInfo*<br/>
İşaretçi bir [TCHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtchittestinfo) test etmek için ekran konumunu belirtir. Windows SDK içinde anlatıldığı gibi yapılandırın.

### <a name="return-value"></a>Dönüş Değeri

Sekme belirtilen konumda sekme veya - 1 sıfır tabanlı dizinini döndürür.

##  <a name="insertitem"></a>  CTabCtrl::InsertItem

Yeni bir sekme içinde var olan bir sekme denetimini ekler.

```
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam,
    DWORD dwState,
    DWORD dwStateMask);
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
Yeni sekme sıfır tabanlı dizini.

*pTabCtrlItem*<br/>
İşaretçi bir [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) sekmesini özniteliklerini belirtir yapısı.

*lpszItem*<br/>
Sekmenin metni içeren null ile sonlandırılmış bir dize adresi.

*Bir*<br/>
Görüntü listesinden görüntü eklemek için bir görüntü sıfır tabanlı dizini.

*nMask*<br/>
Belirten `TCITEM` yapısı özniteliklerini ayarlayın. Sıfır veya bir birleşimi aşağıdaki değerlerden biri olabilir:

- TCIF_TEXT `pszText` üye geçerlidir.

- TCIF_IMAGE `iImage` üye geçerlidir.

- TCIF_PARAM *lParam* üye geçerlidir.

- TCIF_RTLREADING metin, `pszText` İbranice ve Arapça sistemlerinde sağdan sola okuma düzeni kullanılarak görüntülenir.

- TCIF_STATE *dwState* üye geçerlidir.

*lParam*<br/>
Sekme ile ilişkili uygulama tanımlı veri.

*dwState*<br/>
Öğenin durumları için değerleri belirtir. Daha fazla bilgi için [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Windows SDK.

*dwStateMask*<br/>
Hangi durumları ayarlanacak belirtir. Daha fazla bilgi için [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir sekme başarılı olursa sıfır tabanlı dizini; Aksi takdirde - 1.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

##  <a name="removeimage"></a>  CTabCtrl::RemoveImage

Belirtilen görüntü bir sekme denetiminin resim listesinden kaldırır.

```
void RemoveImage(int nImage);
```

### <a name="parameters"></a>Parametreler

*Bir*<br/>
Görüntüyü kaldırmak için sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Sekme denetimi, her sekmesi aynı görüntü ile ilişkili olarak kalır, böylece her sekmenin görüntü dizini güncelleştirir.

##  <a name="setcurfocus"></a>  CTabCtrl::SetCurFocus

Belirtilen bir sekme denetimindeki sekme odağı ayarlar.

```
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
Odağı alır sekmenin dizinini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [TCM_SETCURFOCUS](/windows/desktop/Controls/tcm-setcurfocus)Windows SDK içinde açıklandığı gibi.

##  <a name="setcursel"></a>  CTabCtrl::SetCurSel

Bir sekme içinde Sekme denetimini seçer.

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
Seçilecek öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Daha önce seçilen sekmesinin başarılı olursa sıfır tabanlı dizin yoksa - 1.

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullanarak bir sekme seçildiğinde Sekme denetimine TCN_SELCHANGING veya TCN_SELCHANGE bir bildirim iletisi göndermez. Kullanıcı tıkladığında veya sekmeleri değiştirmek için klavyeyi kullanır, wm_notıfy kullanarak bu bildirimler gönderilir.

##  <a name="setextendedstyle"></a>  CTabCtrl::SetExtendedStyle

Genişletilmiş stiller sekme denetimi için ayarlar.

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>Parametreler

*dwNewStyle*<br/>
Genişletilmiş stiller sekmesi birleşimi belirten değeri kontrol eder.

*dwExMask*<br/>
Hangi stillerde gösteren bir DWORD değeri *dwNewStyle* etkilenecek olan. Yalnızca genişletilmiş stilleri *dwExMask* değiştirilecek. Diğer tüm stiller olarak korunur. Bu parametre sıfır, ardından tüm stilleri ise *dwNewStyle* etkilenecek.

### <a name="return-value"></a>Dönüş Değeri

Önceki içeren bir DWORD değeri [sekme denetimi genişletilmiş stiller](/windows/desktop/Controls/tab-control-extended-styles)Windows SDK içinde açıklandığı gibi.

### <a name="return-value"></a>Dönüş Değeri

Bu üye işlevi Win32 ileti davranışı uygulayan [TCM_SETEXTENDEDSTYLE](/windows/desktop/Controls/tcm-setextendedstyle)Windows SDK içinde açıklandığı gibi.

##  <a name="setimagelist"></a>  CTabCtrl::SetImageList

Görüntü listesi Sekme denetimine atar.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
Sekme denetimine atanan görüntü listesi için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Görüntü listesi yok ise önceki görüntü listesi veya NULL bir işaretçi döndürür.

##  <a name="setitem"></a>  CTabCtrl::SetItem

Bazılarını veya tümünü bir sekmenin öznitelikleri ayarlar.

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
Öğenin sıfır tabanlı dizini.

*pTabCtrlItem*<br/>
İşaretçi bir [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) yeni öğesi özniteliklerini içeren yapısı. `mask` Üye ayarlamak için hangi özniteliklerin belirtir. Varsa `mask` üye TCIF_TEXT değeri belirtir `pszText` üyesi null ile sonlandırılmış bir dize adresidir ve `cchTextMax` üye göz ardı edilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

  Örneğin bakın [GetItem](#getitem).

##  <a name="setitemextra"></a>  CTabCtrl::SetItemExtra

Uygulama tanımlı bir sekme denetimindeki veri için rezerve sekme başına bayt sayısını ayarlar.

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayarlamak için ek bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [TCM_SETITEMEXTRA](/windows/desktop/Controls/tcm-setitemextra)Windows SDK içinde açıklandığı gibi.

##  <a name="setitemsize"></a>  CTabCtrl::SetItemSize

Genişlik ve yükseklik sekme denetimi öğeleri ayarlar.

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Yeni genişliğini ve yüksekliğini piksel cinsinden sekme denetimi öğeleri.

### <a name="return-value"></a>Dönüş Değeri

Eski genişlik ve yükseklik sekme denetimi öğeleri döndürür.

##  <a name="setitemstate"></a>  CTabCtrl::SetItemState

Sekme denetim öğesi tarafından tanımlanan durumunu ayarlar *nItem*.

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
Durum bilgilerini ayarlanacak öğenin sıfır tabanlı dizin numarası.

*dwMask*<br/>
Maske, öğenin durumu ayarlamak için bayrakları belirtme. Maskesi üye değerlerinin bir listesi için bkz [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Windows SDK içinde anlatıldığı gibi yapılandırın.

*dwState*<br/>
Durum bilgisi içeren bir DWORD değeri bir başvuru. Aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Sekme denetimi öğe seçilidir.|
|TCIS_HIGHLIGHTED|Sekme denetim öğesi vurgulanır ve geçerli vurgulama rengini kullanarak sekme ve metin çizilir. Vurgu rengi kullanırken, bu gerçek bir ilişkilendirme, bir Titremeli renk olacaktır.|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="setmintabwidth"></a>  CTabCtrl::SetMinTabWidth

Bir sekme denetiminde öğelerin minimum genişliğini ayarlar.

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>Parametreler

*CX*<br/>
Sekme denetimi öğe için ayarlanacak minimum genişlik. Bu parametreyi -1 olarak ayarlarsanız, denetimin varsayılan sekme genişliği kullanır.

### <a name="return-value"></a>Dönüş Değeri

Önceki minimum sekme genişliği.

### <a name="return-value"></a>Dönüş Değeri

Bu üye işlevi Win32 ileti davranışı uygulayan [TCM_SETMINTABWIDTH](/windows/desktop/Controls/tcm-setmintabwidth)Windows SDK içinde açıklandığı gibi.

##  <a name="setpadding"></a>  CTabCtrl::SetPadding

(Her sekmenin simgesini ve bir sekme denetimindeki etiket doldurma) boşluk miktarını belirler.

```
void SetPadding(CSize size);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
(Her sekmenin simgesini ve bir sekme denetimindeki etiket doldurma) boşluk miktarını belirler.

##  <a name="settooltips"></a>  CTabCtrl::SetToolTips

Sekme denetimine bir araç ipucunu denetimini atar.

```
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Parametreler

*pWndTip*<br/>
Araç ipucunu denetimini tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bir çağrı yaparak bir sekme denetimiyle ilişkili araç ipucunu denetimini alabilirsiniz `GetToolTips`.

### <a name="example"></a>Örnek

  Örneğin bakın [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="see-also"></a>Ayrıca Bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CHeaderCtrl Sınıfı](../../mfc/reference/cheaderctrl-class.md)<br/>
[CListCtrl Sınıfı](../../mfc/reference/clistctrl-class.md)
