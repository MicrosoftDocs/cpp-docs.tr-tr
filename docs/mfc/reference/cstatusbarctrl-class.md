---
title: CStatusBarCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStatusBarCtrl
- AFXCMN/CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::Create
- AFXCMN/CStatusBarCtrl::CreateEx
- AFXCMN/CStatusBarCtrl::DrawItem
- AFXCMN/CStatusBarCtrl::GetBorders
- AFXCMN/CStatusBarCtrl::GetIcon
- AFXCMN/CStatusBarCtrl::GetParts
- AFXCMN/CStatusBarCtrl::GetRect
- AFXCMN/CStatusBarCtrl::GetText
- AFXCMN/CStatusBarCtrl::GetTextLength
- AFXCMN/CStatusBarCtrl::GetTipText
- AFXCMN/CStatusBarCtrl::IsSimple
- AFXCMN/CStatusBarCtrl::SetBkColor
- AFXCMN/CStatusBarCtrl::SetIcon
- AFXCMN/CStatusBarCtrl::SetMinHeight
- AFXCMN/CStatusBarCtrl::SetParts
- AFXCMN/CStatusBarCtrl::SetSimple
- AFXCMN/CStatusBarCtrl::SetText
- AFXCMN/CStatusBarCtrl::SetTipText
dev_langs:
- C++
helpviewer_keywords:
- CStatusBarCtrl [MFC], CStatusBarCtrl
- CStatusBarCtrl [MFC], Create
- CStatusBarCtrl [MFC], CreateEx
- CStatusBarCtrl [MFC], DrawItem
- CStatusBarCtrl [MFC], GetBorders
- CStatusBarCtrl [MFC], GetIcon
- CStatusBarCtrl [MFC], GetParts
- CStatusBarCtrl [MFC], GetRect
- CStatusBarCtrl [MFC], GetText
- CStatusBarCtrl [MFC], GetTextLength
- CStatusBarCtrl [MFC], GetTipText
- CStatusBarCtrl [MFC], IsSimple
- CStatusBarCtrl [MFC], SetBkColor
- CStatusBarCtrl [MFC], SetIcon
- CStatusBarCtrl [MFC], SetMinHeight
- CStatusBarCtrl [MFC], SetParts
- CStatusBarCtrl [MFC], SetSimple
- CStatusBarCtrl [MFC], SetText
- CStatusBarCtrl [MFC], SetTipText
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b89f51fbcb3ca46afdb5ad56a6e162e7fe42cf0d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122901"
---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl sınıfı
Windows ortak durum çubuğu denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|Oluşturan bir `CStatusBarCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStatusBarCtrl::Create](#create)|Durum çubuğu denetimi oluşturur ve ona ekler bir `CStatusBarCtrl` nesnesi.|  
|[CStatusBarCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile durum çubuğu denetimi oluşturur ve ekler bir `CStatusBarCtrl` nesnesi.|  
|[CStatusBarCtrl::DrawItem](#drawitem)|Bir sahip çizim durum çubuğu denetim değişikliklerini visual yönünü çağrılır.|  
|[CStatusBarCtrl::GetBorders](#getborders)|Geçerli bir durum çubuğu denetiminin yatay ve dikey kenarlık genişliğini alır.|  
|[CStatusBarCtrl::GetIcon](#geticon)|Bir bölümü (bölme olarak da bilinir) simgesi, geçerli durum çubuğu denetimi alır.|  
|[CStatusBarCtrl::GetParts](#getparts)|Durum çubuğu denetimi bölümlerinde sayısını alır.|  
|[CStatusBarCtrl::GetRect](#getrect)|Durum çubuğu denetimi bölümünde sınırlayıcı dikdörtgenini alır.|  
|[CStatusBarCtrl::GetText](#gettext)|Durum çubuğu denetimi verilen bölümünden metni alır.|  
|[CStatusBarCtrl::GetTextLength](#gettextlength)|Durum çubuğu denetiminin verilen bölümünden metnin karakter cinsinden uzunluğu alır.|  
|[CStatusBarCtrl::GetTipText](#gettiptext)|Durum çubuğu bölmesinde ipucu metnini alır.|  
|[CStatusBarCtrl::IsSimple](#issimple)|Basit modunda olup olmadığını belirlemek için bir durum pencere denetim denetler.|  
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|Arka plan rengini durum çubuğunda ayarlar.|  
|[CStatusBarCtrl::SetIcon](#seticon)|Bir bölme simgesi durum çubuğunda ayarlar.|  
|[CStatusBarCtrl::SetMinHeight](#setminheight)|En küçük yüksekliğini bir durum denetiminin çizim alanını ayarlar.|  
|[CStatusBarCtrl::SetParts](#setparts)|Durum çubuğu denetim ve her bölümü sağ köşesine koordinatını bölümlerinin sayısını ayarlar.|  
|[CStatusBarCtrl::SetSimple](#setsimple)|Durum çubuğu denetimi basit metin görüntüler veya önceki bir çağrı tarafından ayarlanan tüm denetim bölümleri görüntüler belirtir `SetParts`.|  
|[CStatusBarCtrl::SetText](#settext)|Metin durum çubuğu denetimi verilen parçası ayarlar.|  
|[CStatusBarCtrl::SetTipText](#settiptext)|Araç İpucu metni bölmesi için durum çubuğunda ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Durum çubuğu denetimi" genellikle uygulamanın çeşitli durum bilgileri görüntüleyebilir, bir üst penceresinin en altında görüntülenen yatay bir penceredir. Durum çubuğu denetimi birden fazla tür bilgilerini görüntüleme parçalara ayrılabilir.  
  
 Bu denetim (ve bu nedenle `CStatusBarCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Kullanma hakkında daha fazla bilgi için `CStatusBarCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatusBarCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="create"></a>  CStatusBarCtrl::Create  
 Durum çubuğu denetimi oluşturur ve ona ekler bir `CStatusBarCtrl` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwStyle*  
 Durum çubuğu denetiminin stilini belirtir. Durum çubuğu denetim stilleri listelenen herhangi bir bileşimini uygulamak [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498) Windows SDK. Bu parametre WS_CHILD stilini içermesi gerekir. Ayrıca ws_vısıble stili içermesi gerekir.  
  
 *Rect*  
 Durum çubuğu denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı.  
  
 *pParentWnd*  
 Durum çubuğu denetiminin ana penceresinde, genellikle belirten bir `CDialog`. NULL olmamalıdır.  
  
 *nID*  
 Durum çubuğu denetiminin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CStatusBarCtrl` iki adımda. İlk olarak, Oluşturucusu arayın ve sonra çağırın `Create`, durum çubuğu denetimi oluşturur ve ekler `CStatusBarCtrl` nesnesi.  
  
 Bir durum pencere varsayılan konumunu, pencerenin üst olmakla birlikte üst pencerenin istemci alanının üstünde görünür için CCS_TOP stili belirtebilirsiniz. Durum penceresinin sağ uçta boyutlandırma tutamacı içerecek şekilde SBARS_SIZEGRIP stili belirtebilirsiniz. Sonuçta elde edilen boyutlandırma tutamacı işlev olmadığından isteğe bağlı olarak sistem durumu penceresinde çizer olsa bile CCS_TOP ve SBARS_SIZEGRIP stillerini birleştirme, önerilmez.  
  
 Genişletilmiş pencere stilleri ile durum çubuğu oluşturmak için arama [CStatusBarCtrl::CreateEx](#createex) yerine `Create`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CStatusBarCtrl::CreateEx  
 Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CStatusBarCtrl` nesnesi.  
  
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
 Durum çubuğu denetiminin stilini belirtir. Durum çubuğu denetim stilleri listelenen herhangi bir bileşimini uygulamak [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498) Windows SDK. Bu parametre WS_CHILD stilini içermesi gerekir. Ayrıca ws_vısıble stili içermesi gerekir.  
  
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
  
##  <a name="cstatusbarctrl"></a>  CStatusBarCtrl::CStatusBarCtrl  
 Oluşturan bir `CStatusBarCtrl` nesnesi.  
  
```  
CStatusBarCtrl();
```  
  
##  <a name="drawitem"></a>  CStatusBarCtrl::DrawItem  
 Bir sahip çizim durum çubuğu denetim değişikliklerini visual yönünü zaman çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpDrawItemStruct*  
 Uzun bir işaretçi bir [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) gerekli çizim türü hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `itemAction` Üyesi `DRAWITEMSTRUCT` yapısı gerçekleştirilecek çizim eylemi tanımlar.  
  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Çizim sahibi çizim için uygulamak için bu üye işlevi geçersiz kılma `CStatusBarCtrl` nesnesi.  
  
 Tüm grafik cihaz arabirimi (GDI) nesneleri görüntüleme bağlamı içinde sağlanan için seçilen uygulama kurtarmalısınız *lpDrawItemStruct* önce bu üye fonksiyonu sonlandırır.  
  
##  <a name="getborders"></a>  CStatusBarCtrl::GetBorders  
 Durum çubuğu denetiminin geçerli genişlikleri yatay ve dikey Kenarlıklar ve dikdörtgenler arasında yer alır.  
  
```  
BOOL GetBorders(int* pBorders) const;  
  
BOOL GetBorders(
    int& nHorz,  
    int& nVert,  
    int& nSpacing) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pBorders*  
 Üç öğeye sahip bir tamsayı dizisi adresidir. İlk öğe yatay kenarlık genişliğini alır, ikinci Dikey kenarlık genişliğini alır ve üçüncü dikdörtgenler arasındaki kenarlığın genişliğini alır.  
  
 *nHorz*  
 Yatay kenarlık genişliğini alır tamsayı başvuru.  
  
 *r*  
 Dikey kenarlık genişliğini alır tamsayı başvuru.  
  
 *nSpacing*  
 Dikdörtgenler arasındaki kenarlığın genişliğini alır tamsayı başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu Kenarlıklar denetiminin dış kenarına ve metin içeren dikdörtgenler denetim içindeki arasındaki boşluğu belirler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]  
  
