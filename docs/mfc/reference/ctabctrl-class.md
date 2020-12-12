---
description: 'Daha fazla bilgi edinin: CTabCtrl sınıfı'
title: CTabCtrl sınıfı
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
ms.openlocfilehash: 363e97ec848976b78b1c75b70997ff6f4b4b5c36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318578"
---
# <a name="ctabctrl-class"></a>CTabCtrl sınıfı

Windows ortak sekme denetimi işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CTabCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTabCtrl:: CTabCtrl](#ctabctrl)|Bir `CTabCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTabCtrl:: AdjustRect](#adjustrect)|Bir pencere dikdörtgeni verilen sekme denetiminin görüntüleme alanını hesaplar veya belirli bir görüntüleme alanına karşılık gelen pencere dikdörtgenini hesaplar.|
|[CTabCtrl:: Create](#create)|Bir sekme denetimi oluşturur ve bunu bir nesne örneğine ekler `CTabCtrl` .|
|[CTabCtrl:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir sekme denetimi oluşturur ve bunu bir nesne örneğine ekler `CTabCtrl` .|
|[CTabCtrl::D Eleteallıtems](#deleteallitems)|Bir sekme denetiminden tüm öğeleri kaldırır.|
|[CTabCtrl::D Eleteıtem](#deleteitem)|Sekme denetiminden bir öğeyi kaldırır.|
|[CTabCtrl::D eselectAll](#deselectall)|Sekme denetimindeki öğeleri sıfırlayarak, basılan denetimleri temizleyebilirsiniz.|
|[CTabCtrl::D rawItem](#drawitem)|Sekme denetiminin belirtilen bir öğesini çizer.|
|[CTabCtrl:: GetCurFocus](#getcurfocus)|Sekme denetiminin geçerli odağının sekmesini alır.|
|[CTabCtrl:: GetCurSel](#getcursel)|Sekme denetiminde seçili olan sekmeyi belirler.|
|[CTabCtrl:: Getcdedstyle](#getextendedstyle)|Sekme denetimi için kullanılmakta olan Genişletilmiş stilleri alır.|
|[CTabCtrl:: GetImageList](#getimagelist)|Bir sekme denetimiyle ilişkili resim listesini alır.|
|[CTabCtrl:: GetItem](#getitem)|Sekme denetimindeki bir sekme hakkındaki bilgileri alır.|
|[CTabCtrl:: GetItemCount](#getitemcount)|Sekme denetimindeki sekmelerin sayısını alır.|
|[CTabCtrl:: GetItemRect](#getitemrect)|Sekme denetimindeki bir sekmenin sınırlayıcı dikdörtgenini alır.|
|[CTabCtrl:: GetItemState](#getitemstate)|Belirtilen sekme denetim öğesinin durumunu alır.|
|[CTabCtrl:: GetRowCount](#getrowcount)|Sekme denetimindeki sekmelerin geçerli satır sayısını alır.|
|[CTabCtrl:: GetToolTip](#gettooltips)|Bir sekme denetimiyle ilişkili araç ipucu denetiminin tanıtıcısını alır.|
|[CTabCtrl:: HighlightItem](#highlightitem)|Bir sekme öğesinin vurgulama durumunu ayarlar.|
|[CTabCtrl:: HitTest](#hittest)|Hangi sekmenin (varsa) belirtilen ekran konumunda olduğunu belirler.|
|[CTabCtrl:: InsertItem](#insertitem)|Sekme denetimine yeni bir sekme ekler.|
|[CTabCtrl:: removeImage](#removeimage)|Sekme denetiminin görüntü listesinden bir görüntüyü kaldırır.|
|[CTabCtrl:: SetCurFocus](#setcurfocus)|Odağı sekme denetimindeki belirli bir sekmeye ayarlar.|
|[CTabCtrl:: SetCurSel](#setcursel)|Sekme denetimindeki bir sekmeyi seçer.|
|[CTabCtrl:: Setcdedstyle](#setextendedstyle)|Sekme denetimi için Genişletilmiş stilleri ayarlar.|
|[CTabCtrl:: SetImageList](#setimagelist)|Bir sekme denetimine bir görüntü listesi atar.|
|[CTabCtrl:: SetItem](#setitem)|Sekmenin özniteliklerinin bazılarını veya tümünü ayarlar.|
|[CTabCtrl:: SetItemExtra](#setitemextra)|Sekme denetimindeki uygulama tanımlı veriler için ayrılan sekme başına düşen bayt sayısını ayarlar.|
|[CTabCtrl:: Setıtemsize](#setitemsize)|Bir öğenin genişliğini ve yüksekliğini ayarlar.|
|[CTabCtrl:: SetItemState](#setitemstate)|Belirtilen sekme denetimi öğesinin durumunu ayarlar.|
|[CTabCtrl:: SetMinTabWidth](#setmintabwidth)|Bir sekme denetimindeki öğelerin en küçük genişliğini ayarlar.|
|[CTabCtrl:: SetPadding](#setpadding)|Sekme denetimindeki her sekmenin simgesinin ve etiketinin çevresindeki boşluk miktarını (Padding) ayarlar.|
|[CTabCtrl:: SetToolTip](#settooltips)|Sekme denetimine bir araç ipucu denetimi atar.|

## <a name="remarks"></a>Açıklamalar

"Sekme denetimi" bir not defterindeki bölücülerin veya dosya dolabdaki etiketlerin benzerdir. Bir uygulama bir sekme denetimi kullanarak bir pencere veya iletişim kutusunun aynı alanı için birden çok sayfa tanımlayabilir. Her sayfa bir bilgi kümesinden veya Kullanıcı ilgili sekmeyi seçtiğinde uygulamanın görüntülediği bir denetim grubundan oluşur. Özel bir sekme denetimi türü düğme gibi görünen sekmeleri görüntüler. Bir düğmeye tıklanması, bir sayfayı görüntülemek yerine hemen bir komut gerçekleştirmelidir.

Bu denetim (ve bu nedenle `CTabCtrl` sınıfı) yalnızca windows 95/98 ve WINDOWS NT sürüm 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Kullanma hakkında daha fazla bilgi için `CTabCtrl` bkz [](../../mfc/controls-mfc.md) . ve [CTabCtrl kullanma](../../mfc/using-ctabctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

## <a name="ctabctrladjustrect"></a><a name="adjustrect"></a> CTabCtrl:: AdjustRect

Bir pencere dikdörtgeni verilen sekme denetiminin görüntüleme alanını hesaplar veya belirli bir görüntüleme alanına karşılık gelen pencere dikdörtgenini hesaplar.

```cpp
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*bDaha büyük*<br/>
Hangi işlemin gerçekleştirileceğini gösterir. Bu parametre TRUE ise, *lpRect* bir görüntüleme dikdörtgeni belirtir ve ilgili pencere dikdörtgenini alır. Bu parametre FALSE ise, *lpRect* bir pencere dikdörtgeni belirtir ve ilgili görüntüleme dikdörtgenini alır.

*lpRect*<br/>
Verilen dikdörtgeni belirten ve hesaplanan dikdörtgeni alan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına yönelik işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

## <a name="ctabctrlcreate"></a><a name="create"></a> CTabCtrl:: Create

Bir sekme denetimi oluşturur ve bunu bir nesne örneğine ekler `CTabCtrl` .

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Sekme denetiminin stilini belirtir. Windows SDK açıklanan [Sekme Denetim stillerinin](/windows/win32/Controls/tab-control-styles)herhangi bir birleşimini uygulayın. Denetim için de uygulayabileceğiniz pencere stillerinin listesi için bkz. **açıklamalar** .

*Rect*<br/>
Sekme denetiminin boyutunu ve konumunu belirtir. Bu, bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Sekme denetiminin ana penceresini (genellikle a) belirtir `CDialog` . NULL olmaması gerekir.

*NID*<br/>
Sekme denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin başlatılması başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

`CTabCtrl`İki adımda bir nesne oluşturursunuz. İlk olarak, oluşturucuyu çağırın ve sonra `Create` Sekme denetimini oluşturan ve bunu nesnesine ekleyen çağırın `CTabCtrl` .

Sekme denetim stillerine ek olarak, bir sekme denetimine aşağıdaki pencere stillerini uygulayabilirsiniz:

- WS_CHILD Tab denetimini temsil eden bir alt pencere oluşturur. WS_POPUP stille birlikte kullanılamaz.

- WS_VISIBLE Başlangıçta görünür olan bir sekme denetimi oluşturur.

- WS_DISABLED başlangıçta devre dışı olan bir pencere oluşturur.

- WS_GROUP, kullanıcının ok tuşlarıyla bir denetimden diğerine taşıyabileceği bir denetim grubunun ilk denetimini belirtir. İlk denetimden sonra WS_GROUP stili ile tanımlanmış tüm denetimler aynı gruba aittir. WS_GROUP stili olan bir sonraki denetim stil grubunu sonlandırır ve sonraki grubu başlatır (yani, bir grup bir sonraki başladığı yerde sona erer).

- WS_TABSTOP, kullanıcının TAB tuşunu kullanarak taşıyabileceği birçok denetimden birini belirtir. TAB tuşu, Kullanıcı WS_TABSTOP stili tarafından belirtilen sonraki denetime taşınıyor.

Genişletilmiş pencere stilleriyle bir sekme denetimi oluşturmak için yerine [CTabCtrl:: CreateEx](#createex) çağırın `Create` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

## <a name="ctabctrlcreateex"></a><a name="createex"></a> CTabCtrl:: CreateEx

Bir denetim (alt pencere) oluşturur ve `CTabCtrl` nesneyle ilişkilendirir.

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
Oluşturulmakta olan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerinin listesi için, Windows SDK için bkz. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Için *dwExStyle* parametresi.

*dwStyle*<br/>
Sekme denetiminin stilini belirtir. Windows SDK açıklanan [Sekme Denetim stillerinin](/windows/win32/Controls/tab-control-styles)herhangi bir birleşimini uygulayın. Denetime de uygulayabileceğiniz pencere stillerinin [listesi için bkz](#create) . **açıklamalar** .

*Rect*<br/>
*PParentWnd* istemci koordinatları içinde oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*NID*<br/>
Denetimin alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır değilse 0.

### <a name="remarks"></a>Açıklamalar

`CreateEx`Windows genişletilmiş stil ön yüzü **ws_ex_** tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için [Create](#create) yerine kullanın.

`CreateEx`*dwExStyle* tarafından belirtilen Genişletilmiş Windows stilleriyle denetimi oluşturur. [Setil dedstyle](#setextendedstyle)kullanarak bir denetime özgü genişletilmiş stilleri ayarlayın. Örneğin, `CreateEx` Bu tür stilleri ws_ex_contexthelp olarak ayarlamak için kullanın, ancak `SetExtendedStyle` Bu tür stilleri TCS_EX_FLATSEPARATORS olarak ayarlamak için kullanın. Daha fazla bilgi için, Windows SDK [sekme denetimi genişletilmiş stilleri](/windows/win32/Controls/tab-control-extended-styles) bölümünde açıklanan stillere bakın.

## <a name="ctabctrlctabctrl"></a><a name="ctabctrl"></a> CTabCtrl:: CTabCtrl

Bir `CTabCtrl` nesnesi oluşturur.

```
CTabCtrl();
```

## <a name="ctabctrldeleteallitems"></a><a name="deleteallitems"></a> CTabCtrl::D Eleteallıtems

Bir sekme denetiminden tüm öğeleri kaldırır.

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

## <a name="ctabctrldeleteitem"></a><a name="deleteitem"></a> CTabCtrl::D Eleteıtem

Bir sekme denetiminden belirtilen öğeyi kaldırır.

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Silinecek öğenin sıfır tabanlı değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

## <a name="ctabctrldeselectall"></a><a name="deselectall"></a> CTabCtrl::D eselectAll

Sekme denetimindeki öğeleri sıfırlayarak, basılan denetimleri temizleyebilirsiniz.

```cpp
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>Parametreler

*fExcludeFocus*<br/>
Öğe seçiminin kapsamını belirten bayrak. Bu parametre FALSE olarak ayarlandıysa, tüm sekme düğmeleri sıfırlanır. TRUE olarak ayarlanırsa, şu anda seçili olanı hariç tüm sekme öğeleri sıfırlanır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklanan [TCM_DESELECTALL](/windows/win32/Controls/tcm-deselectall)Win32 iletisinin davranışını uygular.

## <a name="ctabctrldrawitem"></a><a name="drawitem"></a> CTabCtrl::D rawItem

Sahip çizim sekmesi denetiminin görsel bir yönü değiştiğinde Framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Boyanmış öğeyi açıklayan [Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`itemAction` `DRAWITEMSTRUCT` Yapının üyesi gerçekleştirilecek çizim eylemini tanımlar.

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bir sahip çizim nesnesi için çizimi uygulamak üzere bu üye işlevini geçersiz kılın `CTabCtrl` .

Uygulamanın, bu üye işlevi sonlandırılmadan önce *Lpdrawitemstruct* içinde sağlanan görüntüleme bağlamı için seçilen tüm grafik cihaz ARABIRIMI (GDI) nesnelerini geri yüklemesi gerekir.

## <a name="ctabctrlgetcurfocus"></a><a name="getcurfocus"></a> CTabCtrl:: GetCurFocus

Geçerli odağa sahip sekmenin dizinini alır.

```
int GetCurFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli odağa sahip sekmenin sıfır tabanlı dizini.

## <a name="ctabctrlgetcursel"></a><a name="getcursel"></a> CTabCtrl:: GetCurSel

Sekme denetimindeki seçili olan sekmeyi alır.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa seçili sekmenin sıfır tabanlı dizini veya hiçbir sekme seçilmemişse-1.

## <a name="ctabctrlgetextendedstyle"></a><a name="getextendedstyle"></a> CTabCtrl:: Getcdedstyle

Sekme denetimi için kullanılmakta olan Genişletilmiş stilleri alır.

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimi için şu anda kullanılan genişletilmiş stilleri temsil eder. Bu değer, Windows SDK açıklandığı gibi, [sekme denetimi genişletilmiş stillerinin](/windows/win32/Controls/tab-control-extended-styles)bir birleşimidir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TCM_GETEXTENDEDSTYLE](/windows/win32/Controls/tcm-getextendedstyle)davranışını uygular.

## <a name="ctabctrlgetimagelist"></a><a name="getimagelist"></a> CTabCtrl:: GetImageList

Bir sekme denetimiyle ilişkili olan görüntü listesini alır.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sekme denetiminin görüntü listesine yönelik bir işaretçi; Aksi takdirde, NULL.

## <a name="ctabctrlgetitem"></a><a name="getitem"></a> CTabCtrl:: GetItem

Sekme denetimindeki bir sekme hakkındaki bilgileri alır.

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Sekmenin sıfır tabanlı dizini.

*Ptabctrlıdıtem*<br/>
Alınacak bilgileri belirtmek için kullanılan bir [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısına yönelik işaretçi. Sekmeyle ilgili bilgi almak için de kullanılır. Bu yapı `InsertItem` ,, `GetItem` ve üye işlevleriyle birlikte kullanılır `SetItem` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE döndürür; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

İleti gönderildiğinde `mask` üye hangi özniteliklerin dönemeyeceğini belirtir. `mask`Üye TCIF_TEXT değerini belirtiyorsa `pszText` üye, öğe metnini alan arabelleğin adresini içermeli ve `cchTextMax` üyenin arabelleğin boyutunu belirtmesi gerekir.

- `mask`

   `TCITEM`Alınacak veya ayarlanacak yapı üyelerini belirten değer. Bu üye sıfır veya aşağıdaki değerlerin bir birleşimi olabilir:

  - `pszText`Üyenin geçerli TCIF_TEXT.

  - `iImage`Üyenin geçerli TCIF_IMAGE.

  - `lParam`Üyenin geçerli TCIF_PARAM.

  - TCIF_RTLREADING metin, `pszText` İbranice veya Arapça sistemler üzerinde sağdan sola okuma düzeni kullanılarak görüntülenir.

  - `dwState`Üyenin geçerli TCIF_STATE.

- `pszText`

   Yapı bir sekme hakkında bilgi içeriyorsa sekme metnini içeren, null ile sonlandırılmış bir dize işaretçisi. Yapı bilgi alıyorsa, bu üye sekme metnini alan arabelleğin adresini belirtir.

- `cchTextMax`

   Tarafından işaret edilen arabelleğin boyutu `pszText` . Yapı bilgi almadığı takdirde bu üye yok sayılır.

- `iImage` Sekme denetiminin görüntü listesinde dizin veya sekme için görüntü yoksa-1.

- `lParam`

   Sekmeyle ilişkili uygulama tanımlı veriler. Sekme başına uygulama tanımlı dört bayttan daha fazla veri varsa, bir uygulama bir yapıyı tanımlamalıdır ve yapı yerine onu kullanmalıdır `TCITEM` . Uygulama tanımlı yapının ilk üyesi bir [TCITEMHEADER](/windows/win32/api/commctrl/ns-commctrl-tcitemheaderw)yapısı olmalıdır. `TCITEMHEADER`Yapı, yapı ile aynıdır `TCITEM` , ancak üye olmadan `lParam` . Yapınızın boyutu ve yapının boyutu arasındaki fark, `TCITEMHEADER` sekme başına fazladan bayt sayısına eşit olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

## <a name="ctabctrlgetitemcount"></a><a name="getitemcount"></a> CTabCtrl:: GetItemCount

Sekme denetimindeki sekmelerin sayısını alır.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimindeki öğe sayısı.

### <a name="example"></a>Örnek

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)örneğine bakın.

## <a name="ctabctrlgetitemrect"></a><a name="getitemrect"></a> CTabCtrl:: GetItemRect

Sekme denetimindeki belirtilen sekme için sınırlayıcı dikdörtgeni alır.

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Sekme öğesinin sıfır tabanlı dizini.

*lpRect*<br/>
Sekmenin sınırlayıcı dikdörtgenini alan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına yönelik işaretçi. Bu koordinatlar görünüm penceresinin geçerli eşleme modunu kullanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)örneğine bakın.

## <a name="ctabctrlgetitemstate"></a><a name="getitemstate"></a> CTabCtrl:: GetItemState

*Nitem* tarafından tanımlanan sekme denetim öğesinin durumunu alır.

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Durum bilgilerinin alınacağı öğenin sıfır tabanlı dizin numarası.

*dwMask*<br/>
Öğenin durum bayraklarının hangisinin döndürülecek olduğunu belirten maske. Değerlerin listesi için, Windows SDK bölümünde açıklandığı gibi, [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısının maske üyesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Durum bilgilerini alan DWORD değerine bir başvuru. Aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Sekme Denetim öğesi seçilidir.|
|TCIS_HIGHLIGHTED|Sekme Denetim öğesi vurgulanır ve sekme ve metin geçerli vurgu rengi kullanılarak çizilir. Vurgu rengi kullanılırken bu, bir titremeli rengi değil, doğru bir ilişkilendirme olacaktır.|

### <a name="remarks"></a>Açıklamalar

Öğenin durumu `dwState` yapının üyesi tarafından belirtilir `TCITEM` .

## <a name="ctabctrlgetrowcount"></a><a name="getrowcount"></a> CTabCtrl:: GetRowCount

Bir sekme denetimindeki geçerli satır sayısını alır.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimindeki sekmelerin satır sayısı.

### <a name="remarks"></a>Açıklamalar

Yalnızca TCS_MULTILINE stili olan sekme denetimlerinde birden çok sekme satırı bulunabilir.

## <a name="ctabctrlgettooltips"></a><a name="gettooltips"></a> CTabCtrl:: GetToolTip

Bir sekme denetimiyle ilişkili araç ipucu denetiminin tanıtıcısını alır.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa araç ipucu denetiminin tanıtıcısı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Sekme denetimi, TCS_TOOLTIPS stiline sahipse bir araç ipucu denetimi oluşturur. Ayrıca üye işlevini kullanarak sekme denetimine bir araç ipucu denetimi atayabilirsiniz `SetToolTips` .

## <a name="ctabctrlhighlightitem"></a><a name="highlightitem"></a> CTabCtrl:: HighlightItem

Bir sekme öğesinin vurgulama durumunu ayarlar.

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>Parametreler

*Deyim*<br/>
Sekme Denetim öğesinin sıfır tabanlı dizini.

*fHighlight*<br/>
Ayarlanacak vurgu durumunu belirten değer. Bu değer TRUE ise sekme vurgulanır; FALSE ise, sekme varsayılan durumuna ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TCM_HIGHLIGHTITEM](/windows/win32/Controls/tcm-highlightitem)uygular.

## <a name="ctabctrlhittest"></a><a name="hittest"></a> CTabCtrl:: HitTest

Hangi sekmenin (varsa) belirtilen ekran konumunda olduğunu belirler.

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>Parametreler

*pHitTestInfo*<br/>
Windows SDK bölümünde açıklandığı gibi, test edilecek ekran konumunu belirten bir [Tchittestınfo](/windows/win32/api/commctrl/ns-commctrl-tchittestinfo) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sekmenin sıfır tabanlı dizinini veya belirtilen konumda hiçbir sekme yoksa-1 değerini döndürür.

## <a name="ctabctrlinsertitem"></a><a name="insertitem"></a> CTabCtrl:: InsertItem

Varolan sekme denetimine yeni bir sekme ekler.

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
Yeni sekmenin sıfır tabanlı dizini.

*Ptabctrlıdıtem*<br/>
Sekmenin özniteliklerini belirten bir [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısına yönelik işaretçi.

*lpszItem*<br/>
Sekmenin metnini içeren, null ile sonlandırılmış bir dizenin adresi.

*Ngörüntü*<br/>
Bir görüntü listesinden eklenecek görüntünün sıfır tabanlı dizini.

*nMask*<br/>
`TCITEM`Ayarlanacak yapı özniteliklerini belirtir. Sıfır veya aşağıdaki değerlerin bir birleşimi olabilir:

- `pszText`Üyenin geçerli TCIF_TEXT.

- `iImage`Üyenin geçerli TCIF_IMAGE.

- *LParam* üyesi TCIF_PARAM geçerli.

- TCIF_RTLREADING metin, `pszText` İbranice veya Arapça sistemler üzerinde sağdan sola okuma düzeni kullanılarak görüntülenir.

- *DwState* üyesi TCIF_STATE geçerli.

*lParam*<br/>
Sekmeyle ilişkili uygulama tanımlı veriler.

*dwState*<br/>
Öğe durumlarının değerlerini belirtir. Daha fazla bilgi için bkz. Windows SDK [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) .

*dwStateMask*<br/>
Hangi durumların ayarlanacağını belirtir. Daha fazla bilgi için bkz. Windows SDK [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yeni sekmenin sıfır tabanlı dizini; Aksi takdirde-1.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

## <a name="ctabctrlremoveimage"></a><a name="removeimage"></a> CTabCtrl:: removeImage

Belirtilen görüntüyü sekme denetiminin görüntü listesinden kaldırır.

```cpp
void RemoveImage(int nImage);
```

### <a name="parameters"></a>Parametreler

*Ngörüntü*<br/>
Kaldırılacak görüntünün sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Sekme denetimi her sekmenin görüntü dizinini güncelleştirir, böylece her sekme aynı görüntüyle ilişkilendirilmeye devam eder.

## <a name="ctabctrlsetcurfocus"></a><a name="setcurfocus"></a> CTabCtrl:: SetCurFocus

Odağı sekme denetimindeki belirli bir sekmeye ayarlar.

```cpp
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Odağı alan sekmenin dizinini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TCM_SETCURFOCUS](/windows/win32/Controls/tcm-setcurfocus)davranışını uygular.

## <a name="ctabctrlsetcursel"></a><a name="setcursel"></a> CTabCtrl:: SetCurSel

Sekme denetimindeki bir sekmeyi seçer.

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Seçilecek öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, daha önce seçilen sekmenin sıfır tabanlı dizini; Aksi takdirde-1.

### <a name="remarks"></a>Açıklamalar

Bu işlev kullanılarak sekme seçildiğinde sekme denetimi bir TCN_SELCHANGING veya TCN_SELCHANGE bildirim iletisi göndermez. Bu bildirimler, Kullanıcı sekmeleri değiştirmek için klavyeyi tıklattığında veya kullandığında WM_NOTIFY kullanılarak gönderilir.

## <a name="ctabctrlsetextendedstyle"></a><a name="setextendedstyle"></a> CTabCtrl:: Setcdedstyle

Sekme denetimi için Genişletilmiş stilleri ayarlar.

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>Parametreler

*dwNewStyle*<br/>
Sekme denetimi genişletilmiş stillerinin birleşimini belirten değer.

*dwExMask*<br/>
*DwNewStyle* içindeki hangi stillerin etkileneceğini BELIRTEN bir DWORD değeri. Yalnızca *dwExMask* içindeki genişletilmiş stiller değiştirilecek. Diğer tüm stiller olduğu gibi korunur. Bu parametre sıfırsa, *dwNewStyle* içindeki tüm stiller etkilenecektir.

### <a name="return-value"></a>Dönüş Değeri

Windows SDK bölümünde açıklandığı gibi, önceki [sekme denetimi genişletilmiş stillerini](/windows/win32/Controls/tab-control-extended-styles)IÇEREN bir DWORD değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TCM_SETEXTENDEDSTYLE](/windows/win32/Controls/tcm-setextendedstyle)davranışını uygular.

## <a name="ctabctrlsetimagelist"></a><a name="setimagelist"></a> CTabCtrl:: SetImageList

Bir sekme denetimine bir görüntü listesi atar.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
Sekme denetimine Atanacak görüntü listesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Önceki resim listesi için bir işaretçi veya önceki görüntü listesi yoksa NULL değerini döndürür.

## <a name="ctabctrlsetitem"></a><a name="setitem"></a> CTabCtrl:: SetItem

Sekmenin özniteliklerinin bazılarını veya tümünü ayarlar.

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Öğenin sıfır tabanlı dizini.

*Ptabctrlıdıtem*<br/>
Yeni öğe özniteliklerini içeren bir [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısına yönelik işaretçi. `mask`Üye hangi özniteliklerin ayarlanacağını belirler. `mask`Üye TCIF_TEXT değerini belirtiyorsa `pszText` üye, null ile sonlandırılmış bir dizenin adresidir ve `cchTextMax` üye yok sayılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

  [GetItem](#getitem)örneğine bakın.

## <a name="ctabctrlsetitemextra"></a><a name="setitemextra"></a> CTabCtrl:: SetItemExtra

Sekme denetimindeki uygulama tanımlı veriler için ayrılan sekme başına düşen bayt sayısını ayarlar.

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayarlanacak fazladan bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TCM_SETITEMEXTRA](/windows/win32/Controls/tcm-setitemextra)davranışını uygular.

## <a name="ctabctrlsetitemsize"></a><a name="setitemsize"></a> CTabCtrl:: Setıtemsize

Sekme Denetim öğelerinin genişliğini ve yüksekliğini ayarlar.

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Sekme Denetim öğelerinin piksel cinsinden yeni genişlik ve yükseklik.

### <a name="return-value"></a>Dönüş Değeri

Sekme Denetim öğelerinin eski genişliğini ve yüksekliğini döndürür.

## <a name="ctabctrlsetitemstate"></a><a name="setitemstate"></a> CTabCtrl:: SetItemState

*Nitem* tarafından tanımlanan sekme denetim öğesinin durumunu ayarlar.

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Durum bilgilerinin ayarlanacağı öğenin sıfır tabanlı dizin numarası.

*dwMask*<br/>
Öğenin hangi durum bayraklarının ayarlanacağını belirten maske. Değerlerin listesi için, Windows SDK bölümünde açıklandığı gibi, [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısının maske üyesine bakın.

*dwState*<br/>
Durum bilgilerini içeren bir DWORD değerine başvuru. Aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Sekme Denetim öğesi seçilidir.|
|TCIS_HIGHLIGHTED|Sekme Denetim öğesi vurgulanır ve sekme ve metin geçerli vurgu rengi kullanılarak çizilir. Vurgu rengi kullanılırken bu, bir titremeli rengi değil, doğru bir ilişkilendirme olacaktır.|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

## <a name="ctabctrlsetmintabwidth"></a><a name="setmintabwidth"></a> CTabCtrl:: SetMinTabWidth

Bir sekme denetimindeki öğelerin en küçük genişliğini ayarlar.

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>Parametreler

*yazmaç*<br/>
Sekme Denetim öğesi için ayarlanacak en düşük Genişlik. Bu parametre-1 olarak ayarlanırsa, denetim varsayılan sekme genişliğini kullanır.

### <a name="return-value"></a>Dönüş Değeri

Önceki minimum sekme genişliği.

### <a name="return-value"></a>Dönüş Değeri

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TCM_SETMINTABWIDTH](/windows/win32/Controls/tcm-setmintabwidth)davranışını uygular.

## <a name="ctabctrlsetpadding"></a><a name="setpadding"></a> CTabCtrl:: SetPadding

Sekme denetimindeki her sekmenin simgesinin ve etiketinin çevresindeki boşluk miktarını (Padding) ayarlar.

```cpp
void SetPadding(CSize size);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Sekme denetimindeki her sekmenin simgesinin ve etiketinin çevresindeki boşluk miktarını (Padding) ayarlar.

## <a name="ctabctrlsettooltips"></a><a name="settooltips"></a> CTabCtrl:: SetToolTip

Sekme denetimine bir araç ipucu denetimi atar.

```cpp
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Parametreler

*pWndTip*<br/>
Araç ipucu denetiminin tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

' A çağrı yaparak bir sekme denetimiyle ilişkili araç ipucu denetimini alabilirsiniz `GetToolTips` .

### <a name="example"></a>Örnek

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CHeaderCtrl sınıfı](../../mfc/reference/cheaderctrl-class.md)<br/>
[CListCtrl sınıfı](../../mfc/reference/clistctrl-class.md)
