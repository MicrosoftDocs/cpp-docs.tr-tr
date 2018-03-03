---
title: "CAnimateCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimateCtrl
- AFXCMN/CAnimateCtrl
- AFXCMN/CAnimateCtrl::CAnimateCtrl
- AFXCMN/CAnimateCtrl::Close
- AFXCMN/CAnimateCtrl::Create
- AFXCMN/CAnimateCtrl::CreateEx
- AFXCMN/CAnimateCtrl::IsPlaying
- AFXCMN/CAnimateCtrl::Open
- AFXCMN/CAnimateCtrl::Play
- AFXCMN/CAnimateCtrl::Seek
- AFXCMN/CAnimateCtrl::Stop
dev_langs:
- C++
helpviewer_keywords:
- CAnimateCtrl [MFC], CAnimateCtrl
- CAnimateCtrl [MFC], Close
- CAnimateCtrl [MFC], Create
- CAnimateCtrl [MFC], CreateEx
- CAnimateCtrl [MFC], IsPlaying
- CAnimateCtrl [MFC], Open
- CAnimateCtrl [MFC], Play
- CAnimateCtrl [MFC], Seek
- CAnimateCtrl [MFC], Stop
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58918a45daa1a6f64c160d79f52503e3a3c61cff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="canimatectrl-class"></a>CAnimateCtrl sınıfı
Windows ortak animasyon denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimateCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|Oluşturan bir `CAnimateCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimateCtrl::Close](#close)|AVI küçük kapatır.|  
|[CAnimateCtrl::Create](#create)|Animasyon denetimi oluşturur ve ona ekler bir `CAnimateCtrl` nesnesi.|  
|[CAnimateCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri animasyon denetimi oluşturur ve ekler bir `CAnimateCtrl` nesnesi.|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Ses Video araya eklemeli (AVI) küçük çalma olup olmadığını gösterir.|  
|[CAnimateCtrl::Open](#open)|Bir AVI küçük bir dosya veya kaynak açar ve ilk çerçeve görüntüler.|  
|[CAnimateCtrl::Play](#play)|Ses olmadan AVI küçük yürütür.|  
|[CAnimateCtrl::Seek](#seek)|Seçili tek bir çerçeve AVI küçük görüntüler.|  
|[CAnimateCtrl::Stop](#stop)|AVI küçük yürütmeyi durdurur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu denetim (ve bu nedenle `CAnimateCtrl` sınıfı) yalnızca Windows 95, Windows 98 ve Windows NT sürüm 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Animasyon denetimi küçük AVI (Ses Video araya eklemeli) biçiminde görüntüler dikdörtgen bir penceredir — standart Windows video/ses biçimi. Bir AVI klip, film gibi bit eşlem çerçeveler dizisidir.  
  
 Animasyon denetimleri yalnızca basit AVI klipleri yürütebilirsiniz. Özellikle, animasyon denetimi tarafından çalınacak klipleri aşağıdaki gereksinimleri karşılaması gerekir:  
  
-   Tam olarak bir video akışına olmalıdır ve en az bir çerçeve olması gerekir.  
  
-   Olabilir en fazla iki akışları dosyasında (ses bilgi animasyon denetimi yoksayar genellikle diğer akış varsa, bir ses akışını olsa).  
  
-   Küçük sıkıştırılmamış veya RLE8 sıkıştırması ile sıkıştırılmış.  
  
-   Palet değişiklik içinde video akışına izin verilir.  
  
 Uygulamanızın ayrı AVI dosyası olarak eşlik eden veya AVI kaynak olarak uygulamanıza AVI küçük ekleyebilirsiniz.  
  
 İş parçacığı AVI küçük görüntülenirken yürütmeye devam eder çünkü bir ortak animasyon denetimi için uzun bir işlem sırasında sistem etkinliğini belirtmek için kullanılır. Örneğin, dosya Gezgini Bul iletişim kutusunun bir dosya sistemi arar taşıma Büyüteç görüntüler.  
  
 Oluşturursanız, bir `CAnimateCtrl` nesne içinde bir iletişim kutusunda ya da kullanıcı iletişim kutusu kapandığında iletişim kaynağı iletişim kutusu Düzenleyicisi'ni kullanarak, onu otomatik olarak yok edilir.  
  
 Oluşturursanız, bir `CAnimateCtrl` nesne bir pencerede, destroy gerekebilir. Oluşturursanız, `CAnimateCtrl` nesne yığında otomatik olarak yok. Oluşturursanız, `CAnimateCtrl` nesnesi kullanarak yığında **yeni** işlevini çağırmanız gerekir **silmek** onu yok etmek için nesne üzerinde. Yeni bir sınıf türetirseniz `CAnimateCtrl` ve bu sınıftaki tüm bellek ayıramadı, geçersiz kılma `CAnimateCtrl` yıkıcı ayrılmasını silmek için.  
  
 Kullanma hakkında daha fazla bilgi için `CAnimateCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CAnimateCtrl](../../mfc/using-canimatectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="canimatectrl"></a>CAnimateCtrl::CAnimateCtrl  
 Oluşturan bir `CAnimateCtrl` nesnesi.  
  
```  
CAnimateCtrl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız [oluşturma](#create) oluşturduğunuz nesne üzerinde herhangi bir işlem gerçekleştirmeden önce üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="close"></a>CAnimateCtrl::Close  
 Animasyon denetimi (varsa) içinde daha önce açıldı AVI küçük kapatır ve belleğinden kaldırır.  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="create"></a>CAnimateCtrl::Create  
 Animasyon denetimi oluşturur ve ona ekler bir `CAnimateCtrl` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Animasyon denetimin stilini belirtir. Aşağıdaki Açıklamalar bölümüne ve animasyon denetim stilleri açıklanan stilleri açıklanan windows herhangi bir bileşimini uygulamak [animasyon denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb761886) Windows SDK.  
  
 `rect`  
 Animasyon denetimin konumunu ve boyutunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](../../mfc/reference/rect-structure1.md) yapısı.  
  
 `pParentWnd`  
 Animasyon denetimin ana penceresinde, genellikle belirten bir `CDialog`. Değil olmalıdır **NULL.**  
  
 `nID`  
 Animasyon denetimin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CAnimateCtrl` iki adımda. İlk olarak, Oluşturucusu arayın ve sonra çağırın **oluşturma**, animasyon denetimi oluşturur ve ekler `CAnimateCtrl` nesnesi.  
  
 Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) animasyon denetimi için.  
  
