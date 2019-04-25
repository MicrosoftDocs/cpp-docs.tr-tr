---
title: CComboBox sınıfı
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
ms.openlocfilehash: a76be4be87471f26970a5b517d9993ae324b56c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62253993"
---
# <a name="ccombobox-class"></a>CComboBox sınıfı

Windows birleşik giriş kutusu işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComboBox : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComboBox::CComboBox](#ccombobox)|Oluşturur bir `CComboBox` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComboBox::AddString](#addstring)|Bir dize liste kutusunda bir birleşik giriş kutusunun ya da liste kutuları ile CBS_SORT stili için sıralanmış konumunda listesinin sonuna ekler.|
|[CComboBox::Clear](#clear)|Siler (temizler) varsa, düzenleme denetimindeki geçerli seçimi.|
|[CComboBox::CompareItem](#compareitem)|Yeni bir liste öğesi bir sıralanmış çizimli birleşik giriş kutusunda göreli konumunu belirlemek için framework tarafından çağırılır.|
|[CComboBox::Copy](#copy)|Geçerli seçimi, varsa CF_TEXT biçimde Pano'ya kopyalar.|
|[CComboBox::Create](#create)|Birleşik giriş kutusu oluşturur ve ona ekler `CComboBox` nesne.|
|[CComboBox::Cut](#cut)|(Keser) siler geçerli seçimin içindeki bir düzen denetlemek ve CF_TEXT biçiminde silinen metin Pano'ya kopyalar.|
|[CComboBox::DeleteItem](#deleteitem)|Bir kullanıcı çizimli birleşik giriş kutusundan bir liste öğesi silindiğinde framework tarafından çağırılır.|
|[CComboBox::DeleteString](#deletestring)|Bir dizeyi bir birleşik giriş kutusu liste kutusundan siler.|
|[CComboBox::Dir](#dir)|Dosya adları listesini bir birleşik giriş kutusu liste kutusuna ekler.|
|[CComboBox::DrawItem](#drawitem)|Bir kullanıcı çizimli birleşik giriş kutusu değişiklikleri görsel bir özelliği, framework tarafından çağırılır.|
|[CComboBox::FindString](#findstring)|Birleşik giriş kutusu liste kutusunda belirtilen prefix öğesini içerip ilk dize bulur.|
|[CComboBox::FindStringExact](#findstringexact)|Belirtilen dizeyi eşleşen ilk liste kutusu dizesinde (bir birleşik giriş kutusu) bulur.|
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Hakkında bilgi alır `CComboBox` nesne.|
|[CComboBox::GetCount](#getcount)|Birleşik giriş kutusu liste kutusunun içinde öğe sayısını alır.|
|[CComboBox::GetCueBanner](#getcuebanner)|Birleşik giriş kutusu denetimi için görüntülenen İpucu metni alır.|
|[CComboBox::GetCurSel](#getcursel)|Birleşik giriş kutusu liste kutusunda seçili öğenin dizinini alır|
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Ekran koordinatları görünür (aşağı bırakılan) liste kutusunun yanıdaki açılan birleşik giriş kutusunun alır.|
|[CComboBox::GetDroppedState](#getdroppedstate)|(Bırakılan) açılan birleşik giriş kutusu liste kutusunun görünür olup olmadığını belirler.|
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Genişlik bir birleşik giriş kutusu açılan liste kutusu kısmı için izin verilen en düşük alır.|
|[CComboBox::GetEditSel](#geteditsel)|Bir birleşik giriş kutusunun düzenleme denetimindeki geçerli bölüm başlangıç ve bitiş karakter konumlarını alır.|
|[CComboBox::GetExtendedUI](#getextendedui)|Birleşik giriş kutusu varsayılan kullanıcı arabirimi veya genişletilmiş kullanıcı arabirimini olup olmadığını belirler.|
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Birleşik giriş kutusu liste kutusu kısmı yatay yönde kaydırılabileceğini piksel cinsinden genişliğini döndürür.|
|[CComboBox::GetItemData](#getitemdata)|Belirtilen birleşik giriş kutusu öğesi ile ilişkili uygulama tarafından sağlanan 32-bit değeri alır.|
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Belirtilen birleşik giriş kutusu öğesi ile ilişkilendirilen uygulama tarafından sağlanan 32 bit işaretçi alır.|
|[CComboBox::GetItemHeight](#getitemheight)|Birleşik giriş kutusu liste öğelerini yüksekliğini alır.|
|[CComboBox::GetLBText](#getlbtext)|Birleşik giriş kutusu liste kutusundan bir dize alır.|
|[CComboBox::GetLBTextLen](#getlbtextlen)|Birleşik giriş kutusu liste kutusunda bir dizenin uzunluğunu alır.|
|[CComboBox::GetLocale](#getlocale)|Bir açılan kutunun yerel ayar tanımlayıcısını alır.|
|[CComboBox::GetMinVisible](#getminvisible)|En az sayıda görünen öğeler, geçerli birleşik giriş kutusundaki açılır listesini alır.|
|[CComboBox::GetTopIndex](#gettopindex)|Birleşik giriş kutusu liste kutusu bölümünde görünen ilk öğenin dizinini döndürür.|
|[CComboBox::InitStorage](#initstorage)|Öğeleri ve birleşik giriş kutusu liste kutusu kısmı dizeler için bellek blokları preallocates.|
|[CComboBox::InsertString](#insertstring)|Bir dizeyi bir birleşik giriş kutusu liste kutusuna ekler.|
|[CComboBox::LimitText](#limittext)|Kullanıcı bir birleşik giriş kutusunun düzenleme denetimine girebilirsiniz metnin uzunluğunu kısıtlar.|
|[CComboBox::MeasureItem](#measureitem)|Kullanıcı çizimli birleşik giriş kutusu oluşturulduğunda birleşik giriş kutusu boyutları belirlemek için framework tarafından çağırılır.|
|[CComboBox::Paste](#paste)|Verileri düzenleme denetimine geçerli imleç konumu panodan ekler. Yalnızca Pano CF_TEXT biçiminde veri içeriyorsa, veriler eklenir.|
|[CComboBox::ResetContent](#resetcontent)|Listeden tüm öğeler kutu ve bir birleşik giriş kutusu denetimi Düzenle kaldırır.|
|[CComboBox::SelectString](#selectstring)|Birleşik giriş kutusu liste kutusunda bir dizeyi arar ve dize bulunursa, dizeyi liste kutusunda seçer ve dize düzenleme denetimine kopyalar.|
|[CComboBox::SetCueBanner](#setcuebanner)|Birleşik giriş kutusu denetimi için görüntülenen İpucu metni ayarlar.|
|[CComboBox::SetCurSel](#setcursel)|Bir dizeyi bir birleşik giriş kutusu liste kutusunda seçer.|
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Genişlik bir birleşik giriş kutusu açılan liste kutusu kısmı için izin verilen en düşük ayarlar.|
|[CComboBox::SetEditSel](#seteditsel)|Birleşik giriş kutusu düzenleme denetiminde karakterleri seçer.|
|[CComboBox::SetExtendedUI](#setextendedui)|Varsayılan kullanıcı arabirimi veya CBS_DROPDOWN veya cbs_dropdownlıst stilde bir birleşik giriş kutusu için genişletilmiş kullanıcı arabirimini seçer.|
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Birleşik giriş kutusu liste kutusu kısmı yatay yönde kaydırılabileceğini piksel cinsinden genişliğini belirler.|
|[CComboBox::SetItemData](#setitemdata)|Belirtilen öğeyi bir birleşik giriş kutusunda ile ilişkili 32-bit değeri ayarlar.|
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Belirtilen öğeyi bir birleşik giriş kutusunda ile ilişkili 32 bit işaretçi ayarlar.|
|[CComboBox::SetItemHeight](#setitemheight)|Liste öğeleri yüksekliğini bir birleşik giriş kutusu veya bir birleşik giriş kutusu denetimini düzenleme (veya statik metin) bölümünün yüksekliği ayarlar.|
|[CComboBox::SetLocale](#setlocale)|Bir açılan kutunun yerel ayar tanımlayıcısı ayarlar.|
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Geçerli birleşik giriş kutusunun yanıdaki açılan listesinde görünen öğeleri en az sayısını ayarlar.|
|[CComboBox::SetTopIndex](#settopindex)|Belirtilen dizinle öğeyi üstünde görüntülenecek birleşik giriş kutusu liste kutusu kısmı söyler.|
|[CComboBox::ShowDropDown](#showdropdown)|CBS_DROPDOWN veya cbs_dropdownlıst stilde bir birleşik giriş kutusu liste kutusunda gizler veya gösterir.|

## <a name="remarks"></a>Açıklamalar

Statik denetim veya düzen denetimi ile birleştirilmiş bir liste kutusunun bir birleşik giriş kutusu oluşur. Liste kutusu denetimi her zaman görüntülenebilir veya bir kullanıcı denetimi yanındaki açılır oka seçtiğinde yalnızca açılan.

Liste kutusunda seçili öğenin (varsa) Denetim Düzenle veya statik görüntülenir. Ayrıca, birleşik giriş kutusunun yanıdaki açılan liste stilini varsa, kullanıcı listesinde öğelerin birinin ilk karakter yazabilirsiniz ve liste kutusu görünüyorsa, bu ilk karakteri ile sonraki öğeye vurgular.

Aşağıdaki tabloda karşılaştırılmıştır üç birleşik giriş kutusu [stilleri](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

|Stil|Liste kutusu görünür olduğunda olmadığı|Statik veya düzenleme denetimi|
|-----------|-------------------------------|-----------------------------|
|Basit|Her zaman|Düzenle|
|Açılan|Bırakılan olduğunda|Düzenle|
|Aşağı açılan listesi|Bırakılan olduğunda|Statik|

Oluşturabileceğiniz bir `CComboBox` iletişim kutusu şablonundan ya da kodunuzda doğrudan nesne. Her iki durumda da Oluşturucu çağırmanız `CComboBox` oluşturmak için `CComboBox` nesne; ardından çağırarak [Oluştur](#create) denetim oluşturma ve buna eklemek için üye işlevini `CComboBox` nesne.

Birleşik giriş kutusu tarafından yollanır Windows bildirim iletilerini işlemek isterseniz (öğesinden türetilmiş bir sınıf genellikle `CDialog`), üst sınıfın her ileti için ileti eşleme girişi ve ileti işleyicisi üye işlevi ekleyin.

Her ileti eşleme girişi aşağıdaki biçimi alır:

**ON\_**_bildirim_ **(** _kimliği_, _memberFxn_ **)**

Burada `id` bildirimi gönderilmesi birleşik giriş kutusu denetimi alt pencere Kimliğini belirtir ve `memberFxn` bildirimini işlemek için yazdığınız üst üye işlev adıdır.

Üst öğenin işlev prototipi aşağıdaki gibidir:

**afx_msg** `void` `memberFxn` **( );**

Belirli bildirimleri gönderilecek sırası tahmin edilemez. Özellikle, CBN_SELCHANGE bildirim önce veya sonra CBN_CLOSEUP bildirim ortaya çıkabilir.

Olası ileti eşlemesi girişleri aşağıda verilmiştir:

- ON_CBN_CLOSEUP (Windows 3.1 ve üzeri.) Birleşik giriş kutusu liste kutusunun kapattı. Bu bildirim iletisi içeren bir birleşik giriş kutusu için gönderilmez [cbs_sımple](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.

- Kullanıcı ON_CBN_DBLCLK birleşik giriş kutusu liste kutusunun bir dizede çift tıklamaları birbirinden ayırma. Bu bildirim iletisi yalnızca bir açılan kutunun cbs_sımple stiliyle gönderilir. İle bir açılan kutunun [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) tek tıklamayla gizler liste kutusu olduğundan, çift tıklama oluşamaz stili.

- Birleşik giriş kutusu liste kutusunun olduğundan yaklaşık olarak aşağı ON_CBN_DROPDOWN (yapılacak görünür). Bu bildirim iletisi yalnızca bir birleşik giriş kutusu CBS_DROPDOWN veya cbs_dropdownlıst stiliyle için oluşabilir.

- Metin düzenleme denetiminin bölümüne bir birleşik giriş kutusunun değiştirmiş bir eylem ON_CBN_EDITCHANGE kullanıcı sürdü. Ekran Windows güncelleştirmeleri sonrasında CBN_EDITUPDATE ileti farklı olarak bu ileti gönderilir. Birleşik giriş kutusu cbs_dropdownlıst stile sahipse gönderilmez.

- ON_CBN_EDITUPDATE düzenleme denetimi bir açılan kutunun hakkında değiştirilmiş görünen metni bölümüdür. Denetim biçimlendirilmiş metin sonra ancak metni görüntüler önce bu bildirim iletisi gönderilir. Birleşik giriş kutusu cbs_dropdownlıst stile sahipse gönderilmez.

- Birleşik giriş kutusu ON_CBN_ERRSPACE belirli bir istek karşılamak için yeterli bellek ayrılamıyor.

- ON_CBN_SELENDCANCEL (Windows 3.1 ve üzeri.) Kullanıcının seçiminin iptal edilmesi gerektiğine gösterir. Kullanıcı bir öğeyi tıklattığında ve ardından başka bir pencere veya birleşik giriş kutusu liste kutusunun gizlemek için denetime tıklar. Bu bildirim iletisi, kullanıcının seçimini yoksayılıp yoksayılmaması gerektiğini göstermek için önce CBN_CLOSEUP bildirim iletisi gönderilir. CBN_CLOSEUP bildirim iletisi (durumunda bir birleşik giriş kutusu gibi cbs_sımple stiliyle) gönderilmez bile CBN_SELENDCANCEL veya CBN_SELENDOK bildirim iletisi gönderilir.

- ON_CBN_SELENDOK kullanıcı bir öğeyi seçer ve ardından ENTER tuşuna bastığında veya birleşik giriş kutusu liste kutusunun gizlemek için aşağı ok tuşunu tıklar. Bu bildirim iletisi, kullanıcının seçiminin geçerli olarak değerlendirilmesi gerektiğini belirtmek için önce CBN_CLOSEUP ileti gönderilir. CBN_CLOSEUP bildirim iletisi (durumunda bir birleşik giriş kutusu gibi cbs_sımple stiliyle) gönderilmez bile CBN_SELENDCANCEL veya CBN_SELENDOK bildirim iletisi gönderilir.

- Giriş odağını kaybetmekte ON_CBN_KILLFOCUS birleşik giriş kutusu.

- Liste kutusunda tıklayarak veya ok tuşlarını kullanarak seçimi değiştirme kullanıcı sonucunda değiştirilmek üzere ON_CBN_SELCHANGE seçimi birleşik giriş kutusu liste kutusunda var. Bu iletiyi işlerken, birleşik giriş kutusunun düzenleme denetiminde metni yalnızca aracılığıyla alınabilir `GetLBText` ya da benzer başka bir işlev. `GetWindowText` kullanılamaz.

- Birleşik giriş kutusu ON_CBN_SETFOCUS giriş odağı alır.

Oluşturursanız, bir `CComboBox` nesnesi içinde bir iletişim kutusu (iletişim kaynak) aracılığıyla `CComboBox` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.

İsterseniz, bir `CComboBox` başka bir pencere içinde nesne nesnesi, onu yok gerekmez. Oluşturursanız `CComboBox` yığında nesne otomatik olarak bozulur. Oluşturursanız `CComboBox` kullanarak yığında nesne **yeni** işlevini çağırmalıdır **Sil** Windows birleşik giriş kutusu kaldırıldığında yok etmek için nesne üzerinde.

**Not** WM_KEYDOWN ve WM_CHAR iletileri işlemek istiyorsanız, düzenleme ve liste kutusu denetimleri, sınıflarından açılan kutunun alt sınıfı için sahip `CEdit` ve `CListBox`, ve bu iletileri için işleyiciler için türetilmiş sınıfları ekleyin. Daha fazla bilgi için [CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="addstring"></a>  CComboBox::AddString

Bir dizeyi bir birleşik giriş kutusu liste kutusuna ekler.

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*lpszString*<br/>
Eklenecek null ile sonlandırılmış dizeye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri 0'a eşit veya daha büyük ise, liste kutusunda dizeye sıfır tabanlı dizindir. Dönüş değeri CB_ERR ise bir hata oluşur. dönüş değeri CB_ERRSPACE ise yeni bir dize depolamak yeterli alan kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Liste kutusu ile oluşturulmamışsa [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili, dize, listenin sonuna eklenir. Aksi takdirde, dize listesine eklenir ve Liste sıralanmıştır.

> [!NOTE]
>  Bu işlev, Windows tarafından desteklenmiyor `ComboBoxEx` denetimi. Bu denetimi hakkında daha fazla bilgi için bkz. [ComboBoxEx denetimleri](/windows/desktop/Controls/comboboxex-controls) Windows SDK.

Liste içindeki belirli bir konumun bir dize eklemek için kullanın [InsertString](#insertstring) üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

##  <a name="ccombobox"></a>  CComboBox::CComboBox

Oluşturur bir `CComboBox` nesne.

```
CComboBox();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

##  <a name="clear"></a>  CComboBox::Clear

Siler (temizler) varsa, birleşik giriş kutusunun düzenleme denetimindeki geçerli seçimi.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Geçerli seçimi Sil ve Silinen içeriği Pano'ya yerleştir için kullandığınız [Kes](#cut) üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

##  <a name="compareitem"></a>  CComboBox::CompareItem

Bir sıralanmış özelleştirilmiş çizimli birleşik giriş kutusu liste kutusu bölümünde yeni bir öğe göreli konumunu belirlemek için framework tarafından çağırılır.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpCompareItemStruct*<br/>
Uzun bir işaretçi bir [COMPAREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcompareitemstruct) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Açıklanan iki öğenin göreli konumunu belirten `COMPAREITEMSTRUCT` yapısı. Aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-------------|
|- 1|Öğe 1 öğe 2 önce sıralar.|
|0|Öğe 1 ve 2 öğe aynı sıralama.|
|1.|Öğe 1 öğe 2 sonra sıralar.|

Bkz: [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) açıklamasını `COMPAREITEMSTRUCT`.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. LBS_SORT stiliyle bir özelleştirilmiş çizimli birleşik giriş kutusu oluşturursanız, yeni liste kutusuna eklenen öğeleri sıralama yordamlarında framework yardımcı olması için bu üye işlevini geçersiz kılmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

##  <a name="copy"></a>  CComboBox::Copy

Geçerli seçimi, varsa düzenleme denetiminde birleşik giriş kutusunun CF_TEXT biçimde Pano'ya kopyalar.

```
void Copy();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

##  <a name="create"></a>  CComboBox::Create

Birleşik giriş kutusu oluşturur ve ona ekler `CComboBox` nesne.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Birleşik giriş kutusu stilini belirtir. Herhangi bir birleşimini uygulamak [birleşik giriş kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) kutusu.

*Rect*<br/>
Birleşik giriş kutusunun boyutunu ve konumunu işaret eder. Olabilir bir [RECT yapısı](/windows/desktop/api/windef/ns-windef-tagrect) veya `CRect` nesne.

*pParentWnd*<br/>
Açılan kutunun üst penceresine belirtir (genellikle bir `CDialog`). NULL olmamalıdır.

*nID*<br/>
Açılan kutunun denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CComboBox` iki adımda nesne. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, hangi Windows birleşik giriş kutusu oluşturur ve ona ekler `CComboBox` nesne.

Zaman `Create` yürütür, Windows gönderir [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Birleşik giriş kutusundaki iletileri.

Bu iletiler tarafından varsayılan olarak işlenir [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [Ongetminmaxınfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) üye işlevleri içinde `CWnd` temel sınıfı. Varsayılan ileti işleme genişletmek için öğesinden bir sınıf türetin `CComboBox`, yeni sınıfa ileti eşlemesi ekleyin ve önceki ileti işleyicisi üye işlevleri geçersiz kılar. Geçersiz kılma `OnCreate`, örneğin, gerekli başlatma için yeni bir sınıf gerçekleştirmek için.

Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) birleşik giriş kutusu denetimine. :

- WS_CHILD her zaman

- Ws_vısıble genellikle

- Ws_dısabled nadiren

- WS_VSCROLL eklemek için birleşik giriş kutusu liste kutusunda dikey kaydırma

- WS_HSCROLL eklemek için birleşik giriş kutusu liste kutusunda yatay kaydırma

- WS_GROUP grup denetimleri için

- WS_TABSTOP için birleşik giriş kutusu sekme sırasını ekleyin

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

##  <a name="cut"></a>  CComboBox::Cut

Geçerli seçimi birleşik giriş kutusu içindeki düzenlerseniz, denetlemek ve silinen metin Pano'ya kopyalar CF_TEXT biçiminde siler (keser).

```
void Cut();
```

### <a name="remarks"></a>Açıklamalar

Silinen metin Pano'ya yerleştirme olmadan geçerli seçimi silmek için çağrı [Temizle](#clear) üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

##  <a name="deleteitem"></a>  CComboBox::DeleteItem

Kullanıcı bir öğeyi bir özelleştirilmiş çizimli sildiğinde framework tarafından çağırılır `CComboBox` nesne veya birleşik giriş kutusu yok eder.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDeleteItemStruct*<br/>
Bir Windows uzun bir işaretçiye [DELETEITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdeleteitemstruct) olan silinmiş öğenin hakkında bilgi içeren yapısı. Bkz: [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) bu yapı tanımı için.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulama, hiçbir şey yapmaz. Bu işlev birleşik giriş kutusu gerektiği gibi yeniden çizmek için geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

##  <a name="deletestring"></a>  CComboBox::DeleteString

Konumdaki öğeyi siler *nIndex* birleşik giriş kutusundan.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Silinecek dizeye dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri 0'a eşit veya daha büyük ise, ardından listede kalan dizeleri sayısı olan. Dönüş değeri CB_ERR ise *nIndex* listesindeki öğeleri sayısından daha büyük bir dizini belirtir.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tüm öğeleri *nIndex* artık bir pozisyon aşağı taşıyın. Örneğin, bir birleşik giriş kutusu iki öğe içeriyorsa, ilk öğenin silinmesi artık ilk konumda kalan öğeyi neden olur. *nIndex*= 0 öğenin ilk konumu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

##  <a name="dir"></a>  CComboBox::Dir

Dosya adları veya sürücülerin listesini bir birleşik giriş kutusu liste kutusuna ekler.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Parametreler

*attr*<br/>
Herhangi bir birleşimi olabilir **enum** değerleri açıklanan [CFile::GetStatus](../../mfc/reference/cfile-class.md#getstatus) veya herhangi bir birleşimini aşağıdaki değerleri:

- DDL_READWRITE dosya okunamıyor veya yazılamıyor.

- DDL_READONLY dosya okuma ancak yazılan değil.

- DDL_HIDDEN dosya gizlidir ve dizin listesinde görüntülenmez.

- Bir sistem dosyası DDL_SYSTEM dosyasıdır.

- Tarafından belirtilen adı DDL_DIRECTORY *lpszWildCard* bir dizini belirtir.

- DDL_ARCHIVE dosya arşivlendi.

- DDL_DRIVES tarafından belirtilen adla eşleşen tüm sürücüleri dahil *lpszWildCard*.

- DDL_EXCLUSIVE özel bayrak. Özel bayrağı ayarlandıysa, yalnızca belirtilen türde dosyalar listelenir. Aksi takdirde, belirtilen türdeki dosyaları "normal" dosyalarına ek olarak listelenir.

*lpszWildCard*<br/>
Bir dosya belirtimi dize işaret eder. Dize, joker karakterler içerebilir (örneğin, *.\*).

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri 0'a eşit veya daha büyük ise, listeye eklenen son dosya adının sıfır tabanlı dizindir. Dönüş değeri CB_ERR ise bir hata oluşur. dönüş değeri CB_ERRSPACE ise yeni dizeleri depolamak yeterli alan kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows tarafından desteklenmiyor `ComboBoxEx` denetimi. Bu denetimi hakkında daha fazla bilgi için bkz. [ComboBoxEx denetimleri](/windows/desktop/Controls/comboboxex-controls) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

##  <a name="drawitem"></a>  CComboBox::DrawItem

Bir Görselliğin bir özelleştirilmiş çizimli birleşik giriş kutusu değişiklikler olduğunda framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Bir işaretçi bir [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) gerekli çizim türü hakkında bilgi içeren yapısı.

### <a name="remarks"></a>Açıklamalar

`itemAction` Üyesi `DRAWITEMSTRUCT` gerçekleştirilecek çizim eylemi yapısını tanımlar. Bkz: [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) bu yapı tanımı için.

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Sahip çizim için çizim uygulamak için bu üye işlevi geçersiz kılma `CComboBox` nesne. Bu üye işlev sonlandırılmadan önce uygulamanın tüm grafik cihaz arabirimi (GDI) nesneleri görüntüleme bağlamı sağlanan için seçilen kurtarmalısınız *lpDrawItemStruct*.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

##  <a name="findstring"></a>  CComboBox::FindString

Bulur, ancak değil seçin, birleşik giriş kutusu liste kutusunda belirtilen prefix öğesini içerip ilk dize.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>Parametreler

*nStartAfter*<br/>
Aranacak ilk öğeden önce öğenin sıfır tabanlı dizinini içerir. Arama liste kutusunun alt kısmındaki ulaştığında, liste kutusunun üst kısmından geri tarafından belirtilen öğe için devam *nStartAfter*. Tüm liste kutusu,-1, en baştan aranır.

*lpszString*<br/>
Aranacak önek içeren boş sonlandırılmış dizeye işaret eder. Arama çalışması bağımsız olduğundan, bu dizenin herhangi bir bileşimini büyük ve küçük harfler içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri 0'a eşit veya daha büyük ise, eşleşen öğenin sıfır tabanlı dizini var. Arama başarısız olmuşsa CB_ERR var.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows tarafından desteklenmiyor `ComboBoxEx` denetimi. Bu denetimi hakkında daha fazla bilgi için bkz. [ComboBoxEx denetimleri](/windows/desktop/Controls/comboboxex-controls) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

##  <a name="findstringexact"></a>  CComboBox::FindStringExact

Çağrı `FindStringExact` içinde belirtilen dize eşleşen ilk liste kutusu dizedeki (bir birleşik giriş kutusu) üye işlevi *lpszFind*.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Parametreler

*nIndexStart*<br/>
Aranacak ilk öğeden önce öğenin sıfır tabanlı dizinini belirtir. Arama liste kutusunun alt kısmındaki ulaştığında, liste kutusunun üst kısmından geri tarafından belirtilen öğe için devam *nIndexStart*. Varsa *nIndexStart* -1 olan tüm liste kutusu baştan aranır.

*lpszFind*<br/>
Aramak için null ile sonlandırılmış dizeye işaret eder. Bu dize, tam dosya adı uzantısı dahil olmak üzere, içerebilir. Bu dize, herhangi bir bileşimini büyük ve küçük harfler içerebilir. Bu nedenle, arama büyük/küçük harfe duyarlı değil.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen bir öğe veya arama başarısız olmuşsa CB_ERR sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Birleşik giriş kutusu ile bir özelleştirilmiş çizimli stili olmadan oluşturulduysa [cbs_hasstrıngs](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili `FindStringExact` değerini karşı doubleword değer eşleşmeye *lpszFind*.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

##  <a name="getcomboboxinfo"></a>  CComboBox::GetComboBoxInfo

Bilgi için alır `CComboBox` nesne.

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>Parametreler

*pcbi*<br/>
Bir işaretçi [COMBOBOXINFO](/windows/desktop/api/winuser/ns-winuser-tagcomboboxinfo) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi işlevselliğine öykünür [CB_GETCOMBOBOXINFO](/windows/desktop/Controls/cb-getcomboboxinfo) Windows SDK içinde açıklandığı gibi ileti.

##  <a name="getcount"></a>  CComboBox::GetCount

Birleşik giriş kutusu liste kutusu bölümünde öğe sayısını almak için bu üye işlevini çağırın.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısı. Döndürülen sayı değerinden dizinini (sıfır tabanlı dizindir) son öğenin biridir. Bir hata oluşursa CB_ERR var.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

##  <a name="getcuebanner"></a>  CComboBox::GetCueBanner

Birleşik giriş kutusu denetimi için görüntülenen İpucu metni alır.

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpszText*|[out] İşaret başlık metnini alan arabellek için işaretçi.|
|*cchText*|[in] Arabellek boyutu, *lpszText* parametresi işaret eder.|

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yükleme içinde bir [CString](../../atl-mfc-shared/using-cstring.md) varsa; işaret başlık metnini içeren nesne Aksi halde, bir `CString` sıfır uzunlukta bir nesne.

-veya-

İkinci aşırı yükleme, bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

İşaret metni Kombo kutusu denetiminin giriş alanında görüntülenen bir uyarı içindir. Kullanıcı giriş yapana kadar işaret metni görüntülenir.

Bu yöntem gönderir [CB_GETCUEBANNER](/windows/desktop/Controls/cb-getcuebanner) Windows SDK'da açıklanan ileti.

##  <a name="getcursel"></a>  CComboBox::GetCurSel

Birleşik giriş kutusunda hangi öğenin seçilip seçilmediğini belirlemek için bu üye işlevini çağırın.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğeyi liste kutusunda bir birleşik giriş kutusu ya da hiçbir öğe seçili değilse CB_ERR sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

`GetCurSel` bir dizin listesi döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

##  <a name="getdroppedcontrolrect"></a>  CComboBox::GetDroppedControlRect

Çağrı `GetDroppedControlRect` görünür (bırakılan aşağı) liste kutusunun yanıdaki açılan birleşik giriş kutusu ekran koordinatları alınacak üye işlevi.

```
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>Parametreler

*lprect*<br/>
İşaret [RECT yapısı](/windows/desktop/api/windef/ns-windef-tagrect) koordinatlarını almak için olmasıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

##  <a name="getdroppedstate"></a>  CComboBox::GetDroppedState

Çağrı `GetDroppedState` (bırakılan) açılan birleşik giriş kutusu liste kutusunun görünür olup olmadığını belirlemek için üye işlevi.

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusu görünür olduğunda sıfır olmayan; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

##  <a name="getdroppedwidth"></a>  CComboBox::GetDroppedWidth

Minimum izin verilen genişliğini piksel cinsinden birleşik giriş kutusu liste kutusunun almak için bu işlevi çağırın.

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, minimum izin verilen genişliğini piksel cinsinden; Aksi takdirde, CB_ERR.

### <a name="remarks"></a>Açıklamalar

Bu işlev birleşik giriş kutuları ile yalnızca uygulandığı [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.

Varsayılan olarak, aşağı açılan liste kutusunu izin verilen en düşük genişliği 0'dır. İzin verilen en küçük genişliği çağırarak ayarlanabilir [SetDroppedWidth](#setdroppedwidth). Birleşik giriş kutusu liste kutusu kısmı görüntülendiğinde, genişliği izin verilen minimum genişliğini veya birleşik giriş kutusu genişliği büyüktür.

### <a name="example"></a>Örnek

  Örneğin bakın [SetDroppedWidth](#setdroppedwidth).

##  <a name="geteditsel"></a>  CComboBox::GetEditSel

Bir birleşik giriş kutusunun düzenleme denetimindeki geçerli bölüm başlangıç ve bitiş karakter konumlarını alır.

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düşük düzey Word'ün başlangıç konumunu ve nonselected ilk karakterin konumu dwpoint seçiminde sonunda içeren 32 bit bir değer. Bu işlev, bir düzenleme denetimi olmadan bir açılan kutunun kullanılırsa, CB_ERR döndürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

##  <a name="getextendedui"></a>  CComboBox::GetExtendedUI

Çağrı `GetExtendedUI` bir birleşik giriş kutusu varsayılan kullanıcı arabirimi veya genişletilmiş kullanıcı arabirimini olup olmadığını belirlemek için üye işlevi.

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusu genişletilmiş kullanıcı arabirimi yoksa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş kullanıcı arabirimi aşağıdaki yollarla tanımlanabilir:

- Statik denetimi tıklatmak görüntüler liste kutusunu yalnızca Birleşik giriş kutuları ile [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.

- Aşağı Ok tuşuna basarak (F4 devre dışıdır) liste kutusunu görüntüler.

Öğe listesi (anahtarları devre dışı görünür ok) olmadığında statik denetimi kaydırmayı devre dışı bırakıldı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

##  <a name="gethorizontalextent"></a>  CComboBox::GetHorizontalExtent

Birleşik giriş kutusundan, birleşik giriş kutusu liste kutusu kısmı yatay olarak kaydırılabilir piksel cinsinden genişliğini alır.

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırılabilir genişliğini piksel cinsinden birleşik giriş kutusu liste kutusu kısmının.

### <a name="remarks"></a>Açıklamalar

Bu seçenek, yalnızca Birleşik giriş kutusu liste kutusu kısmı bir yatay kaydırma çubuğu varsa geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

##  <a name="getitemdata"></a>  CComboBox::GetItemData

Belirtilen birleşik giriş kutusu öğesi ile ilişkili uygulama tarafından sağlanan 32-bit değeri alır.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Açılan kutunun liste kutusunda bir öğenin sıfır tabanlı dizini içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa öğe veya CB_ERR ile ilişkili 32-bit değeri.

### <a name="remarks"></a>Açıklamalar

32-bit değere ayarlanabilir *dwItemData* parametresinin bir [Setıtemdata](#setitemdata) üye işlev çağrısı. Kullanım `GetItemDataPtr` 32-bit değeri alınacak bir işaretçi ise üye işlevi (**void** <strong>\*</strong>).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

##  <a name="getitemdataptr"></a>  CComboBox::GetItemDataPtr

Bir işaretçi olarak belirtilen birleşik giriş kutusu öğesi ile ilişkilendirilmiş uygulama tarafından sağlanan 32-bit değerini alır (**void** <strong>\*</strong>).

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Açılan kutunun liste kutusunda bir öğenin sıfır tabanlı dizini içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa bir işaretçi veya -1 alır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

##  <a name="getitemheight"></a>  CComboBox::GetItemHeight

Çağrı `GetItemHeight` bir birleşik giriş kutusu liste öğelerini yüksekliğini almak için üye işlevi.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Alınacak olan yüksekliktir birleşik giriş kutusu bileşeni belirtir. Varsa *nIndex* parametresi, -1, birleşik giriş kutusu denetimini düzenleme (veya statik metin) bölümünün yüksekliği alınır. Birleşik giriş kutusu varsa [cbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili *nIndex* olan yüksekliktir alınacak liste öğesinin sıfır tabanlı dizinini belirtir. Aksi takdirde, *nIndex* 0 olarak ayarlanması gerekir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğeyi bir birleşik giriş kutusunda piksel cinsinden yüksekliği. Bir hata oluşursa dönüş CB_ERR değeridir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

##  <a name="getlbtext"></a>  CComboBox::GetLBText

Birleşik giriş kutusu liste kutusundan bir dize alır.

```
int GetLBText(
    int nIndex,
    LPTSTR lpszText) const;

void GetLBText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Kopyalanacak liste kutusu dizesi sıfır tabanlı dizinini içerir.

*lpszText*<br/>
Dizeyi almak için olan bir arabellek işaret eder. Arabellek, dize ve bir sonlandırıcı null karakter için yeterli alan olmalıdır.

*rString*<br/>
Bir başvuru bir `CString`.

### <a name="return-value"></a>Dönüş Değeri

Sondaki null karakter hariç, dizenin uzunluğu (bayt cinsinden). Varsa *nIndex* geçerli bir dizin belirtmiyor CB_ERR dönüş değeridir.

### <a name="remarks"></a>Açıklamalar

İkinci form, bu üye işlev dolgular bir `CString` öğenin metin içeren nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

##  <a name="getlbtextlen"></a>  CComboBox::GetLBTextLen

Birleşik giriş kutusu liste kutusunda bir dizenin uzunluğunu alır.

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Liste kutusu dize sıfır tabanlı dizinini içerir.

### <a name="return-value"></a>Dönüş Değeri

Dize sondaki null karakter hariç bayt cinsinden uzunluğu. Varsa *nIndex* geçerli bir dizin belirtmiyor CB_ERR dönüş değeridir.

### <a name="example"></a>Örnek

  Örneğin bakın [CComboBox::GetLBText](#getlbtext).

##  <a name="getlocale"></a>  CComboBox::GetLocale

Birleşik giriş kutusu tarafından kullanılan yerel ayarları alır.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusundaki dizeleri için yerel ayar tanıtıcısı (LCID) değeri.

### <a name="remarks"></a>Açıklamalar

Yerel ayar, örneğin, bir sıralanmış birleşik giriş kutusu dizeleri sıralama düzeninin belirlemek için kullanılır.

### <a name="example"></a>Örnek

  Örneğin bakın [CComboBox::SetLocale](#setlocale).

##  <a name="getminvisible"></a>  CComboBox::GetMinVisible

Geçerli birleşik giriş kutusu denetimi aşağı açılan listesinde görünen öğeleri en az sayısını alır.

```
int GetMinVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli aşağı açılan listesinde görünen öğeleri en küçük sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [CB_GETMINVISIBLE](/windows/desktop/Controls/cb-setminvisible) Windows SDK'da açıklanan ileti.

##  <a name="gettopindex"></a>  CComboBox::GetTopIndex

Birleşik giriş kutusu liste kutusu bölümünde görünen ilk öğenin sıfır tabanlı dizinini alır.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, birleşik giriş kutusu liste kutusu bölümünde görünen ilk öğenin sıfır tabanlı dizini CB_ERR Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Başlangıçta, liste kutusunun üstünde öğesi 0 olan, ancak liste kutusu kaydırırsanız, başka bir öğe üst kısmında olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

##  <a name="initstorage"></a>  CComboBox::InitStorage

Liste kutusu öğelerini birleşik giriş kutusu liste kutusu bölümünü depolamak için bellek ayırır.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>Parametreler

*nItems*<br/>
Eklenecek öğe sayısını belirtir.

*nBytes*<br/>
Öğesi dizeleri için ayrılacak bayt cinsinden bellek miktarını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı bir bellek reallocation önce birleşik giriş kutusu liste kutusu kısmı depolayan öğelerin maksimum sayı olup olmadığını gerekli, aksi takdirde CB_ERRSPACE, yeterli bellek kullanılabilir olmayan anlamına gelir.

### <a name="remarks"></a>Açıklamalar

Liste kutusu bölümü çok sayıda öğeleri eklemeden önce bu işlevi çağırın `CComboBox`.

Windows 95/98 yalnızca: *WParam* 16 bitlik değerler için parametre sınırlıdır. Başka bir deyişle, liste kutuları 32.767'den fazla öğe içeremez. Öğe sayısını kısıtlı olsa da, bir liste kutusu öğeleri toplam boyutu yalnızca kullanılabilir bellekle sınırlıdır.

Bu işlev, özel olarak çok sayıda (100'den fazla) öğe olan liste kutuları başlatma sürecinin hızlanmasına yardımcı olur. Bu nedenle, sonraki bellek belirtilen miktarı preallocates [AddString](#addstring), [InsertString](#insertstring), ve [Dir](#dir) işlevler en kısa sürede alır. Tahminleri parametrelerini kullanabilirsiniz. Overestimate, bazı ek bellek tahsis edilmez; çoğu kişinin hafife aldığı, normal ayırma ön tahsis miktarınızı aşan öğeleri için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

##  <a name="insertstring"></a>  CComboBox::InsertString

Bir dizeyi bir birleşik giriş kutusu liste kutusuna ekler.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Dize alacak liste kutusunda konumuna sıfır tabanlı dizini içerir. Bu parametreyi -1 ise, dize, listenin sonuna eklenir.

*lpszString*<br/>
Eklenecek olan boş sonlandırılmış dizeye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Hangi dize eklenmiş konumu sıfır tabanlı dizini. Bir hata oluşursa dönüş CB_ERR değeridir. Dönüş değeri CB_ERRSPACE ise yeni bir dize depolamak yeterli alan kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Farklı [AddString](#addstring) üye işlevini `InsertString` üye işlevi bir listesiyle neden olmaz [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) sıralanacak stili.

> [!NOTE]
>  Bu işlev, Windows tarafından desteklenmiyor `ComboBoxEx` denetimi. Bu denetimi hakkında daha fazla bilgi için bkz. [ComboBoxEx denetimleri](/windows/desktop/Controls/comboboxex-controls) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

##  <a name="limittext"></a>  CComboBox::LimitText

Kullanıcı bir birleşik giriş kutusunun düzenleme denetimine girebilirsiniz metnin bayt cinsinden uzunluğunu kısıtlar.

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>Parametreler

*nMaxChars*<br/>
Kullanıcının girebileceği metin uzunluğu (bayt cinsinden) belirtir. Bu parametre 0 ise, metin uzunluğu 65,535 bayt ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı. Birleşik giriş kutusu stiliyle çağrılırsa [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya bir düzenleme denetimi olmadan bir açılan kutunun için CB_ERR değer döndürülür.

### <a name="remarks"></a>Açıklamalar

Birleşik giriş kutusu stili yoksa [CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles), metin sınır düzenleme denetiminin boyutundan daha büyük olacak şekilde ayarlayarak herhangi bir etkisi olacaktır.

`LimitText` Yalnızca kullanıcının girebileceği metin sınırlar. Bunu herhangi bir metin zaten düzenleme denetimine, mesajın gönderilip gönderilmediği ya da liste kutusunda bir dize seçildiğinde düzenleme denetimine kopyalanan metnin uzunluğunu etkilemez etkisi yoktur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

##  <a name="measureitem"></a>  CComboBox::MeasureItem

Sahip çizim stili içeren bir birleşik giriş kutusu oluşturulduğunda framework tarafından çağırılır.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpMeasureItemStruct*<br/>
Uzun bir işaretçi bir [MEASUREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagmeasureitemstruct) yapısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bu üye işlevini geçersiz kılabilir ve doldurun `MEASUREITEMSTRUCT` listede boyutların Windows birleşik giriş kutusunda kutusunda bildirmek için yapısı. Birleşik giriş kutusu ile oluşturulursa [cbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili framework çağıran bu üye işlevi liste kutusunda her bir öğe için. Aksi takdirde, bu üye, yalnızca bir kez çağrılır.

Cbs_ownerdrawfıxed stil bir özelleştirilmiş çizimli birleşik giriş kutusunda kullanılarak oluşturulan ile [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) üye işlevinin `CWnd` başka programlama konuları içerir. İçindeki tartışmalara bakın [Teknik Not 14](../../mfc/tn014-custom-controls.md).

Bkz: [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) açıklamasını `MEASUREITEMSTRUCT` yapısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

##  <a name="paste"></a>  CComboBox::Paste

Verileri birleşik giriş kutusunun geçerli imleç konumundaki düzenleme denetiminin panodan ekler.

```
void Paste();
```

### <a name="remarks"></a>Açıklamalar

Yalnızca Pano CF_TEXT biçiminde veri içeriyorsa, veriler eklenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

##  <a name="resetcontent"></a>  CComboBox::ResetContent

Listeden tüm öğeler kutu ve bir birleşik giriş kutusu denetimi Düzenle kaldırır.

```
void ResetContent();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

##  <a name="selectstring"></a>  CComboBox::SelectString

Birleşik giriş kutusu liste kutusunda bir dizeyi arar ve dize bulunursa, dizeyi liste kutusunda seçer ve düzenleme denetimine kopyalar.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*nStartAfter*<br/>
Aranacak ilk öğeden önce öğenin sıfır tabanlı dizinini içerir. Arama liste kutusunun alt kısmındaki ulaştığında, liste kutusunun üst kısmından geri tarafından belirtilen öğe için devam *nStartAfter*. Tüm liste kutusu,-1, en baştan aranır.

*lpszString*<br/>
Aranacak önek içeren boş sonlandırılmış dizeye işaret eder. Arama çalışması bağımsız olduğundan, bu dizenin herhangi bir bileşimini büyük ve küçük harfler içerebilir.

### <a name="return-value"></a>Dönüş Değeri

Dize bulunursa seçilen öğenin sıfır tabanlı dizini. Arama başarısız olmuşsa CB_ERR dönüş değeridir ve geçerli seçimi değiştirilmez.

### <a name="remarks"></a>Açıklamalar

Yalnızca ön ek dizesini karakterler, ilk karakterleri (başlangıç noktasından) eşleşen bir dize seçilir.

Unutmayın `SelectString` ve `FindString` her iki üye işlevleri, bir dize Bul ancak `SelectString` üye işlevi, dize de seçer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

##  <a name="setcuebanner"></a>  CComboBox::SetCueBanner

Birleşik giriş kutusu denetimi için görüntülenen İpucu metni ayarlar.

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpszText*|[in] İşaret metni içeren null ile sonlandırılmış bir arabellek için işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

İşaret metni Kombo kutusu denetiminin giriş alanında görüntülenen bir uyarı içindir. Kullanıcı giriş yapana kadar işaret metni görüntülenir.

Bu yöntem gönderir [CB_SETCUEBANNER](/windows/desktop/Controls/cb-setcuebanner) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar *m_combobox*, yani Kombo kutusu denetiminin programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, işaret başlığı birleşik giriş kutusu denetimi için ayarlar.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

##  <a name="setcursel"></a>  CComboBox::SetCurSel

Bir dizeyi bir birleşik giriş kutusu liste kutusunda seçer.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Parametreler

*Seçin*<br/>
Dize seçmek için sıfır tabanlı dizini belirtir. -1, liste kutusunda herhangi bir geçerli seçimi kaldırılır ve düzenleme denetiminin temizlenir.

### <a name="return-value"></a>Dönüş Değeri

İletinin başarılı olursa seçilen öğenin sıfır tabanlı dizini. Dönüş değeri CB_ERR ise *Seç Ntümünü* listedeki öğe sayısı değerinden büyükse veya *Seç Ntümünü* seçim temizlenir -1 olarak ayarlanır.

### <a name="remarks"></a>Açıklamalar

(Liste kutusu görünür durumdaysa) gerekiyorsa, liste kutusunda dize görünüme kaydırır. Birleşik giriş kutusunun düzenleme denetiminde metni yeni seçimini yansıtacak şekilde değişir. Liste kutusunda herhangi bir önceki seçim kaldırıldı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

##  <a name="setdroppedwidth"></a>  CComboBox::SetDroppedWidth

Birleşik giriş kutusu liste kutusunun piksel cinsinden minimum izin verilen genişliğini ayarlamak için bu işlevi çağırın.

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
Minimum izin verilen genişliğini piksel cinsinden birleşik giriş kutusu liste kutusu kısmının.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, liste kutusunda, aksi takdirde CB_ERR yeni genişliği.

### <a name="remarks"></a>Açıklamalar

Bu işlev birleşik giriş kutuları ile yalnızca uygulandığı [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.

Varsayılan olarak, aşağı açılan liste kutusunu izin verilen en düşük genişliği 0'dır. Birleşik giriş kutusu liste kutusu kısmı görüntülendiğinde, genişliği izin verilen minimum genişliğini veya birleşik giriş kutusu genişliği büyüktür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

##  <a name="seteditsel"></a>  CComboBox::SetEditSel

Birleşik giriş kutusu düzenleme denetiminde karakterleri seçer.

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>Parametreler

*nStartChar*<br/>
Başlangıç konumu belirtir. Başlangıç konumu -1 olarak ayarlarsanız, ardından varolan herhangi bir seçimi kaldırıldı.

*nEndChar*<br/>
Bitiş konumu belirtir. Bitiş konumu -1, ardından tüm metindeki başlangıç konumu son ayarlanırsa düzenleme denetiminde karakter seçilir.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi başarılı olursa sıfır dışı; Aksi durumda 0. Bunu CB_ERR ise `CComboBox` sahip [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stil veya bir liste kutusu yok.

### <a name="remarks"></a>Açıklamalar

Konumları sıfır tabanlıdır. İlk karakter düzenleme denetimi seçmek için bir başlangıç konumu 0 belirtin. Bitiş konumu seçmek için yalnızca son karakterine için karakterdir. Örneğin, ilk dört karakter düzenleme denetimi seçmek için başlangıç konumu 0 ve 4'ün bitiş konumu kullanırsınız.

> [!NOTE]
>  Bu işlev, Windows tarafından desteklenmiyor `ComboBoxEx` denetimi. Bu denetimi hakkında daha fazla bilgi için bkz. [ComboBoxEx denetimleri](/windows/desktop/Controls/comboboxex-controls) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CComboBox::GetEditSel](#geteditsel).

##  <a name="setextendedui"></a>  CComboBox::SetExtendedUI

Çağrı `SetExtendedUI` üye işlevini varsayılan kullanıcı arabirimi veya içeren bir birleşik giriş kutusu için genişletilmiş kullanıcı arabirimini seçmek için [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>Parametreler

*bMicrosoft*<br/>
Birleşik giriş kutusu genişletilmiş kullanıcı arabirimi veya varsayılan kullanıcı arabirimini kullanıp kullanmayacağını belirtir. DOĞRU değeri, genişletilmiş kullanıcı arabirimini seçer; FALSE değeri, standart kullanıcı arabirimi seçer.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa CB_OKAY veya bir hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş kullanıcı arabirimi aşağıdaki yollarla tanımlanabilir:

- Statik denetim tıklandığında liste kutusunu yalnızca Birleşik giriş kutuları cbs_dropdownlıst stiliyle görüntüler.

- Aşağı Ok tuşuna basarak (F4 devre dışıdır) liste kutusunu görüntüler.

Statik denetimi kaydırmayı devre dışı öğe listesinde görünmediğinde (ok tuşlarını devre dışı bırakılır).

### <a name="example"></a>Örnek

  Örneğin bakın [CComboBox::GetExtendedUI](#getextendedui).

##  <a name="sethorizontalextent"></a>  CComboBox::SetHorizontalExtent

Genişlik, birleşik giriş kutusu liste kutusu kısmı yatay olarak kaydırılabilir piksel cinsinden ayarlar.

```
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>Parametreler

*nExtent*<br/>
Birleşik giriş kutusu liste kutusu kısmı yatay olarak kaydırılabilir piksel sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Liste kutusunun genişliğini bu değerden daha küçükse, yatay kaydırma çubuğu öğeleri liste kutusunda yatay kaydırma. Yatay kaydırma çubuğunun genişliğini liste kutusunun eşit veya bu değerden daha büyük ise, gizli veya birleşik giriş kutusu varsa [cbs_dısablenoscroll](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili, devre dışı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

##  <a name="setitemdata"></a>  CComboBox::SetItemData

Belirtilen öğeyi bir birleşik giriş kutusunda ile ilişkili 32-bit değeri ayarlar.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Ayarlanacak öğenin sıfır tabanlı bir dizini içerir.

*dwItemData*<br/>
Öğeyle ilişkilendirilecek yeni değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Kullanım `SetItemDataPtr` 32-bit öğesi işaretçisi olması durumunda üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

##  <a name="setitemdataptr"></a>  CComboBox::SetItemDataPtr

Belirtilen öğe belirtilen işaretçisi olacak şekilde bir birleşik giriş kutusunda ile ilişkili 32-bit değeri ayarlar (**void** <strong>\*</strong>).

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Öğenin sıfır tabanlı bir dizini içerir.

*pData*<br/>
Öğeyle ilişkilendirilecek işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Birleşik giriş kutusu içindeki öğenin göreli konumu gibi öğeleri eklendiğinde veya kaldırıldığında değişebilir olsa bile bu işaretçinin birleşik giriş kutusu süresince geçerli kalır. Bu nedenle, kutunun içinde öğenin dizini değiştirebilirsiniz, ancak işaretçi güvenilir kalır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

##  <a name="setitemheight"></a>  CComboBox::SetItemHeight

Çağrı `SetItemHeight` liste öğelerini yüksekliğini bir birleşik giriş kutusu veya bir birleşik giriş kutusu denetimini düzenleme (veya statik metin) bölümünün yüksekliği ayarlamak için üye işlevi.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Liste öğeleri yüksekliğini veya birleşik giriş kutusu denetimini düzenleme (veya statik metin) bölümünün yüksekliği ayarlanmış olup olmadığını belirtir.

Birleşik giriş kutusu varsa [cbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili *nIndex* olan yüksekliktir Ayarla; Aksi takdirde liste öğesinin sıfır tabanlı dizinini belirtir *nIndex* 0 olmalıdır ve tüm liste öğelerinin yüksekliği ayarlayın.

Varsa *nIndex* -1, düzenleme denetiminin yüksekliğini veya birleşik giriş kutusu statik metin bölümü ayarlanacak.

*cyItemHeight*<br/>
Tarafından tanımlanan birleşik giriş kutusu bileşeninin piksel cinsinden yüksekliğini belirtir *nIndex*.

### <a name="return-value"></a>Dönüş Değeri

Dizin veya yüksekliği geçersizse CB_ERR; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Düzenleme denetimi (veya statik metin) bölümü açılan kutunun yüksekliği, liste öğelerini yüksekliğini bağımsız olarak ayarlanır. Bir uygulamayı düzenleme denetimi (veya statik metin) bölümü yüksekliğini belirli bir liste kutusu öğe yüksekliğini küçük değil emin olmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

##  <a name="setlocale"></a>  CComboBox::SetLocale

Bu birleşik giriş kutusu yerel ayar tanımlayıcısı ayarlar.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Parametreler

*nNewLocale*<br/>
Açılan kutu için ayarlanacak yeni yerel ayar tanıtıcısı (LCID) değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu birleşik giriş kutusunun önceki yerel ayar tanıtıcısı (LCID) değeri.

### <a name="remarks"></a>Açıklamalar

Varsa `SetLocale` çağrılmaz; varsayılan yerel ayar sistemden elde edilir. Denetim Masası ndaki kullanarak bu sistem varsayılan yerel ayar değiştirilebilir bölge (veya uluslararası) uygulama.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

##  <a name="setminvisibleitems"></a>  CComboBox::SetMinVisibleItems

En az sayıda görünen öğeler geçerli birleşik açılır listesi kutusu denetimi ayarlar.

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iMinVisible*|[in] Görünen öğeleri en az sayısını belirtir.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [CB_SETMINVISIBLE](/windows/desktop/Controls/cb-setminvisible) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar *m_combobox*, yani Kombo kutusu denetiminin programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, 20 öğe bir birleşik giriş kutusu denetimi aşağı açılan listesine ekler. Ardından 10 öğe en az bir kullanıcı, açılan liste okunu bastığında görüntülendiğini belirtir.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

##  <a name="settopindex"></a>  CComboBox::SetTopIndex

Belirli bir öğe birleşik giriş kutusu liste kutusu bölümünde görünür olmasını sağlar.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Liste kutusu öğesinin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır veya bir hata oluşursa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Sistem tarafından belirtilen öğe kadar liste kutusu kaydırır *nIndex* görünür listenin en üstünde kutusu veya en fazla kaydırma aralığı ulaşıldı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

##  <a name="showdropdown"></a>  CComboBox::ShowDropDown

Gösterir veya gizler içeren bir birleşik giriş kutusu liste kutusunda [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.

```
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>Parametreler

*bShowIt*<br/>
Aşağı açılan liste kutusunda gösterilen veya gizli olup olmadığını belirtir. Liste kutusunda TRUE değerini gösterir. FALSE değeri liste kutusu gizler.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu stilin bir birleşik giriş kutusu liste kutusunun gösterir.

Bu üye işlevi ile oluşturulan bir birleşik giriş kutusu üzerinde hiçbir etkisi olmaz [cbs_sımple](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.

### <a name="example"></a>Örnek

  Örneğin bakın [CComboBox::GetDroppedState](#getdroppedstate).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CButton Sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar Sınıfı](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic Sınıfı](../../mfc/reference/cstatic-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
