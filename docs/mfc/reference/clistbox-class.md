---
title: CListBox sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: e47a580e786572b0741700721a9d1ba4ac925fcd
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505688"
---
# <a name="clistbox-class"></a>CListBox sınıfı

Windows liste kutusu işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CListBox : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Clienstbox:: Clienstbox](#clistbox)|Bir `CListBox` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Clienstbox:: AddString](#addstring)|Liste kutusuna bir dize ekler.|
|[Clienstbox:: Chartoıtem](#chartoitem)|Dizeleri olmayan, sahip çizimi liste kutuları için özel WM_CHAR işleme sağlamak üzere geçersiz kılın.|
|[Clienstbox:: CompareItem](#compareitem)|Sıralanmış bir sahip çiz liste kutusunda yeni bir öğenin konumunu öğrenmek için Framework tarafından çağırılır.|
|[Clienstbox:: Create](#create)|Windows liste kutusunu oluşturur ve `CListBox` nesneye ekler.|
|[Clienstbox::D Eleteıtem](#deleteitem)|Kullanıcı bir sahip çizimi liste kutusundan bir öğe sildiğinde Framework tarafından çağırılır.|
|[Clienstbox::D eleteString](#deletestring)|Bir liste kutusundan bir dize siler.|
|[Clienstbox::D IR](#dir)|Geçerli dizinden dosya adlarını, sürücüleri veya her ikisini de bir liste kutusuna ekler.|
|[Clienstbox::D rawItem](#drawitem)|Bir sahip çizimi liste kutusunun görsel yönü değiştiğinde Framework tarafından çağırılır.|
|[Clienstbox:: FindString](#findstring)|Liste kutusunda bir dize arar.|
|[Clienstbox:: Findstringözdeş](#findstringexact)|Belirtilen dizeyle eşleşen ilk liste kutusu dizesini bulur.|
|[Clienstbox:: Getanchorındex](#getanchorindex)|Bir liste kutusunda geçerli bağlantı öğesinin sıfır tabanlı dizinini alır.|
|[Clienstbox:: Getcaretındex](#getcaretindex)|Birden çok seçimli liste kutusunda odak dikdörtgeni olan öğenin dizinini belirler.|
|[Clienstbox:: GetCount](#getcount)|Bir liste kutusundaki dize sayısını döndürür.|
|[Clienstbox:: GetCurSel](#getcursel)|Bir liste kutusunda şu anda seçili olan dizenin sıfır tabanlı dizinini döndürür.|
|[Clienstbox:: GetHorizontalExtent](#gethorizontalextent)|Bir liste kutusunun yatay olarak kaydırılabileceği piksel cinsinden genişliği döndürür.|
|[Clienstbox:: GetItemData](#getitemdata)|Liste kutusu öğesiyle ilişkili bir değer döndürür.|
|[Clienstbox:: GetItemDataPtr](#getitemdataptr)|Liste kutusu öğesine bir işaretçi döndürür.|
|[Clienstbox:: GetItemHeight](#getitemheight)|Bir liste kutusundaki öğelerin yüksekliğini belirler.|
|[Clienstbox:: GetItemRect](#getitemrect)|Liste kutusu öğesinin Şu anda görüntülendiği şekilde sınırlayıcı dikdörtgenini döndürür.|
|[Clienstbox:: Getlistboxınfo](#getlistboxinfo)|Sütun başına öğe sayısını alır.|
|[Clienstbox:: GetLocale](#getlocale)|Bir liste kutusu için yerel ayar tanıtıcısını alır.|
|[Clienstbox:: GetSel](#getsel)|Liste kutusu öğesinin seçim durumunu döndürür.|
|[Clienstbox:: GetSelCount](#getselcount)|Birden çok seçimli liste kutusunda şu anda seçili olan dizelerin sayısını döndürür.|
|[Clienstbox:: GetSelItems](#getselitems)|Liste kutusunda seçili olan dizelerin dizinlerini döndürür.|
|[Clienstbox:: GetText](#gettext)|Bir liste kutusu öğesini arabelleğe kopyalar.|
|[Clienstbox:: GetTextLen](#gettextlen)|Bir liste kutusu öğesinin bayt cinsinden uzunluğunu döndürür.|
|[Clienstbox:: GetTopIndex](#gettopindex)|Liste kutusundaki ilk görünür dizenin dizinini döndürür.|
|[Clienstbox:: ınitstorage](#initstorage)|Liste kutusu öğeleri ve dizeler için bellek bloklarını önceden ayırır.|
|[CListBox:: InsertString](#insertstring)|Liste kutusunda belirli bir konuma bir dize ekler.|
|[Clienstbox:: ItemFromPoint](#itemfrompoint)|Bir noktaya en yakın olan liste kutusu öğesinin dizinini döndürür.|
|[Clienstbox:: MeasureItem](#measureitem)|Liste kutusu boyutlarını belirlemekte bir sahip çizimi liste kutusu oluşturulduğunda Framework tarafından çağırılır.|
|[Clienstbox:: ResetContent](#resetcontent)|Bir liste kutusundan tüm girdileri temizler.|
|[CListBox:: SelectString](#selectstring)|Tek seçimli liste kutusunda bir dize arar ve seçer.|
|[CListBox:: SelItemRange](#selitemrange)|Birden çok seçimli liste kutusunda bir dizi dizeyi seçer veya seçer.|
|[Clienstbox:: SetAnchorIndex](#setanchorindex)|Bir genişletilmiş seçimi başlatmak için birden çok seçimli liste kutusunda yer alan bağlayıcıyı ayarlar.|
|[Clienstbox:: SetCaretIndex](#setcaretindex)|Bir çok seçimli liste kutusunda belirtilen dizindeki öğeye odak dikdörtgenini ayarlar.|
|[Clienstbox:: SetColumnWidth](#setcolumnwidth)|Çok sütunlu bir liste kutusunun sütun genişliğini ayarlar.|
|[Clienstbox:: SetCurSel](#setcursel)|Bir liste kutusu dizesi seçer.|
|[Clienstbox:: SetHorizontalExtent](#sethorizontalextent)|Bir liste kutusunun yatay olarak kaydırılabileceği piksel cinsinden genişliği belirler.|
|[Clienstbox:: SetItemData](#setitemdata)|Liste kutusu öğesiyle ilişkili bir değer ayarlar.|
|[Clienstbox:: SetItemDataPtr](#setitemdataptr)|Liste kutusu öğesine bir işaretçi ayarlar.|
|[Clienstbox:: SetItemHeight](#setitemheight)|Liste kutusundaki öğelerin yüksekliğini ayarlar.|
|[Clienstbox:: SetLocale](#setlocale)|Bir liste kutusu için yerel ayar tanıtıcısını ayarlar.|
|[Clienstbox:: SetSel](#setsel)|Birden çok seçimli liste kutusunda liste kutusu öğesi seçer veya seçimini kaldırır.|
|[Clienstbox:: Settabstop](#settabstops)|Liste kutusunda sekme durağı konumlarını ayarlar.|
|[Clienstbox:: Settopındex](#settopindex)|Liste kutusunda ilk görünür dizenin sıfır tabanlı dizinini ayarlar.|
|[Clienstbox:: Vkeytoıtem](#vkeytoitem)|LBS_WANTKEYBOARDINPUT stili ayarlanmış liste kutuları için özel WM_KEYDOWN işleme sağlamak üzere geçersiz kılın.|

## <a name="remarks"></a>Açıklamalar

Bir liste kutusu, kullanıcının görüntüleyebileceği ve seçebileceğiniz dosya adları gibi öğelerin bir listesini görüntüler.

Tek seçimli liste kutusunda Kullanıcı yalnızca bir öğe seçebilir. Çoklu seçim listesi kutusunda bir dizi öğe seçilebilir. Kullanıcı bir öğe seçtiğinde, vurgulanır ve liste kutusu üst pencereye bir bildirim iletisi gönderir.

Bir iletişim kutusu şablonundan ya da doğrudan kodunuzda bir liste kutusu oluşturabilirsiniz. Doğrudan `CListBox` oluşturmak için, nesneyi oluşturun, sonra Windows liste kutusu denetimini [](#create) oluşturmak ve `CListBox` nesneye iliştirmek için Create member işlevini çağırın. İletişim kutusu şablonunda bir liste kutusu kullanmak için, iletişim kutusu sınıfınızda bir liste kutusu değişkeni bildirin, sonra üye değişkenini denetime bağlamak için `DDX_Control` iletişim kutusu `DoDataExchange` sınıfınızın işlevinde kullanın. (iletişim kutusu sınıfınıza bir denetim değişkeni eklediğinizde bu sizin için otomatik olarak yapılır.)

Oluşturma, öğesinden `CListBox`türetilmiş bir sınıfta tek adımlı bir işlem olabilir. Türetilmiş sınıf için bir Oluşturucu yazın ve oluşturucuyu içinden `Create` çağırın.

Bir liste kutusu tarafından üst öğeye (genellikle [CDialog](../../mfc/reference/cdialog-class.md)'dan türetilmiş bir sınıf) gönderilen Windows bildirim iletilerini işlemek istiyorsanız, her ileti için üst sınıfa bir ileti eşleme girişi ve ileti işleyici üye işlevi ekleyin.

Her ileti eşleme girişi aşağıdaki biçimi alır:

`ON_Notification( id, memberFxn )`

Burada `id` , bildirimi gönderen liste kutusu denetiminin alt pencere kimliğini belirtir ve `memberFxn` bildirimi işlemek için yazdığınız ana üye işlevinin adıdır.

Üst öğenin işlev prototipi aşağıdaki gibidir:

`afx_msg void memberFxn( );`

Aşağıda olası ileti eşleme girişlerinin listesi ve bunların üst öğeye gönderileceği durumların açıklaması verilmiştir:

- ON_LBN_DBLCLK Kullanıcı, liste kutusunda bir dizeyi çift tıklatır. Yalnızca [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiline sahip bir liste kutusu bu bildirim iletisini gönderir.

- ON_LBN_ERRSPACE liste kutusu isteği karşılamak için yeterli bellek ayıramıyor.

- ON_LBN_KILLFOCUS liste kutusu giriş odağını kaybetmekte.

- ON_LBN_SELCANCEL geçerli liste kutusu seçimi iptal edildi. Bu ileti yalnızca bir liste kutusu LBS_NOTIFY stiline sahip olduğunda gönderilir.

- ON_LBN_SELCHANGE liste kutusunda seçimi değişmiştir. Seçim [Clienstbox:: SetCurSel](#setcursel) member işlevi tarafından değiştirilirse bu bildirim gönderilmez. Bu bildirim yalnızca LBS_NOTIFY stiline sahip bir liste kutusu için geçerlidir. Seçim değişmese de, Kullanıcı bir ok tuşuna bastığında, LBN_SELCHANGE bildirim iletisi bir çoklu seçim liste kutusu için gönderilir.

- ON_LBN_SETFOCUS liste kutusu giriş odağını alıyor.

- ON_WM_CHARTOITEM bir WM_CHAR iletisi alan bir sahip çiz liste kutusu.

- LBS_WANTKEYBOARDINPUT stiline sahip bir liste kutusu ON_WM_VKEYTOITEM bir WM_KEYDOWN iletisi alır.

İletişim kutusu içinde ( `CListBox` bir iletişim kaynağı aracılığıyla) bir nesne oluşturursanız `CListBox` , Kullanıcı iletişim kutusunu kapattığında nesne otomatik olarak yok edilir.

Bir pencere içinde bir `CListBox` nesne oluşturursanız, `CListBox` nesneyi yok etmeniz gerekebilir. `CListBox` Nesneyi yığında oluşturursanız, otomatik olarak yok edilir. `CListBox` Nesneyi **Yeni** işlevi kullanarak yığında oluşturursanız, Kullanıcı üst pencereyi kapattığında nesneyi yok etmek için **Delete** öğesini çağırmanız gerekir.

`CListBox` Nesnede herhangi bir bellek ayırırsanız ayırmayı atmak için `CListBox` yıkıcıyı geçersiz kılın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="addstring"></a>Clienstbox:: AddString

Liste kutusuna bir dize ekler.

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>Parametreler

*lpszItem*<br/>
Eklenecek null ile sonlandırılmış dizeyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki dizenin sıfır tabanlı dizini. Bir hata oluşursa, dönüş değeri LB_ERR olur; Yeni dizeyi depolamak için yeterli alan yoksa, dönüş değeri LB_ERRSPACE olur.

### <a name="remarks"></a>Açıklamalar

Liste kutusu [lbs_sort](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulmadıysa, dize listenin sonuna eklenir. Aksi takdirde, dize listeye eklenir ve liste sıralanır. Liste kutusu lbs_sort stiliyle oluşturulduysa ancak [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulduysa çerçeve, listeyi `CompareItem` üye işlevine bir veya daha fazla çağrıya göre sıralar.

Liste kutusu içindeki belirli bir konuma bir dize eklemek için [InsertString](#insertstring) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

##  <a name="chartoitem"></a>Clienstbox:: Chartoıtem

Liste kutusunun ana penceresi liste kutusundan bir WM_CHARTOITEM iletisi aldığında Framework tarafından çağırılır.

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Parametreler

*nAnahtar*<br/>
Kullanıcının girdiği karakterin ANSI kodu.

*nDizin*<br/>
Liste kutusu giriş işaretinin geçerli konumu.

### <a name="return-value"></a>Dönüş Değeri

Daha fazla eylem olmaması için-1 veya-2, tuş vuruşu için varsayılan eylemin gerçekleştirileceği bir liste kutusu öğesinin dizinini belirtmek üzere negatif olmayan bir sayı döndürür. Varsayılan uygulama-1 döndürür.

### <a name="remarks"></a>Açıklamalar

WM_CHARTOITEM iletisi, bir WM_CHAR iletisi aldığında liste kutusu tarafından gönderilir, ancak yalnızca liste kutusu bu ölçütlerin tümünü karşılıyorsa:

- , Bir sahip çizimi liste kutusudur.

- [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stil kümesine sahip değildir.

- En az bir öğesi vardır.

Bu işlevi asla Çağırmamanız gerekir. Klavye iletilerinin kendi özel işlemesini sağlamak için bu işlevi geçersiz kılın.

Geçersiz kılmada, çerçeveye hangi eylemi gerçekleştirdiklerinizi anlatmak için bir değer döndürmeniz gerekir. -1 veya-2 ' nin dönüş değeri, öğe seçme ve liste kutusu tarafından başka bir eylem gerektirmeyen tüm yönlerini karşıladığını gösterir. -1 veya-2 ' yi döndürmeden önce seçimi ayarlayabilir veya giriş işaretini veya her ikisini de taşıyabilirsiniz. Seçimi ayarlamak için [SetCurSel](#setcursel) veya [SetSel](#setsel)kullanın. Giriş işaretini taşımak için [SetCaretIndex](#setcaretindex)kullanın.

0 veya daha büyük bir dönüş değeri, liste kutusunda bir öğenin dizinini belirtir ve liste kutusunun belirtilen öğede tuş vuruşu için varsayılan eylemi gerçekleştirmesini gerektiğini gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

##  <a name="clistbox"></a>Clienstbox:: Clienstbox

Bir `CListBox` nesnesi oluşturur.

```
CListBox();
```

### <a name="remarks"></a>Açıklamalar

İki adımda bir `CListBox` nesne oluşturursunuz. İlk olarak, oluşturucuyu `ClistBox` çağırın ve ardından Windows liste kutusunu başlatan `CListBox`ve öğesine ekleyen çağırın `Create`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

##  <a name="compareitem"></a>Clienstbox:: CompareItem

Sıralanmış bir sahip çiz liste kutusunda yeni bir öğenin göreli konumunu öğrenmek için Framework tarafından çağırılır.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpCompareItemStruct*<br/>
`COMPAREITEMSTRUCT` Yapıya uzun bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

[COMPAREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-compareitemstruct) yapısında açıklanan iki öğenin göreli konumunu gösterir. Aşağıdaki değerlerden herhangi biri olabilir:

|Değer|Açıklama|
|-----------|-------------|
|-1|Öğe 1 öğe 2 ' den önce sıralar.|
|0|Öğe 1 ve öğe 2 aynı şekilde sıralayın.|
|1\.|Öğe 1 öğe 2 ' den sonra sıralar.|

`COMPAREITEMSTRUCT` Yapının açıklaması için bkz. [CWnd:: OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) .

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. LBS_SORT stilinde sahip çizimi olan bir liste kutusu oluşturursanız, çerçeveye, liste kutusuna eklenen yeni öğeleri sıralama konusunda yardımcı olması için bu üye işlevi geçersiz kılmalısınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

##  <a name="create"></a>Clienstbox:: Create

Windows liste kutusunu oluşturur ve `CListBox` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Liste kutusunun stilini belirtir. Kutuya [liste kutusu stillerinin](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) herhangi bir birleşimini uygulayın.

*Rect*<br/>
Liste kutusu boyutunu ve konumunu belirtir. Bir `CRect` nesne`RECT` ya da yapı olabilir.

*pParentWnd*<br/>
Liste kutusunun üst penceresini (genellikle bir `CDialog` nesne) belirtir. NULL olmaması gerekir.

*NID*<br/>
Liste kutusunun Denetim KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda bir `CListBox` nesne oluşturursunuz. İlk olarak, oluşturucuyu çağırın ve sonra Windows `Create`liste kutusunu başlatan ve bunu `CListBox` nesnesine ekleyen çağırın.

[](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) [](../../mfc/reference/cwnd-class.md#oncreate) [](../../mfc/reference/cwnd-class.md#onnccalcsize) [](../../mfc/reference/cwnd-class.md#onnccreate)Yürütüldüğünde, Windows WM_NCCREATE, WM_CREATE, WM_NCCALCSIZE ve WM_GETMINMAXINFO iletilerini liste kutusu denetimine gönderir. `Create`

Bu iletiler, `CWnd` temel sınıftaki [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) member işlevleri tarafından varsayılan olarak işlenir. Varsayılan ileti işlemeyi genişletmek için, öğesinden `CListBox`bir sınıf türetebilir, yeni sınıfa bir ileti haritası ekleyin ve önceki ileti işleyici üye işlevlerini geçersiz kılın. Yeni `OnCreate`bir sınıf için gerekli başlatmayı gerçekleştirmek üzere, örneğin, öğesini geçersiz kılın.

Aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) liste kutusu denetimine uygulayın.

- WS_CHILD her zaman

- WS_VISIBLE genellikle

- WS_DISABLED nadiren

- Dikey kaydırma çubuğunu eklemek Için WS_VSCROLL

- Yatay kaydırma çubuğu eklemek Için WS_HSCROLL

- WS_GROUP denetimleri

- WS_TABSTOP bu denetime sekmeye izin vermek Için

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

##  <a name="deleteitem"></a>Clienstbox::D Eleteıtem

Kullanıcı, sahip çizim `CListBox` nesnesinden bir öğe sildiğinde veya liste kutusunu yok eder, Framework tarafından çağırılır.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Parametreler

*Lpdeleteıtemstruct*<br/>
Silinen öğe hakkında bilgi içeren bir Windows [DELETEITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) yapısına yönelik uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması hiçbir şey yapmaz. Gerektiğinde bir sahip çizimi liste kutusunu yeniden çizmek için bu işlevi geçersiz kılın.

`DELETEITEMSTRUCT` Yapının açıklaması için bkz. [CWnd:: OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

##  <a name="deletestring"></a>Clienstbox::D eleteString

Liste kutusundan *nIndex* konumundaki öğeyi siler.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Silinecek dizenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Listede kalan dizelerin sayısı. *NIndex* , listedeki öğe sayısından daha büyük bir dizin belirtiyorsa, dönüş değeri lb_err olur.

### <a name="remarks"></a>Açıklamalar

*NIndex* ' i izleyen tüm öğeler şimdi bir konum aşağı taşınır. Örneğin, bir liste kutusu iki öğe içeriyorsa, ilk öğeyi silmek kalan öğenin artık ilk konumda olmasına neden olur. ilk konumdaki öğe için *nindex*= 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

##  <a name="dir"></a>Clienstbox::D IR

Bir liste kutusuna dosya adlarının, sürücülerin veya her ikisinin bir listesini ekler.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Parametreler

*özniteliği*<br/>
, ' De `CFile::GetStatu`tanımlanan **enum** değerlerinin herhangi bir birleşimi ya da aşağıdaki değerlerin herhangi bir birleşimi olabilir: [](../../mfc/reference/cfile-class.md#getstatus)

|Değer|Açıklama|
|-----------|-------------|
|0x0000|Dosya, öğesinden okunabilir veya yazılabilir.|
|0x0001|Dosya okunabilir, ancak üzerine yazılamaz.|
|0x0002|Dosya gizlidir ve bir dizin listesinde görünmez.|
|0x0004|Dosya bir sistem dosyasıdır.|
|0x0010|*LpszWildCard* tarafından belirtilen ad bir dizini belirtir.|
|0x0020|Dosya arşivlendi.|
|0x4000|*LpszWildCard*tarafından belirtilen adla eşleşen tüm sürücüleri ekleyin.|
|0x8000|Dışlamalı bayrak. Dışlamalı bayrak ayarlandıysa, yalnızca belirtilen türdeki dosyalar listelenir. Aksi halde, belirtilen türdeki dosyalar "normal" dosyalara ek olarak listelenir.|

*lpszWildCard*<br/>
Dosya belirtimi dizesini işaret eder. Dize joker karakterler içerebilir (örneğin, *.\*).

### <a name="return-value"></a>Dönüş Değeri

Listeye eklenen son dosya adının sıfır tabanlı dizini. Bir hata oluşursa, dönüş değeri LB_ERR olur; Yeni dizeleri depolamak için yeterli alan yoksa, dönüş değeri LB_ERRSPACE olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

##  <a name="drawitem"></a>Clienstbox::D rawItem

Bir sahip çizimi liste kutusunun görsel yönü değiştiğinde Framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına yönelik uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yapının ve `itemState` üyeleri gerçekleştirilecek çizim eylemini tanımlar. `itemAction` `DRAWITEMSTRUCT`

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bir sahip çizim `CListBox` nesnesi için çizimi uygulamak üzere bu üye işlevini geçersiz kılın. Uygulamanın, bu üye işlevi sonlandırılmadan önce *Lpdrawitemstruct* içinde sağlanan görüntüleme bağlamı için seçilen tüm grafik cihaz ARABIRIMI (GDI) nesnelerini geri yüklemesi gerekir.

`DRAWITEMSTRUCT` Yapının açıklaması için bkz. [CWnd:: OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

##  <a name="findstring"></a>Clienstbox:: FindString

Liste kutusu seçimini değiştirmeden belirtilen öneki içeren bir liste kutusunda ilk dizeyi bulur.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>Parametreler

*nStartAfter*<br/>
Aranacak ilk öğeden önceki öğenin sıfır tabanlı dizinini içerir. Arama liste kutusunun en altına ulaştığında, liste kutusunun en üstünden *nStartAfter*tarafından belirtilen öğeye kadar devam eder. *NStartAfter* -1 ise, tüm liste kutusu başlangıçtan itibaren aranır.

*lpszItem*<br/>
Arama yapılacak öneki içeren null ile sonlandırılmış dizeyi işaret eder. Arama büyük/küçük harfe bağımsızdır, bu nedenle bu dize büyük ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen öğenin sıfır tabanlı dizini veya arama başarısız ise LB_ERR.

### <a name="remarks"></a>Açıklamalar

Bir dizeyi bulmak ve seçmek için [SelectString](#selectstring) üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

##  <a name="findstringexact"></a>Clienstbox:: Findstringözdeş

*LpszFind*içinde belirtilen dizeyle eşleşen ilk liste kutusu dizesini bulur.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Parametreler

*nIndexStart*<br/>
Aranacak ilk öğeden önce öğenin sıfır tabanlı dizinini belirtir. Arama liste kutusunun en altına ulaştığında, liste kutusunun en üstünden *nIndexStart*tarafından belirtilen öğeye geri devam eder. *NIndexStart* -1 ise, tüm liste kutusu başlangıçtan itibaren aranır.

*lpszFind*<br/>
Aranacak null ile sonlandırılmış dizeyi gösterir. Bu dize, uzantısı dahil olmak üzere tam bir dosya adı içerebilir. Arama büyük/küçük harfe duyarlı değildir, bu nedenle dize büyük ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen öğenin dizini veya arama başarısız olduysa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Liste kutusu bir sahip çizimi stiliyle oluşturulduysa ancak [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili olmadan oluşturulmuşsa, `FindStringExact` üye işlevi doubleword değerini *lpszFind*değeriyle eşleştirmeye çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

##  <a name="getanchorindex"></a>Clienstbox:: Getanchorındex

Liste kutusunda geçerli bağlayıcı öğesinin sıfır tabanlı dizinini alır.

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa geçerli bağlayıcı öğesinin dizini; Aksi halde LB_ERR.

### <a name="remarks"></a>Açıklamalar

Birden çok seçimli liste kutusunda, tutturucu öğesi, ardışık seçili öğelerin bloğundaki ilk veya son öğedir.

### <a name="example"></a>Örnek

  [CListBox:: SetAnchorIndex](#setanchorindex)örneğine bakın.

##  <a name="getcaretindex"></a>Clienstbox:: Getcaretındex

Birden çok seçimli liste kutusunda odak dikdörtgeni olan öğenin dizinini belirler.

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir liste kutusunda odak dikdörtgeni olan öğenin sıfır tabanlı dizini. Liste kutusu tek seçimli bir liste kutusu ise, dönüş değeri, varsa seçilen öğenin dizinidir.

### <a name="remarks"></a>Açıklamalar

Öğe seçilemeyebilir veya seçilmeyebilir.

### <a name="example"></a>Örnek

  [CListBox:: SetCaretIndex](#setcaretindex)için örneğe bakın.

##  <a name="getcount"></a>Clienstbox:: GetCount

Liste kutusundaki öğelerin sayısını alır.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki öğelerin sayısı veya bir hata oluşursa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Döndürülen sayı, son öğenin dizin değerinden (Dizin sıfır tabanlı) büyük bir değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

##  <a name="getcursel"></a>Clienstbox:: GetCurSel

Seçili olan öğenin sıfır tabanlı dizinini, varsa, tek seçimli liste kutusunda alır.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tek seçimli liste kutusun seçili olan öğenin sıfır tabanlı dizini. Şu anda seçili bir öğe yoksa, LB_ERR.

Birden çok seçimli liste kutusunda, odağa sahip olan öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Birden çok seçimli `GetCurSel` liste kutusu için çağrı kullanmayın. Bunun yerine [Clienstbox:: GetSelItems](#getselitems) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

##  <a name="gethorizontalextent"></a>Clienstbox:: GetHorizontalExtent

Yatay olarak kaydırılabileceği, liste kutusundan genişliği piksel cinsinden alır.

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunun piksel cinsinden kaydırılabilir genişliği.

### <a name="remarks"></a>Açıklamalar

Bu, yalnızca liste kutusunda yatay kaydırma çubuğu varsa geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

##  <a name="getitemdata"></a>Clienstbox:: GetItemData

Belirtilen liste kutusu öğesiyle ilişkili, uygulama tarafından sağlanan doubleword değerini alır.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusunda öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa, öğesiyle ilişkili değer veya LB_ERR.

### <a name="remarks"></a>Açıklamalar

Doubleword değeri, bir [SetItemData](#setitemdata) çağrısının *dwitemdata* parametresidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

##  <a name="getitemdataptr"></a>Clienstbox:: GetItemDataPtr

Belirtilen liste kutusu öğesiyle ilişkili uygulama tarafından sağlanan 32 bitlik değeri işaretçi (**void** <strong>\*</strong>) olarak alır.

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusunda öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi alır veya bir hata oluşursa-1.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

##  <a name="getitemheight"></a>Clienstbox:: GetItemHeight

Bir liste kutusundaki öğelerin yüksekliğini belirler.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusunda öğenin sıfır tabanlı dizinini belirtir. Bu parametre yalnızca liste kutusunda LBS_OWNERDRAWVARIABLE stili varsa kullanılır; Aksi takdirde, 0 olarak ayarlanmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki öğelerin piksel cinsinden yüksekliği. Liste kutusunda [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili varsa, dönüş değeri *nIndex*tarafından belirtilen öğenin yüksekliğidir. Bir hata oluşursa, dönüş değeri LB_ERR ' dir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

##  <a name="getitemrect"></a>Clienstbox:: GetItemRect

Liste kutusu penceresinde görüntülenmekte olan bir liste kutusu öğesini alan dikdörtgenin boyutlarını alır.

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Öğenin sıfır tabanlı dizinini belirtir.

*lpRect*<br/>
Öğenin liste kutusu istemci koordinatlarını alan bir [Rect yapısına](/windows/win32/api/windef/ns-windef-rect) yönelik uzun bir işaretçi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa LB_ERR.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

##  <a name="getlistboxinfo"></a>Clienstbox:: Getlistboxınfo

Sütun başına öğe sayısını alır.

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CListBox` Nesnenin sütun başına öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi [LB_GETLISTBOXINFO](/windows/win32/Controls/lb-getlistboxinfo) iletisinin işlevselliğine öykünür.

##  <a name="getlocale"></a>Clienstbox:: GetLocale

Liste kutusu tarafından kullanılan yerel ayarı alır.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki dizeler için yerel ayar tanıtıcısı (LCıD) değeri.

### <a name="remarks"></a>Açıklamalar

Yerel ayar, örneğin, sıralanmış bir liste kutusunda dizelerin sıralama düzenini tespit etmek için kullanılır.

### <a name="example"></a>Örnek

  [CListBox:: setlocale](#setlocale)örneğine bakın.

##  <a name="getsel"></a>Clienstbox:: GetSel

Bir öğenin seçim durumunu alır.

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe seçilmişse pozitif bir sayı; Aksi takdirde, 0 ' dır. Bir hata oluşursa dönüş değeri LB_ERR olur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hem tek hem de birden çok seçimli liste kutularıyla çalışır.

Şu anda seçili olan liste kutusu öğesinin dizinini almak için [CListBox:: GetCurSel](#getcursel)' i kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

##  <a name="getselcount"></a>Clienstbox:: GetSelCount

Birden çok seçimli liste kutusunda seçili öğelerin toplam sayısını alır.

```
int GetSelCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki seçili öğelerin sayısı. Liste kutusu tek seçimli bir liste kutusu ise, dönüş değeri LB_ERR ' dir.

### <a name="example"></a>Örnek

  [CListBox:: Getselilıtems](#getselitems)örneğine bakın.

##  <a name="getselitems"></a>Clienstbox:: GetSelItems

Birden çok seçimli liste kutusunda seçili öğelerin öğe numaralarını belirten tamsayılar dizisiyle bir arabelleği doldurur.

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>Parametreler

*nMaxItems*<br/>
Öğe numaraları arabelleğe yerleştirilecek olan seçili öğe sayısı üst sınırını belirtir.

*Rgındex*<br/>
*NMaxItems*tarafından belirtilen tamsayı sayısı için yeterince büyük bir arabellek işaretçisi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Arabelleğe yerleştirilmiş olan öğelerin gerçek sayısı. Liste kutusu tek seçimli bir liste kutusu ise, dönüş değeri olur `LB_ERR`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

##  <a name="gettext"></a>Clienstbox:: GetText

Bir liste kutusundan bir dize alır.

```
int GetText(
    int nIndex,
    LPTSTR lpszBuffer) const;

void GetText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Alınacak dizenin sıfır tabanlı dizinini belirtir.

*lpszBuffer*<br/>
Dizeyi alan arabelleğe işaret eder. Arabellekte dize ve Sonlandırıcı null karakteri için yeterli alan olması gerekir. Dize boyutu, `GetTextLen` üye işlevi çağırarak zaman önünde belirlenebilir.

*rString*<br/>
Bir `CString` nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Dizenin sonlandırılıyor null karakteri hariç uzunluğu (bayt cinsinden). *NIndex* geçerli bir dizin belirtmezse, dönüş değeri lb_err olur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin ikinci formu, bir `CString` nesneyi dize metniyle doldurur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

##  <a name="gettextlen"></a>Clienstbox:: GetTextLen

Bir liste kutusu öğesindeki bir dizenin uzunluğunu alır.

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Dizenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Dizenin, Sonlandırıcı null karakteri hariç karakter cinsinden uzunluğu. *NIndex* geçerli bir dizin belirtmezse, dönüş değeri lb_err olur.

### <a name="example"></a>Örnek

  [CListBox:: GetText](#gettext)örneğine bakın.

##  <a name="gettopindex"></a>Clienstbox:: GetTopIndex

Liste kutusunda ilk görünür öğenin sıfır tabanlı dizinini alır.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, LB_ERR Aksi halde, bir liste kutusundaki ilk görünür öğenin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Başlangıçta, öğe 0 liste kutusunun en üstünde, ancak liste kutusu kaydırıldığında, en üstte başka bir öğe olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

##  <a name="initstorage"></a>Clienstbox:: ınitstorage

Liste kutusu öğelerini depolamak için bellek ayırır.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>Parametreler

*nItems*<br/>
Eklenecek öğelerin sayısını belirtir.

*nBytes*<br/>
Öğe dizeleri için ayrılacak bellek miktarını bayt cinsinden belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bir bellek yeniden tahsisatı gerekmeden önce liste kutusunun depolayabileceği en fazla öğe sayısı, aksi takdirde LB_ERRSPACE, ancak yeterli bellek yok.

### <a name="remarks"></a>Açıklamalar

' A `CListBox`çok sayıda öğe eklemeden önce bu işlevi çağırın.

Bu işlev, çok sayıda öğe (100 ' den fazla) olan liste kutularının başlatılmasını hızlandırmaya yardımcı olur. Sonraki [AddString](#addstring), [InsertString](#insertstring)ve [dir](#dir) işlevlerinin olası en kısa süreyi alması için belirtilen bellek miktarını önceden ayırır. Parametreler için tahminleri kullanabilirsiniz. Fazla tahmin ediyorsanız, bazı ek bellek ayrılır; tahmin ediyorsanız, önceden ayrılan miktarı aşan öğeler için normal ayırma kullanılır.

Yalnızca Windows 95/98: *NItems* parametresi 16 bit değerlerle sınırlıdır. Bu, liste kutularının 32.767 taneden fazla öğe içeremeyeceği anlamına gelir. Öğe sayısı kısıtlanmış olsa da, bir liste kutusundaki öğelerin toplam boyutu yalnızca kullanılabilir bellekle sınırlıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

##  <a name="insertstring"></a>CListBox:: InsertString

Liste kutusuna bir dize ekler.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Dizeyi eklemek için konumun sıfır tabanlı dizinini belirtir. Bu parametre-1 ise, dize listenin sonuna eklenir.

*lpszItem*<br/>
Eklenecek null ile sonlandırılmış dizeyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Dizenin eklendiği konumun sıfır tabanlı dizini. Bir hata oluşursa, dönüş değeri LB_ERR olur; Yeni dizeyi depolamak için yeterli alan yoksa, dönüş değeri LB_ERRSPACE olur.

### <a name="remarks"></a>Açıklamalar

[AddString](#addstring) üye işlevinin aksine, `InsertString` [lbs_sort](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili sıralanarak bir listeye neden olmaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

##  <a name="itemfrompoint"></a>Clienstbox:: ItemFromPoint

*PT*olarak belirtilen noktayı en yakın olan liste kutusu öğesini belirler.

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
Liste kutusunun istemci alanının sol üst köşesine göre belirtilen en yakın öğenin bulunacağı nokta.

*i tarafı*<br/>
*PT* en yakın liste kutusu öğesinin istemci ALANıNıN dışındaysa true olarak AYARLANACAK bir bool değişkenine başvuru, PT ise en yakın liste kutusu öğesinin istemci ALANıNıN içindeyse false olur.

### <a name="return-value"></a>Dönüş Değeri

En yakın öğenin, *PT*olarak belirtilen noktaya ait dizini.

### <a name="remarks"></a>Açıklamalar

Bu işlevi, fare imlecinin hangi liste kutusu öğesine taşındığını öğrenmek için kullanabilirsiniz.

### <a name="example"></a>Örnek

  [CListBox:: SetAnchorIndex](#setanchorindex)örneğine bakın.

##  <a name="measureitem"></a>Clienstbox:: MeasureItem

Sahip çizim stili olan bir liste kutusu oluşturulduğunda Framework tarafından çağırılır.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) yapısına yönelik uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bu üye işlevini geçersiz kılın ve liste kutusu `MEASUREITEMSTRUCT` boyutlarının pencerelerini bilgilendirmek için yapıyı girin. Liste kutusu [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulduysa, çerçeve liste kutusundaki her öğe için bu üye işlevini çağırır. Aksi takdirde, bu üye yalnızca bir kez çağrılır.

`SubclassDlgItem` Üye işleviyle`CWnd`oluşturulan bir sahip çizimi liste kutusunda [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stilini kullanma hakkında daha fazla bilgi için, [Teknik not14](../../mfc/tn014-custom-controls.md)' te tartışmaya bakın.

`MEASUREITEMSTRUCT` Yapının açıklaması için bkz. [CWnd:: OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

##  <a name="resetcontent"></a>Clienstbox:: ResetContent

Tüm öğeleri bir liste kutusundan kaldırır.

```
void ResetContent();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

##  <a name="selectstring"></a>CListBox:: SelectString

Belirtilen dizeyle eşleşen bir liste kutusu öğesi arar ve eşleşen bir öğe bulunursa öğeyi seçer.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Parametreler

*nStartAfter*<br/>
Aranacak ilk öğeden önceki öğenin sıfır tabanlı dizinini içerir. Arama liste kutusunun en altına ulaştığında, liste kutusunun en üstünden *nStartAfter*tarafından belirtilen öğeye kadar devam eder. *NStartAfter* -1 ise, tüm liste kutusu başlangıçtan itibaren aranır.

*lpszItem*<br/>
Arama yapılacak öneki içeren null ile sonlandırılmış dizeyi işaret eder. Arama büyük/küçük harfe bağımsızdır, bu nedenle bu dize büyük ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Arama başarılı olursa seçili öğenin dizini. Arama başarısız olduysa, dönüş değeri LB_ERR olur ve geçerli seçim değiştirilmez.

### <a name="remarks"></a>Açıklamalar

Seçili öğeyi görünüme getirmek için gerekiyorsa liste kutusu kaydırıldı.

Bu üye işlevi, [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiline sahip bir liste kutusuyla birlikte kullanılamaz.

Yalnızca ilk karakterleri (başlangıç noktasından) *lpszItem*tarafından belirtilen dizedeki karakterlerle eşleşiyorsa bir öğe seçilir.

Öğeyi seçmeden bir dize bulmak için üyeişlevinikullanın.`FindString`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

##  <a name="selitemrange"></a>CListBox:: SelItemRange

Birden çok seçimli liste kutusunda birden çok ardışık öğe seçer.

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>Parametreler

*bSelect*<br/>
Seçimin nasıl ayarlanacağını belirtir. *BSelect* true ise, dize seçilir ve vurgulanır; FALSE ise, vurgu kaldırılır ve dize artık seçili olmaz.

*Nfirtıtem*<br/>
Ayarlanacak ilk öğenin sıfır tabanlı dizinini belirtir.

*Nlatıtem*<br/>
Ayarlanacak son öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca birden çok seçimli liste kutularıyla kullanın. Birden çok seçimli liste kutusunda yalnızca bir öğe seçmeniz gerekiyorsa — Yani, *Nfirtıtem* *nlatıtem* 'a eşitse — bunun yerine [SetSel](#setsel) üye işlevini çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

##  <a name="setanchorindex"></a>Clienstbox:: SetAnchorIndex

Bir genişletilmiş seçimi başlatmak için birden çok seçimli liste kutusunda yer alan bağlayıcıyı ayarlar.

```
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Tutturucu olacak liste kutusu öğesinin sıfır tabanlı dizinini belirtir.

### <a name="remarks"></a>Açıklamalar

Birden çok seçimli liste kutusunda, tutturucu öğesi, ardışık seçili öğelerin bloğundaki ilk veya son öğedir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

##  <a name="setcaretindex"></a>Clienstbox:: SetCaretIndex

Bir çok seçimli liste kutusunda belirtilen dizindeki öğeye odak dikdörtgenini ayarlar.

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusunda odak dikdörtgenini alacak öğenin sıfır tabanlı dizinini belirtir.

*bScroll*<br/>
Bu değer 0 ise, öğe tamamen görünene kadar kaydırıldı. Bu değer 0 değilse, öğe en az kısmen görünene kadar kaydırıldı.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Öğe görünür değilse, görünüme kaydırılacağından.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

##  <a name="setcolumnwidth"></a>Clienstbox:: SetColumnWidth

Birden çok sütunlu liste kutusu içindeki tüm sütunların piksel cinsinden genişliğini ayarlar ( [LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulur).

```
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>Parametreler

*cxWidth*<br/>
Tüm sütunların piksel cinsinden genişliğini belirtir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

##  <a name="setcursel"></a>Clienstbox:: SetCurSel

Bir dize seçer ve gerekirse görünüme kaydırır.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Parametreler

*Nyükseltmeye*<br/>
Seçilecek dizenin sıfır tabanlı dizinini belirtir. *NSelect* -1 ise, liste kutusu seçim olmayacak şekilde ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Yeni dize seçildiğinde, liste kutusu daha önce seçilen dizeden vurgulamayı kaldırır.

Bu üye işlevini yalnızca tek seçimli liste kutularıyla kullanın.

Bir seçimi çoklu seçim liste kutusunda ayarlamak veya kaldırmak için [CListBox:: SetSel](#setsel)komutunu kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

##  <a name="sethorizontalextent"></a>Clienstbox:: SetHorizontalExtent

Bir liste kutusunun yatay olarak kaydırılabileceği piksel cinsinden genişliği belirler.

```
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>Parametreler

*Cxkapsam*<br/>
Liste kutusunun yatay olarak kaydırılabileceği piksel sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Liste kutusunun boyutu bu değerden küçükse, yatay kaydırma çubuğu liste kutusunda öğeleri yatay olarak kaydıracaktır. Liste kutusu bu değerden büyükse veya daha büyükse, yatay kaydırma çubuğu gizlenir.

Bir çağrısına `SetHorizontalExtent`yanıt vermek için liste kutusu [ws_hscroll](../../mfc/reference/styles-used-by-mfc.md#window-styles) stiliyle tanımlanmış olmalıdır.

Bu üye işlevi çok sütunlu liste kutuları için yararlı değildir. Birden çok sütunlu liste kutuları için `SetColumnWidth` üye işlevini çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

##  <a name="setitemdata"></a>Clienstbox:: SetItemData

Liste kutusunda belirtilen öğeyle ilişkili bir değer ayarlar.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Öğenin sıfır tabanlı dizinini belirtir.

*dwItemData*<br/>
Öğeyle ilişkilendirilecek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa LB_ERR.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

##  <a name="setitemdataptr"></a>Clienstbox:: SetItemDataPtr

Liste kutusundaki belirtilen öğeyle ilişkili 32 bitlik değeri belirtilen işaretçi ( **void** <strong>\*</strong>) olarak ayarlar.

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Öğenin sıfır tabanlı dizinini belirtir.

*pData*<br/>
Öğeyle ilişkilendirilecek işaretçiyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu işaretçi liste kutusunun ömrü boyunca geçerli kalır, ancak öğe eklendiğinde veya kaldırıldığında öğenin liste kutusu içindeki göreli konumu değişebilir. Bu nedenle, öğenin kutu içindeki dizini değişebilir, ancak işaretçi güvenilir kalır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

##  <a name="setitemheight"></a>Clienstbox:: SetItemHeight

Liste kutusundaki öğelerin yüksekliğini ayarlar.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusunda öğenin sıfır tabanlı dizinini belirtir. Bu parametre yalnızca liste kutusunda LBS_OWNERDRAWVARIABLE stili varsa kullanılır; Aksi takdirde, 0 olarak ayarlanmalıdır.

*Cyıtemheight*<br/>
Öğenin piksel cinsinden yüksekliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Dizin veya yükseklik geçersiz ise LB_ERR.

### <a name="remarks"></a>Açıklamalar

Liste kutusunda [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili varsa, bu Işlev *nIndex*tarafından belirtilen öğenin yüksekliğini ayarlar. Aksi takdirde, bu işlev liste kutusundaki tüm öğelerin yüksekliğini ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

##  <a name="setlocale"></a>Clienstbox:: SetLocale

Bu liste kutusu için yerel ayar tanıtıcısını ayarlar.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Parametreler

*nNewLocale*<br/>
Liste kutusu için ayarlanacak yeni yerel ayar tanıtıcısı (LCıD) değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu liste kutusu için önceki yerel ayar tanıtıcısı (LCıD) değeri.

### <a name="remarks"></a>Açıklamalar

Çağrılmaması durumunda `SetLocale` , varsayılan yerel ayar sistemden alınır. Bu sistem varsayılan yerel ayarı, Denetim Masası 'nın bölgesel (veya uluslararası) uygulaması kullanılarak değiştirilebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

##  <a name="setsel"></a>Clienstbox:: SetSel

Birden çok seçimli liste kutusunda bir dize seçer.

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Ayarlanacak dizenin sıfır tabanlı dizinini içerir. -1 ise, seçim, *bSelect*değerine bağlı olarak tüm dizelere eklenir veya kaldırılır.

*bSelect*<br/>
Seçimin nasıl ayarlanacağını belirtir. *BSelect* true ise, dize seçilir ve vurgulanır; FALSE ise, vurgu kaldırılır ve dize artık seçili olmaz. Belirtilen dize seçilidir ve varsayılan olarak vurgulanır.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca birden çok seçimli liste kutularıyla kullanın.

Tek seçimli liste kutusundan bir öğe seçmek için [CListBox:: SetCurSel](#setcursel)komutunu kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

##  <a name="settabstops"></a>Clienstbox:: Settabstop

Liste kutusunda sekme durağı konumlarını ayarlar.

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Parametreler

*cxEachStop*<br/>
Sekme duraklarının her *cxEachStop* diyalog birimlerinde ayarlandığı. Bir iletişim biriminin açıklaması için bkz. *Rgtabstop* .

*Ntabstop*<br/>
Liste kutusunda sahip olacak sekme duraklarının sayısını belirtir.

*Rgtabstop*<br/>
Diyalog birimlerindeki sekme durağı konumlarını içeren bir tamsayılar dizisinin ilk üyesini işaret eder. İletişim kutusu birimi yatay veya dikey bir uzaklığına sahiptir. Bir yatay iletişim kutusu birimi, geçerli iletişim kutusu taban genişliği biriminin dörtte birine eşittir ve bir dikey iletişim birimi geçerli iletişim kutusu Taban yükseklik biriminin sekizde birine eşittir. İletişim kutusu temel birimleri geçerli sistem yazı tipinin yüksekliği ve genişliğine göre hesaplanır. Windows `GetDialogBaseUnits` işlevi, geçerli iletişim kutusu taban birimlerini piksel cinsinden döndürür. Sekme duraklarının artan sırada sıralanması gerekir; geri sekmelere izin verilmez.

### <a name="return-value"></a>Dönüş Değeri

Tüm sekmeler ayarlandıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sekme duraklarını varsayılan 2 iletişim kutusu birimi olarak ayarlamak için, bu üye işlevin parametresiz sürümünü çağırın. Sekme duraklarının 2 dışında bir boyuta ayarlanması için, bu sürümü *cxEachStop* bağımsız değişkeniyle çağırın.

Sekme duraklarını bir boyut dizisine göre ayarlamak için, bu sürümü *rgtabstop* ve *ntabstop* bağımsız değişkenleriyle kullanın. *Rgtabstop*'taki her bir değer Için, *ntabstop*tarafından belirtilen sayıya kadar bir sekme durağı ayarlanır.

`SetTabStops` Üye işlevine yapılan çağrıya yanıt vermek için, liste kutusu [lbs_usetabstops](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulmuş olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

##  <a name="settopindex"></a>Clienstbox:: Settopındex

Belirli bir liste kutusu öğesinin görünür olmasını sağlar.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusu öğesinin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır veya bir hata oluşursa LB_ERR.

### <a name="remarks"></a>Açıklamalar

Sistem liste kutusunu, *nIndex* tarafından belirtilen öğe liste kutusunun en üstünde görünene veya en fazla kaydırma aralığına ulaşılana kadar kaydırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

##  <a name="vkeytoitem"></a>Clienstbox:: Vkeytoıtem

Liste kutusunun ana penceresi liste kutusundan bir WM_VKEYTOITEM iletisi aldığında Framework tarafından çağırılır.

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Parametreler

*nAnahtar*<br/>
Kullanıcıya basılan anahtarın sanal anahtar kodu. Standart sanal anahtar kodlarının listesi için bkz. Winuser. h

*nDizin*<br/>
Liste kutusu giriş işaretinin geçerli konumu.

### <a name="return-value"></a>Dönüş Değeri

Daha fazla işlem olmaması için-2, varsayılan eylem için 1, veya tuş vuruşu için varsayılan eylemin gerçekleştirileceği bir liste kutusu öğesinin dizinini belirtmek için negatif olmayan bir sayı döndürür.

### <a name="remarks"></a>Açıklamalar

WM_VKEYTOITEM iletisi, WM_KEYDOWN iletisi aldığında liste kutusu tarafından gönderilir, ancak yalnızca liste kutusu aşağıdakilerin her ikisini de karşılıyorsa:

- [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stil kümesine sahiptir.

- En az bir öğesi vardır.

Bu işlevi asla Çağırmamanız gerekir. Klavye iletilerinin kendi özel işlemesini sağlamak için bu işlevi geçersiz kılın.

Bir değeri, geçersiz kılmanın hangi eylemde olduğunu söylemek için bir değer döndürmeniz gerekir. -2 ' nin dönüş değeri, uygulamanın öğeyi seçme ve liste kutusu tarafından başka bir eylem gerektirmesinin tüm yönlerini yaptığını gösterir. -2 ' yi döndürmeden önce seçimi ayarlayabilir veya giriş işaretini veya her ikisini de taşıyabilirsiniz. Seçimi ayarlamak için [SetCurSel](#setcursel) veya [SetSel](#setsel)kullanın. Giriş işaretini taşımak için [SetCaretIndex](#setcaretindex)kullanın.

-1 ' in dönüş değeri, liste kutusunun tuş vuruşunda varsayılan eylemi gerçekleştirmesi gerektiğini gösterir. Varsayılan uygulama-1 döndürür.

0 veya daha büyük bir dönüş değeri, liste kutusunda bir öğenin dizinini belirtir ve liste kutusunun belirtilen öğede tuş vuruşu için varsayılan eylemi gerçekleştirmesini gerektiğini gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CButton Sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CScrollBar Sınıfı](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic Sınıfı](../../mfc/reference/cstatic-class.md)
