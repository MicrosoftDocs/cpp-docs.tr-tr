---
title: CCheckListBox sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4129da35eca5aecfb1e976361d1716d1cd78e906
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358205"
---
# <a name="cchecklistbox-class"></a>CCheckListBox sınıfı
Bir Windows Yapılacaklar listesi kutusu işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CCheckListBox : public CListBox  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCheckListBox::CCheckListBox](#cchecklistbox)|Oluşturan bir `CCheckListBox` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCheckListBox::Create](#create)|Windows Denetim listesi kutusu oluşturur ve ona ekler `CCheckListBox` nesnesi.|  
|[CCheckListBox::DrawItem](#drawitem)|Bir sahip çizim liste kutusunu değişiklikleri visual yönünü zaman çerçevesi tarafından çağrılır.|  
|[CCheckListBox::Enable](#enable)|Etkinleştirir veya bir Yapılacaklar listesi kutusu öğesi devre dışı bırakır.|  
|[CCheckListBox::GetCheck](#getcheck)|Bir öğenin onay kutusunu durumunu alır.|  
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Denetimin onay kutularını stilini alır.|  
|[CCheckListBox::IsEnabled](#isenabled)|Bir öğe etkin olup olmadığını belirler.|  
|[CCheckListBox::MeasureItem](#measureitem)|Sahibi çizim stili içeren bir liste kutusu oluşturulduğunda çerçevesi tarafından çağrılır.|  
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|Bir öğenin onay kutusunun konumunu almak için çerçevesi tarafından çağrılır.|  
|[CCheckListBox::SetCheck](#setcheck)|Bir öğenin onay kutusunun durumunu ayarlar.|  
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Denetimin onay kutularını stilini ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Yapılacaklar listesi kutusu" dosya adları gibi öğeleri listesini görüntüler. Listedeki her öğeye kullanıcı denetleyin veya silebileceği yanında bir onay kutusu var.  
  
 `CCheckListBox` yalnızca sahip tarafından çizilmiş denetimleri için listenin en fazla metin dizelerini içerir olmasıdır. En basit şekliyle, yapılacaklar listesi kutusu metin dizelerini ve onay kutularını içerir, ancak metin hiç olması gerekmez. Örneğin, her öğenin yanındaki onay kutusunu küçük bit eşlemler listesi olabilir.  
  
 Kendi Yapılacaklar listesi kutusu oluşturmak için kendi sınıfından türetilen `CCheckListBox`. Türetilmiş sınıf için bir oluşturucu türetilen kendi sınıfı yazmak için ' ı çağırın **oluşturma**.  
  
 Üst için bir liste kutusu tarafından gönderilen Windows bildirim iletilerini işlemek istiyorsanız (öğesinden türetilmiş bir sınıf genellikle [CDialog](../../mfc/reference/cdialog-class.md)), her ileti için üst sınıfı için ileti eşleme girişi ve ileti işleyicisi üye işlevi ekleme.  
  
 Her ileti eşleme girişi aşağıdaki biçimdedir:  
  
 **ON_** bildirim **(**`id`, `memberFxn` **)**  
  
 Burada `id` bildirim göndererek denetimi alt pencere Kimliğini belirtir ve `memberFxn` bildirimini işlemek için yazılmış üst üye işlevi adıdır.  
  
 Üst öğenin işlev prototipi aşağıdaki gibidir:  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 Özellikle çok ilgilidir yalnızca bir ileti eşleme girişi **CCheckListBox** (ancak aynı zamanda ileti eşleme girişlerini görmek [CListBox](../../mfc/reference/clistbox-class.md)):  
  
- **ON_CLBN_CHKCHANGE** kullanıcının bir öğenin onay kutusunu durumu değişti.  
  
 Yapılacaklar listesi kutusu varsayılan Yapılacaklar listesi kutusu (varsayılan boyutlu onay kutularını her solundaki dizelerle listesi) ise, varsayılan kullanabilirsiniz [CCheckListBox::DrawItem](#drawitem) Yapılacaklar listesi kutusu çizmek için. Aksi takdirde kılmalıdır [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) işlevi ve [CCheckListBox::DrawItem](#drawitem) ve [CCheckListBox::MeasureItem](#measureitem) işlevleri.  
  
 Bir iletişim şablonunu ya da kodunuzdaki doğrudan bir Yapılacaklar listesi kutusu oluşturabilirsiniz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cchecklistbox"></a>  CCheckListBox::CCheckListBox  
 Oluşturan bir `CCheckListBox` nesnesi.  
  
```  
CCheckListBox();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CCheckListBox` iki adımda nesne. İlk türetilmiş bir sınıf tanımlama `CCheckListBox`, ardından çağıran **oluşturma**, hangi Windows Yapılacaklar listesi kutusu başlatır ve ona ekler `CCheckListBox` nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]  
  
##  <a name="create"></a>  CCheckListBox::Create  
 Windows Denetim listesi kutusu oluşturur ve ona ekler `CCheckListBox` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Yapılacaklar listesi kutusu stilini belirtir. Stil olmalıdır **lbs_hasstrıngs** ve her iki **lbs_ownerdrawfıxed** (listedeki tüm öğelerin aynı yükseklikte olan) veya **lbs_ownerdrawvarıable** (listedeki öğeleri olan değişen yükseklikte). Bu stili diğer ile birleştirilebilir [liste kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) dışında **LBS_USETABSTOPS**.  
  
 `rect`  
 Yapılacaklar listesi kutusu boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](../../mfc/reference/rect-structure1.md) yapısı.  
  
 `pParentWnd`  
 Denetim listesi kutunun üst pencere belirtir (genellikle bir `CDialog` nesnesi). Değil olmalıdır **NULL**.  
  
 `nID`  
 Denetim listesi kutunun denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CCheckListBox` iki adımda nesne. İlk olarak, türetilmiş bir sınıf tanımlama **CcheckListBox** ve ardından arama **oluşturma**, hangi Windows Yapılacaklar listesi kutusu başlatır ve ekleninceye `CCheckListBox`. Bkz: [CCheckListBox::CCheckListBox](#cchecklistbox) bir örnek için.  
  
 Zaman **oluşturma** yürütür, Windows gönderir [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [WM_ GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Yapılacaklar listesi kutusu denetim iletileri.  
  
 Bu iletiler, varsayılan olarak tarafından işlenen [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [Ongetminmaxınfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) üye işlevleri içinde `CWnd` temel sınıfı. Varsayılan ileti işleme genişletmek için ileti Eşlemesi Ekle geçersiz kılma önceki ileti işleyicisi üye işlevleri ve türetilmiş sınıf. Geçersiz kılma `OnCreate`, örneğin, gerekli başlatma için yeni bir sınıf gerçekleştirmek için.  
  
 Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir Yapılacaklar listesi kutusu denetlemek için:  
  
- **WS_CHILD** her zaman  
  
- **Ws_vısıble** genellikle  
  
- **Ws_dısabled** nadiren  
  
- **WS_VSCROLL** dikey kaydırma çubuğu eklemek için  
  
- **WS_HSCROLL** yatay kaydırma çubuğu eklemek için  
  
- **WS_GROUP** grup denetimleri için  
  
- **WS_TABSTOP** bu denetim için sekme izin vermek için  
  
##  <a name="drawitem"></a>  CCheckListBox::DrawItem  
 Sahip tarafından çizilmiş Yapılacaklar listesi kutusu değişiklikler visual yönünü zaman çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDrawItemStruct`  
 Uzun bir işaretçi bir [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) gerekli çizim türü hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 **İtemAction** ve **itemState** üyeleri `DRAWITEMSTRUCT` yapısı gerçekleştirilecek çizim eylemi tanımlayın.  
  
 Varsayılan olarak, bu işlev dizelerinin listesini her varsayılan boyutlu bir onay kutusunu sol ile oluşan bir varsayılan onay kutusu listesi çizer. Onay kutusu listesi boyutu belirtilen biridir [oluşturma](#create).  
  
 Denetim listesi kutuları dize olmayan listeleri, değişken yükseklikli öğeleri veya solda olmayan onay kutularını gibi varsayılan olmayan sahip çizim denetim kutuları çiziminin uygulamak için bu üye işlevi geçersiz kılar. Tüm grafik cihaz arabirimi (GDI) nesneleri görüntüleme bağlamı içinde sağlanan için seçilen uygulama kurtarmalısınız `lpDrawItemStruct` bu üye işlevinin sona ermeden önce.  
  
 Yapılacaklar listesi kutusu öğeleri aynı yüksekliği emin değilseniz, yapılacaklar listesi kutusu stili (belirtilen **oluşturma**) olmalıdır **LBS_OWNERVARIABLE**, ve geçersiz kılmanız gerekir [MeasureItem](#measureitem) işlev.  
  
##  <a name="enable"></a>  CCheckListBox::Enable  
 Bu işlevi etkinleştirmek veya devre dışı bir Yapılacaklar listesi kutusu öğesi için çağırın.  
  
```  
void Enable(
    int nIndex,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Etkinleştirilecek Yapılacaklar listesi kutusu öğenin dizini.  
  
 `bEnabled`  
 Öğe etkin mi yoksa devre dışı mı olduğunu belirtir.  
  
##  <a name="getcheck"></a>  CCheckListBox::GetCheck  
 Belirtilen onay kutusunun durumunu alır.  
  
```  
int GetCheck(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Liste kutusunda içerdiği bir onay kutusu sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen onay kutusunun durumu. Olası değerler aşağıdaki tabloda listelenmektedir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`BST_CHECKED`|Onay kutusu işaretliyse.|  
|`BST_UNCHECKED`|Onay kutusu işaretli değildir.|  
|`BST_INDETERMINATE`|Belirsiz onay kutusunu durumudur.|  
  
##  <a name="getcheckstyle"></a>  CCheckListBox::GetCheckStyle  
 Denetim listesi kutunun stili almak için bu işlevini çağırın.  
  
```  
UINT GetCheckStyle();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin onay kutularını stili.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası stilleri hakkında daha fazla bilgi için bkz: [SetCheckStyle](#setcheckstyle).  
  
##  <a name="isenabled"></a>  CCheckListBox::IsEnabled  
 Bir öğe etkin olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL IsEnabled(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe etkinse, sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="measureitem"></a>  CCheckListBox::MeasureItem  
 Varsayılan olmayan stiliyle bir Yapılacaklar listesi kutusu oluşturulduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpMeasureItemStruct`  
 Uzun bir işaretçi bir [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bu üye işlevi geçersiz kılma ve doldurmak `MEASUREITEMSTRUCT` Windows'a Yapılacaklar listesi kutusu öğeleri boyutlarının bildirmek için yapısı. Yapılacaklar listesi kutusu ile oluşturulursa [lbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili framework çağırması bu üye işlevi liste kutusunda her bir öğe için. Aksi takdirde, bu üye yalnızca bir kez çağrılır.  
  
##  <a name="ongetcheckposition"></a>  CCheckListBox::OnGetCheckPosition  
 Framework onay kutusunun boyutunu ve konumunu bir öğeyi almak için bu işlevi çağırır.  
  
```  
virtual CRect OnGetCheckPosition(
    CRect rectItem,  
    CRect rectCheckBox);
```  
  
### <a name="parameters"></a>Parametreler  
 *rectItem*  
 Konum ve boyut liste öğesi.  
  
 `rectCheckBox`  
 Varsayılan konumunu ve öğenin boyutunu onay kutusunu işaretleyin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin boyutunu ve konumunu onay kutusunu işaretleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, yalnızca varsayılan konumu ve boyutu onay kutusunun döndürür ( `rectCheckBox`). Varsayılan olarak, onay kutusu öğenin sol üst köşesindeki hizalanır ve standart onay kutusu boyutudur. Burada, onay kutularını sağdaki istediğiniz veya daha büyük veya küçük bir onay kutusunu istediğiniz durumlar olabilir. Bu durumlarda, geçersiz kılma `OnGetCheckPosition` onay kutusunu konumu ve boyutu öğe içinde değiştirmek için.  
  
##  <a name="setcheck"></a>  CCheckListBox::SetCheck  
 Belirtilen onay kutusunun durumunu ayarlar.  
  
```  
void SetCheck(
    int nIndex,  
    int nCheck);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Liste kutusunda içerdiği bir onay kutusu sıfır tabanlı dizini.  
  
 `nCheck`  
 Belirtilen onay kutusunu düğme durumu. Olası değerler için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin olası değerler aşağıdaki tabloda listelenmektedir `nCheck` parametresi.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|**BST_CHECKED**|Belirtilen onay kutusunu seçin.|  
|**BST_UNCHECKED**|Belirtilen onay kutusunu temizleyin.|  
|**BST_INDETERMINATE**|Belirtilen onay kutusunun durumu belirsiz şekilde ayarlayın.<br /><br /> Bu durum yalnızca onay kutusu stili ise kullanılabilir `BS_AUTO3STATE` veya `BS_3STATE`. Daha fazla bilgi için bkz: [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
  
##  <a name="setcheckstyle"></a>  CCheckListBox::SetCheckStyle  
 Denetim Listesi kutusunda onay kutularını stilini ayarlamak için bu işlevini çağırın.  
  
```  
void SetCheckStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `nStyle`  
 Denetim listesi kutusundaki onay kutularını stilini belirler.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli stilleri şunlardır:  
  
- **BS_CHECKBOX**  
  
- **BS_AUTOCHECKBOX**  
  
- **BS_AUTO3STATE**  
  
- **BS_3STATE**  
  
 Bu stiller hakkında daha fazla bilgi için bkz: [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek TSTCON](../../visual-cpp-samples.md)   
 [CListBox sınıfı](../../mfc/reference/clistbox-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CListBox Sınıfı](../../mfc/reference/clistbox-class.md)
