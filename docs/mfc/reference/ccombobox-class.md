---
title: "CComboBox sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6a8b9c9de69f9042f68cc04d435070ade9b24dd9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccombobox-class"></a>CComboBox sınıfı
Bir Windows birleşik giriş kutusu işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CComboBox : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComboBox::CComboBox](#ccombobox)|Oluşturan bir `CComboBox` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComboBox::AddString](#addstring)|Birleşik giriş kutusu veya liste kutuları ile için sıralanmış konumunda liste kutusunda listesinin sonuna bir dize ekler **CBS_SORT** stili.|  
|[CComboBox::Clear](#clear)|(Temizler) siler varsa düzenleme denetimindeki geçerli seçim.|  
|[CComboBox::CompareItem](#compareitem)|Sıralanmış sahip tarafından çizilmiş açılan kutuya yeni bir liste öğesi göreli konumunu belirlemek için çerçevesi tarafından çağrılır.|  
|[CComboBox::Copy](#copy)|Geçerli seçim Pano'ya varsa kopyalar **CF_TEXT** biçimi.|  
|[CComboBox::Create](#create)|Birleşik giriş kutusu oluşturur ve ona ekler `CComboBox` nesnesi.|  
|[CComboBox::Cut](#cut)|(Keser) siler düzenleme herhangi denetlemek ve silinen metni panoya üzerine kopyalar geçerli seçim **CF_TEXT** biçimi.|  
|[CComboBox::DeleteItem](#deleteitem)|Sahip tarafından çizilmiş açılan kutudan bir liste öğesi silindiğinde çerçevesi tarafından çağrılır.|  
|[CComboBox::DeleteString](#deletestring)|Bir dizeyi bir birleşik giriş kutusu liste kutusundan siler.|  
|[CComboBox::Dir](#dir)|Dosya adları listesini açılan kutu listesi kutusuna ekler.|  
|[CComboBox::DrawItem](#drawitem)|Sahip tarafından çizilmiş birleşik giriş kutusu değişiklikler visual yönünü zaman çerçevesi tarafından çağrılır.|  
|[CComboBox::FindString](#findstring)|Birleşik giriş kutusu liste kutusunda belirtilen bir önek içeren ilk dizeyi bulur.|  
|[CComboBox::FindStringExact](#findstringexact)|Belirtilen dize eşleşen ilk liste kutusu dizesinde (birleşik giriş kutusu) bulur.|  
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Hakkında bilgi alır `CComboBox` nesnesi.|  
|[CComboBox::GetCount](#getcount)|Birleşik giriş kutusu liste kutusunda öğe sayısını alır.|  
|[CComboBox::GetCueBanner](#getcuebanner)|Birleşik giriş kutusu denetimi için görüntülenen işaret metni alır.|  
|[CComboBox::GetCurSel](#getcursel)|Birleşik giriş kutusu liste kutusunda seçili öğenin dizinini alır|  
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Ekran koordinatları açılan kutusu görünür (aşağı bırakılan) liste kutusu alır.|  
|[CComboBox::GetDroppedState](#getdroppedstate)|(Bırakılan) açılan kutusunun liste kutusunda görünür olup olmadığını belirler.|  
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Birleşik giriş kutusu açılan liste kutusu kısmı için genişliği izin verilen en düşük alır.|  
|[CComboBox::GetEditSel](#geteditsel)|Birleşik giriş kutusu düzenleme denetimindeki geçerli bölüm başlangıç ve bitiş karakteri konumlarını alır.|  
|[CComboBox::GetExtendedUI](#getextendedui)|Birleşik giriş kutusu varsayılan kullanıcı arabirimi veya genişletilmiş kullanıcı arabirimi olup olmadığını belirler.|  
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Birleşik giriş kutusu liste kutusu kısmı yatay kaydırılabileceğini piksel cinsinden genişliği döndürür.|  
|[CComboBox::GetItemData](#getitemdata)|Belirtilen birleşik giriş kutusu öğeyle ilişkili uygulama tarafından sağlanan 32-bit değeri alır.|  
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Belirtilen birleşik giriş kutusu öğesiyle ilişkili uygulama tarafından sağlanan 32-bit işaretçi alır.|  
|[CComboBox::GetItemHeight](#getitemheight)|Birleşik giriş kutusu bulunan liste öğelerini yüksekliğini alır.|  
|[CComboBox::GetLBText](#getlbtext)|Birleşik giriş kutusu liste kutusundan bir dize alır.|  
|[CComboBox::GetLBTextLen](#getlbtextlen)|Birleşik giriş kutusu liste kutusunda bir dizenin uzunluğunu alır.|  
|[CComboBox::GetLocale](#getlocale)|Birleşik giriş kutusu için yerel ayar tanıtıcısını alır.|  
|[CComboBox::GetMinVisible](#getminvisible)|Geçerli birleşik giriş kutusu aşağı açılan listesinde en az görünür öğe sayısını alır.|  
|[CComboBox::GetTopIndex](#gettopindex)|Görünen ilk öğenin dizinini birleşik giriş kutusu liste kutusu kısmını döndürür.|  
|[CComboBox::InitStorage](#initstorage)|Öğeleri ve birleşik giriş kutusu liste kutusu kısmının dizeleri için bellek bloklarını preallocates.|  
|[CComboBox::InsertString](#insertstring)|Birleşik giriş kutusu liste kutusuna bir dize ekler.|  
|[CComboBox::LimitText](#limittext)|Kullanıcı bir birleşik giriş kutusu düzenleme denetimine girebilir metnin uzunluğunu sınırlar.|  
|[CComboBox::MeasureItem](#measureitem)|Sahip tarafından çizilmiş birleşik giriş kutusu oluşturulduğunda birleşik giriş kutusu boyutları belirlemek için çerçevesi tarafından çağrılır.|  
|[CComboBox::Paste](#paste)|Verileri düzenleme denetimi geçerli imleç konumundaki panodan ekler. Verileri yalnızca Pano veri içeriyorsa eklenir **CF_TEXT** biçimi.|  
|[CComboBox::ResetContent](#resetcontent)|Listeden tüm öğeler kutu ve bir birleşik giriş kutusu denetimi Düzenle kaldırır.|  
|[CComboBox::SelectString](#selectstring)|Birleşik giriş kutusu liste kutusunda bir dizeyi arar ve dize bulunursa, liste kutusunda dize seçer ve dize Düzenle denetime kopyalar.|  
|[CComboBox::SetCueBanner](#setcuebanner)|Birleşik giriş kutusu denetimi için görüntülenen işaret metni ayarlar.|  
|[CComboBox::SetCurSel](#setcursel)|Bir dizeyi bir birleşik giriş kutusu liste kutusunda seçer.|  
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Birleşik giriş kutusu açılan liste kutusu kısmı için genişliği izin verilen en düşük ayarlar.|  
|[CComboBox::SetEditSel](#seteditsel)|Karakterleri birleşik giriş kutusu düzenleme denetimine seçer.|  
|[CComboBox::SetExtendedUI](#setextendedui)|Varsayılan kullanıcı arabirimi veya sahip bir birleşik giriş kutusu için genişletilmiş kullanıcı arabirimi seçer **CBS_DROPDOWN** veya **cbs_dropdownlıst** stili.|  
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Birleşik giriş kutusu liste kutusu kısmı yatay kaydırılabileceğini piksel cinsinden genişliğini belirler.|  
|[CComboBox::SetItemData](#setitemdata)|Belirtilen öğe bir açılan kutuda ilişkili 32-bit değerini ayarlar.|  
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Belirtilen öğe bir açılan kutuda ilişkili 32-bit işaretçi ayarlar.|  
|[CComboBox::SetItemHeight](#setitemheight)|Liste öğeleri yüksekliğini birleşik giriş kutusu veya açılan kutu düzenleme denetimi (veya statik metin) bölümünü yüksekliğini ayarlar.|  
|[CComboBox::SetLocale](#setlocale)|Birleşik giriş kutusu için yerel ayar kimliğini ayarlar.|  
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Geçerli birleşik giriş kutusu aşağı açılan listesinde en az görünür öğe sayısını ayarlar.|  
|[CComboBox::SetTopIndex](#settopindex)|Belirtilen dizinle öğeyi en üstünde görüntülenecek birleşik giriş kutusu liste kutusu kısmı söyler.|  
|[CComboBox::ShowDropDown](#showdropdown)|Gösterir veya gizler sahip bir birleşik giriş kutusu liste kutusunda **CBS_DROPDOWN** veya **cbs_dropdownlıst** stili.|  
  
## <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu statik denetimi veya düzenleme denetimi ile birleştirilmiş bir liste kutusu oluşur. Liste kutusu denetiminin bir kısmına her zaman görüntülenebilir veya kullanıcı denetimi yanındaki açılan oka seçtiğinde yalnızca açılan.  
  
 Liste kutusunda seçili öğenin (varsa) veya düzen denetimi statik görüntülenir. Ayrıca, birleşik giriş kutusu açılan liste stilini varsa, kullanıcı listedeki öğelerden birini ilk karakteri yazın ve liste kutusu görünüyorsa, bu ilk karakteri ile sonraki öğe vurgular.  
  
 Aşağıdaki tabloda, üç birleşik giriş kutusu karşılaştırılmaktadır [stilleri](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles).  
  
|Stil|Liste kutusu görünür olduğunda olmadığı|Statik veya düzenleme denetimi|  
|-----------|-------------------------------|-----------------------------|  
|Basit|Her zaman|Düzenle|  
|Aşağı açılır|Bırakılan olduğunda|Düzenle|  
|Aşağı açılan liste|Bırakılan olduğunda|Statik|  
  
 Oluşturabileceğiniz bir `CComboBox` nesne iletişim kutusu şablondan ya da doğrudan kodunuzu. Her iki durumda da ilk Oluşturucusu çağrısı `CComboBox` oluşturmak için `CComboBox` nesne; ardından çağıran [oluşturma](#create) denetimi oluşturmak ve ona eklemek için üye işlevi `CComboBox` nesne.  
  
 Birleşik giriş kutusu tarafından kendi üst gönderilen Windows bildirim iletilerini işlemek istiyorsanız (öğesinden türetilmiş bir sınıf genellikle `CDialog`), her ileti için üst sınıfı için ileti eşleme girişi ve ileti işleyicisi üye işlevi ekleme.  
  
 Her ileti eşleme girişi aşağıdaki biçimdedir:  
  
 **ON_**bildirim **(**`id`**,**`memberFxn`**)**  
  
 Burada `id` bildirim göndererek birleşik giriş kutusu denetimi alt pencere Kimliğini belirtir ve `memberFxn` bildirimini işlemek için yazılmış üst üye işlevi adıdır.  
  
 Üst öğenin işlev prototipi aşağıdaki gibidir:  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 Belirli bildirim gönderilir sipariş tahmin edilemez. Özellikle, bir **CBN_SELCHANGE** önce veya sonra bildirim oluşabilir bir **CBN_CLOSEUP** bildirim.  
  
 Potansiyel ileti eşleme girdiler şunlardır:  
  
- **ON_CBN_CLOSEUP** (Windows 3.1 ve üzeri.) Birleşik giriş kutusu liste kutusunda kapattı. Bu bildirim iletisi içeren bir birleşik giriş kutusu gönderilmez [cbs_sımple](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.  
  
- **ON_CBN_DBLCLK** kullanıcı çift tıklamalar birleşik giriş kutusu liste kutusunda bir dize. Bu bildirim iletisi içeren bir birleşik giriş kutusu için yalnızca gönderilir **cbs_sımple** stili. Birleşik giriş kutusu ile [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) liste kutusu tek tıklatmayla gizler olduğundan, bir çift gerçekleşemez stili.  
  
- **ON_CBN_DROPDOWN** hakkında aşağı açılan kutu liste kutusunda olduğundan (yapılan görünür). Bu bildirim iletisi içeren bir birleşik giriş kutusu için yalnızca oluşabilir **CBS_DROPDOWN** veya **cbs_dropdownlıst** stili.  
  
- **ON_CBN_EDITCHANGE** kullanıcı birleşik giriş kutusu düzenleme denetimi kısmı metinde değiştirmiş bir eylem sürdü. Farklı **CBN_EDITUPDATE** ileti, bu iletiyi Windows ekran güncelleştirildikten sonra gönderilir. Birleşik giriş kutusu varsa gönderilmez **cbs_dropdownlıst** stili.  
  
- **ON_CBN_EDITUPDATE** düzenleme denetimi birleşik giriş kutusu hakkında değiştirilen metni görüntülemek için bölümüdür. Bu bildirim iletisi denetimi biçimlendirilmiş metin sonra ancak metin görüntülemeden önce gönderilir. Birleşik giriş kutusu varsa gönderilmez **cbs_dropdownlıst** stili.  
  
- **ON_CBN_ERRSPACE** birleşik giriş kutusu belirli bir isteği karşılamak için yeterli bellek ayrılamıyor.  
  
- **ON_CBN_SELENDCANCEL** (Windows 3.1 ve üzeri.) Kullanıcının seçimini iptal gösterir. Kullanıcı bir öğeyi tıklattığında ve başka bir pencere veya birleşik giriş kutusu liste kutusunda gizlemek için Denetim tıklar. Bu bildirim iletisi önce gönderilen **CBN_CLOSEUP** kullanıcının seçimini yoksayılmalıdır göstermek için bildirim iletisi. **CBN_SELENDCANCEL** veya **CBN_SELENDOK** bildirim iletisi gönderilir olsa bile **CBN_CLOSEUP** bildirim iletisini gönderilmez (gibi bir birleşik giriş kutusu söz konusu olduğunda **Cbs_sımple** stili).  
  
- **ON_CBN_SELENDOK** kullanıcı bir öğeyi seçer ve ardından ENTER tuşuna bastığında veya birleşik giriş kutusu liste kutusunda gizlemek için aşağı ok tuşunu tıklar. Bu bildirim iletisi önce gönderilen **CBN_CLOSEUP** kullanıcının seçimini geçerli değerlendirilmesi gerektiğini belirtmek için ileti. **CBN_SELENDCANCEL** veya **CBN_SELENDOK** bildirim iletisi gönderilir olsa bile **CBN_CLOSEUP** bildirim iletisini gönderilmez (gibi bir birleşik giriş kutusu söz konusu olduğunda **Cbs_sımple** stili).  
  
- **ON_CBN_KILLFOCUS** birleşik giriş kutusu giriş odağını kaybetme.  
  
- **ON_CBN_SELCHANGE** liste kutusunda tıklayarak veya ok tuşlarını kullanarak seçimi değiştirme kullanıcı sonucunda değiştirilmek üzere birleşik giriş kutusu liste kutusunda seçim değildir. Bu iletiyi işlerken açılan kutunun düzenleme denetimindeki metin yalnızca aracılığıyla alınabilir `GetLBText` veya başka bir benzer işlevi. `GetWindowText`kullanılamaz.  
  
- **ON_CBN_SETFOCUS** birleşik giriş kutusu giriş odağını alır.  
  
 Oluşturursanız, bir `CComboBox` nesnesi (aracılığıyla bir iletişim kutusu kaynağı), bir iletişim kutusu içinde `CComboBox` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.  
  
 Katıştırılmış içerirse bir `CComboBox` nesnesi içinde başka bir pencere nesnesi, onu destroy gerekmez. Oluşturursanız, `CComboBox` nesne yığında otomatik olarak yok. Oluşturursanız, `CComboBox` nesnesi kullanarak yığında **yeni** işlevini çağırmanız gerekir **silmek** Windows birleşik giriş kutusu bozulduğunda yok etmek için nesne üzerinde.  
  
 **Not** işlemek istiyorsanız `WM_KEYDOWN` ve `WM_CHAR` iletileri, sahip olduğunuz bir alt kümesi için düzenleme ve liste kutusu denetimleri, sınıflarından açılan kutunun `CEdit` ve `CListBox`, ve bu iletileri için işleyiciler türetilmiş ekleyin sınıflar. Daha fazla bilgi için bkz: [http://support.microsoft.com/default.aspxscid=kb;en-us; Q174667](http://support.microsoft.com/default.aspxscid=kb;en-us;q174667) ve [CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="addstring"></a>CComboBox::AddString  
 Birleşik giriş kutusu liste kutusu için bir dize ekler.  
  
```  
int AddString(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszString`  
 Eklenecek null ile sonlandırılmış dizeye noktaları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri sıfırdan büyük veya 0 değerine eşit ise, liste kutusunda dize sıfır tabanlı dizini.. Dönüş değeri **CB_ERR** bir hata oluşursa; dönüş değeri olan **CB_ERRSPACE** yeni bir dize depolamak yeterli alan olup olmadığını.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu ile oluşturulmamışsa [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili, dize listesinin sonuna eklenir. Aksi takdirde dize listesine eklenir ve liste sıralanır.  
  
> [!NOTE]
>  Bu işlev Windows tarafından desteklenmiyor **ComboBoxEx** denetim. Bu denetimi hakkında daha fazla bilgi için bkz: [ComboBoxEx denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb775738) Windows SDK.  
  
 Belirli bir konuma listesi içindeki bir dize eklemek için kullanın [InsertString](#insertstring) üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]  
  
##  <a name="ccombobox"></a>CComboBox::CComboBox  
 Oluşturan bir `CComboBox` nesnesi.  
  
```  
CComboBox();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]  
  
##  <a name="clear"></a>CComboBox::Clear  
 (Temizler) siler varsa açılan kutunun düzenleme denetimindeki geçerli seçim.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli seçimi silin ve Pano'ya silinen içeriği yerleştirmek için kullanmak [Kes](#cut) üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]  
  
##  <a name="compareitem"></a>CComboBox::CompareItem  
 Yeni bir öğe bir sıralanmış sahibi tarafından çizilen birleşik giriş kutusu liste kutusu kısmının göreli konumunu belirlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpCompareItemStruct`  
 Uzun bir işaretçi bir [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açıklanan iki öğe göreli konumunu gösterir `COMPAREITEMSTRUCT` yapısı. Aşağıdaki değerlerden herhangi birini olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|- 1|Madde 1, 2 öğesi önce sıralar.|  
|0|Madde 1 ve 2 öğesi aynı sıralayın.|  
|1.|Madde 1, 2 öğesinden sonra sıralar.|  
  
 Bkz: [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) bir açıklaması için `COMPAREITEMSTRUCT`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bir sahip çizim birleşik giriş kutusu oluşturursanız **LBS_SORT** stili, yeni liste kutusu eklenen öğeleri sıralama framework yardımcı olması için bu üye işlevi geçersiz kılması gerekir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]  
  
##  <a name="copy"></a>CComboBox::Copy  
 Varsa Pano'ya birleşik giriş kutusu düzenleme denetimindeki geçerli seçimi kopyalar **CF_TEXT** biçimi.  
  
```  
void Copy();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]  
  
##  <a name="create"></a>CComboBox::Create  
 Birleşik giriş kutusu oluşturur ve ona ekler `CComboBox` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Birleşik giriş kutusu stilini belirtir. Herhangi bir bileşimini uygulamak [birleşik giriş kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) kutusuna.  
  
 `rect`  
 Birleşik giriş kutusu boyutunu ve konumunu işaret. Olabilir bir [RECT yapısı](../../mfc/reference/rect-structure1.md) veya `CRect` nesnesi.  
  
 `pParentWnd`  
 Açılan kutunun üst pencere belirtir (genellikle bir `CDialog`). Değil olmalıdır **NULL**.  
  
 `nID`  
 Açılan kutunun denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CComboBox` iki adımda nesne. İlk olarak, Oluşturucusu arayın ve ardından arama **oluşturma**, hangi Windows birleşik giriş kutusu oluşturur ve ona ekler `CComboBox` nesnesi.  
  
 Zaman **oluşturma** yürütür, Windows gönderir [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [WM_ GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) birleşik giriş kutusu iletileri.  
  
 Bu iletiler, varsayılan olarak tarafından işlenen [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [Ongetminmaxınfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) üye işlevleri içinde `CWnd` temel sınıfı. Varsayılan ileti işleme genişletmek için öğesinden bir sınıf türetin `CComboBox`ileti eşlemesi için yeni sınıf ekleyin ve önceki ileti işleyicisi üye işlevlerini geçersiz kılma. Geçersiz kılma `OnCreate`, örneğin, gerekli başlatma için yeni bir sınıf gerçekleştirmek için.  
  
 Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) birleşik giriş kutusu denetimine. :  
  
- **WS_CHILD** her zaman  
  
- **Ws_vısıble** genellikle  
  
- **Ws_dısabled** nadiren  
  
- **WS_VSCROLL** birleşik giriş kutusu liste kutusunda dikey kaydırma eklemek için  
  
- **WS_HSCROLL** birleşik giriş kutusu liste kutusunda yatay kaydırma eklemek için  
  
- **WS_GROUP** grup denetimleri için  
  
- **WS_TABSTOP** sekme sırasını birleşik giriş kutusu eklemek için  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]  
  
##  <a name="cut"></a>CComboBox::Cut  
 Siler (keser) geçerli seçim içindeki bir birleşik giriş kutusu düzenlerseniz, denetlemek ve silinen metni panoya üzerine kopyalar **CF_TEXT** biçimi.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli seçim silinen metni Pano'ya koymadan silmek için arama [Temizle](#clear) üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]  
  
##  <a name="deleteitem"></a>CComboBox::DeleteItem  
 Kullanıcı bir öğeyi sahibi çizim sildiğinde çerçevesi tarafından çağrılır `CComboBox` nesne veya birleşik giriş kutusu yok eder.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDeleteItemStruct`  
 Windows için uzun bir işaretçi [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) silinmiş öğeyi hakkında bilgi içeren yapısı. Bkz: [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) bu yapı açıklaması.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması hiçbir şey yapmaz. Birleşik giriş kutusu gerektiği gibi yeniden çizmek için bu işlevi geçersiz kılar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]  
  
##  <a name="deletestring"></a>CComboBox::DeleteString  
 Konum öğesinde siler `nIndex` açılan kutusundan.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Silinecek dizeye dizinini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri sıfırdan büyük veya 0 değerine eşit ise, ardından bunu bir listede kalan dizeleri sayısıdır. Dönüş değeri **CB_ERR** varsa `nIndex` öğe sayısından daha büyük bir dizin listesindeki belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İzleyen tüm öğeleri `nIndex` şimdi bir konum aşağı taşıma. Örneğin, bir birleşik giriş kutusu iki öğeler içeriyorsa, ilk öğe silinmesi şimdi ilk konumda kalan öğeyi neden olur. `nIndex`ilk konumda öğesi için 0 =.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]  
  
##  <a name="dir"></a>CComboBox::Dir  
 Dosya adları veya sürücüler listesini açılan kutu listesi kutusuna ekler.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Parametreler  
 `attr`  
 Herhangi bir bileşimi olabilir `enum` değerleri açıklanan [CFile::GetStatus](../../mfc/reference/cfile-class.md#getstatus) veya herhangi bir birleşimini aşağıdaki değerlerden biri:  
  
- **DDL_READWRITE** dosyası okunamıyor veya yazılamıyor.  
  
- **DDL_READONLY** dosyayı okuyabilir, ancak yazılabilir değil.  
  
- **DDL_HIDDEN** dosya gizlidir ve dizin listesinde görüntülenmez.  
  
- **DDL_SYSTEM** bir sistem dosyası bir dosyadır.  
  
- **DDL_DIRECTORY** tarafından belirtilen adını `lpszWildCard` bir dizini belirtir.  
  
- **DDL_ARCHIVE** dosya arşivlenir.  
  
- **DDL_DRIVES** tarafından belirtilen adla eşleşen tüm sürücüler dahil `lpszWildCard`.  
  
- **DDL_EXCLUSIVE** özel bayrağı. Özel bayrağı ayarlarsanız, yalnızca belirtilen türde dosyalar listelenir. Aksi halde, belirtilen türdeki dosyaları "normal" dosyalarına ek olarak listelenir.  
  
 `lpszWildCard`  
 Bir dosya belirtimi dize noktalarına. Dize, joker karakter içerebilir (örneğin, *.\*).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri sıfırdan büyük veya 0 değerine eşit ise, listeye eklenen son filename sıfır tabanlı dizini.. Dönüş değeri **CB_ERR** bir hata oluşursa; dönüş değeri olan **CB_ERRSPACE** yeni dize depolamak yeterli alan olup olmadığını.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev Windows tarafından desteklenmiyor **ComboBoxEx** denetim. Bu denetimi hakkında daha fazla bilgi için bkz: [ComboBoxEx denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb775738) Windows SDK.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]  
  
##  <a name="drawitem"></a>CComboBox::DrawItem  
 Bir sahip çizim birleşik giriş kutusu değişiklikler visual yönünü zaman çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDrawItemStruct`  
 Bir işaretçi bir [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) gerekli çizim türü hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 **İtemAction** üyesi `DRAWITEMSTRUCT` yapısı gerçekleştirilecek çizim eylemi tanımlar. Bkz: [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) bu yapı açıklaması.  
  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Çizim sahibi çizim için uygulamak için bu üye işlevi geçersiz kılma `CComboBox` nesnesi. Bu üye işlevi sona erdirmeden önce uygulamanın tüm grafik cihaz arabirimi (GDI) nesneleri görüntüleme bağlamı içinde sağlanan için seçilen kurtarmalısınız `lpDrawItemStruct`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]  
  
##  <a name="findstring"></a>CComboBox::FindString  
 Bulur ancak değil seçin, açılan kutunun liste kutusunda belirtilen bir önek içeren ilk dizesi.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszString) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nStartAfter`  
 Aranacak ilk öğeden önce öğenin sıfır tabanlı dizini içerir. Arama listesi kutusunun alt kısmındaki ulaştığında, liste kutusunu üstten geri tarafından belirtilen öğeye devam `nStartAfter`. -1, tüm liste kutusunu baştan aranır.  
  
 `lpszString`  
 Aranacak önek içeren null ile sonlandırılmış dize noktalarına. Arama durumu bağımsız olduğundan, bu dizeyi herhangi bir bileşimini büyük ve küçük harfleri içerebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri sıfırdan büyük veya 0 değerine eşit ise, eşleşen öğenin sıfır tabanlı dizini.. Bu **CB_ERR** arama başarısız olmuşsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev Windows tarafından desteklenmiyor **ComboBoxEx** denetim. Bu denetimi hakkında daha fazla bilgi için bkz: [ComboBoxEx denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb775738) Windows SDK.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]  
  
##  <a name="findstringexact"></a>CComboBox::FindStringExact  
 Çağrı `FindStringExact` içinde belirtilen dize eşleşen ilk liste kutusu dizesinde (birleşik giriş kutusu) bulmak için üye işlevi `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndexStart`  
 Aranacak ilk öğeden önce öğenin sıfır tabanlı dizini belirtir. Arama listesi kutusunun alt kısmındaki ulaştığında, liste kutusunu üstten geri tarafından belirtilen öğeye devam `nIndexStart`. Varsa `nIndexStart` -1 olan tüm liste kutusunu baştan aranır.  
  
 `lpszFind`  
 Aranacak null ile sonlandırılmış dizeyi noktalarına. Bu dize uzantısı dahil tam bir dosya adı içerebilir. Arama büyük küçük harf duyarlı olmadığından bu dize herhangi bir bileşimini büyük ve küçük harfleri içerebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen öğenin sıfır tabanlı dizini veya **CB_ERR** arama başarısız olmuşsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu ile bir sahibi çizim stili olmadan oluşturulduysa [cbs_hasstrıngs](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili `FindStringExact` değeriyle karşılaştırarak doubleword değeri eşleştirmeye çalışır `lpszFind`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]  
  
##  <a name="getcomboboxinfo"></a>CComboBox::GetComboBoxInfo  
 Bilgi için alır `CComboBox` nesnesi.  
  
```  
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pcbi*  
 Bir işaretçi [COMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775798) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen [CB_GETCOMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775839) , Windows SDK'ın açıklandığı gibi ileti.  
  
##  <a name="getcount"></a>CComboBox::GetCount  
 Birleşik giriş kutusu liste kutusu kısmının öğe sayısını almak için bu üye işlevini çağırın.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe sayısı. Döndürülen sayım değerinden dizinini (sıfır tabanlı dizindir) en son öğenin biridir. Bu **CB_ERR** bir hata oluşursa.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]  
  
##  <a name="getcuebanner"></a>CComboBox::GetCueBanner  
 Birleşik giriş kutusu denetimi için görüntülenen işaret metni alır.  
  
```  
CString GetCueBanner() const;  
  
BOOL GetCueBanner(
    LPTSTR lpszText,   
    int cchText) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out]`lpszText`|İşaretçi işaret başlık metni alır bir arabellek.|  
|[in]`cchText`|Arabellek boyutu, `lpszText` parametresi işaret eder.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk aşırı içinde bir [CString](../../atl-mfc-shared/using-cstring.md) varsa; işaret başlık metni içeren nesne Aksi halde, bir `CString` sıfır uzunlukta bir nesne.  
  
 veya  
  
 İkinci aşırı içinde `true` bu yöntem başarılı olursa Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu denetimi giriş alanında görüntülenen bir istem işaret metindir. Kullanıcı girişi sağlayana kadar işaret metin görüntülenir.  
  
 Bu yöntem gönderir [CB_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775843) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getcursel"></a>CComboBox::GetCurSel  
 Birleşik giriş kutusu hangi öğesinde seçili belirlemek için bu üye işlevini çağırın.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu, liste kutusunda seçili öğenin sıfır tabanlı dizini veya **CB_ERR** öğe seçili değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetCurSel`bir dizin listeye döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]  
  
##  <a name="getdroppedcontrolrect"></a>CComboBox::GetDroppedControlRect  
 Çağrı `GetDroppedControlRect` açılan kutusu görünür (bırakılan aşağı) liste kutusu ekran koordinatları almak için üye işlevi.  
  
```  
void GetDroppedControlRect(LPRECT lprect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lprect*  
 İşaret [RECT yapısı](../../mfc/reference/rect-structure1.md) koordinatları almaya olmasıdır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]  
  
##  <a name="getdroppedstate"></a>CComboBox::GetDroppedState  
 Çağrı `GetDroppedState` üye işlevi (bırakılan) açılan kutusunun liste kutusunda görünür olup olmadığını belirlemek için.  
  
```  
BOOL GetDroppedState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusu görünür durumdaysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]  
  
##  <a name="getdroppedwidth"></a>CComboBox::GetDroppedWidth  
 Minimum izin verilen genişliğini piksel cinsinden bir birleşik giriş kutusu liste kutusunda almak için bu işlevini çağırın.  
  
```  
int GetDroppedWidth() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, en az izin verilen, piksel cinsinden genişliği; Aksi takdirde, **CB_ERR**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca Birleşik giriş kutuları ile uygular [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.  
  
 Varsayılan olarak, açılan liste kutusu izin verilen en küçük genişliği 0'dır. İzin verilen en küçük genişliği çağırarak ayarlanabilir [SetDroppedWidth](#setdroppedwidth). Birleşik giriş kutusu liste kutusu kısmı görüntülendiğinde eni izin verilen en küçük genişliği veya birleşik giriş kutusu genişliği büyüktür.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [SetDroppedWidth](#setdroppedwidth).  
  
##  <a name="geteditsel"></a>CComboBox::GetEditSel  
 Birleşik giriş kutusu düzenleme denetimindeki geçerli bölüm başlangıç ve bitiş karakteri konumlarını alır.  
  
```  
DWORD GetEditSel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düşük düzey Word'de başlangıç konumu ve ilk karakterin nonselected yüksek düzey word seçim bitişinden sonra içeren 32 bitlik bir değer. Bu işlev açılan kutuda bir düzen denetimi olmadan kullanılırsa, **CB_ERR** döndürülür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]  
  
##  <a name="getextendedui"></a>CComboBox::GetExtendedUI  
 Çağrı `GetExtendedUI` birleşik giriş kutusu varsayılan kullanıcı arabirimi veya genişletilmiş kullanıcı arabirimi olup olmadığını belirlemek için üye işlevi.  
  
```  
BOOL GetExtendedUI() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu genişletilmiş kullanıcı arabirimi varsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Genişletilmiş kullanıcı arabirimi, aşağıdaki yollarla tanımlanabilir:  
  
-   Statik denetimi tıklatmak görüntüler liste kutusunu yalnızca Birleşik giriş kutuları ile [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.  
  
-   Aşağı Ok tuşuna basarak (F4 devre dışıdır) liste kutusu görüntüler.  
  
 Öğe listesinin (görünür ok tuşları devre dışı bırakılır) olmadığında statik denetiminde kaydırma devre dışı bırakılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]  
  
##  <a name="gethorizontalextent"></a>CComboBox::GetHorizontalExtent  
 Birleşik giriş kutusu olarak birleşik giriş kutusu liste kutusu kısmı yatay olarak kaydırılabilir piksel cinsinden genişliği alır.  
  
```  
UINT GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılan kutuda piksel liste kutusu kısmının kaydırılabilir genişliğini.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu liste kutusu kısmı yatay kaydırma çubuğu varsa bu geçerlidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]  
  
##  <a name="getitemdata"></a>CComboBox::GetItemData  
 Belirtilen birleşik giriş kutusu öğeyle ilişkili uygulama tarafından sağlanan 32-bit değeri alır.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Açılan kutunun liste kutusunda bir öğenin sıfır tabanlı dizini içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyle ilişkili 32-bit değeri veya **CB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 32-bit değeri ile ayarlayabilirsiniz `dwItemData` parametresinin bir [Setıtemdata](#setitemdata) üye işlev çağrısı. Kullanım `GetItemDataPtr` alınması için 32-bit bir işaretçi değeri geçerliyse üye işlevi ( **void\***).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]  
  
##  <a name="getitemdataptr"></a>CComboBox::GetItemDataPtr  
 Bir işaretçi olarak belirtilen birleşik giriş kutusu öğesi ile ilişkili uygulama tarafından sağlanan 32-bit değerini alır ( **void\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Açılan kutunun liste kutusunda bir öğenin sıfır tabanlı dizini içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa bir işaretçi veya -1 alır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]  
  
##  <a name="getitemheight"></a>CComboBox::GetItemHeight  
 Çağrı `GetItemHeight` birleşik giriş kutusu bulunan liste öğelerini yüksekliğini almak için üye işlevi.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Yükseklik alınacak birleşik giriş kutusunu bileşeni belirtir. Varsa `nIndex` parametre -1 ve birleşik giriş kutusu düzenleme denetimi (veya statik metin) bölümünü yüksekliğini alınır. Birleşik giriş kutusu varsa [cbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili `nIndex` , yükseklik olduğu alınacak liste öğesinin sıfır tabanlı dizinini belirtir. Aksi takdirde `nIndex` 0 olarak ayarlanması gerekir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu içinde belirtilen öğenin piksel cinsinden yüksekliği. Dönüş değeri **CB_ERR** bir hata oluşursa.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]  
  
##  <a name="getlbtext"></a>CComboBox::GetLBText  
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
 `nIndex`  
 Kopyalanacak liste kutusu dize sıfır tabanlı dizini içerir.  
  
 `lpszText`  
 Dize alacak bir arabellek noktalarına. Arabellek dize ve bir sonlandırma null karakter için yeterli alan olmalıdır.  
  
 `rString`  
 Bir başvuru bir `CString`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sondaki boş karakter hariç dize uzunluğu (bayt cinsinden). Varsa `nIndex` geçerli bir dizin belirtmiyor dönüş değeri **CB_ERR**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üyenin ikinci formun işlev dolgular bir `CString` öğesi'nin metin içeren nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]  
  
##  <a name="getlbtextlen"></a>CComboBox::GetLBTextLen  
 Birleşik giriş kutusu liste kutusunda bir dizenin uzunluğunu alır.  
  
```  
int GetLBTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Liste kutusu dize sıfır tabanlı dizini içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dize boş karakter ile sonlandırmadan hariç bayt cinsinden uzunluğu. Varsa `nIndex` geçerli bir dizin belirtmiyor dönüş değeri **CB_ERR**.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CComboBox::GetLBText](#getlbtext).  
  
##  <a name="getlocale"></a>CComboBox::GetLocale  
 Birleşik giriş kutusu tarafından kullanılan yerel ayarları alır.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu dizelerde yerel ayar kimliği (LCID) değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerel ayar, örneğin, bir sıralanmış birleşik giriş kutusu dizelerde sıralama düzenini belirlemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CComboBox::SetLocale](#setlocale).  
  
##  <a name="getminvisible"></a>CComboBox::GetMinVisible  
 Geçerli birleşik giriş kutusu denetimi aşağı açılan listesinde en az görünür öğe sayısını alır.  
  
```  
int GetMinVisible() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli aşağı açılan listede görünen öğeleri minimum sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [CB_GETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) Windows SDK'ın açıklanan ileti.  
  
##  <a name="gettopindex"></a>CComboBox::GetTopIndex  
 Birleşik giriş kutusu liste kutusu kısmında görünen ilk öğenin sıfır tabanlı dizinini alır.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu başarılı olursa, liste kutusu kısmında görünen ilk öğenin sıfır tabanlı dizini **CB_ERR** Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlangıçta, liste kutusunu üstünde öğesi 0 olan ancak liste kutusu kaydırırsanız başka bir öğe en üstünde olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]  
  
##  <a name="initstorage"></a>CComboBox::InitStorage  
 Birleşik giriş kutusu liste kutusu bölümünde liste kutusu öğeleri depolamak için bellek ayırır.  
  
```  
int InitStorage(
    int nItems,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Parametreler  
 `nItems`  
 Eklenecek öğe sayısını belirtir.  
  
 `nBytes`  
 Öğe dizeleri için ayırmak için bayt cinsinden bellek miktarını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, en fazla sayısını bu öğeler, bir bellek yeniden ayırma, aksi takdirde gerekli önce birleşik giriş kutusu liste kutusu kısmı depolayabilir **CB_ERRSPACE**, yeterli bellek anlamına gelir kullanılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çok sayıda öğe için liste kutusu bölümünü eklemeden önce bu işlevi çağırmak `CComboBox`.  
  
 Windows 95/98 yalnızca: `wParam` parametresi için 16 bit değerleri sınırlıdır. Bu liste kutuları birden fazla 32.767 öğeleri içeremez anlamına gelir. Öğe sayısı sınırlı olsa da, liste kutusunda öğelerin toplam boyutu yalnızca kullanılabilir bellek ile sınırlıdır.  
  
 Bu işlev büyük sayıda (100'den fazla) öğe liste kutuları başlatma hızlandırmaya yardımcı olur. Bu nedenle bu sonraki bellek belirtilen miktarı preallocates [AddString](#addstring), [InsertString](#insertstring), ve [Dir](#dir) işlevler en kısa sürede alın. Tahminler parametrelerini kullanabilirsiniz. Overestimate, bazı ek bellek tahsis edilir; daha düşük normal ayırma ön tahsis miktarını aşıyor öğeleri için kullanılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]  
  
##  <a name="insertstring"></a>CComboBox::InsertString  
 Birleşik giriş kutusu liste kutusuna bir dize ekler.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Dize alacak liste kutusunda konumuna sıfır tabanlı dizini içerir. Bu parametre -1 ise, dize listesinin sonuna eklenir.  
  
 `lpszString`  
 Eklenecek null ile sonlandırılmış dizeye noktaları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hangi dize eklenmiş konumu sıfır tabanlı dizini. Dönüş değeri **CB_ERR** bir hata oluşursa. Dönüş değeri **CB_ERRSPACE** yeni bir dize depolamak yeterli alan olup olmadığını.  
  
### <a name="remarks"></a>Açıklamalar  
 Farklı [AddString](#addstring) üye işlevi `InsertString` üye işlevi bir listesiyle neden olmaz [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) sıralanacak stili.  
  
> [!NOTE]
>  Bu işlev Windows tarafından desteklenmiyor **ComboBoxEx** denetim. Bu denetimi hakkında daha fazla bilgi için bkz: [ComboBoxEx denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb775738) Windows SDK.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]  
  
##  <a name="limittext"></a>CComboBox::LimitText  
 Kullanıcı bir birleşik giriş kutusu düzenleme denetimine girebilir metnin bayt cinsinden uzunluğu sınırlar.  
  
```  
BOOL LimitText(int nMaxChars);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMaxChars`  
 Kullanıcının girebileceği metin uzunluğu (bayt cinsinden) belirtir. Bu parametre 0 ise, metin uzunluğu 65.535 bayta ayarlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır. Birleşik giriş kutusu stiliyle çağrıldıklarında [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya bir düzen denetimi olmadan bir birleşik giriş kutusu için dönüş değerini **CB_ERR**.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu stili yoksa [CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles), düzenleme denetimi boyutundan büyük olacak şekilde metin sınırını ayarlama herhangi bir etkisi olacaktır.  
  
 `LimitText`Yalnızca kullanıcının girebileceği metin sınırlar. Bunu herhangi bir metin zaten düzenleme denetimine ileti gönderilir ya da bir dize liste kutusunda seçili olduğunda düzenleme denetimi kopyalanan metnin uzunluğunu etkilemez zaman etkisi yoktur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]  
  
##  <a name="measureitem"></a>CComboBox::MeasureItem  
 Birleşik giriş kutusu sahibi çizim stili ile oluşturulduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpMeasureItemStruct`  
 Uzun bir işaretçi bir [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bu üye işlevi geçersiz kılma ve doldurmak `MEASUREITEMSTRUCT` listesinin boyutlarının Windows içinde birleşik giriş kutusu bildirmek için yapısı. Birleşik giriş kutusu ile oluşturulursa [cbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili framework çağırması bu üye işlevi liste kutusunda her bir öğe için. Aksi takdirde, bu üye yalnızca bir kez çağrılır.  
  
 Kullanarak **cbs_ownerdrawfıxed** ile oluşturulan bir sahip çizim açılan kutu stilinde [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) üye işlevini `CWnd` daha fazla programlama noktalar göz önünde bulundurulmalıdır. Tartışmada bkz [Teknik Not 14](../../mfc/tn014-custom-controls.md).  
  
 Bkz: [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) açıklaması `MEASUREITEMSTRUCT` yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]  
  
##  <a name="paste"></a>CComboBox::Paste  
 Verileri birleşik giriş kutusu geçerli imleç konumundaki düzenleme denetimi panodan ekler.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Verileri yalnızca Pano veri içeriyorsa eklenir **CF_TEXT** biçimi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]  
  
##  <a name="resetcontent"></a>CComboBox::ResetContent  
 Listeden tüm öğeler kutu ve bir birleşik giriş kutusu denetimi Düzenle kaldırır.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]  
  
##  <a name="selectstring"></a>CComboBox::SelectString  
 Birleşik giriş kutusu liste kutusunda bir dizeyi arar ve dize bulunursa, liste kutusunda dize seçer ve düzenleme denetimi kopyalar.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parametreler  
 `nStartAfter`  
 Aranacak ilk öğeden önce öğenin sıfır tabanlı dizini içerir. Arama listesi kutusunun alt kısmındaki ulaştığında, liste kutusunu üstten geri tarafından belirtilen öğeye devam `nStartAfter`. -1, tüm liste kutusunu baştan aranır.  
  
 `lpszString`  
 Aranacak önek içeren null ile sonlandırılmış dize noktalarına. Arama durumu bağımsız olduğundan, bu dizeyi herhangi bir bileşimini büyük ve küçük harfleri içerebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dize bulunursa seçili öğenin sıfır tabanlı dizini. Arama başarısız oldu, dönüş değeri ise **CB_ERR** ve geçerli seçim değiştirilmedi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca kendi ilk karakter (başlangıç noktasından) önek dizesi karakterleri eşleşiyorsa bir dize seçilir.  
  
 Unutmayın `SelectString` ve `FindString` iki üye işlevleri bir dizeyi bulmak ancak `SelectString` üye işlevi de dize seçer.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]  
  
##  <a name="setcuebanner"></a>CComboBox::SetCueBanner  
 Birleşik giriş kutusu denetimi için görüntülenen işaret metni ayarlar.  
  
```  
BOOL SetCueBanner(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *lpszText*|İşaretçi işaret metni içeren null ile sonlandırılmış bir arabellek.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu denetimi giriş alanında görüntülenen bir istem işaret metindir. Kullanıcı girişi sağlayana kadar işaret metin görüntülenir.  
  
 Bu yöntem gönderir [CB_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775897) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_combobox`, yani birleşik giriş kutusu denetimi programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde işaret başlık birleşik giriş kutusu denetimi için ayarlar.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="setcursel"></a>CComboBox::SetCurSel  
 Bir dizeyi bir birleşik giriş kutusu liste kutusunda seçer.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Parametreler  
 `nSelect`  
 Dize seçmek için sıfır tabanlı dizini belirtir. -1, liste kutusunda herhangi bir geçerli seçimi kaldırılır ve düzenleme denetimi temizlenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletinin başarılı olursa seçili öğenin sıfır tabanlı dizini. Dönüş değeri **CB_ERR** varsa `nSelect` listedeki öğeleri sayısından büyük veya `nSelect` Seçimi temizler -1 olarak ayarlayın.  
  
### <a name="remarks"></a>Açıklamalar  
 (Liste kutusunu görünür durumdaysa) gerekiyorsa, liste kutusunda dize görünüme kayar. Açılan kutunun düzenleme denetimindeki metnin yeni seçimini yansıtacak şekilde değiştirilir. Liste kutusunda herhangi bir önceki seçimi kaldırılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]  
  
##  <a name="setdroppedwidth"></a>CComboBox::SetDroppedWidth  
 Birleşik giriş kutusu liste kutusunda piksel cinsinden minimum izin verilen genişliğini ayarlamak için bu işlevini çağırın.  
  
```  
int SetDroppedWidth(UINT nWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 `nWidth`  
 Minimum izin verilen liste kutusu bölümünün genişliğini piksel cinsinden birleşik giriş kutusu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, listesinin yeni genişliğini, aksi takdirde kutusunda varsa **CB_ERR**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca Birleşik giriş kutuları ile uygular [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.  
  
 Varsayılan olarak, açılan liste kutusu izin verilen en küçük genişliği 0'dır. Birleşik giriş kutusu liste kutusu kısmı görüntülendiğinde eni izin verilen en küçük genişliği veya birleşik giriş kutusu genişliği büyüktür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]  
  
##  <a name="seteditsel"></a>CComboBox::SetEditSel  
 Karakterleri birleşik giriş kutusu düzenleme denetimine seçer.  
  
```  
BOOL SetEditSel(
    int nStartChar,  
    int nEndChar);
```  
  
### <a name="parameters"></a>Parametreler  
 `nStartChar`  
 Başlangıç konumu belirtir. Başlangıç konumu -1 olarak ayarlanırsa, varolan bir seçimi kaldırılır.  
  
 `nEndChar`  
 Bitiş konumu belirtir. Bitiş konumu -1, ardından tüm metindeki başlangıç konumu son ayarlanırsa karakter düzenleme denetimindeki seçili değil.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevini başarılıysa sıfır olmayan; Aksi takdirde 0. Bu **CB_ERR** varsa `CComboBox` sahip [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stil veya bir liste kutusu yok.  
  
### <a name="remarks"></a>Açıklamalar  
 Konumlar sıfır tabanlı. Düzenleme denetimi ilk karakteri seçmek için 0 başlangıç konumunu belirtin. Bitiş konumu seçmek için son karakter hemen sonra için karakterdir. Örneğin, düzenleme denetimi ilk dört karakterini seçmek için başlangıç konumu 0 ve 4'ün bitiş konumu kullanırsınız.  
  
> [!NOTE]
>  Bu işlev Windows tarafından desteklenmiyor **ComboBoxEx** denetim. Bu denetimi hakkında daha fazla bilgi için bkz: [ComboBoxEx denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb775738) Windows SDK.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CComboBox::GetEditSel](#geteditsel).  
  
##  <a name="setextendedui"></a>CComboBox::SetExtendedUI  
 Çağrı `SetExtendedUI` varsayılan kullanıcı arabirimi veya sahip bir birleşik giriş kutusu için genişletilmiş kullanıcı arabirimi seçmek için üye işlevi [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.  
  
```  
int SetExtendedUI(BOOL bExtended = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bMicrosoft*  
 Birleşik giriş kutusu genişletilmiş kullanıcı arabirimi veya varsayılan kullanıcı arabirimi kullanması gerekip gerekmediğini belirtir. Değerini **TRUE** genişletilmiş seçer kullanıcı arabirimi; değerini **FALSE** standart kullanıcı arabirimi seçer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **CB_OKAY** işlemi başarılı olursa ya da **CB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Genişletilmiş kullanıcı arabirimi, aşağıdaki yollarla tanımlanabilir:  
  
-   Statik denetimi tıklatmak görüntüler liste kutusunu yalnızca Birleşik giriş kutuları ile **cbs_dropdownlıst** stili.  
  
-   Aşağı Ok tuşuna basarak (F4 devre dışıdır) liste kutusu görüntüler.  
  
 Statik denetiminde kaydırma devre dışı öğesi listesinde görünmediğinde (ok tuşlarını devre dışı bırakılır).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CComboBox::GetExtendedUI](#getextendedui).  
  
##  <a name="sethorizontalextent"></a>CComboBox::SetHorizontalExtent  
 Genişlik olarak birleşik giriş kutusu liste kutusu kısmı yatay olarak kaydırılabilir piksel cinsinden ayarlar.  
  
```  
void SetHorizontalExtent(UINT nExtent);
```  
  
### <a name="parameters"></a>Parametreler  
 *nExtent*  
 Piksel olarak birleşik giriş kutusu liste kutusu kısmı yatay olarak kaydırılabilir sayısını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu genişliğini bu değerden daha küçükse, yatay kaydırma çubuğu yatay öğeleri liste kutusunda kaydırma. Yatay kaydırma çubuğu liste kutusunun genişliğini eşit veya bu değerden büyük ise, gizli veya birleşik giriş kutusu varsa [cbs_dısablenoscroll](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili, devre dışı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]  
  
##  <a name="setitemdata"></a>CComboBox::SetItemData  
 Belirtilen öğe bir açılan kutuda ilişkili 32-bit değerini ayarlar.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Ayarlanacak öğenin sıfır tabanlı dizini içerir.  
  
 `dwItemData`  
 Öğeyle ilişkilendirilecek yeni değeri içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **CB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `SetItemDataPtr` 32-bit öğesi bir işaretçi olması durumunda üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]  
  
##  <a name="setitemdataptr"></a>CComboBox::SetItemDataPtr  
 Belirtilen öğe belirtilen işaretçisi olacak şekilde bir açılan kutuda ilişkili 32-bit değeri ayarlar ( **void\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin sıfır tabanlı dizini içerir.  
  
 `pData`  
 Öğeyle ilişkilendirilecek bir işaretçi içeriyor.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **CB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğeler eklendiğinde veya kaldırıldığında gibi öğesi'nin göreli konum birleşik giriş kutusu içinde değişebilir olsa bile bu işaretçinin birleşik giriş kutusu ömrü için geçerli kalır. Bu nedenle, öğenin dizini kutusunda değiştirebilirsiniz, ancak işaretçi güvenilir kalır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]  
  
##  <a name="setitemheight"></a>CComboBox::SetItemHeight  
 Çağrı `SetItemHeight` üye işlevi bir birleşik giriş kutusu veya açılan kutu düzenleme denetimi (veya statik metin) bölümünü yüksekliğini liste öğeleri yüksekliğini ayarlayın.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Liste öğeleri yüksekliğini veya birleşik giriş kutusu düzenleme denetimi (veya statik metin) bölümünü yüksekliğini ayarlanmış olup olmadığını belirtir.  
  
 Birleşik giriş kutusu varsa [cbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili `nIndex` , yükseklik olduğu ayarlayın; Aksi takdirde liste öğesinin sıfır tabanlı dizinini belirtir `nIndex` 0 ve tüm liste öğeleri ayarlanacak yüksekliğini olması gerekir.  
  
 Varsa `nIndex` -1, düzenleme denetimi yüksekliğini veya birleşik giriş kutusu statik metin bölümünü ayarlanacak.  
  
 `cyItemHeight`  
 Tarafından tanımlanan birleşik giriş kutusu bileşeninin piksel cinsinden yüksekliği belirtir `nIndex`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **CB_ERR** dizini veya yükseklik ise geçersiz; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu düzenleme denetimi (veya statik metin) bölümünü yüksekliğini liste öğeleri Yükseklik bağımsız olarak ayarlanır. Uygulama düzenleme denetimi (veya statik metin) bölümü yüksekliğini belirli liste kutusu öğesi yüksekliğini küçük olmadığından emin olmalısınız.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]  
  
##  <a name="setlocale"></a>CComboBox::SetLocale  
 Bu birleşik giriş kutusu için yerel ayar kimliğini ayarlar.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Parametreler  
 `nNewLocale`  
 Açılan kutu için ayarlanacak yeni yerel ayar kimliği (LCID) değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu birleşik giriş kutusu önceki yerel ayar kimliği (LCID) değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa **SetLocale** çağrılmaz, varsayılan yerel ayar sistemden elde edilir. Denetim Masası ndaki kullanarak bu sistem varsayılan yerel ayar değiştirilebilir bölge (veya uluslararası) uygulama.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]  
  
##  <a name="setminvisibleitems"></a>CComboBox::SetMinVisibleItems  
 En az görünür öğe sayısını geçerli birleşik açılır listesi kutusu denetimi ayarlar.  
  
```  
BOOL SetMinVisibleItems(int iMinVisible);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`iMinVisible`|En az görünür öğe sayısını belirtir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [CB_SETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_combobox`, yani birleşik giriş kutusu denetimi programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde 20 öğeleri birleşik giriş kutusu denetimi aşağı açılan listesine ekler. Ardından kullanıcı aşağı açılan okunu bastığında en az 10 öğe görüntüleneceğini belirtir.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="settopindex"></a>CComboBox::SetTopIndex  
 Belirli bir öğe birleşik giriş kutusu liste kutusu kısmında görünür olmasını sağlar.  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Liste kutusu öğenin sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır veya **CB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Sistem tarafından belirtilen öğeyi kadar liste kutusu kayar `nIndex` görünür listesinin başında kutusu veya maksimum kaydırma aralığı ulaşıldı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]  
  
##  <a name="showdropdown"></a>CComboBox::ShowDropDown  
 Gösterir veya gizler sahip bir birleşik giriş kutusu liste kutusunda [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) veya [cbs_dropdownlıst](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.  
  
```  
void ShowDropDown(BOOL bShowIt = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bShowIt*  
 Aşağı açılan liste kutusunu gösterileceğini veya gizleneceğini olup olmadığını belirtir. Değerini **TRUE** liste kutusu gösterir. Değerini **FALSE** liste kutusunu gizler.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu stili birleşik giriş kutusu liste kutusunu gösterir.  
  
 Bu üye işlevi ile oluşturulan bir birleşik giriş kutusu üzerinde hiçbir etkisi olmaz [cbs_sımple](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) stili.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CComboBox::GetDroppedState](#getdroppedstate).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CButton sınıfı](../../mfc/reference/cbutton-class.md)   
 [CEdit sınıfı](../../mfc/reference/cedit-class.md)   
 [CListBox sınıfı](../../mfc/reference/clistbox-class.md)   
 [CScrollBar sınıfı](../../mfc/reference/cscrollbar-class.md)   
 [CStatic sınıfı](../../mfc/reference/cstatic-class.md)   
 [CDialog sınıfı](../../mfc/reference/cdialog-class.md)
