---
title: CStatusBar sınıfı
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
ms.openlocfilehash: 48de31d95814ce5fc1fb015e69cf38d73337cb79
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502332"
---
# <a name="cstatusbar-class"></a>CStatusBar sınıfı

Metin çıkış bölmeleri veya "göstergeler" satırı içeren bir denetim çubuğu.

## <a name="syntax"></a>Sözdizimi

```
class CStatusBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStatusBar:: CStatusBar](#cstatusbar)|Bir `CStatusBar` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStatusBar:: CommandToIndex](#commandtoindex)|Verilen bir gösterge KIMLIĞI için dizini alır.|
|[CStatusBar:: Create](#create)|Durum çubuğunu oluşturur, `CStatusBar` nesnesine iliştirir ve ilk yazı tipi ve çubuk yüksekliğini ayarlar.|
|[CStatusBar:: CreateEx](#createex)|`CStatusBar` Katıştırılmış`CStatusBarCtrl` nesne için ek stillere sahip bir nesne oluşturur.|
|[CStatusBar::D rawItem](#drawitem)|Sahip çizimi bir durum çubuğu denetiminin görsel bir yönü değiştiğinde çağırılır.|
|[CStatusBar:: GetItemID](#getitemid)|Belirli bir dizin için gösterge KIMLIĞINI alır.|
|[CStatusBar:: GetItemRect](#getitemrect)|Belirli bir dizin için görüntüleme dikdörtgeni alır.|
|[CStatusBar:: Getbölmesi bilgileri](#getpaneinfo)|Belirli bir dizin için gösterge KIMLIĞINI, stili ve genişliği alır.|
|[CStatusBar:: Getbölmesi stili](#getpanestyle)|Belirli bir dizin için gösterge stilini alır.|
|[CStatusBar:: Getbölmesi metni](#getpanetext)|Belirli bir dizin için gösterge metnini alır.|
|[CStatusBar:: GetStatusBarCtrl](#getstatusbarctrl)|Temel alınan ortak denetime doğrudan erişim sağlar.|
|[CStatusBar:: SetIndicators](#setindicators)|Gösterge kimliklerini ayarlar.|
|[CStatusBar:: Setbölmesi bilgileri](#setpaneinfo)|Belirli bir dizin için gösterge KIMLIĞINI, stili ve genişliği ayarlar.|
|[CStatusBar:: Setbölmesi stili](#setpanestyle)|Belirli bir dizin için gösterge stilini ayarlar.|
|[CStatusBar:: Setbölmesi metni](#setpanetext)|Belirli bir dizin için gösterge metnini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Çıkış bölmeleri genellikle ileti satırları ve durum göstergeleri olarak kullanılır. Örnek olarak, seçilen menü komutu ve SCROLL LOCK, NUM LOCK ve diğer anahtarların durumunu gösteren göstergeler kısaca açıklayan menü yardım-ileti satırları bulunur.

MFC 4,0 ' ye yeni bir üye işlevi olan [CStatusBar:: GetStatusBarCtrl](#getstatusbarctrl), durum çubuğu özelleştirmesi ve ek Işlevler için Windows ortak denetim desteğinden yararlanmanızı sağlar. `CStatusBar`üye işlevleri, Windows ortak denetimleri işlevlerinin çoğunu sağlar; Ancak, öğesini çağırdığınızda `GetStatusBarCtrl`, bir Windows 95/98 durum çubuğunun özelliklerine daha fazla sahip olmak üzere durum çubuklarınızı da verebilirsiniz. Öğesini çağırdığınızda `GetStatusBarCtrl`, bir `CStatusBarCtrl` nesnesine bir başvuru döndürür. Windows ortak denetimleri kullanarak araç çubukları tasarlama hakkında daha fazla bilgi için bkz. [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) . Ortak denetimler hakkında daha fazla genel bilgi için bkz. Windows SDK [ortak denetimleri](/windows/win32/Controls/common-controls-intro) .

Çerçeve, gösterge bilgilerini 0 konumunda en soldaki göstergeyi içeren bir dizide depolar. Bir durum çubuğu oluşturduğunuzda, Framework 'ün ilgili göstergeler ile ilişkilendiğini belirten bir dize kimlikleri dizisi kullanırsınız. Daha sonra, bir göstergeye erişmek için bir dize KIMLIĞI veya dizin kullanabilirsiniz.

Varsayılan olarak, ilk gösterge "elastik" dır: diğer bölmeler doğru hizalı olacak şekilde diğer gösterge bölmeleri tarafından kullanılmayan durum çubuğu uzunluğunu kaplar.

Bir durum çubuğu oluşturmak için aşağıdaki adımları izleyin:

1. `CStatusBar` Nesnesini oluşturun.

1. Durum çubuğu penceresini oluşturmak ve `CStatusBar` nesneye iliştirmek için [Create](#create) (veya [CreateEx](#createex)) işlevini çağırın.

1. Bir dize KIMLIĞINI her göstergeyle ilişkilendirmek için [Setgöstergelerini](#setindicators) çağırın.

Durum çubuğu bölmesindeki metni güncelleştirmenin üç yolu vardır:

1. Yalnızca 0 bölmesindeki metni güncelleştirmek için [CWnd:: SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) öğesini çağırın.

1. Durum çubuğunun ON_UPDATE_COMMAND_UI işleyicisinde [CCmdUI:: SetText](../../mfc/reference/ccmdui-class.md#settext) öğesini çağırın.

1. Herhangi bir bölmenin metnini güncelleştirmek için [Setpane metnini](#setpanetext) çağırın.

Bir durum çubuğu bölmesinin stilini güncelleştirmek için [Setpane stilini](#setpanestyle) çağırın.

Kullanma `CStatusBar`hakkında daha fazla bilgi için bkz. [MFC 'de durum çubuğu uygulama](../../mfc/status-bar-implementation-in-mfc.md) ve [teknik Not31: Denetim Çubukları](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

##  <a name="commandtoindex"></a>CStatusBar:: CommandToIndex

Verilen bir KIMLIK için gösterge dizinini alır.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parametreler

*Nıdfind*<br/>
Dizini alınacak göstergenin dize KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa göstergenin dizini; başarısız değilse-1.

### <a name="remarks"></a>Açıklamalar

İlk göstergenin dizini 0 ' dır.

##  <a name="create"></a>CStatusBar:: Create

Bir durum çubuğu (alt pencere) oluşturur ve `CStatusBar` nesneyle ilişkilendirir.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Windows penceresi durum çubuğunun üst öğesi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik işaretçi.

*dwStyle*<br/>
Durum çubuğu stili. Standart Windows [stillerinin](../../mfc/reference/styles-used-by-mfc.md#window-styles)yanı sıra bu stiller de desteklenir.

- CBRS_TOP denetim çubuğu, çerçeve penceresinin en üstünde.

- CBRS_BOTTOM denetim çubuğu, çerçeve penceresinin en altında.

- Üst yeniden boyutlandırıldığında CBRS_NOALIGN denetim çubuğu yeniden konumlandırılmaz.

*NID*<br/>
Araç çubuğunun alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca, başlangıç yazı tipini ayarlar ve durum çubuğunun yüksekliğini varsayılan bir değere ayarlar.

##  <a name="createex"></a>CStatusBar:: CreateEx

Bir durum çubuğu (bir alt pencere) oluşturmak ve bunu `CStatusBar` nesnesiyle ilişkilendirmek için bu işlevi çağırın.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Windows penceresi durum çubuğunun üst öğesi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik işaretçi.

*dwCtrlStyle*<br/>
Katıştırılmış [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) nesnesinin oluşturulmasına yönelik ek stiller. Varsayılan değer, boyutlandırma tutamacı veya araç ipucu desteği olmadan bir durum çubuğu belirtir. Desteklenen durum çubuğu stilleri şunlardır:

- SBARS_SIZEGRIP durum çubuğu denetimi durum çubuğunun sağ ucunda bir boyutlandırma tutamacı içerir. Boyutlandırma tutamacı boyutlandırma kenarlığına benzerdir; Bu, kullanıcının üst pencereyi yeniden boyutlandırmak için tıklave sürükleyebilmesini sağlayan dikdörtgen bir alandır.

- SBT_TOOLTIPS durum çubuğu araç ipuçlarını destekler.

Bu stillerle ilgili ayrıntılar için bkz. [CStatusBarCtrl Settings](../../mfc/settings-for-the-cstatusbarctrl.md).

*dwStyle*<br/>
Durum çubuğu stili. Varsayılan değer, çerçeve penceresinin alt kısmında görünür bir durum çubuğunun oluşturulacağını belirtir. [Windows stillerinde](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [CDialogBar:: Create](../../mfc/reference/cdialogbar-class.md#create)' de listelenen tüm durum çubuğu denetim stillerinin birleşimini uygulayın. Ancak, bu parametre her zaman WS_CHILD ve WS_VISIBLE stillerini içermelidir.

*NID*<br/>
Durum çubuğunun alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, başlangıç yazı tipini de ayarlar ve durum çubuğunun yüksekliğini varsayılan bir değere ayarlar.

Katıştırılmış `CreateEx`durum çubuğu denetiminin oluşturulması sırasında belirli stillerin bulunması gereken durumlarda, [Oluştur](#create)yerine kullanın. Örneğin, araç ipuçlarını bir durum çubuğu nesnesinde göstermek için *dwCtrlStyle* olarak ayarlayın.

##  <a name="cstatusbar"></a>CStatusBar:: CStatusBar

Bir `CStatusBar` nesne oluşturur, gerekirse varsayılan bir durum çubuğu yazı tipi oluşturur ve yazı tipi özelliklerini varsayılan değerlere ayarlar.

```
CStatusBar();
```

##  <a name="drawitem"></a>CStatusBar::D rawItem

Bu üye işlevi, sahip tarafından çizilmiş bir durum çubuğunun görsel bir yönü değiştiğinde Framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`DRAWITEMSTRUCT` Yapının üyesi gerçekleştirilecek çizim eylemini tanımlar. `itemAction` Bir sahip çizim `CStatusBar` nesnesi için çizimi uygulamak üzere bu üye işlevini geçersiz kılın. Uygulamanın, bu üye işlevin sonlandırılması için *Lpdrawitemstruct* içinde sağlanan görüntüleme bağlamı için seçilen tüm grafik cihaz ARABIRIMI (GDI) nesnelerini geri yüklemesi gerekir.

##  <a name="getitemid"></a>CStatusBar:: GetItemID

*Nindex*tarafından BELIRTILEN göstergenin kimliğini döndürür.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
KIMLIĞI alınacak olan göstergenin dizini.

### <a name="return-value"></a>Dönüş Değeri

*NIndex*tarafından BELIRTILEN göstergenin kimliği.

##  <a name="getitemrect"></a>CStatusBar:: GetItemRect

*NIndex* tarafından belirtilen göstergenin koordinatlarını, *lpRect*tarafından işaret edilen yapıya kopyalar.

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Dikdörtgen koordinatları alınacak olan göstergenin dizini.

*lpRect*<br/>
Bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına veya *nIndex*tarafından belirtilen göstergenin koordinatlarını alacak bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

Koordinatlar durum çubuğunun sol üst köşesine göre piksel cinsinden görüntülenir.

##  <a name="getpaneinfo"></a>CStatusBar:: Getbölmesi bilgileri

*NID*, *nStyle*ve *Cxwidth* ' i, nIndex tarafından belirtilen konumdaki gösterge bölmesinin kimliği, stili ve genişliğine göre ayarlar.

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Bilgileri alınacak olan bölmenin dizini.

*NID*<br/>
Bölmenin KIMLIĞI olarak ayarlanan bir UINT öğesine başvuru.

*nStyle*<br/>
Bölmenin stiline ayarlanan bir UINT öğesine başvuru.

*cxWidth*<br/>
Bölmenin genişliğine ayarlanmış bir tamsayıya başvuru.

##  <a name="getpanestyle"></a>CStatusBar:: Getbölmesi stili

Bir durum çubuğu bölmesinin stilini almak için bu üye işlevini çağırın.

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Stili alınacak olan bölmenin dizini.

### <a name="return-value"></a>Dönüş Değeri

*NIndex*tarafından belirtilen durum çubuğu bölmesinin stili.

### <a name="remarks"></a>Açıklamalar

Bölmenin stili bölmenin nasıl göründüğünü belirler.

Durum çubukları için kullanılabilen stillerin bir listesi için bkz. [Oluştur](#create).

##  <a name="getpanetext"></a>CStatusBar:: Getbölmesi metni

Bir durum çubuğu bölmesinde görünen metni almak için bu üye işlevini çağırın.

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Metni alınacak olan bölmenin dizini.

*rString*<br/>
Alınacak metni içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Bölmenin metnini içeren nesne. `CString`

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin ikinci formu, bir `CString` nesneyi dize metniyle doldurur.

##  <a name="getstatusbarctrl"></a>CStatusBar:: GetStatusBarCtrl

Bu üye işlevi, temel alınan ortak denetime doğrudan erişim sağlar.

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) nesnesine bir başvuru içerir.

### <a name="remarks"></a>Açıklamalar

Windows `GetStatusBarCtrl` durum çubuğu ortak denetiminin işlevselliğinin avantajlarından yararlanmak ve [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) desteğinin avantajlarından yararlanmak için, durum çubuğu özelleştirmesi için kullanın. Örneğin, ortak denetimi kullanarak durum çubuğunda boyutlandırma tutamacı içeren bir stil belirtebilir veya durum çubuğunun üst pencerenin istemci alanının en üstünde görünmesini sağlamak için bir stil belirtebilirsiniz.

Ortak denetimler hakkında daha fazla genel bilgi için bkz. Windows SDK [ortak denetimleri](/windows/win32/Controls/common-controls-intro) .

##  <a name="setindicators"></a>CStatusBar:: SetIndicators

Her bir göstergenin KIMLIĞINI dizi *lpIDArray*karşılık gelen öğesi tarafından belirtilen değere ayarlar, her kimlik tarafından belirtilen dize kaynağını yükler ve göstergenin metnini dizeye ayarlar.

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parametreler

*lpIDArray*<br/>
Bir kimlik dizisine yönelik işaretçi.

*nIDCount*<br/>
Dizide *lpIDArray*tarafından işaret edilen öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

##  <a name="setpaneinfo"></a>CStatusBar:: Setbölmesi bilgileri

Belirtilen gösterge bölmesini yeni bir KIMLIĞE, stile ve genişliğe ayarlar.

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Stili ayarlanacak gösterge bölmesinin dizini.

*NID*<br/>
Gösterge bölmesi için yeni KIMLIK.

*nStyle*<br/>
Gösterge bölmesi için yeni stil.

*cxWidth*<br/>
Gösterge bölmesi için yeni Genişlik.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki gösterge stilleri desteklenir:

- Bölmenin etrafında 3-D kenarlığı SBPS_NOBORDERS.

- Metnin "açılan" SBPS_POPOUT için ters kenarlık.

- SBPS_DISABLED metin çizmeyin.

- Kullanılmayan alanı dolduracak SBPS_STRETCH uzat bölmesi. Durum çubuğu başına yalnızca bir bölme Bu stile sahip olabilir.

- Esnetme, kenarlık veya açılan SBPS_NORMAL.

##  <a name="setpanestyle"></a>CStatusBar:: Setbölmesi stili

Bir durum çubuğu bölmesinin stilini ayarlamak için bu üye işlevini çağırın.

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Stili ayarlanacak olan bölmenin dizini.

*nStyle*<br/>
Stili ayarlanacak olan bölmenin stili.

### <a name="remarks"></a>Açıklamalar

Bölmenin stili bölmenin nasıl göründüğünü belirler.

Durum çubuklarının mevcut stillerin bir listesi için bkz. [Setbölmesi bilgileri](#setpaneinfo).

##  <a name="setpanetext"></a>CStatusBar:: Setbölmesi metni

Bölme metnini *lpszNewText*tarafından işaret edilen dizeye ayarlamak için bu üye işlevini çağırın.

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Metni ayarlanacak bölmenin dizini.

*lpszNewText*<br/>
Yeni bölme metnine yönelik işaretçi.

*Macrovision*<br/>
TRUE olarak ayarlanırsa, metin ayarlandıktan sonra bölme geçersiz kılınır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

' İ çağırdığınızda `SetPaneText`, durum çubuğunda yeni metni göstermek için bir UI güncelleştirme işleyicisi eklemeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStatusBarCtrl Sınıfı](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
