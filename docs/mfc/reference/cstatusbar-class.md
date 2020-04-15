---
title: CStatusBar Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 0549ee10faa15b80b18a0bee2f115425002e1479
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376255"
---
# <a name="cstatusbar-class"></a>CStatusBar Sınıfı

Metin çıktısı bölmeleri veya "göstergeler" satırı içeren bir denetim çubuğu.

## <a name="syntax"></a>Sözdizimi

```
class CStatusBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CStatusBar::cstatusbar](#cstatusbar)|Bir `CStatusBar` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Cstatusbar::commandtoindex](#commandtoindex)|Belirli bir gösterge kimliği için dizin alır.|
|[CStatusBar::Oluştur](#create)|Durum çubuğunu oluşturur, `CStatusBar` nesneye bağlar ve ilk yazı tipini ve çubuk yüksekliğini ayarlar.|
|[CStatusBar::CreateEx](#createex)|Katıştırılmış `CStatusBar` `CStatusBarCtrl` nesne için ek stiller içeren bir nesne oluşturur.|
|[CStatusBar::DrawItem](#drawitem)|Sahibi-beraberlik durum çubuğu denetiminin görsel bir yönü değiştiğinde çağrılır.|
|[CStatusBar::GetItemID](#getitemid)|Belirli bir dizin için gösterge kimliği alır.|
|[CStatusBar::GetItemRect](#getitemrect)|Belirli bir dizin için ekran dikdörtgeni alır.|
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Belirli bir dizin için gösterge kimliği, stil ve genişlik alır.|
|[CStatusBar::GetPaneStyle](#getpanestyle)|Belirli bir dizin için gösterge stilialır.|
|[CStatusBar::GetPaneText](#getpanetext)|Belirli bir dizin için gösterge metni alır.|
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|Altta yatan ortak denetime doğrudan erişim sağlar.|
|[CStatusBar::SetIndicators](#setindicators)|Gösterge işlleri ayarlar.|
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Belirli bir dizin için gösterge kimliği, stil ve genişlik ayarlar.|
|[CStatusBar::SetPaneStyle](#setpanestyle)|Belirli bir dizin için gösterge stilini ayarlar.|
|[CStatusBar::SetPaneText](#setpanetext)|Belirli bir dizin için gösterge metnini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Çıktı bölmeleri genellikle ileti satırları ve durum göstergeleri olarak kullanılır. Örnekler arasında, seçili menü komutunu kısaca açıklayan menü yardım iletisi satırları ve SCROLL LOCK, NUM LOCK ve diğer tuşların durumunu gösteren göstergeler yer almaktadır.

MFC 4.0'a yeni bir üye işlevi olan [CStatusBarBarCtrl,](#getstatusbarctrl)durum çubuğu özelleştirme ve ek işlevsellik için Windows ortak denetiminin desteğinden yararlanmanızı sağlar. `CStatusBar`üye işlevler, Windows ortak denetimlerinin işlevselliğinin çoğunu sağlar; ancak, aradiğinizde, `GetStatusBarCtrl`durum çubuklarınıza Windows 95/98 durum çubuğunun özelliklerinden daha fazlasını verebilirsiniz. `GetStatusBarCtrl`Aradiğinizde, bir `CStatusBarCtrl` nesneye bir başvuru döndürecektir. Windows ortak denetimlerini kullanarak araç çubukları tasarlama hakkında daha fazla bilgi için [CStatusBarCtrl'a](../../mfc/reference/cstatusbarctrl-class.md) bakın. Ortak denetimler hakkında daha genel bilgi için Windows SDK'daki [Ortak Denetimler'e](/windows/win32/Controls/common-controls-intro) bakın.

Çerçeve, gösterge bilgilerini en soldaki gösterge 0 konumunda olan bir dizide depolar. Bir durum çubuğu oluşturduğunuzda, çerçevenin ilgili göstergelerle ilişkilendiren bir dizi dize ii kullanırsınız. Daha sonra bir göstergeye erişmek için dize kimliği veya dizin kullanabilirsiniz.

Varsayılan olarak, ilk gösterge "elastik"tir: diğer gösterge bölmeleri tarafından kullanılmayan durum çubuğu uzunluğunu alır, böylece diğer bölmeler sağa hizalanır.

Durum çubuğu oluşturmak için aşağıdaki adımları izleyin:

1. Nesneyi `CStatusBar` oluştur.

1. Durum çubuğu penceresini oluşturmak ve `CStatusBar` nesneye takmak için [Oluştur](#create) (veya [CreateEx)](#createex)işlevini arayın.

1. Dize kimliğini her göstergeyle ilişkilendirmek için [SetIndicators'ı](#setindicators) arayın.

Durum çubuğu bölmesinde metni güncelleştirmenin üç yolu vardır:

1. [CWnd'yi arayın::Yalnızca](../../mfc/reference/cwnd-class.md#setwindowtext) bölme 0'daki metni güncelleştirmek için SetWindowText'i ayarlayın.

1. [CCmdUI'yi arayın::Durum](../../mfc/reference/ccmdui-class.md#settext) çubuğunun ON_UPDATE_COMMAND_UI işleyicisinde SetText' i arayın.

1. Herhangi bir bölme için metni güncelleştirmek için [SetPaneText'i](#setpanetext) arayın.

Durum çubuğu bölmesinin stilini güncelleştirmek için [SetPaneStyle'ı](#setpanestyle) arayın.

Kullanma `CStatusBar`hakkında daha fazla bilgi için, MFC ve [Teknik Not 31](../../mfc/tn031-control-bars.md)makale Durum [Çubuğu Uygulama](../../mfc/status-bar-implementation-in-mfc.md) bakın : Denetim Çubukları .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Ccontrolbar](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="cstatusbarcommandtoindex"></a><a name="commandtoindex"></a>Cstatusbar::commandtoindex

Belirli bir kimliğin gösterge dizini alır.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parametreler

*nIDFind*<br/>
Dizin alınacak göstergenin dize kimliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa göstergenin dizini; -1 başarılı olmazsa.

### <a name="remarks"></a>Açıklamalar

İlk göstergenin dizini 0'dır.

## <a name="cstatusbarcreate"></a><a name="create"></a>CStatusBar::Oluştur

Durum çubuğu (alt pencere) oluşturur ve `CStatusBar` nesneyle ilişkilendirer.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Windows penceresi durum çubuğunun üst öğesi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi.

*Dwstyle*<br/>
Durum çubuğu stili. Standart Windows [stillerine](../../mfc/reference/styles-used-by-mfc.md#window-styles)ek olarak, bu stiller desteklenir.

- CBRS_TOP Denetim çubuğu çerçeve penceresinin en üstündedir.

- CBRS_BOTTOM Denetim çubuğu çerçeve penceresinin alt kısmındadır.

- CBRS_NOALIGN Denetim çubuğu, üst öğe yeniden boyutlandırıldığında yeniden konumlandırılmez.

*Nıd*<br/>
Araç çubuğunun alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca ilk yazı tipini ayarlar ve durum çubuğunun yüksekliğini varsayılan değere ayarlar.

## <a name="cstatusbarcreateex"></a><a name="createex"></a>CStatusBar::CreateEx

Durum çubuğu (alt pencere) oluşturmak ve `CStatusBar` nesneyle ilişkilendirmek için bu işlevi arayın.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Windows penceresi durum çubuğunun üst öğesi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi.

*dwCtrlStyle*<br/>
Katıştılmış [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) nesnesinin oluşturulması için ek stiller. Varsayılan, boyutlandırma kavrama veya araç ipucu desteği olmayan bir durum çubuğu belirtir. Desteklenen durum çubuğu stilleri şunlardır:

- SBARS_SIZEGRIP Durum çubuğu denetimi, durum çubuğunun sağ ucunda bir boyutlandırma kavrama içerir. Boyutlandırma kavrama, boyutlandırma sınırına benzer; kullanıcının üst pencereyi yeniden boyutlandırmak için tıklatıp sürükleyebileceği dikdörtgen bir alandır.

- SBT_TOOLTIPS Durum çubuğu araç ipuçlarını destekler.

Bu stiller hakkında ayrıntılı bilgi için [CStatusBarCtrl ayarlarına](../../mfc/settings-for-the-cstatusbarctrl.md)bakın.

*Dwstyle*<br/>
Durum çubuğu stili. Varsayılan, çerçeve penceresinin alt kısmında görünür bir durum çubuğu oluşturulacak şekilde belirtir. [Pencere Stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve CDialogBar listelenen durum çubuğu denetim stilleri herhangi bir birleşimini [uygulayın:Oluştur](../../mfc/reference/cdialogbar-class.md#create). Ancak, bu parametre her zaman WS_CHILD ve WS_VISIBLE stilleri içermelidir.

*Nıd*<br/>
Durum çubuğunun alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev ayrıca ilk yazı tipini ayarlar ve durum çubuğunun yüksekliğini varsayılan değere ayarlar.

Katıştırılmış durum çubuğu denetiminin oluşturulması sırasında belirli stillerin bulunması gerektiğinde `CreateEx` [Oluştur](#create)yerine kullanın. Örneğin, durum çubuğu nesnesinde araç uçlarını görüntülemek için *dwCtrlStyle'yı* SBT_TOOLTIPS ayarlayın.

## <a name="cstatusbarcstatusbar"></a><a name="cstatusbar"></a>CStatusBar::cstatusbar

Nesne `CStatusBar` oluşturur, gerekirse varsayılan durum çubuğu yazı tipi oluşturur ve yazı tipi özelliklerini varsayılan değerlere ayarlar.

```
CStatusBar();
```

## <a name="cstatusbardrawitem"></a><a name="drawitem"></a>CStatusBar::DrawItem

Bu üye işlev, sahip tarafından çizilen durum çubuğunun görsel bir yönü değiştiğinde çerçeve tarafından çağrılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısıiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yapının `itemAction` `DRAWITEMSTRUCT` üyesi, gerçekleştirilecek çizim eylemini tanımlar. Bir sahip çizim `CStatusBar` nesnesi için çizim uygulamak için bu üye işlevi geçersiz kılın. Uygulama, bu üye işlevin sonlandırılmasından önce *lpDrawItemStruct'ta* sağlanan ekran bağlamı için seçilen tüm grafik aygıtı arabirimi (GDI) nesnelerini geri yüklemelidir.

## <a name="cstatusbargetitemid"></a><a name="getitemid"></a>CStatusBar::GetItemID

*nIndex*tarafından belirtilen göstergenin kimliğini verir.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Kimliği alınacak göstergenin dizini.

### <a name="return-value"></a>Dönüş Değeri

*nIndex*tarafından belirtilen göstergenin kimliği.

## <a name="cstatusbargetitemrect"></a><a name="getitemrect"></a>CStatusBar::GetItemRect

*nIndex* tarafından belirtilen göstergenin koordinatlarını *lpRect*tarafından işaret edilen yapıya kopyalar.

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Dikdörtgen koordinatları alınacak göstergenin dizin.

*Lprect*<br/>
*NIndex*tarafından belirtilen göstergenin koordinatlarını alacak bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

Koordinatlar durum çubuğunun sol üst köşesine göre piksel olarak dır.

## <a name="cstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>CStatusBar::GetPaneInfo

*ND,* *nStyle*ve *cxWidth'i* *nIndex*tarafından belirtilen konumdaki gösterge bölmesinin kimliğine, stiline ve genişliğine ayarlar.

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Bilgileri alınacak bölmenin dizini.

*Nıd*<br/>
Bölmenin kimliğine ayarlanan bir UINT'ye başvuru.

*nStyle*<br/>
Bölmenin stiline ayarlanmış bir UINT'ye başvuru.

*cxGenişlik*<br/>
Bölmenin genişliğine ayarlanmış bir karşıcıya başvuru.

## <a name="cstatusbargetpanestyle"></a><a name="getpanestyle"></a>CStatusBar::GetPaneStyle

Durum çubuğu bölmesinin stilini almak için bu üye işlevi arayın.

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Stili alınacak bölmenin dizini.

### <a name="return-value"></a>Dönüş Değeri

*nIndex*tarafından belirtilen durum çubuğu bölmesinin stili.

### <a name="remarks"></a>Açıklamalar

Bölmenin stili bölmenin nasıl görüner belirler.

Durum çubukları için kullanılabilen stillerin listesi için [bkz.](#create)

## <a name="cstatusbargetpanetext"></a><a name="getpanetext"></a>CStatusBar::GetPaneText

Durum çubuğu bölmesinde görünen metni almak için bu üye işlevi arayın.

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Metni alınacak bölmenin dizini.

*rString*<br/>
Alınacak metni içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Bölmenin metnini içeren bir `CString` nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin ikinci biçimi, bir `CString` nesneyi dize metniyle doldurur.

## <a name="cstatusbargetstatusbarctrl"></a><a name="getstatusbarctrl"></a>CStatusBar::GetStatusBarCtrl

Bu üye işlev, temel ortak denetime doğrudan erişim sağlar.

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) nesnesine bir başvuru içerir.

### <a name="remarks"></a>Açıklamalar

Windows `GetStatusBarCtrl` durum çubuğu ortak denetiminin işlevselliğinden yararlanmak ve [CStatusBarCtrl'nin](../../mfc/reference/cstatusbarctrl-class.md) durum çubuğu özelleştirmesi için sağladığı destekten yararlanmak için kullanın. Örneğin, ortak denetimi kullanarak, durum çubuğunda boyutlandırma kavraması içeren bir stil belirtebilir veya durum çubuğunun üst pencerenin istemci alanının üst kısmında görünmesi için bir stil belirtebilirsiniz.

Ortak denetimler hakkında daha genel bilgi için Windows SDK'daki [Ortak Denetimler'e](/windows/win32/Controls/common-controls-intro) bakın.

## <a name="cstatusbarsetindicators"></a><a name="setindicators"></a>CStatusBar::SetIndicators

Her göstergenin *kimliğini, lpIDArray*dizisinin ilgili öğesi tarafından belirtilen değere ayarlar, her kimlik tarafından belirtilen dize kaynağını yükler ve göstergemetnini dize ayarlar.

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parametreler

*lpIDArray*<br/>
Bir dizi ie'ye işaretçi.

*nIDSayısı*<br/>
*lpIDArray*tarafından işaret edilen dizideki öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="cstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a>CStatusBar::SetPaneInfo

Belirtilen gösterge bölmesini yeni bir kimlik, stil ve genişlik olarak ayarlar.

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Stili ayarlanacak gösterge bölmesinin dizini.

*Nıd*<br/>
Gösterge bölmesi için yeni kimlik.

*nStyle*<br/>
Gösterge bölmesi için yeni stil.

*cxGenişlik*<br/>
Gösterge bölmesi için yeni genişlik.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki gösterge stilleri desteklenir:

- SBPS_NOBORDERS bölmenin etrafında 3-D sınırı yok.

- SBPS_POPOUT ters kenarlık böylece metin "açılır."

- SBPS_DISABLED Metin çizmayın.

- kullanılmayan alanı doldurmak için SBPS_STRETCH Streç bölmesi. Durum çubuğu başına yalnızca bir bölme bu stili olabilir.

- SBPS_NORMAL Hiçbir esneme, kenarlıklar veya pop-out.

## <a name="cstatusbarsetpanestyle"></a><a name="setpanestyle"></a>CStatusBar::SetPaneStyle

Durum çubuğu bölmesinin stilini ayarlamak için bu üye işlevi arayın.

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Stili ayarlanacak bölmenin dizini.

*nStyle*<br/>
Stili ayarlanacak bölmenin stili.

### <a name="remarks"></a>Açıklamalar

Bölmenin stili bölmenin nasıl görüner belirler.

Durum çubukları için kullanılabilen stillerin listesi için [SetPaneInfo'ya](#setpaneinfo)bakın.

## <a name="cstatusbarsetpanetext"></a><a name="setpanetext"></a>CStatusBar::SetPaneText

Bölme metnini *lpszNewText*tarafından işaret edilen dize ayarlamak için bu üye işlevi arayın.

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Metni ayarlanacak bölmenin dizini.

*lpszNewText*<br/>
Yeni bölme metnini işaretçi.

*Bgüncelleştirme*<br/>
TRUE ise, metin ayarlandıktan sonra bölme geçersiz kılınz.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Aramadan `SetPaneText`sonra, durum çubuğundaki yeni metni görüntülemek için bir Kullanıcı Arabirimi güncelleştirme işleyicisi eklemeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStatusBarCtrl Sınıfı](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
