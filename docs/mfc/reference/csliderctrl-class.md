---
title: CSliderCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e5b0fac11c2472bbaf0d5f4a3ede7d4f5658f9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377164"
---
# <a name="csliderctrl-class"></a>CSliderCtrl sınıfı
Windows ortak kaydırıcı denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|Oluşturan bir `CSliderCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](#clearsel)|Kaydırıcı denetimi geçerli seçim temizler.|  
|[CSliderCtrl::ClearTics](#cleartics)|Geçerli değer çizgilerinin kaydırıcı denetimden kaldırır.|  
|[CSliderCtrl::Create](#create)|Kaydırıcı denetimi oluşturur ve ona ekler bir `CSliderCtrl` nesnesi.|  
|[CSliderCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri içeren bir kaydırıcı denetimi oluşturur ve ekler bir `CSliderCtrl` nesnesi.|  
|[CSliderCtrl::GetBuddy](#getbuddy)|Belirtilen konumda bir kaydırıcı denetimi arkadaş penceresi tanıtıcısını alır.|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|Kaydırıcı denetim kanalı boyutunu alır.|  
|[CSliderCtrl::GetLineSize](#getlinesize)|Kaydırıcı denetimi satır boyutunu alır.|  
|[CSliderCtrl::GetNumTics](#getnumtics)|Kaydırıcı denetimi onay işaretleri sayısını alır.|  
|[CSliderCtrl::GetPageSize](#getpagesize)|Kaydırıcı denetimi sayfa boyutunu alır.|  
|[CSliderCtrl::GetPos](#getpos)|Kaydırıcı geçerli konumunu alır.|  
|[CSliderCtrl::GetRange](#getrange)|Kaydırıcı için minimum ve maksimum konumları alır.|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|Bir kaydırıcının en büyük konumunu alır.|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|Bir kaydırıcının en düşük konumunu alır.|  
|[CSliderCtrl::GetSelection](#getselection)|Geçerli seçimin aralığını alır.|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|Kaydırıcı geçerli trackbar denetimi, uzunluğunu alır.|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|Kaydırıcı denetim Flash boyutunu alır.|  
|[CSliderCtrl::GetTic](#gettic)|Belirtilen değer çizgisi konumunu alır.|  
|[CSliderCtrl::GetTicArray](#getticarray)|Kaydırıcı denetimi için onay işareti konumlarına dizisi alır.|  
|[CSliderCtrl::GetTicPos](#getticpos)|İstemci koordinatları belirtilen değer çizgisi konumunu alır.|  
|[CSliderCtrl::GetToolTips](#gettooltips)|Kaydırıcı denetimi için atanan araç ipucu denetimi için tanıtıcı varsa alır.|  
|[CSliderCtrl::SetBuddy](#setbuddy)|Kaydırıcı denetimi arkadaş pencere olarak bir pencere atar.|  
|[CSliderCtrl::SetLineSize](#setlinesize)|Kaydırıcı denetimi satır boyutunu ayarlar.|  
|[CSliderCtrl::SetPageSize](#setpagesize)|Kaydırıcı denetimi sayfa boyutunu ayarlar.|  
|[CSliderCtrl::SetPos](#setpos)|Kaydırıcı geçerli konumunu ayarlar.|  
|[CSliderCtrl::SetRange](#setrange)|Kaydırıcı için minimum ve maksimum konumlar ayarlar.|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|Bir kaydırıcının en büyük konumunu ayarlar.|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|Bir kaydırıcının en düşük konumunu ayarlar.|  
|[CSliderCtrl::SetSelection](#setselection)|Geçerli seçim aralığını ayarlar.|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|Kaydırıcı uzunluğu, geçerli trackbar denetimi ayarlar.|  
|[CSliderCtrl::SetTic](#settic)|Belirtilen değer çizgisi konumunu ayarlar.|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|Değer çizgilerinin sıklığını kaydırıcı denetimi artışı başına işaretleri ayarlar.|  
|[CSliderCtrl::SetTipSide](#settipside)|Konumlar bir araç ipucu denetimi trackbar denetimi tarafından kullanılır.|  
|[CSliderCtrl::SetToolTips](#settooltips)|Bir araç ipucu denetimi için kaydırıcı denetimi atar.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Kaydırıcı denetimi" (trackbar olarak da bilinir) bir kaydırıcı ve isteğe bağlı değer çizgileri içeren bir penceredir. Kullanıcı, fare veya yön tuşlarını kullanarak, kaydırıcıyı geçtiğinde, denetim değişikliği göstermek için bildirim iletileri gönderir.  
  
 Kaydırıcı denetimleri ayrık bir değer veya bir dizi ardışık değerleri bir aralık seçmek için kullanıcı istediğinizde faydalıdır. Örneğin, verilen değer çizgisi için kaydırıcıyı hareket ettirerek klavye yineleme oranını ayarlamak izin vermek için kaydırıcı denetimi kullanabilirsiniz.  
  
 Bu denetim (ve bu nedenle `CSliderCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Kaydırıcı oluşturduğunuzda, belirttiğiniz artışlarla taşır. Kaydırıcı beş bir dizi olması gerektiğini belirtirseniz, örneğin, kaydırıcıyı yalnızca altı konumlar kaplar: sol tarafında bir konuma kaydırıcı denetimi ve aralığında her artış için bir konum. Genellikle, bu konumlar her bir değer çizgisi tarafından tanımlanır.  
  
 Oluşturucu kullanarak bir kaydırıcı oluşturmak ve **oluşturma** üye işlevini `CSliderCtrl`. Kaydırıcı denetimi oluşturduktan sonra üye işlevlerini kullanabilirsiniz `CSliderCtrl` birçok özelliklerini değiştirmek için. Yapabileceğiniz değişiklikleri kaydırıcıyı için minimum ve maksimum konumlarına ayarlama, değer çizgileri çizim, seçim aralığını ayarlama ve kaydırıcıyı yeniden konumlandırma içerir.  
  
 Kullanma hakkında daha fazla bilgi için `CSliderCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="clearsel"></a>  CSliderCtrl::ClearSel  
 Kaydırıcı denetimi geçerli seçim temizler.  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bRedraw`  
 Bayrağı yeniden çizin. Bu parametre ise **doğru**, kaydırıcıyı seçimi temizlendikten sonra çizilir; Aksi takdirde kaydırıcıyı değil çizilir.  
  
