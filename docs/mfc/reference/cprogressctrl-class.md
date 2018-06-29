---
title: CProgressCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38ccc4acfdfd618bf0fa11f4a49c1e0b78f009ca
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079396"
---
# <a name="cprogressctrl-class"></a>CProgressCtrl sınıfı
Windows ortak ilerleme çubuğu denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|Oluşturan bir `CProgressCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CProgressCtrl::Create](#create)|Bir ilerleme çubuğu denetimi oluşturur ve ona ekler bir `CProgressCtrl` nesnesi.|  
|[CProgressCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stiliyle bir ilerleme denetiminin oluşturur ve ekler bir `CProgressCtrl` nesnesi.|  
|[CProgressCtrl::GetBarColor](#getbarcolor)|İlerleme göstergesi çubuğu rengini geçerli ilerleme çubuğu denetimi için alır.|  
|[CProgressCtrl::GetBkColor](#getbkcolor)|Geçerli ilerleme çubuğu arka plan rengini alır.|  
|[CProgressCtrl::GetPos](#getpos)|İlerleme çubuğu geçerli konumunu alır.|  
|[CProgressCtrl::GetRange](#getrange)|Bir ilerleme çubuğu denetimi aralığı alt ve üst sınırları alır.|  
|[CProgressCtrl::GetState](#getstate)|Geçerli ilerleme çubuğu denetimi durumunu alır.|  
|[CProgressCtrl::GetStep](#getstep)|İlerleme çubuğu geçerli ilerleme çubuğu denetimi için adım artırma alır.|  
|[CProgressCtrl::OffsetPos](#offsetpos)|Belirtilen bir artış oranında bir ilerleme çubuğu denetiminin geçerli konumunu ilerler ve yeni konumu yansıtacak şekilde çubuğu yeniden çizer.|  
|[CProgressCtrl::SetBarColor](#setbarcolor)|İlerleme göstergesi çubuğu rengini geçerli ilerleme çubuğu denetiminde ayarlar.|  
|[CProgressCtrl::SetBkColor](#setbkcolor)|İlerleme çubuğu arka plan rengini belirler.|  
|[CProgressCtrl::SetMarquee](#setmarquee)|Geçerli ilerleme çubuğu denetimi için kayan modunu açmak veya kapatmak etkinleştirir.|  
|[CProgressCtrl::SetPos](#setpos)|Geçerli konumu bir ilerleme çubuğu denetimi için ayarlar ve yeni konumu yansıtacak şekilde çubuğu yeniden çizer.|  
|[CProgressCtrl::SetRange](#setrange)|Minimum ve maksimum aralıkları bir ilerleme çubuğu denetimi için ayarlar ve yeni aralıkları yansıtacak şekilde çubuğu yeniden çizer.|  
|[CProgressCtrl::SetState](#setstate)|Geçerli ilerleme çubuğu denetimi durumunu ayarlar.|  
|[CProgressCtrl::SetStep](#setstep)|Bir ilerleme çubuğu denetimi için adım artırma belirtir.|  
|[CProgressCtrl::StepIt](#stepit)|Bir ilerleme çubuğu denetimi için geçerli konumunu adım artışla ilerletir (bkz [SetStep](#setstep)) ve yeni konumu yansıtacak şekilde çubuğu yeniden çizer.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir ilerleme çubuğu denetiminin uygulama ilerleme uzun bir işlem durumunu göstermek için kullanabileceğiniz bir penceredir. Kademeli olarak, soldan sağa sistemiyle renk işlem ilerledikçe vurgulayın doğru doldurulmuş dikdörtgen oluşur.  
  
 Bir ilerleme çubuğu denetimi aralığı ve geçerli bir konum vardır. Aralık işlemi toplam süresi ve uygulama işleminin tamamlanmasına yönelik yaptı ilerleme geçerli konumu temsil eder. Pencere yordamı aralığı ve geçerli konumu vurgulama rengiyle doldurmak için ilerleme çubuğu yüzdesini belirlemek için kullanır. Aralık ve geçerli konum değerleri imzalı tamsayı olarak ifade edilir çünkü olası geçerli konum değerleri -2.147.483.648 2.147.483.647 dahil aralığıdır.  
  
 Kullanma hakkında daha fazla bilgi için `CProgressCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CProgressCtrl](../../mfc/using-cprogressctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CProgressCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="cprogressctrl"></a>  CProgressCtrl::CProgressCtrl  
 Oluşturan bir `CProgressCtrl` nesnesi.  
  
```  
CProgressCtrl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma sonrasında `CProgressCtrl` nesne, çağrı `CProgressCtrl::Create` ilerleme çubuğu denetimi oluşturmak için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]  
  
##  <a name="create"></a>  CProgressCtrl::Create  
 Bir ilerleme çubuğu denetimi oluşturur ve ona ekler bir `CProgressCtrl` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwStyle*  
 İlerleme çubuğu denetiminin stilini belirtir. Herhangi bir bileşimini penceresi stylesdescribed uygulamak [CreateWindow'u](http://msdn.microsoft.com/library/windows/desktop/ms632679) aşağıdaki ilerleme çubuğu denetimi için denetim stilleri ek olarak Windows SDK:  
  
- `PBS_VERTICAL` Dikey olarak ilerleme bilgileri, altına top gösterir. Bu bayrak olmadan, ilerleme çubuğu denetimi yatay, sol sağa doğru görüntüler.  
  
- `PBS_SMOOTH` Aşamalı, kesintisiz, ilerleme çubuğu denetimi doldurma görüntüler. Bu bayrak olmadan, denetim blokları ile doldurur.  
  
 *Rect*  
 İlerleme çubuğu denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı. Denetimi alt pencere olması gerektiğinden, belirtilen koordinatlar istemci alanını göre belirlenir *pParentWnd*.  
  
 *pParentWnd*  
 İlerleme çubuğu denetiminin ana penceresinde, genellikle belirten bir `CDialog`. Değil olmalıdır **NULL.**  
  
 *nID*  
 İlerleme çubuğu denetiminin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** varsa `CProgressCtrl` nesnesi, başarıyla oluşturulmuş aksi **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CProgressCtrl` iki adımda nesne. İlk olarak, oluşturur Oluşturucusu çağrısı `CProgressCtrl` nesnesini genişletin ve ardından arama `Create`, ilerleme çubuğu denetimi oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]  
  