##  <a name="geticon"></a>  CStatusBarCtrl::GetIcon  
 Bir bölümü (bölme olarak da bilinir) simgesi, geçerli durum çubuğu denetimi alır.  
  
```  
HICON GetIcon(int iPart) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *iPart*|Alınacak simgesini içeren bölümü sıfır tabanlı dizini. Bu parametre -1 ise, durum çubuğu basit mod durum çubuğu olduğu varsayılır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Simge tanıtıcısını varsa başarılı; yöntemi Aksi takdirde NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [SB_GETICON](http://msdn.microsoft.com/library/windows/desktop/bb760744) Windows SDK'ın açıklanan ileti.  
  
 Durum çubuğu denetimi olarak da bilinen bazı bölümleri metin çıktısı bölmeleri satırının oluşur. Durum çubuğu hakkında daha fazla bilgi için bkz: [MFC'de durum çubuğu uygulaması](../../mfc/status-bar-implementation-in-mfc.md) ve [CStatusBarCtrl nesnesinin modunu ayarlama](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir değişken tanımlar `m_statusBar`, yani geçerli durum çubuğu denetimi erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, geçerli durum çubuğu denetimi iki bölme için bir simge kopyalar. Önceki kod örneğinde bölümünde biz durum çubuğu denetimi ile üç bölmeleri oluşturulur ve ardından bir simge ilk bölmesine eklenir. Bu örnek ilk bölmesinden simgeyi alır ve ikinci ve üçüncü bölmesine ekler.  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]  
  
##  <a name="getparts"></a>  CStatusBarCtrl::GetParts  
 Durum çubuğu denetimi bölümlerinde sayısını alır.  
  
```  
int GetParts(
    int nParts,  
    int* pParts) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nParts*  
 Bölümleri koordinatları alınacağı için sayısı. Bu parametre denetimi bölümlerinde sayısından büyükse, yalnızca var olan bölümleri için koordinatları iletiyi alır.  
  
 *pParts*  
 Tarafından belirtilen parçaların sayısı olarak aynı sayıda öğe olması tamsayı dizisi adresini *nParts*. Dizideki her öğe karşılık gelen bölümü sağ köşesine istemci koordinatını alır. Bir öğe-ayarlanmışsa, 1, durum çubuğunun sağ kenarı sağ kenarı bu bölümü için konumunu genişletir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimi başarılı olursa ya da sıfır değilse bölümlerinde sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi de bölümleri belirtilen sayıda sağ köşesine koordinatını alır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]  
  
