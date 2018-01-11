---
title: "CStatusBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
dev_langs: C++
helpviewer_keywords:
- CStatusBar [MFC], CStatusBar
- CStatusBar [MFC], CommandToIndex
- CStatusBar [MFC], Create
- CStatusBar [MFC], CreateEx
- CStatusBar [MFC], DrawItem
- CStatusBar [MFC], GetItemID
- CStatusBar [MFC], GetItemRect
- CStatusBar [MFC], GetPaneInfo
- CStatusBar [MFC], GetPaneStyle
- CStatusBar [MFC], GetPaneText
- CStatusBar [MFC], GetStatusBarCtrl
- CStatusBar [MFC], SetIndicators
- CStatusBar [MFC], SetPaneInfo
- CStatusBar [MFC], SetPaneStyle
- CStatusBar [MFC], SetPaneText
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c373f21762c1bf7f21d2a775453bab74c735891d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cstatusbar-class"></a>CStatusBar sınıfı
Denetim çubuğu satır metin çıktısı bölmeleri ya da "göstergeleri."  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CStatusBar : public CControlBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStatusBar::CStatusBar](#cstatusbar)|Oluşturan bir `CStatusBar` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStatusBar::CommandToIndex](#commandtoindex)|Verilen göstergesi kimliği için dizinini alır|  
|[CStatusBar::Create](#create)|Durum çubuğu oluşturur, ekleninceye `CStatusBar` nesne ve ilk yazı tipi ve çubuğu yüksekliğini ayarlar.|  
|[CStatusBar::CreateEx](#createex)|Oluşturur bir `CStatusBar` katıştırılmış için ek stiller nesnesiyle `CStatusBarCtrl` nesnesi.|  
|[CStatusBar::DrawItem](#drawitem)|Bir sahip çizim durum çubuğu denetim değişikliklerini visual yönünü çağrılır.|  
|[CStatusBar::GetItemID](#getitemid)|Gösterge kimliği için belirli bir dizine alır.|  
|[CStatusBar::GetItemRect](#getitemrect)|Alır, belirli bir dizine için dikdörtgen görüntüler.|  
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Gösterge kimliği, stil ve genişlik için belirli bir dizine alır.|  
|[CStatusBar::GetPaneStyle](#getpanestyle)|Gösterge stili için belirli bir dizine alır.|  
|[CStatusBar::GetPaneText](#getpanetext)|Gösterge metni için belirli bir dizine alır.|  
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|Temel alınan ortak denetimi doğrudan erişim sağlar.|  
|[CStatusBar::SetIndicators](#setindicators)|Gösterge kimlikleri ayarlar.|  
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Gösterge kimliği, stil ve genişlik belirli bir dizine için ayarlar.|  
|[CStatusBar::SetPaneStyle](#setpanestyle)|Belirli bir dizine gösterge stilini ayarlar.|  
|[CStatusBar::SetPaneText](#setpanetext)|Gösterge Metni belirli bir dizine için ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çıkış bölmeleri, ileti satırları ve durum göstergesi olarak yaygın olarak kullanılır. Örnekler seçili menü komutu kısaca açıklayan menü Yardım iletisi satırları ve Kaydırma kilidi, NUM LOCK ve diğer anahtarlar durumunu göster göstergelerini içerir.  
  
 [CStatusBar::GetStatusBarCtrl](#getstatusbarctrl), üye işlevi yeni MFC 4.0 ile Windows ortak denetimin durum çubuğu özelleştirme ve ek işlevsellik için desteğinden olanak tanır. `CStatusBar`Windows ortak denetimleri işlevselliğini çoğunu size üye işlevleri; çağırdığınızda ancak `GetStatusBarCtrl`, durum çubukları Windows 95/98 durum çubuğu özelliklerini daha da verebilirsiniz. Çağırdığınızda `GetStatusBarCtrl`, bir başvuru döndürür bir `CStatusBarCtrl` nesnesi. Bkz: [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Windows ortak denetimleri kullanma araç çubukları tasarlama hakkında daha fazla bilgi için. Ortak Denetimler hakkında daha fazla genel bilgi için bkz: [ortak denetimler](http://msdn.microsoft.com/library/windows/desktop/bb775493) Windows SDK'sındaki.  
  
 Framework 0 konumunda soldaki göstergesi olan bir dizi göstergesi bilgilerini depolar. Durum çubuğu oluşturduğunuzda, karşılık gelen göstergeleriyle framework ilişkilendirir kimlikleri dizesinin bir dizi kullanın. Ardından, bir gösterge erişmek için bir dize kimliği veya bir dizin kullanabilirsiniz.  
  
 Varsayılan olarak, ilk "esnek" göstergesidir: sağa hizalı diğer bölmeleri; böylece, diğer göstergesi bölmeler tarafından kullanılmayan durum çubuğu uzunluğu kaplar.  
  
 Durum çubuğu oluşturmak için aşağıdaki adımları izleyin:  
  
1.  Oluşturmak `CStatusBar` nesnesi.  
  
2.  Çağrı [oluşturma](#create) (veya [CreateEx](#createex)) durum çubuğu penceresi oluşturun ve ona eklemek için işlevi `CStatusBar` nesnesi.  
  
3.  Çağrı [SetIndicators](#setindicators) dize kimliği her göstergesi ile ilişkilendirilecek.  
  
 Durum çubuğu bölmesinin metinde güncelleştirmenin üç yolu vardır:  
  
1.  Çağrı [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) bölmesinde 0 yalnızca metin güncelleştirmek için.  
  
2.  Çağrı [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) durum çubuğundaki 's `ON_UPDATE_COMMAND_UI` işleyicisi.  
  
3.  Çağrı [SetPaneText](#setpanetext) herhangi bir bölme için metin güncelleştirmek için.  
  
 Çağrı [SetPaneStyle](#setpanestyle) durum çubuğu bölmesinin stili güncelleştirmek için.  
  
 Kullanma hakkında daha fazla bilgi için `CStatusBar`, makaleye bakın [MFC'de durum çubuğu uygulaması](../../mfc/status-bar-implementation-in-mfc.md) ve [Teknik Not 31: denetim çubukları](../../mfc/tn031-control-bars.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="commandtoindex"></a>CStatusBar::CommandToIndex  
 Verilen kimliğe ait göstergesi dizinini alır  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDFind`  
 Alınacak dizinini olduğu göstergesi kimliği dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa göstergesi dizin; başarılı olursa -1.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk göstergesi dizini 0'dır.  
  
##  <a name="create"></a>CStatusBar::Create  
 Bir durum çubuğu (alt pencere) oluşturur ve bunu ile ilişkilendirir `CStatusBar` nesnesi.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 İşaretçi [CWnd](../../mfc/reference/cwnd-class.md) olan Windows penceresi durum çubuğunun üst nesne.  
  
 `dwStyle`  
 Durum çubuğu stili. Standart Windows yanı sıra [stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles), bu stiller desteklenir.  
  
- `CBRS_TOP`Denetim çubuğu çerçeve penceresi tepesinde bulunur.  
  
- `CBRS_BOTTOM`Denetim çubuğu çerçeve penceresinin alt kısmındaki ' dir.  
  
- `CBRS_NOALIGN`Üst yeniden boyutlandırıldığında denetim çubuğu yeniden konumlandırılır değil.  
  
 `nID`  
 Araç çubuğunun alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrıca, ilk yazı tipini ayarlar ve durumunu ayarlar varsayılan bir değerle çubuğunun yüksekliği.  
  
##  <a name="createex"></a>CStatusBar::CreateEx  
 Bir durum çubuğu (alt pencere) oluşturun ve bunu ile ilişkilendirmek için bu işlevi çağırmak `CStatusBar` nesnesi.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 İşaretçi [CWnd](../../mfc/reference/cwnd-class.md) olan Windows penceresi durum çubuğunun üst nesne.  
  
 `dwCtrlStyle`  
 Katıştırılmış oluşturulması için ek stilleri [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) nesnesi. Durum çubuğu boyutlandırma tutamacı veya araç ipucu olmadan varsayılan belirtir destekler. Durum çubuğu stilleri desteklenen şunlardır:  
  
- **SBARS_SIZEGRIP** durum çubuğu denetiminin boyutlandırma tutamacı durum çubuğunun sağ ucunda içerir. Boyutlandırma tutamacı boyutlandırma kenarlık benzer; Bu, kullanıcı tıklayın ve ana pencereyi yeniden boyutlandırmak için sürükleyin dikdörtgen bir alandır.  
  
- **SBT_TOOLTIPS** durum çubuğu araç ipuçları destekler.  
  
 Bu stiller hakkında daha fazla bilgi için bkz: [CStatusBarCtrl ayarları](../../mfc/settings-for-the-cstatusbarctrl.md).  
  
 `dwStyle`  
 Durum çubuğu stili. Varsayılan çerçeve penceresinin alt kısmında görünür durum çubuğu oluşturulması belirtir. Durum çubuğu denetim stilleri listelenen herhangi bir bileşimini uygulamak [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create). Ancak, bu parametre her zaman WS_CHILD ve ws_vısıble stilleri içermelidir.  
  
 `nID`  
 Durum çubuğu alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, ayrıca ilk yazı tipini ayarlar ve durumunu ayarlar varsayılan bir değerle çubuğunun yüksekliği.  
  
 Kullanım `CreateEx`, yerine [oluşturma](#create), belirli stilleri gömülü durum çubuğu denetimi oluşturma sırasında mevcut olması gerekir. Örneğin, `dwCtrlStyle` için **SBT_TOOLTIPS** bir durum çubuğu nesnesinde araç ipuçları görüntülenecek.  
  
##  <a name="cstatusbar"></a>CStatusBar::CStatusBar  
 Oluşturan bir `CStatusBar` nesnesi, gerekirse varsayılan durum çubuğu yazı oluşturur ve varsayılan değerleri için yazı tipi özelliklerini ayarlar.  
  
```  
CStatusBar();
```  
  
##  <a name="drawitem"></a>CStatusBar::DrawItem  
 Bu üye işlev sahip tarafından çizilmiş durum çubuğu değişikliklerini visual yönünü zaman çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDrawItemStruct`  
 Bir işaretçi bir [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) gerekli çizim türü hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 **İtemAction** üyesi `DRAWITEMSTRUCT` yapısı gerçekleştirilecek çizim eylemi tanımlar. Çizim sahibi çizim için uygulamak için bu üye işlevi geçersiz kılma `CStatusBar` nesnesi. Tüm grafik cihaz arabirimi (GDI) nesneleri görüntüleme bağlamı içinde sağlanan için seçilen uygulama kurtarmalısınız `lpDrawItemStruct` bu üye işlevinin sona ermeden önce.  
  
##  <a name="getitemid"></a>CStatusBar::GetItemID  
 Tarafından belirtilen göstergesi Kimliğini döndürür `nIndex`.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Alınacak Kimliğine sahip göstergesi dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirtilen göstergesi Kimliğini `nIndex`.  
  
##  <a name="getitemrect"></a>CStatusBar::GetItemRect  
 Tarafından belirtilen göstergesi koordinatlarını kopyalar `nIndex` gösterdiği yapıda `lpRect`.  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Alınacak olan dikdörtgen koordinatları olan göstergesi dizini.  
  
 `lpRect`  
 İşaret eden bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) tarafından belirtilen göstergesi koordinatlarını alacak nesne `nIndex`.  
  
### <a name="remarks"></a>Açıklamalar  
 Durum çubuğu sol üst köşesindeki göreli piksel cinsinden koordinatlar belirlenir.  
  
##  <a name="getpaneinfo"></a>CStatusBar::GetPaneInfo  
 Ayarlar `nID`, `nStyle`, ve `cxWidth` kimliği, stil ve genişlik tarafından belirtilen konumda göstergesi bölmesinin `nIndex`.  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Alınacak olan bilgidir bölmesinde dizini.  
  
 `nID`  
 Başvuru bir **UINT** bölmesinde Kimliğine ayarlayın.  
  
 `nStyle`  
 Başvuru bir **UINT** bölmesinde stiline ayarlayın.  
  
 `cxWidth`  
 Bölmesinin genişliğini ayarlamak tamsayı başvuru.  
  
##  <a name="getpanestyle"></a>CStatusBar::GetPaneStyle  
 Durum çubuğu bölmesinin stilini almak için bu üye işlevini çağırın.  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Alınacak stilini olduğu bölmesinde dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirtilen durum çubuğu bölmesinin stilini `nIndex`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmesinde görünme bölme 's stilini belirler.  
  
 Durum çubukları stilleri listesi için bkz: [oluşturma](#create).  
  
##  <a name="getpanetext"></a>CStatusBar::GetPaneText  
 Durum çubuğu bölmesinde görüntülenen metni almak için bu üye işlevini çağırın.  
  
```  
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Alınacak metni olan bölmesinde dizini.  
  
 `rString`  
 Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) alınması için metni içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` Bölmesi'nin metin içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üyenin ikinci formun işlev dolgular bir `CString` dize metin içeren nesne.  
  
##  <a name="getstatusbarctrl"></a>CStatusBar::GetStatusBarCtrl  
 Bu üye işlevi temel ortak denetimi doğrudan erişim sağlar.  
  
```  
CStatusBarCtrl& GetStatusBarCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru içeren bir [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `GetStatusBarCtrl` Windows durum çubuğu ortak denetimi işlevsellikten yararlanmak için ve Destek yararlanmak için [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) için durum çubuğunu özelleştirme sağlar. Örneğin, ortak denetimi kullanarak, durum çubuğundaki boyutlandırma tutamacı içeren bir stil belirtebilirsiniz veya üst pencerenin istemci alanının üstünde görünür durum çubuğu sağlamak için bir stil belirtebilirsiniz.  
  
 Ortak Denetimler hakkında daha fazla genel bilgi için bkz: [ortak denetimler](http://msdn.microsoft.com/library/windows/desktop/bb775493) Windows SDK'sındaki.  
  
##  <a name="setindicators"></a>CStatusBar::SetIndicators  
 Dizi karşılık gelen öğesi tarafından belirtilen değere her göstergenin Kimliğini ayarlar `lpIDArray`, her kimliği tarafından belirtilen dize kaynağı yükler ve göstergenin metin dizesi olarak ayarlar.  
  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpIDArray`  
 Bir dizi kimlikleri işaretçi.  
  
 `nIDCount`  
 Tarafından dizideki öğelerin sayısı işaret için `lpIDArray`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="setpaneinfo"></a>CStatusBar::SetPaneInfo  
 Belirtilen gösterge bölmesinde yeni bir kimliği, stil ve genişlik ayarlar.  
  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Ayarlanacak stilini olduğu göstergesi bölmesinde dizini.  
  
 `nID`  
 Gösterge bölmesinde yeni kimliği.  
  
 `nStyle`  
 Gösterge bölmesinde yeni stili.  
  
 `cxWidth`  
 Yeni genişliği göstergesi bölmesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki göstergesi stilleri desteklenir:  
  
- **SBPS_NOBORDERS** bölmesinde geçici 3-b kenarlık yok.  
  
- **SBPS_POPOUT** ters kenarlık metin "POP çıkışı böylece."  
  
- **SBPS_DISABLED** metin çizme değil.  
  
- **SBPS_STRETCH** kullanılmayan alanı doldurmak için Esnetme bölmesi. Durum çubuğu başına yalnızca bir bölmesinde bu stili olabilir.  
  
- **SBPS_NORMAL** esnetme, kenarlık veya açılır.  
  
##  <a name="setpanestyle"></a>CStatusBar::SetPaneStyle  
 Durum çubuğu bölmesinin stilini ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Ayarlanacak stilini olduğu bölmesinde dizini.  
  
 `nStyle`  
 Ayarlanacak stilini olduğu bölmesinde stili.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmesinde görünme bölme 's stilini belirler.  
  
 Durum çubukları stilleri listesi için bkz: [SetPaneInfo](#setpaneinfo).  
  
##  <a name="setpanetext"></a>CStatusBar::SetPaneText  
 Gösterdiği dizeye bölmesinde metnini ayarlamak için bu üye işlevini çağırın `lpszNewText`.  
  
```  
BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Ayarlanacak metni olan bölmesinde dizini.  
  
 `lpszNewText`  
 Yeni bölmesinde metin işaretçisi.  
  
 *bgüncelleştirmesinin*  
 Varsa **doğru**, metin ayarlandıktan sonra bölmesinde geçersiz kıldı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra `SetPaneText`, yeni metin durum çubuğunda görüntülemek için bir kullanıcı Arabirimi güncelleştirme işleyicisi eklemeniz gerekir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CTRLBARS](../../visual-cpp-samples.md)   
 [MFC örnek DLGCBR32](../../visual-cpp-samples.md)   
 [CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl sınıfı](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