##  <a name="createex"></a>  CProgressCtrl::CreateEx  
 Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CProgressCtrl` nesnesi.  
  
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
 Oluşturulan denetim genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri listesi için bkz: *dwExStyle* parametresi için [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK'sındaki.  
  
 *dwStyle*  
 İlerleme çubuğu denetiminin stilini belirtir. Pencere stilleri açıklanan herhangi bir bileşimini uygulamak [CreateWindow'u](http://msdn.microsoft.com/library/windows/desktop/ms632679) Windows SDK'sındaki.  
  
 *Rect*  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) boyutunu ve konumunu, istemci koordinatları oluşturulacak penceresinin açıklayan yapısı *pParentWnd*.  
  
 *pParentWnd*  
 Denetimin üst penceresi için bir işaretçi.  
  
 *nID*  
 Denetimin alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine [oluşturma](#create) Windows genişletilmiş stili önsöz tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için **WS_EX_**.  
  
##  <a name="getbarcolor"></a>  CProgressCtrl::GetBarColor  
 İlerleme göstergesi çubuğu rengini geçerli ilerleme çubuğu denetimi için alır.  
  
```  
COLORREF GetBarColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli ilerleme çubuğu rengi temsil olarak bir [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değeri veya `CLR_DEFAULT` İlerleme göstergesi çubuğu rengi kullanılan varsayılan rengi ise.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PBM_GETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760826) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getbkcolor"></a>  CProgressCtrl::GetBkColor  
 Geçerli ilerleme çubuğu arka plan rengini alır.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli ilerleme çubuğu arka plan rengi temsil olarak bir [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PBM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760828) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getpos"></a>  CProgressCtrl::GetPos  
 İlerleme çubuğu geçerli konumunu alır.  
  
