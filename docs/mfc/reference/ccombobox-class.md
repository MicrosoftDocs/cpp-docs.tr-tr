---
title: CComboBox Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: dc803fb4ce137b256f4197afaec7bc3327e1e85a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754834"
---
# <a name="ccombobox-class"></a>CComboBox Sınıfı

Windows açılan kutusunun işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComboBox : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComboBox::CComboBox](#ccombobox)|Bir `CComboBox` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComboBox::AddString](#addstring)|Açılan kutunun liste kutusuna veya CBS_SORT stiline sahip liste kutuları için sıralanmış konuma listenin sonuna bir dize ekler.|
|[CComboBox::Temizleyin](#clear)|Düzen denetiminde varsa geçerli seçimi siler (temizler).|
|[CComboBox::Karşılaştırma Öğesi](#compareitem)|Sıralanmış bir sahip açılan kutusunda yeni bir liste öğesinin göreli konumunu belirlemek için çerçeve tarafından çağrılır.|
|[CComboBox::Kopyala](#copy)|Varsa geçerli seçimi Pano'ya CF_TEXT biçiminde kopyalar.|
|[CComboBox::Oluştur](#create)|Açılan kutuyu oluşturur ve `CComboBox` nesneye bağlar.|
|[CComboBox::Kes](#cut)|Varsa geçerli seçimi düzenle denetiminde siler (keser) ve silinen metni panoya CF_TEXT biçiminde kopyalar.|
|[CComboBox::DeleteItem](#deleteitem)|Bir liste öğesi sahibi tarafından çizilen açılan kutudan silindiğinde çerçeve tarafından çağrılır.|
|[CComboBox::DeleteString](#deletestring)|Açılan kutunun liste kutusundan bir dize yi siler.|
|[CComboBox::Dir](#dir)|Açılan kutunun liste kutusuna dosya adlarının listesini ekler.|
|[CComboBox::DrawItem](#drawitem)|Bir sahibi tarafından çizilmiş açılan kutunun görsel bir yönü değiştiğinde çerçeve tarafından çağrılır.|
|[CComboBox::FindString](#findstring)|Açılan kutunun liste kutusunda belirtilen önek içeren ilk dizeyi bulur.|
|[CComboBox::FindStringExact](#findstringexact)|Belirtilen dizeyle eşleşen ilk liste kutusu dizesini (açılan kutuda) bulur.|
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|`CComboBox` Nesne hakkında bilgi alır.|
|[CComboBox::GetCount](#getcount)|Açılan kutunun liste kutusundaki öğe sayısını alır.|
|[CComboBox::GetCueBanner](#getcuebanner)|Açılan kutu denetimi için görüntülenen işaret metnini alır.|
|[CComboBox::GetCurSel](#getcursel)|Bir açılan kutunun liste kutusunda, varsa, şu anda seçili öğenin dizinini alır.|
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Açılan açılan kutunun görünür (bırakılan) liste kutusunun ekran koordinatlarını alır.|
|[CComboBox::GetDroppedState](#getdroppedstate)|Açılan açılan açılan kutunun liste kutusunun görünür olup olmadığını (aşağı bırakıldığını) belirler.|
|[CComboBox::GetDroppedGenişliği](#getdroppedwidth)|Açılan kutunun açılır liste kutusu bölümü için izin verilen minimum genişliği alır.|
|[CComboBox::GetEditSel](#geteditsel)|Açılan kutunun edit denetiminde geçerli seçimin başlangıç ve bitiş karakter konumlarını alır.|
|[CComboBox::GetExtendedUI](#getextendedui)|Açılan kutunun varsayılan kullanıcı arabirimine mi yoksa genişletilmiş kullanıcı arabirimine mi sahip olduğunu belirler.|
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Açılan kutunun liste kutusu bölümünün yatay olarak kaydırılabildiği piksellerde genişliği döndürür.|
|[CComboBox::GetItemData](#getitemdata)|Belirtilen açılan kutu öğesi ile ilişkili uygulama tarafından sağlanan 32 bit değeri alır.|
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Belirtilen açılan kutu öğesi ile ilişkili uygulama tarafından sağlanan 32 bit işaretçiyi alır.|
|[CComboBox::GetItemHeight](#getitemheight)|Liste öğelerinin yüksekliğini açılan kutuda alır.|
|[CComboBox::GetLBText](#getlbtext)|Açılan kutunun liste kutusundan bir dize alır.|
|[CComboBox::GetLBTextLen](#getlbtextlen)|Açılan kutunun liste kutusunda bir dize uzunluğunu alır.|
|[CComboBox::GetLocale](#getlocale)|Açılan kutu için yerel tanımlayıcıyı alır.|
|[CComboBox::GetMinVisible](#getminvisible)|Geçerli açılan kutunun açılır listesindeki en az görünür öğe sayısını alır.|
|[CComboBox::GetTopIndex](#gettopindex)|Açılan kutunun liste kutusu bölümündeki ilk görünür öğenin dizinini döndürür.|
|[CComboBox::InitStorage](#initstorage)|Açılan kutunun liste kutusu bölümündeki öğeler ve dizeleri için bellek bloklarını önceden ayırır.|
|[CComboBox::InsertString](#insertstring)|Açılan kutunun liste kutusuna bir dize ekler.|
|[CComboBox::LimitText](#limittext)|Kullanıcının bir açılan kutunun denetim denetimine girebileceği metnin uzunluğunu sınırlar.|
|[CComboBox::MeasureItem](#measureitem)|Bir sahibi tarafından çizilmiş açılan kutu oluşturulduğunda açılan kutu boyutlarını belirlemek için çerçeve tarafından çağrılır.|
|[CComboBox::Paste](#paste)|Panodaki verileri geçerli imleç konumundaki edit denetimine ekler. Veriler yalnızca Pano CF_TEXT biçiminde veri içeriyorsa eklenir.|
|[CComboBox::ResetContent](#resetcontent)|Liste kutusundaki tüm öğeleri kaldırır ve açılan kutunun denetimini denetler.|
|[CComboBox::SelectString](#selectstring)|Açılan kutunun liste kutusunda bir dize arar ve dize bulunursa, liste kutusundaki dizeyi seçer ve dizeyi denetim denetimine kopyalar.|
|[CComboBox::SetCueBanner](#setcuebanner)|Açılan kutu denetimi için görüntülenen işaret metnini ayarlar.|
|[CComboBox::SetCurSel](#setcursel)|Açılan kutunun liste kutusunda bir dize seçer.|
|[CComboBox::SetDroppedGenişliği](#setdroppedwidth)|Açılan kutunun açılır liste kutusu bölümü için izin verilen minimum genişliği ayarlar.|
|[CComboBox::SetEditSel](#seteditsel)|Açılan kutunun denetiminde karakterleri seçer.|
|[CComboBox::SetExtendedUI](#setextendedui)|CBS_DROPDOWN veya CBS_DROPDOWNLIST stiline sahip bir açılan kutu için varsayılan kullanıcı arabirimini veya genişletilmiş kullanıcı arabirimini seçer.|
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Açılan kutunun liste kutusu bölümünün yatay olarak kaydırılabildiği piksellerde genişliği ayarlar.|
|[CComboBox::SetItemData](#setitemdata)|Açılan kutuda belirtilen öğeyle ilişkili 32 bit lik değeri ayarlar.|
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Açılan kutuda belirtilen öğeyle ilişkili 32 bit işaretçiyi ayarlar.|
|[CComboBox::SetItemHeight](#setitemheight)|Liste öğelerinin yüksekliğini bir açılan kutuda veya bir açılan kutunun edit denetimi (veya statik metin) bölümünün yüksekliğini ayarlar.|
|[CComboBox::SetLocale](#setlocale)|Açılan kutu için yerel tanımlayıcıyı ayarlar.|
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Geçerli açılan kutunun açılır listesindeki en az görünür öğe sayısını ayarlar.|
|[CComboBox::SetTopIndex](#settopindex)|En üstte belirtilen dizin ile öğeyi görüntülemek için açılan kutunun liste kutusu bölümünü söyler.|
|[CComboBox::ShowDropDown](#showdropdown)|CBS_DROPDOWN veya CBS_DROPDOWNLIST stiline sahip açılan kutunun liste kutusunu gösterir veya gizler.|

## <a name="remarks"></a>Açıklamalar

Açılan kutu, statik denetim veya denetimle birlikte bir liste kutusundan oluşur. Denetimin liste kutusu bölümü her zaman görüntülenebilir veya yalnızca kullanıcı denetimin yanındaki açılır ok'u seçtiğinde düşebilir.

Liste kutusunda ki şu anda seçili öğe (varsa) statik veya edit denetiminde görüntülenir. Ayrıca, açılan liste stilivarsa, kullanıcı listedeki öğelerden birinin ilk karakterini yazabilir ve liste kutusu görünürse, bir sonraki öğeyi bu ilk karakterle vurgular.

Aşağıdaki tablo üç açılan kutu [stilini](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)karşılaştırır.

|Stil|Liste kutusu ne zaman görünür|Statik veya denetim edin|
|-----------|-------------------------------|-----------------------------|
|Basit|Her zaman|Düzenle|
|Açılır|Düştüğünde|Düzenle|
|Açılır liste|Düştüğünde|Statik|

Bir iletişim `CComboBox` şablonundan veya doğrudan kodunuzda bir nesne oluşturabilirsiniz. Her iki durumda da, `CComboBox` `CComboBox` önce nesneoluşturmak için oluşturucuyu arayın; ardından denetimi [Create](#create) oluşturmak ve `CComboBox` nesneye bağlamak için Üye Oluştur işlevini çağırın.

Açılan kutu tarafından üst kutusuna gönderilen Windows bildirim iletilerini (genellikle türetilmiş bir sınıf) işlemek `CDialog`istiyorsanız, her ileti için üst sınıfa bir ileti eşlemi girişi ve ileti işleyicisi üye işlevi ekleyin.

Her ileti-eş-eşlemi girişi aşağıdaki formu alır:

**ON\_**_Bildirimi_ **(** _id_, _üyeFxn_ **)**

bildirim `id` gönderen açılan kutu denetiminin alt pencere kimliğini belirtir ve `memberFxn` bildirimi işlemek için yazdığınız üst üye işlevinin adıdır.

Ebeveynin işlev prototipi aşağıdaki gibidir:

**afx_msg** `void` afx_msg `memberFxn` **( );**

Belirli bildirimlerin gönderilme sırası tahmin edilemez. Özellikle, CBN_CLOSEUP bildiriminden önce veya sonra CBN_SELCHANGE bir bildirim oluşabilir.

Olası ileti eşlemi girişleri şunlardır:

- ON_CBN_CLOSEUP (Windows 3.1 ve sonrası.) Açılan kutunun liste kutusu kapandı. Bu bildirim iletisi, [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahip bir açılan kutu için gönderilmez.

- ON_CBN_DBLCLK Kullanıcı, açılan kutunun liste kutusundaki bir dizeyi çift tıklatıyor. Bu bildirim iletisi yalnızca CBS_SIMPLE stiline sahip bir açılan kutu için gönderilir. [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili olan bir açılan kutu için, tek bir tıklama liste kutusunu gizlediği için çift tıklatma yapılamaz.

- ON_CBN_DROPDOWN Açılan kutunun liste kutusu düşmek üzere (görünür hale getirilebilir). Bu bildirim iletisi yalnızca CBS_DROPDOWN veya CBS_DROPDOWNLIST stiline sahip bir açılan kutu için oluşabilir.

- ON_CBN_EDITCHANGE Kullanıcı, açılan kutunun denetim denetimi bölümündeki metni değiştirmiş olabilecek bir eylemde bulunabilir. CBN_EDITUPDATE iletinin aksine, bu ileti Windows ekranı güncelledikten sonra gönderilir. Açılan kutu CBS_DROPDOWNLIST stiline sahipse gönderilmez.

- ON_CBN_EDITUPDATE Açılan kutunun denetim denetimi bölümü değiştirilmiş metni görüntülemek üzeredir. Bu bildirim iletisi, denetim metni biçimlendirdikten sonra ancak metni görüntülemeden önce gönderilir. Açılan kutu CBS_DROPDOWNLIST stiline sahipse gönderilmez.

- ON_CBN_ERRSPACE Açılan kutu, belirli bir isteği karşılamak için yeterli belleği ayıramaz.

- ON_CBN_SELENDCANCEL (Windows 3.1 ve sonrası.) Kullanıcı seçiminin iptal edilmesi gerektiğini gösterir. Kullanıcı bir öğeyi tıklatır ve ardından açılan kutunun liste kutusunu gizlemek için başka bir pencereyi veya denetimi tıklatır. Bu bildirim iletisi, kullanıcı seçiminin göz ardı edilmesi gerektiğini belirtmek için CBN_CLOSEUP bildirim iletisinden önce gönderilir. CBN_SELENDCANCEL veya CBN_SELENDOK bildirim iletisi, CBN_CLOSEUP bildirim iletisi gönderilmese bile (CBS_SIMPLE stiline sahip bir açılan kutuda olduğu gibi) gönderilir.

- ON_CBN_SELENDOK Kullanıcı bir öğe seçer ve sonra ENTER tuşuna basarsa veya açılan kutunun liste kutusunu gizlemek için DOWN ARROW tuşuna tıklar. Bu bildirim iletisi, kullanıcı seçiminin geçerli kabul edilmesi gerektiğini belirtmek için CBN_CLOSEUP iletisinden önce gönderilir. CBN_SELENDCANCEL veya CBN_SELENDOK bildirim iletisi, CBN_CLOSEUP bildirim iletisi gönderilmese bile (CBS_SIMPLE stiline sahip bir açılan kutuda olduğu gibi) gönderilir.

- ON_CBN_KILLFOCUS Açılan kutu giriş odağı kaybediyor.

- ON_CBN_SELCHANGE Açılan kutunun liste kutusundaki seçim, kullanıcının liste kutusuna tıklayarak veya ok tuşlarını kullanarak seçimi değiştirmesi sonucu değişmek üzeredir. Bu iletiyi işlerken, açılan kutunun denetimindeki metin yalnızca benzer `GetLBText` bir işlev veya başka bir işlev aracılığıyla alınabilir. `GetWindowText`kullanılamaz.

- ON_CBN_SETFOCUS Açılan kutu giriş odağı alır.

İletişim kutusu `CComboBox` içinde (iletişim kaynağı aracılığıyla) bir nesne `CComboBox` oluşturursanız, kullanıcı iletişim kutusunu kapattığında nesne otomatik olarak yok edilir.

Bir nesneyi `CComboBox` başka bir pencere nesnesine katıştırmak, onu yok etmeniz gerekmez. Yığının `CComboBox` üzerinde nesne oluşturursanız, otomatik olarak yok edilir. Nesneyi `CComboBox` **yeni** işlevi kullanarak yığında oluşturursanız, Windows açılan kutusu yok edildiğinde nesneyi yok etmek için nesneyi **silme'yi** aramanız gerekir.

**Not** WM_KEYDOWN ve WM_CHAR iletileri işlemek istiyorsanız, açılan kutunun edit ve liste kutusu denetimlerini alt sınıfa eklemeniz, türemiş sınıflardan `CEdit` sınıflar türetmeniz ve `CListBox`bu iletiler için işleyiciler eklemeniz gerekir. Daha fazla bilgi için [Bkz. CWnd::Alt Sınıf Penceresi.](../../mfc/reference/cwnd-class.md#subclasswindow)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="ccomboboxaddstring"></a><a name="addstring"></a>CComboBox::AddString

Açılan kutunun liste kutusuna bir dize ekler.

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*lpszString*<br/>
Eklenecek null-sonlandırılan dize işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

İade değeri 0'dan büyük veya eşitse, liste kutusundaki dizedeki sıfır tabanlı dizindir. Bir hata oluşursa iade değeri CB_ERR; yeni dizeyi depolamak için yeterli alan varsa, iade değeri CB_ERRSPACE.

### <a name="remarks"></a>Açıklamalar

Liste kutusu [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiliyle oluşturulmadıysa, dize listenin sonuna eklenir. Aksi takdirde, dize listeye eklenir ve liste sıralanır.

> [!NOTE]
> Bu işlev Windows `ComboBoxEx` denetimi tarafından desteklenmez. Bu denetim hakkında daha fazla bilgi için Windows SDK'daki [ComboBoxEx Denetimleri'ne](/windows/win32/Controls/comboboxex-controls) bakın.

Liste içinde belirli bir konuma bir dize eklemek için [InsertString](#insertstring) üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

## <a name="ccomboboxccombobox"></a><a name="ccombobox"></a>CComboBox::CComboBox

Bir `CComboBox` nesne inşa eder.

```
CComboBox();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

## <a name="ccomboboxclear"></a><a name="clear"></a>CComboBox::Temizleyin

Açılan kutunun düzenkontrolünde geçerli seçimi siler (temizler).

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Geçerli seçimi silmek ve silinen içeriği Pano'ya yerleştirmek için [Kes](#cut) üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

## <a name="ccomboboxcompareitem"></a><a name="compareitem"></a>CComboBox::Karşılaştırma Öğesi

Sıralanmış bir sahip-beraberlik açılan kutusunun liste kutusu bölümünde yeni bir öğenin göreli konumunu belirlemek için çerçeve tarafından çağrılır.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpCompareItemStruct*<br/>
[COMPAREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-compareitemstruct) yapısıiçin uzun bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`COMPAREITEMSTRUCT` Yapıda açıklanan iki öğenin göreli konumunu gösterir. Aşağıdaki değerlerden herhangi biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|- 1|Madde 1 madde 2'den önce sıralar.|
|0|Madde 1 ve madde 2 aynı sıralayın.|
|1|Madde 1 madde 2'den sonra sıralar.|

Bkz. [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) açıklaması `COMPAREITEMSTRUCT`için .

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. LBS_SORT stiline sahip bir sahip çizimi açılan kutusu oluşturursanız, liste kutusuna eklenen yeni öğeleri sıralamada çerçeveye yardımcı olmak için bu üye işlevini geçersiz kılmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

## <a name="ccomboboxcopy"></a><a name="copy"></a>CComboBox::Kopyala

Varsa geçerli seçimi, açılan kutunun denetiminde CF_TEXT biçiminde Pano üzerine kopyalar.

```cpp
void Copy();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

## <a name="ccomboboxcreate"></a><a name="create"></a>CComboBox::Oluştur

Açılan kutuyu oluşturur ve `CComboBox` nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Açılan kutunun stilini belirtir. [Kutuya açılan kutu stillerinin](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) herhangi bir birleşimini uygulayın.

*Rect*<br/>
Açılan kutunun konumunu ve boyutunu işaret edin. [RECT yapısı](/windows/win32/api/windef/ns-windef-rect) veya nesne `CRect` olabilir.

*pParentWnd*<br/>
Açılan kutunun üst penceresini belirtir (genellikle `CDialog`bir). NULL olmamalıdır.

*Nıd*<br/>
Açılan kutunun denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CComboBox` iki adımda inşa ee. İlk olarak, oluşturucuyu `Create`çağırın ve ardından Windows açılan kutusunu oluşturan `CComboBox` ve nesneye iliştiren ,

Yürütüldüğünde, `Create` Windows [WM_NCCREATE,](../../mfc/reference/cwnd-class.md#onnccreate) [WM_CREATE,](../../mfc/reference/cwnd-class.md#oncreate) [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) iletilerini açılan kutuya gönderir.

Bu iletiler varsayılan olarak [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) üye işlevleri `CWnd` tarafından temel sınıfta işlenir. Varsayılan ileti işlemeyi genişletmek için, `CComboBox`yeni sınıfa bir ileti eşlemi ekleyin ve önceki ileti işleyicisi üye işlevlerini geçersiz kılın. Geçersiz `OnCreate`kılma , örneğin, yeni bir sınıf için gerekli başlatma gerçekleştirmek için.

Açılan kutu denetimine aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) uygulayın. :

- WS_CHILD Her Zaman

- WS_VISIBLE Genellikle

- WS_DISABLED Nadiren

- WS_VSCROLL Açılan kutudaki liste kutusu için dikey kaydırma eklemek için

- WS_HSCROLL Açılan kutudaki liste kutusu için yatay kaydırma eklemek için

- WS_GROUP Denetimleri gruplandırmak için

- WS_TABSTOP Açılan kutuyu sekme sırasına eklemek için

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

## <a name="ccomboboxcut"></a><a name="cut"></a>CComboBox::Kes

Açılan kutu düzenle denetiminde geçerli seçimi siler (keser) ve silinen metni CF_TEXT biçiminde Pano üzerine kopyalar.

```cpp
void Cut();
```

### <a name="remarks"></a>Açıklamalar

Silinen metni Pano'ya yerleştirmeden geçerli seçimi silmek için [Üye](#clear) İcadını Temizle'yi arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

## <a name="ccomboboxdeleteitem"></a><a name="deleteitem"></a>CComboBox::DeleteItem

Kullanıcı bir öğeyi sahip çizim `CComboBox` nesnesinden sildiğinde veya açılan kutuyu yok ettiğinde çerçeve tarafından çağrılır.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDeleteItemStruct*<br/>
Silinen öğe hakkında bilgi içeren windows [deleteitemstruct](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) yapısıiçin uzun bir işaretçi. Bu yapının açıklaması için [Bkz. CWnd::OnDeleteItem.](../../mfc/reference/cwnd-class.md#ondeleteitem)

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması hiçbir şey yapmaz. Gerektiğinde açılan kutuyu yeniden çizmek için bu işlevi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

## <a name="ccomboboxdeletestring"></a><a name="deletestring"></a>CComboBox::DeleteString

NIndex konumundaki *nIndex* öğeyi açılan kutudan siler.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Dizin silinecek dize belirtir.

### <a name="return-value"></a>Dönüş Değeri

İade değeri 0'dan büyük veya eşitse, listede kalan dizelerin sayısıdır. *nIndex* listedeki madde sayısından daha büyük bir dizin belirtse, iade değeri CB_ERR edilir.

### <a name="remarks"></a>Açıklamalar

*nIndex'i* izleyen tüm öğeler artık tek bir konumda aşağı hareket ediyor. Örneğin, açılan kutu iki öğe içeriyorsa, ilk öğenin silmesi kalan öğenin şimdi ilk konumda olmasıgerekir. *nIndex*=0 ilk konumdaki öğe için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

## <a name="ccomboboxdir"></a><a name="dir"></a>CComboBox::Dir

Açılan kutunun liste kutusuna dosya adlarının veya sürücülerin listesini ekler.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Parametreler

*Attr*<br/>
CFile'da açıklanan **enum** değerlerinin herhangi bir kombinasyonu [olabilir::GetStatus](../../mfc/reference/cfile-class.md#getstatus) veya aşağıdaki değerlerin herhangi bir kombinasyonu:

- DDL_READWRITE Dosya okunabilir veya yazılabilir.

- DDL_READONLY Dosya okunabilir ama yazılamaz.

- DDL_HIDDEN Dosyası gizlidir ve bir dizin listesinde görünmez.

- DDL_SYSTEM Dosya bir sistem dosyasıdır.

- DDL_DIRECTORY *LpszWildCard* tarafından belirtilen ad bir dizini belirtir.

- DDL_ARCHIVE Dosyası arşivlendi.

- DDL_DRIVES *lpszWildCard*tarafından belirtilen ada uyan tüm sürücüleri ekleyin.

- DDL_EXCLUSIVE Özel bayrak. Özel bayrak ayarlanırsa, yalnızca belirtilen türdeki dosyalar listelenir. Aksi takdirde, belirtilen türdeki dosyalar "normal" dosyalara ek olarak listelenir.

*lpszWildCard*<br/>
Dosya belirtimi dizesini işaret edin. Dize joker karakterler içerebilir (örneğin,\**. ).

### <a name="return-value"></a>Dönüş Değeri

İade değeri 0'dan büyük veya eşitse, listeye eklenen son dosya adının sıfır tabanlı dizinidir. Bir hata oluşursa iade değeri CB_ERR; yeni dizeleri depolamak için yeterli alan varsa, iade değeri CB_ERRSPACE edilir.

### <a name="remarks"></a>Açıklamalar

Bu işlev Windows `ComboBoxEx` denetimi tarafından desteklenmez. Bu denetim hakkında daha fazla bilgi için Windows SDK'daki [ComboBoxEx Denetimleri'ne](/windows/win32/Controls/comboboxex-controls) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

## <a name="ccomboboxdrawitem"></a><a name="drawitem"></a>CComboBox::DrawItem

Bir sahibi-beraberlik açılan kutusunun görsel bir yönü değiştiğinde çerçeve tarafından çağrılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısıiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yapının `itemAction` `DRAWITEMSTRUCT` üyesi, gerçekleştirilecek çizim eylemini tanımlar. Bu yapının açıklaması için [Bkz. CWnd::OnDrawItem.](../../mfc/reference/cwnd-class.md#ondrawitem)

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bir sahip çizim `CComboBox` nesnesi için çizim uygulamak için bu üye işlevi geçersiz kılın. Bu üye işlev sona ermeden önce, uygulama *lpDrawItemStruct'ta*sağlanan ekran bağlamı için seçilen tüm grafik aygıtı arabirimi (GDI) nesnelerini geri yüklemelidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

## <a name="ccomboboxfindstring"></a><a name="findstring"></a>CComboBox::FindString

Açılan kutunun liste kutusunda belirtilen önek'i içeren ilk dizeyi bulur, ancak seçmez.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>Parametreler

*nStartAfter*<br/>
Aranacak ilk öğeden önce maddenin sıfır tabanlı dizinini içerir. Arama liste kutusunun altına ulaştığında, liste kutusunun üst kısmından *nStartAfter*tarafından belirtilen öğeye kadar devam ediyor. -1 ise, tüm liste kutusu baştan aranır.

*lpszString*<br/>
Aranacak önek içeren null-sonlandırılan dizeyi işaret edin. Arama büyük/küçük harften bağımsızdır, bu nedenle bu dize büyük harf ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

İade değeri 0'dan büyük veya eşitse, eşleşen maddenin sıfır tabanlı dizinidir. Arama başarısız olup olmadığını CB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu işlev Windows `ComboBoxEx` denetimi tarafından desteklenmez. Bu denetim hakkında daha fazla bilgi için Windows SDK'daki [ComboBoxEx Denetimleri'ne](/windows/win32/Controls/comboboxex-controls) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

## <a name="ccomboboxfindstringexact"></a><a name="findstringexact"></a>CComboBox::FindStringExact

`FindStringExact` *LpszFind'da*belirtilen dizeyle eşleşen ilk liste kutusu dizesini (açılan kutuda) bulmak için üye işlevi arayın.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Parametreler

*nIndexStart*<br/>
Aranacak ilk öğeden önce maddenin sıfır tabanlı dizinini belirtir. Arama liste kutusunun altına ulaştığında, liste kutusunun üstünden *nIndexStart*tarafından belirtilen öğeye kadar devam ediyor. *nIndexStart* -1 ise, tüm liste kutusu baştan aranır.

*lpszBul*<br/>
Aramak için null-sonlandırılan dize işaret. Bu dize uzantısı da dahil olmak üzere tam bir dosya adı içerebilir. Arama büyük/küçük harf duyarlı değildir, bu nedenle bu dize büyük harf ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen öğenin sıfır tabanlı dizin veya arama başarısız olup olmadığını CB_ERR.

### <a name="remarks"></a>Açıklamalar

Açılan kutu bir sahibi-beraberlik tarzı ile ancak [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) tarzı `FindStringExact` olmadan oluşturuldu, *lpszFind*değeri karşı doubleword değeri eşleştirmek için çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

## <a name="ccomboboxgetcomboboxinfo"></a><a name="getcomboboxinfo"></a>CComboBox::GetComboBoxInfo

`CComboBox` Nesne için bilgi alır.

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>Parametreler

*pcbi*<br/>
[COMBOBOXINFO](/windows/win32/api/winuser/ns-winuser-comboboxinfo) yapısına bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [CB_GETCOMBOBOXINFO](/windows/win32/Controls/cb-getcomboboxinfo) iletinin işlevselliğini taklit eder.

## <a name="ccomboboxgetcount"></a><a name="getcount"></a>CComboBox::GetCount

Açılan kutunun liste kutusu bölümündeki öğelerin sayısını almak için bu üye işlevi arayın.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısı. Döndürülen sayım, son maddenin dizin değerinden bir büyüktür (dizin sıfır tabanlıdır). Bir hata oluşursa CB_ERR.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

## <a name="ccomboboxgetcuebanner"></a><a name="getcuebanner"></a>CComboBox::GetCueBanner

Açılan kutu denetimi için görüntülenen işaret metnini alır.

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpszMetin*|[çıkış] İşaretçi afiş metnini alan bir arabelleğe işaretçi.|
|*cchText*|[içinde] *LpszText* parametresinin işaret ettiği arabelleğe boyutu.|

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yüklemede, varsa işaret başlığı metnini içeren bir [CString](../../atl-mfc-shared/using-cstring.md) nesnesi; aksi takdirde, sıfır uzunluğa sahip bir `CString` nesne.

-veya-

İkinci aşırı yükte, bu yöntem başarılı olursa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

İşaret metni, açılan kutu denetiminin giriş alanında görüntülenen bir istemdir. İşaret metni, kullanıcı giriş sağlayana kadar görüntülenir.

Bu yöntem, Windows SDK'da açıklanan [CB_GETCUEBANNER](/windows/win32/Controls/cb-getcuebanner) iletisini gönderir.

## <a name="ccomboboxgetcursel"></a><a name="getcursel"></a>CComboBox::GetCurSel

Açılan kutudaki öğenin seçili olduğunu belirlemek için bu üye işlevini arayın.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan kutunun liste kutusunda şu anda seçili öğenin sıfır tabanlı dizini veya öğe seçili değilse CB_ERR.

### <a name="remarks"></a>Açıklamalar

`GetCurSel`listeye bir dizin döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

## <a name="ccomboboxgetdroppedcontrolrect"></a><a name="getdroppedcontrolrect"></a>CComboBox::GetDroppedControlRect

Açılan `GetDroppedControlRect` açılan kutunun görünür (bırakılan)liste kutusunun ekran koordinatlarını almak için üye işlevi arayın.

```cpp
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Koordinatları almak için [RECT yapısını](/windows/win32/api/windef/ns-windef-rect) işaret eder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

## <a name="ccomboboxgetdroppedstate"></a><a name="getdroppedstate"></a>CComboBox::GetDroppedState

Açılan `GetDroppedState` açılan açılan kutunun liste kutusunun görünür olup olmadığını (aşağı bırakıldığını) belirlemek için üye işlevi arayın.

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusu görünürse sıfırolmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

## <a name="ccomboboxgetdroppedwidth"></a><a name="getdroppedwidth"></a>CComboBox::GetDroppedGenişliği

Açılan kutunun liste kutusunun piksel olarak izin verilebilen en az genişliğini almak için bu işlevi arayın.

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, piksellerde izin verilebilen en az genişlik; aksi takdirde, CB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahip açılan kutular için geçerlidir.

Varsayılan olarak, açılır liste kutusunun izin verilebilen minimum genişliği 0'dır. İzin verilebilecek minimum genişlik [SetDroppedWidth](#setdroppedwidth)olarak ayarlanabilir. Açılan kutunun liste kutusu kısmı görüntülendiğinde, genişliği izin verilebilen minimum genişlik veya açılan kutu genişliğinden daha büyüktür.

### <a name="example"></a>Örnek

  [SetDroppedWidth](#setdroppedwidth)örneğine bakın.

## <a name="ccomboboxgeteditsel"></a><a name="geteditsel"></a>CComboBox::GetEditSel

Açılan kutunun edit denetiminde geçerli seçimin başlangıç ve bitiş karakter konumlarını alır.

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düşük sıralı sözcükteki başlangıç konumunu ve yüksek sıralı sözcükteki seçimin bitiminden sonra seçilmeyen ilk karakterin konumunu içeren 32 bitlik bir değer. Bu işlev, bir denetim denetimi olmayan bir açılan kutuda kullanılırsa, CB_ERR döndürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

## <a name="ccomboboxgetextendedui"></a><a name="getextendedui"></a>CComboBox::GetExtendedUI

Açılan `GetExtendedUI` kutunun varsayılan kullanıcı arabirimine mi yoksa genişletilmiş kullanıcı arabirimine mi sahip olduğunu belirlemek için üye işlevini arayın.

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan kutu genişletilmiş kullanıcı arabirimine sahipse sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş kullanıcı arabirimi aşağıdaki yollarla tanımlanabilir:

- Statik denetimi tıklattığınızda, liste kutusu yalnızca [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahip açılan kutular için görüntülenir.

- DOWN ARROW tuşuna basıldığında liste kutusu görüntülenir (F4 devre dışı bırakılır).

Öğe listesi görünmüyorsa statik denetimde kaydırma devre dışı bırakılır (ok tuşları devre dışı bırakılır).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

## <a name="ccomboboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CComboBox::GetHorizontalExtent

Açılan kutudan, açılan kutunun liste kutusu bölümünün yatay olarak kaydırılabildiği piksel genişliği alır.

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan kutunun piksel olarak liste kutusu bölümünün kaydırılabilir genişliği.

### <a name="remarks"></a>Açıklamalar

Bu, yalnızca açılan kutunun liste kutusu bölümünün yatay kaydırma çubuğuna sahip olması durumunda geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

## <a name="ccomboboxgetitemdata"></a><a name="getitemdata"></a>CComboBox::GetItemData

Belirtilen açılan kutu öğesi ile ilişkili uygulama tarafından sağlanan 32 bit değeri alır.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Açılan kutunun liste kutusundaki bir öğenin sıfır tabanlı dizinini içerir.

### <a name="return-value"></a>Dönüş Değeri

Maddeyle ilişkili 32 bit değeri veya bir hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

32 bit lik değer, [SetItemData](#setitemdata) üye işlev çağrısının *dwItemdata* parametresi ile ayarlanabilir. Alınacak `GetItemDataPtr` 32 bit değeri bir işaretçi **(geçersiz)** <strong>\*</strong>ise üye işlevi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

## <a name="ccomboboxgetitemdataptr"></a><a name="getitemdataptr"></a>CComboBox::GetItemDataPtr

Belirtilen açılan kutu öğesi ile ilişkili uygulama tarafından sağlanan 32 bit değeri işaretçi **(geçersiz)** <strong>\*</strong>olarak alır.

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Açılan kutunun liste kutusundaki bir öğenin sıfır tabanlı dizinini içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi veya bir hata oluşursa -1 alır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

## <a name="ccomboboxgetitemheight"></a><a name="getitemheight"></a>CComboBox::GetItemHeight

Liste `GetItemHeight` öğelerinin yüksekliğini bir açılan kutuda almak için üye işlevi arayın.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Yüksekliği alınacak açılan kutunun bileşenini belirtir. *nIndex* parametresi -1 ise, açılan kutunun edit denetimi (veya statik metin) bölümünün yüksekliği alınır. Açılan kutuda [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili varsa, *nIndex* yüksekliği alınacak liste öğesinin sıfır tabanlı dizinini belirtir. Aksi takdirde, *nIndex* 0 olarak ayarlanmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Açılan kutuda belirtilen öğenin piksel cinsinden yüksekliği. Bir hata oluşursa iade değeri CB_ERR.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

## <a name="ccomboboxgetlbtext"></a><a name="getlbtext"></a>CComboBox::GetLBText

Açılan kutunun liste kutusundan bir dize alır.

```
int GetLBText(
    int nIndex,
    LPTSTR lpszText) const;

void GetLBText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Kopyalanacak liste kutusu dizesinin sıfır tabanlı dizinini içerir.

*lpszMetin*<br/>
Dize almak için bir arabellek işaret ediyor. Arabellek dize ve sonlandırıcı null karakter için yeterli alana sahip olmalıdır.

*rString*<br/>
Bir başvuru `CString`.

### <a name="return-value"></a>Dönüş Değeri

Sonlandırıcı null karakteri hariç, dize uzunluğu (bayt olarak). nIndex geçerli bir *dizin* belirtmezse, iade değeri CB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin ikinci biçimi, bir `CString` nesneyi öğenin metniyle doldurur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

## <a name="ccomboboxgetlbtextlen"></a><a name="getlbtextlen"></a>CComboBox::GetLBTextLen

Açılan kutunun liste kutusunda bir dize uzunluğunu alır.

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste kutusu dizesinin sıfır tabanlı dizinini içerir.

### <a name="return-value"></a>Dönüş Değeri

Sonlandırıcı null karakteri hariç olmak üzere, baytlar halindeki dize uzunluğu. nIndex geçerli bir *dizin* belirtmezse, iade değeri CB_ERR.

### <a name="example"></a>Örnek

  [CComboBox örneğine bakın:GetLBText](#getlbtext).

## <a name="ccomboboxgetlocale"></a><a name="getlocale"></a>CComboBox::GetLocale

Açılan kutu tarafından kullanılan yerel alanı alır.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan kutudaki dizeleri için yerel tanımlayıcı (LCID) değeri.

### <a name="remarks"></a>Açıklamalar

Yerel, örneğin, sıralanmış bir açılan kutudaki dizelerin sıralama sırasını belirlemek için kullanılır.

### <a name="example"></a>Örnek

  [CComboBox örneğine bakın:SetLocale](#setlocale).

## <a name="ccomboboxgetminvisible"></a><a name="getminvisible"></a>CComboBox::GetMinVisible

Geçerli açılan kutu denetiminin açılır listesindeki en az görünür öğe sayısını alır.

```
int GetMinVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli açılır listedeki en az görünür öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [CB_GETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) iletisini gönderir.

## <a name="ccomboboxgettopindex"></a><a name="gettopindex"></a>CComboBox::GetTopIndex

Açılan kutunun liste kutusu bölümündeki ilk görünür öğenin sıfır tabanlı dizinini alır.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, açılan kutunun liste kutusu bölümündeki ilk görünür öğenin sıfır tabanlı dizini aksi CB_ERR.

### <a name="remarks"></a>Açıklamalar

Başlangıçta, madde 0 liste kutusunun en üstündedir, ancak liste kutusu kaydırılırsa, başka bir öğe en üstte olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

## <a name="ccomboboxinitstorage"></a><a name="initstorage"></a>CComboBox::InitStorage

Liste kutusu öğelerini açılan kutunun liste kutusu bölümünde depolamak için bellek ayırır.

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

Başarılı olursa, açılan kutunun liste kutusu bölümünün bellek yeniden tahsisi gerekli olmadan önce depolayabildiği maksimum öğe sayısı, aksi takdirde CB_ERRSPACE, yani yeterli bellek kullanılamaz.

### <a name="remarks"></a>Açıklamalar

Listenin kutu bölümüne çok sayıda öğe eklemeden önce `CComboBox`bu işlevi arayın.

Yalnızca Windows 95/98: *WParam* parametresi 16 bit değerlerle sınırlıdır. Bu, liste kutularının 32.767'den fazla öğe içeremeyeceği anlamına gelir. Öğe sayısı kısıtlanmış olsa da, liste kutusundaki öğelerin toplam boyutu yalnızca kullanılabilir bellekle sınırlıdır.

Bu işlev, çok sayıda öğeye (100'den fazla) sahip liste kutularının başlatılmasını hızlandırmaya yardımcı olur. Sonraki [AddString](#addstring), [InsertString](#insertstring)ve [Dir](#dir) işlevlerimümkün olan en kısa sürede almak böylece bellek belirtilen miktarda önceden ayırır. Parametreler için tahminleri kullanabilirsiniz. Eğer abartmak, bazı ekstra bellek ayrılır; eğer küçümserseniz, normal ayırma önceden tahsis edilen tutarı aşan maddeler için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

## <a name="ccomboboxinsertstring"></a><a name="insertstring"></a>CComboBox::InsertString

Açılan kutunun liste kutusuna bir dize ekler.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Dizeyi alacak liste kutusundaki konuma sıfır tabanlı dizin içerir. Bu parametre -1 ise, dize listenin sonuna eklenir.

*lpszString*<br/>
Eklenecek null-sonlandırılan dize işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

Dize eklendiği pozisyonun sıfır tabanlı dizin. Bir hata oluşursa iade değeri CB_ERR. Yeni dizeyi depolamak için yeterli alan varsa, iade değeri CB_ERRSPACE.

### <a name="remarks"></a>Açıklamalar

[AddString](#addstring) üye işlevinin `InsertString` aksine, üye işlev [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stilinin sıralanmasına sahip bir listeye neden olmaz.

> [!NOTE]
> Bu işlev Windows `ComboBoxEx` denetimi tarafından desteklenmez. Bu denetim hakkında daha fazla bilgi için Windows SDK'daki [ComboBoxEx Denetimleri'ne](/windows/win32/Controls/comboboxex-controls) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

## <a name="ccomboboxlimittext"></a><a name="limittext"></a>CComboBox::LimitText

Kullanıcının açılan kutunun düzenleme denetimine girebileceği metnin baytlarındaki uzunluğunu sınırlar.

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>Parametreler

*nMaxChars*<br/>
Kullanıcının girebileceği metnin uzunluğunu (baytolarak) belirtir. Bu parametre 0 ise, metin uzunluğu 65.535 bayt olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır değil. Stil [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya bir denetim denetimi olmayan bir açılan kutu için çağrılırsa, iade değeri CB_ERR.

### <a name="remarks"></a>Açıklamalar

Açılan [kutuda stil CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)yoksa, metin sınırını denetim denetiminin boyutundan daha büyük olacak şekilde ayarlamak hiçbir etki yaratmaz.

`LimitText`yalnızca kullanıcının girebileceği metni sınırlar. İleti gönderildiğinde denetim denetiminde zaten bulunan hiçbir metin üzerinde hiçbir etkisi yoktur veya liste kutusundaki bir dize seçildiğinde denetim denetimine kopyalanan metnin uzunluğunu etkilemez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

## <a name="ccomboboxmeasureitem"></a><a name="measureitem"></a>CComboBox::MeasureItem

Bir sahibi-beraberlik stili ile açılan kutu oluşturulduğunda çerçeve tarafından çağrılır.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) yapısıiçin uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bu üye işlevini geçersiz kılın `MEASUREITEMSTRUCT` ve windows'u açılan kutudaki liste kutusunun boyutları hakkında bilgilendirmek için yapıyı doldurun. Açılan kutu [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiliyle oluşturulursa, çerçeve liste kutusundaki her öğe için bu üye işlevi çağırır. Aksi takdirde, bu üye yalnızca bir kez çağrılır.

[SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) üye işlevi ile oluşturulan bir sahibi-beraberlik açılan kutusunda `CWnd` CBS_OWNERDRAWFIXED stili kullanarak daha fazla programlama hususlar içerir. Tartışmayı Teknik [Not 14'te](../../mfc/tn014-custom-controls.md)görün.

Bkz. [CWnd::Yapının](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT` açıklaması için OnMeasureItem.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

## <a name="ccomboboxpaste"></a><a name="paste"></a>CComboBox::Paste

Panodaki verileri geçerli imleç konumundaki açılan kutunun edit denetimine ekler.

```cpp
void Paste();
```

### <a name="remarks"></a>Açıklamalar

Veriler yalnızca Pano CF_TEXT biçiminde veri içeriyorsa eklenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

## <a name="ccomboboxresetcontent"></a><a name="resetcontent"></a>CComboBox::ResetContent

Liste kutusundaki tüm öğeleri kaldırır ve açılan kutunun denetimini denetler.

```cpp
void ResetContent();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

## <a name="ccomboboxselectstring"></a><a name="selectstring"></a>CComboBox::SelectString

Açılan kutunun liste kutusunda bir dize arar ve dize bulunursa, liste kutusundaki dizeyi seçer ve bunu denetime kopyalar.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*nStartAfter*<br/>
Aranacak ilk öğeden önce maddenin sıfır tabanlı dizinini içerir. Arama liste kutusunun altına ulaştığında, liste kutusunun üst kısmından *nStartAfter*tarafından belirtilen öğeye kadar devam ediyor. -1 ise, tüm liste kutusu baştan aranır.

*lpszString*<br/>
Aranacak önek içeren null-sonlandırılan dizeyi işaret edin. Arama büyük/küçük harften bağımsızdır, bu nedenle bu dize büyük harf ve küçük harflerin herhangi bir birleşimini içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Dize bulunduysa, seçili öğenin sıfır tabanlı dizin. Arama başarısız olduysa, iade değeri CB_ERR ve geçerli seçim değiştirilmez.

### <a name="remarks"></a>Açıklamalar

Bir dize yalnızca ilk karakterleri (başlangıç noktasından) önek dizedeki karakterlerle eşleşirse seçilir.

Hem bir `SelectString` `FindString` dize hem de üye `SelectString` işlevlerin bir dize bulduğunu, ancak üye işlevin de dizeyi seçtiğini unutmayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

## <a name="ccomboboxsetcuebanner"></a><a name="setcuebanner"></a>CComboBox::SetCueBanner

Açılan kutu denetimi için görüntülenen işaret metnini ayarlar.

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpszMetin*|[içinde] İşaretmetnini içeren null-sonlandırılan arabelleği işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

İşaret metni, açılan kutu denetiminin giriş alanında görüntülenen bir istemdir. İşaret metni, kullanıcı giriş sağlayana kadar görüntülenir.

Bu yöntem, Windows SDK'da açıklanan [CB_SETCUEBANNER](/windows/win32/Controls/cb-setcuebanner) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, açılan kutu denetimine programlı olarak erişmek için kullanılan değişken, *m_combobox*tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, açılan kutu denetimi için işaret başlığını ayarlar.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsetcursel"></a><a name="setcursel"></a>CComboBox::SetCurSel

Açılan kutunun liste kutusunda bir dize seçer.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Parametreler

*nSeç*<br/>
Seçilecek dizenin sıfır tabanlı dizinini belirtir. -1 ise, liste kutusundaki herhangi bir geçerli seçim kaldırılır ve denetim denetimi temizlenir.

### <a name="return-value"></a>Dönüş Değeri

İleti başarılı olursa seçilen öğenin sıfır tabanlı dizin. nSelect listedeki öğe sayısından büyükse veya *nSelect* *nSelect* seçimi temizleyen -1 olarak ayarlanmışsa, iade değeri CB_ERR edilir.

### <a name="remarks"></a>Açıklamalar

Gerekirse, liste kutusu dizeyi görünüme kaydırır (liste kutusu görünürse). Açılan kutunun denetimindeki metin, yeni seçimi yansıtacak şekilde değiştirilir. Liste kutusundaki önceki herhangi bir seçim kaldırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

## <a name="ccomboboxsetdroppedwidth"></a><a name="setdroppedwidth"></a>CComboBox::SetDroppedGenişliği

Açılan kutunun liste kutusunun piksel olarak izin verilebilen en az genişliğini ayarlamak için bu işlevi arayın.

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>Parametreler

*Nwidth*<br/>
Açılan kutunun pikselolarak liste kutusu bölümünün izin verilebilen minimum genişliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, liste kutusunun yeni genişliği, aksi takdirde CB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahip açılan kutular için geçerlidir.

Varsayılan olarak, açılır liste kutusunun izin verilebilen minimum genişliği 0'dır. Açılan kutunun liste kutusu kısmı görüntülendiğinde, genişliği izin verilebilen minimum genişlik veya açılan kutu genişliğinden daha büyüktür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

## <a name="ccomboboxseteditsel"></a><a name="seteditsel"></a>CComboBox::SetEditSel

Açılan kutunun denetiminde karakterleri seçer.

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>Parametreler

*nStartChar*<br/>
Başlangıç konumunu belirtir. Başlangıç konumu -1 olarak ayarlanırsa, varolan herhangi bir seçim kaldırılır.

*nEndChar*<br/>
Bitiş konumunu belirtir. Bitiş konumu -1 olarak ayarlanırsa, başlangıç konumundan edit denetimindeki son karaktere kadar tüm metin seçilir.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev başarılı olursa sıfırsız; aksi takdirde 0. CBS_DROPDOWNLIST stili `CComboBox` varsa [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya liste kutusu yoksa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Pozisyonlar sıfır tabanlıdır. Edit denetiminin ilk karakterini seçmek için, 0 başlangıç pozisyonu belirtirsiniz. Bitiş konumu, seçilecek son karakterden hemen sonra karakterin dir. Örneğin, denetim denetiminin ilk dört karakterini seçmek için, 0 başlangıç pozisyonu ve 4 bitiş pozisyonu kullanırsınız.

> [!NOTE]
> Bu işlev Windows `ComboBoxEx` denetimi tarafından desteklenmez. Bu denetim hakkında daha fazla bilgi için Windows SDK'daki [ComboBoxEx Denetimleri'ne](/windows/win32/Controls/comboboxex-controls) bakın.

### <a name="example"></a>Örnek

  [CComboBox örneğine bakın:GetEditSel](#geteditsel).

## <a name="ccomboboxsetextendedui"></a><a name="setextendedui"></a>CComboBox::SetExtendedUI

Varsayılan `SetExtendedUI` kullanıcı arabirimini veya [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahip bir açılan kutu için genişletilmiş kullanıcı arabirimini seçmek için üye işlevini arayın.

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>Parametreler

*Bmicrosoft*<br/>
Açılan kutunun genişletilmiş kullanıcı arabirimini mi yoksa varsayılan kullanıcı arabirimini mi kullanması gerektiğini belirtir. TRUE değeri genişletilmiş kullanıcı arabirimini seçer; FALSE değeri standart kullanıcı arabirimini seçer.

### <a name="return-value"></a>Dönüş Değeri

CB_OKAY işlem başarılı olursa veya bir hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş kullanıcı arabirimi aşağıdaki yollarla tanımlanabilir:

- Statik denetimi tıklattığınızda liste kutusu yalnızca CBS_DROPDOWNLIST stiline sahip açılan kutular için görüntülenir.

- DOWN ARROW tuşuna basıldığında liste kutusu görüntülenir (F4 devre dışı bırakılır).

Öğe listesi görünmüyorsa statik denetimde kaydırma devre dışı bırakılır (ok tuşları devre dışı bırakılır).

### <a name="example"></a>Örnek

  [CComboBox örneğine bakın:GetExtendedUI](#getextendedui).

## <a name="ccomboboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CComboBox::SetHorizontalExtent

Açılan kutunun liste kutusu bölümünün yatay olarak kaydırılabildiği genişliği piksel olarak ayarlar.

```cpp
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>Parametreler

*nExtent*<br/>
Açılan kutunun liste kutusu bölümünün yatay olarak kaydırılabildiği piksel sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Liste kutusunun genişliği bu değerden küçükse, yatay kaydırma çubuğu liste kutusundaki öğeleri yatay olarak kaydırır. Liste kutusunun genişliği bu değere eşit veya daha büyükse, yatay kaydırma çubuğu gizlenir veya açılan kutuda [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili varsa devre dışı bırakılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

## <a name="ccomboboxsetitemdata"></a><a name="setitemdata"></a>CComboBox::SetItemData

Açılan kutuda belirtilen öğeyle ilişkili 32 bit lik değeri ayarlar.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Ayarlayabilmek için öğeye sıfır tabanlı dizin içerir.

*dwItemData*<br/>
Öğeyle ilişkilendirilen yeni değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

CB_ERR bir hata oluşursa.

### <a name="remarks"></a>Açıklamalar

32 `SetItemDataPtr` bit öğesi işaretçi olacaksa üye işlevi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

## <a name="ccomboboxsetitemdataptr"></a><a name="setitemdataptr"></a>CComboBox::SetItemDataPtr

Belirtilen işaretçi **(geçersiz)** <strong>\*</strong>olarak açılan kutuda belirtilen öğeyle ilişkili 32 bit lik değeri ayarlar.

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Öğeye sıfır tabanlı dizin içerir.

*Pdata*<br/>
Öğeyle ilişkilendirmek için işaretçiyi içerir.

### <a name="return-value"></a>Dönüş Değeri

CB_ERR bir hata oluşursa.

### <a name="remarks"></a>Açıklamalar

Bu işaretçi, öğeler eklendikçe veya kaldırıldıkça öğenin açılan kutu içindeki göreli konumu değişse bile, açılan kutunun ömrü için geçerli kalır. Bu nedenle, öğenin kutunun içindeki dizin değişebilir, ancak işaretçi güvenilir kalır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

## <a name="ccomboboxsetitemheight"></a><a name="setitemheight"></a>CComboBox::SetItemHeight

Liste `SetItemHeight` öğelerinin yüksekliğini açılan kutuda veya bir açılan kutunun denetim denetimi (veya statik metin) bölümünün yüksekliğini ayarlamak için üye işlevi arayın.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste öğelerinin yüksekliğinin mi yoksa açılan kutunun denetim (veya statik metin) bölümünün yüksekliğinin ayarlanıp ayarlanmayacağını belirtir.

Açılan kutu [da CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahipse, *nIndex* yüksekliği ayarlanacak liste öğesinin sıfır tabanlı dizinini belirtir; aksi takdirde, *nIndex* 0 olmalıdır ve tüm liste öğelerinin yüksekliği ayarlanır.

*nIndex* -1 ise, açılan kutunun edit denetimi veya statik metin bölümünün yüksekliği ayarlanır.

*cyItemHeight*<br/>
*nIndex*tarafından tanımlanan açılan kutu bileşeninin yüksekliğini, piksel olarak belirtir.

### <a name="return-value"></a>Dönüş Değeri

dizin veya yükseklik geçersiz seCB_ERR; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Açılan kutunun denetim (veya statik metin) bölümünün yüksekliği, liste öğelerinin yüksekliğinden bağımsız olarak ayarlanır. Bir uygulama, denetim (veya statik metin) bölümünün yüksekliğinin belirli bir liste kutusu öğesinin yüksekliğinden küçük olmadığından emin olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

## <a name="ccomboboxsetlocale"></a><a name="setlocale"></a>CComboBox::SetLocale

Bu açılan kutu için yerel tanımlayıcıyı ayarlar.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Parametreler

*nNewLocale*<br/>
Açılan kutu için ayarlanan yeni yerel tanımlayıcı (LCID) değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu açılan kutu için önceki yerel tanımlayıcı (LCID) değeri.

### <a name="remarks"></a>Açıklamalar

`SetLocale` Çağrılmazsa, varsayılan yerel sistemden elde edilir. Bu sistem varsayılan yerel alanı, Denetim Masası'nın Bölgesel (veya Uluslararası) uygulaması kullanılarak değiştirilebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

## <a name="ccomboboxsetminvisibleitems"></a><a name="setminvisibleitems"></a>CComboBox::SetMinVisibleItems

Geçerli açılan kutu denetiminin açılır listesindeki en az görünür öğe sayısını ayarlar.

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iMinVisible*|[içinde] En az görünür öğe sayısını belirtir.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [CB_SETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, açılan kutu denetimine programlı olarak erişmek için kullanılan değişken, *m_combobox*tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, açılan kutu denetiminin açılır listesine 20 öğe ekler. Daha sonra, kullanıcı açılır oka bastığında en az 10 öğenin görüntüleneceğini belirtir.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsettopindex"></a><a name="settopindex"></a>CComboBox::SetTopIndex

Açılan kutunun liste kutusu bölümünde belirli bir öğenin görünür olmasını sağlar.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Liste kutusu öğesinin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır veya hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Sistem, *nIndex* tarafından belirtilen öğe liste kutusunun en üstünde görünene veya maksimum kaydırma aralığına ulaşılana kadar liste kutusunu kaydırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

## <a name="ccomboboxshowdropdown"></a><a name="showdropdown"></a>CComboBox::ShowDropDown

[CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiline sahip açılan kutunun liste kutusunu gösterir veya gizler.

```cpp
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>Parametreler

*bShowIt*<br/>
Açılan liste kutusunun gösterip gösterilmeyeceğini veya gizlenip gizlenmeyeceğini belirtir. TRUE değeri liste kutusunu gösterir. FALSE değeri liste kutusunu gizler.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu stildeki bir açılan kutu liste kutusunu gösterir.

Bu üye işlevin [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stiliyle oluşturulan açılan kutu üzerinde hiçbir etkisi yoktur.

### <a name="example"></a>Örnek

  [CComboBox örneğine bakın:GetDroppedState](#getdroppedstate).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CButton Sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar Sınıfı](../../mfc/reference/cscrollbar-class.md)<br/>
[Cstatic Sınıfı](../../mfc/reference/cstatic-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