##  <a name="cleartics"></a>  CSliderCtrl::ClearTics  
 Geçerli değer çizgilerinin kaydırıcı denetimden kaldırır.  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bRedraw`  
 Bayrağı yeniden çizin. Bu parametre ise **doğru**, kaydırıcıyı çizgilerinin temizlendikten sonra çizilir; Aksi takdirde kaydırıcıyı değil çizilir.  
  
##  <a name="create"></a>  CSliderCtrl::Create  
 Kaydırıcı denetimi oluşturur ve ona ekler bir `CSliderCtrl` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Kaydırıcı denetim stilini belirtir. Herhangi bir bileşimini uygulamak [kaydırıcı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760147)denetlemek için Windows SDK açıklanan.  
  
 `rect`  
 Kaydırıcı denetim boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı.  
  
 `pParentWnd`  
 Kaydırıcı denetim ana penceresinde, genellikle belirtir bir `CDialog`. Değil olmalıdır **NULL**.  
  
 `nID`  
 Kaydırıcı denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CSliderCtrl` iki adımda. İlk olarak, Oluşturucusu arayın ve sonra çağırın **oluşturma**, hangi kaydırıcı denetimi oluşturur ve ona ekler `CSliderCtrl` nesnesi.  
  
 İçin ayarlanan değerlerle bağlı olarak `dwStyle`, kaydırıcı denetimi dikey veya yatay yönlendirme olabilir. Her iki tarafında çizgilerinin olabilir hem kenara veya hiçbiridir. Ardışık değerlerin aralığını belirtmek için de kullanılabilir.  
  
 Genişletilmiş pencere stilleri kaydırıcı denetimi uygulamak için arama [CreateEx](#createex) yerine **oluşturma**.  
  
##  <a name="createex"></a>  CSliderCtrl::CreateEx  
 Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CSliderCtrl` nesnesi.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwExStyle`  
 Oluşturulan denetim genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri listesi için bkz: `dwExStyle` parametresi için [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK'sındaki.  
  
 `dwStyle`  
 Kaydırıcı denetim stilini belirtir. Herhangi bir bileşimini uygulamak [kaydırıcı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760147)denetlemek için Windows SDK açıklanan.  
  
 `rect`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) boyutunu ve konumunu, istemci koordinatları oluşturulacak penceresinin açıklayan yapısı `pParentWnd`.  
  
 `pParentWnd`  
 Denetimin üst penceresi için bir işaretçi.  
  
 `nID`  
 Denetimin alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine [oluşturma](#create) Windows genişletilmiş stili önsöz tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için **WS_EX_**.  
  
##  <a name="csliderctrl"></a>  CSliderCtrl::CSliderCtrl  
 Oluşturan bir `CSliderCtrl` nesnesi.  
  
```  
CSliderCtrl();
```  
  
##  <a name="getbuddy"></a>  CSliderCtrl::GetBuddy  
 Belirtilen konumda bir kaydırıcı denetimi arkadaş penceresi tanıtıcısını alır.  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `fLocation`  
 Almak için iki arkadaş pencere işleyicileri hangisinin gösteren bir Boole değeri. Aşağıdaki değerlerden biri olabilir:  
  
- **DOĞRU** kaydırıcıyı sola arkadaş tanıtıcısını alır. Kaydırıcı denetimi kullanıyorsa, `TBS_VERT` stili, kaydırıcıyı yukarıda arkadaş iletiyi alır.  
  
- **YANLIŞ** kaydırıcıyı sağa arkadaş tanıtıcısını alır. Kaydırıcı denetimi kullanıyorsa, `TBS_VERT` tarzı ileti arkadaş kaydırıcıyı altına alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) tarafından belirtilen konumda arkadaş pencere nesnesi `fLocation`, veya **NULL** arkadaş pencere o konumda varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TBM_GETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760178), Windows SDK'ın açıklandığı gibi. Kaydırıcı denetim stilleri açıklaması için bkz: [Trackbar denetimi stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760147) Windows SDK.  
  