```  
int GetPos();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlerleme çubuğu denetiminin konumunu.  
  
### <a name="remarks"></a>Açıklamalar  
 İlerleme çubuğu denetiminin konumunu ekranında fiziksel konumu değildir, ancak bunun yerine arasında üst ve alt aralığı belirtilen [SetRange](#setrange).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]  
  
##  <a name="getrange"></a>  CProgressCtrl::GetRange  
 Geçerli alt ve üst sınırları veya ilerleme çubuğu denetimi aralığını alır.  
  
```  
void GetRange(
    int& nLower,  
    int& nUpper);
```  
  
### <a name="parameters"></a>Parametreler  
 *nLower*  
 İlerleme çubuğu denetiminin alt sınırı alma tamsayı referansı.  
  
 *nUpper*  
 İlerleme çubuğu denetimi sayısı üst sınırı alma tamsayı referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, alt ve üst sınırları değerlerini başvurduğu tamsayılar kopyalar *nLower* ve *nUpper*sırasıyla.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]  
  
##  <a name="getstate"></a>  CProgressCtrl::GetState  
 Geçerli ilerleme çubuğu denetimi durumunu alır.  
  
```  
int GetState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden biri geçerli ilerleme çubuğu denetimi durumu:  
  
|Değer|Durum|  
|-----------|-----------|  
|`PBST_NORMAL`|Sürüyor|  
|`PBST_ERROR`|Hata|  
|`PBST_PAUSED`|Duraklatıldı|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PBM_GETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760834) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_progressCtrl`, yani ilerleme çubuğu denetimi programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde geçerli ilerleme çubuğu denetimi durumunu alır.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]  
  
##  <a name="getstep"></a>  CProgressCtrl::GetStep  
 İlerleme çubuğu geçerli ilerleme çubuğu denetimi için adım artırma alır.  
  
```  
int GetStep() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlerleme çubuğu adım artırma.  
  
### <a name="remarks"></a>Açıklamalar  
 Adım artış, miktardır yapılan bir çağrı [CProgressCtrl::StepIt](#stepit) ilerleme çubuğu geçerli konumunu artırır.  
  
 Bu yöntem gönderir [PBM_GETSTEP](http://msdn.microsoft.com/library/windows/desktop/bb760836) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_progressCtrl`, yani ilerleme çubuğu denetimi programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde geçerli ilerleme çubuğu denetimi adım artışı alır.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]  
  
##  <a name="offsetpos"></a>  CProgressCtrl::OffsetPos  
 İlerleme çubuğu denetiminin geçerli konumu tarafından belirtilen artış ilerler *nPos* ve yeni konumu yansıtacak şekilde çubuğu yeniden çizer.  
  
```  
int OffsetPos(int nPos);
```  
  
### <a name="parameters"></a>Parametreler  
 *nPos*  
 Konumu ilerletmek için tutar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlerleme çubuğu denetimi önceki konumu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]  
  
##  <a name="setbarcolor"></a>  CProgressCtrl::SetBarColor  
 İlerleme göstergesi çubuğu rengini geçerli ilerleme çubuğu denetiminde ayarlar.  
  
```  
COLORREF SetBarColor(COLORREF clrBar);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *clrBar*|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) İlerleme göstergesi çubuğu yeni rengi belirten değer. Belirtin `CLR_DEFAULT` varsayılan rengini kullanmak ilerleme çubuğu neden olacak.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlerleme göstergesi çubuğu önceki rengi temsil olarak bir [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değeri veya `CLR_DEFAULT` İlerleme göstergesi çubuğu rengini varsayılan rengini ise.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetBarColor` Yöntemini ayarlar ilerleme çubuğu renk eksikse bir [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] [tema](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx) etkili değildir.  
  
 Bu yöntem gönderir [PBM_SETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760838) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_progressCtrl`, yani ilerleme çubuğu denetimi programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde ilerleme çubuğu rengi kırmızı, yeşil, mavi veya varsayılan değiştirir.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]  
  
##  <a name="setbkcolor"></a>  CProgressCtrl::SetBkColor  
 İlerleme çubuğu arka plan rengini belirler.  
  
```  
COLORREF SetBkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Parametreler  
 *clrNew*  
 A **COLORREF** yeni arka plan rengini belirten değer. Belirtin `CLR_DEFAULT` varsayılan arka plan rengi ilerleme çubuğu için kullanılacak bir değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) önceki arka plan rengini belirten değer veya **CLR_DEFAULT** arka plan rengini varsayılan rengini ise.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]  
  