##  <a name="getrect"></a>  CStatusBarCtrl::GetRect  
 Durum çubuğu denetimi bölümünde sınırlayıcı dikdörtgenini alır.  
  
```  
BOOL GetRect(
    int nPane,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nPane*  
 Alınacak olan sınırlayıcı dikdörtgenini olduğu bölümü sıfır tabanlı dizini.  
  
 *lpRect*  
 Adres bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) sınırlayıcı dikdörtgenini alır yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]  
  
##  <a name="gettext"></a>  CStatusBarCtrl::GetText  
 Durum çubuğu denetimi verilen bölümünden metni alır.  
  
```  
CString GetText(
    int nPane,  
    int* pType = NULL) const;  
  
int GetText(
    LPCTSTR lpszText,  
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszText*  
 Metni alır arabellek adresi. Bu parametre null ile sonlandırılmış bir dizedir.  
  
 *nPane*  
 Metnin alınacağı bölümü sıfır tabanlı dizini.  
  
 *pType*  
 İşaretçi tamsayıya türü bilgilerini alır. Türü şu değerlerden biri olabilir:  
  
- **0** metni durum çubuğu düzlemi düşük görünmesi kenarlık ile çizilir.  
  
- SBT_NOBORDERS metni Kenarlıklar olmadan çizilir.  
  
- SBT_POPOUT metin durum çubuğu düzlemi yüksek görünmesi kenarlık ile çizilir.  
  
- SBT_OWNERDRAW metin sahipse çizim türü, SBT_OWNERDRAW *pType* bu iletiyi alır ve metnin uzunluğu ve işlem türü yerine ilişkili 32-bit değeri döndürür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metnin karakter cinsinden uzunluğu veya [CString](../../atl-mfc-shared/reference/cstringt-class.md) geçerli metni içeren.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]  
  
