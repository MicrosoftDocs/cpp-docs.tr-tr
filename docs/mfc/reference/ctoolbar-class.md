---
title: Ctoolbar Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: fdbf343c91725783afd79bbebd73f66fdb1d67e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364290"
---
# <a name="ctoolbar-class"></a>Ctoolbar Sınıfı

Bir sıra biteşe düğmeleri ve isteğe bağlı ayırıcılar içeren denetim çubukları.

## <a name="syntax"></a>Sözdizimi

```
class CToolBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Ctoolbar::Ctoolbar](#ctoolbar)|Bir `CToolBar` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Ctoolbar::commandtoindex](#commandtoindex)|Verilen komut kimliğiyle bir düğmenin dizinini döndürür.|
|[Ctoolbar::Oluştur](#create)|Windows araç çubuğunu oluşturur ve `CToolBar` nesneye bağlar.|
|[Ctoolbar::Createex](#createex)|Katıştırılmış `CToolBar` `CToolBarCtrl` nesne için ek stiller içeren bir nesne oluşturur.|
|[CtoolBar::GetButtonInfo](#getbuttoninfo)|Bir düğmenin kimliğini, stilini ve görüntü numarasını alır.|
|[Ctoolbar::GetButtonStyle](#getbuttonstyle)|Düğmenin stilini alır.|
|[CtoolBar::GetButtonText](#getbuttontext)|Düğmede görünecek metni alır.|
|[CtoolBar::GetItemID](#getitemid)|Verilen dizinde bir düğmenin veya ayırıcının komut kimliğini verir.|
|[CToolBar::GetItemRect](#getitemrect)|Verilen dizindeki öğenin ekran dikdörtgenini alır.|
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|Altta yatan ortak denetime doğrudan erişim sağlar.|
|[CToolBar::LoadBitmap](#loadbitmap)|Bitmap düğmesi görüntüleri içeren bit eşlemi yükler.|
|[Ctoolbar::loadtoolbar](#loadtoolbar)|Kaynak düzenleyicisi ile oluşturulan bir araç çubuğu kaynağı yükler.|
|[CToolBar::SetBitmap](#setbitmap)|Biteşed görüntü ayarlar.|
|[CtoolBar::SetButtonInfo](#setbuttoninfo)|Bir düğmenin kimliğini, stilini ve görüntü numarasını ayarlar.|
|[CToolBar::SetButtons](#setbuttons)|Bit eşlemi içinde düğme stilleri ve düğme görüntülerinin dizini ayarlar.|
|[Ctoolbar::setbuttonstyle](#setbuttonstyle)|Düğme nin stilini ayarlar.|
|[Ctoolbar::SetButtonText](#setbuttontext)|Düğmede görünecek metni ayarlar.|
|[Ctoolbar::SetHeight](#setheight)|Araç çubuğunun yüksekliğini ayarlar.|
|[CToolBar::SetSizes](#setsizes)|Düğmelerin boyutlarını ve bit eşlemlerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Düğmeler düğmeler, onay kutusu düğmeleri veya radyo düğmeleri gibi davranabilir. `CToolBar`nesneler genellikle [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)sınıfından türetilen çerçeve penceresi nesnelerinin katıştirilmiş üyeleridir.

[CToolBar::GetToolBarCtrl](#gettoolbarctrl), MFC 4.0'a yeni bir üye işlev, araç çubuğu özelleştirme ve ek işlevsellik için Windows ortak denetiminin desteğinden yararlanmanızı sağlar. `CToolBar`üye işlevler, Windows ortak denetimlerinin işlevselliğinin çoğunu sağlar; ancak, aradiğinizde, `GetToolBarCtrl`araç çubuklarınıza Windows 95/98 araç çubuklarının özelliklerinden daha fazlasını verebilirsiniz. `GetToolBarCtrl`Aradiğinizde, bir `CToolBarCtrl` nesneye bir başvuru döndürecektir. Windows ortak denetimlerini kullanarak araç çubukları tasarlama hakkında daha fazla bilgi için [CToolBarCtrl'a](../../mfc/reference/ctoolbarctrl-class.md) bakın. Ortak denetimler hakkında daha genel bilgi için Windows SDK'daki [Ortak Denetimler'e](/windows/win32/Controls/common-controls-intro) bakın.

Visual C++ araç çubuğu oluşturmak için iki yöntem sağlar. Kaynak Düzenleyicisi'ni kullanarak bir araç çubuğu kaynağı oluşturmak için aşağıdaki adımları izleyin:

1. Araç çubuğu kaynağı oluşturun.

1. Nesneyi `CToolBar` oluştur.

1. Windows araç çubuğunu oluşturmak ve `CToolBar` nesneye takmak için [Oluştur](#create) (veya [CreateEx)](#createex)işlevini arayın.

1. Araç çubuğu kaynağını yüklemek için [LoadToolBar'ı](#loadtoolbar) arayın.

Erişemiyorsanız şu adımları uygulayın:

1. Nesneyi `CToolBar` oluştur.

1. Windows araç çubuğunu oluşturmak ve `CToolBar` nesneye takmak için [Oluştur](#create) (veya [CreateEx)](#createex)işlevini arayın.

1. Araç çubuğu düğmesi görüntülerini içeren bit eşlemeyi yüklemek için [LoadBitmap'i](#loadbitmap) arayın.

1. Düğme stilini ayarlamak için [SetButtons'ı](#setbuttons) arayın ve her düğmeyi bit haritasındaki bir resimle ilişkilendirin.

Araç çubuğundaki tüm düğme görüntüleri, her düğme için bir görüntü içermesi gereken bir bit eşlemden alınır. Tüm görüntüler aynı boyutta olmalıdır; varsayılan değer 16 piksel genişliğinde ve 15 piksel yüksektir. Resimler bit haritasında yan yana olmalıdır.

İşlev, `SetButtons` bir dizi denetim kimliklerine ve dizideki öğe sayısını belirten bir tamsayıya işaretçi alır. İşlev, her düğmenin kimliğini dizinin ilgili öğesinin değerine ayarlar ve her düğmeye bit haritasında düğmenin görüntüsünün konumunu belirten bir görüntü dizini atar. Bir dizi öğesi ID_SEPARATOR değerine sahipse, görüntü dizini atanmadı.

Bit eşlemdeki görüntülerin sırası genellikle ekranda çizilme sırasıdır, ancak görüntü sırası ile çizim sırası arasındaki ilişkiyi değiştirmek için [SetButtonInfo](#setbuttoninfo) işlevini kullanabilirsiniz.

Araç çubuğundaki tüm düğmeler aynı boyuttadır. Varsayılan yazılım *tasarımı için Windows Arabirim Yönergeleri*uyarınca, 24 x 22 pikseldir. Görüntü ve düğme boyutları arasında herhangi bir ek boşluk görüntü nün etrafında bir kenarlık oluşturmak için kullanılır.

Her düğmenin bir görüntüsü vardır. Çeşitli düğme durumları ve stilleri (basılı, yukarı, aşağı, devre dışı bırakılmış, devre dışı bırakılmış ve belirsiz) bu görüntüden oluşturulur. Biteşler herhangi bir renk olabilir, ancak siyah ve gri tonlarında görüntüler ile en iyi sonuçları elde edebilirsiniz.

> [!WARNING]
> `CToolBar`bit eşlemlerini en fazla 16 renkle destekler. Görüntüyü araç çubuğu düzenleyicisine yüklediğinizde, Visual Studio gerekirse görüntüyü otomatik olarak 16 renkli bit eşlene dönüştürür ve görüntü dönüştürüldüyse bir uyarı iletisi görüntüler. 16'dan fazla rengi olan bir görüntü kullanıyorsanız (görüntüyü düzenliletmek için harici bir düzenleyici kullanıyorsanız), uygulama beklenmedik şekilde hareket edebilir.

Araç çubuğu düğmeleri varsayılan olarak düğmeleri taklit eder. Ancak, araç çubuğu düğmeleri onay kutusu düğmelerini veya radyo düğmelerini de taklit edebilir. Onay kutusu düğmelerinin üç durum vardır: işaretli, temizlenmiş ve belirsiz. Radyo düğmelerinin yalnızca iki eyaleti vardır: kontrol edilmiş ve temizlenmiş.

Bir diziye işaret etmeden tek bir düğme veya ayırıcı stili ayarlamak için, stili almak için `SetButtons` [GetButtonStyle'ı](#getbuttonstyle) arayın ve ardından [setbuttonstyle'ı](#setbuttonstyle) çağırın. `SetButtonStyle`çalışma zamanında bir düğmenin stilini değiştirmek istediğinizde en kullanışlıdır.

Düğmede görünecek şekilde metin atamak için [GetButtonText'i](#getbuttontext) arayarak düğmede görünmesi için metni alın ve ardından metni ayarlamak için [SetButtonText'i](#setbuttontext) arayın.

Onay kutusu düğmesi oluşturmak için, stil TBBS_CHECKBOX atayın `CCmdUI` veya `SetCheck` bir nesnenin üye işlevini ON_UPDATE_COMMAND_UI işleyicisinde kullanın. Arama, `SetCheck` bir düğmeyi onay kutusu düğmesine dönüştürür. `SetCheck` Denetlenmemiş için 0 bağımsız değişkeni, kontrol edilen ler için 1 veya belirsiz için 2 bağımsız değişken geçirin.

Radyo düğmesi oluşturmak için, [ccmdUI](../../mfc/reference/ccmdui-class.md) nesnenin [SetRadio](../../mfc/reference/ccmdui-class.md#setradio) üye işlevini ON_UPDATE_COMMAND_UI bir işleyiciden arayın. Denetlenmemiş veya işaretlenmemiş olarak işaretlenmemiş için 0 bağımsız değişkenini geçirin. `SetRadio` Bir radyo grubunun birbirini dışlayan davranışını sağlamak için, gruptaki tüm düğmeler için ON_UPDATE_COMMAND_UI işleyiciniz olmalıdır.

Kullanma `CToolBar`hakkında daha fazla bilgi için, [makalem MFC Araç Çubuğu Uygulama](../../mfc/mfc-toolbar-implementation.md) ve Teknik Not [31 bakın: Denetim Çubukları](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Ccontrolbar](../../mfc/reference/ccontrolbar-class.md)

`CToolBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="ctoolbarcommandtoindex"></a><a name="commandtoindex"></a>Ctoolbar::commandtoindex

