---
title: CTabCtrl Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 42d4b24222b1760bc418e904881edb2bb0e5a1f4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752314"
---
# <a name="ctabctrl-class"></a>CTabCtrl Sınıfı

Windows ortak sekme denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CTabCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CTabCtrl::CTabCtrl](#ctabctrl)|Bir `CTabCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTabCtrl::Rect'i ayarla](#adjustrect)|Bir pencere dikdörtgeni verilen bir sekme denetiminin görüntü alanını hesaplar veya belirli bir görüntüleme alanına karşılık gelecek pencere dikdörtgenini hesaplar.|
|[CTabCtrl::Oluştur](#create)|Sekme denetimi oluşturur ve nesnenin `CTabCtrl` bir örneğine bağlar.|
|[CTabCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir sekme denetimi oluşturur ve `CTabCtrl` bir nesnenin bir örneğine bağlar.|
|[CTabCtrl::DeleteTüm Öğeler](#deleteallitems)|Sekme denetiminden tüm öğeleri kaldırır.|
|[CTabCtrl::DeleteItem](#deleteitem)|Bir öğeyi sekme denetiminden kaldırır.|
|[CTabCtrl::DeselectAll](#deselectall)|Bir sekme denetimindeki öğeleri sıfırlar ve basıldığındakileri temizler.|
|[CTabCtrl::DrawItem](#drawitem)|Sekme denetiminin belirli bir öğesini çizer.|
|[CTabCtrl::GetCurFocus](#getcurfocus)|Sekmeyi sekme denetiminin geçerli odağıyla alır.|
|[CTabCtrl::GetCurSel](#getcursel)|Sekme denetiminde şu anda seçili sekmeyi belirler.|
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Sekme denetimi için şu anda kullanılmakta olan genişletilmiş stilleri alır.|
|[CTabCtrl::GetImageList](#getimagelist)|Sekme denetimiyle ilişkili resim listesini alır.|
|[CTabCtrl::GetItem](#getitem)|Sekme denetimindeki sekme yle ilgili bilgileri alır.|
|[CTabCtrl::GetItemCount](#getitemcount)|Sekme denetimindeki sekme sayısını alır.|
|[CTabCtrl::GetItemRect](#getitemrect)|Sekme denetimindeki bir sekme için sınırlayıcı dikdörtgeni alır.|
|[CTabCtrl::GetItemState](#getitemstate)|Belirtilen sekme denetim öğesinin durumunu alır.|
|[CTabCtrl::GetRowCount](#getrowcount)|Sekme denetiminde geçerli sekme satır sayısını alır.|
|[CTabCtrl::GetToolİpuçları](#gettooltips)|Sekme denetimiyle ilişkili takım ipucu denetiminin tutamacını alır.|
|[CTabCtrl::Vurgu Öğesi](#highlightitem)|Sekme öğesinin vurgu durumunu ayarlar.|
|[CTabCtrl::HitTest](#hittest)|Varsa hangi sekmenin belirli bir ekran konumunda olduğunu belirler.|
|[CTabCtrl::InsertItem](#insertitem)|Sekme denetimine yeni bir sekme ekler.|
|[CTabCtrl::Görüntüyü Kaldır](#removeimage)|Bir sekme denetiminin resim listesinden görüntüyü kaldırır.|
|[CTabCtrl::SetCurFocus](#setcurfocus)|Odak noktasını sekme denetiminde belirli bir sekmeye ayarlar.|
|[CTabCtrl::SetCurSel](#setcursel)|Sekme denetiminde bir sekme seçer.|
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Sekme denetimi için genişletilmiş stilleri ayarlar.|
|[CTabCtrl::SetImageList](#setimagelist)|Bir sekme denetimine resim listesi atar.|
|[CTabCtrl::SetItem](#setitem)|Sekmeözlerinin bazılarını veya tümlerini ayarlar.|
|[CTabCtrl::SetItemExtra](#setitemextra)|Sekme denetiminde uygulama tanımlı veriler için ayrılmış sekme başına bayt sayısını ayarlar.|
|[CTabCtrl::SetItemSize](#setitemsize)|Bir öğenin genişliğini ve yüksekliğini ayarlar.|
|[CTabCtrl::SetItemState](#setitemstate)|Belirtilen sekme denetim öğesinin durumunu ayarlar.|
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|Sekme denetimindeki öğelerin minimum genişliğini ayarlar.|
|[CTabCtrl::SetPadding](#setpadding)|Sekme denetiminde her sekenin simgesinin ve etiketinin etrafındaki alan (dolgu) miktarını ayarlar.|
|[CTabCtrl::SetToolİpuçları](#settooltips)|Bir sekme denetimine bir araç ipucu denetimi atar.|

## <a name="remarks"></a>Açıklamalar

"Sekme denetimi" not defterindeki bölücülere veya dosya dolabındaki etiketlere benzer. Bir sekme denetimi kullanarak, bir uygulama pencere veya iletişim kutusunun aynı alanı için birden çok sayfa tanımlayabilir. Her sayfa, kullanıcı ilgili sekmeyi seçtiğinde uygulamanın görüntülenebilen bir bilgi kümesi veya denetim ler grubundan oluşur. Özel bir sekme denetimi türü, düğmelere benzeyen sekmeleri görüntüler. Bir düğmeyi tıklatmak, sayfa görüntülemek yerine hemen bir komut gerçekleştirmelidir.

Bu denetim (ve `CTabCtrl` bu nedenle sınıf) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Kullanma `CTabCtrl`hakkında daha fazla bilgi [Using CTabCtrl](../../mfc/using-ctabctrl.md)için, [bkz.](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="ctabctrladjustrect"></a><a name="adjustrect"></a>CTabCtrl::Rect'i ayarla

Bir pencere dikdörtgeni verilen bir sekme denetiminin görüntü alanını hesaplar veya belirli bir görüntüleme alanına karşılık gelecek pencere dikdörtgenini hesaplar.

```cpp
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*bBüyük*<br/>
Hangi işlemin gerçekleştiriltini gösterir. Bu parametre TRUE ise, *lpRect* bir ekran dikdörtgeni belirtir ve ilgili pencere dikdörtgenini alır. Bu parametre FALSE ise, *lpRect* bir pencere dikdörtgeni belirtir ve ilgili ekran dikdörtgenini alır.

*Lprect*<br/>
Verilen dikdörtgeni belirten ve hesaplanan dikdörtgeni alan bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

## <a name="ctabctrlcreate"></a><a name="create"></a>CTabCtrl::Oluştur

Sekme denetimi oluşturur ve nesnenin `CTabCtrl` bir örneğine bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Sekme denetiminin stilini belirtir. Windows SDK'da açıklanan [sekme denetim stillerinin](/windows/win32/Controls/tab-control-styles)herhangi bir birleşimini uygulayın. Denetime de uygulayabileceğiniz pencere stilleri listesi için **Açıklamalar'a** bakın.

*Rect*<br/>
Sekme denetiminin boyutunu ve konumunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Sekme denetiminin üst penceresini belirtir, `CDialog`genellikle bir . NULL olmamalıdır.

*Nıd*<br/>
Sekme denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin başlatılması başarılı olduysa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CTabCtrl` iki adımda inşa ee. Önce oluşturucuyu çağırın, `Create`sonra sekme denetimini oluşturan ve `CTabCtrl` nesneye iliştiren , çağırın.

Sekme denetim stillerine ek olarak, sekme denetimine aşağıdaki pencere stillerini uygulayabilirsiniz:

- WS_CHILD Sekme denetimini temsil eden bir alt pencere oluşturur. WS_POPUP stili ile kullanılamaz.

- WS_VISIBLE Başlangıçta görünür bir sekme denetimi oluşturur.

- WS_DISABLED Başlangıçta devre dışı bırakılmış bir pencere oluşturur.

- WS_GROUP Kullanıcının ok tuşları yla bir denetimden diğerine geçebileceği bir denetim grubunun ilk denetimini belirtir. İlk denetimden sonra WS_GROUP stili ile tanımlanan tüm denetimler aynı gruba aittir. stil WS_GROUP sonraki denetim stil grubunu sona erdirer ve bir sonraki grubu başlatır (diğer bir grup bir sonrakinin başladığı yerde biter).

- WS_TABSTOP Kullanıcının TAB tuşunu kullanarak hareket edebileceği herhangi bir sayıdadenetimden birini belirtir. TAB tuşu kullanıcıyı WS_TABSTOP stili tarafından belirtilen bir sonraki denetime taşır.

Genişletilmiş pencere stillerine sahip bir sekme denetimi oluşturmak için [CTabCtrl::CreateEx](#createex) yerine `Create`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

## <a name="ctabctrlcreateex"></a><a name="createex"></a>CTabCtrl::CreateEx

Denetim (alt pencere) oluşturur ve `CTabCtrl` nesneyle ilişkilendirir.

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
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerilistesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) için *dwExStyle* parametreye bakın.

*Dwstyle*<br/>
Sekme denetiminin stilini belirtir. Windows SDK'da açıklanan [sekme denetim stillerinin](/windows/win32/Controls/tab-control-styles)herhangi bir birleşimini uygulayın. Denetime de uygulayabileceğiniz pencere stilleri listesi için [Oluştur'daki](#create) **Açıklamalar'a** bakın.

*Rect*<br/>
*PParentWnd*istemci koordinatlarında oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencereye işaretçi.

*Nıd*<br/>
Denetimin alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Nonzero aksi takdirde başarılı 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş stil önsöz **WS_EX_** tarafından belirtilen genişletilmiş Windows stilleri uygulamak için [Oluştur](#create) yerine kullanın.

`CreateEx`*dwExStyle*tarafından belirtilen genişletilmiş Windows stilleri ile denetim oluşturur. [SetExtendedStyle'ı](#setextendedstyle)kullanarak denetime özgü genişletilmiş stilleri ayarlayın. Örneğin, WS_EX_CONTEXTHELP `CreateEx` gibi stilleri ayarlamak için `SetExtendedStyle` kullanın, ancak TCS_EX_FLATSEPARATORS gibi stilleri ayarlamak için kullanın. Daha fazla bilgi için, Windows SDK'da [Sekme Denetimi Genişletilmiş Stilleri'nde](/windows/win32/Controls/tab-control-extended-styles) açıklanan stillere bakın.

## <a name="ctabctrlctabctrl"></a><a name="ctabctrl"></a>CTabCtrl::CTabCtrl

Bir `CTabCtrl` nesne inşa eder.

```
CTabCtrl();
```

## <a name="ctabctrldeleteallitems"></a><a name="deleteallitems"></a>CTabCtrl::DeleteTüm Öğeler

Sekme denetiminden tüm öğeleri kaldırır.

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="ctabctrldeleteitem"></a><a name="deleteitem"></a>CTabCtrl::DeleteItem

Belirtilen öğeyi sekme denetiminden kaldırır.

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Silmek için öğenin sıfır tabanlı değeri.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

## <a name="ctabctrldeselectall"></a><a name="deselectall"></a>CTabCtrl::DeselectAll

Bir sekme denetimindeki öğeleri sıfırlar ve basıldığındakileri temizler.

```cpp
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>Parametreler

*fExcludeFocus*<br/>
Öğe nin seçimini belirten bayrak. Bu parametre FALSE olarak ayarlanırsa, tüm sekme düğmeleri sıfırlanır. TRUE olarak ayarlanırsa, şu anda seçili olan dışında tüm sekme öğeleri sıfırlanır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/tcm-deselectall)iletisinin TCM_DESELECTALL davranışını uygular.

## <a name="ctabctrldrawitem"></a><a name="drawitem"></a>CTabCtrl::DrawItem

Bir sahibi-beraberlik sekmesi denetiminin görsel bir yönü değiştiğinde çerçeve tarafından çağrılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Boyanacak öğeyi açıklayan [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına işaretçi.

### <a name="remarks"></a>Açıklamalar

Yapının `itemAction` `DRAWITEMSTRUCT` üyesi, gerçekleştirilecek çizim eylemini tanımlar.

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bir sahip çizim `CTabCtrl` nesnesi için çizim uygulamak için bu üye işlevi geçersiz kılın.

Uygulama, bu üye işlev sona erdirilmeden önce *lpDrawItemStruct'ta* sağlanan ekran bağlamı için seçilen tüm grafik aygıtı arabirimi (GDI) nesnelerini geri yüklemelidir.

## <a name="ctabctrlgetcurfocus"></a><a name="getcurfocus"></a>CTabCtrl::GetCurFocus

Geçerli odakla sekme dizini alır.

```
int GetCurFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli odakla sekmenin sıfır tabanlı dizini.

## <a name="ctabctrlgetcursel"></a><a name="getcursel"></a>CTabCtrl::GetCurSel

Sekme denetiminde şu anda seçili sekmeyi alır.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa seçili sekmenin sıfır tabanlı dizini veya - 1 sekmesi seçili değilse.

## <a name="ctabctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CTabCtrl::GetExtendedStyle

Sekme denetimi için şu anda kullanılmakta olan genişletilmiş stilleri alır.

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimi için şu anda kullanılmakta olan genişletilmiş stilleri temsil eder. Bu değer, Windows SDK'da açıklandığı gibi [sekme denetimi genişletilmiş stillerinin](/windows/win32/Controls/tab-control-extended-styles)bir birleşimidir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/tcm-getextendedstyle)iletisinin TCM_GETEXTENDEDSTYLE davranışını uygular.

## <a name="ctabctrlgetimagelist"></a><a name="getimagelist"></a>CTabCtrl::GetImageList

Sekme denetimiyle ilişkili resim listesini alır.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sekme denetiminin resim listesine bir işaretçi; aksi takdirde, NULL.

## <a name="ctabctrlgetitem"></a><a name="getitem"></a>CTabCtrl::GetItem

Sekme denetimindeki sekme yle ilgili bilgileri alır.

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Sekmesıfır tabanlı dizin.

*pTabCtrlItem*<br/>
TcITEM [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısıiçin işaretçi, almak için bilgileri belirtmek için kullanılır. Sekme hakkında bilgi almak için de kullanılır. Bu yapı `InsertItem`, `GetItem`, ve `SetItem` üye işlevler ile kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE döndürür; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

İleti gönderildiğinde, `mask` üye hangi özniteliklerin döndürülecek olduğunu belirtir. `mask` Üye TCIF_TEXT değerini belirtirse, `pszText` üye nin öğe metnini alan arabelleğe adresini `cchTextMax` içermesi ve üyenin arabellin boyutunu belirtmesi gerekir.

- `mask`

   Hangi yapı `TCITEM` üyelerinin alınveya ayarlanacak larını belirten değer. Bu üye sıfır veya aşağıdaki değerlerin bir kombinasyonu olabilir:

  - TCIF_TEXT `pszText` Üye geçerlidir.

  - TCIF_IMAGE `iImage` Üye geçerlidir.

  - TCIF_PARAM `lParam` Üye geçerlidir.

  - TCIF_RTLREADING Metni `pszText` İbranice veya Arapça sistemlerde sağdan sola okuma sırası kullanılarak görüntülenir.

  - TCIF_STATE `dwState` Üye geçerlidir.

- `pszText`

   Yapı bir sekme hakkında bilgi içeriyorsa, sekme metnini içeren null-sonlandırılan dize işaretçisi. Yapı bilgi alıyorsa, bu üye sekme metnini alan arabelleğe adresini belirtir.

- `cchTextMax`

   Tarafından işaret edilen arabelleğe `pszText`boyutu. Yapı bilgi almuyorsa bu üye yoksayılır.

- `iImage`Sekme denetiminin resim listesine dizin veya - 1 sekmesi için resim yoksa.

- `lParam`

   Sekmeyle ilişkili uygulama tanımlı veriler. Sekme başına dört bayttan fazla uygulama tanımlı veri varsa, bir uygulama bir `TCITEM` yapı tanımlamalı ve yapı yerine onu kullanmalıdır. Uygulama tanımlı yapının ilk üyesi bir [TCITEMHEADER](/windows/win32/api/commctrl/ns-commctrl-tcitemheaderw)yapısı olmalıdır. Yapı `TCITEMHEADER` `TCITEM` yapısı ile aynıdır, ancak `lParam` üye olmadan. Yapınızın boyutu ile `TCITEMHEADER` yapının boyutu arasındaki fark, sekme başına fazladan bayt sayısına eşit olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

## <a name="ctabctrlgetitemcount"></a><a name="getitemcount"></a>CTabCtrl::GetItemCount

Sekme denetimindeki sekme sayısını alır.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimindeki öğe sayısı.

### <a name="example"></a>Örnek

  CPropertySheet için örneğe [bakın:GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctabctrlgetitemrect"></a><a name="getitemrect"></a>CTabCtrl::GetItemRect

Sekme denetiminde belirtilen sekme için sınırlayıcı dikdörtgeni alır.

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Sekme öğesinin sıfır tabanlı dizin.

*Lprect*<br/>
Sekmenin sınırlayıcı dikdörtgenini alan bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına işaretçi. Bu koordinatlar, viewport'un geçerli eşleme modunu kullanır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

  CPropertySheet için örneğe [bakın:GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctabctrlgetitemstate"></a><a name="getitemstate"></a>CTabCtrl::GetItemState

*nItem*tarafından tanımlanan sekme denetim öğesinin durumunu alır.

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Durum bilgilerini almak için öğenin sıfır tabanlı dizin numarası.

*Dwmask*<br/>
Maske, öğenin durum bayraklarından hangisinin döndürülecek olduğunu belirtir. Değerler listesi için, Windows SDK'da açıklandığı gibi [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısının maske üyesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Durum bilgilerini alan bir DWORD değerine başvuru. Aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Sekme denetim öğesi seçilir.|
|TCIS_HIGHLIGHTED|Sekme denetim öğesi vurgulanır ve sekme ve metin geçerli vurgu rengi kullanılarak çizilir. Vurgu lu renk kullanırken, bu gerçek bir enterpolasyon değil, bir dithered renk olacaktır.|

### <a name="remarks"></a>Açıklamalar

Bir öğenin durumu `dwState` `TCITEM` yapının üyesi tarafından belirtilir.

## <a name="ctabctrlgetrowcount"></a><a name="getrowcount"></a>CTabCtrl::GetRowCount

Sekme denetiminde geçerli satır sayısını alır.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimindeki sekme satırlarının sayısı.

### <a name="remarks"></a>Açıklamalar

Yalnızca TCS_MULTILINE stiline sahip sekme denetimlerinde birden çok sekme satırı olabilir.

## <a name="ctabctrlgettooltips"></a><a name="gettooltips"></a>CTabCtrl::GetToolİpuçları

Sekme denetimiyle ilişkili takım ipucu denetiminin tutamacını alır.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa takım ucu denetiminin tutamacı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Sekme denetimi, TCS_TOOLTIPS stili varsa bir araç ipucu denetimi oluşturur. Ayrıca, üye işlevini kullanarak bir sekme denetimine `SetToolTips` bir araç ipucu denetimi atayabilirsiniz.

## <a name="ctabctrlhighlightitem"></a><a name="highlightitem"></a>CTabCtrl::Vurgu Öğesi

Sekme öğesinin vurgu durumunu ayarlar.

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>Parametreler

*idÖğe*<br/>
Sekme denetim öğesinin sıfır tabanlı dizini.

*fHighlight*<br/>
Ayarlanacak vurgu durumunu belirten değer. Bu değer TRUE ise, sekme vurgulanır; FALSE ise, sekme varsayılan durumuna ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisini [TCM_HIGHLIGHTITEM](/windows/win32/Controls/tcm-highlightitem)uygular.

## <a name="ctabctrlhittest"></a><a name="hittest"></a>CTabCtrl::HitTest

Varsa hangi sekmenin belirtilen ekran konumunda olduğunu belirler.

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>Parametreler

*pHitTestInfo*<br/>
Test etmek için ekran konumunu belirten Windows SDK'da açıklandığı gibi, [TCHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-tchittestinfo) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konumda sekme yoksa sekme veya - 1'in sıfır tabanlı dizinini döndürür.

## <a name="ctabctrlinsertitem"></a><a name="insertitem"></a>CTabCtrl::InsertItem

Varolan bir sekme denetimine yeni bir sekme ekler.

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

*nÖğe*<br/>
Yeni sekmesıfır tabanlı dizin.

*pTabCtrlItem*<br/>
Sekme özniteliklerini belirten bir [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısı için işaretçi.

*lpszItem*<br/>
Sekme metnini içeren null-sonlandırılan dize adresi.

*nImage*<br/>
Görüntü listesinden eklenecek görüntünün sıfır tabanlı dizini.

*nMask*<br/>
Hangi `TCITEM` yapı özniteliklerinin ayarlanacağa göre belirlenecek. Sıfır veya aşağıdaki değerlerin bir leşimi olabilir:

- TCIF_TEXT `pszText` Üye geçerlidir.

- TCIF_IMAGE `iImage` Üye geçerlidir.

- TCIF_PARAM *LParam* üyesi geçerlidir.

- TCIF_RTLREADING Metni `pszText` İbranice veya Arapça sistemlerde sağdan sola okuma sırası kullanılarak görüntülenir.

- TCIF_STATE *DwState* üyesi geçerlidir.

*Lparam*<br/>
Sekmeyle ilişkili uygulama tanımlı veriler.

*dwState*<br/>
Maddenin durumları için değerleri belirtir. Daha fazla bilgi için Windows SDK'daki [TCITEM'e](/windows/win32/api/commctrl/ns-commctrl-tcitemw) bakın.

*dwStateMask*<br/>
Hangi durumların ayarlaneceğini belirtir. Daha fazla bilgi için Windows SDK'daki [TCITEM'e](/windows/win32/api/commctrl/ns-commctrl-tcitemw) bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yeni sekmesıfır tabanlı dizin; aksi takdirde - 1.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

## <a name="ctabctrlremoveimage"></a><a name="removeimage"></a>CTabCtrl::Görüntüyü Kaldır

Belirtilen görüntüyü sekme denetiminin resim listesinden kaldırır.

```cpp
void RemoveImage(int nImage);
```

### <a name="parameters"></a>Parametreler

*nImage*<br/>
Görüntünün sıfır tabanlı dizini kaldırmak için.

### <a name="remarks"></a>Açıklamalar

Sekme denetimi, her sekenin görüntü dizini yle ilişkili kalması için güncelleştirir.

## <a name="ctabctrlsetcurfocus"></a><a name="setcurfocus"></a>CTabCtrl::SetCurFocus

Odak noktasını sekme denetiminde belirli bir sekmeye ayarlar.

```cpp
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Odağı alan sekme dizini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TCM_SETCURFOCUS](/windows/win32/Controls/tcm-setcurfocus)davranışını uygular.

## <a name="ctabctrlsetcursel"></a><a name="setcursel"></a>CTabCtrl::SetCurSel

Sekme denetiminde bir sekme seçer.

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Seçilecek öğenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, aksi takdirde daha önce seçilen sekme sıfır tabanlı dizin - 1.

### <a name="remarks"></a>Açıklamalar

Sekme denetimi, bu işlevi kullanarak bir sekme seçildiğinde TCN_SELCHANGING veya TCN_SELCHANGE bildirim iletisi göndermez. Bu bildirimler, kullanıcı sekmeleri değiştirmek için klavyeyi tıkladığında veya kullandığında, WM_NOTIFY kullanılarak gönderilir.

## <a name="ctabctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CTabCtrl::SetExtendedStyle

Sekme denetimi için genişletilmiş stilleri ayarlar.

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>Parametreler

*dwNewStyle*<br/>
Sekme denetimi genişletilmiş stillerin bir birleşimini belirten değer.

*dwExMask*<br/>
*dwNewStyle'daki* hangi stillerin etkileneceğini gösteren bir DWORD değeri. Sadece *dwExMask* genişletilmiş stilleri değiştirilecektir. Diğer tüm stiller olduğu gibi korunacaktır. Bu parametre sıfırise, *dwNewStyle'daki* tüm stiller etkilenir.

### <a name="return-value"></a>Dönüş Değeri

Windows SDK'da açıklandığı gibi, önceki [sekme denetimi genişletilmiş stilleri](/windows/win32/Controls/tab-control-extended-styles)içeren bir DWORD değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/tcm-setextendedstyle)iletisinin TCM_SETEXTENDEDSTYLE davranışını uygular.

## <a name="ctabctrlsetimagelist"></a><a name="setimagelist"></a>CTabCtrl::SetImageList

Bir sekme denetimine resim listesi atar.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
Sekme denetimine atanacak resim listesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Önceki resim listesi yoksa bir işaretçiyi önceki resim listesine veya NULL'a döndürür.

## <a name="ctabctrlsetitem"></a><a name="setitem"></a>CTabCtrl::SetItem

Sekmeözlerinin bazılarını veya tümlerini ayarlar.

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Maddenin sıfır tabanlı dizin.

*pTabCtrlItem*<br/>
Yeni madde özniteliklerini içeren bir [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısıiçin işaretçi. Üye `mask` hangi öznitelikleri ayarlamak için belirtir. `mask` Üye TCIF_TEXT değerini belirtirse, `pszText` üye geçersiz bir dize adresidir `cchTextMax` ve üye yoksayılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

  [GetItem](#getitem)örneğine bakın.

## <a name="ctabctrlsetitemextra"></a><a name="setitemextra"></a>CTabCtrl::SetItemExtra

Sekme denetiminde uygulama tanımlı veriler için ayrılmış sekme başına bayt sayısını ayarlar.

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>Parametreler

*nBayt*<br/>
Ayarlanan ekstra bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TCM_SETITEMEXTRA](/windows/win32/Controls/tcm-setitemextra)davranışını uygular.

## <a name="ctabctrlsetitemsize"></a><a name="setitemsize"></a>CTabCtrl::SetItemSize

Sekme denetim öğelerinin genişliğini ve yüksekliğini ayarlar.

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Sekme denetim öğelerinin piksellerde yeni genişliği ve yüksekliği.

### <a name="return-value"></a>Dönüş Değeri

Sekme denetim öğelerinin eski genişliğini ve yüksekliğini döndürür.

## <a name="ctabctrlsetitemstate"></a><a name="setitemstate"></a>CTabCtrl::SetItemState

*nItem*tarafından tanımlanan sekme denetim öğesinin durumunu ayarlar.

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Durum bilgilerini ayarlamak için maddenin sıfır tabanlı dizin numarası.

*Dwmask*<br/>
Maske, öğenin durum bayraklarından hangisinin ayarlanamasını belirtir. Değerler listesi için, Windows SDK'da açıklandığı gibi [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısının maske üyesine bakın.

*dwState*<br/>
Durum bilgilerini içeren bir DWORD değerine başvuru. Aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Sekme denetim öğesi seçilir.|
|TCIS_HIGHLIGHTED|Sekme denetim öğesi vurgulanır ve sekme ve metin geçerli vurgu rengi kullanılarak çizilir. Vurgu lu renk kullanırken, bu gerçek bir enterpolasyon değil, bir dithered renk olacaktır.|

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="ctabctrlsetmintabwidth"></a><a name="setmintabwidth"></a>CTabCtrl::SetMinTabWidth

Sekme denetimindeki öğelerin minimum genişliğini ayarlar.

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>Parametreler

*Cx*<br/>
Sekme denetim öğesi için ayarlanacak minimum genişlik. Bu parametre -1 olarak ayarlanırsa, denetim varsayılan sekme genişliğini kullanır.

### <a name="return-value"></a>Dönüş Değeri

Önceki minimum sekme genişliği.

### <a name="return-value"></a>Dönüş Değeri

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TCM_SETMINTABWIDTH](/windows/win32/Controls/tcm-setmintabwidth)davranışını uygular.

## <a name="ctabctrlsetpadding"></a><a name="setpadding"></a>CTabCtrl::SetPadding

Sekme denetiminde her sekenin simgesinin ve etiketinin etrafındaki alan (dolgu) miktarını ayarlar.

```cpp
void SetPadding(CSize size);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Sekme denetiminde her sekenin simgesinin ve etiketinin etrafındaki alan (dolgu) miktarını ayarlar.

## <a name="ctabctrlsettooltips"></a><a name="settooltips"></a>CTabCtrl::SetToolİpuçları

Bir sekme denetimine bir araç ipucu denetimi atar.

```cpp
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Parametreler

*pWndTip*<br/>
Takım ucu kontrolünün sapı.

### <a name="remarks"></a>Açıklamalar

Bir sekme denetimiile ilişkili araç ipucu denetimini. `GetToolTips`

### <a name="example"></a>Örnek

  CPropertySheet için örneğe [bakın:GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CHeaderCtrl Sınıfı](../../mfc/reference/cheaderctrl-class.md)<br/>
[CListCtrl Sınıfı](../../mfc/reference/clistctrl-class.md)
