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
ms.openlocfilehash: 1f67107b17f304c5a9c4d6f68d68797370502065
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761189"
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
|[CListBox::CListBox](#clistbox)|Oluşturur bir `CListBox` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CListBox::AddString](#addstring)|Bir dizeyi bir liste kutusuna ekler.|  
|[CListBox::CharToItem](#chartoitem)|Dizeleri yoksa, sahip çizim liste kutuları için işleme özel WM_CHAR sağlamak için geçersiz kılın.|  
|[CListBox::CompareItem](#compareitem)|Bir sıralanmış sahip-çizim liste kutusu yeni bir öğe konumunu belirlemek için framework tarafından çağırılır.|  
|[CListBox::Create](#create)|Windows liste kutusu oluşturur ve ona ekler `CListBox` nesne.|  
|[CListBox::DeleteItem](#deleteitem)|Kullanıcı bir özelleştirilmiş çizimli liste kutusundan bir öğe sildiğinde framework tarafından çağırılır.|  
|[CListBox::DeleteString](#deletestring)|Bir dizeyi bir liste kutusundan siler.|  
|[CListBox::Dir](#dir)|Dosya adları, sürücüler veya her ikisi de geçerli dizindeki bir liste kutusuna ekler.|  
|[CListBox::DrawItem](#drawitem)|Görsel bir özelliği bir sahip çizim liste kutusu değişiklikler olduğunda framework tarafından çağırılır.|  
|[CListBox::FindString](#findstring)|Bir liste kutusunda bir dize arar.|  
|[CListBox::FindStringExact](#findstringexact)|Belirtilen bir dizenin eşleşen ilk liste kutusu dize bulur.|  
|[CListBox::GetAnchorIndex](#getanchorindex)|Geçerli bir bağlantı öğesi bir liste kutusunda sıfır tabanlı dizinini alır.|  
|[CListBox::GetCaretIndex](#getcaretindex)|Birden çok seçim liste kutusuna odak dikdörtgenini olan öğenin dizinini belirler.|  
|[CListBox::GetCount](#getcount)|Dizelerden oluşan bir liste kutusunda döndürür.|  
|[CListBox::GetCurSel](#getcursel)|Bir liste kutusunda seçili dize sıfır tabanlı dizinini döndürür.|  
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|Liste kutusu yatay yönde kaydırılabileceğini piksel cinsinden genişliğini döndürür.|  
|[CListBox::GetItemData](#getitemdata)|Liste kutusu öğesi ile ilişkili 32-bit değeri döndürür.|  
|[CListBox::GetItemDataPtr](#getitemdataptr)|Liste kutusu öğeye bir işaretçi döndürür.|  
|[CListBox::GetItemHeight](#getitemheight)|Öğeleri liste kutusunda yüksekliğini belirler.|  
|[CListBox::GetItemRect](#getitemrect)|Şu anda görüntülenen liste kutusu öğesinin dikdörtgen döndürür.|  
|[CListBox::GetListBoxInfo](#getlistboxinfo)|Sütun başına öğe sayısını alır.|  
|[CListBox::GetLocale](#getlocale)|Liste kutusu için yerel ayar tanımlayıcısını alır.|  
|[CListBox::GetSel](#getsel)|Bir liste kutusu öğesinin seçimi durumunu döndürür.|  
|[CListBox::GetSelCount](#getselcount)|Birden çok seçim liste kutusunda seçili dizeleri sayısını döndürür.|  
|[CListBox::GetSelItems](#getselitems)|Dizinleri şu anda bir liste kutusunda seçili dize döndürür.|  
|[CListBox::GetText](#gettext)|Bir liste kutusu öğesini bir arabelleğe kopyalar.|  
|[CListBox::GetTextLen](#gettextlen)|Bir liste kutusu öğesinin bayt cinsinden uzunluğunu döndürür.|  
|[CListBox::GetTopIndex](#gettopindex)|Bir liste kutusunda görünen ilk dize dizinini döndürür.|  
|[CListBox::InitStorage](#initstorage)|Liste kutusu öğelerini ve dizeler için bellek blokları preallocates.|  
|[CListBox::InsertString](#insertstring)|Bir liste kutusundaki belirli bir konumda bir dize ekler.|  
|[CListBox::ItemFromPoint](#itemfrompoint)|Bir nokta en yakın liste kutusu öğenin dizinini döndürür.|  
|[CListBox::MeasureItem](#measureitem)|Liste kutusu boyutları belirlemek için bir sahip çizim liste kutusu oluşturulduğunda framework tarafından çağırılır.|  
|[CListBox::ResetContent](#resetcontent)|Bir liste kutusundan tüm girişlerini temizler.|  
|[CListBox::SelectString](#selectstring)|Arar ve bir dize içinde tek seçim liste kutusu seçer.|  
|[CListBox::SelItemRange](#selitemrange)|Seçer veya çoklu seçim liste kutusu dizelerde aralığı seçimini kaldırır.|  
|[CListBox::SetAnchorIndex](#setanchorindex)|Yer işareti genişletilmiş bir seçim başlamak için bir çoklu seçim liste kutusu ayarlar.|  
|[CListBox::SetCaretIndex](#setcaretindex)|Birden çok seçim liste kutusunda belirtilen dizindeki öğenin odak dikdörtgenini ayarlar.|  
|[CListBox::SetColumnWidth](#setcolumnwidth)|Bir çoklu sütun liste kutusunu sütun genişliğini belirler.|  
|[CListBox::SetCurSel](#setcursel)|Bir liste kutusu dize seçer.|  
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|Liste kutusu yatay yönde kaydırılabileceğini piksel cinsinden genişliğini belirler.|  
|[CListBox::SetItemData](#setitemdata)|Liste kutusu öğesi ile ilişkili 32-bit değeri ayarlar.|  
|[CListBox::SetItemDataPtr](#setitemdataptr)|Bir işaretçi liste kutusu öğesini ayarlar.|  
|[CListBox::SetItemHeight](#setitemheight)|Öğe yüksekliğini bir liste kutusunda ayarlar.|  
|[CListBox::SetLocale](#setlocale)|Liste kutusu yerel ayar tanımlayıcısı ayarlar.|  
|[CListBox::SetSel](#setsel)|Seçer veya birden çok seçim liste kutusu bir liste kutusu öğe seçimini kaldırır.|  
|[CListBox::SetTabStops](#settabstops)|Bir liste kutusunun sekme durağı konumda ayarlar.|  
|[CListBox::SetTopIndex](#settopindex)|Bir liste kutusunda görünen ilk dize sıfır tabanlı dizinini ayarlar.|  
|[CListBox::VKeyToItem](#vkeytoitem)|Liste kutuları ile lbs_wantkeyboardınput stil kümesi için işleme özel WM_KEYDOWN sağlamak için geçersiz kılın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Liste kutusu, kullanıcının görüntüleyebileceği ve seçin dosya adları gibi öğeleri listesini görüntüler.  
  
 Tek seçim liste kutusunda, kullanıcının yalnızca bir öğe seçebilirsiniz. Birden çok seçim liste kutusu içinde bir öğe aralığı seçilebilir. Kullanıcı bir öğe seçtiğinde vurgulanır ve liste kutusunun üst penceresine bir bildirim iletisi gönderir.  
  
 Liste kutusu, bir iletişim kutusu şablonundan ya da kodunuzda doğrudan oluşturabilirsiniz. Doğrudan oluşturmak için oluşturmak `CListBox` nesnesi ve ardından arama [Oluştur](#create) Windows liste kutusu denetimi oluşturma ve buna eklemek için üye işlevini `CListBox` nesne. Bir liste kutusunda bir iletişim şablonunu kullanmak için iletişim kutusu sınıfında bir liste kutusu değişkeni bildirir ve ardından kullanın `DDX_Control` iletişim kutusu sınıfın içinde `DoDataExchange` denetime üye değişkeni bağlanmak için işlevi. (iletişim kutusu sınıfı bir denetim değişkeni eklediğiniz zaman bu sizin için otomatik olarak gerçekleştirilir.)  
  
 Yapı, türetilen bir sınıf tek adımlı işlemde olabilir `CListBox`. Bir oluşturucu çağrı ve türetilen sınıf için yazma `Create` gelen oluşturucu içinde.  
  
 Liste kutusu tarafından yollanır Windows bildirim iletilerini işlemek isterseniz (öğesinden türetilmiş bir sınıf genellikle [CDialog](../../mfc/reference/cdialog-class.md)), üst sınıfın her ileti için ileti eşleme girişi ve ileti işleyicisi üye işlevi ekleyin.  
  
 Her ileti eşleme girişi aşağıdaki biçimi alır:  
  
 `ON_Notification( id, memberFxn )`  
  
 Burada `id` bildirimi gönderilmesi liste kutusu denetimi alt pencere Kimliğini belirtir ve `memberFxn` bildirimini işlemek için yazdığınız üst üye işlev adıdır.  
  
 Üst öğenin işlev prototipi aşağıdaki gibidir:  
  
 `afx_msg void memberFxn( );`  
  
 Olası ileti eşlemesi girişleri ve açıklamasını, bunların üst gönderilecek örneklerinin listesi aşağıda verilmiştir:  
  
- ON_LBN_DBLCLK kullanıcı çift tıkladığında bir liste kutusunda bir dize. İçeren bir liste kutusu [lbs_notıfy](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili, bu bildirim iletisi gönderir.  
  
- Liste kutusu ON_LBN_ERRSPACE isteği karşılamak için yeterli bellek ayrılamıyor.  
  
- Giriş odağını kaybetmekte ON_LBN_KILLFOCUS liste kutusu.  
  
- ON_LBN_SELCANCEL geçerli liste kutusu seçimi iptal edildi. Bu ileti yalnızca bir liste kutusu lbs_notıfy stilde gönderilir.  
  
- Seçimi liste kutusunda ON_LBN_SELCHANGE değişti. Seçimi tarafından değiştirilirse bu bildirim gönderilmez [CListBox::SetCurSel](#setcursel) üye işlevi. Bu bildirim yalnızca lbs_notıfy stilde liste kutusu için geçerlidir. Her kullanıcı bir ok tuşuna bastığında bile seçimin değişmez için birden çok seçim liste kutusu LBN_SELCHANGE bildirim iletisi gönderilir.  
  
- Liste kutusu ON_LBN_SETFOCUS giriş odağını alıyor.  
  
- Koşulsuz olan bir sahip çizim liste kutusu ON_WM_CHARTOITEM WM_CHAR mesajı alır.  
  
- Lbs_wantkeyboardınput stiliyle ON_WM_VKEYTOITEM bir liste kutusu WM_KEYDOWN iletisi alır.  
  
 Oluşturursanız, bir `CListBox` nesnesi içinde bir iletişim kutusu (iletişim kaynak) aracılığıyla `CListBox` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.  
  
 Oluşturursanız, bir `CListBox` nesne bir pencere içinde yok etmek gerekebilir `CListBox` nesne. Oluşturursanız `CListBox` yığında nesne otomatik olarak bozulur. Oluşturursanız `CListBox` kullanarak yığında nesne **yeni** işlevini çağırmalıdır **Sil** kullanıcı üst pencere kapandığında yok etmek için nesne üzerinde.  
  
 Herhangi bir bellek ayırdığınızda `CListBox` nesne, geçersiz kılma `CListBox` ayırma atmayı yıkıcı.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListBox`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="addstring"></a>  CListBox::AddString  
 Bir dizeyi bir liste kutusuna ekler.  
  
```  
int AddString(LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszItem*  
 Eklenecek null ile sonlandırılmış dizeye işaret eder.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda dizeye sıfır tabanlı dizini. Dönüş değeri LB_ERR ise bir hata oluşur. dönüş değeri LB_ERRSPACE ise yeni bir dize depolamak yeterli alan kullanılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu ile oluşturulmamışsa [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili, dize, listenin sonuna eklenir. Aksi takdirde, dize listesine eklenir ve Liste sıralanmıştır. Liste kutusu LBS_SORT stil ile oluşturulmuşsa, ama [lbs_hasstrıngs](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili framework listeyi sıralar için bir veya daha fazla çağrılar tarafından `CompareItem` üye işlevi.  
  
 Kullanım [InsertString](#insertstring) liste kutusunun içinde belirli bir konumun bir dize eklemek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]  
  
##  <a name="chartoitem"></a>  CListBox::CharToItem  
 Liste kutusunun ana pencereye liste kutusundan WM_CHARTOITEM ileti aldığında framework tarafından çağırılır.  
  
```  
virtual int CharToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *nKey*  
 ANSI kod kullanıcı yazılan karakter.  
  
 *nIndex*  
 Liste kutusu giriş işaretini geçerli konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür - 1 veya - başka bir eylem veya tuş vuruşu için varsayılan eylem gerçekleştirmek için bir liste kutusu öğesinin bir dizin belirtmek için negatif olmayan bir sayı için 2. Varsayılan uygulama döndürür - 1.  
  
### <a name="remarks"></a>Açıklamalar  
 WM_CHAR mesajı aldığında, ancak liste kutusu aşağıdaki ölçütlerin tamamını karşılıyorsa, WM_CHARTOITEM ileti liste kutusu tarafından gönderilir:  
  
-   Bir sahip çizim liste kutusu bulunur.  
  
-   Olmayan [lbs_hasstrıngs](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stil kümesi.  
  
-   En az bir öğe var.  
  
 Hiçbir zaman kendiniz bu işlevini çağırmalıdır. Klavye iletileri kendi özel işleme sağlamak için bu işlevi geçersiz kılar.  
  
 Geçersiz kılmada framework gerçekleştirdiğiniz eylemi bildirmek için bir değer döndürmesi gerekir. Dönüş değeri - 1 veya - 2 öğeyi seçerek tüm yönlerini işlenmiş ve liste kutusu tarafından başka bir eylem gerektiren gösterir. Sonuç döndürülmeden önce - 1 veya - 2, seçimini ayarlayın veya klavyeyle veya her ikisini de taşıyın. Seçimi ayarlamak için kullanın [SetCurSel](#setcursel) veya [SetSel](#setsel). Giriş işaretini taşımanız [SetCaretIndex](#setcaretindex).  
  
 Dönüş değeri 0 veya daha büyük, liste kutusunda bir öğenin dizinini belirtir ve liste kutusu tuş vuruşu verilen öğe üzerinde için varsayılan eylem gerçekleştirmesini gösterir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]  
  
##  <a name="clistbox"></a>  CListBox::CListBox  
 Oluşturur bir `CListBox` nesne.  
  
```  
CListBox();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CListBox` iki adımda nesne. İlk olarak, oluşturucusunu `ClistBox` ve sonra çağrı `Create`, Windows liste kutusu başlatır ve ekler `CListBox`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]  
  
##  <a name="compareitem"></a>  CListBox::CompareItem  
 Bir sıralanmış sahip-çizim liste kutusu yeni bir öğe göreli konumunu belirlemek için framework tarafından çağırılır.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpCompareItemStruct*  
 Uzun bir işaretçi bir `COMPAREITEMSTRUCT` yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açıklanan iki öğenin göreli konumunu belirten [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) yapısı. Aşağıdaki değerlerden herhangi biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|-1|Öğe 1 öğe 2 önce sıralar.|  
|0|Öğe 1 ve 2 öğe aynı sıralama.|  
|1.|Öğe 1 öğe 2 sonra sıralar.|  
  
 Bkz: [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) açıklamasını `COMPAREITEMSTRUCT` yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. LBS_SORT stiliyle bir sahip çizim liste kutusu oluşturursanız, yeni liste kutusuna eklenen öğeleri sıralama yordamlarında framework yardımcı olması için bu üye işlevini geçersiz kılmanız gerekir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]  
  
##  <a name="create"></a>  CListBox::Create  
 Windows liste kutusu oluşturur ve ona ekler `CListBox` nesne.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwStyle*  
 Liste kutusu stilini belirtir. Herhangi bir birleşimini uygulamak [liste kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) kutusu.  
  
 *Rect*  
 Liste kutusu boyutunu ve konumunu belirtir. Olabilir bir `CRect` nesnesi veya bir `RECT` yapısı.  
  
 *pParentWnd*  
 Liste kutusunun ana penceresi belirtir (genellikle bir `CDialog` nesne). NULL olmamalıdır.  
  
 *nID*  
 Liste kutusunun denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CListBox` iki adımda nesne. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, Windows liste kutusu başlatır ve ekler `CListBox` nesne.  
  
 Zaman `Create` yürütür, Windows gönderir [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Liste kutusu denetim iletileri.  
  
 Bu iletiler tarafından varsayılan olarak işlenir [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [Ongetminmaxınfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) üye işlevleri içinde `CWnd` temel sınıfı. Varsayılan ileti işleme genişletmek için öğesinden bir sınıf türetin `CListBox`, yeni sınıfa ileti eşlemesi ekleyin ve önceki ileti işleyicisi üye işlevleri geçersiz kılar. Geçersiz kılma `OnCreate`, örneğin, gerekli başlatma için yeni bir sınıf gerçekleştirmek için.  
  
 Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) için bir liste kutusu denetimi.  
  
- WS_CHILD her zaman  
  
- Ws_vısıble genellikle  
  
- Ws_dısabled nadiren  
  
- WS_VSCROLL için dikey kaydırma çubuğu ekleyin  
  
- WS_HSCROLL için yatay kaydırma çubuğu ekleyin  
  
- WS_GROUP grup denetimleri için  
  
- WS_TABSTOP izin vermek için bu denetimin sekme  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]  
  
##  <a name="deleteitem"></a>  CListBox::DeleteItem  
 Kullanıcı bir öğeyi bir özelleştirilmiş çizimli sildiğinde framework tarafından çağırılır `CListBox` nesne veya liste kutusunu yok eder.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpDeleteItemStruct*  
 Bir Windows uzun bir işaretçiye [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) olan silinmiş öğenin hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevin varsayılan uygulama, hiçbir şey yapmaz. Bu işlev bir sahip çizim liste kutusu gerektiği gibi yeniden çizmek için geçersiz kılın.  
  
 Bkz: [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) açıklamasını `DELETEITEMSTRUCT` yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]  
  
##  <a name="deletestring"></a>  CListBox::DeleteString  
 Konumdaki öğeyi siler *nIndex* liste kutusundan.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Silinecek dize sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listede kalan dizeleri sayısı. Dönüş değeri LB_ERR ise *nIndex* listesindeki öğeleri sayısından daha büyük bir dizini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tüm öğeleri *nIndex* artık bir pozisyon aşağı taşıyın. Örneğin, bir liste kutusu iki öğe içeriyorsa, ilk öğenin silinmesi artık ilk konumda kalan öğeyi neden olur. *nIndex*= 0 öğenin ilk konumu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]  
  
##  <a name="dir"></a>  CListBox::Dir  
 Dosya adları, sürücüleri ya da her ikisini bir liste kutusu listesi ekler.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Parametreler  
 *attr*  
 Herhangi bir birleşimi olabilir **enum** değerleri açıklanan `CFile::GetStatu` [s](../../mfc/reference/cfile-class.md#getstatus), ya da herhangi bir birleşimini aşağıdaki değerleri:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|0x0000|Dosya okunamıyor veya yazılamıyor.|  
|0x0001|Dosya okuma ancak yazılan değil.|  
|0x0002|Dosya, gizli ve dizin listesinde görüntülenmez.|  
|0x0004|Dosya sistemi dosyadır.|  
|0x0010|Tarafından belirtilen adı *lpszWildCard* bir dizini belirtir.|  
|0x0020|Dosya arşivlendi.|  
|0x4000|Tarafından belirtilen adla eşleşen tüm sürücüleri dahil *lpszWildCard*.|  
|0x8000|Özel bayrak. Özel bayrağı ayarlandıysa, yalnızca belirtilen türde dosyalar listelenir. Aksi takdirde, belirtilen türdeki dosyaları "normal" dosyalarına ek olarak listelenir.|  
  
 *lpszWildCard*  
 Bir dosya belirtimi dize işaret eder. Dize, joker karakterler içerebilir (örneğin, *.\*).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listeye eklenen son filename sıfır tabanlı dizini. Dönüş değeri LB_ERR ise bir hata oluşur. dönüş değeri LB_ERRSPACE ise yeni dizeleri depolamak yeterli alan kullanılabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]  
  
##  <a name="drawitem"></a>  CListBox::DrawItem  
 Görsel bir özelliği bir sahip çizim liste kutusu değişiklikler olduğunda framework tarafından çağırılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpDrawItemStruct*  
 Uzun bir işaretçi bir [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) gerekli çizim türü hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `itemAction` Ve `itemState` üyeleri `DRAWITEMSTRUCT` yapısı gerçekleştirilecek çizim eylemi tanımlayın.  
  
 Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Sahip çizim için çizim uygulamak için bu üye işlevi geçersiz kılma `CListBox` nesne. Uygulama görünen bağlam sağlanan için seçilen tüm grafik cihaz arabirimi (GDI) nesneleri geri yüklemeniz gerekir *lpDrawItemStruct* önce bu üye işlevi sonlandırır.  
  
 Bkz: [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) açıklamasını `DRAWITEMSTRUCT` yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]  
  
##  <a name="findstring"></a>  CListBox::FindString  
 Liste kutusu seçimi değiştirmeden Belirtilen önek içeren bir liste kutusu ilk dize bulur.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nStartAfter*  
 Aranacak ilk öğeden önce öğenin sıfır tabanlı dizinini içerir. Arama liste kutusunun alt kısmındaki ulaştığında, liste kutusunun üst kısmından geri tarafından belirtilen öğe için devam *nStartAfter*. Varsa *nStartAfter* -1 olan tüm liste kutusu baştan aranır.  
  
 *lpszItem*  
 Aranacak önek içeren boş sonlandırılmış dizeye işaret eder. Arama çalışması bağımsız olduğundan, bu dizenin herhangi bir bileşimini büyük ve küçük harfler içerebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen bir öğe veya arama başarısız olmuşsa LB_ERR sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [SelectString](#selectstring) bulmak ve bir dize seçmek için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]  
  
##  <a name="findstringexact"></a>  CListBox::FindStringExact  
 İçinde belirtilen dize eşleşen ilk liste kutusu dize bulur *lpszFind*.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndexStart*  
 Aranacak ilk öğeden önce öğenin sıfır tabanlı dizinini belirtir. Arama liste kutusunun alt kısmındaki ulaştığında, liste kutusunun üst kısmından geri tarafından belirtilen öğe için devam *nIndexStart*. Varsa *nIndexStart* -1 olan tüm liste kutusu baştan aranır.  
  
 *lpszFind*  
 Aramak için null ile sonlandırılmış dizeye işaret eder. Bu dize, tam dosya adı uzantısı dahil olmak üzere, içerebilir. Arama büyük/küçük harfe duyarlı değil dize herhangi bir bileşimini büyük ve küçük harfler içerebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen bir öğe veya arama başarısız olmuşsa LB_ERR dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusunda bir özelleştirilmiş çizimli stiliyle olmadan oluşturulduysa [lbs_hasstrıngs](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili `FindStringExact` üye işlevi çalışır değerini karşı doubleword değerle eşleşecek şekilde *lpszFind*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]  
  
##  <a name="getanchorindex"></a>  CListBox::GetAnchorIndex  
 Liste kutusunda geçerli bağlayıcı öğenin sıfır tabanlı dizinini alır.  
  
```  
int GetAnchorIndex() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin dizini geçerli bağlayıcı, başarılı olursa; Aksi takdirde LB_ERR.  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok seçim liste kutusunda, ilk veya son öğeye bitişik seçilen öğelerin bir blok içinde yer işareti öğesidir.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="getcaretindex"></a>  CListBox::GetCaretIndex  
 Birden çok seçim liste kutusuna odak dikdörtgenini olan öğenin dizinini belirler.  
  
```  
int GetCaretIndex() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir liste kutusunda odak dikdörtgenini olan öğenin sıfır tabanlı dizini. Tek seçim liste kutusu liste kutusunun ise dönüş değeri seçili öğe varsa dizinidir.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğesi olabilir veya seçili değildir.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CListBox::SetCaretIndex](#setcaretindex).  
  
##  <a name="getcount"></a>  CListBox::GetCount  
 Bir liste kutusunda öğe sayısını alır.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusu ya da bir hata oluşursa LB_ERR öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen sayı değerinden dizinini (sıfır tabanlı dizindir) son öğenin biridir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]  
  
##  <a name="getcursel"></a>  CListBox::GetCurSel  
 Tek seçim liste kutusunda seçili öğenin sıfır tabanlı dizinini alır  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek seçim liste kutusu ise seçili öğenin sıfır tabanlı dizini. Şu anda hiçbir öğe seçili değilse LB_ERR var.  
  
 Birden çok seçim liste kutusunda odağa sahip öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmayın `GetCurSel` birden çok seçim liste kutusu için. Kullanım [CListBox::GetSelItems](#getselitems) yerine.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]  
  
##  <a name="gethorizontalextent"></a>  CListBox::GetHorizontalExtent  
 Liste kutusundan, bu yatay yönde kaydırılabileceğini piksel cinsinden genişliğini alır.  
  
```  
int GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırılabilir liste kutusunda piksel genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlem yalnızca liste kutusunda yatay kaydırma çubuğu varsa geçerlidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]  
  
##  <a name="getitemdata"></a>  CListBox::GetItemData  
 Belirtilen liste kutusu öğeyle ilişkili uygulama tarafından sağlanan doubleword değeri alır.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Liste kutusunda öğenin sıfır tabanlı dizinini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa öğe veya LB_ERR ile ilişkili 32-bit değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Doubleword değerindeydi *dwItemData* parametresinin bir [Setıtemdata](#setitemdata) çağırın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]  
  
##  <a name="getitemdataptr"></a>  CListBox::GetItemDataPtr  
 Bir işaretçi olarak belirtilen liste kutusu öğesi ile ilişkilendirilmiş uygulama tarafından sağlanan 32-bit değerini alır (**void** <strong>\*</strong>).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Liste kutusunda öğenin sıfır tabanlı dizinini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa bir işaretçi veya -1 alır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]  
  
##  <a name="getitemheight"></a>  CListBox::GetItemHeight  
 Öğeleri liste kutusunda yüksekliğini belirler.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Liste kutusunda öğenin sıfır tabanlı dizinini belirtir. Bu parametre yalnızca liste kutusu lbs_ownerdrawvarıable stili varsa kullanılır. Aksi durumda 0 olarak ayarlanmalıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri liste kutusunda piksel cinsinden yüksekliği. Liste kutusu varsa [lbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili, dönüş değeri, tarafından belirtilen öğe yüksekliğini *nIndex*. Bir hata oluşursa, dönüş değeri LB_ERR ' dir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]  
  
##  <a name="getitemrect"></a>  CListBox::GetItemRect  
 Şu anda liste kutusu penceresinde görüntülenen boyutlar dikdörtgenin bu sınırları bir liste kutusu öğesini alır.  
  
```  
int GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Öğenin sıfır tabanlı dizinini belirtir.  
  
 *lpRect*  
 Uzun bir işaretçiye belirtir bir [RECT yapısı](../../mfc/reference/rect-structure1.md) , öğenin liste kutusu istemci koordinatlarını alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa LB_ERR.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]  
  
##  <a name="getlistboxinfo"></a>  CListBox::GetListBoxInfo  
 Sütun başına öğe sayısını alır.  
  
```  
DWORD GetListBoxInfo() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sütunun başına öğe sayısı `CListBox` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğine öykünür [LB_GETLISTBOXINFO](/windows/desktop/Controls/lb-getlistboxinfo) Windows SDK içinde açıklandığı gibi ileti.  
  
##  <a name="getlocale"></a>  CListBox::GetLocale  
 Liste kutusu tarafından kullanılan yerel ayarları alır.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda dizeleri için yerel ayar tanıtıcısı (LCID) değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerel ayar, örneğin, dizelerin sıralı liste kutusu sıralama düzeninin belirlemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CListBox::SetLocale](#setlocale).  
  
##  <a name="getsel"></a>  CListBox::GetSel  
 Bir öğe seçimi durumunu alır.  
  
```  
int GetSel(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Öğenin sıfır tabanlı dizinini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen öğe seçili değilse pozitif bir sayı; Aksi halde, 0'dır. Bir hata oluşursa dönüş LB_ERR değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi, hem tek ve birden çok seçim liste kutuları ile çalışır.  
  
 Dizin şu anda seçili liste kutusu öğesini almak için kullanın [CListBox::GetCurSel](#getcursel).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]  
  
##  <a name="getselcount"></a>  CListBox::GetSelCount  
 Birden çok seçim liste kutusunda seçili öğeleri toplam sayısını alır.  
  
```  
int GetSelCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir liste kutusunda seçili öğelerin sayısı. Tek seçim liste kutusu liste kutusunun ise, dönüş değeri LB_ERR ' dir.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CListBox::GetSelItems](#getselitems).  
  
##  <a name="getselitems"></a>  CListBox::GetSelItems  
 Birden çok seçim liste kutusunda seçili öğelerin öğesi numaraları belirten bir tamsayı dizisi olan bir arabellek doldurur.  
  
```  
int GetSelItems(
    int nMaxItems,  
    LPINT rgIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nMaxItems*  
 En fazla arabellek yerleştirilecek olan öğesi numaraları olan seçili öğe sayısını belirtir.  
  
 *rgIndex*  
 Arabellek sayısı tarafından belirtilen tamsayılar için yeterince büyük bir işaretçiye belirtir *nMaxItems*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerçek öğe sayısını arabellekteki yerleştirilir. Tek seçim liste kutusu liste kutusunun ise, dönüş değeri olduğu `LB_ERR`.  
  
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
 *nIndex*  
 Alınacak dize sıfır tabanlı dizini belirtir.  
  
 *lpszBuffer*  
 Dize alan arabellek işaret eder. Arabellek, dize ve bir sonlandırıcı null karakter için yeterli alan olmalıdır. Dize boyutu çağırarak önceden belirlenebilir `GetTextLen` üye işlevi.  
  
 *rString*  
 Bir başvuru bir `CString` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sondaki null karakter hariç, dizenin uzunluğu (bayt cinsinden). Varsa *nIndex* geçerli bir dizin belirtmiyor LB_ERR dönüş değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci form, bu üye işlev dolgular bir `CString` dize metin içeren nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]  
  
##  <a name="gettextlen"></a>  CListBox::GetTextLen  
 Bir liste kutusu öğesini bir dizenin uzunluğunu alır.  
  
```  
int GetTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Dize sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sondaki null karakter hariç en çok karakter dizenin uzunluğu. Varsa *nIndex* geçerli bir dizin belirtmiyor LB_ERR dönüş değeridir.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CListBox::GetText](#gettext).  
  
##  <a name="gettopindex"></a>  CListBox::GetTopIndex  
 Bir liste kutusunda ilk görünür öğenin sıfır tabanlı dizinini alır.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, bir liste kutusunda görünür bir ilk öğenin sıfır tabanlı dizinini LB_ERR Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlangıçta, liste kutusunun üstünde öğesi 0 olan, ancak liste kutusu kaydırırsanız, başka bir öğe üst kısmında olabilir.  
  
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
 *nItems*  
 Eklenecek öğe sayısını belirtir.  
  
 *nBytes*  
 Öğesi dizeleri için ayrılacak bayt cinsinden bellek miktarını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, liste kutusunda bir bellek reallocation önce depolayabilirsiniz öğelerin maksimum sayı olup olmadığını gerekli, aksi takdirde LB_ERRSPACE, yeterli bellek kullanılabilir olmayan anlamına gelir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çok sayıda öğeleri eklemeden önce bu işlevi çağırın bir `CListBox`.  
  
 Bu işlev, özel olarak çok sayıda (100'den fazla) öğe olan liste kutuları başlatma sürecinin hızlanmasına yardımcı olur. Bu nedenle, sonraki bellek belirtilen miktarı preallocates [AddString](#addstring), [InsertString](#insertstring), ve [Dir](#dir) işlevler en kısa sürede alır. Tahminleri parametrelerini kullanabilirsiniz. Overestimate, bazı ek bellek tahsis edilmez; çoğu kişinin hafife aldığı, normal ayırma ön tahsis miktarınızı aşan öğeleri için kullanılır.  
  
 Windows 95/98 yalnızca: *nItems* 16 bitlik değerler için parametre sınırlıdır. Başka bir deyişle, liste kutuları 32.767'den fazla öğe içeremez. Öğe sayısını kısıtlı olsa da, bir liste kutusu öğeleri toplam boyutu yalnızca kullanılabilir bellekle sınırlıdır.  
  
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
 *nIndex*  
 Dizeyi eklemek için konumun sıfır tabanlı dizini belirtir. Bu parametreyi -1 ise, dize, listenin sonuna eklenir.  
  
 *lpszItem*  
 Eklenecek olan boş sonlandırılmış dizeye işaret eder.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hangi dize eklenmiş konumu sıfır tabanlı dizini. Dönüş değeri LB_ERR ise bir hata oluşur. dönüş değeri LB_ERRSPACE ise yeni bir dize depolamak yeterli alan kullanılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Farklı [AddString](#addstring) üye işlevini `InsertString` bir listesiyle neden olmaz [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) sıralanacak stili.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]  
  
##  <a name="itemfrompoint"></a>  CListBox::ItemFromPoint  
 Liste kutusu öğe belirtilen noktası en yakın belirler *pt*.  
  
```  
UINT ItemFromPoint(
    CPoint pt,  
    BOOL& bOutside) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *PT*  
 Liste kutusu istemci alanını sol üst köşesine göre belirlenen en yakın öğesi bulunacağı gelin.  
  
 *bOutside*  
 Gerekirse TRUE ayarlanan bir BOOL değişken başvurusu *pt* istemci alanı yakın liste kutusu öğesinin FALSE ise *pt* yakın liste kutusu öğesinin istemci alanı içinde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen noktasına yakın öğenin dizinini *pt*.  
  
### <a name="remarks"></a>Açıklamalar  
 Fare imleci taşır üzerinden hangi liste kutusu öğesinin belirlemek için bu işlevi kullanabilirsiniz.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="measureitem"></a>  CListBox::MeasureItem  
 Sahip çizim stili bir liste kutusu oluşturulduğunda framework tarafından çağırılır.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMeasureItemStruct*  
 Uzun bir işaretçi bir [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bu üye işlevini geçersiz kılabilir ve doldurun `MEASUREITEMSTRUCT` Windows liste kutusu boyutlarının bildirmek için yapısı. Liste kutusu ile oluşturulursa [lbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili framework çağıran bu üye işlevi liste kutusunda her bir öğe için. Aksi takdirde, bu üye, yalnızca bir kez çağrılır.  
  
 Kullanma hakkında daha fazla bilgi için [lbs_ownerdrawfıxed](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) ile oluşturulan bir sahip çizim liste kutusu stilinde `SubclassDlgItem` üye işlevinin `CWnd`, içindeki tartışmalara bakın [Teknik Not 14](../../mfc/tn014-custom-controls.md).  
  
 Bkz: [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) açıklamasını `MEASUREITEMSTRUCT` yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]  
  
##  <a name="resetcontent"></a>  CListBox::ResetContent  
 Tüm öğeleri bir liste kutusundan kaldırır.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]  
  
##  <a name="selectstring"></a>  CListBox::SelectString  
 Aramalar için bir liste kutusu öğesi, belirtilen dizeyle eşleşir ve eşleşen bir öğe bulunursa, bu öğeyi seçer.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *nStartAfter*  
 Aranacak ilk öğeden önce öğenin sıfır tabanlı dizinini içerir. Arama liste kutusunun alt kısmındaki ulaştığında, liste kutusunun üst kısmından geri tarafından belirtilen öğe için devam *nStartAfter*. Varsa *nStartAfter* -1 olan tüm liste kutusu baştan aranır.  
  
 *lpszItem*  
 Aranacak önek içeren boş sonlandırılmış dizeye işaret eder. Arama çalışması bağımsız olduğundan, bu dizenin herhangi bir bileşimini büyük ve küçük harfler içerebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arama başarılı olursa seçilen öğenin dizini. Arama başarısız olmuşsa LB_ERR dönüş değeridir ve geçerli seçimi değiştirilmez.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusunda, seçili öğenin görüntülenebilmesi gerekirse kaydırılan.  
  
 Bu üye işlevi olan bir liste kutusu kullanılamaz [lbs_multıplesel](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili.  
  
 Yalnızca kendi ilk karakterleri (başlangıç noktasından) tarafından belirtilen dizedeki karakterlerle eşleşen, bir öğe seçildiğinde *lpszItem*.  
  
 Kullanım `FindString` öğesini seçmeden bir dizeyi bulmak için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]  
  
##  <a name="selitemrange"></a>  CListBox::SelItemRange  
 Birden çok seçim liste kutusunda birden fazla ardışık öğeleri seçer.  
  
```  
int SelItemRange(
    BOOL bSelect,  
    int nFirstItem,  
    int nLastItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *bGüvenlik ayarlarını*  
 Seçimi ayarlama işlemini belirtir. Varsa *bGüvenlik ayarlarını* doğru ise, dize seçili ve vurgulanmış; FALSE ise Vurgusu kaldırılır ve dize artık seçilir.  
  
 *nFirstItem*  
 Ayarlamak için ilk öğenin sıfır tabanlı dizinini belirtir.  
  
 *nLastItem*  
 Ayarlanacak son öğenin sıfır tabanlı dizinini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa LB_ERR.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi, yalnızca birden çok seçim liste kutuları ile kullanın. Birden çok seçim liste kutusu içinde yalnızca bir öğe seçmeniz gerekiyorsa — diğer bir deyişle, *nFirstItem* eşittir *nLastItem* — çağrı [SetSel](#setsel) üye işlevini yerine.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]  
  
##  <a name="setanchorindex"></a>  CListBox::SetAnchorIndex  
 Yer işareti genişletilmiş bir seçim başlamak için bir çoklu seçim liste kutusu ayarlar.  
  
```  
void SetAnchorIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Yer işareti olacak liste kutusu öğesinin sıfır tabanlı dizinini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok seçim liste kutusunda, ilk veya son öğeye bitişik seçilen öğelerin bir blok içinde yer işareti öğesidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]  
  
##  <a name="setcaretindex"></a>  CListBox::SetCaretIndex  
 Birden çok seçim liste kutusunda belirtilen dizindeki öğenin odak dikdörtgenini ayarlar.  
  
```  
int SetCaretIndex(
    int nIndex,  
    BOOL bScroll = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Liste kutusunda odak dikdörtgenini almak için öğenin sıfır tabanlı dizinini belirtir.  
  
 *bScroll*  
 Bu değer 0 ise, tam olarak görünene kadar öğe kaydırılan. Bu değer ise 0 öğe kaydırılan en azından kısmen görünür olana kadar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa LB_ERR.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğe görünür değilse, görünüme kaydırılan.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]  
  
##  <a name="setcolumnwidth"></a>  CListBox::SetColumnWidth  
 Bir çoklu sütun liste kutusunda tüm sütunları piksel cinsinden genişliğini ayarlar (ile oluşturulan [lbs_multıcolumn](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili).  
  
```  
void SetColumnWidth(int cxWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 *cxWidth*  
 Tüm sütunları piksel cinsinden genişliğini belirtir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]  
  
##  <a name="setcursel"></a>  CListBox::SetCurSel  
 Bir dize seçer ve gerekirse, görünüme kaydırır.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Parametreler  
 *Seçin*  
 Seçilecek dize sıfır tabanlı dizini belirtir. Varsa *Seç Ntümünü* -1, liste kutusunda seçim için ayarlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa LB_ERR.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir dize seçildiğinde, liste kutusu vurgulama daha önce seçilen dizeden kaldırır.  
  
 Bu üye işlevi yalnızca tek seçim liste kutuları ile kullanın.  
  
 Ayarlamak veya birden çok seçim liste kutusunda bir seçimi kaldırmak için kullanın [CListBox::SetSel](#setsel).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]  
  
##  <a name="sethorizontalextent"></a>  CListBox::SetHorizontalExtent  
 Genişliği olarak yatay liste kutusu kaydırılabileceğini piksel cinsinden ayarlar.  
  
```  
void SetHorizontalExtent(int cxExtent);
```  
  
### <a name="parameters"></a>Parametreler  
 *cxExtent*  
 Piksel olarak liste kutusunu yatay olarak kaydırılabilir sayısını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu boyutu bu değerden daha küçükse, yatay kaydırma çubuğu öğeleri liste kutusunda yatay kaydırma. Liste kutusu gibi büyük veya bu değerden daha büyük ise, yatay kaydırma çubuğunun gizlenir.  
  
 Bir çağrı yanıt `SetHorizontalExtent`, liste kutusu ile tanımlanmış olmalıdır [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles) stili.  
  
 Bu üye işlevi, çoklu sütun liste kutuları için faydalı değil. Çoklu sütun liste kutularını çağırma `SetColumnWidth` üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]  
  
##  <a name="setitemdata"></a>  CListBox::SetItemData  
 Belirtilen öğeyi liste kutusunda ile ilişkili 32 bit bir değer ayarlar.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Öğenin sıfır tabanlı dizinini belirtir.  
  
 *dwItemData*  
 Öğeyle ilişkilendirilecek değeri belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa LB_ERR.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]  
  
##  <a name="setitemdataptr"></a>  CListBox::SetItemDataPtr  
 Belirtilen öğe belirtilen işaretçisi olacak şekilde, bir liste kutusunda ile ilişkili 32-bit değeri ayarlar ( **void** <strong>\*</strong>).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Öğenin sıfır tabanlı dizinini belirtir.  
  
 *pData*  
 Öğeyle ilişkilendirilecek işaretçi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa LB_ERR.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğeleri eklendiğinde veya kaldırıldığında gibi liste kutusu içindeki öğenin göreli konumu değişebilir olsa bile bu işaretçinin liste kutusunda süresince geçerli kalır. Bu nedenle, kutunun içinde öğenin dizini değiştirebilirsiniz, ancak işaretçi güvenilir kalır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]  
  
##  <a name="setitemheight"></a>  CListBox::SetItemHeight  
 Öğe yüksekliğini bir liste kutusunda ayarlar.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Liste kutusunda öğenin sıfır tabanlı dizinini belirtir. Bu parametre yalnızca liste kutusu lbs_ownerdrawvarıable stili varsa kullanılır. Aksi durumda 0 olarak ayarlanmalıdır.  
  
 *cyItemHeight*  
 Öğe piksel cinsinden yüksekliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizin veya yüksekliği geçersizse LB_ERR.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu varsa [lbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stilini ayarlar bu işlev tarafından belirtilen öğe yüksekliğini *nIndex*. Aksi takdirde, bu işlevi tüm öğeleri yüksekliğini liste kutusunda ayarlar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]  
  
##  <a name="setlocale"></a>  CListBox::SetLocale  
 Bu liste kutusu yerel ayar tanımlayıcısı ayarlar.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Parametreler  
 *nNewLocale*  
 Liste kutusu için ayarlanacak yeni yerel ayar tanıtıcısı (LCID) değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu liste kutusunun önceki yerel ayar tanıtıcısı (LCID) değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `SetLocale` çağrılmaz; varsayılan yerel ayar sistemden elde edilir. Denetim Masası ndaki kullanarak bu sistem varsayılan yerel ayar değiştirilebilir bölge (veya uluslararası) uygulama.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]  
  
##  <a name="setsel"></a>  CListBox::SetSel  
 Bir dize içinde birden çok seçim liste kutusu seçer.  
  
```  
int SetSel(
    int nIndex,  
    BOOL bSelect = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Ayarlanacak dize sıfır tabanlı dizinini içerir. -1, seçimi eklendiğinde veya değerine bağlı olarak tüm dizeleri kaldırıldığında, *bGüvenlik ayarlarını*.  
  
 *bGüvenlik ayarlarını*  
 Seçimi ayarlama işlemini belirtir. Varsa *bGüvenlik ayarlarını* doğru ise, dize seçili ve vurgulanmış; FALSE ise Vurgusu kaldırılır ve dize artık seçilir. Belirtilen dizeyi seçilir ve varsayılan olarak vurgulanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa LB_ERR.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi, yalnızca birden çok seçim liste kutuları ile kullanın.  
  
 Tek seçim listesinden bir öğe seçmek için kullanın [CListBox::SetCurSel](#setcursel).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]  
  
##  <a name="settabstops"></a>  CListBox::SetTabStops  
 Bir liste kutusunun sekme durağı konumda ayarlar.  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>Parametreler  
 *cxEachStop*  
 Sekme duraklarını ayarlamak her *cxEachStop* iletişim kutusu birimleri. Bkz: *rgTabStops* iletişim birim açıklaması.  
  
 *nTabStops*  
 Liste kutusunda için sekme durağı sayısını belirtir.  
  
 *rgTabStops*  
 Bir dizinin ilk üye işaret iletişim kutusu birimlerinde sekme durağı konumlarını içeren bir tamsayı. Yatay ve dikey uzaklığı bir iletişim birimidir. Tek bir yatay iletişim birim dörtte için geçerli iletişim temel genişliği birimi eşittir ve bir dikey iletişim birimi bir sekizinci için geçerli iletişim temel yükseklik biriminin eşittir. İletişim temel birimler geçerli sistem yazı tipi genişliği ve yüksekliği göre hesaplanır. `GetDialogBaseUnits` Windows işlevi temel birimlerinin geçerli iletişim piksel cinsinden döndürür. Sekme duraklarını artan düzende sıralanmış olmalıdır; geri sekmeler izin verilmez.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm sekmeler ayarlanan olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekme duraklarını 2 iletişim kutusu birimleri varsayılan boyutunu ayarlamak için bu üye işlevi parametresiz sürümünü arayın. Sürümü ile 2 dışındaki bir boyuta sekme durakları ayarlama çağrısı *cxEachStop* bağımsız değişken.  
  
 Sekme durakları bir dizi boyutları için ayarlanacak sürümüyle kullanmak *rgTabStops* ve *nTabStops* bağımsız değişkenler. Sekme durağı her bir değer ayarlamak *rgTabStops*, ile belirtilen sayıya kadar *nTabStops*.  
  
 Bir çağrı yanıt `SetTabStops` üye işlevi, liste kutusu gerekir oluşturulmuş ile [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]  
  
##  <a name="settopindex"></a>  CListBox::SetTopIndex  
 Belirli bir liste kutusu öğesi görünür olmasını sağlar.  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Liste kutusu öğesinin sıfır tabanlı dizinini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır veya bir hata oluşursa LB_ERR.  
  
### <a name="remarks"></a>Açıklamalar  
 Sistem tarafından belirtilen öğe kadar liste kutusu kaydırır *nIndex* görünür listenin en üstünde kutusu veya en fazla kaydırma aralığı ulaşıldı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]  
  
##  <a name="vkeytoitem"></a>  CListBox::VKeyToItem  
 Liste kutusunun ana pencereye liste kutusundan wm_vkeytoıtem ileti aldığında framework tarafından çağırılır.  
  
```  
virtual int VKeyToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *nKey*  
 Sanal tuş kodunu kullanıcının basılı. Winuser.h standart sanal anahtar kodlarının listesi için bkz.  
  
 *nIndex*  
 Liste kutusu giriş işaretini geçerli konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür - başka bir işlem için 2, - 1 için varsayılan eylem veya tuş vuruşu için varsayılan eylem gerçekleştirmek için bir liste kutusu öğesinin bir dizin belirtmek için negatif olmayan bir sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 WM_KEYDOWN iletisi aldığında, ancak liste kutusu şunların ikisini de karşılıyorsa, wm_vkeytoıtem ileti liste kutusu tarafından gönderilir:  
  
-   Sahip [lbs_wantkeyboardınput](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stil kümesi.  
  
-   En az bir öğe var.  
  
 Hiçbir zaman kendiniz bu işlevini çağırmalıdır. Klavye iletileri kendi özel işleme sağlamak için bu işlevi geçersiz kılar.  
  
 Geçersiz kılma gerçekleştirilen eylemi framework bildirmek için bir değer döndürmesi gerekir. Dönüş değeri - uygulama öğeyi seçerek tüm yönlerini işlenmiş ve liste kutusu tarafından başka bir eylem gerektiren 2 gösterir. Önce döndüren - 2 ' nin seçimini ayarlayın veya klavyeyle veya her ikisini de taşıyın. Seçimi ayarlamak için kullanın [SetCurSel](#setcursel) veya [SetSel](#setsel). Giriş işaretini taşımanız [SetCaretIndex](#setcaretindex).  
  
 Dönüş değeri - 1 liste kutusu tuş vuruşu yanıt varsayılan eylem yapmanız gerektiğini gösterir. Varsayılan uygulama döndürür - 1.  
  
 Dönüş değeri 0 veya daha büyük, liste kutusunda bir öğenin dizinini belirtir ve liste kutusu tuş vuruşu verilen öğe üzerinde için varsayılan eylem gerçekleştirmesini gösterir.  
  
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
