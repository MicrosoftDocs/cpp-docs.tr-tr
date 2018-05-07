---
title: CListBox sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1101e4115efa3c5c822d0d64b767cdee379a0e0b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="clistbox-class"></a>CListBox sınıfı
Bir Windows liste kutusu işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CListBox : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CListBox::CListBox](#clistbox)|Oluşturan bir `CListBox` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CListBox::AddString](#addstring)|Liste kutusu için bir dize ekler.|  
|[CListBox::CharToItem](#chartoitem)|Özel sağlamak için geçersiz kılma `WM_CHAR` dizeleri olmayan sahip çizim liste kutuları için işleme.|  
|[CListBox::CompareItem](#compareitem)|Sıralanmış sahibi tarafından çizilen liste kutusunda yeni bir öğe konumunu belirlemek için çerçevesi tarafından çağrılır.|  
|[CListBox::Create](#create)|Windows liste kutusu oluşturur ve ona ekler `CListBox` nesnesi.|  
|[CListBox::DeleteItem](#deleteitem)|Kullanıcı bir sahibi tarafından çizilen liste kutusundan bir öğeyi sildiğinde çerçevesi tarafından çağrılır.|  
|[CListBox::DeleteString](#deletestring)|Bir dize kümesinden liste kutusunu siler.|  
|[CListBox::Dir](#dir)|Dosya adları, sürücüleri veya her ikisi de geçerli dizinden bir liste kutusu ekler.|  
|[CListBox::DrawItem](#drawitem)|Bir sahip çizim liste kutusunu değişiklikleri visual yönünü zaman çerçevesi tarafından çağrılır.|  
|[CListBox::FindString](#findstring)|Liste kutusunda bir dize arar.|  
|[CListBox::FindStringExact](#findstringexact)|Belirtilen dizenin eşleşen ilk liste kutusu dizeyi bulur.|  
|[CListBox::GetAnchorIndex](#getanchorindex)|Liste kutusunda geçerli bağlantı öğenin sıfır tabanlı dizinini alır.|  
|[CListBox::GetCaretIndex](#getcaretindex)|Çoklu seçim liste kutusunda odak dikdörtgeni sahip öğenin dizinini belirler.|  
|[CListBox::GetCount](#getcount)|Liste kutusunda dizeleri sayısını döndürür.|  
|[CListBox::GetCurSel](#getcursel)|Liste kutusunda seçili dize sıfır tabanlı dizinini döndürür.|  
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|Liste kutusu yatay kaydırılabileceğini piksel cinsinden genişliği döndürür.|  
|[CListBox::GetItemData](#getitemdata)|Liste kutusu öğeyle ilişkili 32-bit değeri döndürür.|  
|[CListBox::GetItemDataPtr](#getitemdataptr)|Bir işaretçi bir liste kutusu öğesi döndürür.|  
|[CListBox::GetItemHeight](#getitemheight)|Liste kutusu öğeleri yüksekliğini belirler.|  
|[CListBox::GetItemRect](#getitemrect)|Şu anda görüntülenen sınırlayıcı dikdörtgenini liste kutusu öğesi döndürür.|  
|[CListBox::GetListBoxInfo](#getlistboxinfo)|Sütun başına öğe sayısını alır.|  
|[CListBox::GetLocale](#getlocale)|Liste kutusu için yerel ayar tanıtıcısını alır.|  
|[CListBox::GetSel](#getsel)|Liste kutusu öğesi seçimi durumunu döndürür.|  
|[CListBox::GetSelCount](#getselcount)|Çoklu seçim liste kutusunda seçili dizeleri sayısını döndürür.|  
|[CListBox::GetSelItems](#getselitems)|Liste kutusunda seçili dizeleri dizinleri döndürür.|  
|[CListBox::GetText](#gettext)|Bir liste kutusu öğesi bir arabelleğe kopyalar.|  
|[CListBox::GetTextLen](#gettextlen)|Bir liste kutusu öğesi bayt cinsinden uzunluğu döndürür.|  
|[CListBox::GetTopIndex](#gettopindex)|Liste kutusunda ilk görünür dizesi dizinini döndürür.|  
|[CListBox::InitStorage](#initstorage)|Liste kutusu öğeleri ve dizeleri için bellek bloklarını preallocates.|  
|[CListBox::InsertString](#insertstring)|Liste kutusunda belirli bir konumdaki bir dize ekler.|  
|[CListBox::ItemFromPoint](#itemfrompoint)|Liste kutusu öğesi bir point en yakın dizinini döndürür.|  
|[CListBox::MeasureItem](#measureitem)|Liste kutusu boyutları belirlemek için bir sahip çizim liste kutusu oluşturulduğunda çerçevesi tarafından çağrılır.|  
|[CListBox::ResetContent](#resetcontent)|Bir liste kutusundan tüm girişleri siler.|  
|[CListBox::SelectString](#selectstring)|Arar ve tek seçim liste kutusunda bir dize seçer.|  
|[CListBox::SelItemRange](#selitemrange)|Seçer veya çoklu seçim liste kutusu dizelerde çeşitli seçimini kaldırır.|  
|[CListBox::SetAnchorIndex](#setanchorindex)|Bağlantı bir Genişletilmiş seçim başlamak için bir çoklu seçim liste kutusunda ayarlar.|  
|[CListBox::SetCaretIndex](#setcaretindex)|Çoklu seçim liste kutusunda belirtilen dizindeki öğe için odak dikdörtgeni ayarlar.|  
|[CListBox::SetColumnWidth](#setcolumnwidth)|Sütunlu liste kutusu sütun genişliğini ayarlar.|  
|[CListBox::SetCurSel](#setcursel)|Liste kutusu dize seçer.|  
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|Liste kutusu yatay kaydırılabileceğini piksel cinsinden genişliğini belirler.|  
|[CListBox::SetItemData](#setitemdata)|Liste kutusu öğeyle ilişkili 32-bit değeri ayarlar.|  
|[CListBox::SetItemDataPtr](#setitemdataptr)|Bir işaretçi liste kutusu öğesine ayarlar.|  
|[CListBox::SetItemHeight](#setitemheight)|Öğe yüksekliği liste kutusunda ayarlar.|  
|[CListBox::SetLocale](#setlocale)|Liste kutusu için yerel ayar kimliğini ayarlar.|  
|[CListBox::SetSel](#setsel)|Seçer veya bir liste kutusu öğesi çoklu seçim liste kutusunda seçimini kaldırır.|  
|[CListBox::SetTabStops](#settabstops)|Liste kutusu sekme durağı konumda ayarlar.|  
|[CListBox::SetTopIndex](#settopindex)|İlk görünür dizesi sıfır tabanlı dizini bir liste kutusunda ayarlar.|  
|[CListBox::VKeyToItem](#vkeytoitem)|Özel sağlamak için geçersiz kılma `WM_KEYDOWN` liste kutuları ile için işleme **lbs_wantkeyboardınput** stil kümesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Liste kutusu, kullanıcının görüntüleyebileceği ve seçin dosya adları gibi öğeleri listesini görüntüler.  
  
 Tek seçim liste kutusunda, kullanıcının yalnızca bir öğe seçebilirsiniz. Bir çoklu seçim liste kutusunda bir öğe aralığı seçilebilir. Kullanıcı bir öğeyi seçtiğinde vurgulanır ve liste kutusu üst penceresine bir bildirim iletisi gönderir.  
  
 Bir iletişim şablonunu ya da kodunuzdaki doğrudan bir liste kutusu oluşturabilirsiniz. Doğrudan oluşturmak için oluşturmak `CListBox` nesne sonra çağırın [oluşturma](#create) Windows liste kutusu denetimi oluşturma ve kendisine eklemek için üye işlevi `CListBox` nesnesi. Bir iletişim şablonunu liste kutusunda kullanmak için bir liste kutusu değişkeni iletişim kutusu sınıfınızda bildirme sonra kullanın `DDX_Control` iletişim kutusu sınıfınızın içinde `DoDataExchange` üye değişkeni denetime bağlanmak için işlevi. (iletişim kutusu sınıfı denetim değişkeni eklediğinizde bu sizin için otomatik olarak gerçekleştirilir.)  
  
 Yapım tek adımlı işlem türetilen bir sınıfta olabilir `CListBox`. Çağrı ve türetilmiş sınıf oluşturucu yazma **oluşturma** gelen oluşturucusu içinde.  
  
 Üst için bir liste kutusu tarafından gönderilen Windows bildirim iletilerini işlemek istiyorsanız (öğesinden türetilmiş bir sınıf genellikle [CDialog](../../mfc/reference/cdialog-class.md)), her ileti için üst sınıfı için ileti eşleme girişi ve ileti işleyicisi üye işlevi ekleme.  
  
 Her ileti eşleme girişi aşağıdaki biçimdedir:  
  
 `ON_Notification( id, memberFxn )`  
  
 Burada `id` bildirim göndererek liste kutusu denetimi alt pencere Kimliğini belirtir ve `memberFxn` bildirimini işlemek için yazılmış üst üye işlevi adıdır.  
  
 Üst öğenin işlev prototipi aşağıdaki gibidir:  
  
 `afx_msg void memberFxn( );`  
  
 Olası ileti eşleme girişleri ve açıklamasını, bunlar üst gönderilecek örneklerinin listesi aşağıdadır:  
  
- **ON_LBN_DBLCLK** kullanıcı bir liste kutusu dizesinde çift tıklamalar. İçeren bir liste kutusu [lbs_notıfy](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili bu bildirim iletisi gönderir.  
  
- **ON_LBN_ERRSPACE** liste kutusu isteği karşılamak için yeterli bellek ayrılamıyor.  
  
- **ON_LBN_KILLFOCUS** liste kutusu giriş odağını kaybetme.  
  
- **ON_LBN_SELCANCEL** geçerli liste kutusu seçimi iptal edildi. Liste kutusu sahip olduğunda bu ileti yalnızca gönderilir **lbs_notıfy** stili.  
  
- **ON_LBN_SELCHANGE** liste kutusunda seçim değişti. Seçim tarafından değiştirilirse bu bildirim gönderilmez [CListBox::SetCurSel](#setcursel) üye işlevi. Bu bildirim sahip yalnızca bir liste kutusu için geçerli **lbs_notıfy** stili. **LBN_SELCHANGE** bildirim iletinin gönderildiği bir çoklu seçim liste kutusu her kullanıcı bir ok tuşuna bastığında seçimi değişmeyen olsa bile.  
  
- **ON_LBN_SETFOCUS** liste kutusu giriş odağını alıyor.  
  
- **ON_WM_CHARTOITEM** hiç dize olan bir sahip çizim liste kutusu alan bir `WM_CHAR` ileti.  
  
- **ON_WM_VKEYTOITEM** içeren bir liste kutusu **lbs_wantkeyboardınput** stili alır bir `WM_KEYDOWN` ileti.  
  
 Oluşturursanız, bir `CListBox` nesnesi (aracılığıyla bir iletişim kutusu kaynağı), bir iletişim kutusu içinde `CListBox` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.  
  
 Oluşturursanız, bir `CListBox` nesne bir pencerede destroy gerekebilir `CListBox` nesnesi. Oluşturursanız, `CListBox` nesne yığında otomatik olarak yok. Oluşturursanız, `CListBox` nesnesi kullanarak yığında **yeni** işlevini çağırmanız gerekir **silmek** kullanıcı üst pencere kapatıldığında yok etmek için nesne üzerinde.  
  
 Tüm bellekte ayırdığınızda `CListBox` nesne, geçersiz kılma `CListBox` yıkıcı ayrılması silmek için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListBox`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="addstring"></a>  CListBox::AddString  
 Liste kutusu için bir dize ekler.  
  
```  
int AddString(LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszItem`  
 Eklenecek null ile sonlandırılmış dizeye noktaları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda dizeye sıfır tabanlı dizini. Dönüş değeri **LB_ERR** bir hata oluşursa; dönüş değeri olan **LB_ERRSPACE** yeni bir dize depolamak yeterli alan olup olmadığını.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu ile oluşturulmamışsa [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili, dize listesinin sonuna eklenir. Aksi takdirde dize listesine eklenir ve liste sıralanır. Liste kutusu oluşturulmuşsa **LBS_SORT** stil ancak [lbs_hasstrıngs](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili framework sıralar listesinde bir veya daha fazla çağrı tarafından `CompareItem` üye işlevi.  
  
 Kullanım [InsertString](#insertstring) liste kutusu içinde belirli bir konuma bir dize eklemek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]  
  
##  <a name="chartoitem"></a>  CListBox::CharToItem  
 Liste kutunun üst pencere aldığında çerçevesi tarafından çağrılır bir `WM_CHARTOITEM` liste kutusundan ileti.  
  
```  
virtual int CharToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nKey`  
 Kullanıcı yazılan karakter ANSI kodu.  
  
 `nIndex`  
 Liste kutusu şapka geçerli konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür - 1 veya - başka bir eylem veya bir liste kutusu öğesi tuş vuruşu için varsayılan eylem gerçekleştirileceği dizinini belirtmek için negatif olmayan bir sayı için 2. Varsayılan uygulama döndürür - 1.  
  
### <a name="remarks"></a>Açıklamalar  
 `WM_CHARTOITEM` İleti, aldığında liste kutusu tarafından gönderilen bir `WM_CHAR` yalnızca liste kutusu tümünü Bu ölçütleri karşılayan, ancak ileti:  
  
-   Bir sahip çizim liste kutusu bulunur.  
  
-   Sahip olmayan [lbs_hasstrıngs](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stil kümesi.  
  
-   En az bir öğe içeriyor.  
  
 Hiçbir zaman kendiniz bu işlev çağırmalıdır. Klavye iletileri kendi özel işlenmesini sağlamak için bu işlevi geçersiz kılar.  
  
 Geçersiz kılmada framework gerçekleştirdiğiniz hangi eylemini bildirmek için bir değer döndürmesi gerekir. Dönüş değeri - 1 veya - 2 öğeyi seçerek tüm yönlerini işlenmiş ve liste kutusu tarafından başka bir eylem gerektiren gösterir. Döndürmeden önce - 1 veya - 2, size seçimini ayarlayın veya şapka veya her ikisini de taşıyın. Seçimi ayarlamak için kullanın [SetCurSel](#setcursel) veya [SetSel](#setsel). Şapka taşımak için kullanın [SetCaretIndex](#setcaretindex).  
  
 Dönüş değeri 0 veya daha büyük bir öğenin dizini liste kutusunda belirtir ve verilen öğe üzerinde tuş vuruşu için liste kutusunu varsayılan eylem yapmanız gerektiğini belirtir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]  
  
##  <a name="clistbox"></a>  CListBox::CListBox  
 Oluşturan bir `CListBox` nesnesi.  
  
```  
CListBox();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CListBox` iki adımda nesne. İlk olarak, Oluşturucusu çağrısı **ClistBox** ve ardından arama **oluşturma**, Windows liste kutusu başlatır ve ekleninceye `CListBox`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]  
  
##  <a name="compareitem"></a>  CListBox::CompareItem  
 Yeni bir öğe sıralanmış sahibi tarafından çizilen liste kutusunda göreli konumunu belirlemek için framework tarafından çağrılır.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpCompareItemStruct`  
 Uzun bir işaretçi bir `COMPAREITEMSTRUCT` yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açıklanan iki öğe göreli konumunu gösterir [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) yapısı. Aşağıdaki değerlerden herhangi birini olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|-1|Madde 1, 2 öğesi önce sıralar.|  
|0|Madde 1 ve 2 öğesi aynı sıralayın.|  
|1.|Madde 1, 2 öğesinden sonra sıralar.|  
  
 Bkz: [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) açıklaması `COMPAREITEMSTRUCT` yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bir sahip çizim liste kutusu oluşturursanız **LBS_SORT** stili, yeni liste kutusu eklenen öğeleri sıralama framework yardımcı olması için bu üye işlevi geçersiz kılması gerekir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]  
  
##  <a name="create"></a>  CListBox::Create  
 Windows liste kutusu oluşturur ve ona ekler `CListBox` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Liste kutusu stilini belirtir. Herhangi bir bileşimini uygulamak [liste kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) kutusuna.  
  
 `rect`  
 Liste kutusu boyutunu ve konumunu belirtir. Ya da olabilir bir `CRect` nesnesi veya bir `RECT` yapısı.  
  
 `pParentWnd`  
 Liste kutunun üst pencere belirtir (genellikle bir `CDialog` nesnesi). Değil olmalıdır **NULL**.  
  
 `nID`  
 Liste kutunun denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CListBox` iki adımda nesne. İlk olarak, Oluşturucusu arayın ve ardından arama **oluşturma**, hangi Windows liste kutusu başlatır ve ekleninceye `CListBox` nesnesi.  
  
 Zaman **oluşturma** yürütür, Windows gönderir [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [WM_ GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) liste kutusu denetim iletileri.  
  
 Bu iletiler, varsayılan olarak tarafından işlenen [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [Ongetminmaxınfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) üye işlevleri içinde `CWnd` temel sınıfı. Varsayılan ileti işleme genişletmek için öğesinden bir sınıf türetin `CListBox`ileti eşlemesi için yeni sınıf ekleyin ve önceki ileti işleyicisi üye işlevlerini geçersiz kılma. Geçersiz kılma `OnCreate`, örneğin, gerekli başlatma için yeni bir sınıf gerçekleştirmek için.  
  
 Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir liste kutusu denetimi için.  
  
- **WS_CHILD** her zaman  
  
- **Ws_vısıble** genellikle  
  
- **Ws_dısabled** nadiren  
  
- **WS_VSCROLL** dikey kaydırma çubuğu eklemek için  
  
- **WS_HSCROLL** yatay kaydırma çubuğu eklemek için  
  
- **WS_GROUP** grup denetimleri için  
  
- **WS_TABSTOP** bu denetim için sekme izin vermek için  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]  
  
##  <a name="deleteitem"></a>  CListBox::DeleteItem  
 Kullanıcı bir öğeyi sahibi çizim sildiğinde çerçevesi tarafından çağrılır `CListBox` nesne veya liste kutusu yok eder.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDeleteItemStruct`  
 Windows için uzun bir işaretçi [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) silinmiş öğeyi hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması hiçbir şey yapmaz. Bu işlevi gerektiği gibi bir sahibi tarafından çizilen liste kutusunu yeniden düzenleme için geçersiz kılar.  
  
 Bkz: [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) açıklaması `DELETEITEMSTRUCT` yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]  
  
##  <a name="deletestring"></a>  CListBox::DeleteString  
 Konum öğesinde siler `nIndex` liste kutusundan.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Silinecek dize sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listede kalan dizeleri sayısı. Dönüş değeri **LB_ERR** varsa `nIndex` öğe sayısından daha büyük bir dizin listesindeki belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İzleyen tüm öğeleri `nIndex` şimdi bir konum aşağı taşıma. Örneğin, bir liste kutusu iki öğeler içeriyorsa, ilk öğe silinmesi şimdi ilk konumda kalan öğeyi neden olur. `nIndex`ilk konumda öğesi için 0 =.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]  
  
##  <a name="dir"></a>  CListBox::Dir  
 Dosya adları, sürücüler ya da her ikisini bir liste kutusu listesi ekler.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Parametreler  
 `attr`  
 Herhangi bir bileşimi olabilir `enum` değerleri açıklanan **CFile::GetStatu**[s](../../mfc/reference/cfile-class.md#getstatus), ya da herhangi bir birleşimini aşağıdaki değerlerden biri:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|0x0000|Dosya okunamıyor veya yazılamıyor.|  
|0x0001|Dosya okuma ancak yazılabilir değil.|  
|0x0002|Dosya gizlidir ve dizin listesinde görüntülenmez.|  
|0x0004|Dosya sistemi dosyadır.|  
|0x0010|Tarafından belirtilen adını `lpszWildCard` bir dizini belirtir.|  
|0x0020|Dosya arşivledi.|  
|0x4000|Tarafından belirtilen adla eşleşen tüm sürücüler dahil `lpszWildCard`.|  
|0x8000|Özel bayrağı. Özel bayrağı ayarlarsanız, yalnızca belirtilen türde dosyalar listelenir. Aksi halde, belirtilen türdeki dosyaları "normal" dosyalarına ek olarak listelenir.|  
  
 `lpszWildCard`  
 Bir dosya belirtimi dize noktalarına. Dize, joker karakter içerebilir (örneğin, *.\*).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listeye eklenen son filename sıfır tabanlı dizini. Dönüş değeri **LB_ERR** bir hata oluşursa; dönüş değeri olan **LB_ERRSPACE** yeni dize depolamak yeterli alan olup olmadığını.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]  
  
##  <a name="drawitem"></a>  CListBox::DrawItem  
 Bir sahip çizim liste kutusunu değişiklikleri visual yönünü zaman çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDrawItemStruct`  
 Uzun bir işaretçi bir [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) gerekli çizim türü hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 **İtemAction** ve **itemState** üyeleri `DRAWITEMSTRUCT` yapısı gerçekleştirilecek çizim eylemi tanımlayın.  
  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Çizim sahibi çizim için uygulamak için bu üye işlevi geçersiz kılma `CListBox` nesnesi. Tüm grafik cihaz arabirimi (GDI) nesneleri görüntüleme bağlamı içinde sağlanan için seçilen uygulama kurtarmalısınız `lpDrawItemStruct` önce bu üye fonksiyonu sonlandırır.  
  
 Bkz: [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) açıklaması `DRAWITEMSTRUCT` yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]  
  
##  <a name="findstring"></a>  CListBox::FindString  
 Liste kutusu seçimi değiştirmeden Belirtilen önek içeren bir liste kutusunda ilk dizesi bulur.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nStartAfter`  
 Aranacak ilk öğeden önce öğenin sıfır tabanlı dizini içerir. Arama listesi kutusunun alt kısmındaki ulaştığında, liste kutusunu üstten geri tarafından belirtilen öğeye devam `nStartAfter`. Varsa `nStartAfter` -1 olan tüm liste kutusunu baştan aranır.  
  
 `lpszItem`  
 Aranacak önek içeren null ile sonlandırılmış dize noktalarına. Arama durumu bağımsız olduğundan, bu dizeyi herhangi bir bileşimini büyük ve küçük harfleri içerebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen öğenin sıfır tabanlı dizini veya **LB_ERR** arama başarısız olmuşsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [SelectString](#selectstring) hem bulmak ve bir dize seçmek için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]  
  
##  <a name="findstringexact"></a>  CListBox::FindStringExact  
 İçinde belirtilen dize eşleşen ilk liste kutusu dizesi bulur `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndexStart`  
 Aranacak ilk öğeden önce öğenin sıfır tabanlı dizini belirtir. Arama listesi kutusunun alt kısmındaki ulaştığında, liste kutusunu üstten geri tarafından belirtilen öğeye devam `nIndexStart`. Varsa `nIndexStart` -1 olan tüm liste kutusunu baştan aranır.  
  
 `lpszFind`  
 Aranacak null ile sonlandırılmış dizeyi noktalarına. Bu dize uzantısı dahil tam bir dosya adı içerebilir. Arama büyük küçük harf duyarlı olmadığından dize herhangi bir bileşimini büyük ve küçük harfleri içerebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen öğenin dizini veya **LB_ERR** arama başarısız olmuşsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu ile bir sahibi çizim stili olmadan oluşturulduysa [lbs_hasstrıngs](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili `FindStringExact` üye işlevi çalışır değeriyle karşılaştırarak doubleword değerle eşleşecek şekilde `lpszFind`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]  
  
##  <a name="getanchorindex"></a>  CListBox::GetAnchorIndex  
 Liste kutusunda geçerli bağlantı öğenin sıfır tabanlı dizinini alır.  
  
```  
int GetAnchorIndex() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bağlantı öğenin dizini, başarılı olursa; Aksi takdirde **LB_ERR**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir çoklu seçim liste kutusunda bitişik seçili öğeleri bloğunda ilk veya son öğeye bağlantı öğesidir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="getcaretindex"></a>  CListBox::GetCaretIndex  
 Çoklu seçim liste kutusunda odak dikdörtgeni sahip öğenin dizinini belirler.  
  
```  
int GetCaretIndex() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda odak dikdörtgeni sahip öğenin sıfır tabanlı dizini. Liste kutusu tek seçimli liste kutusu, dönüş değeri seçili öğenin dizini varsa ise.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğeyi olabilir veya seçili değildir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CListBox::SetCaretIndex](#setcaretindex).  
  
##  <a name="getcount"></a>  CListBox::GetCount  
 Liste kutusunda öğe sayısını alır.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda öğe sayısını veya **LB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen sayım değerinden dizinini (sıfır tabanlı dizindir) en son öğenin biridir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]  
  
##  <a name="getcursel"></a>  CListBox::GetCurSel  
 Tek seçim liste kutusunda seçili öğenin sıfır tabanlı dizinini alır  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek seçim liste kutusu ise seçili öğenin sıfır tabanlı dizini. Bu `LB_ERR` hiçbir öğe şu anda seçili ise.  
  
 Çoklu seçim liste kutusunda odağa sahip öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmayın `GetCurSel` çoklu seçim liste kutusu için. Kullanım [CListBox::GetSelItems](#getselitems) yerine.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]  
  
##  <a name="gethorizontalextent"></a>  CListBox::GetHorizontalExtent  
 Liste kutusundan olarak, yatay olarak kaydırılabilir piksel cinsinden genişliği alır.  
  
```  
int GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda piksel kaydırılabilir genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu yatay kaydırma çubuğu varsa bu geçerlidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]  
  
##  <a name="getitemdata"></a>  CListBox::GetItemData  
 Belirtilen liste kutusu öğeyle ilişkili uygulama tarafından sağlanan doubleword değeri alır.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin sıfır tabanlı dizini liste kutusunda belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyle ilişkili 32-bit değeri veya **LB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Doubleword değeri `dwItemData` parametresinin bir [Setıtemdata](#setitemdata) çağırın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]  
  
##  <a name="getitemdataptr"></a>  CListBox::GetItemDataPtr  
 Belirtilen liste kutusu öğesi bir işaretçi olarak ile ilişkili uygulama tarafından sağlanan 32-bit değerini alır ( **void\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin sıfır tabanlı dizini liste kutusunda belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa bir işaretçi veya -1 alır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]  
  
##  <a name="getitemheight"></a>  CListBox::GetItemHeight  
 Liste kutusu öğeleri yüksekliğini belirler.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin sıfır tabanlı dizini liste kutusunda belirtir. Bu parametre yalnızca liste kutusu varsa kullanılır **lbs_ownerdrawvarıable** stil; Aksi halde 0 olarak ayarlanmalıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda öğelerin piksel cinsinden yüksekliği. Liste kutusu varsa [lbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili, dönüş değeri tarafından belirtilen öğenin yüksekliğini mi `nIndex`. Bir hata oluşursa, dönüş değeri olan **LB_ERR**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]  
  
##  <a name="getitemrect"></a>  CListBox::GetItemRect  
 Şu anda liste kutusu penceresinde gösterilen dikdörtgen boyutlarını bu sınırların bir liste kutusu öğesi alır.  
  
```  
int GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin sıfır tabanlı dizini belirtir.  
  
 `lpRect`  
 Uzun bir işaretçi belirten bir [RECT yapısı](../../mfc/reference/rect-structure1.md) öğesi liste kutusu istemci koordinatları alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **LB_ERR** bir hata oluşursa.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]  
  
##  <a name="getlistboxinfo"></a>  CListBox::GetListBoxInfo  
 Sütun başına öğe sayısını alır.  
  
```  
DWORD GetListBoxInfo() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sütunun başına öğe sayısı `CListBox` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen [LB_GETLISTBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775208) , Windows SDK'ın açıklandığı gibi ileti.  
  
##  <a name="getlocale"></a>  CListBox::GetLocale  
 Liste kutusu tarafından kullanılan yerel ayarları alır.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusu dizelerde yerel ayar kimliği (LCID) değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerel ayar, örneğin, bir sıralı liste kutusu dizelerde sıralama düzenini belirlemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CListBox::SetLocale](#setlocale).  
  
##  <a name="getsel"></a>  CListBox::GetSel  
 Öğenin seçim durumunu alır.  
  
```  
int GetSel(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen öğe seçiliyse, pozitif bir sayı; Aksi takdirde, 0'dır. Dönüş değeri `LB_ERR` bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi hem tek ve çoklu seçim liste kutuları ile çalışır.  
  
 Şu anda seçili liste kutusu öğesi dizinini almak kullanın [CListBox::GetCurSel](#getcursel).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]  
  
##  <a name="getselcount"></a>  CListBox::GetSelCount  
 Çoklu seçim liste kutusunda seçili öğeleri toplam sayısını alır.  
  
```  
int GetSelCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda seçili öğelerin sayısı. Liste kutusu tek seçimli liste kutusu dönüş değeri ise, **LB_ERR**.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CListBox::GetSelItems](#getselitems).  
  
##  <a name="getselitems"></a>  CListBox::GetSelItems  
 Çoklu seçim liste kutusunda seçili öğeleri öğesi numaralarını belirten dizisi ile bir arabellek doldurur.  
  
```  
int GetSelItems(
    int nMaxItems,  
    LPINT rgIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nMaxItems`  
 Seçili öğeleri, öğe arabellekte yerleştirilecek numaralarıdır en fazla sayısını belirtir.  
  
 `rgIndex`  
 Tarafından belirtilen tamsayılar sayısı için yeterince büyük bir arabellek için bir işaretçi belirtir `nMaxItems`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arabellekte sıraya alınan öğeleri gerçek sayısıdır. Liste kutusu tek seçimli liste kutusu dönüş değeri ise, `LB_ERR`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]  
  
##  <a name="gettext"></a>  CListBox::GetText  
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
 `nIndex`  
 Alınacak dize sıfır tabanlı dizini belirtir.  
  
 `lpszBuffer`  
 Dizeyi alır arabellek noktalarına. Arabellek dize ve bir sonlandırma null karakter için yeterli alan olmalıdır. Dize boyutu çağırarak önceden belirlenebilir `GetTextLen` üye işlevi.  
  
 `rString`  
 Bir başvuru bir `CString` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sondaki boş karakter hariç dize uzunluğu (bayt cinsinden). Varsa `nIndex` geçerli bir dizin belirtmiyor dönüş değeri **LB_ERR**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üyenin ikinci formun işlev dolgular bir `CString` dize metin içeren nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]  
  
##  <a name="gettextlen"></a>  CListBox::GetTextLen  
 Bir dizenin uzunluğunu bir liste kutusu öğesi alır.  
  
```  
int GetTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Dize sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sondaki boş karakter hariç karakter dizesini uzunluğu. Varsa `nIndex` geçerli bir dizin belirtmiyor dönüş değeri **LB_ERR**.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CListBox::GetText](#gettext).  
  
##  <a name="gettopindex"></a>  CListBox::GetTopIndex  
 Liste kutusunda görünen ilk öğenin sıfır tabanlı dizinini alır.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, liste kutusunda görünen ilk öğenin sıfır tabanlı dizini **LB_ERR** Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlangıçta, liste kutusunu üstünde öğesi 0 olan ancak liste kutusu kaydırırsanız başka bir öğe en üstünde olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]  
  
##  <a name="initstorage"></a>  CListBox::InitStorage  
 Liste kutusu öğeleri depolamak için bellek ayırır.  
  
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
 Başarılı, en fazla sayısını bu öğeler, bir bellek yeniden ayırma, aksi takdirde gerekli önce liste kutusu depolayabilir **LB_ERRSPACE**, yeterli bellek anlamına gelir kullanılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çok sayıda öğelerine eklemeden önce bu işlev çağrısı bir `CListBox`.  
  
 Bu işlev büyük sayıda (100'den fazla) öğe liste kutuları başlatma hızlandırmaya yardımcı olur. Bu nedenle bu sonraki bellek belirtilen miktarı preallocates [AddString](#addstring), [InsertString](#insertstring), ve [Dir](#dir) işlevler en kısa sürede alın. Tahminler parametrelerini kullanabilirsiniz. Overestimate, bazı ek bellek tahsis edilir; daha düşük normal ayırma ön tahsis miktarını aşıyor öğeleri için kullanılır.  
  
 Windows 95/98 yalnızca: `nItems` parametresi için 16 bit değerleri sınırlıdır. Bu liste kutuları birden fazla 32.767 öğeleri içeremez anlamına gelir. Öğe sayısı sınırlı olsa da, liste kutusunda öğelerin toplam boyutu yalnızca kullanılabilir bellek ile sınırlıdır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]  
  
##  <a name="insertstring"></a>  CListBox::InsertString  
 Bir dize liste kutusuna ekler.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Dize eklemek için konumunun sıfır tabanlı dizinini belirtir. Bu parametre -1 ise, dize listesinin sonuna eklenir.  
  
 `lpszItem`  
 Eklenecek null ile sonlandırılmış dizeye noktaları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hangi dize eklenmiş konumu sıfır tabanlı dizini. Dönüş değeri **LB_ERR** bir hata oluşursa; dönüş değeri olan **LB_ERRSPACE** yeni bir dize depolamak yeterli alan olup olmadığını.  
  
### <a name="remarks"></a>Açıklamalar  
 Farklı [AddString](#addstring) üye işlevi `InsertString` bir listesiyle neden olmaz [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) sıralanacak stili.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]  
  
##  <a name="itemfrompoint"></a>  CListBox::ItemFromPoint  
 Liste kutusu öğesi belirtilen noktası en yakın belirler `pt`.  
  
```  
UINT ItemFromPoint(
    CPoint pt,  
    BOOL& bOutside) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 İstemci alanını liste kutusunun sol üst köşesindeki göre belirlenen en yakın öğesi bulunacağı noktası.  
  
 `bOutside`  
 Başvuru bir `BOOL` ayarlanacak değişkeni `TRUE` varsa `pt` yakın liste kutusu öğesi istemci alanın dışındaki `FALSE` varsa `pt` istemci yakın liste kutusu öğesi içinde alanıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen noktasına yakın öğenin dizini `pt`.  
  
### <a name="remarks"></a>Açıklamalar  
 Fare imleci taşır üzerinden hangi liste kutusu öğesi belirlemek için bu işlevi kullanabilirsiniz.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="measureitem"></a>  CListBox::MeasureItem  
 Sahibi çizim stili içeren bir liste kutusu oluşturulduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpMeasureItemStruct`  
 Uzun bir işaretçi bir [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bu üye işlevi geçersiz kılma ve doldurmak `MEASUREITEMSTRUCT` Windows'a liste kutusu boyutlarının bildirmek için yapısı. Liste kutusu ile oluşturulursa [lbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili framework çağırması bu üye işlevi liste kutusunda her bir öğe için. Aksi takdirde, bu üye yalnızca bir kez çağrılır.  
  
 Kullanma hakkında daha fazla bilgi için [lbs_ownerdrawfıxed](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) ile oluşturulan bir sahibi tarafından çizilen liste kutusunda stili `SubclassDlgItem` üye işlevini `CWnd`, tartışmada bkz [Teknik Not 14](../../mfc/tn014-custom-controls.md).  
  
 Bkz: [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) bir açıklaması için `MEASUREITEMSTRUCT` yapısı **.**  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]  
  
##  <a name="resetcontent"></a>  CListBox::ResetContent  
 Bir liste kutusundan tüm öğeleri kaldırır.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]  
  
##  <a name="selectstring"></a>  CListBox::SelectString  
 Aramaları için bir liste kutusu öğesi belirtilen dize ile eşleşen ve eşleşen bir öğe bulunursa, öğeyi seçer.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `nStartAfter`  
 Aranacak ilk öğeden önce öğenin sıfır tabanlı dizini içerir. Arama listesi kutusunun alt kısmındaki ulaştığında, liste kutusunu üstten geri tarafından belirtilen öğeye devam `nStartAfter`. Varsa `nStartAfter` -1 olan tüm liste kutusunu baştan aranır.  
  
 `lpszItem`  
 Aranacak önek içeren null ile sonlandırılmış dize noktalarına. Arama durumu bağımsız olduğundan, bu dizeyi herhangi bir bileşimini büyük ve küçük harfleri içerebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arama başarılı olduysa seçili öğenin dizini. Arama başarısız oldu, dönüş değeri ise **LB_ERR** ve geçerli seçim değiştirilmedi.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu, gerekirse, seçili öğe görünüme getirmek kaydırılan.  
  
 Bu üye işlevi olan bir liste kutusu kullanılamaz [lbs_multıplesel](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili.  
  
 Yalnızca kendi ilk karakter (başlangıç noktasından) tarafından belirtilen dizedeki karakter eşleşiyorsa öğe seçildiğinde `lpszItem`.  
  
 Kullanım `FindString` öğesi seçmeden bir dizeyi bulmak için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]  
  
##  <a name="selitemrange"></a>  CListBox::SelItemRange  
 Birden çok ardışık öğeleri çoklu seçim liste kutusunda seçer.  
  
```  
int SelItemRange(
    BOOL bSelect,  
    int nFirstItem,  
    int nLastItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `bSelect`  
 Seçimi ayarlamak nasıl belirtir. Varsa `bSelect` olan **TRUE**, dize seçilir ve; varsa vurgulanmış **yanlış**, Vurgu kaldırılır ve dize artık seçili.  
  
 `nFirstItem`  
 Ayarlamak için ilk öğenin sıfır tabanlı dizini belirtir.  
  
 `nLastItem`  
 Ayarlamak için en son öğenin sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **LB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu yalnızca çoklu seçim liste kutuları ile kullanın. Yalnızca bir öğe çoklu seçim liste kutusunu gerekiyorsa — diğer bir deyişle, varsa `nFirstItem` eşittir `nLastItem` — çağrı [SetSel](#setsel) üye işlev yerine.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]  
  
##  <a name="setanchorindex"></a>  CListBox::SetAnchorIndex  
 Bağlantı bir Genişletilmiş seçim başlamak için bir çoklu seçim liste kutusunda ayarlar.  
  
```  
void SetAnchorIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Bağlantı olacaktır liste kutusu öğenin sıfır tabanlı dizini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir çoklu seçim liste kutusunda bitişik seçili öğeleri bloğunda ilk veya son öğeye bağlantı öğesidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]  
  
##  <a name="setcaretindex"></a>  CListBox::SetCaretIndex  
 Çoklu seçim liste kutusunda belirtilen dizindeki öğe için odak dikdörtgeni ayarlar.  
  
```  
int SetCaretIndex(
    int nIndex,  
    BOOL bScroll = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Liste kutusunda odak dikdörtgeni almaya öğenin sıfır tabanlı dizini belirtir.  
  
 *bScroll*  
 Bu değer 0 ise, tam olarak görünene kadar öğe kaydırılan. Bu değer değilse 0 ise, öğenin kaydırılan en az kısmen görünür olana kadar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **LB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğe görünür durumda değilse, görünüme kaydırılan.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]  
  
##  <a name="setcolumnwidth"></a>  CListBox::SetColumnWidth  
 Sütunlu liste kutusunda tüm sütunları piksel cinsinden genişliği ayarlar (ile oluşturulan [lbs_multıcolumn](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili).  
  
```  
void SetColumnWidth(int cxWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 `cxWidth`  
 Tüm sütunları piksel cinsinden genişliğini belirtir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]  
  
##  <a name="setcursel"></a>  CListBox::SetCurSel  
 Bir dize seçer ve gerekirse, görünüme kayar.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Parametreler  
 `nSelect`  
 Seçilecek dize sıfır tabanlı dizini belirtir. Varsa `nSelect` -1 ' dir liste kutusu herhangi bir seçim olacak şekilde ayarlanmış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `LB_ERR` bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir dize seçildiğinde, liste kutusunu daha önce seçilen dizeden Vurgu kaldırır.  
  
 Bu üye işlevi yalnızca tek seçim liste kutuları ile kullanın.  
  
 Ayarlamak veya çoklu seçim liste kutusunda bir seçimi kaldırmak için kullanın [CListBox::SetSel](#setsel).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]  
  
##  <a name="sethorizontalextent"></a>  CListBox::SetHorizontalExtent  
 Genişlik olarak bir liste kutusu yatay olarak kaydırılabilir piksel cinsinden ayarlar.  
  
```  
void SetHorizontalExtent(int cxExtent);
```  
  
### <a name="parameters"></a>Parametreler  
 *cxExtent*  
 Piksel olarak liste kutusu yatay olarak kaydırılabilir sayısını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu boyutunu bu değerden daha küçükse, yatay kaydırma çubuğu yatay öğeleri liste kutusunda kaydırma. Liste kutusu gibi büyük veya bu değerden daha büyük ise, yatay kaydırma çubuğu gizlenir.  
  
 Çağrı yanıt verecek şekilde `SetHorizontalExtent`, liste kutusu ile tanımlanmış olmalıdır [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles) stili.  
  
 Bu üye işlevi sütunlu liste kutuları için yararlı değildir. Sütunlu liste kutuları için çağrı `SetColumnWidth` üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]  
  
##  <a name="setitemdata"></a>  CListBox::SetItemData  
 Belirtilen öğe bir liste kutusunda ile ilişkili bir 32-bit değeri ayarlar.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin sıfır tabanlı dizini belirtir.  
  
 `dwItemData`  
 Öğe ile ilişkilendirilecek değeri belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **LB_ERR** bir hata oluşursa.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]  
  
##  <a name="setitemdataptr"></a>  CListBox::SetItemDataPtr  
 Belirtilen öğe belirtilen işaretçisi olacak şekilde bir liste kutusunda ilişkili 32-bit değeri ayarlar ( **void\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin sıfır tabanlı dizini belirtir.  
  
 `pData`  
 Öğeyle ilişkilendirilecek işaretçiyi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **LB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğeler eklendiğinde veya kaldırıldığında gibi öğesi'nin göreli konum liste kutusu içinde değişebilir olsa bile bu işaretçi liste kutusu ömrü için geçerli kalır. Bu nedenle, öğenin dizini kutusunda değiştirebilirsiniz, ancak işaretçi güvenilir kalır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]  
  
##  <a name="setitemheight"></a>  CListBox::SetItemHeight  
 Öğe yüksekliği liste kutusunda ayarlar.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin sıfır tabanlı dizini liste kutusunda belirtir. Bu parametre yalnızca liste kutusu varsa kullanılır **lbs_ownerdrawvarıable** stil; Aksi halde 0 olarak ayarlanmalıdır.  
  
 `cyItemHeight`  
 Öğenin piksel cinsinden yüksekliği belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **LB_ERR** dizin veya yükseklik geçersizse.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu varsa [lbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili, bu işlev tarafından belirtilen öğenin yüksekliğini ayarlar `nIndex`. Aksi takdirde, bu işlev liste kutusunda tüm öğeleri yüksekliğini ayarlar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]  
  
##  <a name="setlocale"></a>  CListBox::SetLocale  
 Bu liste kutusu için yerel ayar kimliğini ayarlar.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Parametreler  
 `nNewLocale`  
 Liste kutusu için ayarlanacak yeni yerel ayar kimliği (LCID) değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu liste kutusu için önceki yerel ayar kimliği (LCID) değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa **SetLocale** çağrılmaz, varsayılan yerel ayar sistemden elde edilir. Denetim Masası ndaki kullanarak bu sistem varsayılan yerel ayar değiştirilebilir bölge (veya uluslararası) uygulama.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]  
  
##  <a name="setsel"></a>  CListBox::SetSel  
 Bir dizeyi bir çoklu seçim liste kutusunda seçer.  
  
```  
int SetSel(
    int nIndex,  
    BOOL bSelect = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Ayarlanacak dize sıfır tabanlı dizini içerir. -1, seçimi eklendiğinde veya değerine bağlı olarak tüm dizeleri kaldırıldı, `bSelect`.  
  
 `bSelect`  
 Seçimi ayarlamak nasıl belirtir. Varsa `bSelect` olan `TRUE`, dize seçilir ve; varsa vurgulanmış `FALSE`, Vurgu kaldırılır ve dize artık seçili. Belirtilen dize seçili ve varsayılan olarak vurgulanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `LB_ERR` bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu yalnızca çoklu seçim liste kutuları ile kullanın.  
  
 Tek seçim liste kutusundan bir öğeyi seçmek için kullanın [CListBox::SetCurSel](#setcursel).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]  
  
##  <a name="settabstops"></a>  CListBox::SetTabStops  
 Liste kutusu sekme durağı konumda ayarlar.  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>Parametreler  
 `cxEachStop`  
 Sekme durakları ayarlama her `cxEachStop` iletişim kutusu birimleri. Bkz: *rgTabStops* iletişim birimi açıklaması.  
  
 `nTabStops`  
 Liste kutusunda sağlamak için sekme durakları sayısını belirtir.  
  
 `rgTabStops`  
 Bir dizinin ilk üye noktalarına iletişim kutusu birimleri sekme durağı konumda içeren tamsayıların. Yatay ve dikey uzaklık bir iletişim birimdir. Bir yatay iletişim biriminin geçerli iletişim temel genişliği biriminin bir-dördüncü için eşit olan ve geçerli iletişim temel yükseklik biriminin bir-sekizinci için bir dikey iletişim birimi eşittir. İletişim kutusu temel birimleri geçerli sistem yazı tipi genişliği ve yüksekliği göre hesaplanır. **GetDialogBaseUnits** Windows işlevi temel birimleri geçerli iletişim piksel cinsinden döndürür. Sekme durakları artan düzende sıralanmış olmalıdır; geri sekmeler izin verilmiyor.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm sekmeleri ayarlarsanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekme durakları 2 iletişim kutusu birimleri varsayılan boyutunu ayarlamak için bu üye işlevi parametresiz sürümü çağırın. Sürümüyle 2 dışındaki bir boyuta sekme durakları ayarlama çağrısı `cxEachStop` bağımsız değişkeni.  
  
 Bir dizi boyutları için sekme durakları ayarlamak için sürümüyle kullanmak `rgTabStops` ve `nTabStops` bağımsız değişkenler. Sekme durağı her değer için ayarlanmış `rgTabStops`, tarafından belirtilen sayıya kadar `nTabStops`.  
  
 Çağrı yanıt verecek şekilde `SetTabStops` üye işlevi, liste kutusunu gerekir oluşturulmuş ile [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]  
  
##  <a name="settopindex"></a>  CListBox::SetTopIndex  
 Belirli liste kutusu öğesi görünür olmasını sağlar.  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Liste kutusu öğenin sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır veya **LB_ERR** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Sistem tarafından belirtilen öğeyi kadar liste kutusu kayar `nIndex` görünür listesinin başında kutusu veya maksimum kaydırma aralığı ulaşıldı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]  
  
##  <a name="vkeytoitem"></a>  CListBox::VKeyToItem  
 Liste kutunun üst pencere aldığında çerçevesi tarafından çağrılır bir `WM_VKEYTOITEM` liste kutusundan ileti.  
  
```  
virtual int VKeyToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nKey`  
 Sanal anahtar kodu anahtarının kullanıcı basılı. Winuser.h bir standart sanal anahtar kodlarının listesi için bkz.  
  
 `nIndex`  
 Liste kutusu şapka geçerli konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür - 2 başka eylem için - 1 varsayılan eylem için veya bir liste kutusu öğesi tuş vuruşu için varsayılan eylem gerçekleştirileceği dizinini belirtmek için negatif olmayan bir sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 `WM_VKEYTOITEM` İleti, aldığında liste kutusu tarafından gönderilen bir `WM_KEYDOWN` yalnızca liste kutusu aşağıdaki her iki sağlayıp sağlamadığını ancak ileti:  
  
-   Sahip [lbs_wantkeyboardınput](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stil kümesi.  
  
-   En az bir öğe içeriyor.  
  
 Hiçbir zaman kendiniz bu işlev çağırmalıdır. Klavye iletileri kendi özel işlenmesini sağlamak için bu işlevi geçersiz kılar.  
  
 Geçersiz kılma gerçekleştirilen hangi eylemini framework bildirmek için bir değer döndürmesi gerekir. Dönüş değeri - 2 uygulamanın tüm yönlerini öğesi seçilerek işlenmiş ve liste kutusu tarafından başka bir eylem gerektiren gösterir. Önce döndürme - 2 ' nin seçimini ayarlayın veya şapka veya her ikisini de taşıyın. Seçimi ayarlamak için kullanın [SetCurSel](#setcursel) veya [SetSel](#setsel). Şapka taşımak için kullanın [SetCaretIndex](#setcaretindex).  
  
 Dönüş değeri - 1, liste kutusunu tuş vuruşu yanıta varsayılan eylem gerçekleştirmesi gereken gösterir. Varsayılan uygulama döndürür - 1.  
  
 Dönüş değeri 0 veya daha büyük bir öğenin dizini liste kutusunda belirtir ve verilen öğe üzerinde tuş vuruşu için liste kutusunu varsayılan eylem yapmanız gerektiğini belirtir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CTRLTEST](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CButton sınıfı](../../mfc/reference/cbutton-class.md)   
 [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)   
 [CEdit sınıfı](../../mfc/reference/cedit-class.md)   
 [CScrollBar sınıfı](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Sınıfı](../../mfc/reference/cstatic-class.md)