Bu üye işlev, komut kimliği eşleşen 0 konumundan başlayarak ilk `nIDFind`araç çubuğu düğmesinin dizini döndürür.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parametreler

*nIDFind*<br/>
Araç çubuğu düğmesinin komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Verilen komut kimliğine sahip değilse düğmenin dizini veya -1.

## <a name="ctoolbarcreate"></a><a name="create"></a>Ctoolbar::Oluştur

Bu üye işlev bir Windows araç çubuğu (alt pencere) `CToolBar` oluşturur ve nesneyle ilişkilendirir.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Araç çubuğunun üst öğesi olan pencereyi işaretçi.

*Dwstyle*<br/>
Araç çubuğu stili. Desteklenen ek araç çubuğu stilleri şunlardır:

- CBRS_TOP Denetim çubuğu çerçeve penceresinin en üstündedir.

- CBRS_BOTTOM Denetim çubuğu çerçeve penceresinin alt kısmındadır.

- CBRS_NOALIGN Denetim çubuğu, üst öğe yeniden boyutlandırıldığında yeniden konumlandırılmez.

- CBRS_TOOLTIPS Denetim çubuğu araç ipuçlarını görüntüler.

- CBRS_SIZE_DYNAMIC Kontrol çubuğu dinamiktir.

- CBRS_SIZE_FIXED Kontrol çubuğu sabittir.

