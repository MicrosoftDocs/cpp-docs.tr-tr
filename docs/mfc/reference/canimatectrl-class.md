---
title: CAnimateCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b8f9f99b38d2878025546379a185aef53bb663
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213775"
---
# <a name="canimatectrl-class"></a>CAnimateCtrl sınıfı
Windows ortak animasyon denetimi işlevlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimateCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|Oluşturur bir `CAnimateCtrl` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimateCtrl::Close](#close)|AVI klibi kapatır.|  
|[CAnimateCtrl::Create](#create)|Animasyon denetimi oluşturur ve ona bağlanan bir `CAnimateCtrl` nesne.|  
|[CAnimateCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stiller animasyon denetimi oluşturur ve ona bağlanan bir `CAnimateCtrl` nesne.|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Bir Ses Video aralıklı (AVI) klibi duraklatmasının olup olmadığını gösterir.|  
|[CAnimateCtrl::Open](#open)|Bir dosya ya da kaynağa AVI klibi açılır ve ilk çerçeve görüntüler.|  
|[CAnimateCtrl::Play](#play)|Ses olmadan AVI klibi yürütür.|  
|[CAnimateCtrl::Seek](#seek)|AVI klibi, seçili tek bir çerçeve görüntüler.|  
|[CAnimateCtrl::Stop](#stop)|AVI klibi yürütmeyi durdurur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu denetimi (ve bu nedenle `CAnimateCtrl` sınıfı) ve üzeri yalnızca Windows 95, Windows 98 ve Windows NT sürüm 3.51 altında çalışan programlar için kullanılabilir.  
  
 Animasyon denetimi AVI (Ses Video aralıklı) biçiminde bir küçük resim görüntüleyen bir dikdörtgen penceredir — standart Windows görüntü/ses biçimi. AVI klibi, bit eşlem çerçeveler, film gibi dizisidir.  
  
 Animasyon denetimlerinin basit AVI klipleri oynatabilirsiniz. Özellikle, animasyon denetimi tarafından yürütülecek klipleri aşağıdaki gereksinimleri karşılaması gerekir:  
  
-   Tam olarak bir video akışı olmalıdır ve en az bir çerçeve olmalıdır.  
  
-   Olabilir en fazla iki dosyada (ses bilgi animasyon denetimi göz ardı eder ancak genellikle diğer, varsa, bir ses akışı akıştır).  
  
-   Küçük sıkıştırılmamış veya RLE8 sıkıştırmasıyla sıkıştırılır.  
  
-   Palet değişiklik içinde video akışına izin verilir.  
  
 AVI kaynak olarak uygulamanıza AVI klibi ekleyebilir veya uygulamanızı ayrı AVI dosyası olarak eşlik.  
  
 AVI klibi görüntülenirken çalıştırma, iş parçacığı devam ettiğinden bir ortak animasyon denetimi için uzun bir işlem sırasında sistem etkinliğini belirtmek için kullanılır. Örneğin, dosya Gezgini'nde, Bul iletişim kutusunda, bir dosya sistemi arar olarak hareketli Büyüteç görüntüler.  
  
 Oluşturursanız, bir `CAnimateCtrl` nesne içinde bir iletişim kutusu ya da kullanıcı iletişim kutusu kapandığında iletişim kaynağı iletişim kutusu düzenleyicisini kullanma, bunu otomatik olarak yok edileceği.  
  
 Oluşturursanız, bir `CAnimateCtrl` nesnesi bir pencere içinde yok etmek gerekebilir. Oluşturursanız `CAnimateCtrl` yığında nesne otomatik olarak bozulur. Oluşturursanız `CAnimateCtrl` kullanarak yığında nesne **yeni** işlevini çağırmalıdır **Sil** , yok etmek için nesne üzerinde. Yeni bir sınıf türetirseniz `CAnimateCtrl` ve o sınıftaki herhangi bir bellek ayırma, geçersiz kılma `CAnimateCtrl` ayrılmasını atmayı yıkıcı.  
  
 Kullanma hakkında daha fazla bilgi için `CAnimateCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [CAnimateCtrl kullanma](../../mfc/using-canimatectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="canimatectrl"></a>  CAnimateCtrl::CAnimateCtrl  
 Oluşturur bir `CAnimateCtrl` nesne.  
  
```  
CAnimateCtrl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız [Oluştur](#create) oluşturduğunuz nesne üzerinde diğer herhangi bir işlem gerçekleştirmeden önce üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="close"></a>  CAnimateCtrl::Close  
 Animasyon denetimi (varsa) daha önce açıldı AVI klibi kapatır ve bellekten kaldırır.  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi halde sıfır.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="create"></a>  CAnimateCtrl::Create  
 Animasyon denetimi oluşturur ve ona bağlanan bir `CAnimateCtrl` nesne.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwStyle*  
 Animasyon denetiminin stilini belirtir. Herhangi bir birleşimini stilleri aşağıdaki Açıklamalar bölümüne ve animasyon denetim stilleri açıklanan açıklanan windows uygulama [animasyon denetim stilleri](/windows/desktop/Controls/animation-control-styles) Windows SDK.  
  
 *Rect*  
 Animasyonu denetimin konumunu ve boyutunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](../../mfc/reference/rect-structure1.md) yapısı.  
  
 *pParentWnd*  
 Animasyon denetiminin üst penceresine, genellikle belirtir bir `CDialog`. NULL olmamalıdır.  
  
 *nID*  
 Animasyonu denetimin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi halde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CAnimateCtrl` iki adımda. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, animasyon denetimi oluşturur ve ona ekler `CAnimateCtrl` nesne.  
  
 Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) animasyon denetimi için.  
  
- WS_CHILD her zaman  
  
- Ws_vısıble genellikle  
  
- Ws_dısabled nadiren  
  
 Genişletilmiş windows stilleri, animasyon denetimi ile kullanmak istiyorsanız, çağrı [CreateEx](#createex) yerine `Create`.  
  
 Pencere stilleri ek olarak, yukarıda listelenen animasyon denetimi için bir veya daha fazla animasyon denetim stilleri uygulamak isteyebilirsiniz. Daha fazla bilgi için Windows SDK'sı bakın [animasyon denetim stilleri](/windows/desktop/Controls/animation-control-styles).  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="createex"></a>  CAnimateCtrl::CreateEx  
 Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CAnimateCtrl` nesne.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwExStyle*  
 Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](https://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK.  
  
 *dwStyle*  
 Animasyon denetiminin stilini belirtir. Pencerenin herhangi bir bileşimini uygulayın ve animasyon denetim stilleri açıklanan [animasyon denetim stilleri](/windows/desktop/Controls/animation-control-styles) Windows SDK.  
  
 *Rect*  
 Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.  
  
 *pParentWnd*  
 Denetimin ana penceresine bir işaretçi.  
  
 *nID*  
 Denetimin alt penceresi kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine [Oluştur](#create) Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.  
  
##  <a name="isplaying"></a>  CAnimateCtrl::IsPlaying  
 Bir Ses Video aralıklı (AVI) klibi duraklatmasının olup olmadığını gösterir.  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 AVI klibi duraklatmasının TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [ACM_ISPLAYING](/windows/desktop/Controls/acm-isplaying) Windows SDK'da açıklanan ileti.  
  
##  <a name="open"></a>  CAnimateCtrl::Open  
 AVI klibi açın ve ilk çerçevesini görüntülemek için bu işlevi çağırın.  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszFileName*  
 A `CString` nesne veya AVI dosyasının adını veya AVI kaynağın adını içeren bir null ile sonlandırılmış dizeye bir işaretçi. Bu parametre NULL ise, sistem animasyon denetimi için daha önce açıldı AVI klibi varsa kapatır.  
  
 *nID*  
 AVI kaynak tanımlayıcısı. Bu parametre NULL ise, sistem animasyon denetimi için daha önce açıldı AVI klibi varsa kapatır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi halde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon denetimi oluşturulan modülünden AVI kaynak yüklenir.  
  
 `Open` Ses bir AVI klibi desteklemiyor; Sessiz AVI klipleri açabilirsiniz.  
  
 Animasyon denetimi varsa `ACS_AUTOPLAY` tarzı animasyon denetimi otomatik olarak başlayacak açılmasından hemen sonra klibi yürütmeye. Yürütme, iş parçacığı devam ederken, arka planda klibi yürütmeye devam eder. Küçük bittiğinde Yürütülüyor, otomatik olarak yinelenir.  
  
 Animasyon denetimi varsa `ACS_CENTER` stili AVI klibi denetiminde ortalanmış olacağını ve denetimin boyutunu değişmez. Animasyon denetimi yoksa `ACS_CENTER` stili AVI klibi AVI klibi görüntüleri boyutuna açıldığında denetimi yeniden boyutlandırılır. Denetimin sol üst köşedeki konumunu değiştirmez, yalnızca denetimin boyutu.  
  
 Animasyon denetimi varsa `ACS_TRANSPARENT` stilini ilk kare saydam bir arka plan kullanarak çizilip yerine arka plan rengi belirtilen animasyon küçük.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="play"></a>  CAnimateCtrl::Play  
 Animasyon denetimi içinde bir AVI klibi için bu işlevi çağırın.  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>Parametreler  
 *nFrom*  
 Çerçevenin yürütmeyi başladığı sıfır tabanlı dizini. Değer 65.536'den az olmalıdır. AVI klibi ilk kare anlamına gelir şununla 0 değeri.  
  
 *Yönetiliyor*  
 Çerçevenin sıfır tabanlı dizin uçları'burada yürütülüyor. Değer 65.536'den az olmalıdır. Değeri - 1 ile son kare AVI klibi son anlamına gelir.  
  
 *nRep*  
 AVI klibi oynatmanızı deneme sayısı. Bir değeri - 1 dosya süresiz olarak yeniden oynatma anlamına gelir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi halde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Yürütme, iş parçacığı devam ederken animasyon denetimi arka planda klibi yürütür. Animasyon denetimi varsa `ACS_TRANSPARENT` stili AVI klibi yürütülen animasyon küçük resmi belirtilen arka plan rengi yerine saydam bir arka plan.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="seek"></a>  CAnimateCtrl::Seek  
 Statik olarak AVI klibi, tek bir karesini görüntülemek için bu işlevi çağırın.  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>Parametreler  
 *Yönetiliyor*  
 Görüntülenecek çerçeve sıfır tabanlı dizini. Değer 65.536'den az olmalıdır. 0 değeri ilk kare AVI klibi sms_ınbox_manager. -1 değeri son kare AVI klibi sms_ınbox_manager.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi halde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon denetimi varsa `ACS_TRANSPARENT` stili AVI klibi saydam bir arka plan kullanarak çizilip yerine arka plan rengi belirtilen animasyon küçük.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="stop"></a>  CAnimateCtrl::Stop  
 Animasyon denetimi içinde bir AVI klibi yürütmeye durdurmak için bu işlevi çağırın.  
  
```  
BOOL Stop();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi halde sıfır.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](#create)   
 [ON_CONTROL](message-map-macros-mfc.md#on_control)

