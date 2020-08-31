---
title: CComboBox sınıfı
description: MFC Windows Birleşik giriş kutusu sınıfı CComboBox için API başvurusu
ms.date: 08/27/2020
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
helpviewer_keywords:
- CComboBox [MFC], CComboBox
- CComboBox [MFC], AddString
- CComboBox [MFC], Clear
- CComboBox [MFC], CompareItem
- CComboBox [MFC], Copy
- CComboBox [MFC], Create
- CComboBox [MFC], Cut
- CComboBox [MFC], DeleteItem
- CComboBox [MFC], DeleteString
- CComboBox [MFC], Dir
- CComboBox [MFC], DrawItem
- CComboBox [MFC], FindString
- CComboBox [MFC], FindStringExact
- CComboBox [MFC], GetComboBoxInfo
- CComboBox [MFC], GetCount
- CComboBox [MFC], GetCueBanner
- CComboBox [MFC], GetCurSel
- CComboBox [MFC], GetDroppedControlRect
- CComboBox [MFC], GetDroppedState
- CComboBox [MFC], GetDroppedWidth
- CComboBox [MFC], GetEditSel
- CComboBox [MFC], GetExtendedUI
- CComboBox [MFC], GetHorizontalExtent
- CComboBox [MFC], GetItemData
- CComboBox [MFC], GetItemDataPtr
- CComboBox [MFC], GetItemHeight
- CComboBox [MFC], GetLBText
- CComboBox [MFC], GetLBTextLen
- CComboBox [MFC], GetLocale
- CComboBox [MFC], GetMinVisible
- CComboBox [MFC], GetTopIndex
- CComboBox [MFC], InitStorage
- CComboBox [MFC], InsertString
- CComboBox [MFC], LimitText
- CComboBox [MFC], MeasureItem
- CComboBox [MFC], Paste
- CComboBox [MFC], ResetContent
- CComboBox [MFC], SelectString
- CComboBox [MFC], SetCueBanner
- CComboBox [MFC], SetCurSel
- CComboBox [MFC], SetDroppedWidth
- CComboBox [MFC], SetEditSel
- CComboBox [MFC], SetExtendedUI
- CComboBox [MFC], SetHorizontalExtent
- CComboBox [MFC], SetItemData
- CComboBox [MFC], SetItemDataPtr
- CComboBox [MFC], SetItemHeight
- CComboBox [MFC], SetLocale
- CComboBox [MFC], SetMinVisibleItems
- CComboBox [MFC], SetTopIndex
- CComboBox [MFC], ShowDropDown
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
ms.openlocfilehash: 515a079ca4f6c3896733bbebec424f63455fb979
ms.sourcegitcommit: c8f1605354724a13566bc3b0fac3c5d98265f1d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2020
ms.locfileid: "89062191"
---
# <a name="ccombobox-class"></a>CComboBox sınıfı