##  <a name="gettextlength"></a>  CStatusBarCtrl::GetTextLength  
 Durum çubuğu denetiminin verilen bölümünden metnin karakter cinsinden uzunluğu alır.  
  
```  
int GetTextLength(
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nPane*  
 Metnin alınacağı bölümü sıfır tabanlı dizini.  
  
 *pType*  
 İşaretçi tamsayıya türü bilgilerini alır. Türü şu değerlerden biri olabilir:  
  
- **0** metni durum çubuğu düzlemi düşük görünmesi kenarlık ile çizilir.  
  
- SBT_NOBORDERS metni Kenarlıklar olmadan çizilir.  
  
- SBT_OWNERDRAW metni üst pencere çizilir.  
  
- SBT_POPOUT metin durum çubuğu düzlemi yüksek görünmesi kenarlık ile çizilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metnin karakter cinsinden uzunluğu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]  
  
##  <a name="gettiptext"></a>  CStatusBarCtrl::GetTipText  
 Durum çubuğu bölmesinde ipucu metnini alır.  
  
```  
CString GetTipText(int nPane) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nPane*  
 Araç İpucu metni almak için durum çubuğu bölmesinin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) ipucunda kullanılacak metni içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [SB_GETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760751), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]  
  
##  <a name="issimple"></a>  CStatusBarCtrl::IsSimple  
 Basit modunda olup olmadığını belirlemek için bir durum pencere denetim denetler.  
  
