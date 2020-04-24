---
title: CCheckListBox Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
ms.openlocfilehash: dc0e80e80d61104a4d8cb5f1cfd4e26a64c42249
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752737"
---
# <a name="cchecklistbox-class"></a>CCheckListBox Sınıfı

Windows denetim listesi kutusunun işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CCheckListBox::CCheckListBox](#cchecklistbox)|Bir `CCheckListBox` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCheckListBox::Oluştur](#create)|Windows denetim listesi kutusunu oluşturur ve `CCheckListBox` nesneye bağlar.|
|[CCheckListBox::DrawItem](#drawitem)|Bir sahip-beraberlik listesi kutusunun görsel bir yönü değiştiğinde çerçeve tarafından çağrılır.|
|[CCheckListBox::Etkinleştir](#enable)|Bir denetim listesi kutusu öğesini etkinleştirer veya devre dışı kılabilir.|
|[CCheckListBox::GetCheck](#getcheck)|Bir öğenin onay kutusunun durumunu alır.|
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Denetimin onay kutularının stilini alır.|
|[CcheckListBox::IsEnabled](#isenabled)|Öğenin etkin olup olmadığını belirler.|
|[CCheckListBox::MeasureItem](#measureitem)|Sahip çizim stiline sahip bir liste kutusu oluşturulduğunda çerçeve tarafından çağrılır.|
|[CcheckListBox::OnGetCheckPosition](#ongetcheckposition)|Bir öğenin onay kutusunun konumunu almak için çerçeve tarafından çağrılır.|
|[CCheckListBox::Setcheck](#setcheck)|Öğenin onay kutusunun durumunu ayarlar.|
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Denetimin onay kutularının stilini ayarlar.|

## <a name="remarks"></a>Açıklamalar

"Denetim listesi kutusu" dosya adları gibi öğelerin listesini görüntüler. Listedeki her öğenin yanında kullanıcının denetebileceği veya temizleyebileceği bir onay kutusu vardır.

`CCheckListBox`liste metin dizelerinden daha fazlasını içerdiğinden yalnızca sahip tarafından çizilen denetimler içindir. En basit haliyle, bir denetim listesi kutusu metin dizeleri ve onay kutuları içerir, ancak metin olması gerekmez. Örneğin, her öğenin yanında bir onay kutusu olan küçük bit eşlemlerin bir listesi olabilir.

Kendi denetim listesi kutunuzu oluşturmak için kendi sınıfınızı `CCheckListBox`. Kendi sınıftüre, türemiş sınıf için bir oluşturucu yazın, sonra çağırın. `Create`

Bir liste kutusu tarafından üst kutusuna gönderilen Windows bildirim iletilerini (genellikle [CDialog'dan](../../mfc/reference/cdialog-class.md)türetilmiş bir sınıf) işlemek istiyorsanız, her ileti için üst sınıfa bir ileti eşlemi girişi ve ileti işleyicisi üye işlevi ekleyin.

Her ileti-eş-eşlemi girişi aşağıdaki formu alır:

**ON\_**_Bildirimi_ **(** _id_, _üyeFxn_ **)**

bildirimi `id` gönderen denetimin alt pencere kimliğini belirtir `memberFxn` ve bildirimi işlemek için yazdığınız üst üye işlevinin adıdır.

Ebeveynin işlev prototipi aşağıdaki gibidir:

`afx_msg void memberFxn();`

Özellikle ilgili yalnızca bir ileti-harita girişi `CCheckListBox` vardır (ancak [CListBox](../../mfc/reference/clistbox-class.md)için ileti-eş-eş girişlerine de bakın):

- ON_CLBN_CHKCHANGE Kullanıcı bir öğenin onay kutusunun durumunu değiştirdi.

Denetim listesi kutunuz varsayılan bir denetim listesi kutusuysa (her birinin solunda varsayılan boyutlu onay kutuları olan dizeleri listesi), denetim listesi kutusunu çizmek için varsayılan [CCheckListBox::DrawItem'i](#drawitem) kullanabilirsiniz. Aksi takdirde, CListBox geçersiz kılmanız [gerekir::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) işlevi ve [CCheckListBox::DrawItem](#drawitem) ve [CCheckListListBox::MeasureItem](#measureitem) işlevleri.

Bir iletişim şablonundan veya doğrudan kodunuzda bir denetim listesi kutusu oluşturabilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Clistbox](../../mfc/reference/clistbox-class.md)

`CCheckListBox`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cchecklistboxcchecklistbox"></a><a name="cchecklistbox"></a>CCheckListBox::CCheckListBox

Bir `CCheckListBox` nesne inşa eder.

```
CCheckListBox();
```

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CCheckListBox` iki adımda inşa ee. Önce, Windows denetim `CCheckListBox`listesi `Create`kutusunu başharfleyen ve `CCheckListBox` nesneye iliştiren bir sınıf tanımlayın, sonra ara,

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

## <a name="cchecklistboxcreate"></a><a name="create"></a>CCheckListBox::Oluştur

Windows denetim listesi kutusunu oluşturur ve `CCheckListBox` nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Denetim listesi kutusunun stilini belirtir. Stil LBS_HASSTRINGS olmalı ve LBS_OWNERDRAWFIXED (listedeki tüm öğeler aynı yüksekliktedir) veya LBS_OWNERDRAWVARIABLE (listedeki öğeler değişen yüksekliklerdedir). Bu stil, LBS_USETABSTOPS hariç diğer [liste kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) ile birleştirilebilir.

*Rect*<br/>
Denetim listesi kutusu boyutunu ve konumunu belirtir. [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Denetim listesi kutusunun üst penceresini (genellikle `CDialog` bir nesne) belirtir. NULL olmamalıdır.

*Nıd*<br/>
Denetim listesi kutusunun denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CCheckListBox` iki adımda inşa ee. İlk olarak, türetilen `CcheckListBox` bir `Create`sınıf tanımlayın ve sonra arama , Windows onay `CCheckListBox`listesi kutusunu başharflerine ve . Örnek için [CCheckListBox::CCheckListBox'a](#cchecklistbox) bakın.

Yürütüldüğünde, `Create` Windows [WM_NCCREATE,](../../mfc/reference/cwnd-class.md#onnccreate) [WM_CREATE,](../../mfc/reference/cwnd-class.md#oncreate) [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) iletileri denetim kutusu denetimine gönderir.

Bu iletiler varsayılan olarak [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) üye işlevleri `CWnd` tarafından temel sınıfta işlenir. Varsayılan ileti işlemeyi genişletmek için, türemiş sınıfınıza bir ileti eşlemi ekleyin ve önceki ileti işleyicisi üye işlevlerini geçersiz kılın. Geçersiz `OnCreate`kılma , örneğin, yeni bir sınıf için gerekli başlatma gerçekleştirmek için.

Aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir denetim listesi denetimine uygulayın:

- WS_CHILD Her Zaman

- WS_VISIBLE Genellikle

- WS_DISABLED Nadiren

- WS_VSCROLL Dikey kaydırma çubuğu eklemek için

- WS_HSCROLL Yatay kaydırma çubuğu eklemek için

- WS_GROUP Denetimleri gruplandırmak için

- WS_TABSTOP Bu denetime sekme izin vermek için

## <a name="cchecklistboxdrawitem"></a><a name="drawitem"></a>CCheckListBox::DrawItem

Sahip tarafından çizilen bir onay listesi kutusunun görsel yönü değiştiğinde çerçeve tarafından çağrılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısıiçin uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`itemAction` Yapının `itemState` `DRAWITEMSTRUCT` üyeleri ve yapıları, gerçekleştirilecek çizim eylemini tanımlar.

Varsayılan olarak, bu işlev, her biri varsayılan boyutlu onay kutusu olan dizeleri listesinden oluşan varsayılan bir onay kutusu listesi çizer. Onay kutusu liste boyutu [Oluştur'da](#create)belirtilendir.

Bu üye işlevini, dizeleri olmayan, değişken yükseklikte öğelerle veya solda olmayan onay kutularıyla dizeleri olmayan listeli denetim listesi kutuları gibi varsayılan olmayan sahip çizimi denetim listesi kutularını uygulamak için geçersiz kılın. Uygulama, bu üye işlevin sonlandırılmasından önce *lpDrawItemStruct'ta* sağlanan ekran bağlamı için seçilen tüm grafik aygıtı arabirimi (GDI) nesnelerini geri yüklemelidir.

Denetim listesi kutusu öğelerinin tümü aynı yükseklikte değilse, onay `Create`listesi kutusu stili (belirtilen) **LBS_OWNERVARIABLE**olmalıdır ve [MeasureItem](#measureitem) işlevini geçersiz kılmanız gerekir.

## <a name="cchecklistboxenable"></a><a name="enable"></a>CCheckListBox::Etkinleştir

Bir denetim listesi kutusu öğesini etkinleştirmek veya devre dışı kalmak için bu işlevi arayın.

```cpp
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Denetlistesi kutusu öğesinin dizini etkinleştirilecek.

*bEtkin*<br/>
Öğenin etkin veya devre dışı bırakıldığını belirtir.

## <a name="cchecklistboxgetcheck"></a><a name="getcheck"></a>CCheckListBox::GetCheck

Belirtilen onay kutusunun durumunu alır.

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste kutusunda bulunan bir onay kutusunun sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen onay kutusunun durumu. Aşağıdaki tabloda olası değerler listeleilmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|BST_CHECKED|Onay kutusu işaretli.|
|Bst_unchecked|Onay kutusu işaretlenmedi.|
|BST_INDETERMINATE|Onay kutusu durumu belirsizdir.|

## <a name="cchecklistboxgetcheckstyle"></a><a name="getcheckstyle"></a>CCheckListBox::GetCheckStyle

Denetim listesi kutusunun stilini almak için bu işlevi arayın.

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin onay kutularının stili.

### <a name="remarks"></a>Açıklamalar

Olası stiller hakkında daha fazla bilgi için [SetCheckStyle'a](#setcheckstyle)bakın.

## <a name="cchecklistboxisenabled"></a><a name="isenabled"></a>CcheckListBox::IsEnabled

Bir öğenin etkin olup olmadığını belirlemek için bu işlevi arayın.

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Öğenin dizin.

### <a name="return-value"></a>Dönüş Değeri

Öğe etkinse sıfırsız; aksi takdirde 0.

## <a name="cchecklistboxmeasureitem"></a><a name="measureitem"></a>CCheckListBox::MeasureItem

Varsayılan olmayan stili olan bir denetim listesi kutusu oluşturulduğunda çerçeve tarafından çağrılır.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) yapısıiçin uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bu üye işlevi geçersiz kılın `MEASUREITEMSTRUCT` ve Windows'u denetim listesi kutusu öğelerinin boyutları hakkında bilgilendirmek için yapıyı doldurun. Onay listesi kutusu [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulursa, çerçeve liste kutusundaki her öğe için bu üye işlevi çağırır. Aksi takdirde, bu üye yalnızca bir kez çağrılır.

## <a name="cchecklistboxongetcheckposition"></a><a name="ongetcheckposition"></a>CcheckListBox::OnGetCheckPosition

Çerçeve, bir öğedeki onay kutusunun konumunu ve boyutunu almak için bu işlevi çağırır.

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>Parametreler

*rektItem*<br/>
Liste öğesinin konumu ve boyutu.

*rectCheckBox*<br/>
Varsayılan konum ve öğenin onay kutusunun boyutu.

### <a name="return-value"></a>Dönüş Değeri

Bir öğenin onay kutusunun konumu ve boyutu.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama yalnızca varsayılan konumu ve onay kutusunun boyutunu döndürür (`rectCheckBox`). Varsayılan olarak, bir onay kutusu bir öğenin sol üst köşesinde hizalanır ve standart onay kutusu boyutudur. Sağdaki onay kutularını istediğiniz veya daha büyük veya daha küçük bir onay kutusu istediğiniz durumlar olabilir. Bu gibi durumlarda, `OnGetCheckPosition` öğe içindeki onay kutusu konumunu ve boyutunu değiştirmek için geçersiz kılın.

## <a name="cchecklistboxsetcheck"></a><a name="setcheck"></a>CCheckListBox::Setcheck

Belirtilen onay kutusunun durumunu ayarlar.

```cpp
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste kutusunda bulunan bir onay kutusunun sıfır tabanlı dizin.

*nCheck*<br/>
Belirtilen onay kutusunun düğme durumu. Olası değerler için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda *nCheck* parametresi için olası değerler listeleilmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|BST_CHECKED|Belirtilen onay kutusunu seçin.|
|Bst_unchecked|Belirtilen onay kutusunu temizleyin.|
|BST_INDETERMINATE|Belirtilen onay kutusu durumunu belirsiz olarak ayarlayın.<br /><br /> Bu durum yalnızca onay kutusu stili BS_AUTO3STATE veya BS_3STATE olduğunda kullanılabilir. Daha fazla bilgi için [Düğme Stilleri'ne](../../mfc/reference/styles-used-by-mfc.md#button-styles)bakın.|

## <a name="cchecklistboxsetcheckstyle"></a><a name="setcheckstyle"></a>CCheckListBox::SetCheckStyle

Onay listesi kutusundaki onay kutularının stilini ayarlamak için bu işlevi arayın.

```cpp
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
Onay listesi kutusundaki onay kutularının stilini belirler.

### <a name="remarks"></a>Açıklamalar

Geçerli stiller şunlardır:

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- Bs_auto3state

- Bs_3state

Bu stiller hakkında bilgi için [Düğme Stilleri'ne](../../mfc/reference/styles-used-by-mfc.md#button-styles)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)
