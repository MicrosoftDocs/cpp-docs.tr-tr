---
title: CListBox Sınıfı
description: MFC CListBox sınıfının ve üye işlevlerinin açıklaması.
ms.date: 01/22/2020
f1_keywords:
- CListBox
- AFXWIN/CListBox
- AFXWIN/CListBox::CListBox
- AFXWIN/CListBox::AddString
- AFXWIN/CListBox::CharToItem
- AFXWIN/CListBox::CompareItem
- AFXWIN/CListBox::Create
- AFXWIN/CListBox::DeleteItem
- AFXWIN/CListBox::DeleteString
- AFXWIN/CListBox::Dir
- AFXWIN/CListBox::DrawItem
- AFXWIN/CListBox::FindString
- AFXWIN/CListBox::FindStringExact
- AFXWIN/CListBox::GetAnchorIndex
- AFXWIN/CListBox::GetCaretIndex
- AFXWIN/CListBox::GetCount
- AFXWIN/CListBox::GetCurSel
- AFXWIN/CListBox::GetHorizontalExtent
- AFXWIN/CListBox::GetItemData
- AFXWIN/CListBox::GetItemDataPtr
- AFXWIN/CListBox::GetItemHeight
- AFXWIN/CListBox::GetItemRect
- AFXWIN/CListBox::GetListBoxInfo
- AFXWIN/CListBox::GetLocale
- AFXWIN/CListBox::GetSel
- AFXWIN/CListBox::GetSelCount
- AFXWIN/CListBox::GetSelItems
- AFXWIN/CListBox::GetText
- AFXWIN/CListBox::GetTextLen
- AFXWIN/CListBox::GetTopIndex
- AFXWIN/CListBox::InitStorage
- AFXWIN/CListBox::InsertString
- AFXWIN/CListBox::ItemFromPoint
- AFXWIN/CListBox::MeasureItem
- AFXWIN/CListBox::ResetContent
- AFXWIN/CListBox::SelectString
- AFXWIN/CListBox::SelItemRange
- AFXWIN/CListBox::SetAnchorIndex
- AFXWIN/CListBox::SetCaretIndex
- AFXWIN/CListBox::SetColumnWidth
- AFXWIN/CListBox::SetCurSel
- AFXWIN/CListBox::SetHorizontalExtent
- AFXWIN/CListBox::SetItemData
- AFXWIN/CListBox::SetItemDataPtr
- AFXWIN/CListBox::SetItemHeight
- AFXWIN/CListBox::SetLocale
- AFXWIN/CListBox::SetSel
- AFXWIN/CListBox::SetTabStops
- AFXWIN/CListBox::SetTopIndex
- AFXWIN/CListBox::VKeyToItem
helpviewer_keywords:
- CListBox [MFC], CListBox
- CListBox [MFC], AddString
- CListBox [MFC], CharToItem
- CListBox [MFC], CompareItem
- CListBox [MFC], Create
- CListBox [MFC], DeleteItem
- CListBox [MFC], DeleteString
- CListBox [MFC], Dir
- CListBox [MFC], DrawItem
- CListBox [MFC], FindString
- CListBox [MFC], FindStringExact
- CListBox [MFC], GetAnchorIndex
- CListBox [MFC], GetCaretIndex
- CListBox [MFC], GetCount
- CListBox [MFC], GetCurSel
- CListBox [MFC], GetHorizontalExtent
- CListBox [MFC], GetItemData
- CListBox [MFC], GetItemDataPtr
- CListBox [MFC], GetItemHeight
- CListBox [MFC], GetItemRect
- CListBox [MFC], GetListBoxInfo
- CListBox [MFC], GetLocale
- CListBox [MFC], GetSel
- CListBox [MFC], GetSelCount
- CListBox [MFC], GetSelItems
- CListBox [MFC], GetText
- CListBox [MFC], GetTextLen
- CListBox [MFC], GetTopIndex
- CListBox [MFC], InitStorage
- CListBox [MFC], InsertString
- CListBox [MFC], ItemFromPoint
- CListBox [MFC], MeasureItem
- CListBox [MFC], ResetContent
- CListBox [MFC], SelectString
- CListBox [MFC], SelItemRange
- CListBox [MFC], SetAnchorIndex
- CListBox [MFC], SetCaretIndex
- CListBox [MFC], SetColumnWidth
- CListBox [MFC], SetCurSel
- CListBox [MFC], SetHorizontalExtent
- CListBox [MFC], SetItemData
- CListBox [MFC], SetItemDataPtr
- CListBox [MFC], SetItemHeight
- CListBox [MFC], SetLocale
- CListBox [MFC], SetSel
- CListBox [MFC], SetTabStops
- CListBox [MFC], SetTopIndex
- CListBox [MFC], VKeyToItem
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
ms.openlocfilehash: 171038ebaaed815aa687c200fe3210bde8000be3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753586"
---
# <a name="clistbox-class"></a>CListBox Sınıfı