```  
BOOL IsSimple() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum pencere denetim basit modda ise sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [SB_ISSIMPLE](http://msdn.microsoft.com/library/windows/desktop/bb760753), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="setbkcolor"></a>  CStatusBarCtrl::SetBkColor  
 Arka plan rengini durum çubuğunda ayarlar.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>Parametreler  
 *CR*  
 Yeni arka plan rengini belirler COLORREF değeri. Varsayılan arka plan rengini kullanmak için durum çubuğunda neden CLR_DEFAULT değeri belirtin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) önceki varsayılan arka plan rengi temsil eden bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [SB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760754), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]  
  
##  <a name="seticon"></a>  CStatusBarCtrl::SetIcon  
 Bir bölme simgesi durum çubuğunda ayarlar.  
  
```  
BOOL SetIcon(
    int nPane,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Parametreler  
 *nPane*  
 Simge alacak bölmesinde sıfır tabanlı dizini. Bu parametre -1 ise, durum çubuğu basit durum çubuğu olduğu varsayılır.  
  
 *hIcon*  
 Ayarlanacak simgesi işleyin. Bu değer NULL ise, simge bölümünden kaldırılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [SB_SETICON](http://msdn.microsoft.com/library/windows/desktop/bb760755), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CStatusBarCtrl::SetBkColor](#setbkcolor).  
  
##  <a name="setminheight"></a>  CStatusBarCtrl::SetMinHeight  
 En küçük yüksekliğini bir durum denetiminin çizim alanını ayarlar.  
  
```  
void SetMinHeight(int nMin);
```  
  
### <a name="parameters"></a>Parametreler  
 *nMin*  
 Denetimin piksel cinsinden en küçük yükseklik.  
  
### <a name="remarks"></a>Açıklamalar  
 En küçük yükseklik toplamıdır *nMin* ve durum çubuğu denetiminin dikey kenarlığının piksel cinsinden genişliği iki kez.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]  
  
##  <a name="setparts"></a>  CStatusBarCtrl::SetParts  
 Durum çubuğu denetim ve her bölümü sağ köşesine koordinatını bölümlerinin sayısını ayarlar.  
  
```  
BOOL SetParts(
    int nParts,  
    int* pWidths);
```  
  
### <a name="parameters"></a>Parametreler  
 *nParts*  
 Ayarlamak için bölümleri sayısı. Parçaların sayısı 255'ten büyük olamaz.  
  
 *pWidths*  
 Tarafından belirtilen bölümleri olarak aynı sayıda öğe olması tamsayı dizisi adresini *nParts*. Dizideki her öğe konumunu, istemci koordinatlarında karşılık gelen bölümü sağ köşesine belirtir. Bir öğe ise - 1, bu bölümü için sağ kenarı konumunu denetimin sağ kenarı genişletir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]  
  
##  <a name="setsimple"></a>  CStatusBarCtrl::SetSimple  
 Durum çubuğu denetimi basit metin görüntüler veya önceki bir çağrı tarafından ayarlanan tüm denetim bölümleri görüntüler belirtir [SetParts](#setparts).  
  
```  
BOOL SetSimple(BOOL bSimple = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSimple*  
 Görüntü türü bayrağı. Bu parametre TRUE ise, basit metin denetimi görüntüler; FALSE ise, birden fazla bölümü görüntüler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı durum çubuğu denetimi basit olmayan öğesinden basit veya tam tersine değişirse, sistem denetimi hemen yeniden çizer.  
  
##  <a name="settext"></a>  CStatusBarCtrl::SetText  
 Metin durum çubuğu denetimi verilen parçası ayarlar.  
  
```  
BOOL SetText(
    LPCTSTR lpszText,  
    int nPane,  
    int nType);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszText*  
 Ayarlamak için metin belirten bir null ile sonlandırılmış dize adresidir. Varsa *nTür* SBT_OWNERDRAW, olan *lpszText* 32 bit veri temsil eder.  
  
 *nPane*  
 Ayarlanacak bölümü sıfır tabanlı dizini. Bu değer 255 ise, durum çubuğu denetimi yalnızca bir parçası olan basit bir denetim olduğu varsayılır.  
  
 *nTür*  
 İşlemi çizim türü. Bkz: [SB_SETTEXT ileti](http://msdn.microsoft.com/library/bb760758\(vs.85\).aspx) olası değerler listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 İleti, yeni metin denetimi sonraki WM_PAINT ileti aldığında görüntülemek için neden değiştiğini denetim kısmı geçersiz kılar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]  
  
##  <a name="settiptext"></a>  CStatusBarCtrl::SetTipText  
 Araç İpucu metni bölmesi için durum çubuğunda ayarlar.  
  
```  
void SetTipText(
    int nPane,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>Parametreler  
 *nPane*  
 Araç İpucu metni almak için durum çubuğu bölmesinin sıfır tabanlı dizini.  
  
 *pszTipText*  
 Araç İpucu metni içeren bir dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [SB_SETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760759), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl Sınıfı](../../mfc/reference/ctoolbarctrl-class.md)
