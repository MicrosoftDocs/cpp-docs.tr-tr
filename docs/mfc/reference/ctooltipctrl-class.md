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
ms.openlocfilehash: 9436f3809a337b732a2e95d9c30b9baa45c4e8ba
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123116"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl sınıfı
"Araç ipucu denetimi," tek satırlık bir uygulamada bir aracı amacını açıklayan metin görüntüler küçük bir açılır pencere işlevselliği kapsar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|Oluşturan bir `CToolTipCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CToolTipCtrl::Activate](#activate)|Etkinleştirir ve araç ipucunu denetimini devre dışı bırakır.|  
|[CToolTipCtrl::AddTool](#addtool)|Bir aracı araç ipucunu denetimini ile kaydeder.|  
|[CToolTipCtrl::AdjustRect](#adjustrect)|Bir araç ipucu denetimi metnini arasında dönüştürür ve onun penceresi dikdörtgeni dikdörtgen görüntüler.|  
|[CToolTipCtrl::Create](#create)|Bir araç ipucunu denetimini oluşturur ve ona ekler bir `CToolTipCtrl` nesnesi.|  
|[CToolTipCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri içeren bir araç ipucunu denetimini oluşturur ve ekler bir `CToolTipCtrl` nesnesi.|  
|[CToolTipCtrl::DelTool](#deltool)|Bir aracı araç ipucu denetiminden kaldırır.|  
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|Araç İpucu boyutunu alır.|  
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|Boyut, konum ve geçerli araç ipucu denetimi görüntüler araç ipucu penceresinin metin gibi bilgileri alır.|  
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|Başlangıç, açılır ve reshow alır bir araç için ayarlanmış süreleri ipucu denetimi.|  
|[CToolTipCtrl::GetMargin](#getmargin)|Üst ve sol, alt ve bir araç ipucu penceresi için ayarlanan sağ kenar boşluklarının alır.|  
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|Araç İpucu penceresi için en büyük genişliği alır.|  
|[CToolTipCtrl::GetText](#gettext)|Bir araç için bir araç ipucunu denetimini tutar metni alır.|  
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|Araç İpucu penceresinde arka plan rengini alır.|  
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|Araç İpucu penceresinde metin rengini alır.|  
|[CToolTipCtrl::GetTitle](#gettitle)|Geçerli araç ipucu denetimi başlığını alır.|  
|[CToolTipCtrl::GetToolCount](#gettoolcount)|Bir araç ipucunu denetimini tarafından tutulan araçları sayısını alır.|  
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|Bir araç ipucunu denetimini tutan bir araç hakkında bilgi alır.|  
|[CToolTipCtrl::HitTest](#hittest)|Verilen aracı sınırlayıcı dikdörtgenini içinde olup olmadığını belirlemek için bir noktası sınar. Bu durumda, aracı hakkında bilgi alır.|  
|[CToolTipCtrl::Pop](#pop)|Görüntülenen araç ipucu penceresi görünümden kaldırır.|  
|[CToolTipCtrl::Popup](#popup)|Son fare ileti koordinatlarda görüntülenecek geçerli araç ipucu denetimi neden olur.|  
|[CToolTipCtrl::RelayEvent](#relayevent)|Fare ileti işleme için bir araç ipucunu denetimini geçirir.|  
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|İlk açılır, ayarlar ve bir araç ipucunu denetimini sürelerini reshow.|  
|[CToolTipCtrl::SetMargin](#setmargin)|Üst ve sol, alt ve sağ kenar boşlukları bir araç ipucu penceresi için ayarlar.|  
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|Araç İpucu penceresi için en büyük genişliği ayarlar.|  
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|Arka plan rengi, araç ipucu penceresinde ayarlar.|  
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|Araç İpucu penceresinde metin rengini belirler.|  
|[CToolTipCtrl::SetTitle](#settitle)|Standart bir simge ve başlık dize için bir araç ipucu ekler.|  
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|Bir araç için bir araç ipucu tutar bilgilerini ayarlar.|  
|[CToolTipCtrl::SetToolRect](#settoolrect)|Bir aracı için yeni bir sınırlayıcı dikdörtgenini ayarlar.|  
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|Araç İpucu penceresi visual stilini ayarlar.|  
|[CToolTipCtrl::Update](#update)|Geçerli aracın çizilmesi zorlar.|  
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|Bir aracı için araç ipucu metni ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir "" ya da bir pencere, alt pencere veya denetim ya da bir uygulama tanımlı dikdörtgen pencerenin istemci alanda gibi aracıdır. Araç İpucu çoğu yalnızca kullanıcı aracını kullanarak imleci koyar ve onu var. yaklaşık yarısı için ikinci bırakır görünmesini zaman gizlenir. Araç İpucu imlecin yanında görünür ve kullanıcı fare düğmesini tıklattığında ya da imleci Aracı'nı devre dışı taşır kaybolur.  
  
 `CToolTipCtrl` Araç İpucu metni, araç ipucu penceresi kendisini genişliğini ve araç ipucu arka plan ve metin rengini çevreleyen kenar boşluğu genişlikleri başlangıç saatini ve süresini araç ipucu denetimi işlevsellik sağlar. Bir tek araç ipucunu denetimini birden fazla aracı için bilgi sağlayabilir.  
  
 `CToolTipCtrl` Sınıfı Windows ortak araç ipucunu denetimini işlevselliğini sağlar. Bu denetim (ve bu nedenle `CToolTipCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürümler 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Araç ipuçlarını etkinleştirme hakkında daha fazla bilgi için bkz: [araç ipuçları Windows olmayan CFrameWnd türetilen](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 Kullanma hakkında daha fazla bilgi için `CToolTipCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [CToolTipCtrl kullanarak](../../mfc/using-ctooltipctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="activate"></a>  CToolTipCtrl::Activate  
 Bu işlevi etkinleştirmek veya devre dışı bir araç ipucu denetimi için çağırın.  
  
```  
void Activate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 *bActivate*  
 Araç ipucunu denetimini etkinleştirilmiş veya devre dışı olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *bActivate* doğru ise, denetimi etkinleştirilmiş; FALSE ise, onu devre dışı bırakılır.  
  
 Bir araç ipucunu denetimini etkin olduğunda imleci denetimle kayıtlı bir aracı üzerinde olduğunda araç ipucu bilgi görüntülenir; etkin olduğunda, araç ipucu bilgi görüntülenmezse, hatta imleci bir aracı üzerinde olduğunda.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="addtool"></a>  CToolTipCtrl::AddTool  
 Bir aracı araç ipucunu denetimini ile kaydeder.  
  
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
 Aracı içeren bir pencere için işaretçi.  
  
 *nIDText*  
 Metin aracı içeren dize kaynak kimliği.  
  
 *lpRectTool*  
 İşaretçi bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) aracı koordinatlarını içeren yapısını çevreleyen dikdörtgen. İstemci alanı tarafından tanımlanan penceresinin sol üst köşesindeki göre koordinatlar belirlenir *pWnd*.  
  
 *nIDTool*  
 Aracı'nın kimliği.  
  
 *lpszText*  
 Aracı için metin işaretçisi. Bu parametre LPSTR_TEXTCALLBACK değer içeriyorsa, pencerenin üst öğeye TTN_NEEDTEXT bildirim iletilerini gidin, *pWnd* işaret eder.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 *LpRectTool* ve *nIDTool* parametrelerinin her ikisini de olmalıdır geçerli veya *lpRectTool* null, *nIDTool* 0 olmalıdır.  
  
 Bir araç ipucunu denetimini birden fazla aracı ile ilişkili olabilir. İmleç araç olduğunda araç ipucunda depolanan bilgileri görüntülenir böylece araç ipucunu denetimini ile bir aracı kaydetmek için bu işlevini çağırın.  
  