Windows Birleşik giriş kutusunun işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CComboBox : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComboBox:: CComboBox](#ccombobox)|Bir `CComboBox` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComboBox:: AddString](#addstring)|Birleşik giriş kutusunun liste kutusunda veya CBS_SORT stiliyle liste kutularına ilişkin sıralanmış konumda listenin sonuna bir dize ekler.|
|[CComboBox:: Clear](#clear)|Eğer varsa, düzenleme denetimindeki geçerli seçimi siler (temizler).|
|[CComboBox:: CompareItem](#compareitem)|Sıralanmış bir sahip tarafından çizilen birleşik giriş kutusunda yeni liste öğesinin göreli konumunu öğrenmek için Framework tarafından çağırılır.|
|[CComboBox:: Copy](#copy)|Varsa, geçerli seçimi Pano üzerine CF_TEXT biçimde kopyalar.|
|[CComboBox:: Create](#create)|Birleşik giriş kutusunu oluşturur ve `CComboBox` nesneye ekler.|
|[CComboBox:: kes](#cut)|, Varsa, düzenleme denetimindeki geçerli seçimi siler (keser) ve silinen metni pano üzerinde CF_TEXT biçiminde kopyalar.|
|[CComboBox::D Eleteıtem](#deleteitem)|Bir liste öğesi, sahip tarafından çizilmiş Birleşik giriş kutusundan silindiğinde Framework tarafından çağırılır.|
|[CComboBox::D eleteString](#deletestring)|Birleşik giriş kutusunun liste kutusundan bir dizeyi siler.|
|[CComboBox::D IR](#dir)|Birleşik giriş kutusunun liste kutusuna dosya adlarının bir listesini ekler.|
|[CComboBox::D rawItem](#drawitem)|Sahip tarafından çizilmiş Birleşik giriş kutusunun görsel bir yönü değiştiğinde Framework tarafından çağırılır.|
|[CComboBox:: FindString](#findstring)|Birleşik giriş kutusunun liste kutusunda belirtilen öneki içeren ilk dizeyi bulur.|
|[CComboBox:: Findstringözdeş](#findstringexact)|Belirtilen dizeyle eşleşen ilk liste kutusu dizesini (Birleşik giriş kutusunda) bulur.|
|[CComboBox:: Getcomboboxınfo](#getcomboboxinfo)|Nesnesi hakkında bilgi alır `CComboBox` .|
|[CComboBox:: GetCount](#getcount)|Birleşik giriş kutusunun liste kutusundaki öğelerin sayısını alır.|
|[CComboBox:: Getcuebaşlık](#getcuebanner)|Birleşik giriş kutusu denetimi için görüntülenen ipucu metnini alır.|
|[CComboBox:: GetCurSel](#getcursel)|Seçili olan öğenin dizinini, varsa Birleşik giriş kutusunun liste kutusunda alır.|
|[CComboBox:: GetDroppedControlRect](#getdroppedcontrolrect)|Açılan Birleşik giriş kutusunun görünür (bırakılmış) liste kutusunun ekran koordinatlarını alır.|
|[CComboBox:: GetDroppedState](#getdroppedstate)|Açılan Birleşik giriş kutusu liste kutusunun görünür olup olmadığını belirler (aşağı açılan).|
|[CComboBox:: GetDroppedWidth](#getdroppedwidth)|Birleşik giriş kutusunun aşağı açılan liste kutusu bölümü için izin verilen en düşük genişliği alır.|
|[CComboBox:: GetEditSel](#geteditsel)|Birleşik giriş kutusunun düzenleme denetimindeki geçerli seçimin başlangıç ve bitiş karakter konumlarını alır.|
|[CComboBox:: Getckesintileri ı](#getextendedui)|Birleşik giriş kutusunun varsayılan kullanıcı arabirimine mi yoksa Genişletilmiş Kullanıcı arabirimine mi sahip olduğunu belirler.|
|[CComboBox:: GetHorizontalExtent](#gethorizontalextent)|Birleşik giriş kutusunun liste kutusu bölümünün yatay olarak kaydırılabileceği piksel cinsinden genişliği döndürür.|
|[CComboBox:: GetItemData](#getitemdata)|Belirtilen Birleşik giriş kutusu öğesiyle ilişkili uygulama tarafından sağlanan 32 bitlik değeri alır.|
|[CComboBox:: GetItemDataPtr](#getitemdataptr)|Belirtilen Birleşik giriş kutusu öğesiyle ilişkili uygulama tarafından sağlanan 32 bitlik işaretçiyi alır.|
|[CComboBox:: GetItemHeight](#getitemheight)|Birleşik giriş kutusundaki liste öğelerinin yüksekliğini alır.|
|[CComboBox:: GetLBText](#getlbtext)|Birleşik giriş kutusunun liste kutusundan bir dize alır.|
|[CComboBox:: GetLBTextLen](#getlbtextlen)|Birleşik giriş kutusunun liste kutusunda bir dizenin uzunluğunu alır.|
|[CComboBox:: GetLocale](#getlocale)|Birleşik giriş kutusu için yerel ayar tanıtıcısını alır.|
|[CComboBox:: GetMinVisible](#getminvisible)|Geçerli Birleşik giriş kutusunun aşağı açılan listesindeki en az görünür öğe sayısını alır.|
|[CComboBox:: GetTopIndex](#gettopindex)|Birleşik giriş kutusunun liste kutusu bölümünde görünen ilk öğenin dizinini döndürür.|
|[CComboBox:: ınitstorage](#initstorage)|Birleşik giriş kutusunun liste kutusu bölümünde öğeler ve dizeler için bellek bloklarını önceden ayırır.|
|[CComboBox:: InsertString](#insertstring)|Birleşik giriş kutusunun liste kutusuna bir dize ekler.|
|[CComboBox:: LimitText](#limittext)|Kullanıcının bir açılan kutunun düzenleme denetimine girebileceği metnin uzunluğunu sınırlandırır.|
|[CComboBox:: MeasureItem](#measureitem)|Sahip tarafından çizilmiş bir Birleşik giriş kutusu oluşturulduğunda Birleşik giriş kutusu boyutlarını belirleme çerçevesi tarafından çağırılır.|
|[CComboBox::P aste](#paste)|Panodaki verileri, geçerli imleç konumundaki düzenleme denetimine ekler. Veriler yalnızca Pano CF_TEXT biçiminde veri içeriyorsa eklenir.|
|[CComboBox:: ResetContent](#resetcontent)|Tüm öğeleri liste kutusundan kaldırır ve Birleşik giriş kutusunun denetimini düzenleyebilir.|
|[CComboBox:: SelectString](#selectstring)|Birleşik giriş kutusunun liste kutusunda bir dize arar ve dize bulunursa, liste kutusunda dizeyi seçer ve dizeyi düzenleme denetimine kopyalar.|
|[CComboBox:: Setcuebaşlık](#setcuebanner)|Birleşik giriş kutusu denetimi için görüntülenen işaret metnini ayarlar.|
|[CComboBox:: SetCurSel](#setcursel)|Birleşik giriş kutusunun liste kutusunda bir dize seçer.|
|[CComboBox:: SetDroppedWidth](#setdroppedwidth)|Birleşik giriş kutusunun aşağı açılan liste kutusu bölümü için izin verilen en düşük genişliği ayarlar.|
|[CComboBox:: SetEditSel](#seteditsel)|Birleşik giriş kutusunun düzenleme denetimindeki karakterleri seçer.|
|[CComboBox:: Setckesintileri ı](#setextendedui)|CBS_DROPDOWN veya CBS_DROPDOWNLIST stiline sahip bir Birleşik giriş kutusu için varsayılan kullanıcı arabirimini ya da Genişletilmiş Kullanıcı arabirimini seçer.|
|[CComboBox:: SetHorizontalExtent](#sethorizontalextent)|Birleşik giriş kutusunun liste kutusu bölümünün yatay olarak kaydırılabileceği piksel cinsinden genişliği belirler.|
|[CComboBox:: SetItemData](#setitemdata)|Birleşik giriş kutusundaki belirtilen öğeyle ilişkili 32 bitlik değeri ayarlar.|
|[CComboBox:: SetItemDataPtr](#setitemdataptr)|Birleşik giriş kutusunda belirtilen öğeyle ilişkili 32 bitlik işaretçiyi ayarlar.|
|[CComboBox:: SetItemHeight](#setitemheight)|Birleşik giriş kutusundaki liste öğelerinin yüksekliğini veya Birleşik giriş kutusunun düzenleme denetimi (veya statik metin) bölümünün yüksekliğini ayarlar.|
|[CComboBox:: SetLocale](#setlocale)|Birleşik giriş kutusu için yerel ayar tanıtıcısını ayarlar.|
|[CComboBox:: Setminvisibleıtems](#setminvisibleitems)|Geçerli Birleşik giriş kutusunun aşağı açılan listesindeki en az görünür öğe sayısını ayarlar.|
|[CComboBox:: Settopındex](#settopindex)|Birleşik giriş kutusunun liste kutusu kısmına, en üstte belirtilen dizini içeren öğeyi göstermesini söyler.|
|[CComboBox:: ShowDropDown](#showdropdown)|CBS_DROPDOWN veya CBS_DROPDOWNLIST stiline sahip bir Birleşik giriş kutusunun liste kutusunu gösterir veya gizler.|

## <a name="remarks"></a>Açıklamalar

Birleşik giriş kutusu, statik denetim veya düzenleme denetimiyle birleştirilmiş bir liste kutusundan oluşur. Denetimin liste kutusu bölümü her zaman görüntülenebilir veya yalnızca Kullanıcı denetimin yanındaki aşağı açılan oku seçtiğinde açılır.

Liste kutusunda şu anda seçili olan öğe (varsa) statik veya düzenleme denetiminde görüntülenir. Ayrıca, Birleşik giriş kutusunda aşağı açılan liste stili varsa, Kullanıcı listedeki öğelerden birinin ilk karakterini yazabilir ve görünür durumdaysa liste kutusu bu başlangıç karakteriyle bir sonraki öğeyi vurgulayacaktır.

Aşağıdaki tabloda üç Birleşik giriş kutusu [stili](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)karşılaştırılmaktadır.

|Stil|Ne zaman liste kutusu görünür|Statik veya düzenleme denetimi|
|-----------|-------------------------------|-----------------------------|
|Basit|Her zaman|Düzenle|
|Açılır liste|Ne zaman bırakıldığında|Düzenle|
|Açılan liste|Ne zaman bırakıldığında|Statik|

`CComboBox`Bir iletişim kutusu şablonundan ya da doğrudan kodunuzda bir nesne oluşturabilirsiniz. Her iki durumda da, önce nesneyi oluşturmak `CComboBox` için oluşturucuyu çağırın `CComboBox` ; ardından denetimi oluşturmak ve nesneye iliştirmek Için üye [Oluştur](#create) işlevini çağırın `CComboBox` .

Bir Birleşik giriş kutusu tarafından üst öğeye (genellikle öğesinden türetilmiş bir sınıf) gönderilen Windows bildirim iletilerini işlemek istiyorsanız `CDialog` , her ileti için üst sınıfa bir ileti eşleme girişi ve ileti işleyici üye işlevi ekleyin.

Her ileti eşleme girişi aşağıdaki biçimi alır:

`ON_Notification( id, memberFxn )`

Burada `id` bildirimi gönderen Birleşik giriş kutusu denetiminin alt pencere kimliğini belirtir ve `memberFxn` bildirimi işlemek için yazdığınız ana üye işlevinin adıdır.

Üst öğenin işlev prototipi aşağıdaki gibidir:

`afx_msg void memberFxn( );`

Belirli bildirimlerin gönderileceği sıra tahmin edilemez. Özellikle, bir CBN_CLOSEUP bildiriminden önce veya sonra bir CBN_SELCHANGE bildirimi olabilir.

Olası ileti eşleme girdileri şunlardır:

- ON_CBN_CLOSEUP (Windows 3,1 ve üzeri.) Birleşik giriş kutusunun liste kutusu kapatıldı. Bu bildirim iletisi, [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahip bir açılan kutu için gönderilmez.

- Kullanıcı ON_CBN_DBLCLK Birleşik giriş kutusunun liste kutusunda bir dizeye çift tıklar. Bu bildirim iletisi yalnızca CBS_SIMPLE stili olan bir Birleşik giriş kutusu için gönderilir. [Cbs_dropdown](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahip bir Birleşik giriş kutusu için, tek bir tıklama liste kutusunu gizleyen bir çift tıklama gerçekleşemez.

- Birleşik giriş kutusunun liste kutusu ON_CBN_DROPDOWN açılır (görünür hale getirilir). Bu bildirim iletisi yalnızca CBS_DROPDOWN veya CBS_DROPDOWNLIST stili olan bir Birleşik giriş kutusu için oluşabilir.

- ON_CBN_EDITCHANGE kullanıcı, Birleşik giriş kutusunun düzenleme denetimi bölümünde metni değiştirmiş olabilecek bir eylem gerçekleştirmiştir. CBN_EDITUPDATE iletisinin aksine, Windows ekranı güncelleştirdikten sonra bu ileti gönderilir. Birleşik giriş kutusunda CBS_DROPDOWNLIST stili varsa gönderilmez.

- Birleşik giriş kutusunun düzenleme denetimi bölümü ON_CBN_EDITUPDATE değiştirilen metni göstermek için kullanılır. Bu bildirim iletisi, denetim metni biçimlendirdikten sonra ancak metni görüntülemeden önce gönderilir. Birleşik giriş kutusunda CBS_DROPDOWNLIST stili varsa gönderilmez.

- ON_CBN_ERRSPACE Birleşik giriş kutusu belirli bir isteği karşılamak için yeterli bellek ayıramıyor.

- ON_CBN_SELENDCANCEL (Windows 3,1 ve üzeri.) Kullanıcının seçiminin iptal edilmesi gerektiğini gösterir. Kullanıcı bir öğeyi tıklatır ve sonra bir açılan kutunun liste kutusunu gizlemek için başka bir pencere veya denetimi tıklatır. Bu bildirim iletisi, Kullanıcı seçiminin yoksayılması gerektiğini göstermek için CBN_CLOSEUP bildirim iletisinden önce gönderilir. CBN_SELENDCANCEL veya CBN_SELENDOK bildirim iletisi, CBN_CLOSEUP bildirim iletisi gönderilmese bile gönderilir (CBS_SIMPLE stili ile Birleşik giriş kutusu durumunda olduğu gibi).

- Kullanıcı bir öğe seçer ve ardından ENTER tuşuna basar veya açılan kutunun liste kutusunu gizlemek için aşağı ok tuşuna tıklar. ON_CBN_SELENDOK Bu bildirim iletisi, Kullanıcı seçiminin geçerli kabul edilmesi gerektiğini belirtmek için CBN_CLOSEUP iletiden önce gönderilir. CBN_SELENDCANCEL veya CBN_SELENDOK bildirim iletisi, CBN_CLOSEUP bildirim iletisi gönderilmese bile gönderilir (CBS_SIMPLE stili ile Birleşik giriş kutusu durumunda olduğu gibi).

- Birleşik giriş kutusu ON_CBN_KILLFOCUS giriş odağını kaybetmekte.

- Bir Birleşik giriş kutusunun liste kutusunda seçimi ON_CBN_SELCHANGE, kullanıcının liste kutusuna tıklanması ya da ok tuşlarını kullanarak seçimi değiştirmesi gibi bir sonuç olarak değiştirilmekte. Bu ileti işlenirken, Birleşik giriş kutusunun düzenleme denetimindeki metin yalnızca `GetLBText` veya başka bir benzer işlev aracılığıyla alınabilir. `GetWindowText` kullanılamaz.

- Birleşik giriş kutusu ON_CBN_SETFOCUS giriş odağını alır.

İletişim `CComboBox` kutusu içinde (bir iletişim kaynağı aracılığıyla) bir nesne oluşturursanız, `CComboBox` Kullanıcı iletişim kutusunu kapattığında nesne otomatik olarak yok edilir.

Bir `CComboBox` nesneyi başka bir pencere nesnesi içine eklerseniz, yok etmeniz gerekmez. `CComboBox`Nesneyi yığında oluşturursanız, otomatik olarak yok edilir. `CComboBox`Nesnesini, işlevini kullanarak yığında oluşturursanız **`new`** , **`delete`** Windows Birleşik giriş kutusu yok edildiğinde nesneyi yok etmek için nesnesini çağırmanız gerekir.

**Göz önünde** WM_KEYDOWN ve WM_CHAR iletilerini işlemek istiyorsanız, Birleşik giriş kutusunun düzenleme ve liste kutusu denetimlerini alt sınıflara ayırmak, sınıfları `CEdit` ve ile türetmek `CListBox` ve türetilmiş sınıflara bu iletiler için işleyiciler eklemeniz gerekir. Daha fazla bilgi için bkz. [CWnd:: SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="ccomboboxaddstring"></a><a name="addstring"></a> CComboBox:: AddString

Birleşik giriş kutusunun liste kutusuna bir dize ekler.

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*lpszString*<br/>
Eklenecek null ile sonlandırılmış dizeyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri 0 ' dan büyük veya buna eşitse, liste kutusunda dizenin sıfır tabanlı dizinidir. Bir hata oluşursa, dönüş değeri CB_ERR; Yeni dizeyi depolamak için yeterli kullanılabilir alan yoksa, dönüş değeri CB_ERRSPACE.

### <a name="remarks"></a>Açıklamalar

Liste kutusu [cbs_sort](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stille oluşturulmadıysa, dize listenin sonuna eklenir. Aksi takdirde, dize listeye eklenir ve liste sıralanır.

> [!NOTE]
> Bu işlev Windows denetimi tarafından desteklenmiyor `ComboBoxEx` . Bu denetim hakkında daha fazla bilgi için Windows SDK [ComboBoxEx denetimleri](/windows/win32/Controls/comboboxex-controls) bölümüne bakın.

Liste içinde belirli bir konuma bir dize eklemek için [InsertString](#insertstring) üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

## <a name="ccomboboxccombobox"></a><a name="ccombobox"></a> CComboBox:: CComboBox

Bir `CComboBox` nesnesi oluşturur.

```
CComboBox();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

## <a name="ccomboboxclear"></a><a name="clear"></a> CComboBox:: Clear

Birleşik giriş kutusunun düzenleme denetimindeki geçerli seçimi siler (temizler).

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Geçerli seçimi silmek ve silinen içerikleri Pano 'ya yerleştirmek için [Kes](#cut) üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

## <a name="ccomboboxcompareitem"></a><a name="compareitem"></a> CComboBox:: CompareItem

Sıralanmış bir sahip çiz Birleşik giriş kutusunun liste kutusu bölümünde yeni bir öğenin göreli konumunu öğrenmek için Framework tarafından çağırılır.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpCompareItemStruct*<br/>
Bir [COMPAREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-compareitemstruct) yapısına yönelik uzun bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yapıda açıklanan iki öğenin göreli konumunu gösterir `COMPAREITEMSTRUCT` . Aşağıdaki değerlerden herhangi biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|-1|Öğe 1 öğe 2 ' den önce sıralar.|
|0|Öğe 1 ve öğe 2 aynı şekilde sıralayın.|
|1|Öğe 1 öğe 2 ' den sonra sıralar.|

Açıklaması için bkz. [CWnd:: OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) `COMPAREITEMSTRUCT` .

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. LBS_SORT stiliyle bir sahip çizimi Birleşik kutusu oluşturursanız, çerçeveye, liste kutusuna eklenen yeni öğeleri sıralama konusunda yardımcı olması için bu üye işlevini geçersiz kılmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

## <a name="ccomboboxcopy"></a><a name="copy"></a> CComboBox:: Copy

Geçerli seçimi, varsa Birleşik giriş kutusunun düzenleme denetimindeki CF_TEXT biçiminde Pano üzerine kopyalar.

```cpp
void Copy();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

## <a name="ccomboboxcreate"></a><a name="create"></a> CComboBox:: Create

Birleşik giriş kutusunu oluşturur ve `CComboBox` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Birleşik giriş kutusunun stilini belirtir. Kutuya [Birleşik giriş kutusu stillerinin](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) herhangi bir birleşimini uygulayın.

*Rect*<br/>
Birleşik giriş kutusunun konumunu ve boyutunu gösterir. Bir [Rect yapısı](/windows/win32/api/windef/ns-windef-rect) veya bir nesnesi olabilir `CRect` .

*pParentWnd*<br/>
Birleşik giriş kutusunun üst penceresini (genellikle a) belirtir `CDialog` . NULL olmaması gerekir.

*NID*<br/>
Birleşik giriş kutusunun Denetim KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CComboBox`İki adımda bir nesne oluşturursunuz. İlk olarak, oluşturucuyu çağırın ve sonra `Create` Windows Birleşik giriş kutusunu oluşturan ve bunu nesnesine ekleyen çağırın `CComboBox` .

`Create`Yürütüldüğünde Windows, açılan kutuya [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) iletileri gönderir.

Bu iletiler, temel sınıftaki [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) member işlevleri tarafından varsayılan olarak işlenir `CWnd` . Varsayılan ileti işlemeyi genişletmek için, öğesinden bir sınıf türetebilir `CComboBox` , yeni sınıfa bir ileti haritası ekleyin ve önceki ileti işleyici üye işlevlerini geçersiz kılın. `OnCreate`Yeni bir sınıf için gerekli başlatmayı gerçekleştirmek üzere, örneğin, öğesini geçersiz kılın.

Birleşik giriş kutusu denetimine aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) uygulayın. :

- WS_CHILD her zaman

- Genellikle WS_VISIBLE

- WS_DISABLED nadiren

- Birleşik giriş kutusundaki liste kutusu için dikey kaydırma eklemek WS_VSCROLL

- Birleşik giriş kutusundaki liste kutusu için yatay kaydırma eklemek WS_HSCROLL

- Denetimleri gruplamak Için WS_GROUP

- Birleşik giriş kutusunu sekme sırasına dahil etmek Için WS_TABSTOP

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

## <a name="ccomboboxcut"></a><a name="cut"></a> CComboBox:: kes

, Varsa, açılan kutu düzenleme denetimindeki geçerli seçimi siler (keser) ve silinen metni pano üzerine CF_TEXT biçiminde kopyalar.

```cpp
void Cut();
```

### <a name="remarks"></a>Açıklamalar

Silinen metni pano 'ya yerleştirmeksizin geçerli seçimi silmek için, [clear](#clear) member işlevini çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

## <a name="ccomboboxdeleteitem"></a><a name="deleteitem"></a> CComboBox::D Eleteıtem

Kullanıcı, sahip Çizim nesnesinden bir öğe sildiğinde `CComboBox` veya Birleşik giriş kutusunu yok eder, Framework tarafından çağırılır.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Parametreler

*Lpdeleteıtemstruct*<br/>
Silinen öğe hakkında bilgi içeren bir Windows [DELETEITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) yapısına yönelik uzun bir işaretçi. Bu yapının bir açıklaması için bkz. [CWnd:: OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) .

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması hiçbir şey yapmaz. Birleşik giriş kutusunu gerektiği gibi yeniden çizmek için bu işlevi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

## <a name="ccomboboxdeletestring"></a><a name="deletestring"></a> CComboBox::D eleteString

Birleşik giriş kutusundan *nIndex* konumundaki öğeyi siler.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Silinecek dizenin dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri 0 ' dan büyük veya buna eşitse, bu, listede kalan dizelerin sayısıdır. *NIndex* , listedeki öğe sayısından daha büyük bir dizin belirtiyorsa, dönüş değeri cb_err.

### <a name="remarks"></a>Açıklamalar

*NIndex* ' i izleyen tüm öğeler şimdi bir konum aşağı taşınır. Örneğin, bir Birleşik giriş kutusu iki öğe içeriyorsa, ilk öğeyi silmek kalan öğenin artık ilk konumda olmasına neden olur. ilk konumdaki öğe için *nindex*= 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

## <a name="ccomboboxdir"></a><a name="dir"></a> CComboBox::D IR

Birleşik giriş kutusunun liste kutusuna dosya adlarının veya sürücülerin bir listesini ekler.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Parametreler

*özniteliği*<br/>
**`enum`** [CFile:: GetStatus](../../mfc/reference/cfile-class.md#getstatus) bölümünde açıklanan değerlerin herhangi bir birleşimi veya aşağıdaki değerlerin herhangi bir birleşimi olabilir:

- DDL_READWRITE dosya, öğesinden okunabilir veya yazılabilir.

- DDL_READONLY dosya okunabilir, ancak üzerine yazılamaz.

- DDL_HIDDEN Dosya gizlidir ve bir dizin listesinde görünmez.

- DDL_SYSTEM dosyası bir sistem dosyasıdır.

- *LpszWildCard* tarafından belirtilen ad DDL_DIRECTORY bir dizini belirtir.

- DDL_ARCHIVE dosya arşivlendi.

- DDL_DRIVES, *lpszWildCard*tarafından belirtilen adla eşleşen tüm sürücüleri içerir.

- DDL_EXCLUSIVE dışlamalı bayrak. Dışlamalı bayrak ayarlandıysa, yalnızca belirtilen türdeki dosyalar listelenir. Aksi halde, belirtilen türdeki dosyalar "normal" dosyalara ek olarak listelenir.

*lpszWildCard*<br/>
Dosya belirtimi dizesini işaret eder. Dize joker karakterler içerebilir (örneğin, *. \* ).

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri 0 ' dan büyük veya buna eşitse, bu, listeye eklenen son dosya adının sıfır tabanlı dizinidir. Bir hata oluşursa, dönüş değeri CB_ERR; Yeni dizeleri depolamak için yeterli alan yoksa, dönüş değeri CB_ERRSPACE.

### <a name="remarks"></a>Açıklamalar

Bu işlev Windows denetimi tarafından desteklenmiyor `ComboBoxEx` . Bu denetim hakkında daha fazla bilgi için Windows SDK [ComboBoxEx denetimleri](/windows/win32/Controls/comboboxex-controls) bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

## <a name="ccomboboxdrawitem"></a><a name="drawitem"></a> CComboBox::D rawItem

Sahip-çiz Birleşik giriş kutusunun görsel bir yönü değiştiğinde Framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`itemAction` `DRAWITEMSTRUCT` Yapının üyesi gerçekleştirilecek çizim eylemini tanımlar. Bu yapının açıklaması için bkz. [CWnd:: OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) .

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bir sahip çizim nesnesi için çizimi uygulamak üzere bu üye işlevini geçersiz kılın `CComboBox` . Bu üye işlevi sonlandırılmadan önce, uygulamanın, *Lpdrawitemstruct*içinde sağlanan görüntüleme bağlamı için seçilen tüm grafik cihaz ARABIRIMI (GDI) nesnelerini geri yüklemesi gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

## <a name="ccomboboxfindstring"></a><a name="findstring"></a> CComboBox:: FindString

Birleşik giriş kutusunun liste kutusunda belirtilen öneki içeren ilk dizeyi bulur, ancak seçmeyin.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>Parametreler

*nStartAfter*<br/>
Aranacak ilk öğeden önceki öğenin sıfır tabanlı dizinini içerir. Arama liste kutusunun en altına ulaştığında, liste kutusunun en üstünden *nStartAfter*tarafından belirtilen öğeye kadar devam eder. -1 ise, tüm liste kutusu başlangıçtan itibaren aranır.

*lpszString*<br/>
Arama yapılacak öneki içeren null ile sonlandırılmış dizeyi işaret eder. Arama büyük/küçük harfe bağımsızdır, bu nedenle bu dize büyük ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri 0 ' dan büyük veya buna eşitse, eşleşen öğenin sıfır tabanlı dizinidir. Arama başarısız olursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu işlev Windows denetimi tarafından desteklenmiyor `ComboBoxEx` . Bu denetim hakkında daha fazla bilgi için Windows SDK [ComboBoxEx denetimleri](/windows/win32/Controls/comboboxex-controls) bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

## <a name="ccomboboxfindstringexact"></a><a name="findstringexact"></a> CComboBox:: Findstringözdeş

`FindStringExact` *LpszFind*içinde belirtilen dizeyle eşleşen ilk liste kutusu dizesini (Birleşik giriş kutusunda) bulmak için üye işlevini çağırın.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Parametreler

*nIndexStart*<br/>
Aranacak ilk öğeden önce öğenin sıfır tabanlı dizinini belirtir. Arama liste kutusunun en altına ulaştığında, liste kutusunun en üstünden *nIndexStart*tarafından belirtilen öğeye geri devam eder. *NIndexStart* -1 ise, tüm liste kutusu başlangıçtan itibaren aranır.

*lpszFind*<br/>
Aranacak null ile sonlandırılmış dizeyi gösterir. Bu dize, uzantısı dahil olmak üzere tam bir dosya adı içerebilir. Arama büyük/küçük harfe duyarlı değildir, bu nedenle bu dize büyük ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen öğenin sıfır tabanlı dizini veya arama başarısız olduysa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Birleşik giriş kutusu, bir sahip çizimi stiliyle oluşturulduysa ancak [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili olmadan oluşturulmuşsa, `FindStringExact` doubleword değerini *lpszFind*değerine göre eşleştirmeye çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

## <a name="ccomboboxgetcomboboxinfo"></a><a name="getcomboboxinfo"></a> CComboBox:: Getcomboboxınfo

Nesne için bilgileri alır `CComboBox` .

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>Parametreler

*pcbi*<br/>
[COMBOBOXINFO](/windows/win32/api/winuser/ns-winuser-comboboxinfo) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi [CB_GETCOMBOBOXINFO](/windows/win32/Controls/cb-getcomboboxinfo) iletisinin işlevselliğine öykünür.

## <a name="ccomboboxgetcount"></a><a name="getcount"></a> CComboBox:: GetCount

Birleşik giriş kutusunun liste kutusu bölümündeki öğelerin sayısını almak için bu üye işlevi çağırın.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısı. Döndürülen sayı, son öğenin dizin değerinden (Dizin sıfır tabanlı) büyük bir değer. Bir hata oluşursa CB_ERR.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

## <a name="ccomboboxgetcuebanner"></a><a name="getcuebanner"></a> CComboBox:: Getcuebaşlık

Birleşik giriş kutusu denetimi için görüntülenen ipucu metnini alır.

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>Parametreler

*lpszText*\
dışı İpucu başlık metnini alan bir arabelleğin işaretçisi.

*cchText*\
'ndaki *LpszText* parametresinin işaret ettiği arabelleğin boyutu.

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yüklemede, varsa Cue başlık metnini içeren bir [CString](../../atl-mfc-shared/using-cstring.md) nesnesi; Aksi takdirde, `CString` sıfır uzunluğuna sahip bir nesne.

-veya-

İkinci aşırı yüklemede, bu yöntem başarılı olursa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

İpucu metni, Birleşik giriş kutusu denetiminin giriş alanında görüntülenen bir istemdir. Kullanıcı giriş yapana kadar ipucu metni görüntülenir.

Bu yöntem, Windows SDK açıklanan [CB_GETCUEBANNER](/windows/win32/Controls/cb-getcuebanner) iletisini gönderir.

## <a name="ccomboboxgetcursel"></a><a name="getcursel"></a> CComboBox:: GetCurSel

Birleşik giriş kutusundaki hangi öğenin seçili olduğunu öğrenmek için bu üye işlevini çağırın.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusunun liste kutusunda şu anda seçili olan öğenin sıfır tabanlı dizini veya seçili öğe yoksa CB_ERR.

### <a name="remarks"></a>Açıklamalar

`GetCurSel` listeye bir dizin döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

## <a name="ccomboboxgetdroppedcontrolrect"></a><a name="getdroppedcontrolrect"></a> CComboBox:: GetDroppedControlRect

`GetDroppedControlRect`Açılan Birleşik giriş kutusunun görünür (açılan) liste kutusunun ekran koordinatlarını almak için üye işlevini çağırın.

```cpp
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
Koordinatları alacak olan [Rect yapısına](/windows/win32/api/windef/ns-windef-rect) işaret eder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

## <a name="ccomboboxgetdroppedstate"></a><a name="getdroppedstate"></a> CComboBox:: GetDroppedState

`GetDroppedState`Açılan Birleşik giriş kutusunun liste kutusunun görünür olup olmadığını (aşağı açılan) öğrenmek için üye işlevini çağırın.

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusu görünür durumdaysa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

## <a name="ccomboboxgetdroppedwidth"></a><a name="getdroppedwidth"></a> CComboBox:: GetDroppedWidth

Birleşik giriş kutusunun liste kutusunun piksel cinsinden izin verilen en düşük genişliği almak için bu işlevi çağırın.

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa piksel cinsinden izin verilen en düşük Genişlik; Aksi takdirde, CB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca [cbs_dropdown](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili olan Birleşik giriş kutuları için geçerlidir.

Varsayılan olarak, açılan liste kutusunun izin verilen en düşük genişliği 0 ' dır. İzin verilen en düşük Genişlik [SetDroppedWidth](#setdroppedwidth)çağırarak ayarlanabilir. Birleşik giriş kutusunun liste kutusu kısmı görüntülendiğinde, genişliği izin verilen en düşük genişlik veya Birleşik giriş kutusu genişliğinden daha büyük olur.

### <a name="example"></a>Örnek

  [SetDroppedWidth](#setdroppedwidth)örneğine bakın.

## <a name="ccomboboxgeteditsel"></a><a name="geteditsel"></a> CComboBox:: GetEditSel

Birleşik giriş kutusunun düzenleme denetimindeki geçerli seçimin başlangıç ve bitiş karakter konumlarını alır.

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düşük sıralı sözcükteki başlangıç konumunu içeren 32 bitlik bir değer ve yüksek sıralı sözcükteki seçimin sonundan sonra seçili olmayan ilk karakterin konumu. Bu işlev, düzenleme denetimi olmadan Birleşik giriş kutusunda kullanılırsa CB_ERR döndürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

## <a name="ccomboboxgetextendedui"></a><a name="getextendedui"></a> CComboBox:: Getckesintileri ı

`GetExtendedUI`Birleşik giriş kutusunun varsayılan kullanıcı arabirimine mi yoksa Genişletilmiş Kullanıcı arabirimine mi sahip olduğunu öğrenmek için üye işlevini çağırın.

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusunda Genişletilmiş Kullanıcı arabirimi varsa sıfır dışı. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş Kullanıcı arabirimi aşağıdaki yollarla tanımlanabilir:

- Statik denetime tıkladığınızda liste kutusu yalnızca [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili olan Birleşik giriş kutuları için görüntülenir.

- AŞAĞı ok tuşuna basıldığında liste kutusu görüntülenir (F4 devre dışıdır).

Öğe listesi görünür olmadığında statik denetimi kaydırma devre dışı bırakılır (ok tuşları devre dışı bırakılır).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

## <a name="ccomboboxgethorizontalextent"></a><a name="gethorizontalextent"></a> CComboBox:: GetHorizontalExtent

Birleşik giriş kutusundan, Birleşik giriş kutusunun liste kutusu bölümünün yatay olarak kaydırılabileceği piksel cinsinden genişliği alır.

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusunun liste kutusu bölümünün piksel cinsinden kaydırılabilir genişliği.

### <a name="remarks"></a>Açıklamalar

Bu, yalnızca Birleşik giriş kutusunun liste kutusu bölümünde bir yatay kaydırma çubuğu varsa geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

## <a name="ccomboboxgetitemdata"></a><a name="getitemdata"></a> CComboBox:: GetItemData

Belirtilen Birleşik giriş kutusu öğesiyle ilişkili uygulama tarafından sağlanan 32 bitlik değeri alır.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Birleşik giriş kutusunun liste kutusunda bir öğenin sıfır tabanlı dizinini içerir.

### <a name="return-value"></a>Dönüş Değeri

Öğe ile ilişkili 32 bitlik değer veya bir hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

32 bitlik değer bir [SetItemData](#setitemdata) üye Işlev çağrısının *dwitemdata* parametresiyle ayarlanabilir. `GetItemDataPtr`Alınacak 32 bitlik değer bir işaretçisiyse (), üye işlevini kullanın **`void`** <strong>\*</strong> .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

## <a name="ccomboboxgetitemdataptr"></a><a name="getitemdataptr"></a> CComboBox:: GetItemDataPtr

Belirtilen açılan kutu öğesiyle ilişkili uygulama tarafından sağlanan 32 bitlik değeri bir işaretçi () olarak alır **`void`** <strong>\*</strong> .

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Birleşik giriş kutusunun liste kutusunda bir öğenin sıfır tabanlı dizinini içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi alır veya bir hata oluşursa-1.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

## <a name="ccomboboxgetitemheight"></a><a name="getitemheight"></a> CComboBox:: GetItemHeight

`GetItemHeight`Birleşik giriş kutusundaki liste öğelerinin yüksekliğini almak için üye işlevini çağırın.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Yüksekliği alınacak olan Birleşik giriş kutusunun bileşenini belirtir. *NIndex* parametresi-1 ise, Birleşik giriş kutusunun düzenleme denetimi (veya statik metin) bölümünün yüksekliği alınır. Birleşik giriş kutusunda [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili varsa *nDizin* , yüksekliği alınacak olan liste öğesinin sıfır tabanlı dizinini belirtir. Aksi takdirde, *nIndex* 0 olarak ayarlanmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusundaki belirtilen öğenin piksel cinsinden yüksekliği. Bir hata oluşursa, dönüş değeri CB_ERR.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

## <a name="ccomboboxgetlbtext"></a><a name="getlbtext"></a> CComboBox:: GetLBText

Birleşik giriş kutusunun liste kutusundan bir dize alır.

```
int GetLBText(
    int nIndex,
    LPTSTR lpszText) const;

void GetLBText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Kopyalanacak liste kutusu dizesinin sıfır tabanlı dizinini içerir.

*lpszText*<br/>
Dizeyi alacak bir arabelleğe işaret eder. Arabellekte dize ve Sonlandırıcı null karakteri için yeterli alan olması gerekir.

*rString*<br/>
Bir başvurusu `CString` .

### <a name="return-value"></a>Dönüş Değeri

Dizenin sonlandırılıyor null karakteri hariç uzunluğu (bayt cinsinden). *NIndex* geçerli bir dizin belirtmezse, dönüş değeri cb_err.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin ikinci formu, bir `CString` nesneyi öğenin metniyle doldurur. \
*NIndex* geçersiz ise, bu işlev bir `E_INVALIDARG` özel durum oluşturur (hata kodu: `-2147024809` , `0x80070057` ).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

## <a name="ccomboboxgetlbtextlen"></a><a name="getlbtextlen"></a> CComboBox:: GetLBTextLen

Birleşik giriş kutusunun liste kutusunda bir dizenin uzunluğunu alır.

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusu dizesinin sıfır tabanlı dizinini içerir.

### <a name="return-value"></a>Dönüş Değeri

Dizenin, Sonlandırıcı null karakteri hariç bayt cinsinden uzunluğu. *NIndex* geçerli bir dizin belirtmezse, dönüş değeri cb_err.

### <a name="example"></a>Örnek

  [CComboBox:: GetLBText](#getlbtext)örneğine bakın.

## <a name="ccomboboxgetlocale"></a><a name="getlocale"></a> CComboBox:: GetLocale

Birleşik giriş kutusu tarafından kullanılan yerel ayarı alır.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusundaki dizeler için yerel ayar tanıtıcısı (LCıD) değeri.

### <a name="remarks"></a>Açıklamalar

Yerel ayar, örneğin, sıralanmış Birleşik giriş kutusunda dizelerin sıralama düzenini belirlemede kullanılır.

### <a name="example"></a>Örnek

  [CComboBox:: setlocale](#setlocale)örneğine bakın.

## <a name="ccomboboxgetminvisible"></a><a name="getminvisible"></a> CComboBox:: GetMinVisible

Geçerli Birleşik giriş kutusu denetiminin aşağı açılan listesindeki en az görünür öğe sayısını alır.

```
int GetMinVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli açılan listedeki en az görünür öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [CB_GETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) iletisini gönderir.

## <a name="ccomboboxgettopindex"></a><a name="gettopindex"></a> CComboBox:: GetTopIndex

Birleşik giriş kutusunun liste kutusu bölümünde görünen ilk öğenin sıfır tabanlı dizinini alır.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, tersi durumda CB_ERR Birleşik giriş kutusunun liste kutusu bölümündeki ilk görünür öğenin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Başlangıçta, öğe 0 liste kutusunun en üstünde, ancak liste kutusu kaydırıldığında, en üstte başka bir öğe olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

## <a name="ccomboboxinitstorage"></a><a name="initstorage"></a> CComboBox:: ınitstorage

Birleşik giriş kutusunun liste kutusu bölümünde liste kutusu öğelerini depolamak için bellek ayırır.

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

Başarılı olursa, Birleşik giriş kutusunun liste kutusu bölümünün bir bellek yeniden ayırma gerekmeden önce depolayabileceği en fazla öğe sayısı, aksi durumda CB_ERRSPACE, ancak yeterli bellek yok.

### <a name="remarks"></a>Açıklamalar

Öğesinin liste kutusu kısmına çok sayıda öğe eklemeden önce bu işlevi çağırın `CComboBox` .

Yalnızca Windows 95/98: *wParam* parametresi 16 bit değerlerle sınırlıdır. Bu, liste kutularının 32.767 taneden fazla öğe içeremeyeceği anlamına gelir. Öğe sayısı kısıtlanmış olsa da, bir liste kutusundaki öğelerin toplam boyutu yalnızca kullanılabilir bellekle sınırlıdır.

Bu işlev, çok sayıda öğe (100 ' den fazla) olan liste kutularının başlatılmasını hızlandırmaya yardımcı olur. Sonraki [AddString](#addstring), [InsertString](#insertstring)ve [dir](#dir) işlevlerinin olası en kısa süreyi alması için belirtilen bellek miktarını önceden ayırır. Parametreler için tahminleri kullanabilirsiniz. Fazla tahmin ediyorsanız, bazı ek bellek ayrılır; tahmin ediyorsanız, önceden ayrılan miktarı aşan öğeler için normal ayırma kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

## <a name="ccomboboxinsertstring"></a><a name="insertstring"></a> CComboBox:: InsertString

Birleşik giriş kutusunun liste kutusuna bir dize ekler.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusunda dizeyi alacak olan konumun sıfır tabanlı dizinini içerir. Bu parametre-1 ise, dize listenin sonuna eklenir.

*lpszString*<br/>
Eklenecek null ile sonlandırılmış dizeyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Dizenin eklendiği konumun sıfır tabanlı dizini. Bir hata oluşursa, dönüş değeri CB_ERR. Yeni dizeyi depolamak için yeterli kullanılabilir alan yoksa, dönüş değeri CB_ERRSPACE.

### <a name="remarks"></a>Açıklamalar

[AddString](#addstring) üye işlevinin aksine, `InsertString` üye işlevi [cbs_sort](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stilin sıralanmasına sahip bir listeye neden olmaz.

> [!NOTE]
> Bu işlev Windows denetimi tarafından desteklenmiyor `ComboBoxEx` . Bu denetim hakkında daha fazla bilgi için Windows SDK [ComboBoxEx denetimleri](/windows/win32/Controls/comboboxex-controls) bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

## <a name="ccomboboxlimittext"></a><a name="limittext"></a> CComboBox:: LimitText

Kullanıcının bir açılan kutunun düzenleme denetimine girebileceği metnin bayt cinsinden uzunluğunu sınırlandırır.

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>Parametreler

*nMaxChars*<br/>
Kullanıcının girebileceği metnin uzunluğunu (bayt olarak) belirtir. Bu parametre 0 ise, metin uzunluğu 65.535 bayt olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı. Stil [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya düzenleme denetimi olmayan Birleşik giriş kutusu için bir Birleşik giriş kutusu için çağrılırsa, dönüş değeri cb_err olur.

### <a name="remarks"></a>Açıklamalar

Birleşik giriş kutusunun Stil [cbs_autohscroll](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)yoksa, metin sınırının düzenleme denetimi boyutundan daha büyük olarak ayarlanması hiçbir etkiye sahip olmayacaktır.

`LimitText` yalnızca kullanıcının girebileceği metni sınırlandırır. İleti gönderildiğinde düzenleme denetimindeki herhangi bir metin üzerinde hiçbir etkisi yoktur veya liste kutusunda bir dize seçildiğinde düzenleme denetimine kopyalanmış metnin uzunluğunu etkilemez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

## <a name="ccomboboxmeasureitem"></a><a name="measureitem"></a> CComboBox:: MeasureItem

Sahip çizim stili olan bir Birleşik giriş kutusu oluşturulduğunda Framework tarafından çağırılır.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) yapısına yönelik uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bu üye işlevini geçersiz kılın ve `MEASUREITEMSTRUCT` Birleşik giriş kutusundaki liste kutusunun boyutlarını bilgilendirmek için yapıyı girin. Birleşik giriş kutusu [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiliyle oluşturulduysa, çerçeve liste kutusundaki her öğe için bu üye işlevini çağırır. Aksi takdirde, bu üye yalnızca bir kez çağrılır.

[SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) üye işleviyle oluşturulan, sahip çizimi açılan kutusunda CBS_OWNERDRAWFIXED stilini kullanmak, `CWnd` daha fazla programlama ile ilgili hususlar içerir. [Teknik not14](../../mfc/tn014-custom-controls.md)' te tartışmaya bakın.

Yapının açıklaması için bkz. [CWnd:: OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

## <a name="ccomboboxpaste"></a><a name="paste"></a> CComboBox::P aste

Panodaki verileri, geçerli imleç konumundaki Birleşik giriş kutusunun düzenleme denetimine ekler.

```cpp
void Paste();
```

### <a name="remarks"></a>Açıklamalar

Veriler yalnızca Pano CF_TEXT biçiminde veri içeriyorsa eklenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

## <a name="ccomboboxresetcontent"></a><a name="resetcontent"></a> CComboBox:: ResetContent

Tüm öğeleri liste kutusundan kaldırır ve Birleşik giriş kutusunun denetimini düzenleyebilir.

```cpp
void ResetContent();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

## <a name="ccomboboxselectstring"></a><a name="selectstring"></a> CComboBox:: SelectString

Birleşik giriş kutusunun liste kutusunda bir dize arar ve dize bulunursa liste kutusunda dizeyi seçer ve onu düzenleme denetimine kopyalar.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*nStartAfter*<br/>
Aranacak ilk öğeden önceki öğenin sıfır tabanlı dizinini içerir. Arama liste kutusunun en altına ulaştığında, liste kutusunun en üstünden *nStartAfter*tarafından belirtilen öğeye kadar devam eder. -1 ise, tüm liste kutusu başlangıçtan itibaren aranır.

*lpszString*<br/>
Arama yapılacak öneki içeren null ile sonlandırılmış dizeyi işaret eder. Arama büyük/küçük harfe bağımsızdır, bu nedenle bu dize büyük ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Dize bulunursa seçili öğenin sıfır tabanlı dizini. Arama başarısız olduysa, dönüş değeri CB_ERR ve geçerli seçim değiştirilmez.

### <a name="remarks"></a>Açıklamalar

Dize, yalnızca başlangıçtaki karakterleri (başlangıç noktasından) önek dizesindeki karakterlerle eşleşiyorsa seçilir.

`SelectString`Ve `FindString` üyesi işlevlerinin her ikisinin de bir dize buldığına, ancak `SelectString` member işlevinin de dizeyi seçtiği unutulmamalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

## <a name="ccomboboxsetcuebanner"></a><a name="setcuebanner"></a> CComboBox:: Setcuebaşlık

Birleşik giriş kutusu denetimi için görüntülenen işaret metnini ayarlar.

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszText*\
'ndaki İpucu metnini içeren, null ile sonlandırılmış bir arabelleğin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

İpucu metni, Birleşik giriş kutusu denetiminin giriş alanında görüntülenen bir istemdir. Kullanıcı giriş yapana kadar ipucu metni görüntülenir.

Bu yöntem, Windows SDK açıklanan [CB_SETCUEBANNER](/windows/win32/Controls/cb-setcuebanner) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, Birleşik giriş kutusu denetimine programlı bir şekilde erişmek için kullanılan *m_combobox*değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, Birleşik giriş kutusu denetimi için işaret başlığını ayarlar.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsetcursel"></a><a name="setcursel"></a> CComboBox:: SetCurSel

Birleşik giriş kutusunun liste kutusunda bir dize seçer.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Parametreler

*Nyükseltmeye*<br/>
Seçilecek dizenin sıfır tabanlı dizinini belirtir. -1 ise, liste kutusundaki geçerli seçim kaldırılır ve düzenleme denetimi temizlenir.

### <a name="return-value"></a>Dönüş Değeri

İleti başarılı olursa seçili öğenin sıfır tabanlı dizini. *NSelect* , listedeki öğe sayısından büyükse veya *nSelect* -1 olarak ayarlandıysa seçimi temizleyen, dönüş değeri cb_err.

### <a name="remarks"></a>Açıklamalar

Gerekirse, liste kutusu dizeyi görünüme (liste kutusu görünür durumdaysa) kaydırır. Birleşik giriş kutusunun düzenleme denetimindeki metin, yeni seçimi yansıtacak şekilde değiştirilir. Liste kutusunda herhangi bir önceki seçim kaldırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

## <a name="ccomboboxsetdroppedwidth"></a><a name="setdroppedwidth"></a> CComboBox:: SetDroppedWidth

Birleşik giriş kutusunun liste kutusunun piksel cinsinden izin verilen en düşük genişliği ayarlamak için bu işlevi çağırın.

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
Birleşik giriş kutusunun liste kutusu bölümünün piksel cinsinden izin verilen en küçük genişliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, liste kutusunun yeni genişliği, aksi durumda CB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca [cbs_dropdown](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili olan Birleşik giriş kutuları için geçerlidir.

Varsayılan olarak, açılan liste kutusunun izin verilen en düşük genişliği 0 ' dır. Birleşik giriş kutusunun liste kutusu kısmı görüntülendiğinde, genişliği izin verilen en düşük genişlik veya Birleşik giriş kutusu genişliğinden daha büyük olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

## <a name="ccomboboxseteditsel"></a><a name="seteditsel"></a> CComboBox:: SetEditSel

Birleşik giriş kutusunun düzenleme denetimindeki karakterleri seçer.

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>Parametreler

*nStartChar*<br/>
Başlangıç konumunu belirtir. Başlangıç konumu-1 olarak ayarlandıysa, varolan herhangi bir seçim kaldırılır.

*nEndChar*<br/>
Bitiş konumunu belirtir. Bitiş konumu-1 olarak ayarlandıysa, başlangıç konumundan, düzenleme denetimindeki son karaktere kadar olan tüm metinler seçilir.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi başarılı olursa sıfır dışı; Aksi takdirde 0. `CComboBox` [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili varsa veya bir liste kutusu yoksa cb_err.

### <a name="remarks"></a>Açıklamalar

Pozisyonlar sıfır tabanlıdır. Düzenleme denetiminin ilk karakterini seçmek için, 0 ' ın başlangıç konumunu belirtirsiniz. Bitiş konumu, son karakteri seçmek için gereken karakter içindir. Örneğin, düzenleme denetiminin ilk dört karakterini seçmek için, 0 ' ın başlangıç konumunu ve 4 ' ün bitiş konumunu kullanırsınız.

> [!NOTE]
> Bu işlev Windows denetimi tarafından desteklenmiyor `ComboBoxEx` . Bu denetim hakkında daha fazla bilgi için Windows SDK [ComboBoxEx denetimleri](/windows/win32/Controls/comboboxex-controls) bölümüne bakın.

### <a name="example"></a>Örnek

  [CComboBox:: GetEditSel](#geteditsel)örneğine bakın.

## <a name="ccomboboxsetextendedui"></a><a name="setextendedui"></a> CComboBox:: Setckesintileri ı

`SetExtendedUI`Varsayılan Kullanıcı arabirimini veya [cbs_dropdown](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) ya da [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahip bir Birleşik giriş kutusu için Genişletilmiş Kullanıcı arabirimini seçmek için üye işlevini çağırın.

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>Parametreler

*bExtended*<br/>
Birleşik giriş kutusunun Genişletilmiş Kullanıcı arabirimini mi yoksa varsayılan kullanıcı arabirimini mi kullanması gerektiğini belirtir. DOĞRU değeri Genişletilmiş Kullanıcı arabirimini seçer; FALSE değeri standart Kullanıcı arabirimini seçer.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa veya bir hata oluşursa CB_ERR CB_OKAY.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş Kullanıcı arabirimi aşağıdaki yollarla tanımlanabilir:

- Statik denetime tıkladığınızda liste kutusu yalnızca CBS_DROPDOWNLIST stili olan Birleşik giriş kutuları için görüntülenir.

- AŞAĞı ok tuşuna basıldığında liste kutusu görüntülenir (F4 devre dışıdır).

Öğe listesi görünür olmadığında statik denetimi kaydırma devre dışı bırakılır (ok tuşları devre dışı bırakılır).

### <a name="example"></a>Örnek

  [CComboBox:: Getckesintileri ı](#getextendedui)örneğine bakın.

## <a name="ccomboboxsethorizontalextent"></a><a name="sethorizontalextent"></a> CComboBox:: SetHorizontalExtent

Birleşik giriş kutusunun liste kutusu bölümünün yatay olarak kaydırılabileceği piksel cinsinden genişliği belirler.

```cpp
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>Parametreler

*Nexkatlanmış*<br/>
Birleşik giriş kutusunun liste kutusu bölümünün yatay olarak kaydırılabileceği piksel sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Liste kutusunun genişliği bu değerden küçükse, yatay kaydırma çubuğu liste kutusunda öğeleri yatay olarak kaydıracaktır. Liste kutusunun genişliği bu değerden daha büyük veya bu değere eşitse, yatay kaydırma çubuğu gizlenir veya Birleşik giriş kutusunda [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili varsa, devre dışı bırakılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

## <a name="ccomboboxsetitemdata"></a><a name="setitemdata"></a> CComboBox:: SetItemData

Birleşik giriş kutusundaki belirtilen öğeyle ilişkili 32 bitlik değeri ayarlar.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Ayarlanacak öğeye sıfır tabanlı bir dizin içerir.

*dwItemData*<br/>
Öğeyle ilişkilendirilecek yeni değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

`SetItemDataPtr`32 bit öğe bir işaretçi ise üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

## <a name="ccomboboxsetitemdataptr"></a><a name="setitemdataptr"></a> CComboBox:: SetItemDataPtr

Birleşik giriş kutusundaki belirtilen öğeyle ilişkili 32 bitlik değeri belirtilen işaretçi () olarak ayarlar **`void`** <strong>\*</strong> .

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Öğenin sıfır tabanlı bir dizinini içerir.

*pData*<br/>
Öğeyle ilişkilendirilecek işaretçiyi içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu işaretçi Birleşik giriş kutusunun ömrü boyunca geçerli kalır, ancak öğe eklendiğinde veya kaldırıldığında öğenin Birleşik giriş kutusu içindeki göreli konumu değişebilir. Bu nedenle, öğenin kutu içindeki dizini değişebilir, ancak işaretçi güvenilir kalır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

## <a name="ccomboboxsetitemheight"></a><a name="setitemheight"></a> CComboBox:: SetItemHeight

Birleşik giriş kutusundaki `SetItemHeight` liste öğelerinin yüksekliğini veya Birleşik giriş kutusunun düzenleme denetimi (veya statik metin) bölümünün yüksekliğini ayarlamak için üye işlevini çağırın.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste öğelerinin yüksekliğinin veya Birleşik giriş kutusunun düzenleme denetimi (veya statik metin) bölümünün ayarlanmış olup olmadığını belirtir.

Birleşik giriş kutusunda [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili varsa *nDizin* , yüksekliği ayarlanacak liste öğesinin sıfır tabanlı dizinini belirtir; Aksi takdirde, *nIndex* 0 olmalıdır ve tüm liste öğelerinin yüksekliği ayarlanır.

*Nindex* -1 ise, Birleşik giriş kutusunun düzenleme denetimi veya statik metin bölümünün yüksekliği ayarlanır.

*Cyıtemheight*<br/>
*NIndex*tarafından tanımlanan Birleşik giriş kutusu bileşeninin yüksekliğini piksel cinsinden belirtir.

### <a name="return-value"></a>Dönüş Değeri

Dizin veya yükseklik geçersiz ise CB_ERR; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Birleşik giriş kutusunun düzenleme denetimi (veya statik metin) bölümünün yüksekliği, liste öğelerinin yüksekliğinden bağımsız olarak ayarlanır. Bir uygulama, düzenleme denetimi (veya statik metin) bölümünün yüksekliğinin belirli bir liste kutusu öğesinin yüksekliğinden küçük olmamasını sağlamalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

## <a name="ccomboboxsetlocale"></a><a name="setlocale"></a> CComboBox:: SetLocale

Bu Birleşik giriş kutusu için yerel ayar tanıtıcısını ayarlar.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Parametreler

*nNewLocale*<br/>
Birleşik giriş kutusu için ayarlanacak yeni yerel ayar tanıtıcısı (LCıD) değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu Birleşik giriş kutusunun önceki yerel ayar tanıtıcısı (LCıD) değeri.

### <a name="remarks"></a>Açıklamalar

`SetLocale`Çağrılmaması durumunda, varsayılan yerel ayar sistemden alınır. Bu sistem varsayılan yerel ayarı, Denetim Masası 'nın bölgesel (veya uluslararası) uygulaması kullanılarak değiştirilebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

## <a name="ccomboboxsetminvisibleitems"></a><a name="setminvisibleitems"></a> CComboBox:: Setminvisibleıtems

Geçerli Birleşik giriş kutusu denetiminin aşağı açılan listesindeki en az görünür öğe sayısını ayarlar.

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>Parametreler

*Görünmez*\
'ndaki Görünen en az öğe sayısını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [CB_SETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, Birleşik giriş kutusu denetimine programlı bir şekilde erişmek için kullanılan *m_combobox*değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, Birleşik giriş kutusu denetiminin açılan listesine 20 öğe ekler. Daha sonra, Kullanıcı açılır oka bastığında en az 10 öğe görüntülendiğini belirtir.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsettopindex"></a><a name="settopindex"></a> CComboBox:: Settopındex

Birleşik giriş kutusunun liste kutusu bölümünde belirli bir öğenin görünür olmasını sağlar.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusu öğesinin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır veya bir hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Sistem liste kutusunu, *nIndex* tarafından belirtilen öğe liste kutusunun en üstünde görünene veya en fazla kaydırma aralığına ulaşılana kadar kaydırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

## <a name="ccomboboxshowdropdown"></a><a name="showdropdown"></a> CComboBox:: ShowDropDown

[Cbs_dropdown](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahip bir Birleşik giriş kutusunun liste kutusunu gösterir veya gizler.

```cpp
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>Parametreler

*Bshowıt*<br/>
Açılan liste kutusunun gösterilip gösterilmeyeceğini veya gizlenmeyeceğini belirtir. TRUE değeri liste kutusunu gösterir. FALSE değeri liste kutusunu gizler.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu stilin Birleşik giriş kutusu liste kutusunu gösterir.

Bu üye işlevin [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiliyle oluşturulan Birleşik giriş kutusu üzerinde hiçbir etkisi yoktur.

### <a name="example"></a>Örnek

  [CComboBox:: GetDroppedState](#getdroppedstate)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CButton sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[Cedıt sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CListBox sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar sınıfı](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic sınıfı](../../mfc/reference/cstatic-class.md)<br/>
[CDialog sınıfı](../../mfc/reference/cdialog-class.md)
