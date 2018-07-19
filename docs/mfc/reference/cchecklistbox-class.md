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
ms.openlocfilehash: 2118344df9d97ddd8c8ba8f194b5653dea3ba001
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338388"
---
# <a name="cchecklistbox-class"></a>CCheckListBox sınıfı
Bir Windows Denetim listesi kutusu işlevlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CCheckListBox : public CListBox  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCheckListBox::CCheckListBox](#cchecklistbox)|Oluşturur bir `CCheckListBox` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCheckListBox::Create](#create)|Windows Denetim listesi kutusu oluşturur ve ona ekler `CCheckListBox` nesne.|  
|[CCheckListBox::DrawItem](#drawitem)|Görsel bir özelliği bir sahip çizim liste kutusu değişiklikler olduğunda framework tarafından çağırılır.|  
|[CCheckListBox::Enable](#enable)|Etkinleştirir veya bir denetim listesi kutusu öğesi devre dışı bırakır.|  
|[CCheckListBox::GetCheck](#getcheck)|Bir öğenin onay kutusunun durumunu alır.|  
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Denetimin onay kutularını stilini alır.|  
|[CCheckListBox::IsEnabled](#isenabled)|Bir öğe etkin olup olmadığını belirler.|  
|[CCheckListBox::MeasureItem](#measureitem)|Sahip çizim stili bir liste kutusu oluşturulduğunda framework tarafından çağırılır.|  
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|Onay kutusu öğenin konumunu almak için framework tarafından çağırılır.|  
|[CCheckListBox::SetCheck](#setcheck)|Bir öğenin onay kutusunun durumunu ayarlar.|  
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Denetimin onay kutularını stilini ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir "Yapılacaklar listesi kutusu" dosya adları gibi öğeleri listesini görüntüler. Listedeki her öğe kullanıcının işaretleyin veya temizleyin yanında bir onay kutusu var.  
  
 `CCheckListBox` yalnızca kullanıcı çizimli denetimler için listenin en fazla metin dizelerini içeren olmasıdır. En basit şekliyle, bir denetim listesi kutusu metin dizelerini ve onay kutularını içerir, ancak metin hiç sahip olmanız gerekmez. Örneğin, küçük bit eşlemler her öğesinin yanındaki onay kutusu listesi olabilir.  
  
 Kendi Yapılacaklar listesi kutusu oluşturmak için kendi sınıfından türetilir `CCheckListBox`. Türetilmiş sınıf için bir oluşturucu kendi sınıf türetmek yazmak için ardından çağırın `Create`.  
  
 Liste kutusu tarafından yollanır Windows bildirim iletilerini işlemek isterseniz (öğesinden türetilmiş bir sınıf genellikle [CDialog](../../mfc/reference/cdialog-class.md)), üst sınıfın her ileti için ileti eşleme girişi ve ileti işleyicisi üye işlevi ekleyin.  
  
 Her ileti eşleme girişi aşağıdaki biçimi alır:  
  
 **ON_** bildirim **(**`id`, `memberFxn` **)**  
  
 Burada `id` bildirimi gönderilmesi denetimi alt pencere Kimliğini belirtir ve `memberFxn` bildirimini işlemek için yazdığınız üst üye işlev adıdır.  
  
 Üst öğenin işlev prototipi aşağıdaki gibidir:  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 Özellikle çok ilgilidir yalnızca bir ileti eşleme giriş `CCheckListBox` (ancak ileti eşlemesi girişleri için Ayrıca bkz: [CListBox](../../mfc/reference/clistbox-class.md)):  
  
- ON_CLBN_CHKCHANGE kullanıcının bir öğenin onay kutusunun durumunu değiştirdi.  
  
 Bir varsayılan denetim listesi kutusu (her solundaki varsayılan boyutunda onay kutuları içeren dizeleri listesini), yapılacaklar listesi kutusu ise varsayılan kullanabileceğiniz [CCheckListBox::DrawItem](#drawitem) Yapılacaklar listesi kutusu çizmek için. Aksi takdirde, kılmalı [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) işlevi ve [CCheckListBox::DrawItem](#drawitem) ve [CCheckListBox::MeasureItem](#measureitem) işlevleri.  
  
 Bir iletişim kutusu şablonundan ya da kodunuzda doğrudan bir denetim listesi kutusu oluşturabilirsiniz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cchecklistbox"></a>  CCheckListBox::CCheckListBox  
 Oluşturur bir `CCheckListBox` nesne.  
  
```  
CCheckListBox();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CCheckListBox` iki adımda nesne. İlk türetilen bir sınıf tanımlamak `CCheckListBox`, ardından çağırın `Create`, Windows Denetim listesi kutusu başlatır ve ekler `CCheckListBox` nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]  
  
##  <a name="create"></a>  CCheckListBox::Create  
 Windows Denetim listesi kutusu oluşturur ve ona ekler `CCheckListBox` nesne.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwStyle*  
 Yapılacaklar listesi kutusu stilini belirtir. Stil lbs_hasstrıngs ve lbs_ownerdrawfıxed (listedeki tüm öğeleri aynı yükseklikte olan) veya lbs_ownerdrawvarıable olmalıdır (listedeki öğeleri, değişken uzunluklarının olabilir). Bu stil ile birleştirilebilir [liste kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) LBS_USETABSTOPS hariç.  
  
 *Rect*  
 Yapılacaklar listesi kutusu boyutunu ve konumunu belirtir. Olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](../../mfc/reference/rect-structure1.md) yapısı.  
  
 *pParentWnd*  
 Denetim listesi kutunun üst penceresine belirtir (genellikle bir `CDialog` nesne). NULL olmamalıdır.  
  
 *nID*  
 Denetim listesi kutunun denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CCheckListBox` iki adımda nesne. İlk olarak, türetilen bir sınıf tanımlama `CcheckListBox` ve sonra çağrı `Create`, Windows Denetim listesi kutusu başlatır ve ekler `CCheckListBox`. Bkz: [CCheckListBox::CCheckListBox](#cchecklistbox) örneği.  
  
 Zaman `Create` yürütür, Windows gönderir [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Yapılacaklar listesi kutusu denetim iletileri.  
  
 Bu iletiler tarafından varsayılan olarak işlenir [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [Ongetminmaxınfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) üye işlevleri içinde `CWnd` temel sınıfı. Varsayılan ileti işleme genişletmek için ileti eşlemesi için ekleme türetilmiş bir sınıf ve üye işlevleri geçersiz kılma önceki ileti işleyicisi. Geçersiz kılma `OnCreate`, örneğin, gerekli başlatma için yeni bir sınıf gerçekleştirmek için.  
  
 Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir denetim listesi kutusu denetimine:  
  
- WS_CHILD her zaman  
  
- Ws_vısıble genellikle  
  
- Ws_dısabled nadiren  
  
- WS_VSCROLL için dikey kaydırma çubuğu ekleyin  
  
- WS_HSCROLL için yatay kaydırma çubuğu ekleyin  
  
- WS_GROUP grup denetimleri için  
  
- WS_TABSTOP izin vermek için bu denetimin sekme  
  
##  <a name="drawitem"></a>  CCheckListBox::DrawItem  
 Görsel bir özelliği bir sahip tarafından çizilmiş denetim listesi kutusu değişiklikler olduğunda framework tarafından çağırılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpDrawItemStruct*  
 Uzun bir işaretçi bir [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) gerekli çizim türü hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `itemAction` Ve `itemState` üyeleri `DRAWITEMSTRUCT` yapısı gerçekleştirilecek çizim eylemi tanımlayın.  
  
 Varsayılan olarak, bu işlev bir dize listesi her varsayılan boyutunda bir onay kutusu sol ile oluşan varsayılan onay kutusu listesi, çizer. Belirtilen onay kutusu listesi boyutu öğedir [Oluştur](#create).  
  
 Dize olmayan listeleri, değişken yükseklik öğeleri veya sol tarafta olmayan onay kutularını denetim kutuları gibi varsayılan olmayan özelleştirilmiş çizimli denetim listesi kutusu çizim uygulamak için bu üye işlevini geçersiz kılar. Uygulama görünen bağlam sağlanan için seçilen tüm grafik cihaz arabirimi (GDI) nesneleri geri yüklemeniz gerekir *lpDrawItemStruct* bu üye işlevinin sona ermeden önce.  
  
 Denetim listesi kutusu öğeleri aynı yükseklikte emin değilseniz, Denetim listesi kutusu stili (belirtilen `Create`) olmalıdır ** LBS_OWNERVARIABLE ve kılmalı [MeasureItem](#measureitem) işlevi.  
  
##  <a name="enable"></a>  CCheckListBox::Enable  
 Etkinleştirmek veya devre dışı bir denetim listesi kutusu öğesi için bu işlevi çağırın.  
  
```  
void Enable(
    int nIndex,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Etkinleştirilmesi için Denetim listesi kutusu öğenin dizini.  
  
 *bEtkin*  
 Öğe etkin mi yoksa devre dışı mı olduğunu belirtir.  
  
##  <a name="getcheck"></a>  CCheckListBox::GetCheck  
 Belirtilen onay kutusunun durumunu alır.  
  
```  
int GetCheck(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Liste kutusunda bulunan bir onay kutusu sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen onay kutusunun durumunu. Olası değerler aşağıdaki tabloda listelenmektedir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|BST_CHECKED|Onay kutusunun işaretli olduğundan.|  
|BST_UNCHECKED|Onay kutusu işaretli değildir.|  
|BST_INDETERMINATE|Onay kutusunun durumunu belirsiz.|  
  
##  <a name="getcheckstyle"></a>  CCheckListBox::GetCheckStyle  
 Denetim listesi kutunun stili almak için bu işlevi çağırın.  
  
```  
UINT GetCheckStyle();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin onay kutularını stili.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası stilleri hakkında daha fazla bilgi için bkz: [SetCheckStyle](#setcheckstyle).  
  
##  <a name="isenabled"></a>  CCheckListBox::IsEnabled  
 Bir öğe etkin olup olmadığını belirlemek için bu işlevi çağırın.  
  
```  
BOOL IsEnabled(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Öğenin dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe etkin olursa sıfır dışı; Aksi durumda 0.  
  
##  <a name="measureitem"></a>  CCheckListBox::MeasureItem  
 Varsayılan olmayan stilinde bir denetim listesi kutusu oluşturulduğunda framework tarafından çağırılır.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMeasureItemStruct*  
 Uzun bir işaretçi bir [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bu üye işlevini geçersiz kılabilir ve doldurun `MEASUREITEMSTRUCT` Windows Denetim listesi kutusu öğeleri boyutlarının bildirmek için yapısı. Yapılacaklar listesi kutusu ile oluşturulursa [lbs_ownerdrawvarıable](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stili framework çağıran bu üye işlevi liste kutusunda her bir öğe için. Aksi takdirde, bu üye, yalnızca bir kez çağrılır.  
  
##  <a name="ongetcheckposition"></a>  CCheckListBox::OnGetCheckPosition  
 Framework, bir öğedeki onay kutusunun boyutunu ve konumunu almak için bu işlevi çağırır.  
  
```  
virtual CRect OnGetCheckPosition(
    CRect rectItem,  
    CRect rectCheckBox);
```  
  
### <a name="parameters"></a>Parametreler  
 *rectItem*  
 Liste öğesi boyutunu ve konumunu.  
  
 *rectCheckBox*  
 Bir öğenin boyutunu ve varsayılan konumu onay kutusunu işaretleyin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir öğenin boyutunu ve konumunu onay kutusunu işaretleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama yalnızca onay kutusunun boyutunu ve varsayılan konumunu döndürür (`rectCheckBox`). Varsayılan olarak onay kutusu öğenin sol üst köşesinde bulunan hizalanır ve standart onay kutusunun boyutu. Burada, sağ taraftaki onay kutularını istiyorsanız veya daha büyük veya küçük bir onay kutusunu istediğiniz durumlar olabilir. Bu durumda geçersiz kılma `OnGetCheckPosition` onay kutusunun konumu ve boyutu öğesinin içinde değiştirmek için.  
  
##  <a name="setcheck"></a>  CCheckListBox::SetCheck  
 Belirtilen onay kutusunun durumunu ayarlar.  
  
```  
void SetCheck(
    int nIndex,  
    int nCheck);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Liste kutusunda bulunan bir onay kutusu sıfır tabanlı dizini.  
  
 *Nbakım*  
 Belirtilen onay kutusu düğmesi durumu. Olası değerler için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin olası değerler aşağıdaki tabloda *Nbakım* parametresi.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|BST_CHECKED|Belirtilen onay kutusunu işaretleyin.|  
|BST_UNCHECKED|Belirtilen onay kutusunu temizleyin.|  
|BST_INDETERMINATE|Belirtilen onay kutusunun durumunu belirsiz şekilde ayarlayın.<br /><br /> Bu durum, yalnızca onay kutusu stili BS_AUTO3STATE veya BS_3STATE olduğunda kullanılabilir. Daha fazla bilgi için [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
  
##  <a name="setcheckstyle"></a>  CCheckListBox::SetCheckStyle  
 Onay kutularını stilini Yapılacaklar listesi kutusu içinde ayarlamak için bu işlevi çağırın.  
  
```  
void SetCheckStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 *nStyle*  
 Yapılacaklar listesi kutusu onay kutularına stilini belirler.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli stiller şunlardır:  
  
- BS_CHECKBOX  
  
- BS_AUTOCHECKBOX  
  
- BS_AUTO3STATE  
  
- BS_3STATE  
  
 Bu stiller hakkında daha fazla bilgi için bkz: [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek TSTCON](../../visual-cpp-samples.md)   
 [CListBox sınıfı](../../mfc/reference/clistbox-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CListBox Sınıfı](../../mfc/reference/clistbox-class.md)