> [!NOTE]
>  Araç ipucunu kullanarak statik denetimine ayarlanamıyor `AddTool`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="adjustrect"></a>  CToolTipCtrl::AdjustRect  
 Bir araç ipucu denetimi metnini arasında dönüştürür ve onun penceresi dikdörtgeni dikdörtgen görüntüler.  
  
```  
BOOL AdjustRect(
    LPRECT lprc,  
    BOOL bLarger = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *lprc*  
 İşaretçi bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) bir araç ipucu penceresi dikdörtgen veya metin görüntüleme dikdörtgen tutan yapısı.  
  
 *bLarger*  
 TRUE ise, *lprc* bir metin görüntüleme dikdörtgen belirtmek için kullanılır ve karşılık gelen Pencere dikdörtgeni alır. FALSE ise, *lprc* bir pencere dikdörtgeni belirtmek için kullanılır ve ilgili metin görüntüleme dikdörtgenini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dikdörtgen başarıyla ayarlanıyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu bir araç ipucu denetimin metin görüntüleme dikdörtgenini onun penceresi dikdörtgeni ya da belirtilen metin görüntüleme dikdörtgenini görüntülemek için gereken araç ipucu Pencere dikdörtgeni hesaplar.  
  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_ADJUSTRECT](http://msdn.microsoft.com/library/windows/desktop/bb760352), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="create"></a>  CToolTipCtrl::Create  
 Bir araç ipucunu denetimini oluşturur ve ona ekler bir `CToolTipCtrl` nesnesi.  
  
```  
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentWnd*  
 Araç İpucu denetimin ana penceresinde, genellikle belirten bir `CDialog`. NULL olmamalıdır.  
  
 *dwStyle*  
 Araç İpucu denetimin stilini belirtir. Bkz: **açıklamalar** daha fazla bilgi için bölüm.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CToolTipCtrl` nesnesi, başarıyla oluşturulmuş aksi 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CToolTipCtrl` iki adımda. İlk olarak, oluşturmak için oluşturucu çağrısı `CToolTipCtrl` nesnesini genişletin ve ardından arama `Create` araç ipucunu denetimini oluşturmak ve ona eklemek için `CToolTipCtrl` nesnesi.  
  
 *DwStyle* parametresi, herhangi bir bileşimi olabilir [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles). Ayrıca, bir araç ipucunu denetimini iki sınıf özgü stillerdeki: TTS_ALWAYSTIP ve TTS_NOPREFIX.  
  