- CBRS_FLOATING Kontrol çubuğu yüzer.

- CBRS_FLYBY Durum çubuğu düğme yle ilgili bilgileri görüntüler.

- CBRS_HIDE_INPLACE Denetim çubuğu kullanıcıya görüntülenmez.

*Nıd*<br/>
Araç çubuğunun alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca araç çubuğu yüksekliğini varsayılan değere ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]

## <a name="ctoolbarcreateex"></a><a name="createex"></a>Ctoolbar::Createex

Windows araç çubuğu (alt pencere) oluşturmak ve `CToolBar` nesneyle ilişkilendirmek için bu işlevi arayın.

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

*pParentWnd*<br/>
Araç çubuğunun üst öğesi olan pencereyi işaretçi.

*dwCtrlStyle*<br/>
Katıştırılmış [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) nesnesinin oluşturulması için ek stiller. Varsayılan olarak, bu değer TBSTYLE_FLAT olarak ayarlanır. Araç çubuğu stillerinin tam listesi için *dwStyle'a*bakın.

*Dwstyle*<br/>
Araç çubuğu stili. Uygun stillerin listesi için Windows SDK'daki [Araç Çubuğu Denetimi ve Düğme Stilleri'ne](/windows/win32/Controls/toolbar-control-and-button-styles) bakın.

