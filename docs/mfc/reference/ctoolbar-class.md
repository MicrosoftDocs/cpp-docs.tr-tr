---
title: "CToolBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolBar
- AFXEXT/CToolBar
- AFXEXT/CToolBar::CToolBar
- AFXEXT/CToolBar::CommandToIndex
- AFXEXT/CToolBar::Create
- AFXEXT/CToolBar::CreateEx
- AFXEXT/CToolBar::GetButtonInfo
- AFXEXT/CToolBar::GetButtonStyle
- AFXEXT/CToolBar::GetButtonText
- AFXEXT/CToolBar::GetItemID
- AFXEXT/CToolBar::GetItemRect
- AFXEXT/CToolBar::GetToolBarCtrl
- AFXEXT/CToolBar::LoadBitmap
- AFXEXT/CToolBar::LoadToolBar
- AFXEXT/CToolBar::SetBitmap
- AFXEXT/CToolBar::SetButtonInfo
- AFXEXT/CToolBar::SetButtons
- AFXEXT/CToolBar::SetButtonStyle
- AFXEXT/CToolBar::SetButtonText
- AFXEXT/CToolBar::SetHeight
- AFXEXT/CToolBar::SetSizes
dev_langs:
- C++
helpviewer_keywords:
- CToolBar [MFC], CToolBar
- CToolBar [MFC], CommandToIndex
- CToolBar [MFC], Create
- CToolBar [MFC], CreateEx
- CToolBar [MFC], GetButtonInfo
- CToolBar [MFC], GetButtonStyle
- CToolBar [MFC], GetButtonText
- CToolBar [MFC], GetItemID
- CToolBar [MFC], GetItemRect
- CToolBar [MFC], GetToolBarCtrl
- CToolBar [MFC], LoadBitmap
- CToolBar [MFC], LoadToolBar
- CToolBar [MFC], SetBitmap
- CToolBar [MFC], SetButtonInfo
- CToolBar [MFC], SetButtons
- CToolBar [MFC], SetButtonStyle
- CToolBar [MFC], SetButtonText
- CToolBar [MFC], SetHeight
- CToolBar [MFC], SetSizes
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dec2dac93dae9860dfadd347584fbdf465d15838
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ctoolbar-class"></a>CToolBar sınıfı
Denetim çubukları eşlemli düğmeler ve isteğe bağlı ayırıcılar oluşan bir satır vardır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CToolBar : public CControlBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CToolBar::CToolBar](#ctoolbar)|Oluşturan bir `CToolBar` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CToolBar::CommandToIndex](#commandtoindex)|Verilen komut kimliğe sahip bir düğme dizinini döndürür|  
|[CToolBar::Create](#create)|Windows araç çubuğunun oluşturur ve ona ekler `CToolBar` nesnesi.|  
|[CToolBar::CreateEx](#createex)|Oluşturur bir `CToolBar` katıştırılmış için ek stiller nesnesiyle `CToolBarCtrl` nesnesi.|  
|[CToolBar::GetButtonInfo](#getbuttoninfo)|Kimliği, stili ve bir düğme görüntüsü sayısını alır.|  
|[CToolBar::GetButtonStyle](#getbuttonstyle)|Bir düğme stilini alır.|  
|[CToolBar::GetButtonText](#getbuttontext)|Bir düğme görüntülenir metni alır.|  
|[CToolBar::GetItemID](#getitemid)|Düğme veya ayırıcı verilen dizindeki komut Kimliğini döndürür.|  
|[CToolBar::GetItemRect](#getitemrect)|Verilen dizindeki öğe için Görüntü dikdörtgen alır.|  
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|Temel alınan ortak denetimi doğrudan erişim sağlar.|  
|[CToolBar::LoadBitmap](#loadbitmap)|Bit eşlem düğme resimlerini içeren bit eşlem'i yükler.|  
|[CToolBar::LoadToolBar](#loadtoolbar)|Kaynak Düzenleyicisi ile oluşturulmuş bir araç çubuğu kaynağı yükler.|  
|[CToolBar::SetBitmap](#setbitmap)|Eşlemli bir görüntüyü ayarlar.|  
|[CToolBar::SetButtonInfo](#setbuttoninfo)|Kimliği, stili ve bir düğme görüntüsü sayısını ayarlar.|  
|[CToolBar::SetButtons](#setbuttons)|Ayarlar stilleri ve bit eşlem içinde düğme resimlerini dizini düğme.|  
|[CToolBar::SetButtonStyle](#setbuttonstyle)|Bir düğme stilini ayarlar.|  
|[CToolBar::SetButtonText](#setbuttontext)|Görünür metin çubuğunda ayarlar.|  
|[CToolBar::SetHeight](#setheight)|Araç çubuğunun yüksekliği ayarlar.|  
|[CToolBar::SetSizes](#setsizes)|Düğmeler ve bunların bit eşlemler boyutlarını ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Düğmeleri pushbuttons, onay kutusu düğmeleri veya radyo düğmeleri gibi işlev görebilir. `CToolBar`nesneleri sınıfından türetilen çerçeve pencere nesneleri genellikle katıştırılmış üyeleri olan [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md).  
  
 [CToolBar::GetToolBarCtrl](#gettoolbarctrl), üye işlevi yeni MFC 4.0 ile Windows ortak denetimin araç çubuğunu özelleştirme ve ek işlevsellik desteğinden olanak tanır. `CToolBar`Windows ortak denetimleri işlevselliğini çoğunu size üye işlevleri; çağırdığınızda ancak `GetToolBarCtrl`, araç çubuklarınızı Windows 95/98 araç çubukları özelliklerini daha da verebilirsiniz. Çağırdığınızda `GetToolBarCtrl`, bir başvuru döndürür bir `CToolBarCtrl` nesnesi. Bkz: [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) Windows ortak denetimleri kullanma araç çubukları tasarlama hakkında daha fazla bilgi için. Ortak Denetimler hakkında daha fazla genel bilgi için bkz: [ortak denetimler](http://msdn.microsoft.com/library/windows/desktop/bb775493) Windows SDK'sındaki.  
  
 Visual C++ araç çubuğu oluşturmak için iki yöntem sağlar. Kaynak Düzenleyicisi'ni kullanarak bir araç çubuğu kaynak oluşturmak için aşağıdaki adımları izleyin:  
  
1.  Bir araç çubuğu kaynağı oluşturun.  
  
2.  Oluşturmak `CToolBar` nesnesi.  
  
3.  Çağrı [oluşturma](#create) (veya [CreateEx](#createex)) Windows araç çubuğunun oluşturmak ve ona eklemek için işlevi `CToolBar` nesnesi.  
  
4.  Çağrı [LoadToolBar](#loadtoolbar) araç çubuğu kaynağı yüklenemiyor.  
  
 Aksi takdirde, şu adımları izleyin:  
  
1.  Oluşturmak `CToolBar` nesnesi.  
  
2.  Çağrı [oluşturma](#create) (veya [CreateEx](#createex)) Windows araç çubuğunun oluşturmak ve ona eklemek için işlevi `CToolBar` nesnesi.  
  
3.  Çağrı [LoadBitmap](#loadbitmap) araç çubuğu düğmesi görüntüleri içeren bit eşlem'i yüklemek için.  
  
4.  Çağrı [SetButtons](#setbuttons) düğme stilini ayarlamak ve bit eşlem görüntüdeki her düğme ilişkilendirmek için.  
  
 Araç çubuğundaki tüm düğme resimlerini her düğme için bir resim içermeli bir bit eşlem gelen alınır. Tüm görüntüleri, aynı boyutta olmalıdır; 16 piksel genişliğinde ve 15 piksel yüksek varsayılandır. Görüntüleri yan yana eşleminde olması gerekir.  
  
 `SetButtons` İşlevi bir dizi Denetim kimliklerinin ve dizide öğe sayısını belirten bir tamsayı gösteren bir işaretçi alır. İşlev her düğmenin kimliği dizinin karşılık gelen öğe değerine ayarlar ve her düğme eşleminde düğmenin resim konumunu belirten bir görüntü dizini atar. Bir dizi öğesine değerine sahipse **ID_SEPARATOR**, herhangi bir görüntü dizin atanır.  
  
 Bit eşlem görüntüleri sırasını genellikle ekranda çizilir ancak kullanabileceğiniz sıradır [SetButtonInfo](#setbuttoninfo) görüntü sırası ve çizim sırası arasındaki ilişkiyi değiştirmek için işlevi.  
  
 Tüm bir araç çubuğu düğmeleri aynı boyuttadır. Varsayılan değer 24 x 22, ile uyumlu olarak pikseldir *Windows arabirimi yönergelerine yazılım tasarımı için*. Düğmeyi ve görüntü boyutları arasında ek alan görüntünün çevresinde kenarlık oluşturmak için kullanılır.  
  
 Bir görüntü her bir düğme vardır. Çeşitli durumları düğmesini tıklatın ve bu bir görüntüden stilleri (basılan yukarı, aşağı, devre dışı, aşağı devre dışı bırakılmış ve belirsiz) oluşturulur. Bit eşlemler herhangi bir renk olabilse de, siyah ve gri görüntülerde en iyi sonuçları elde edebilirsiniz.  
  
> [!WARNING]
> `CToolBar`bit eşlemler en fazla 16 renk destekler. Araç çubuğu Düzenleyicisi bir görüntü yüklediğinizde Visual Studio otomatik olarak görüntü renk 16 bit eşlem için gerekirse dönüştürür ve görüntünün dönüştürülürse bir uyarı iletisi görüntüler. Görüntüyü (görüntü düzenlemek için harici bir düzenleyiciyi kullanarak) 16'dan fazla renklerle kullanırsanız, uygulama beklenmedik bir şekilde davranan.  
  
 Araç çubuğu düğmeleri pushbuttons varsayılan olarak taklit. Ancak, araç çubuğu düğmeleri de onay kutusu düğmeler veya radyo düğmeleri taklit. Onay kutusu düğmeleri sahip üç durumdan: checked, temizlenen ve belirsiz. Radyo düğmeleri yalnızca iki durumlu sahiptir: denetlenir ve temizlenir.  
  
 Bir dizi işaret eden olmadan bir bireysel düğme veya ayırıcı stili ayarlamak için arama [GetButtonStyle](#getbuttonstyle) stili almak ve ardından çağırmak için [SetButtonStyle](#setbuttonstyle) yerine `SetButtons`. `SetButtonStyle`Çalışma zamanında düğmenin stilini değiştirmek istediğinizde çok yararlıdır.  
  
 Bir düğme görüntülenecek metni atamak için arama [GetButtonText](#getbuttontext) düğmesi görünür ve ardından çağırmak üzere metin almak için [SetButtonText](#setbuttontext) metnini ayarlamak için.  
  
 Bir onay kutusu düğme oluşturmak için stil atamak **TBBS_CHECKBOX** veya bir `CCmdUI` nesnenin `SetCheck` üye işlevinde bir `ON_UPDATE_COMMAND_UI` işleyicisi. Çağırma `SetCheck` bir onay kutusu düğmesinde bir basma düğmesi kapatır. Geçirmek `SetCheck` bağımsız değişken 0 işaretlenmemişse 1 checked ya da 2 için için belirsiz.  
  
 Radyo düğmesi oluşturmak için arama bir [Ccmduı](../../mfc/reference/ccmdui-class.md) nesnenin [SetRadio](../../mfc/reference/ccmdui-class.md#setradio) üye işlevinden bir `ON_UPDATE_COMMAND_UI` işleyicisi. Geçirmek `SetRadio` 0 denetlenmeyen veya teslim için sıfır olmayan bir bağımsız değişken. Radyo grubun birbirini dışlayan davranışı sağlamak için içermelidir `ON_UPDATE_COMMAND_UI` tüm grubundaki düğmeleri için işleyiciler.  
  
 Kullanma hakkında daha fazla bilgi için `CToolBar`, makaleye bakın [MFC araç çubuğu uygulaması](../../mfc/mfc-toolbar-implementation.md) ve [Teknik Not 31: denetim çubukları](../../mfc/tn031-control-bars.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="commandtoindex"></a>CToolBar::CommandToIndex  
 Bu üye işlevi komut kimliği eşleşen 0, konumdan başlayarak ilk araç çubuğu düğmesi, dizinini döndürür `nIDFind`.  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDFind`  
 Araç çubuğu düğmesi komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme veya hiçbir düğmesi verilen komut kimliği varsa -1 dizini  
  
##  <a name="create"></a>CToolBar::Create  
 Bu üye işlevi bir Windows araç çubuğu (alt pencere) oluşturur ve bunu ile ilişkilendirir `CToolBar` nesnesi.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,  
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 Araç çubuğunun üst penceresine işaretçi.  
  
 `dwStyle`  
 Araç çubuğu stili. Desteklenen ek araç çubuğu stilleri şunlardır:  
  
- `CBRS_TOP`Denetim çubuğu çerçeve penceresi tepesinde bulunur.  
  
- `CBRS_BOTTOM`Denetim çubuğu çerçeve penceresinin alt kısmındaki ' dir.  
  
- `CBRS_NOALIGN`Üst yeniden boyutlandırıldığında denetim çubuğu yeniden konumlandırılır değil.  
  
- `CBRS_TOOLTIPS`Denetim çubuğu araç ipuçları görüntüler.  
  
- **Cbrs_sıze_dynamıc** denetim çubuğu dinamik.  
  
- **Cbrs_sıze_fıxed** denetim çubuğu sabittir.  
  
- **CBRS_FLOATING** denetim çubuğu kayan.  
  
- `CBRS_FLYBY`Durum çubuğu düğme hakkındaki bilgileri görüntüler.  
  
- **CBRS_HIDE_INPLACE** denetim çubuğu kullanıcıya görüntülenmez.  
  
 `nID`  
 Araç çubuğunun alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrıca araç yüksekliği için varsayılan bir değer ayarlar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]  
  
##  <a name="createex"></a>CToolBar::CreateEx  
 Bir Windows araç çubuğu (alt pencere) oluşturun ve bunu ile ilişkilendirmek için bu işlevi çağırmak `CToolBar` nesnesi.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = TBSTYLE_FLAT,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,  
    CRect rcBorders = CRect(
    0, 
    0, 
    0, 
    0), 
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 Araç çubuğunun üst penceresine işaretçi.  
  
 `dwCtrlStyle`  
 Katıştırılmış oluşturulması için ek stilleri [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) nesnesi. Varsayılan olarak, bu değeri ayarlamak **TBSTYLE_FLAT**. Araç çubuğu stilleri tam bir listesi için bkz: `dwStyle`.  
  
 `dwStyle`  
 Araç çubuğu stili. Bkz: [araç çubuğu denetimi ve düğme stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760439) uygun stilleri listesi için Windows SDK.  
  
 *rcBorders*  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) araç penceresi kenarlık genişliğini tanımlayan nesne. Bu Kenarlıklar kenarlık yok ile bir araç penceresinde böylece kaynaklanan varsayılan 0,0,0,0 için ayarlanır.  
  
 `nID`  
 Araç çubuğunun alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrıca araç yüksekliği için varsayılan bir değer ayarlar.  
  
 Kullanım `CreateEx`, yerine [oluşturma](#create), belirli stilleri katıştırılmış araç çubuğu denetimi oluşturma sırasında mevcut olması gerekir. Örneğin, `dwCtrlStyle` için **TBSTYLE_FLAT &#124; TBSTYLE_TRANSPARENT** Internet Explorer 4 araç çubukları benzer bir araç çubuğu oluşturmak için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]  
  
##  <a name="ctoolbar"></a>CToolBar::CToolBar  
 Bu üye işlevi oluşturan bir `CToolBar` nesne ve varsayılan boyutları ayarlar.  
  
```  
CToolBar();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [oluşturma](#create) üye işlevi araç penceresi oluşturulamadı.  
  
##  <a name="getbuttoninfo"></a>CToolBar::GetButtonInfo  
 Bu üye işlevi denetim kimliği, stil ve araç çubuğu düğmesi veya tarafından belirtilen konumda ayırıcı resim dizinini alır *nIndex.*  
  
```  
void GetButtonInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& iImage) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Araç çubuğu düğmesi veya alınacak olan bilgidir ayırıcı dizini.  
  
 `nID`  
 Başvuru bir **UINT** düğmesini komut kimliği ayarlayın.  
  
 `nStyle`  
 Başvuru bir **UINT** düğmesinin stili için ayarlanır.  
  
 `iImage`  
 Bit eşlem içinde düğmenin görüntünün dizinini olarak ayarlanmış bir tamsayı başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değerleri başvurduğu değişkenleri atanan `nID`, `nStyle`, ve `iImage`. Görüntü dizini içindeki tüm araç çubuğu düğmeleri için görüntüleri içeren bit eşlem görüntü konumudur. İlk görüntüyü 0 konumundadır.  
  
 Varsa `nIndex` bir ayırıcı belirtir `iImage` ayırıcı genişliğini piksel cinsinden ayarlanır.  
  
##  <a name="getbuttonstyle"></a>CToolBar::GetButtonStyle  
 Düğme veya araç çubuğunda ayırıcı stilini almak için bu üye işlevini çağırın.  
  
```  
UINT GetButtonStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Alınacak araç çubuğu düğmesini veya ayırıcı stili dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme veya tarafından belirtilen ayırıcı stilini `nIndex`.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme nasıl göründüğünü ve nasıl kullanıcı girişine yanıt vereceğini düğmenin stilini belirler. Bkz: [SetButtonStyle](#setbuttonstyle) düğme stilleri örnekleri için.  
  
##  <a name="getbuttontext"></a>CToolBar::GetButtonText  
 Çubuğunda görüntülenen metni almak için bu üye işlevini çağırın.  
  
```  
CString GetButtonText(int nIndex) const;  
  
void GetButtonText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Alınacak metin dizini.  
  
 `rString`  
 Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) alınacak metni içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` düğme metni içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üyenin ikinci formun işlev dolgular bir `CString` dize metin içeren nesne.  
  
##  <a name="getitemid"></a>CToolBar::GetItemID  
 Bu üye işlevi düğmesini veya ayırıcı tarafından belirtilen komut Kimliğini döndürür `nIndex`.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Alınacak Kimliğine sahip öğenin dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme veya ayırıcı tarafından belirtilen komut Kimliğini `nIndex`.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayırıcılar dönmek **ID_SEPARATOR**.  
  
##  <a name="getitemrect"></a>CToolBar::GetItemRect  
 Bu üye işlevi doldurur `RECT` adresini bulunduğu yapısı `lpRect` düğmesini veya tarafından belirtilen ayırıcı koordinatları ile `nIndex`.  
  
```  
virtual void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Alınacak olan dikdörtgen koordinatları olan öğenin (düğmesini veya ayırıcı) dizini.  
  
 `lpRect`  
 Adres [RECT](../../mfc/reference/rect-structure1.md) öğesi'nin koordinatları içerecek yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Araç sol üst köşesindeki göreli piksel cinsinden koordinatlar belirlenir.  
  
 Kullanım `GetItemRect` birleşik giriş kutusu veya diğer denetim ile değiştirmek istediğiniz bir ayırıcı koordinatlarını alma.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CToolBar::SetSizes](#setsizes).  
  
##  <a name="gettoolbarctrl"></a>CToolBar::GetToolBarCtrl  
 Bu üye işlevi temel ortak denetimi doğrudan erişim sağlar.  
  
```  
CToolBarCtrl& GetToolBarCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru bir `CToolBarCtrl` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `GetToolBarCtrl` Windows araç ortak denetimi işlevsellikten yararlanmak için ve Destek yararlanmak için [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) için araç çubuğunu özelleştirme sağlar.  
  
 Makale ortak denetimleri kullanma hakkında daha fazla bilgi için bkz: [denetimleri](../../mfc/controls-mfc.md) ve [ortak denetimler](http://msdn.microsoft.com/library/windows/desktop/bb775493) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]  
  
##  <a name="loadbitmap"></a>CToolBar::LoadBitmap  
 Tarafından belirtilen bit eşlem'i yüklemek için bu üye işlevini çağırın `lpszResourceName` veya `nIDResource`.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszResourceName`  
 Yüklenecek bit eşlem kaynak adını işaretçi.  
  
 `nIDResource`  
 Yüklenecek kaynak kimliği bitmap.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit eşlem her araç çubuğu düğmesi için bir görüntü içerir. Görüntüler standart boyutu (16 piksel genişliğinde ve yüksek 15 piksel) çağrı değilse [SetSizes](#setsizes) düğme boyutlarını ve resimlerinin ayarlamak için.  
  
> [!WARNING]
> `CToolBar`bit eşlemler en fazla 16 renk destekler. Araç çubuğu Düzenleyicisi bir görüntü yüklediğinizde Visual Studio otomatik olarak görüntü renk 16 bit eşlem için gerekirse dönüştürür ve görüntünün dönüştürülürse bir uyarı iletisi görüntüler. Görüntüyü (görüntü düzenlemek için harici bir düzenleyiciyi kullanarak) 16'dan fazla renklerle kullanırsanız, uygulama beklenmedik bir şekilde davranan.  
  
##  <a name="loadtoolbar"></a>CToolBar::LoadToolBar  
 Tarafından belirtilen araç yüklemek için bu üye işlevini çağırın `lpszResourceName` veya `nIDResource`.  
  
```  
BOOL LoadToolBar(LPCTSTR lpszResourceName);  
BOOL LoadToolBar(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszResourceName`  
 Kaynak adı yüklenmesi için araç çubuğunda işaretçi.  
  
 `nIDResource`  
 Yüklenecek kaynak kimliği araç.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [araç çubuğu Düzenleyicisi](../../windows/toolbar-editor.md) içinde bir araç çubuğu kaynak oluşturma hakkında daha fazla bilgi için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CToolBar::CreateEx](#createex).  
  
##  <a name="setbitmap"></a>CToolBar::SetBitmap  
 Araç çubuğu bit eşlem resim ayarlamak için bu üye işlevini çağırın.  
  
```  
BOOL SetBitmap(HBITMAP hbmImageWell);
```  
  
### <a name="parameters"></a>Parametreler  
 *hbmImageWell*  
 Bir araç çubuğu ile ilişkili bir bit eşlem resim tanıtıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, arama `SetBitmap` kullanıcı bir düğme eylem değiştiren bir belgeyi eylemde sonra eşlemli görüntü değiştirmek için.  
  
##  <a name="setbuttoninfo"></a>CToolBar::SetButtonInfo  
 Düğmenin komut kimliği, stil ve görüntü sayısını ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetButtonInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int iImage);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Düğme veya bilgi ayarlanacak olduğu ayırıcı sıfır tabanlı dizini.  
  
 `nID`  
 Düğmenin komut kimliği ayarlanmış değeri.  
  
 `nStyle`  
 Yeni düğmesi stili. Aşağıdaki düğme stilleri desteklenir:  
  
- **TBBS_BUTTON** standart basma düğmesi (varsayılan)  
  
- **TBBS_SEPARATOR** ayırıcı  
  
- **TBBS_CHECKBOX** otomatik onay kutusu düğmesi  
  
- **TBBS_GROUP** düğmesi grubu başlangıcını işaretler  
  
- **TBBS_CHECKGROUP** onay kutusu düğmesi grubu başlangıcını işaretler  
  
- **TBBS_DROPDOWN** bir açılır liste düğmesi oluşturur.  
  
- **TBBS_AUTOSIZE** düğmenin genişliği, düğme metin, görüntü boyutunu değil, temel hesaplanır.  
  
- **TBBS_NOPREFIX** düğme metni kendisiyle ilişkili bir Hızlandırıcı öneki sahip değil.  
  
 `iImage`  
 Düğmenin resim bit eşlem içinde yeni dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayırıcılar için sahip olduğunuz stili **TBBS_SEPARATOR**, bu işlev depolanan değerine piksel cinsinden ayırıcı 's genişliğini ayarlar `iImage`.  
  
> [!NOTE]
>  Düğme durumları kullanarak de ayarlayabilirsiniz `nStyle` parametresi; ancak, düğme durumları tarafından kontrol edilir çünkü [on_update_command_uı](message-map-macros-mfc.md#on_update_command_ui) işleyici, herhangi bir durum ayarlamak kullanarak `SetButtonInfo` sonraki sırasında kaybolur boşta işleniyor. Bkz: [güncelleştirme kullanıcı arabirimi nesnelerini nasıl](../../mfc/how-to-update-user-interface-objects.md) ve [TN031: denetim çubukları](../../mfc/tn031-control-bars.md) daha fazla bilgi için.  
  
 Bit eşlem görüntüler ve düğmeleri hakkında daha fazla bilgi için bkz: [CToolBar](../../mfc/reference/ctoolbar-class.md) genel bakış ve [CToolBar::LoadBitmap](#loadbitmap).  
  
##  <a name="setbuttons"></a>CToolBar::SetButtons  
 Bu üye işlevi her araç düğmenin komut kimliği dizi karşılık gelen öğesi tarafından belirtilen değere ayarlar `lpIDArray`.  
  
```  
BOOL SetButtons(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpIDArray`  
 Komut kimlikleri bir dizi işaretçi. Bu olabilir **NULL** boş düğmeleri ayrılamadı.  
  
 `nIDCount`  
 Tarafından dizideki öğelerin sayısı işaret için `lpIDArray`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizinin bir öğenin değeri varsa **ID_SEPARATOR**, ayırıcı araç ilgili konumda oluşturulur. Bu işlev ayrıca her düğmenin stilini ayarlar **TBBS_BUTTON** ve her ayırıcı 's stiline **TBBS_SEPARATOR**ve her düğme için resim dizini atar. Görüntü dizini bit eşlem içindeki düğmenin görüntüsünün konumunu belirtir.  
  
 Bu işlev ayırıcılar için görüntü dizinleri atamaz için bit eşlemde ayırıcılar hesaba gerekmez. Araç konumlar 0 düğmesi varsa, 1 ve 3 ve 2 konumunda, görüntüler, bit eşlem, 0, 1 ve 2 konumlarda ayırıcı düğmelerini konumlar 0, 1 ve 3, sırasıyla atanır.  
  
 Varsa `lpIDArray` olan **NULL**, bu işlev tarafından belirtilen öğe sayısı için alan ayırır `nIDCount`. Kullanım [SetButtonInfo](#setbuttoninfo) her öğenin öznitelikleri ayarlamak için.  
  
##  <a name="setbuttonstyle"></a>CToolBar::SetButtonStyle  
 Bir düğme veya ayırıcı ya da Grup düğmelere stil ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Düğme veya ayarlanması, bilgidir ayırıcı dizini.  
  
 `nStyle`  
 Düğme stili. Aşağıdaki düğme stilleri desteklenir:  
  
- **TBBS_BUTTON** standart basma düğmesi (varsayılan)  
  
- **TBBS_SEPARATOR** ayırıcı  
  
- **TBBS_CHECKBOX** otomatik onay kutusu düğmesi  
  
- **TBBS_GROUP** düğmesi grubu başlangıcını işaretler  
  
- **TBBS_CHECKGROUP** onay kutusu düğmesi grubu başlangıcını işaretler  
  
- **TBBS_DROPDOWN** bir açılır liste düğmesi oluşturur  
  
- **TBBS_AUTOSIZE** düğmenin genişliği, düğme metin, görüntü boyutunu değil, temel hesaplanır  
  
- **TBBS_NOPREFIX** düğme metni kendisiyle ilişkili bir Hızlandırıcı öneki sahip değil  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme nasıl göründüğünü ve nasıl kullanıcı girişine yanıt vereceğini düğmenin stilini belirler.  
  
 Çağırmadan önce `SetButtonStyle`, çağrı [GetButtonStyle](#getbuttonstyle) düğmesini veya ayırıcı stili almak için üye işlevi.  
  
> [!NOTE]
>  Düğme durumları kullanarak de ayarlayabilirsiniz `nStyle` parametresi; ancak, düğme durumları tarafından kontrol edilir çünkü [on_update_command_uı](message-map-macros-mfc.md#on_update_command_ui) işleyici, herhangi bir durum ayarlamak kullanarak `SetButtonStyle` sonraki sırasında kaybolur boşta işleniyor. Bkz: [güncelleştirme kullanıcı arabirimi nesnelerini nasıl](../../mfc/how-to-update-user-interface-objects.md) ve [TN031: denetim çubukları](../../mfc/tn031-control-bars.md) daha fazla bilgi için.  
  
##  <a name="setbuttontext"></a>CToolBar::SetButtonText  
 Bir düğme metni ayarlamak için bu işlevini çağırın.  
  
```  
BOOL SetButtonText(
    int nIndex,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Ayarlanacak metni olan düğme dizini.  
  
 `lpszText`  
 Bir düğme ayarlanacak metin noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CToolBar::GetToolBarCtrl](#gettoolbarctrl).  
  
##  <a name="setheight"></a>CToolBar::SetHeight  
 Bu üye işlevi araç çubuğunun yüksekliğini piksel cinsinden belirtilen değere ayarlar `cyHeight`.  
  
```  
void SetHeight(int cyHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 `cyHeight`  
 Araç çubuğunun piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra [SetSizes](#setsizes), standart araç yükseklik geçersiz kılmak için bu üye işlevini kullanın. Yükseklik kadar küçükse düğmeleri altındaki kırpılır.  
  
 Bu işlev çağrılmazsa framework düğmenin boyutunu araç yüksekliği belirlemek için kullanır.  
  
##  <a name="setsizes"></a>CToolBar::SetSizes  
 Araç çubuğunun düğmeleri belirtilen piksel cinsinden boyutu ayarlamak için bu üye işlevini çağırın *sizeButton*.  
  
```  
void SetSizes(
    SIZE sizeButton,  
    SIZE sizeImage);
```  
  
### <a name="parameters"></a>Parametreler  
 *sizeButton*  
 Her düğme piksel cinsinden boyutu.  
  
 `sizeImage`  
 Her görüntüsünün piksel cinsinden boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 `sizeImage` Parametresi piksel cinsinden araç çubuğunun bit eşlem görüntüleri boyutu içermesi gerekir. Boyutlar *sizeButton* görüntü artı 7 piksel cinsinden genişliği fazladan ve 6 piksel cinsinden yükseklik fazladan tutmak için yeterli olmalıdır. Bu işlev, ayrıca araç yüksekliğini düğmeleri ayarlar.  
  
 Bu üye işlevini çağırın değil izleyen yalnızca için araç çubukları *Windows arabirimi yönergelerine yazılım tasarımı için* düğmesi ve görüntü boyutları için öneriler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CTRLBARS](../../visual-cpp-samples.md)   
 [MFC örnek DLGCBR32](../../visual-cpp-samples.md)   
 [MFC örnek DOCKTOOL](../../visual-cpp-samples.md)   
 [CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl sınıfı](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