|Stil|Açıklama|  
|-----------|-------------|  
|TTS_ALWAYSTIP|İmleç araç ipucu denetimin sahibi penceresi etkin veya devre dışı olup bağımsız olarak bir aracı üzerinde olduğunda araç ipucu görüntüleneceğini belirtir. Bu stili araç ipucunu denetimini aracın sahibi penceresi etkin olduğunda, ancak etkin olmadığında görüntülenir.|  
|TTS_NOPREFIX|Bu stili (&) karakter dizesinden çıkarma sistemin engeller. Bir araç ipucunu denetimini TTS_NOPREFIX stili yoksa, sistem otomatik olarak bir araç ipucunu denetimini metinde ve her iki menü öğesi olarak aynı dizeyi kullanmak uygulama izin verme ve işareti karakteri kaldırır.|  
  
 Bir araç ipucunu denetimini olup onları denetimi oluştururken belirttiğiniz bağımsız olarak WS_POPUP ve ws_ex_toolwındow pencere stilleri, sahiptir.  
  
 Bir araç ipucunu denetimini genişletilmiş windows stilleri ile oluşturmak için arama [CToolTipCtrl::CreateEx](#createex) yerine `Create`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="createex"></a>  CToolTipCtrl::CreateEx  
 Bir denetimi (alt pencere) oluşturur ve bu ilişkilendirmeyi `CToolTipCtrl` nesnesi.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwStyle = 0,  
    DWORD dwStyleEx = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentWnd*  
 Denetimin üst penceresi için bir işaretçi.  
  
 *dwStyle*  
 Araç İpucu denetimin stilini belirtir. Bkz: **açıklamalar** bölümünü [oluşturma](#create) daha fazla bilgi için.  
  
 *dwStyleEx*  
 Oluşturulan denetim genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri listesi için bkz: *dwExStyle* parametresi için [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır değilse 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine `Create` Windows genişletilmiş stili önsöz tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için **WS_EX_**.  
  
##  <a name="ctooltipctrl"></a>  CToolTipCtrl::CToolTipCtrl  
 Oluşturan bir `CToolTipCtrl` nesnesi.  
  
```  
CToolTipCtrl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız `Create` nesne oluşturma sonra.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]  
  
##  <a name="deltool"></a>  CToolTipCtrl::DelTool  
 Tarafından belirlenen aracı kaldırır *pWnd* ve *nIDTool* bir araç ipucunu denetimini tarafından desteklenen araçları koleksiyonundan.  
  
```  
void DelTool(
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Aracı içeren bir pencere için işaretçi.  
  
 *nIDTool*  
 Aracı'nın kimliği.  
  
##  <a name="getbubblesize"></a>  CToolTipCtrl::GetBubbleSize  
 Araç İpucu boyutunu alır.  
  
```  
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lpToolInfo*  
 Araç İpucu 's gösteren bir işaretçi [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç İpucu boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_GETBUBBLESIZE](http://msdn.microsoft.com/library/windows/desktop/bb760387), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="getcurrenttool"></a>  CToolTipCtrl::GetCurrentTool  
 Boyut, konum ve geçerli araç ipucu denetimi tarafından görüntülenen araç ipucu pencere metninin gibi bilgileri alır.  
  
```  
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out] *lpToolInfo*|İşaretçi bir [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) yapısı geçerli araç ipucu penceresi hakkında bilgi alır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bilgileri başarıyla alınırsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [TTM_GETCURRENTTOOL](http://msdn.microsoft.com/library/windows/desktop/bb760389) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde geçerli araç ipucu penceresi hakkında bilgi alır.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]  
  
##  <a name="getdelaytime"></a>  CToolTipCtrl::GetDelayTime  
 Açılır, ilk alır ve araç ipucu denetimi için ayarlanmış süreleri reshow.  
  
```  
int GetDelayTime(DWORD dwDuration) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *dwDuration*  
 Hangi süre değerini belirten bayrak alınır. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
- TTDT_AUTOPOP almak araç ipucu penceresi süre işaretçi bir aracın sınırlayıcı dikdörtgenini içinde sabit ise görünür kalır.  
  
- TTDT_INITIAL almak işaretçinin sabit bir aracın sınırlayıcı dikdörtgenini önce araç ipucu penceresi içinde kalması gereken süreyi görüntülenir.  
  
- TTDT_RESHOW almak sonraki araç ipucu windows işaretçi olarak görünmesi için geçen süre bir aracından diğerine taşır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Milisaniye cinsinden belirtilen gecikme süresi  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_GETDELAYTIME](http://msdn.microsoft.com/library/windows/desktop/bb760390), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="getmargin"></a>  CToolTipCtrl::GetMargin  
 Üst ve sol, alt ve sağ kenar boşlukları için bir araç ipucu penceresi ayarlayın alır.  
  
```  
void GetMargin(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lprc*  
 Adres bir `RECT` kenar boşluğu bilgi alacak yapısı. Üyeleri [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı sınırlayıcı dikdörtgenini tanımlamaz. Bu ileti amacıyla yapı üyeleri şu şekilde yorumlanır:  
  
|Üye|Gösterimi|  
|------------|--------------------|  
|`top`|Üst kenarlığın piksel cinsinden araç ipucu metni üst arasındaki uzaklığı.|  
|`left`|Sol kenarlığın piksel cinsinden ipucu metnin sol sonuna arasındaki uzaklığı.|  
|`bottom`|Alt kenarlığın piksel cinsinden ipucu metnin altına arasındaki uzaklığı.|  
|`right`|Sağ kenarlığın piksel cinsinden ipucu metnini sağ uç arasındaki uzaklığı.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_GETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760391), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="getmaxtipwidth"></a>  CToolTipCtrl::GetMaxTipWidth  
 Araç İpucu penceresi için en büyük genişliği alır.  
  
```  
int GetMaxTipWidth() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç İpucu penceresi için en büyük genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_GETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760392), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="gettext"></a>  CToolTipCtrl::GetText  
 Bir araç için bir araç ipucunu denetimini tutar metni alır.  
  
```  
void GetText(
    CString& str,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *str*  
 Başvuru bir `CString` aracın metin alan nesnesi.  
  
 *pWnd*  
 Aracı içeren bir pencere için işaretçi.  
  
 *nIDTool*  
 Aracı'nın kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 *PWnd* ve *nIDTool* parametreleri Aracı'nı belirleyin. Bu aracı önceden önceki çağrısıyla araç ipucu denetimi ile kaydedilmişse `CToolTipCtrl::AddTool`, tarafından başvurulan nesne *str* parametresi, aracın metin atanır.  
  
##  <a name="gettipbkcolor"></a>  CToolTipCtrl::GetTipBkColor  
 Araç İpucu penceresinde arka plan rengini alır.  
  
```  
COLORREF GetTipBkColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) arka plan rengi temsil eden bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_GETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760394), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="gettiptextcolor"></a>  CToolTipCtrl::GetTipTextColor  
 Araç İpucu penceresinde metin rengini alır.  
  
```  
COLORREF GetTipTextColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) metin rengi temsil eden bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_GETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760395), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="gettitle"></a>  CToolTipCtrl::GetTitle  
 Geçerli araç ipucu denetimi başlığını alır.  
  
```  
void GetTitle(PTTGETTITLE pttgt) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out] *pttgt*|İşaretçi bir [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) araç ipucu denetimi hakkında bilgi içeren yapısı. Bu yöntem döndürüldüğünde, *pszTitle* üyesi [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) yapısı başlık metni noktaları.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [TTM_GETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760396) Windows SDK'ın açıklanan ileti.  
  
##  <a name="gettoolcount"></a>  CToolTipCtrl::GetToolCount  
 Araç ipucunu denetimini ile kayıtlı araçları sayısını alır.  
  
```  
int GetToolCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç ipucunu denetimini ile kayıtlı bir araçları sayısı.  
  
##  <a name="gettoolinfo"></a>  CToolTipCtrl::GetToolInfo  
 Bir araç ipucunu denetimini tutan bir araç hakkında bilgi alır.  
  
```  
BOOL GetToolInfo(
    CToolInfo& ToolInfo,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *ToolInfo*  
 Başvuru bir `TOOLINFO` aracın metin alan nesnesi.  
  
 *pWnd*  
 Aracı içeren bir pencere için işaretçi.  
  
 *nIDTool*  
 Aracı'nın kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `hwnd` Ve `uId` üyeleri [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) başvurduğu yapısı *CToolInfo* Aracı'nı belirleyin. Bu aracı önceki çağrısıyla araç ipucu denetimi ile kayıtlı olup olmadığını `AddTool`, `TOOLINFO` yapısı aracı hakkında bilgi ile doldurulur.  
  
##  <a name="hittest"></a>  CToolTipCtrl::HitTest  
 Verilen aracı sınırlayıcı dikdörtgenini içinde olup olmadığını belirlemek ve varsa, aracı hakkında bilgi almak için bir noktası sınar.  
  
```  
BOOL HitTest(
    CWnd* pWnd,  
    CPoint pt,  
    LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Aracı içeren bir pencere için işaretçi.  
  
 *PT*  
 İşaretçi bir `CPoint` sınanacak noktası koordinatları içeren nesne.  
  
 *lpToolInfo*  
 İşaretçi [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) aracı hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İsabet testi bilgileri tarafından belirtilen noktası aracın sınırlayıcı dikdörtgenini içinde ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi sıfır olmayan bir değer döndürürse, yapısı işaret için tarafından *lpToolInfo* noktası olan dikdörtgen içinde kaynaklandığını araç hakkında bilgi ile doldurulur.  
  
 `TTHITTESTINFO` Yapısı şu şekilde tanımlanır:  
  
 `typedef struct _TT_HITTESTINFO { // tthti`  
  
 `HWND hwnd;   // handle of tool or window with tool`  
  
 `POINT pt;    // client coordinates of point to test`  
  
 `TOOLINFO ti; // receives information about the tool`  
  
 `} TTHITTESTINFO, FAR * LPHITTESTINFO;`  
  
 `hwnd`  
 Aracın işleyiciyi belirtir.  
  
 `pt`  
 Noktası dikdörtgen aracın içinde sınırlayıcı bir noktanın koordinatlarını belirtir.  
  
 `ti`  
 Aracı hakkında bilgi. Hakkında daha fazla bilgi için `TOOLINFO` yapısı için bkz: [CToolTipCtrl::GetToolInfo](#gettoolinfo).  
  
##  <a name="pop"></a>  CToolTipCtrl::Pop  
 Görüntülenen araç ipucu penceresi görünümden kaldırır.  
  
```  
void Pop();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_POP](http://msdn.microsoft.com/library/windows/desktop/bb760401), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="popup"></a>  CToolTipCtrl::Popup  
 Son fare ileti koordinatlarda görüntülenecek geçerli araç ipucu denetimi neden olur.  
  
```  
void Popup();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [TTM_POPUP](http://msdn.microsoft.com/library/windows/desktop/bb760402) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir araç ipucu penceresi görüntüler.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]  
  
##  <a name="relayevent"></a>  CToolTipCtrl::RelayEvent  
 Fare ileti işleme için bir araç ipucunu denetimini geçirir.  
  
```  
void RelayEvent(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMsg*  
 İşaretçi bir [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) geçiş iletiye içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir araç ipucunu denetimini tarafından kendisine gönderilen yalnızca aşağıdaki iletileri işleyen `RelayEvent`:  
  
|WM_LBUTTONDOWN|WM_MOUSEMOVE|  
|---------------------|-------------------|  
|WM_LBUTTONUP|WM_RBUTTONDOWN|  
|WM_MBUTTONDOWN|WM_RBUTTONUP|  
|WM_MBUTTONUP||  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="setdelaytime"></a>  CToolTipCtrl::SetDelayTime  
 Gecikme süresi bir araç ipucu denetimi için ayarlar.  
  
```  
void SetDelayTime(UINT nDelay);

 
void SetDelayTime(
    DWORD dwDuration,  
    int iTime);
```  
  
### <a name="parameters"></a>Parametreler  
 *nDelay*  
 Yeni gecikme süresini milisaniye cinsinden belirtir.  
  
 *dwDuration*  
 Hangi süre değerini belirten bayrak alınır. Bkz: [CToolTipCtrl::GetDelayTime](#getdelaytime) geçerli değerler açıklaması.  
  
 *iTime*  
 Belirtilen gecikme süresi, milisaniye cinsinden.  
  
### <a name="remarks"></a>Açıklamalar  
 Gecikme süresi araç ipucu penceresi görünmeden önce imleci bir aracı üzerinde kalması gereken süreyi ' dir. Varsayılan gecikme süresi 500 milisaniyedir.  
  
##  <a name="setmargin"></a>  CToolTipCtrl::SetMargin  
 Üst ve sol, alt ve sağ kenar boşlukları bir araç ipucu penceresi için ayarlar.  
  
```  
void SetMargin(LPRECT lprc);
```  
  
### <a name="parameters"></a>Parametreler  
 *lprc*  
 Adres bir `RECT` ayarlanacak kenar boşluğu bilgi içeren yapısı. Üyeleri `RECT` yapısı sınırlayıcı dikdörtgenini tanımlamaz. Bkz: [CToolTipCtrl::GetMargin](#getmargin) kenar boşluğu bilgi açıklaması.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_SETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760406), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="setmaxtipwidth"></a>  CToolTipCtrl::SetMaxTipWidth  
 Araç İpucu penceresi için en büyük genişliği ayarlar.  
  
```  
int SetMaxTipWidth(int iWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 *iWidth*  
 Ayarlanacak maksimum araç ipucu pencere genişliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki en büyük ipucu genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_SETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760408), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="settipbkcolor"></a>  CToolTipCtrl::SetTipBkColor  
 Arka plan rengi, araç ipucu penceresinde ayarlar.  
  
```  
void SetTipBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parametreler  
 *CLR*  
 Yeni arka plan rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_SETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760411), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="settiptextcolor"></a>  CToolTipCtrl::SetTipTextColor  
 Araç İpucu penceresinde metin rengini belirler.  
  
```  
void SetTipTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parametreler  
 *CLR*  
 Yeni metin rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_SETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760413), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="settitle"></a>  CToolTipCtrl::SetTitle  
 Standart bir simge ve başlık dize için bir araç ipucu ekler.  
  
```  
BOOL SetTitle(
    UINT uIcon,  
    LPCTSTR lpstrTitle);
```  
  
### <a name="parameters"></a>Parametreler  
 *uIcon*  
 Bkz: *simgesi* içinde [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414) Windows SDK'sındaki.  
  
 *lpstrTitle*  
 Başlık dize işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="settoolinfo"></a>  CToolTipCtrl::SetToolInfo  
 Bir araç için bir araç ipucu tutar bilgilerini ayarlar.  
  
```  
void SetToolInfo(LPTOOLINFO lpToolInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpToolInfo*  
 Bir işaretçi bir [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) yapısı ayarlamak için bilgileri belirtir.  
  
##  <a name="settoolrect"></a>  CToolTipCtrl::SetToolRect  
 Bir aracı için yeni bir sınırlayıcı dikdörtgenini ayarlar.  
  
```  
void SetToolRect(
    CWnd* pWnd,  
    UINT_PTR nIDTool,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Aracı içeren bir pencere için işaretçi.  
  
 *nIDTool*  
 Aracı'nın kimliği.  
  
 *lpRect*  
 İşaretçi bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yeni sınırlayıcı dikdörtgenini belirtme yapısı.  
  
##  <a name="setwindowtheme"></a>  CToolTipCtrl::SetWindowTheme  
 Araç İpucu penceresi visual stilini ayarlar.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pszSubAppName*  
 Ayarlamak için görsel stil içeren bir Unicode dize için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen [TTM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb760418) , Windows SDK'ın açıklandığı gibi ileti.  
  
##  <a name="update"></a>  CToolTipCtrl::Update  
 Geçerli aracın çizilmesi zorlar.  
  
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
 Aracı içeren bir pencere için işaretçi.  
  
 *nIDTool*  
 Aracı'nın kimliği.  
  
 *nIDText*  
 Metin aracı içeren dize kaynak kimliği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CToolBar Sınıfı](../../mfc/reference/ctoolbar-class.md)
