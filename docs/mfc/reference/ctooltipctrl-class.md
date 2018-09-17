---
title: CToolTipCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
dev_langs:
- C++
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4708f180a1a1f5e936a6b30650a6432d48878d53
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726758"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl sınıfı
Bir "araç ipucunu denetimini," tek satırlık bir uygulamada bir aracın amacını açıklayan metin görüntüleyen küçük bir açılır pencere işlevselliğini kapsüller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|Oluşturur bir `CToolTipCtrl` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CToolTipCtrl::Activate](#activate)|Etkinleştirir ve araç ipucunu denetimini devre dışı bırakır.|  
|[CToolTipCtrl::AddTool](#addtool)|Bir aracı ile araç ipucunu denetimini kaydeder.|  
|[CToolTipCtrl::AdjustRect](#adjustrect)|Bir araç ipucu denetiminin metin arasında dönüştürür ve kendi Pencere dikdörtgeni dikdörtgen görüntüler.|  
|[CToolTipCtrl::Create](#create)|Bir araç ipucu denetimi oluşturur ve ona bağlanan bir `CToolTipCtrl` nesne.|  
|[CToolTipCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir araç ipucunu denetimini oluşturur ve ekler bir `CToolTipCtrl` nesne.|  
|[CToolTipCtrl::DelTool](#deltool)|Bir aracı araç ipucu denetiminden kaldırır.|  
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|Araç İpucu VHD'nin boyutunu alır.|  
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|Boyut, konum ve metin, araç ipucu penceresinin geçerli araç ipucu denetimi görüntüler gibi bilgileri alır.|  
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|İlk açılır ve reshow alır bir aracı için ayarlanmış süreleri ipucu denetimi.|  
|[CToolTipCtrl::GetMargin](#getmargin)|Üst, sol, alt ve sağ kenar boşluklarının bir araç ipucu penceresi için ayarlanan alır.|  
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|Bir araç ipucu penceresi için en fazla genişliğini alır.|  
|[CToolTipCtrl::GetText](#gettext)|Bir aracı için bir araç ipucunu denetimini tutar metni alır.|  
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|Bir araç ipucu penceresi içinde arka plan rengini alır.|  
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|Bir araç ipucu penceresindeki metin rengini alır.|  
|[CToolTipCtrl::GetTitle](#gettitle)|Geçerli araç ipucu denetimi başlığını alır.|  
|[CToolTipCtrl::GetToolCount](#gettoolcount)|Bir araç ipucu denetimi tarafından tutulan araçları sayısını alır.|  
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|Araç ipucunu denetimini tutan bir araç hakkında bilgi alır.|  
|[CToolTipCtrl::HitTest](#hittest)|Bir nokta belirli bir aracının dikdörtgen içinde olup olmadığını belirlemek için test eder. Bu durumda, aracı hakkında bilgi alır.|  
|[CToolTipCtrl::Pop](#pop)|Görüntülenen araç ipucu penceresi görünümden kaldırır.|  
|[CToolTipCtrl::Popup](#popup)|Son fare mesajı koordinatlarda görüntülenecek geçerli araç ipucu denetimi neden olur.|  
|[CToolTipCtrl::RelayEvent](#relayevent)|Bir fare mesajı işlemek için bir araç ipucunu denetimini geçirir.|  
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|İlk açılır, ayarlar ve süreleri bir araç ipucu denetimi için reshow.|  
|[CToolTipCtrl::SetMargin](#setmargin)|Üst, sol, alt ve sağ kenar boşluklarının bir araç ipucu penceresi için ayarlar.|  
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|Bir araç ipucu penceresi için en fazla genişliğini belirler.|  
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|Bir araç ipucu penceresinde arka plan rengini ayarlar.|  
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|Bir araç ipucu penceresinde metin rengini ayarlar.|  
|[CToolTipCtrl::SetTitle](#settitle)|Standart bir simge ve başlık dize için bir araç ipucu ekler.|  
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|Bir aracı için bir araç ipucu tutar bilgilerini ayarlar.|  
|[CToolTipCtrl::SetToolRect](#settoolrect)|Yeni sınırlayıcı bir dikdörtgen aracı için ayarlar.|  
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|Araç İpucu penceresi visual stilini ayarlar.|  
|[CToolTipCtrl::Update](#update)|Geçerli aracın çizilmesini zorlar.|  
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|Bir araç için araç ipucu metnini ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir "" ya da bir pencere, bir uygulama tarafından tanımlanan dikdörtgen alan bir pencerenin istemci alanı içinde bir alt pencere veya denetim gibi aracıdır. Çoğu zaman, yalnızca kullanıcı imleci bir aracı üzerinde koyar ve veriler var. yaklaşık yarısı için ikinci dışına görünen bir araç ipucu gizlenir. Araç ipucu, imlecin yanında görünür ve kullanıcı fare düğmesine tıklar veya aracın imleci hareket kaybolur.  
  
 `CToolTipCtrl` Araç İpucu metni, araç ipucu penceresi genişliğini ve araç ipucu arka plan ve metin rengini çevreleyen kenar boşluğu genişliği başlangıç saatini ve süresini araç ipucu denetimi için işlevsellik sağlar. Tek araç ipucunu denetimini birden fazla aracı için bilgi sağlayabilir.  
  
 `CToolTipCtrl` Sınıfı Windows ortak araç ipucu denetimi işlevlerini sağlar. Bu denetimi (ve bu nedenle `CToolTipCtrl` sınıfı) ve üzeri yalnızca Windows 95/98 ve Windows NT sürümler 3.51 altında çalışan programlar için kullanılabilir.  
  
 Araç ipuçlarını etkinleştirme hakkında daha fazla bilgi için bkz. [Windows araç ipuçlarında CFrameWnd türetilmemiş](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 Kullanma hakkında daha fazla bilgi için `CToolTipCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak bir CToolTipCtrl](../../mfc/using-ctooltipctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="activate"></a>  CToolTipCtrl::Activate  
 Etkinleştirme veya devre dışı bir araç ipucu denetimi için bu işlevi çağırın.  
  
```  
void Activate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 *bActivate*  
 Araç ipucunu denetimini etkinleştirilmiş veya devre dışı bırakılması olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *bActivate* doğru ise, denetimin etkin; FALSE ise, etkinliği.  
  
 Araç ipucunu denetimini etkin olduğunda, araç ipucu bilgisini denetimi ile kayıtlı bir aracın imleci olduğunda görünür; etkin olduğunda, araç ipucu bilgisini görüntülenmezse, hatta İmleç bir aracı üzerinde olduğunda.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="addtool"></a>  CToolTipCtrl::AddTool  
 Bir aracı ile araç ipucunu denetimini kaydeder.  
  
```  
BOOL AddTool(
    CWnd* pWnd,  
    UINT nIDText,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);

 
BOOL AddTool(
    CWnd* pWnd,  
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Aracı'nı içeren bir pencere işaretçisi.  
  
 *nIDText*  
 Aracı için metni içeren dize kaynağının kimliği.  
  
 *lpRectTool*  
 İşaretçi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) aracının koordinat içeren yapı çevreleyen dikdörtgen. Sol üst köşesinin tarafından tanımlanan pencerenin istemci alanının göreli koordinatları *pWnd*.  
  
 *nIDTool*  
 Aracı kimliği.  
  
 *lpszText*  
 Aracı için metin işaretçisi. Bu parametre değeri LPSTR_TEXTCALLBACK içeriyorsa, pencerenin üst TTN_NEEDTEXT bildirim iletilerini gidin, *pWnd* işaret eder.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 *LpRectTool* ve *nIDTool* parametrelerinin her ikisi de olmalıdır geçerli veya *lpRectTool* NULL ise *nIDTool* 0 olmalıdır.  
  
 Araç ipucunu denetimini birden fazla aracı ile ilişkili olabilir. İmleç araç olduğunda araç ipucunda depolanan bilgilerin görüntülenmesi araç ipucu denetimi ile bir aracı kaydetmek için bu işlevi çağırın.  
  
> [!NOTE]
>  Kullanarak statik denetimine bir araç ipucu ayarlanamıyor `AddTool`.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="adjustrect"></a>  CToolTipCtrl::AdjustRect  
 Bir araç ipucu denetiminin metin arasında dönüştürür ve kendi Pencere dikdörtgeni dikdörtgen görüntüler.  
  
```  
BOOL AdjustRect(
    LPRECT lprc,  
    BOOL bLarger = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *lprc*  
 İşaretçi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) bir araç ipucu penceresi dikdörtgen ya da metin görünen dikdörtgen tutan yapı.  
  
 *bLarger*  
 TRUE ise *lprc* bir metin görünen dikdörtgen belirtmek için kullanılır ve karşılık gelen Pencere dikdörtgeni alır. FALSE ise *lprc* bir pencere dikdörtgeni belirtmek için kullanılır ve ilgili metin görünen dikdörtgen alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dikdörtgen başarıyla ayarlandı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi bir araç ipucu denetiminin metin görünen dikdörtgen, Pencere dikdörtgeni ya da belirtilen metin görünen dikdörtgen görüntülenmesi gereken araç ipucu penceresi dikdörtgen hesaplar.  
  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_ADJUSTRECT](/windows/desktop/Controls/ttm-adjustrect)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="create"></a>  CToolTipCtrl::Create  
 Bir araç ipucu denetimi oluşturur ve ona bağlanan bir `CToolTipCtrl` nesne.  
  
```  
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentWnd*  
 Araç İpucu denetiminin üst penceresine, genellikle belirtir bir `CDialog`. NULL olmamalıdır.  
  
 *dwStyle*  
 Araç İpucu denetiminin stilini belirtir. Bkz: **açıklamalar** bölümünde daha fazla bilgi için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gösterimiyse `CToolTipCtrl` nesne başarıyla oluşturuldu; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CToolTipCtrl` iki adımda. İlk olarak oluşturmak için oluşturucu çağrısı `CToolTipCtrl` nesnesi ve ardından arama `Create` araç ipucunu denetimini oluşturup buna eklemek için `CToolTipCtrl` nesne.  
  
 *DwStyle* parametresi, herhangi bir birleşimi olabilir [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles). Ayrıca, iki sınıf özel stilleri bir araç ipucunu denetimini sahiptir: TTS_ALWAYSTIP ve TTS_NOPREFIX.  
  
|Stil|Açıklama|  
|-----------|-------------|  
|TTS_ALWAYSTIP|İmleç etkin veya etkin olmayan araç ipucu denetiminin sahibi penceresine olmasına bakılmaksızın, bir aracı üzerinde olduğunda araç ipucu görünür belirtir. Bu stil araç ipucunu denetimini Aracı'nın sahibi pencere etkin olduğunda, ancak etkin olmadığı durumlarda görüntülenir.|  
|TTS_NOPREFIX|Bu stil, sistemin (&) karakteri bir dizeden şeridi oluşturma engeller. Araç ipucunu denetimini TTS_NOPREFIX stili yoksa, sistem otomatik olarak aynı dize iki menü öğesi ve bir araç ipucunu denetimini metin olarak kullanmak üzere bir uygulama izin verme, ve işareti karakterleri kaldırır.|  
  
 Araç ipucunu denetimini olup bunları denetim oluştururken belirttiğiniz bağımsız olarak WS_POPUP ve ws_ex_toolwındow pencere stilleri, sahiptir.  
  
 Genişletilmiş windows stilleriyle bir araç ipucu denetimi oluşturmak için arama [CToolTipCtrl::CreateEx](#createex) yerine `Create`.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="createex"></a>  CToolTipCtrl::CreateEx  
 Bir denetimi (alt pencere) oluşturur ve bunu `CToolTipCtrl` nesne.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwStyle = 0,  
    DWORD dwStyleEx = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentWnd*  
 Denetimin ana penceresine bir işaretçi.  
  
 *dwStyle*  
 Araç İpucu denetiminin stilini belirtir. Bkz: **açıklamalar** bölümünü [Oluştur](#create) daha fazla bilgi için.  
  
 *dwStyleEx*  
 Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine `Create` Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.  
  
##  <a name="ctooltipctrl"></a>  CToolTipCtrl::CToolTipCtrl  
 Oluşturur bir `CToolTipCtrl` nesne.  
  
```  
CToolTipCtrl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız `Create` sonra nesne oluşturma.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]  
  
##  <a name="deltool"></a>  CToolTipCtrl::DelTool  
 Tarafından belirtilen aracı kaldırır *pWnd* ve *nIDTool* koleksiyonundan bir araç ipucu denetimi tarafından desteklenen araçlar.  
  
```  
void DelTool(
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Aracı'nı içeren bir pencere işaretçisi.  
  
 *nIDTool*  
 Aracı kimliği.  
  
##  <a name="getbubblesize"></a>  CToolTipCtrl::GetBubbleSize  
 Araç İpucu VHD'nin boyutunu alır.  
  
```  
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lpToolInfo*  
 Araç ipucunun bir işaretçiye [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç İpucu boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_GETBUBBLESIZE](/windows/desktop/Controls/ttm-getbubblesize)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="getcurrenttool"></a>  CToolTipCtrl::GetCurrentTool  
 Boyut, konum ve metin, geçerli bir araç ipucu denetimi tarafından görüntülenen araç ipucu penceresinin gibi bilgileri alır.  
  
```  
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*lpToolInfo*|[out] İşaretçi bir [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) yapısı geçerli araç ipucu penceresi hakkında bilgi alır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bilgileri başarıyla alınırsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [TTM_GETCURRENTTOOL](/windows/desktop/Controls/ttm-getcurrenttool) Windows SDK'da açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, geçerli araç ipucu penceresi hakkında bilgi alır.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]  
  
##  <a name="getdelaytime"></a>  CToolTipCtrl::GetDelayTime  
 İlk açılır, alır ve bir araç ipucu denetimi için ayarlanmış süreleri reshow.  
  
```  
int GetDelayTime(DWORD dwDuration) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *dwDuration*  
 Hangi süre değerini belirten bayrak alınır. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
- TTDT_AUTOPOP alma araç ipucu penceresinin süre içinde bir Aracı'nın sınırlayıcı dikdörtgeni sabit bir işaretçi ise görünür kalır.  
  
- TTDT_INITIAL almak, işaretçi sabit araç ipucu penceresi önce Aracı'nın sınırlayıcı dikdörtgeni içinde kalması gereken süreyi görünür.  
  
- TTDT_RESHOW almak işaretçi olarak görünmesini sonraki araç ipucu windows geçen sürenin uzunluğunu bir araçtan diğerine taşır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Milisaniye cinsinden belirtilen gecikme süresi  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_GETDELAYTIME](/windows/desktop/Controls/ttm-getdelaytime)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="getmargin"></a>  CToolTipCtrl::GetMargin  
 Üst, sol, alt ve sağ kenar boşluklarını ayarlamak için bir araç ipucu penceresi alır.  
  
```  
void GetMargin(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lprc*  
 Adresi bir `RECT` kenar boşluğu bilgi alacak yapısı. Üyeleri [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı sınırlayıcı bir dikdörtgen tanımlamaz. Bu iletinin amacı doğrultusunda, Yapı üyeleri şu şekilde yorumlanır:  
  
|Üye|Temsili|  
|------------|--------------------|  
|`top`|Üst kenarlığın piksel cinsinden araç ipucu metnini üst arasındaki uzaklığı.|  
|`left`|Sol kenarlığın piksel cinsinden ipucu metnini sol ucundaki arasındaki uzaklığı.|  
|`bottom`|Alt Kenarlık ve piksel cinsinden ipucu metnini alt arasındaki uzaklık.|  
|`right`|Sağ Kenarlık ve piksel cinsinden İpucu metni doğru sonu arasındaki uzaklık.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_GETMARGIN](/windows/desktop/Controls/ttm-getmargin)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="getmaxtipwidth"></a>  CToolTipCtrl::GetMaxTipWidth  
 Bir araç ipucu penceresi için en fazla genişliğini alır.  
  
```  
int GetMaxTipWidth() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir araç ipucu penceresi için en fazla genişlik.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_GETMAXTIPWIDTH](/windows/desktop/Controls/ttm-getmaxtipwidth)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="gettext"></a>  CToolTipCtrl::GetText  
 Bir aracı için bir araç ipucunu denetimini tutar metni alır.  
  
```  
void GetText(
    CString& str,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *str*  
 Başvuru bir `CString` Aracı'nın metin alan nesnesi.  
  
 *pWnd*  
 Aracı'nı içeren bir pencere işaretçisi.  
  
 *nIDTool*  
 Aracı kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 *PWnd* ve *nIDTool* aracı parametreleri tanımlayın. Bu araç, önceki bir çağrı yoluyla araç ipucu denetimi ile daha önce kaydedilmiş ise `CToolTipCtrl::AddTool`, tarafından başvurulan nesne *str* parametresi, Aracı'nın metin atanır.  
  
##  <a name="gettipbkcolor"></a>  CToolTipCtrl::GetTipBkColor  
 Bir araç ipucu penceresi içinde arka plan rengini alır.  
  
```  
COLORREF GetTipBkColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COLORREF](/windows/desktop/gdi/colorref) arka plan rengini gösteren bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_GETTIPBKCOLOR](/windows/desktop/Controls/ttm-gettipbkcolor)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="gettiptextcolor"></a>  CToolTipCtrl::GetTipTextColor  
 Bir araç ipucu penceresindeki metin rengini alır.  
  
```  
COLORREF GetTipTextColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COLORREF](/windows/desktop/gdi/colorref) metin rengini gösteren bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_GETTIPTEXTCOLOR](/windows/desktop/Controls/ttm-gettiptextcolor)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="gettitle"></a>  CToolTipCtrl::GetTitle  
 Geçerli araç ipucu denetimi başlığını alır.  
  
```  
void GetTitle(PTTGETTITLE pttgt) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*pttgt*|[out] İşaretçi bir [TTGETTITLE](/windows/desktop/api/commctrl/ns-commctrl-_ttgettitle) araç ipucu denetimi hakkında bilgi içeren yapısı. Bu yöntem döndürüldüğünde, *pszTitle* üyesi [TTGETTITLE](/windows/desktop/api/commctrl/ns-commctrl-_ttgettitle) başlığın metin noktalarını yapılandırın.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [TTM_GETTITLE](/windows/desktop/Controls/ttm-gettitle) Windows SDK'da açıklanan ileti.  
  
##  <a name="gettoolcount"></a>  CToolTipCtrl::GetToolCount  
 Araç ipucunu denetimini ile kayıtlı araçları sayısını alır.  
  
```  
int GetToolCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araçlar sayısı ile araç ipucunu denetimini kayıtlı.  
  
##  <a name="gettoolinfo"></a>  CToolTipCtrl::GetToolInfo  
 Araç ipucunu denetimini tutan bir araç hakkında bilgi alır.  
  
```  
BOOL GetToolInfo(
    CToolInfo& ToolInfo,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *ToolInfo*  
 Başvuru bir `TOOLINFO` Aracı'nın metin alan nesnesi.  
  
 *pWnd*  
 Aracı'nı içeren bir pencere işaretçisi.  
  
 *nIDTool*  
 Aracı kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `hwnd` Ve `uId` üyeleri [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) yapısı tarafından başvurulan *CToolInfo* aracını belirleyin. Bu araç ile araç ipucunu denetimini önceki bir çağrı aracılığıyla kaydedilmişse `AddTool`, `TOOLINFO` yapısı aracıyla ilgili bilgilerle doldurulur.  
  
##  <a name="hittest"></a>  CToolTipCtrl::HitTest  
 Verilen aracının dikdörtgen içinde olup olmadığını belirlemek ve varsa aracı hakkında bilgi almak için bir nokta sınar.  
  
```  
BOOL HitTest(
    CWnd* pWnd,  
    CPoint pt,  
    LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Aracı'nı içeren bir pencere işaretçisi.  
  
 *PT*  
 İşaretçi bir `CPoint` test edilecek noktası koordinatları içeren nesne.  
  
 *lpToolInfo*  
 İşaretçi [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) aracı hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İsabet testi bilgileri tarafından belirtilen noktası Aracı'nın sınırlayıcı dikdörtgeni içinde ise sıfır olmayan; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, sıfır olmayan bir değer döndürürse, yapı tarafından işaret edilen *lpToolInfo* olan dikdörtgen bulunma noktası aracı hakkında bilgi ile doldurulur.  
  
 `TTHITTESTINFO` Yapısı şu şekilde tanımlanır:  
  
 `typedef struct _TT_HITTESTINFO { // tthti`  
  
 `HWND hwnd;   // handle of tool or window with tool`  
  
 `POINT pt;    // client coordinates of point to test`  
  
 `TOOLINFO ti; // receives information about the tool`  
  
 `} TTHITTESTINFO, FAR * LPHITTESTINFO;`  
  
 `hwnd`  
 Aracı'nın tanıtıcı belirtir.  
  
 `pt`  
 Bir nokta koordinatları noktası aracın içinde sınırlayıcı dikdörtgeni olduğunu belirtir.  
  
 `ti`  
 Aracı hakkında bilgi. Hakkında daha fazla bilgi için `TOOLINFO` yapısı için bkz: [CToolTipCtrl::GetToolInfo](#gettoolinfo).  
  
##  <a name="pop"></a>  CToolTipCtrl::Pop  
 Görüntülenen araç ipucu penceresi görünümden kaldırır.  
  
```  
void Pop();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_POP](/windows/desktop/Controls/ttm-pop)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="popup"></a>  CToolTipCtrl::Popup  
 Son fare mesajı koordinatlarda görüntülenecek geçerli araç ipucu denetimi neden olur.  
  
```  
void Popup();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [TTM_POPUP](/windows/desktop/Controls/ttm-popup) Windows SDK'da açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir araç ipucu penceresi görüntülenir.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]  
  
##  <a name="relayevent"></a>  CToolTipCtrl::RelayEvent  
 Bir fare mesajı işlemek için bir araç ipucunu denetimini geçirir.  
  
```  
void RelayEvent(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMsg*  
 İşaretçi bir [MSG](https://msdn.microsoft.com/library/windows/desktop/ms644958) geçiş iletisi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Araç ipucunu denetimini tarafından kendisine gönderilen yalnızca aşağıdaki iletileri işleyen `RelayEvent`:  
  
|WM_LBUTTONDOWN|WM_MOUSEMOVE|  
|---------------------|-------------------|  
|WM_LBUTTONUP|WM_RBUTTONDOWN|  
|WM_MBUTTONDOWN|WM_RBUTTONUP|  
|WM_MBUTTONUP||  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="setdelaytime"></a>  CToolTipCtrl::SetDelayTime  
 Gecikme süresini bir araç ipucu denetimi için ayarlar.  
  
```  
void SetDelayTime(UINT nDelay);

 
void SetDelayTime(
    DWORD dwDuration,  
    int iTime);
```  
  
### <a name="parameters"></a>Parametreler  
 *nDelay*  
 Yeni gecikme süresi, milisaniye cinsinden belirtir.  
  
 *dwDuration*  
 Hangi süre değerini belirten bayrak alınır. Bkz: [CToolTipCtrl::GetDelayTime](#getdelaytime) geçerli değerlerin bir açıklaması.  
  
 *iTime*  
 Belirtilen gecikme süresi, milisaniye cinsinden.  
  
### <a name="remarks"></a>Açıklamalar  
 Gecikme süresi, imleç bir aracı üzerinde araç ipucu penceresi görüntülenmeden önce bekleyeceği süreyi uzunluğudur. Varsayılan gecikme süresi, 500 milisaniyedir.  
  
##  <a name="setmargin"></a>  CToolTipCtrl::SetMargin  
 Üst, sol, alt ve sağ kenar boşluklarının bir araç ipucu penceresi için ayarlar.  
  
```  
void SetMargin(LPRECT lprc);
```  
  
### <a name="parameters"></a>Parametreler  
 *lprc*  
 Adresi bir `RECT` ayarlanacak kenar boşluğu bilgileri içeren yapısı. Üyeleri `RECT` yapısı sınırlayıcı bir dikdörtgen tanımlamaz. Bkz: [CToolTipCtrl::GetMargin](#getmargin) kenar boşluğu bilgileri açıklaması.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_SETMARGIN](/windows/desktop/Controls/ttm-setmargin)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="setmaxtipwidth"></a>  CToolTipCtrl::SetMaxTipWidth  
 Bir araç ipucu penceresi için en fazla genişliğini belirler.  
  
```  
int SetMaxTipWidth(int iWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 *iWidth*  
 Ayarlanacak en fazla araç ipucu penceresi genişliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki en yüksek ipucu genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_SETMAXTIPWIDTH](/windows/desktop/Controls/ttm-setmaxtipwidth)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="settipbkcolor"></a>  CToolTipCtrl::SetTipBkColor  
 Bir araç ipucu penceresinde arka plan rengini ayarlar.  
  
```  
void SetTipBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parametreler  
 *CLR*  
 Yeni arka plan rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_SETTIPBKCOLOR](/windows/desktop/Controls/ttm-settipbkcolor)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="settiptextcolor"></a>  CToolTipCtrl::SetTipTextColor  
 Bir araç ipucu penceresinde metin rengini ayarlar.  
  
```  
void SetTipTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parametreler  
 *CLR*  
 Yeni metin rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_SETTIPTEXTCOLOR](/windows/desktop/Controls/ttm-settiptextcolor)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="settitle"></a>  CToolTipCtrl::SetTitle  
 Standart bir simge ve başlık dize için bir araç ipucu ekler.  
  
```  
BOOL SetTitle(
    UINT uIcon,  
    LPCTSTR lpstrTitle);
```  
  
### <a name="parameters"></a>Parametreler  
 *uIcon*  
 Bkz: *simgesi* içinde [TTM_SETTITLE](/windows/desktop/Controls/ttm-settitle) Windows SDK.  
  
 *lpstrTitle*  
 Başlık dizeye yönelik işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [TTM_SETTITLE](/windows/desktop/Controls/ttm-settitle)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="settoolinfo"></a>  CToolTipCtrl::SetToolInfo  
 Bir aracı için bir araç ipucu tutar bilgilerini ayarlar.  
  
```  
void SetToolInfo(LPTOOLINFO lpToolInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpToolInfo*  
 Bir işaretçi bir [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) ayarlamak üzere bilgi belirten yapısı.  
  
##  <a name="settoolrect"></a>  CToolTipCtrl::SetToolRect  
 Yeni sınırlayıcı bir dikdörtgen aracı için ayarlar.  
  
```  
void SetToolRect(
    CWnd* pWnd,  
    UINT_PTR nIDTool,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Aracı'nı içeren bir pencere işaretçisi.  
  
 *nIDTool*  
 Aracı kimliği.  
  
 *lpRect*  
 İşaretçi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı yeni dikdörtgen belirtme.  
  
##  <a name="setwindowtheme"></a>  CToolTipCtrl::SetWindowTheme  
 Araç İpucu penceresi visual stilini ayarlar.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pszSubAppName*  
 Ayarlanacak görsel stili içeren bir Unicode dize işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğine öykünür [TTM_SETWINDOWTHEME](/windows/desktop/Controls/ttm-setwindowtheme) Windows SDK içinde açıklandığı gibi ileti.  
  
##  <a name="update"></a>  CToolTipCtrl::Update  
 Geçerli aracın çizilmesini zorlar.  
  
```  
void Update();
```  
  
##  <a name="updatetiptext"></a>  CToolTipCtrl::UpdateTipText  
 Bu denetimin araçları için araç ipucu metni güncelleştirir.  
  
```  
void UpdateTipText(
    LPCTSTR lpszText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);

 
void UpdateTipText(
    UINT nIDText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszText*  
 Aracı için metin işaretçisi.  
  
 *pWnd*  
 Aracı'nı içeren bir pencere işaretçisi.  
  
 *nIDTool*  
 Aracı kimliği.  
  
 *nIDText*  
 Aracı için metni içeren dize kaynağının kimliği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CToolBar Sınıfı](../../mfc/reference/ctoolbar-class.md)