##  <a name="getchannelrect"></a>  CSliderCtrl::GetChannelRect  
 Kaydırıcı denetim kanalı için sınırlayıcı dikdörtgenini konumunu ve boyutunu alır.  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lprc`  
 Bir işaretçi bir [CRect](../../atl-mfc-shared/reference/crect-class.md) boyutunu ve konumunu kanalının içeren nesne çevreleyen dikdörtgenin işlevi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kanal, kaydırıcıyı hareket eder ve bir aralığı seçili değilken Vurgu içeren üzerinden alanıdır.  
  
##  <a name="getlinesize"></a>  CSliderCtrl::GetLineSize  
 Kaydırıcı denetimi için satır boyutunu alır.  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı denetimi için bir satır boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Satır boyutu için ne kadar kaydırıcıyı hareket etkiler **TB_LINEUP** ve **TB_LINEDOWN** bildirimleri. 1 satır boyutu için varsayılan ayardır.  
  
##  <a name="getnumtics"></a>  CSliderCtrl::GetNumTics  
 Kaydırıcı denetimi onay işaretleri sayısını alır.  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı denetimi onay işaretleri sayısı.  
  
##  <a name="getpagesize"></a>  CSliderCtrl::GetPageSize  
 Kaydırıcı denetimi için sayfa boyutunu alır.  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı denetimi için bir sayfa boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Sayfa boyutu için ne kadar kaydırıcıyı hareket etkiler **TB_PAGEUP** ve **TB_PAGEDOWN** bildirimleri.  
  
##  <a name="getpos"></a>  CSliderCtrl::GetPos  
 Kaydırıcı denetimi kaydırıcıyı geçerli konumunu alır.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli konumu.  
  
##  <a name="getrange"></a>  CSliderCtrl::GetRange  
 Kaydırıcı için maksimum ve minimum konumlar kaydırıcı denetimi olarak alır.  
  
```  
void GetRange(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nMin`  
 Başvuru tamsayıya minimum konumunu alır.  
  
 `nMax`  
 En fazla konum alan tamsayı başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tarafından başvurulan tamsayılar halinde değerleri kopyalar `nMin` ve `nMax`.  
  
##  <a name="getrangemax"></a>  CSliderCtrl::GetRangeMax  
 Kaydırıcı denetimi en fazla konumda kaydırıcı için alır.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin maksimum konumu.  
  
##  <a name="getrangemin"></a>  CSliderCtrl::GetRangeMin  
 Kaydırıcı denetimi kaydırıcı için minimum konumu alır.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin minimum konumu.  
  
##  <a name="getselection"></a>  CSliderCtrl::GetSelection  
 Kaydırıcı denetimi geçerli seçim başlangıç ve bitiş konumunu alır.  
  
```  
void GetSelection(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nMin`  
 Geçerli seçimin başlangıç konumu alır tamsayı başvuru.  
  
 `nMax`  
 Geçerli seçimi bitiş konumu alır tamsayı başvuru.  
  
##  <a name="getthumblength"></a>  CSliderCtrl::GetThumbLength  
 Kaydırıcı geçerli trackbar denetimi, uzunluğunu alır.  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı piksel cinsinden uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [TBM_GETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760201) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getthumbrect"></a>  CSliderCtrl::GetThumbRect  
 Kaydırıcı denetimi (Flash) kaydırıcı için sınırlayıcı dikdörtgenini konumunu ve boyutunu alır.  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lprc`  
 Bir işaretçi bir `CRect` işlevi döndüğünde kaydırıcı için sınırlayıcı dikdörtgenini içeren nesne.  
  
##  <a name="gettic"></a>  CSliderCtrl::GetTic  
 Kaydırıcı denetimi çizgisi konumunu alır.  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nTic`  
 Değer çizgisi tanımlama sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen değer çizgisi veya - 1 olursa konumunu `nTic` geçerli bir dizin belirtmiyor.  
  
##  <a name="getticarray"></a>  CSliderCtrl::GetTicArray  
 Kaydırıcı denetimi için değer çizgilerinin konumlarını içeren bir dizi adresini alır.  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı denetimi için onay işareti konumlarını içeren bir dizi adresi.  
  
##  <a name="getticpos"></a>  CSliderCtrl::GetTicPos  
 Kaydırıcı denetimi olarak çizgisi geçerli fiziksel konumunu alır.  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nTic`  
 Değer çizgisi tanımlama sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Fiziksel konumunu, istemci koordinatları, belirtilen değer çizgisi veya - 1 IF `nTic` geçerli bir dizin belirtmiyor.  
  
##  <a name="gettooltips"></a>  CSliderCtrl::GetToolTips  
 Kaydırıcı denetimi için atanan araç ipucu denetimi için tanıtıcı varsa alır.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesnesi veya **NULL** araç ipuçları kullanımda değilse. Kaydırıcı denetimi kullanmıyorsa **TBS_TOOLTIPS** stili, dönüş değeri olan **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TBM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760209), Windows SDK'ın açıklandığı gibi. Bu üye işlevinin döndürdüğü Not bir `CToolTipCtrl` bir denetim için bir tanıtıcı yerine nesne.  
  
 Kaydırıcı denetim stilleri açıklaması için bkz: [Trackbar denetimi stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760147) Windows SDK.  
  
##  <a name="setbuddy"></a>  CSliderCtrl::SetBuddy  
 Kaydırıcı denetimi arkadaş pencere olarak bir pencere atar.  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWndBuddy`  
 Bir işaretçi bir `CWnd` kaydırıcı denetimin arkadaş ayarlanacak nesnesi.  
  
 `fLocation`  
 Arkadaş penceresini görüntülemek konumu belirten değer. Bu değer aşağıdakilerden biri olabilir:  
  
- **DOĞRU** trackbar denetimi kullanıyorsa, arkadaş trackbar solunda görünür `TBS_HORZ` stili. Trackbar kullanıyorsa `TBS_VERT` stil, trackbar denetimi arkadaş görüntülenir.  
  
- **YANLIŞ** trackbar denetimi kullanıyorsa, arkadaş trackbar sağında görünür `TBS_HORZ` stili. Trackbar kullanıyorsa `TBS_VERT` stil, arkadaş trackbar denetimi altında görüntülenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) daha önce bu konumda kaydırıcı denetimi atandı nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TBM_SETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760213), Windows SDK'ın açıklandığı gibi. Bu üye işlevi işaretçileri kullandığına dikkat edin `CWnd` pencere işleyicileri için kendi dönüş değeri ve parametre yerine nesneleri.  
  
 Kaydırıcı denetim stilleri açıklaması için bkz: [Trackbar denetimi stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760147) Windows SDK.  
  
##  <a name="setlinesize"></a>  CSliderCtrl::SetLineSize  
 Kaydırıcı denetimi için satır boyutunu ayarlar.  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>Parametreler  
 `nSize`  
 Kaydırıcı denetimi yeni satır boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki satır boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Satır boyutu için ne kadar kaydırıcıyı hareket etkiler **TB_LINEUP** ve **TB_LINEDOWN** bildirimleri.  
  
##  <a name="setpagesize"></a>  CSliderCtrl::SetPageSize  
 Kaydırıcı denetimi için sayfa boyutunu ayarlar.  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>Parametreler  
 `nSize`  
 Kaydırıcı denetimi yeni sayfa boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki sayfa boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Sayfa boyutu için ne kadar kaydırıcıyı hareket etkiler **TB_PAGEUP** ve **TB_PAGEDOWN** bildirimleri.  
  
##  <a name="setpos"></a>  CSliderCtrl::SetPos  
 Kaydırıcı geçerli konumunu kaydırıcı denetimi ayarlar.  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Yeni kaydırıcı konumunu belirtir.  
  
##  <a name="setrange"></a>  CSliderCtrl::SetRange  
 Kaydırıcı denetimi uygulamasındaki kaydırıcı için aralığı (minimum ve maksimum konumlar) ayarlar.  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMin`  
 Kaydırıcı için en az konum.  
  
 `nMax`  
 Kaydırıcı için en fazla konum.  
  
 `bRedraw`  
 Yeniden düzenleme bayrağı. Bu parametre ise **doğru**, aralığı ayarladıktan sonra kaydırıcıyı çizilir; Aksi takdirde kaydırıcıyı değil çizilir.  
  
##  <a name="setrangemax"></a>  CSliderCtrl::SetRangeMax  
 Kaydırıcı denetimi uygulamasındaki kaydırıcı için en büyük aralığı ayarlar.  
  
```  
void SetRangeMax(
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMax`  
 Kaydırıcı için en fazla konum.  
  
 `bRedraw`  
 Yeniden düzenleme bayrağı. Bu parametre ise **doğru**, aralığı ayarladıktan sonra kaydırıcıyı çizilir; Aksi takdirde kaydırıcıyı değil çizilir.  
  
##  <a name="setrangemin"></a>  CSliderCtrl::SetRangeMin  
 Kaydırıcı denetimi uygulamasındaki kaydırıcı için en az aralığı ayarlar.  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMin`  
 Kaydırıcı için en az konum.  
  
 `bRedraw`  
 Yeniden düzenleme bayrağı. Bu parametre ise **doğru**, aralığı ayarladıktan sonra kaydırıcıyı çizilir; Aksi takdirde kaydırıcıyı değil çizilir.  
  
##  <a name="setselection"></a>  CSliderCtrl::SetSelection  
 Geçerli seçim için başlangıç ve bitiş konumlarını kaydırıcı denetimi ayarlar.  
  
```  
void SetSelection(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMin`  
 Kaydırıcı başlangıç konumu.  
  
 `nMax`  
 Kaydırıcı için bitiş konumu.  
  
##  <a name="setthumblength"></a>  CSliderCtrl::SetThumbLength  
 Kaydırıcı uzunluğu, geçerli trackbar denetimi ayarlar.  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `nLength`|Kaydırıcı piksel cinsinden uzunluğu.|  
  
### <a name="remarks"></a>Açıklamalar  
 Trackbar denetimi ayarlanması bu yöntem gerektirir [TBS_FIXEDLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760147) stili.  
  
 Bu yöntem gönderir [TBM_SETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760234) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_sliderCtrl`, yani geçerli trackbar denetimi erişmek için kullanılır. Örnek ayrıca, bir değişken tanımlar `thumbLength`, yani trackbar denetimin kaydırma bileşenin varsayılan uzunluğunu depolamak için kullanılır. Bu değişkenler sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, iki kez varsayılan uzunluğu trackbar denetimin kaydırma bileşen ayarlar.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="settic"></a>  CSliderCtrl::SetTic  
 Değer çizgisi konumunu kaydırıcı denetimi ayarlar.  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>Parametreler  
 `nTic`  
 Değer çizgisi konumu. Bu parametre, pozitif bir değer belirtmeniz gerekir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değer çizgisi ayarlarsanız sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="setticfreq"></a>  CSliderCtrl::SetTicFreq  
 Uygulamasındaki kaydırıcı görüntülenen ile hangi onay işaretleri sıklığı ayarlar.  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>Parametreler  
 *nFreq*  
 Değer çizgilerinin sıklığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Sıklığı 2'ye ayarlanmışsa, değer çizgisi her bir artış kaydırıcının aralıktaki için görüntülenir. 1 sıklığıdır için varsayılan ayar (diğer bir deyişle, her artış aralığında bir onay işareti ile ilişkili olan).  
  
 Denetimle oluşturmalısınız `TBS_AUTOTICKS` stili bu işlevi kullanın. Daha fazla bilgi için bkz: [CSliderCtrl::Create](#create).  
  
##  <a name="settipside"></a>  CSliderCtrl::SetTipSide  
 Konumlar bir araç ipucu denetimi trackbar denetimi tarafından kullanılır.  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>Parametreler  
 `nLocation`  
 Araç İpucu denetimi görüntülemek konumu temsil eden değer. Olası değerler listesi için bkz: Win32 ileti [TBM_SETTIPSIDE](http://msdn.microsoft.com/library/windows/desktop/bb760240), Windows SDK'ın açıklandığı gibi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç İpucu denetimin önceki konumu temsil eden bir değer. Dönüş değeri için olası değerler birini eşittir `nLocation`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan **TBM_SETTIPSIDE**, Windows SDK'ın açıklandığı gibi. Kaydırıcı denetimleri kullanan **TBS_TOOLTIPS** stili görüntü araç ipuçları. Kaydırıcı denetim stilleri açıklaması için bkz: [Trackbar denetimi stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760147) Windows SDK.  
  
##  <a name="settooltips"></a>  CSliderCtrl::SetToolTips  
 Bir araç ipucu denetimi için kaydırıcı denetimi atar.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWndTip`  
 Bir işaretçi bir [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) kaydırıcı denetimi ile kullanmak için araç ipuçları içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TBM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760242), Windows SDK'ın açıklandığı gibi. İle kaydırıcı denetimi oluşturulduğunda **TBS_TOOLTIPS** stil, kaydırıcıyı yanındaki kaydırıcının geçerli konumu görüntüleme görünür bir varsayılan araç ipucu denetimi oluşturur. Kaydırıcı denetim stilleri açıklaması için bkz: [Trackbar denetimi stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760147) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl Sınıfı](../../mfc/reference/cprogressctrl-class.md)