- **WS_CHILD** her zaman  
  
- **Ws_vısıble** genellikle  
  
- **Ws_dısabled** nadiren  
  
 Animasyon denetimi ile genişletilmiş windows stilleri kullanmak istiyorsanız, çağrı [CreateEx](#createex) yerine **oluşturma**.  
  
 Yukarıda listelenen pencere stilleri ek olarak, bir veya daha fazla animasyon denetim stilleri bir animasyon denetimine uygulamak isteyebilirsiniz. Daha fazla bilgi için Windows SDK'sı bakın [animasyon denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb761886).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="createex"></a>CAnimateCtrl::CreateEx  
 Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CAnimateCtrl` nesnesi.  
  
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
 Animasyon denetimin stilini belirtir. Pencerenin herhangi bir bileşimini uygulamak ve animasyon denetim stilleri açıklanan [animasyon denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb761886) Windows SDK.  
  
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
  
##  <a name="isplaying"></a>CAnimateCtrl::IsPlaying  
 Ses Video araya eklemeli (AVI) küçük çalma olup olmadığını gösterir.  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`bir AVI küçük yürütülüyor Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [ACM_ISPLAYING](http://msdn.microsoft.com/library/windows/desktop/bb761895) Windows SDK'ın açıklanan ileti.  
  
##  <a name="open"></a>CAnimateCtrl::Open  
 Bir AVI küçük açmak ve ilk çerçevesini görüntülemek için bu işlevini çağırın.  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFileName`  
 A `CString` nesne veya AVI dosyasının adı ya da bir AVI kaynağın adını içeren null ile sonlandırılmış bir dize için bir işaretçi. Bu parametre ise **NULL**, sistem animasyon denetimi için daha önce açıldı AVI küçük varsa kapatır.  
  
 `nID`  
 AVI kaynak tanımlayıcısı. Bu parametre ise **NULL**, sistem animasyon denetimi için daha önce açıldı AVI küçük varsa kapatır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon denetimi oluşturulan modülünden AVI kaynak yüklenir.  
  
 **Açık** ses AVI klibi içinde; desteklemiyor sessiz AVI klipleri açabilirsiniz.  
  
 Animasyon denetimi varsa `ACS_AUTOPLAY` stili, animasyon denetimi otomatik olarak başlatılacak hemen, açıldıktan sonra küçük yürütülüyor. Yürütme, iş parçacığı devam ederken arka planda küçük çalınmaya devam eder. Küçük tamamlanınca çalma, onu otomatik olarak yinelenir.  
  
 Animasyon denetimi varsa `ACS_CENTER` stili AVI küçük denetiminde ortalanmış olacağını ve denetim boyutunu değişmez. Animasyon denetimi yoksa `ACS_CENTER` stili AVI küçük AVI küçük resim görüntüleri boyutunu açıldığında denetimi boyutlandırılır. Denetimin sol üst köşesinde konumunu değiştirmez, yalnızca denetiminin boyutu.  
  
 Animasyon denetimi varsa `ACS_TRANSPARENT` stili ilk çerçevesi saydam arka plan kullanarak çizilip yerine arka plan rengini belirtilen animasyon küçük.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="play"></a>CAnimateCtrl::Play  
 Animasyon denetimi içinde bir AVI küçük yürütmek için bu işlevini çağırın.  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>Parametreler  
 `nFrom`  
 Çerçevenin oynamaya başladığı sıfır tabanlı dizini. Değer 65.536'den küçük olmalıdır. 0 değeri, anlamına gelir ilk çerçeveyi AVI küçük başlayın.  
  
 `nTo`  
 Çerçeve sıfır tabanlı dizini uçları'burada yürütülüyor. Değer 65.536'den küçük olmalıdır. Bir değeri - 1 ile son çerçeve AVI küçük resmi bitiş anlamına gelir.  
  
 *nRep*  
 AVI küçük yeniden yürütme sayısı. Bir değeri - 1 dosya süresiz olarak yeniden oynatma anlamına gelir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Yürütme, iş parçacığı devam ederken animasyon denetimi küçük arka planda yürütün. Animasyon denetimi varsa `ACS_TRANSPARENT` stili AVI küçük yürütülen animasyon küçük resmi belirtilen arka plan rengi yerine saydam arka plan.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="seek"></a>CAnimateCtrl::Seek  
 Statik olarak tek bir çerçeve AVI küçük görüntülemek için bu işlevini çağırın.  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>Parametreler  
 `nTo`  
 Görüntülenecek çerçeve sıfır tabanlı dizini. Değer 65.536'den küçük olmalıdır. 0 değeri sms_ınbox_manager ilk çerçevesi AVI küçük resmi. -1 değeri sms_ınbox_manager son çerçeve AVI küçük resmi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon denetimi varsa `ACS_TRANSPARENT` stili AVI küçük saydam arka plan kullanarak çizilip yerine arka plan rengini belirtilen animasyon küçük.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="stop"></a>CAnimateCtrl::Stop  
 Animasyon denetimi içinde bir AVI klibi yürütmeyi durdurmak için bu işlevini çağırın.  
  
```  
BOOL Stop();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](#create)   
 [ON_CONTROL](message-map-macros-mfc.md#on_control)