##  <a name="setmarquee"></a>  CProgressCtrl::SetMarquee  
 Geçerli ilerleme çubuğu denetimi için kayan modunu açmak veya kapatmak etkinleştirir.  
  
```  
BOOL SetMarquee(
    BOOL fMarqueeMode,   
    int nInterval);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *fMarqueeMode*|`true` Kayan modunu etkinleştirmek için veya `false` çerçevesi modu devre dışı bırakmak için.|  
|[in] *Naralık*|Kayan animasyon güncelleştirmeleri arasındaki milisaniye olarak süre.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem her zaman `true`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayan modu açık, ilerleme çubuğu animasyonlu ve kayarken ister bir oturum açma tiyatro çerçevesi.  
  
 Bu yöntem gönderir [PBM_SETMARQUEE](http://msdn.microsoft.com/library/windows/desktop/bb760842) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_progressCtrl`, yani ilerleme çubuğu denetimi programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği başlatır ve animasyon kaydırma çerçevesi durdurur.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]  
  
##  <a name="setpos"></a>  CProgressCtrl::SetPos  
 İlerleme çubuğu denetiminin geçerli konumu tarafından belirtilen ayarlar *nPos* ve yeni konumu yansıtacak şekilde çubuğu yeniden çizer.  
  
```  
int SetPos(int nPos);
```  
  
### <a name="parameters"></a>Parametreler  
 *nPos*  
 İlerleme çubuğu denetimi yeni konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlerleme çubuğu denetimi önceki konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 İlerleme çubuğu denetiminin konumunu ekranında fiziksel konumu değildir, ancak bunun yerine arasında üst ve alt aralığı belirtilen [SetRange](#setrange).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]  
  
##  <a name="setrange"></a>  CProgressCtrl::SetRange  
 İlerleme çubuğu denetiminin aralığının üst ve alt sınırları ayarlar ve yeni aralıkları yansıtacak şekilde çubuğu yeniden çizer.  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>Parametreler  
 *nLower*  
 Aralığının alt sınırı belirtir (varsayılan olarak sıfır).  
  
 *nUpper*  
 Aralığın üst sınırını belirtir (varsayılan değer 100).  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini `SetRange32` ilerleme denetimi için 32-bit aralığını ayarlar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]  
  
##  <a name="setstate"></a>  CProgressCtrl::SetState  
 Geçerli ilerleme çubuğu denetimi durumunu ayarlar.  
  
```  
int SetState(int iState);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *iState*|İlerleme çubuğu durumu. Aşağıdaki değerlerden birini kullanın:<br /><br /> - `PBST_NORMAL` -Devam eden<br />- `PBST_ERROR` -Hata<br />- `PBST_PAUSED` -Duraklatıldı|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli ilerleme çubuğu denetimi önceki durumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PBM_SETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760850) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_progressCtrl`, yani ilerleme çubuğu denetimi programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde, duraklatıldı veya devam eden geçerli ilerleme çubuğu denetimi durumunu ayarlar.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]  
  
##  <a name="setstep"></a>  CProgressCtrl::SetStep  
 Bir ilerleme çubuğu denetimi için adım artırma belirtir.  
  
```  
int SetStep(int nStep);
```  
  
### <a name="parameters"></a>Parametreler  
 *nStep*  
 Yeni adım artırma.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki adım artırma.  
  
### <a name="remarks"></a>Açıklamalar  
 Adım artış, miktardır yapılan bir çağrı `CProgressCtrl::StepIt` ilerleme artırır çubuğu geçerli konumu kullanıcının.  
  
 Varsayılan adım artışı 10'dur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]  
  
##  <a name="stepit"></a>  CProgressCtrl::StepIt  
 Bir ilerleme çubuğu denetimi için geçerli konumu adım artışla ilerler ve yeni konumu yansıtacak şekilde çubuğu yeniden çizer.  
  
```  
int StepIt();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlerleme çubuğu denetimi önceki konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Adım artışı belirlediği `CProgressCtrl::SetStep` üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)