Windows liste kutusunun işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CListBox : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CListBox::CListBox](#clistbox)|Bir `CListBox` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CListBox::AddString](#addstring)|Liste kutusuna bir dize ekler.|
|[ClistBox::Chartoitem](#chartoitem)|Dizeleri olmayan sahip-çizim listesi kutuları için özel WM_CHAR işleme sağlamak için geçersiz kılma.|
|[CListBox::Karşılaştırma Öğesi](#compareitem)|Sıralanmış bir sahip-beraberlik listesi kutusunda yeni bir öğenin konumunu belirlemek için çerçeve tarafından çağrılır.|
|[CListBox::Oluştur](#create)|Windows liste kutusunu oluşturur ve `CListBox` nesneye bağlar.|
|[CListBox::DeleteItem](#deleteitem)|Kullanıcı bir öğeyi sahip çizim listesi kutusundan sildiğinde çerçeve tarafından çağrılır.|
|[CListBox::DeleteString](#deletestring)|Liste kutusundan bir dize yi siler.|
|[CListBox::Dir](#dir)|Geçerli dizinden liste kutusuna dosya adları, sürücüler veya her ikisini de ekler.|
|[CListBox::DrawItem](#drawitem)|Bir sahip-beraberlik listesi kutusunun görsel bir yönü değiştiğinde çerçeve tarafından çağrılır.|
|[CListBox::FindString](#findstring)|Liste kutusunda bir dize arar.|
|[CListBox::FindStringExact](#findstringexact)|Belirtilen dizeyle eşleşen ilk liste kutusu dizesini bulur.|
|[CListBox::GetAnchorIndex](#getanchorindex)|Liste kutusundageçerli bağlantı öğesinin sıfır tabanlı dizinini alır.|
|[CListBox::GetCaretIndex](#getcaretindex)|Çok seçimli liste kutusunda odak dikdörtgeni olan öğenin dizinini belirler.|
|[CListBox::GetCount](#getcount)|Liste kutusundaki dizelerin sayısını döndürür.|
|[ClistBox::GetCursel](#getcursel)|Liste kutusunda şu anda seçili dizenin sıfır tabanlı dizinini döndürür.|
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|Liste kutusunun yatay olarak kaydırılabildiği piksellerde genişliği döndürür.|
|[CListBox::GetItemData](#getitemdata)|Liste kutusu öğesiyle ilişkili bir değer verir.|
|[CListBox::GetItemDataPtr](#getitemdataptr)|Bir işaretçiyi liste kutusu öğesine döndürür.|
|[CListBox::GetItemHeight](#getitemheight)|Liste kutusundaki öğelerin yüksekliğini belirler.|
|[CListBox::GetItemRect](#getitemrect)|Liste kutusu öğesinin sınırlayıcı dikdörtgenini şu anda görüntülenirken döndürür.|
|[CListBox::GetListBoxInfo](#getlistboxinfo)|Sütun başına öğe sayısını alır.|
|[CListBox::GetLocale](#getlocale)|Liste kutusu için yerel tanımlayıcıyı alır.|
|[CListBox::GetSel](#getsel)|Liste kutusu öğesinin seçim durumunu döndürür.|
|[CListBox::GetselCount](#getselcount)|Çok seçimli liste kutusunda şu anda seçili dize sayısını döndürür.|
|[CListBox::GetSelItems](#getselitems)|Liste kutusunda şu anda seçili olan dizelerin dekstlerini döndürür.|
|[CListBox::GetText](#gettext)|Liste kutusu öğeyi arabelleğe kopyalar.|
|[CListBox::GetTextlen](#gettextlen)|Liste kutusu öğesinin baytlarındaki uzunluğu döndürür.|
|[CListBox::GetTopIndex](#gettopindex)|Liste kutusundaki ilk görünür dizenin dizinini döndürür.|
|[CListBox::InitStorage](#initstorage)|Liste kutusu öğeleri ve dizeleri için bellek bloklarını önceden ayırır.|
|[CListBox::InsertString](#insertstring)|Liste kutusunda belirli bir konuma bir dize ekler.|
|[CListBox::ItemFromPoint](#itemfrompoint)|Bir noktaya en yakın liste kutusu öğesinin dizinini döndürür.|
|[CListBox::MeasureItem](#measureitem)|Liste kutusu boyutlarını belirlemek için bir sahip çizim listesi kutusu oluşturulduğunda çerçeve tarafından çağrılır.|
|[CListBox::ResetContent](#resetcontent)|Tüm girişleri bir liste kutusundan temizler.|
|[CListBox::SelectString](#selectstring)|Tek seçimli liste kutusunda bir dize arar ve seçer.|
|[ClistBox::SelItemRange](#selitemrange)|Çok seçimli liste kutusunda bir dizi dize seçer veya kaldırır.|
|[CListBox::SetAnchorIndex](#setanchorindex)|Uzun bir seçimbaşlatmak için çapayı çok seçimli liste kutusunda ayarlar.|
|[CListBox::SetCaretIndex](#setcaretindex)|Çok seçimli liste kutusunda belirtilen dizindeki öğeye odak dikdörtgenini ayarlar.|
|[CListBox::SetColumnWidth](#setcolumnwidth)|Çok sütunlu liste kutusunun sütun genişliğini ayarlar.|
|[CListBox::SetCursel](#setcursel)|Bir liste kutusu dizesi seçer.|
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|Bir liste kutusunun yatay olarak kaydırılabildiği piksellerde genişliği ayarlar.|
|[CListBox::SetItemData](#setitemdata)|Liste kutusu öğesiyle ilişkili bir değer ayarlar.|
|[CListBox::SetItemDataPtr](#setitemdataptr)|Liste kutusu öğesine bir işaretçi ayarlar.|
|[CListBox::SetItemHeight](#setitemheight)|Liste kutusundaki öğelerin yüksekliğini ayarlar.|
|[CListBox::SetLocale](#setlocale)|Liste kutusu için yerel tanımlayıcıyı ayarlar.|
|[CListBox::SetSel](#setsel)|Birden çok seçim listesi kutusunda bir liste kutusu öğeyi seçer veya kaldırır.|
|[CListBox::SetTabStops](#settabstops)|Sekme durağı konumlarını liste kutusunda ayarlar.|
|[CListBox::SetTopIndex](#settopindex)|Liste kutusundaki ilk görünür dizenin sıfır tabanlı dizini ayarlar.|
|[ClistBox::VKeytoItem](#vkeytoitem)|LBS_WANTKEYBOARDINPUT stil kümesine sahip liste kutuları için özel WM_KEYDOWN işleme sağlamak için geçersiz kılın.|

## <a name="remarks"></a>Açıklamalar

Liste kutusu, kullanıcının görüntüleyip seçebileceği dosya adları gibi öğelerin listesini görüntüler.

Tek seçimli liste kutusunda, kullanıcı yalnızca bir öğe seçebilir. Çok seçimli liste kutusunda, bir dizi öğe seçilebilir. Kullanıcı bir öğe seçtiğinde, bu öğe vurgulanır ve liste kutusu üst pencereye bir bildirim iletisi gönderir.

Bir iletişim şablonundan veya doğrudan kodunuzda bir liste kutusu oluşturabilirsiniz. Doğrudan oluşturmak için nesneyi `CListBox` oluşturun ve ardından Windows liste kutusu denetimini oluşturmak ve `CListBox` nesneye eklemek için Üye [Oluştur](#create) işlevini çağırın. İletişim şablonundaki liste kutusunu kullanmak için iletişim kutusu sınıfınızda bir liste kutusu `DDX_Control` değişkeni bildirin ve `DoDataExchange` ardından üye değişkeni denetime bağlamak için iletişim kutusu sınıfınızın işlevini kullanın. (bu işlem, iletişim kutusu sınıfınıza bir denetim değişkeni eklediğinizde otomatik olarak sizin için yapılır.)

İnşaat, `CListBox`bir sınıftan türetilen tek adımlı bir işlem olabilir. Türemiş sınıf için bir `Create` oluşturucu yazın ve oluşturucu içinden arayın.

Bir liste kutusu tarafından üst kutusuna gönderilen Windows bildirim iletilerini (genellikle [CDialog'dan](../../mfc/reference/cdialog-class.md)türetilmiş bir sınıf) işlemek istiyorsanız, her ileti için üst sınıfa bir ileti eşlemi girişi ve ileti işleyicisi üye işlevi ekleyin.

Her ileti-eş-eşlemi girişi aşağıdaki formu alır:

`ON_Notification( id, memberFxn )`

bildirim `id` gönderen liste kutusu denetiminin alt pencere kimliğini belirtir `memberFxn` ve bildirimi işlemek için yazdığınız üst üye işlevinin adıdır.

Ebeveynin işlev prototipi aşağıdaki gibidir:

`afx_msg void memberFxn( );`

Aşağıda, olası ileti eşlemi girişlerinin bir listesi ve bunların üst öğeye gönderilecekleri durumların açıklaması verilmiştir:

- ON_LBN_DBLCLK Kullanıcı liste kutusundaki bir dizeyi çift tıklatıyor. Bu bildirim iletisini yalnızca [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiline sahip bir liste kutusu gönderir.

- ON_LBN_ERRSPACE Liste kutusu isteği karşılamak için yeterli bellek ayıramaz.

- ON_LBN_KILLFOCUS Liste kutusu giriş odağı kaybediyor.

- ON_LBN_SELCANCEL Geçerli liste kutusu seçimi iptal edilir. Bu ileti yalnızca liste kutusu LBS_NOTIFY stiline sahipolduğunda gönderilir.

- ON_LBN_SELCHANGE Liste kutusundaki seçim değişti. Seçim [CListBox::SetCurSel](#setcursel) üye işlevi tarafından değiştirilirse bu bildirim gönderilmez. Bu bildirim yalnızca LBS_NOTIFY stiline sahip bir liste kutusu için geçerlidir. LBN_SELCHANGE bildirim iletisi, kullanıcı bir ok tuşuna bastığında, seçim değişmese bile, çok seçimli liste kutusu için gönderilir.

- ON_LBN_SETFOCUS Liste kutusu giriş odağı alıyor.

- ON_WM_CHARTOITEM Dizeleri olmayan bir sahip çizim listesi kutusu WM_CHAR bir ileti alır.

- ON_WM_VKEYTOITEM LBS_WANTKEYBOARDINPUT stiline sahip bir liste kutusu WM_KEYDOWN bir ileti alır.

İletişim kutusu `CListBox` içinde (iletişim kaynağı aracılığıyla) bir nesne `CListBox` oluşturursanız, kullanıcı iletişim kutusunu kapattığında nesne otomatik olarak yok edilir.

Bir pencere `CListBox` içinde bir nesne oluşturursanız, `CListBox` nesneyi yok etmek gerekebilir. Yığının `CListBox` üzerinde nesne oluşturursanız, otomatik olarak yok edilir. Nesneyi `CListBox` **yeni** işlevi kullanarak yığında oluşturursanız, kullanıcı ana pencereyi kapattığında nesneyi yok etmek için nesneyi **sil'i** aramanız gerekir.

Nesnede `CListBox` herhangi bir bellek ayırırsanız, `CListBox` ayırma yıkMak için yıkıcı geçersiz kılın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="clistboxaddstring"></a><a name="addstring"></a>CListBox::AddString

Liste kutusuna bir dize ekler.

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>Parametreler

*lpszItem*<br/>
Eklenecek null-sonlandırılan dize işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki dizeiçin sıfır tabanlı dizin. Bir hata oluşursa iade değeri LB_ERR; yeni dizeyi depolamak için yeterli alan varsa, iade değeri LB_ERRSPACE edilir.

### <a name="remarks"></a>Açıklamalar

Liste kutusu [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulmadıysa, dize listenin sonuna eklenir. Aksi takdirde, dize listeye eklenir ve liste sıralanır. Liste kutusu LBS_SORT stiliyle oluşturulduysa, [ancak LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulmazsa, çerçeve listeyi `CompareItem` üye işlevine yapılan bir veya daha fazla çağrıya göre sıralar.

Liste kutusu içinde belirli bir konuma bir dize eklemek için [InsertString'i](#insertstring) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

## <a name="clistboxchartoitem"></a><a name="chartoitem"></a>ClistBox::Chartoitem

Liste kutusunun üst penceresi liste kutusundan WM_CHARTOITEM bir ileti aldığında çerçeve tarafından çağrılır.

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Parametreler

*nAnahtar*<br/>
Kullanıcının yazdığı karakterin ANSI kodu.

*Nındex*<br/>
Liste kutusu bakımının geçerli konumu.

### <a name="return-value"></a>Dönüş Değeri

Tuş vuruşu için varsayılan eylemi gerçekleştirmek için bir liste kutusu öğesinin dizinini belirtmek için başka bir eylem veya negatif olmayan bir sayı için - 1 veya - 2 döndürür. Varsayılan uygulama döndürür - 1.

### <a name="remarks"></a>Açıklamalar

WM_CHARTOITEM iletisi, WM_CHAR iletisi aldığında liste kutusu tarafından gönderilir, ancak liste kutusu bu ölçütlerin tümlerini karşılıyorsa:

- Bir sahip-beraberlik listesi kutusudur.

- [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stil seti yok.

- En az bir öğesi vardır.

Bu işlevi asla kendin aramamalısın. Klavye iletilerinin kendi özel işlemesağlamak için bu işlevi geçersiz kılın.

Geçersiz kılmada, çerçeveye hangi eylemi gerçekleştirdiğinizi söylemek için bir değer döndürmeniz gerekir. - 1 veya - 2'nin iade değeri, öğeyi seçmenin tüm yönlerini ele aldığınızı ve liste kutusu tarafından başka bir işlem gerektirmediğini gösterir. Dönmeden önce - 1 veya - 2, seçimi ayarlayabilir veya caret'i veya her ikisini birden taşıyabilirsiniz. Seçimi ayarlamak için [SetCurSel](#setcursel) veya [SetSel'i](#setsel)kullanın. Caret'i taşımak için [SetCaretIndex'i](#setcaretindex)kullanın.

0 veya daha büyük bir geri dönüş değeri liste kutusundaki bir öğenin dizinini belirtir ve liste kutusunun verilen öğedeki tuş vuruşu için varsayılan eylemi gerçekleştirmesi gerektiğini gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

## <a name="clistboxclistbox"></a><a name="clistbox"></a>CListBox::CListBox

Bir `CListBox` nesne inşa eder.

```
CListBox();
```

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CListBox` iki adımda inşa ee. İlk olarak, oluşturucuyu `ClistBox` `Create`arayın ve ardından Windows liste kutusunu başharfe `CListBox`çeken ve 'ye iliştiren ' i arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

## <a name="clistboxcompareitem"></a><a name="compareitem"></a>CListBox::Karşılaştırma Öğesi

Sıralanmış bir sahip-beraberlik listesi kutusunda yeni bir öğenin göreli konumunu belirlemek için çerçeve tarafından çağrılan.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpCompareItemStruct*<br/>
Bir yapı için `COMPAREITEMSTRUCT` uzun bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

[COMPAREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-compareitemstruct) yapısında açıklanan iki öğenin göreli konumunu gösterir. Aşağıdaki değerlerden biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|-1|Madde 1 madde 2'den önce sıralar.|
|0|Madde 1 ve madde 2 aynı sıralayın.|
|1|Madde 1 madde 2'den sonra sıralar.|

Bkz. [CWnd::Yapının](../../mfc/reference/cwnd-class.md#oncompareitem) `COMPAREITEMSTRUCT` açıklaması için OnCompareItem.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. LBS_SORT stiline sahip bir sahip çizim listesi kutusu oluşturursanız, liste kutusuna eklenen yeni öğeleri sıralamada çerçeveye yardımcı olmak için bu üye işlevini geçersiz kılmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

## <a name="clistboxcreate"></a><a name="create"></a>CListBox::Oluştur

Windows liste kutusunu oluşturur ve `CListBox` nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Liste kutusunun stilini belirtir. [Kutuya liste kutusu stillerinin](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) herhangi bir birleşimini uygulayın.

*Rect*<br/>
Liste kutusu boyutunu ve konumunu belirtir. Bir `CRect` nesne veya yapı `RECT` olabilir.

*pParentWnd*<br/>
Liste kutusunun üst penceresini (genellikle `CDialog` bir nesne) belirtir. NULL olmamalıdır.

*Nıd*<br/>
Liste kutusunun denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CListBox` iki adımda inşa ee. İlk olarak, oluşturucuyu `Create`çağırın ve ardından Windows liste kutusunu başharfe çeken ve `CListBox` nesneye iliştiren çağrıyı arayın.

Yürütüldüğünde, `Create` Windows liste kutusu denetimine [WM_NCCREATE,](../../mfc/reference/cwnd-class.md#onnccreate) [WM_CREATE,](../../mfc/reference/cwnd-class.md#oncreate) [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) iletileri gönderir.

Bu iletiler varsayılan olarak [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) üye işlevleri `CWnd` tarafından temel sınıfta işlenir. Varsayılan ileti işlemeyi genişletmek için, `CListBox`yeni sınıfa bir ileti eşlemi ekleyin ve önceki ileti işleyicisi üye işlevlerini geçersiz kılın. Geçersiz `OnCreate`kılma , örneğin, yeni bir sınıf için gerekli başlatma gerçekleştirmek için.

Aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) liste kutusu denetimine uygulayın.

- WS_CHILD Her Zaman

- WS_VISIBLE Genellikle

- WS_DISABLED Nadiren

- WS_VSCROLL Dikey kaydırma çubuğu eklemek için

- WS_HSCROLL Yatay kaydırma çubuğu eklemek için

- WS_GROUP Denetimleri gruplandırmak için

- WS_TABSTOP Bu denetime sekme izin vermek için

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

## <a name="clistboxdeleteitem"></a><a name="deleteitem"></a>CListBox::DeleteItem

Kullanıcı bir öğeyi sahip çizim `CListBox` nesnesinden sildiğinde veya liste kutusunu yok ettiğinde çerçeve tarafından çağrılır.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDeleteItemStruct*<br/>
Silinen öğe hakkında bilgi içeren windows [deleteitemstruct](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) yapısıiçin uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması hiçbir şey yapmaz. Gerektiğinde bir sahip çizim listesi kutusunu yeniden çizmek için bu işlevi geçersiz kılın.

Bkz. [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) yapının `DELETEITEMSTRUCT` açıklaması için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

## <a name="clistboxdeletestring"></a><a name="deletestring"></a>CListBox::DeleteString

NIndex konumundaki *nIndex* öğeyi liste kutusundan siler.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Silinecek dizenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Listede kalan dizeleri sayısı. *nIndex* listedeki madde sayısından daha büyük bir dizin belirtse, iade değeri LB_ERR.

### <a name="remarks"></a>Açıklamalar

*nIndex'i* izleyen tüm öğeler artık tek bir konumda aşağı hareket ediyor. Örneğin, bir liste kutusu iki öğe içeriyorsa, ilk öğenin silmesi kalan öğenin şimdi ilk konumda olması gerekir. *nIndex*=0 ilk konumdaki öğe için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

## <a name="clistboxdir"></a><a name="dir"></a>CListBox::Dir

Liste kutusuna dosya adlarının, sürücülerin veya her ikisinin listesini ekler.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Parametreler

*Attr*<br/>
`CFile::GetStatu` [S](../../mfc/reference/cfile-class.md#getstatus)' de açıklanan **enum** değerlerinin veya aşağıdaki değerlerin herhangi bir kombinasyonu olabilir:

|Değer|Anlamı|
|-----------|-------------|
|0x0000|Dosya okunabilir veya yazılabilir.|
|0x0001|Dosya okunabilir ama yazılamaz.|
|0x0002|Dosya gizlidir ve dizin listesinde görünmez.|
|0x0004|Dosya bir sistem dosyasıdır.|
|0x0010|*lpszWildCard* tarafından belirtilen ad bir dizini belirtir.|
|0x0020|Dosya arşivlendi.|
|0x4000|*lpszWildCard*tarafından belirtilen ada uyan tüm sürücüleri ekleyin.|
|0x8000|Özel bayrak. Özel bayrak ayarlanırsa, yalnızca belirtilen türdeki dosyalar listelenir. Aksi takdirde, belirtilen türdeki dosyalar "normal" dosyalara ek olarak listelenir.|

*lpszWildCard*<br/>
Dosya belirtimi dizesini işaret edin. Dize joker karakterler içerebilir (örneğin,\**. ).

### <a name="return-value"></a>Dönüş Değeri

Listeye eklenen son dosya adının sıfır tabanlı dizini. Bir hata oluşursa iade değeri LB_ERR; yeni dizeleri depolamak için yeterli alan varsa, iade değeri LB_ERRSPACE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

## <a name="clistboxdrawitem"></a><a name="drawitem"></a>CListBox::DrawItem

Bir sahip-beraberlik listesi kutusunun görsel bir yönü değiştiğinde çerçeve tarafından çağrılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısıiçin uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`itemAction` Yapının `itemState` `DRAWITEMSTRUCT` üyeleri ve yapıları, gerçekleştirilecek çizim eylemini tanımlar.

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bir sahip çizim `CListBox` nesnesi için çizim uygulamak için bu üye işlevi geçersiz kılın. Uygulama, bu üye işlev sona erdirilmeden önce *lpDrawItemStruct'ta* sağlanan ekran bağlamı için seçilen tüm grafik aygıtı arabirimi (GDI) nesnelerini geri yüklemelidir.

Bkz. [CWnd::Yapının](../../mfc/reference/cwnd-class.md#ondrawitem) `DRAWITEMSTRUCT` açıklaması için OnDrawItem.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

## <a name="clistboxfindstring"></a><a name="findstring"></a>CListBox::FindString

Liste kutusu seçimini değiştirmeden belirtilen önek içeren bir liste kutusundaki ilk dizeyi bulur.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>Parametreler

*nStartAfter*<br/>
Aranacak ilk öğeden önce maddenin sıfır tabanlı dizinini içerir. Arama liste kutusunun altına ulaştığında, liste kutusunun üst kısmından *nStartAfter*tarafından belirtilen öğeye kadar devam ediyor. *nStartAfter* -1 ise, tüm liste kutusu baştan aranır.

*lpszItem*<br/>
Aranacak önek içeren null-sonlandırılan dizeyi işaret edin. Arama büyük/küçük harften bağımsızdır, bu nedenle bu dize büyük harf ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen öğenin sıfır tabanlı dizin veya arama başarısız olup olmadığını LB_ERR.

### <a name="remarks"></a>Açıklamalar

Bir dize yi bulmak ve seçmek için [SelectString](#selectstring) üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

## <a name="clistboxfindstringexact"></a><a name="findstringexact"></a>CListBox::FindStringExact

*LpszFind'da*belirtilen dizeyle eşleşen ilk liste kutusu dizesini bulur.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Parametreler

*nIndexStart*<br/>
Aranacak ilk öğeden önce maddenin sıfır tabanlı dizinini belirtir. Arama liste kutusunun altına ulaştığında, liste kutusunun üstünden *nIndexStart*tarafından belirtilen öğeye kadar devam ediyor. *nIndexStart* -1 ise, tüm liste kutusu baştan aranır.

*lpszBul*<br/>
Aramak için null-sonlandırılan dize işaret. Bu dize uzantısı da dahil olmak üzere tam bir dosya adı içerebilir. Arama büyük/küçük harf duyarlı değildir, bu nedenle dize büyük harf ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen öğenin dizin veya arama başarısız olup olmadığını LB_ERR.

### <a name="remarks"></a>Açıklamalar

Liste kutusu bir sahip-beraberlik stili ile ancak [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) tarzı `FindStringExact` olmadan oluşturulduysa, üye işlev *lpszFind*değeri ile doubleword değeri eşleştirmek için çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

## <a name="clistboxgetanchorindex"></a><a name="getanchorindex"></a>CListBox::GetAnchorIndex

Liste kutusundaki geçerli bağlantı öğesinin sıfır tabanlı dizinini alır.

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, geçerli bağlantı öğesinin dizini; aksi takdirde LB_ERR.

### <a name="remarks"></a>Açıklamalar

Çok seçimli liste kutusunda, bağlantı öğesi bitişik seçili öğeler bloğundaki ilk veya son öğedir.

### <a name="example"></a>Örnek

  CListBox örneğine [bakın:SetAnchorIndex.](#setanchorindex)

## <a name="clistboxgetcaretindex"></a><a name="getcaretindex"></a>CListBox::GetCaretIndex

Çok seçimli liste kutusunda odak dikdörtgeni olan öğenin dizinini belirler.

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunda odak dikdörtgeni bulunan öğenin sıfır tabanlı dizin. Liste kutusu tek seçim listesi kutusuysa, iade değeri varsa seçilen öğenin dizinidir.

### <a name="remarks"></a>Açıklamalar

Öğe seçili olabilir veya olmayabilir.

### <a name="example"></a>Örnek

  CListBox örneğine [bakın:SetCaretIndex.](#setcaretindex)

## <a name="clistboxgetcount"></a><a name="getcount"></a>CListBox::GetCount

Liste kutusundaki öğe sayısını alır.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki öğe sayısı veya bir hata oluşursa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Döndürülen sayım, son maddenin dizin değerinden bir büyüktür (dizin sıfır tabanlıdır).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

## <a name="clistboxgetcursel"></a><a name="getcursel"></a>ClistBox::GetCursel

Varsa, varsa, tek seçim listesi kutusunda, şu anda seçili öğenin sıfır tabanlı dizinini alır.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tek seçimli liste kutusuysa, şu anda seçili öğenin sıfır tabanlı dizini. Şu anda öğe seçili değilse LB_ERR.

Çok seçimli liste kutusunda, odak noktası olan öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Çok seçimli liste kutusunu aramayın. `GetCurSel` Bunun yerine [CListBox::GetSelItems'ı](#getselitems) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

## <a name="clistboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CListBox::GetHorizontalExtent

Liste kutusundan, yatay olarak kaydırılabildiği pikselgenişliğindeki genişliği alır.

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunun piksel olarak kaydırılabilir genişliği.

### <a name="remarks"></a>Açıklamalar

Bu, yalnızca liste kutusunun yatay kaydırma çubuğu varsa geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

## <a name="clistboxgetitemdata"></a><a name="getitemdata"></a>CListBox::GetItemData

Belirtilen liste kutusu öğesiile ilişkili uygulama tarafından sağlanan çift kelime değerini alır.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste kutusundaki öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Maddeyle ilişkili değer veya bir hata oluşursa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Çift kelime değeri, [Bir SetItemData](#setitemdata) çağrısının *dwItemData* parametresiidi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

## <a name="clistboxgetitemdataptr"></a><a name="getitemdataptr"></a>CListBox::GetItemDataPtr

Belirtilen liste kutusu öğesiile ilişkili uygulama tarafından sağlanan 32 bit değeri işaretçi **(geçersiz)** <strong>\*</strong>olarak alır.

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste kutusundaki öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi veya bir hata oluşursa -1 alır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

## <a name="clistboxgetitemheight"></a><a name="getitemheight"></a>CListBox::GetItemHeight

Liste kutusundaki öğelerin yüksekliğini belirler.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste kutusundaki öğenin sıfır tabanlı dizinini belirtir. Bu parametre yalnızca liste kutusunda LBS_OWNERDRAWVARIABLE stili varsa kullanılır; aksi takdirde, 0 olarak ayarlanmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki öğelerin piksel olarak yüksekliği. Liste kutusu [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiline sahipse, iade değeri *nIndex*tarafından belirtilen öğenin yüksekliğidir. Bir hata oluşursa, iade değeri LB_ERR.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

## <a name="clistboxgetitemrect"></a><a name="getitemrect"></a>CListBox::GetItemRect

Liste kutusu penceresinde şu anda görüntülenirken liste kutusu öğesini sınırlayan dikdörtgenin boyutlarını alır.

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Maddenin sıfır tabanlı dizinini belirtir.

*Lprect*<br/>
Öğenin liste kutusu istemci koordinatlarını alan bir [RECT yapısıiçin](/windows/win32/api/windef/ns-windef-rect) uzun bir işaretçi belirtir.

### <a name="return-value"></a>Dönüş Değeri

LB_ERR bir hata oluşursa.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

## <a name="clistboxgetlistboxinfo"></a><a name="getlistboxinfo"></a>CListBox::GetListBoxInfo

Sütun başına öğe sayısını alır.

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CListBox` Nesnenin sütun başına öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [LB_GETLISTBOXINFO](/windows/win32/Controls/lb-getlistboxinfo) iletinin işlevselliğini taklit eder.

## <a name="clistboxgetlocale"></a><a name="getlocale"></a>CListBox::GetLocale

Liste kutusu tarafından kullanılan yerel alanı alır.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki dizeleri için yerel tanımlayıcı (LCID) değeri.

### <a name="remarks"></a>Açıklamalar

Yerel düzen, örneğin, sıralanmış bir liste kutusundadizeli sıralama sırasını belirlemek için kullanılır.

### <a name="example"></a>Örnek

  CListBox örneğine [bakın:SetLocale](#setlocale).

## <a name="clistboxgetsel"></a><a name="getsel"></a>CListBox::GetSel

Bir öğenin seçim durumunu alır.

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Maddenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe seçilirse pozitif bir sayı; aksi takdirde, 0'dır. Bir hata oluşursa iade değeri LB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hem tek hem de çoklu seçim listesi kutularıyla çalışır.

Şu anda seçili liste kutusu öğesinin dizinini almak için [CListBox::GetCurSel'i](#getcursel)kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

## <a name="clistboxgetselcount"></a><a name="getselcount"></a>CListBox::GetselCount

Birden çok seçim listesi kutusunda seçili öğelerin toplam sayısını alır.

```
int GetSelCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunda seçili öğelerin sayısı. Liste kutusu tek seçimli liste kutusuysa, iade değeri LB_ERR.

### <a name="example"></a>Örnek

  CListBox örneğine [bakın:GetSelItems](#getselitems).

## <a name="clistboxgetselitems"></a><a name="getselitems"></a>CListBox::GetSelItems

Arabelleği, birden çok seçim listesi kutusunda seçili öğelerin madde numaralarını belirten bir tamsayı dizisiyle doldurur.

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>Parametreler

*nMaxItems*<br/>
Madde numaraları arabelleğe yerleştirilecek olan seçili maddelerin maksimum sayısını belirtir.

*rgIndex*<br/>
*nMaxItems*tarafından belirtilen tamsayı sayısı için yeterince büyük bir arabellek işaretçisi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Arabelleğe yerleştirilen maddelerin gerçek sayısı. Liste kutusu tek seçim listesi kutusuysa, iade `LB_ERR`değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

## <a name="clistboxgettext"></a><a name="gettext"></a>CListBox::GetText

Liste kutusundan bir dize alır.

```
int GetText(
    int nIndex,
    LPTSTR lpszBuffer) const;

void GetText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Alınacak dizenin sıfır tabanlı dizinini belirtir.

*lpszBuffer*<br/>
Dizeyi alan arabelleğe işaret edin. Arabellek dize ve sonlandırıcı null karakter için yeterli alana sahip olmalıdır. Dize boyutu `GetTextLen` üye işlevi çağırarak önceden belirlenebilir.

*rString*<br/>
Bir `CString` nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sonlandırıcı null karakteri hariç, dize uzunluğu (bayt olarak). nIndex geçerli bir *dizin* belirtmezse, iade değeri LB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin ikinci biçimi, bir `CString` nesneyi dize metniyle doldurur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

## <a name="clistboxgettextlen"></a><a name="gettextlen"></a>CListBox::GetTextlen

Liste kutusu öğesinde bir dize uzunluğunu alır.

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Dize sıfır tabanlı dizini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sonlandırıcı null karakter hariç, karakterlerdeki dize uzunluğu. nIndex geçerli bir *dizin* belirtmezse, iade değeri LB_ERR.

### <a name="example"></a>Örnek

  CListBox örneğine [bakın:GetText](#gettext).

## <a name="clistboxgettopindex"></a><a name="gettopindex"></a>CListBox::GetTopIndex

Liste kutusundaki ilk görünür öğenin sıfır tabanlı dizinini alır.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, liste kutusundaki ilk görünür öğenin sıfır tabanlı dizini, aksi takdirde LB_ERR.

### <a name="remarks"></a>Açıklamalar

Başlangıçta, madde 0 liste kutusunun en üstündedir, ancak liste kutusu kaydırılırsa, başka bir öğe en üstte olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

## <a name="clistboxinitstorage"></a><a name="initstorage"></a>CListBox::InitStorage

Liste kutusu öğelerini depolamak için bellek ayırır.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>Parametreler

*nÖğeler*<br/>
Eklenecek öğe sayısını belirtir.

*nBayt*<br/>
Madde dizeleri için ayırmak için baytlarda bellek miktarını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, liste kutusunun bellek yeniden tahsisinden önce depolayabildiği en fazla öğe sayısı gereklidir, aksi takdirde LB_ERRSPACE, yani yeterli bellek kullanılamaz.

### <a name="remarks"></a>Açıklamalar

Bir öğeye çok sayıda öğe eklemeden önce bu işlevi çağırın. `CListBox`

Bu işlev, çok sayıda öğeye (100'den fazla) sahip liste kutularının başlatılmasını hızlandırmaya yardımcı olur. Sonraki [AddString](#addstring), [InsertString](#insertstring)ve [Dir](#dir) işlevlerimümkün olan en kısa sürede almak böylece bellek belirtilen miktarda önceden ayırır. Parametreler için tahminleri kullanabilirsiniz. Eğer abartmak, bazı ekstra bellek ayrılır; eğer küçümserseniz, normal ayırma önceden tahsis edilen tutarı aşan maddeler için kullanılır.

Yalnızca Windows 95/98: *nItems* parametresi 16 bit değerlerle sınırlıdır. Bu, liste kutularının 32.767'den fazla öğe içeremeyeceği anlamına gelir. Öğe sayısı kısıtlanmış olsa da, liste kutusundaki öğelerin toplam boyutu yalnızca kullanılabilir bellekle sınırlıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

## <a name="clistboxinsertstring"></a><a name="insertstring"></a>CListBox::InsertString

Liste kutusuna bir dize ekler.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Dize eklemek için pozisyonun sıfır tabanlı dizini belirtir. Bu parametre -1 ise, dize listenin sonuna eklenir.

*lpszItem*<br/>
Eklenecek null-sonlandırılan dize işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

Dize eklendiği pozisyonun sıfır tabanlı dizin. Bir hata oluşursa iade değeri LB_ERR; yeni dizeyi depolamak için yeterli alan varsa, iade değeri LB_ERRSPACE edilir.

### <a name="remarks"></a>Açıklamalar

[AddString](#addstring) üye işlevinin `InsertString` aksine, [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stilinin sıralanmasına sahip bir liste neden olmaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

## <a name="clistboxitemfrompoint"></a><a name="itemfrompoint"></a>CListBox::ItemFromPoint

*Pt'de*belirtilen noktaya en yakın liste kutusu öğesini belirler.

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
Liste kutusunun istemci alanının sol üst köşesine göre belirtilen en yakın öğeyi bulmak için nokta.

*bDış*<br/>
*Pt* liste kutusunun istemci alanı dışında ise TRUE olarak ayarlanacak bir BOOL değişkenine başvuru, *pt* liste kutusunun istemci alanı içinde ise FALSE.

### <a name="return-value"></a>Dönüş Değeri

Pt'de belirtilen noktaya en yakın *pt*maddenin dizini .

### <a name="remarks"></a>Açıklamalar

Fare imlecinin hangi liste kutusu öğesiüzerinde hareket leştiğini belirlemek için bu işlevi kullanabilirsiniz.

### <a name="example"></a>Örnek

  CListBox örneğine [bakın:SetAnchorIndex.](#setanchorindex)

## <a name="clistboxmeasureitem"></a><a name="measureitem"></a>CListBox::MeasureItem

Sahip çizim stiline sahip bir liste kutusu oluşturulduğunda çerçeve tarafından çağrılır.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) yapısıiçin uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bu üye işlevini geçersiz kılın `MEASUREITEMSTRUCT` ve Windows'u liste kutusu boyutları hakkında bilgilendirmek için yapıyı doldurun. Liste kutusu [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulursa, çerçeve liste kutusundaki her öğe için bu üye işlevi çağırır. Aksi takdirde, bu üye yalnızca bir kez çağrılır.

Üye işlevi ile oluşturulan bir sahip-beraberlik listesi kutusunda [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili `CWnd`kullanma hakkında daha fazla bilgi için, [Teknik Not 14'teki](../../mfc/tn014-custom-controls.md)tartışmaya bakın. `SubclassDlgItem`

Bkz. [CWnd::Yapının](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT` açıklaması için OnMeasureItem.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

## <a name="clistboxresetcontent"></a><a name="resetcontent"></a>CListBox::ResetContent

Liste kutusundaki tüm öğeleri kaldırır.

```cpp
void ResetContent();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

## <a name="clistboxselectstring"></a><a name="selectstring"></a>CListBox::SelectString

Belirtilen dizeyle eşleşen bir liste kutusu öğesi arar ve eşleşen bir öğe bulunursa, öğeyi seçer.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Parametreler

*nStartAfter*<br/>
Aranacak ilk öğeden önce maddenin sıfır tabanlı dizinini içerir. Arama liste kutusunun altına ulaştığında, liste kutusunun üst kısmından *nStartAfter*tarafından belirtilen öğeye kadar devam ediyor. *nStartAfter* -1 ise, tüm liste kutusu baştan aranır.

*lpszItem*<br/>
Aranacak önek içeren null-sonlandırılan dizeyi işaret edin. Arama büyük/küçük harften bağımsızdır, bu nedenle bu dize büyük harf ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Arama başarılı olduysa seçili öğenin dizin. Arama başarısız olduysa, iade değeri LB_ERR ve geçerli seçim değiştirilmez.

### <a name="remarks"></a>Açıklamalar

Seçili öğeyi görünüme getirmek için gerekirse liste kutusu kaydırılır.

Bu üye [işlev, LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiline sahip bir liste kutusuyla kullanılamaz.

Bir öğe yalnızca ilk karakterleri (başlangıç noktasından) *lpszItem*tarafından belirtilen dizedeki karakterlerle eşleşirse seçilir.

Öğeyi `FindString` seçmeden bir dize bulmak için üye işlevi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

## <a name="clistboxselitemrange"></a><a name="selitemrange"></a>ClistBox::SelItemRange

Birden çok seçim listesi kutusunda art arda birden çok öğe seçer.

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>Parametreler

*bSeçin*<br/>
Seçimin nasıl ayarlanılsüreceğini belirtir. *bSelect* TRUE ise, dize seçilir ve vurgulanır; FALSE ise, vurgu kaldırılır ve dize artık seçili değildir.

*nFirstItem*<br/>
Ayarlanan ilk öğenin sıfır tabanlı dizinini belirtir.

*nLastItem*<br/>
Ayarlanan son öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

LB_ERR bir hata oluşursa.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca birden çok seçim listesi kutularıyla kullanın. Birden çok seçim listesi kutusunda yalnızca bir öğe seçmeniz gerekiyorsa ( yani *nFirstItem* *nLastItem'e* eşitse- Bunun yerine [SetSel](#setsel) üye işlevini arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

## <a name="clistboxsetanchorindex"></a><a name="setanchorindex"></a>CListBox::SetAnchorIndex

Uzun bir seçimbaşlatmak için çapayı çok seçimli liste kutusunda ayarlar.

```cpp
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Bağlantı olacak liste kutusu öğesinin sıfır tabanlı dizinini belirtir.

### <a name="remarks"></a>Açıklamalar

Çok seçimli liste kutusunda, bağlantı öğesi bitişik seçili öğeler bloğundaki ilk veya son öğedir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

## <a name="clistboxsetcaretindex"></a><a name="setcaretindex"></a>CListBox::SetCaretIndex

Çok seçimli liste kutusunda belirtilen dizindeki öğeye odak dikdörtgenini ayarlar.

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste kutusundaki odak dikdörtgenini almak için öğenin sıfır tabanlı dizinini belirtir.

*bKaydırma*<br/>
Bu değer 0 ise, öğe tamamen görünür olana kadar kaydırılır. Bu değer 0 değilse, öğe en azından kısmen görünür olana kadar kaydırılır.

### <a name="return-value"></a>Dönüş Değeri

LB_ERR bir hata oluşursa.

### <a name="remarks"></a>Açıklamalar

Öğe görünmüyorsa, görünüme kaydırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

## <a name="clistboxsetcolumnwidth"></a><a name="setcolumnwidth"></a>CListBox::SetColumnWidth

Çok sütunlu bir liste kutusundaki tüm sütunların piksellerinde genişliği ayarlar [(LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulur).

```cpp
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>Parametreler

*cxGenişlik*<br/>
Tüm sütunların piksellerinde genişliği belirtir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

## <a name="clistboxsetcursel"></a><a name="setcursel"></a>CListBox::SetCursel

Bir dize seçer ve gerekirse görünüme kaydırır.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Parametreler

*nSeç*<br/>
Seçilecek dizenin sıfır tabanlı dizinini belirtir. *nSelect* -1 ise, liste kutusu seçim olmayacak şekilde ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

LB_ERR bir hata oluşursa.

### <a name="remarks"></a>Açıklamalar

Yeni dize seçildiğinde, liste kutusu vurguyu önceden seçili dizeden kaldırır.

Bu üye işlevini yalnızca tek seçim listesi kutularıyla kullanın.

Bir seçimi birden çok seçim listesi kutusunda ayarlamak veya kaldırmak için [CListBox:SetSel'i](#setsel)kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

## <a name="clistboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CListBox::SetHorizontalExtent

Bir liste kutusunun yatay olarak kaydırılabildiği genişliği piksel olarak ayarlar.

```cpp
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>Parametreler

*cxÖlçüde*<br/>
Liste kutusunun yatay olarak kaydırılabildiği piksel sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Liste kutusunun boyutu bu değerden küçükse, yatay kaydırma çubuğu liste kutusundaki öğeleri yatay olarak kaydırır. Liste kutusu bu değerden büyük veya büyükse, yatay kaydırma çubuğu gizlenir.

Bir çağrıya yanıt `SetHorizontalExtent`vermek için liste kutusu [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles) stiliyle tanımlanmış olmalıdır.

Bu üye işlev çok sütunlu liste kutuları için kullanışlı değildir. Çok sütunlu liste kutuları `SetColumnWidth` için üye işlevi arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

## <a name="clistboxsetitemdata"></a><a name="setitemdata"></a>CListBox::SetItemData

Bir liste kutusunda belirtilen öğeyle ilişkili bir değer ayarlar.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Maddenin sıfır tabanlı dizinini belirtir.

*dwItemData*<br/>
Maddeyle ilişkilendirilecek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

LB_ERR bir hata oluşursa.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

## <a name="clistboxsetitemdataptr"></a><a name="setitemdataptr"></a>CListBox::SetItemDataPtr

Bir liste kutusunda belirtilen öğeyle ilişkili 32 bit değeri, belirtilen işaretçi **(geçersiz)** <strong>\*</strong>olarak ayarlar.

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Maddenin sıfır tabanlı dizinini belirtir.

*Pdata*<br/>
İşaretçiyi öğeyle ilişkilendirilecek belirtir.

### <a name="return-value"></a>Dönüş Değeri

LB_ERR bir hata oluşursa.

### <a name="remarks"></a>Açıklamalar

Bu işaretçi, öğeler eklendikçe veya kaldırıldıkça öğenin liste kutusundaki göreli konumu değişse bile, liste kutusunun ömrü için geçerli kalır. Bu nedenle, öğenin kutunun içindeki dizin değişebilir, ancak işaretçi güvenilir kalır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

## <a name="clistboxsetitemheight"></a><a name="setitemheight"></a>CListBox::SetItemHeight

Liste kutusundaki öğelerin yüksekliğini ayarlar.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste kutusundaki öğenin sıfır tabanlı dizinini belirtir. Bu parametre yalnızca liste kutusunda LBS_OWNERDRAWVARIABLE stili varsa kullanılır; aksi takdirde, 0 olarak ayarlanmalıdır.

*cyItemHeight*<br/>
Öğenin yüksekliğini, piksel olarak belirtir.

### <a name="return-value"></a>Dönüş Değeri

Dizin veya yükseklik geçersiz seLB_ERR.

### <a name="remarks"></a>Açıklamalar

Liste kutusunda [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili varsa, bu işlev *nIndex*tarafından belirtilen öğenin yüksekliğini ayarlar. Aksi takdirde, bu işlev liste kutusundaki tüm öğelerin yüksekliğini ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

## <a name="clistboxsetlocale"></a><a name="setlocale"></a>CListBox::SetLocale

Bu liste kutusunun yerel tanımlayıcısını ayarlar.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Parametreler

*nNewLocale*<br/>
Liste kutusu için ayarlanan yeni yerel ayar tanımlayıcısı (LCID) değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu liste kutusu için önceki yerel tanımlayıcı (LCID) değeri.

### <a name="remarks"></a>Açıklamalar

`SetLocale` Çağrılmazsa, varsayılan yerel sistemden elde edilir. Bu sistem varsayılan yerel alanı, Denetim Masası'nın Bölgesel (veya Uluslararası) uygulaması kullanılarak değiştirilebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

## <a name="clistboxsetsel"></a><a name="setsel"></a>CListBox::SetSel

Çok seçimli liste kutusunda bir dize seçer.

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Ayarlanacak dizenin sıfır tabanlı dizinini içerir. -1 ise, seçim *bSelect*değerine bağlı olarak tüm dizeleri eklenir veya tüm dizeleri kaldırılır.

*bSeçin*<br/>
Seçimin nasıl ayarlanılsüreceğini belirtir. *bSelect* TRUE ise, dize seçilir ve vurgulanır; FALSE ise, vurgu kaldırılır ve dize artık seçili değildir. Belirtilen dize seçilir ve varsayılan olarak vurgulanır.

### <a name="return-value"></a>Dönüş Değeri

LB_ERR bir hata oluşursa.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca birden çok seçim listesi kutularıyla kullanın.

Tek seçim li liste kutusundan bir öğe seçmek için [CListBox:SetCurSel'i](#setcursel)kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

## <a name="clistboxsettabstops"></a><a name="settabstops"></a>CListBox::SetTabStops

Sekme durağı konumlarını liste kutusunda ayarlar.

```cpp
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Parametreler

*cxEachStop*<br/>
Sekme durakları her *cxEachStop* iletişim birimlerinde ayarlanır. Bir iletişim biriminin açıklaması için *rgTabStops'a* bakın.

*nTabStops*<br/>
Liste kutusunda olması gereken sekme duraklarının sayısını belirtir.

*rgTabStops*<br/>
İletişim birimlerindeki sekme durdurma konumlarını içeren bir dizi ortalık dizisinin ilk üyesini işaret eder. İletişim birimi yatay veya dikey bir uzaklıktır. Bir yatay iletişim birimi, geçerli iletişim taban genişliği biriminin dörtte birine eşittir ve bir dikey iletişim birimi geçerli iletişim taban yüksekliği biriminin sekizde birine eşittir. İletişim taban birimleri, geçerli sistem yazı tipinin yüksekliğine ve genişliğine göre hesaplanır. `GetDialogBaseUnits` Windows işlevi, geçerli iletişim taban birimlerini piksellerde döndürür. Sekme durakları artan sırayla sıralanmalıdır; geri sekmelere izin verilmez.

### <a name="return-value"></a>Dönüş Değeri

Tüm sekmeler ayarlanmışsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sekme duraklarını varsayılan boyuta ayarlamak için 2 iletişim birimi, bu üye işlevin parametresiz sürümünü arayın. Sekmeyi 2'den başka bir boyuta ayarlamak için *cxEachStop* bağımsız değişkenini içeren sürümü arayın.

Sekmeyi bir dizi boyuta ayarlamak *için, rgTabStops* ve *nTabStops* bağımsız değişkenlerini içeren sürümü kullanın. *RgTabStops*her değer için bir sekme durağı ayarlanır , *nTabStops*tarafından belirtilen sayıya kadar.

Üye işlevine yapılan `SetTabStops` çağrıya yanıt vermek için liste kutusunun [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulmuş olması gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

## <a name="clistboxsettopindex"></a><a name="settopindex"></a>CListBox::SetTopIndex

Belirli bir liste kutusu öğesinin görünür olmasını sağlar.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste kutusu öğesinin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır veya hata oluşursa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Sistem, *nIndex* tarafından belirtilen öğe liste kutusunun en üstünde görünene veya maksimum kaydırma aralığına ulaşılana kadar liste kutusunu kaydırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

## <a name="clistboxvkeytoitem"></a><a name="vkeytoitem"></a>ClistBox::VKeytoItem

Liste kutusunun üst penceresi liste kutusundan WM_VKEYTOITEM bir ileti aldığında çerçeve tarafından çağrılır.

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Parametreler

*nAnahtar*<br/>
Kullanıcının bastığı anahtarın sanal anahtar kodu. Standart sanal anahtar kodlarının listesi için Winuser.h

*Nındex*<br/>
Liste kutusu bakımının geçerli konumu.

### <a name="return-value"></a>Dönüş Değeri

Başka bir eylem için - 2, varsayılan eylem için 1 veya tuş vuruşu için varsayılan eylemi gerçekleştirmek için bir liste kutusu öğesinin dizinini belirtmek için negatif olmayan bir sayı.

### <a name="remarks"></a>Açıklamalar

WM_VKEYTOITEM iletisi, WM_KEYDOWN iletisi aldığında liste kutusu tarafından gönderilir, ancak liste kutusu aşağıdakilerden her ikisini de karşılıyorsa:

- [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stil setine sahiptir.

- En az bir öğesi vardır.

Bu işlevi asla kendin aramamalısın. Klavye iletilerinin kendi özel işlemesağlamak için bu işlevi geçersiz kılın.

Geçersiz kılma eyleminizin hangi eylemi gerçekleştirdiğini çerçeveye söylemek için bir değer döndürmeniz gerekir. - 2'nin iade değeri, uygulamanın öğeyi seçmenin tüm yönlerini ele aldığıve liste kutusu tarafından başka bir işlem gerektirmediğini gösterir. Dönmeden önce - 2, seçimi ayarlayabilir veya caret'i veya her ikisini birden taşıyabilirsiniz. Seçimi ayarlamak için [SetCurSel](#setcursel) veya [SetSel'i](#setsel)kullanın. Caret'i taşımak için [SetCaretIndex'i](#setcaretindex)kullanın.

- 1'in geri dönüş değeri, liste kutusunun tuş vuruşuna yanıt olarak varsayılan eylemi gerçekleştirmesi gerektiğini gösterir. Varsayılan uygulama döndürür - 1.

0 veya daha büyük bir geri dönüş değeri liste kutusundaki bir öğenin dizinini belirtir ve liste kutusunun verilen öğedeki tuş vuruşu için varsayılan eylemi gerçekleştirmesi gerektiğini gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CButton Sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CScrollBar Sınıfı](../../mfc/reference/cscrollbar-class.md)<br/>
[Cstatic Sınıfı](../../mfc/reference/cstatic-class.md)