*rcBorders*<br/>
Araç çubuğu penceresi kenarlıklarının genişliklerini tanımlayan bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi. Bu kenarlıklar varsayılan olarak 0,0,0,0 olarak ayarlanır ve bu da kenarlıksız bir araç çubuğu penceresiyle sonuçlanır.

*Nıd*<br/>
Araç çubuğunun alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca araç çubuğu yüksekliğini varsayılan değere ayarlar.

Katıştırılmış araç çubuğu denetiminin oluşturulması sırasında belirli stillerin bulunması gerektiğinde `CreateEx` [Oluştur](#create)yerine kullanın. Örneğin, *dwCtrlStyle'ı* TBSTYLE_FLAT &#124; TBSTYLE_TRANSPARENT internet gezgini 4 araç çubuklarına benzeyen bir araç çubuğu oluşturmak için ayarlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]

## <a name="ctoolbarctoolbar"></a><a name="ctoolbar"></a>Ctoolbar::Ctoolbar

Bu üye işlev `CToolBar` bir nesne oluşturuyor ve varsayılan boyutları ayarlar.

```
CToolBar();
```

### <a name="remarks"></a>Açıklamalar

Araç çubuğu penceresini oluşturmak için Üye [Oluştur](#create) işlevini çağırın.

## <a name="ctoolbargetbuttoninfo"></a><a name="getbuttoninfo"></a>CtoolBar::GetButtonInfo

Bu üye işlev, nIndex tarafından belirtilen konumda araç çubuğu düğmesinin veya ayırıcının denetim kimliğini, stilini ve görüntü dizini *alır.*

```
void GetButtonInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& iImage) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Araç çubuğu düğmesinin veya bilgilerinin alınacak olan ayırıcısının dizini.

*Nıd*<br/>
Düğmenin komut kimliğine ayarlanmış bir UINT'ye başvuru.

*nStyle*<br/>
Düğmenin stiline ayarlanmış bir UINT'ye başvuru.

*ıımage*<br/>
Biteş içindeki düğmenin görüntüsünün dizinine ayarlanmış bir aramaya başvuru.

### <a name="remarks"></a>Açıklamalar

Bu değerler *nID*, *nStyle*ve *iImage*tarafından başvurulan değişkenlere atanır. Görüntü dizini, görüntünün tüm araç çubuğu düğmeleri için görüntü içeren bit eşlem içindeki konumudur. İlk görüntü 0 pozisyonundadır.

*nIndex* bir ayırıcı belirtirse, *iImage* piksel ayırıcı genişlik ayarlanır.

## <a name="ctoolbargetbuttonstyle"></a><a name="getbuttonstyle"></a>Ctoolbar::GetButtonStyle

Araç çubuğundaki bir düğme veya ayırıcının stilini almak için bu üye işlevi arayın.

```
UINT GetButtonStyle(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Alınacak araç çubuğu düğmesinin veya ayırıcı stilinin dizini.

### <a name="return-value"></a>Dönüş Değeri

*nIndex*tarafından belirtilen düğme veya ayırıcının stili.

### <a name="remarks"></a>Açıklamalar

Düğmenin stili, düğmenin nasıl görünüp kullanıcı girişine nasıl yanıt veriyi belirler. Düğme stilleri örnekleri için [SetButtonStyle'a](#setbuttonstyle) bakın.

## <a name="ctoolbargetbuttontext"></a><a name="getbuttontext"></a>CtoolBar::GetButtonText

Düğmede görünen metni almak için bu üye işlevi arayın.

```
CString GetButtonText(int nIndex) const;

void GetButtonText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Alınacak metnin dizini.

*rString*<br/>
Alınacak metni içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Düğme `CString` metnini içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin ikinci biçimi, bir `CString` nesneyi dize metniyle doldurur.

## <a name="ctoolbargetitemid"></a><a name="getitemid"></a>CtoolBar::GetItemID

Bu üye işlev, *nIndex*tarafından belirtilen düğme veya ayırıcının komut kimliğini döndürür.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Kimliği alınacak öğenin dizin.

### <a name="return-value"></a>Dönüş Değeri

*nIndex*tarafından belirtilen düğme veya ayırıcının komut kimliği.

### <a name="remarks"></a>Açıklamalar

Ayırıcılar ID_SEPARATOR dönerler.

## <a name="ctoolbargetitemrect"></a><a name="getitemrect"></a>CToolBar::GetItemRect

Bu üye işlev, `RECT` adresi *lpRect'te* bulunan yapıyı *nIndex*tarafından belirtilen düğme veya ayırıcıkoordinatları ile doldurur.

```
virtual void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Dikdörtgen koordinatları alınacak öğenin (düğme veya ayırıcı) dizini.

*Lprect*<br/>
Öğenin koordinatlarını içerecek [RECT](/windows/win32/api/windef/ns-windef-rect) yapısının adresi.

### <a name="remarks"></a>Açıklamalar

Koordinatlar, araç çubuğunun sol üst köşesine göre piksel olarak dır.

Bir `GetItemRect` açılan kutu veya başka bir denetim ile değiştirmek istediğiniz bir ayırıcı koordinatları almak için kullanın.

### <a name="example"></a>Örnek

  CToolBar örneğine [bakın:SetSizes](#setsizes).

## <a name="ctoolbargettoolbarctrl"></a><a name="gettoolbarctrl"></a>CToolBar::GetToolBarCtrl

Bu üye işlev, temel ortak denetime doğrudan erişim sağlar.

```
CToolBarCtrl& GetToolBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CToolBarCtrl` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Windows `GetToolBarCtrl` araç çubuğu ortak denetiminin işlevselliğinden yararlanmak ve [CToolBarCtrl'nin](../../mfc/reference/ctoolbarctrl-class.md) araç çubuğu özelleştirmesi için sağladığı destekten yararlanmak için kullanın.

Ortak denetimleri kullanma hakkında daha fazla bilgi için Windows SDK'daki [Denetimler](../../mfc/controls-mfc.md) ve [Ortak Denetimler](/windows/win32/Controls/common-controls-intro) makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]

## <a name="ctoolbarloadbitmap"></a><a name="loadbitmap"></a>CToolBar::LoadBitmap

Tarafından belirtilen bit eşlemi `lpszResourceName` yüklemek `nIDResource`için bu üye işlevi arayın veya .

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Yüklenecek bit eşleminin kaynak adına işaretçi.

*nIDKaynak*<br/>
Yüklenecek bit eşliğinin kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bit eşlemi, her araç çubuğu düğmesi için bir görüntü içermelidir. Görüntüler standart boyutta değilse (16 piksel genişliğinde ve 15 piksel yüksekliğinde), düğme boyutlarını ve görüntülerini ayarlamak için [SetSizes'ı](#setsizes) arayın.

> [!WARNING]
> `CToolBar`bit eşlemlerini en fazla 16 renkle destekler. Görüntüyü araç çubuğu düzenleyicisine yüklediğinizde, Visual Studio gerekirse görüntüyü otomatik olarak 16 renkli bit eşlene dönüştürür ve görüntü dönüştürüldüyse bir uyarı iletisi görüntüler. 16'dan fazla rengi olan bir görüntü kullanıyorsanız (görüntüyü düzenliletmek için harici bir düzenleyici kullanıyorsanız), uygulama beklenmedik şekilde hareket edebilir.

## <a name="ctoolbarloadtoolbar"></a><a name="loadtoolbar"></a>Ctoolbar::loadtoolbar

*lpszResourceName* veya *nIDResource*tarafından belirtilen araç çubuğunu yüklemek için bu üye işlevini arayın.

```
BOOL LoadToolBar(LPCTSTR lpszResourceName);
BOOL LoadToolBar(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Yüklenecek araç çubuğunun kaynak adına işaretçi.

*nIDKaynak*<br/>
Yüklenecek araç çubuğunun kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Araç çubuğu kaynağı oluşturma hakkında daha fazla bilgi için [araç çubuğu düzenleyicisi](../../windows/toolbar-editor.md) ile ilgili bakın.

### <a name="example"></a>Örnek

  CToolBar örneğine [bakın:CreateEx](#createex).

## <a name="ctoolbarsetbitmap"></a><a name="setbitmap"></a>CToolBar::SetBitmap

Araç çubuğunun biteş görüntüsünü ayarlamak için bu üye işlevi arayın.

```
BOOL SetBitmap(HBITMAP hbmImageWell);
```

### <a name="parameters"></a>Parametreler

*hbmImageWell*<br/>
Araç çubuğuyla ilişkili bir bitmap görüntüsünün tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Örneğin, kullanıcı `SetBitmap` bir düğmenin eylemini değiştiren bir belge üzerinde işlem yaptıktan sonra biteşe görüntüyü değiştirmek için çağrıda bulunma.

## <a name="ctoolbarsetbuttoninfo"></a><a name="setbuttoninfo"></a>CtoolBar::SetButtonInfo

Düğmenin komut kimliğini, stilini ve resim numarasını ayarlamak için bu üye işlevini arayın.

```
void SetButtonInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int iImage);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Bilginin ayarlanabilmek için düğme veya ayırıcının sıfır tabanlı dizini.

*Nıd*<br/>
Düğmenin komut kimliğinin ayarlandığı değer.

*nStyle*<br/>
Yeni düğme stili. Aşağıdaki düğme stilleri desteklenir:

- TBBS_BUTTON Standart buton (varsayılan)

- TBBS_SEPARATOR Ayırıcı

- TBBS_CHECKBOX Otomatik onay kutusu düğmesi

- TBBS_GROUP Bir düğme grubunun başlangıcını işaretler

- TBBS_CHECKGROUP Onay kutusu düğmeleri grubunun başlangıcını işaretler

- TBBS_DROPDOWN Açılır liste düğmesi oluşturur.

- TBBS_AUTOSIZE Düğmenin genişliği, görüntünün boyutuna değil, düğmenin metnine göre hesaplanır.

- TBBS_NOPREFIX Düğme metninde hızlandırıcı öneki olmayacaktır.

*ıımage*<br/>
Biteş içindeki düğmenin görüntüsü için yeni dizin.

### <a name="remarks"></a>Açıklamalar

Stil TBBS_SEPARATOR olan ayırıcılar için bu işlev, ayırıcının piksel genişliğinin *iImage'de*depolanan değere göre ayarlandığı bir durumdur.

> [!NOTE]
> Ayrıca *nStyle* parametresini kullanarak düğme durumlarını ayarlayabilirsiniz; ancak, düğme durumları [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) işleyicisi tarafından denetlendiği `SetButtonInfo` için, kullandığınız herhangi bir durum sonraki boşta işleme sırasında kaybolur. Bkz. Kullanıcı Arabirimi Nesneleri ve [TN031](../../mfc/tn031-control-bars.md) [Nasıl Güncellenir:](../../mfc/how-to-update-user-interface-objects.md) Daha fazla bilgi için Çubukları Denetleme.

Bitmap görüntüleri ve düğmeleri hakkında bilgi için [CToolBar](../../mfc/reference/ctoolbar-class.md) Genel Bakış ve [CToolBar::LoadBitmap'e](#loadbitmap)bakın.

## <a name="ctoolbarsetbuttons"></a><a name="setbuttons"></a>CToolBar::SetButtons

Bu üye işlev, her araç çubuğu düğmesinin komut kimliğini *lpIDArray*dizisinin ilgili öğesi tarafından belirtilen değere ayarlar.

```
BOOL SetButtons(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parametreler

*lpIDArray*<br/>
Komut Kimlikleri dizisiiçin işaretçi. Boş düğmeleri ayırmak NULL olabilir.

*nIDSayısı*<br/>
*lpIDArray*tarafından işaret edilen dizideki öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Dizinin bir öğesi ID_SEPARATOR değerine sahipse, araç çubuğunun karşılık gelen konumunda bir ayırıcı oluşturulur. Bu işlev ayrıca her düğmenin stilini TBBS_BUTTON ve her ayırıcının stilini TBBS_SEPARATOR olarak ayarlar ve her düğmeye bir görüntü dizini atar. Görüntü dizini, düğmenin görüntüsünün bit eşlem içindeki konumunu belirtir.

Bu işlev ayırıcılar için görüntü dizinleri atamaydığından, bit eşlemdeki ayırıcıları hesaba katmanız gerekmez. Araç çubuğunuzda 0, 1 ve 3 pozisyonlarında düğmeler ve 2.

*LPIDArray* NULL ise, bu işlev *nIDCount*tarafından belirtilen öğe sayısı için alan ayırır. Her öğenin özniteliklerini ayarlamak için [SetButtonInfo'u](#setbuttoninfo) kullanın.

## <a name="ctoolbarsetbuttonstyle"></a><a name="setbuttonstyle"></a>Ctoolbar::setbuttonstyle

Bir düğme veya ayırıcının stilini ayarlamak veya düğmeleri gruplandırmak için bu üye işlevi arayın.

```
void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Bilgileri ayarlanacak düğme veya ayırıcının dizin.

*nStyle*<br/>
Düğme stili. Aşağıdaki düğme stilleri desteklenir:

- TBBS_BUTTON Standart buton (varsayılan)

- TBBS_SEPARATOR Ayırıcı

- TBBS_CHECKBOX Otomatik onay kutusu düğmesi

- TBBS_GROUP Bir düğme grubunun başlangıcını işaretler

- TBBS_CHECKGROUP Onay kutusu düğmeleri grubunun başlangıcını işaretler

- TBBS_DROPDOWN Açılır liste düğmesi oluşturur

- TBBS_AUTOSIZE Düğmenin genişliği, görüntünün boyutuna değil, düğmenin metnine göre hesaplanır

- TBBS_NOPREFIX Düğme metninde hızlandırıcı öneki olmayacak

### <a name="remarks"></a>Açıklamalar

Düğmenin stili, düğmenin nasıl görünüp kullanıcı girişine nasıl yanıt veriyi belirler.

Aramadan `SetButtonStyle`önce, düğmeyi veya ayırıcı stili almak için [GetButtonStyle](#getbuttonstyle) üye işlevini arayın.

> [!NOTE]
> Ayrıca *nStyle* parametresini kullanarak düğme durumlarını ayarlayabilirsiniz; ancak, düğme durumları [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) işleyicisi tarafından denetlendiği `SetButtonStyle` için, kullandığınız herhangi bir durum sonraki boşta işleme sırasında kaybolur. Bkz. Kullanıcı Arabirimi Nesneleri ve [TN031](../../mfc/tn031-control-bars.md) [Nasıl Güncellenir:](../../mfc/how-to-update-user-interface-objects.md) Daha fazla bilgi için Çubukları Denetleme.

## <a name="ctoolbarsetbuttontext"></a><a name="setbuttontext"></a>Ctoolbar::SetButtonText

Metni bir düğmeye ayarlamak için bu işlevi arayın.

```
BOOL SetButtonText(
    int nIndex,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Metni ayarlanacak düğmenin dizin.

*lpszMetin*<br/>
Bir düğmeye ayarlanacak metne işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

  CToolBar örneğine [bakın:GetToolBarCtrl](#gettoolbarctrl).

## <a name="ctoolbarsetheight"></a><a name="setheight"></a>Ctoolbar::SetHeight

Bu üye işlev, araç çubuğunun yüksekliğini *cyHeight'da*belirtilen pikselcinsinden değere ayarlar.

```
void SetHeight(int cyHeight);
```

### <a name="parameters"></a>Parametreler

*cyYükseklik*<br/>
Araç çubuğunun piksel yüksekliği.

### <a name="remarks"></a>Açıklamalar

[SetSizes'ı](#setsizes)aradıktan sonra, standart araç çubuğu yüksekliğini geçersiz kılmak için bu üye işlevi kullanın. Yükseklik çok küçükse, düğmeler alt kısımdan kırpılır.

Bu işlev çağrılmazsa, çerçeve araç çubuğu yüksekliğini belirlemek için düğmenin boyutunu kullanır.

## <a name="ctoolbarsetsizes"></a><a name="setsizes"></a>CToolBar::SetSizes

Araç çubuğunun düğmelerini *boyutolarak, boyut Düğme'de*belirtilen piksellere ayarlamak için bu üye işlevini arayın.

```
void SetSizes(
    SIZE sizeButton,
    SIZE sizeImage);
```

### <a name="parameters"></a>Parametreler

*boyutDüğme*<br/>
Her düğmenin piksel boyutu.

*boyutGörüntü*<br/>
Her görüntünün piksel boyutu.

### <a name="remarks"></a>Açıklamalar

*SizeImage* parametresi, araç çubuğunun bit haritasındaki görüntülerin piksel boyutuna içermelidir. *BoyutDüğme'deki* boyutlar görüntüyü tutmak için yeterli olmalı artı 7 piksel genişliğinde ekstra ve 6 piksel ekstra yükseklikte. Bu işlev, düğmelere uyacak şekilde araç çubuğu yüksekliğini de ayarlar.

Bu üye işlevini yalnızca düğme ve görüntü boyutları için Yazılım Tasarımı önerileri *için Windows Arabirim Yönergeleri'ne* uymayan araç çubukları için arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl Sınıfı](../../mfc/reference/ctoolbarctrl-class.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
