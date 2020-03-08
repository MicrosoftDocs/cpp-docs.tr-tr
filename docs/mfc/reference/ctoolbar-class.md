---
title: CToolBar sınıfı
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
ms.openlocfilehash: 4977cbe0b749724f999d6d7089d46f12d1e2963e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866454"
---
# <a name="ctoolbar-class"></a>CToolBar sınıfı

Bit eşlenmiş düğmelerin ve isteğe bağlı ayırıcıların bulunduğu denetim çubukları.

## <a name="syntax"></a>Sözdizimi

```
class CToolBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CToolBar:: CToolBar](#ctoolbar)|`CToolBar` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CToolBar:: Commandtoındex](#commandtoindex)|Verilen komut KIMLIKLI bir düğmenin dizinini döndürür.|
|[CToolBar:: Create](#create)|Windows araç çubuğunu oluşturur ve `CToolBar` nesnesine iliştirir.|
|[CToolBar:: CreateEx](#createex)|Katıştırılmış `CToolBarCtrl` nesnesi için ek stillerle `CToolBar` nesnesi oluşturur.|
|[CToolBar:: GetButtonInfo](#getbuttoninfo)|Bir düğmenin KIMLIĞINI, stilini ve resim numarasını alır.|
|[CToolBar:: GetButtonStyle](#getbuttonstyle)|Bir düğmenin stilini alır.|
|[CToolBar:: GetButtonText](#getbuttontext)|Bir düğme üzerinde görünecek metni alır.|
|[CToolBar:: GetItemID](#getitemid)|Verilen dizindeki bir düğmenin veya ayırıcının komut KIMLIĞINI döndürür.|
|[CToolBar:: GetItemRect](#getitemrect)|Verilen dizindeki öğe için görüntüleme dikdörtgenini alır.|
|[CToolBar:: GetToolBarCtrl](#gettoolbarctrl)|Temel alınan ortak denetime doğrudan erişim sağlar.|
|[CToolBar:: LoadBitmap](#loadbitmap)|Bit eşlem düğmesi görüntüleri içeren bit eşlemi yükler.|
|[CToolBar:: LoadToolBar](#loadtoolbar)|Kaynak Düzenleyicisi ile oluşturulan bir araç çubuğu kaynağını yükler.|
|[CToolBar:: SetBit eşlem](#setbitmap)|Bit eşlemeli bir görüntü ayarlar.|
|[CToolBar:: SetButtonInfo](#setbuttoninfo)|Bir düğmenin KIMLIĞINI, stilini ve resim numarasını ayarlar.|
|[CToolBar:: SetButtons](#setbuttons)|Düğme stillerini ve bit eşlem içindeki düğme görüntülerinin dizinini ayarlar.|
|[CToolBar:: SetButtonStyle](#setbuttonstyle)|Bir düğmenin stilini ayarlar.|
|[CToolBar:: SetButtonText](#setbuttontext)|Bir düğme üzerinde görünecek metni ayarlar.|
|[CToolBar:: SetHeight](#setheight)|Araç çubuğunun yüksekliğini ayarlar.|
|[CToolBar:: Setboyutlar](#setsizes)|Düğmelerin ve bit eşlemlerinin boyutlarını ayarlar.|

## <a name="remarks"></a>Açıklamalar

Düğmeler, pushbuttons, onay kutusu düğmeleri veya radyo düğmeleri gibi davranabilir. `CToolBar` nesneler genellikle [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)sınıfından türetilmiş çerçeve pencere nesnelerinin katıştırılmış üyeleridir.

[CToolBar:: GetToolBarCtrl](#gettoolbarctrl), MFC 4,0 ' ye yeni bir üye Işlevi, Windows ortak denetim 'in araç çubuğu özelleştirmesi ve ek işlevler için destek avantajlarından yararlanmanızı sağlar. `CToolBar` üye işlevleri, Windows ortak denetimleri işlevlerinin çoğunu sağlar; Ancak, `GetToolBarCtrl`çağırdığınızda, araç çubuklarınızın Windows 95/98 araç çubuklarının özelliklerine daha da fazlasını sağlayabilirsiniz. `GetToolBarCtrl`çağırdığınızda, bir `CToolBarCtrl` nesnesine bir başvuru döndürür. Windows ortak denetimleri kullanarak araç çubukları tasarlama hakkında daha fazla bilgi için bkz. [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) . Ortak denetimler hakkında daha fazla genel bilgi için bkz. Windows SDK [ortak denetimleri](/windows/win32/Controls/common-controls-intro) .

Görsel C++ , bir araç çubuğu oluşturmak için size iki yöntem sunar. Kaynak düzenleyicisini kullanarak bir araç çubuğu kaynağı oluşturmak için aşağıdaki adımları izleyin:

1. Bir araç çubuğu kaynağı oluşturun.

1. `CToolBar` nesnesini oluşturun.

1. Windows araç çubuğunu oluşturmak ve `CToolBar` nesnesine eklemek için [Create](#create) (veya [CreateEx](#createex)) işlevini çağırın.

1. Araç çubuğu kaynağını yüklemek için [LoadToolBar](#loadtoolbar) çağrısı yapın.

Aksi takdirde, aşağıdaki adımları izleyin:

1. `CToolBar` nesnesini oluşturun.

1. Windows araç çubuğunu oluşturmak ve `CToolBar` nesnesine eklemek için [Create](#create) (veya [CreateEx](#createex)) işlevini çağırın.

1. Araç çubuğu düğme görüntülerini içeren bit eşlemi yüklemek için [LoadBitmap](#loadbitmap) çağrısı yapın.

1. Düğme stilini ayarlamak ve her düğmeyi bit eşlemdeki bir görüntüyle ilişkilendirmek için [SetButtons](#setbuttons) çağırın.

Araç çubuğundaki tüm düğme görüntüleri, her düğme için bir resim içermesi gereken bir bit eşlemden alınır. Tüm görüntüler aynı boyutta olmalıdır; Varsayılan değer 16 piksel genişliğinde ve 15 piksel yüksekliğinde olur. Görüntülerin bit eşlemde yan yana olması gerekir.

`SetButtons` işlevi bir dizi denetim kimliği ve dizideki öğe sayısını belirten bir tamsayı alır. İşlevi, her düğmenin KIMLIĞINI dizinin karşılık gelen öğesinin değerine ayarlar ve her düğmeye, düğme resminin bit eşlemdeki konumunu belirten bir resim dizini atar. Bir dizi öğesinin değeri ID_SEPARATOR, hiçbir görüntü dizini atanmaz.

Bit eşlemdeki görüntülerin sırası genellikle ekranda çizilme sırasıdır, ancak görüntü sırası ve çizim sırası arasındaki ilişkiyi değiştirmek için [SetButtonInfo](#setbuttoninfo) işlevini kullanabilirsiniz.

Bir araç çubuğundaki tüm düğmeler aynı boyutlardır. *Yazılım tasarımı Için Windows arabirim yönergelerine*uygun olarak, varsayılan değer 24 x 22 pikseldir. Görüntü ve düğme boyutları arasındaki ek boşluklar görüntünün etrafında kenarlık oluşturmak için kullanılır.

Her düğmenin bir görüntüsü vardır. Çeşitli düğme durumları ve stilleri (basıldığında, yukarı, aşağı, devre dışı, devre dışı ve belirsiz) bu görüntüden oluşturulur. Bit eşlemler herhangi bir renk olabilse de, görüntülerde siyah ve gri gölgelerle en iyi sonuçları elde edebilirsiniz.

> [!WARNING]
> `CToolBar`, en fazla 16 renk olan bit eşlemleri destekler. Bir araç çubuğu düzenleyicisine bir görüntü yüklediğinizde, Visual Studio, gerekirse görüntüyü otomatik olarak 16 renkli bir bit eşlem 'e dönüştürür ve görüntü dönüştürülürse bir uyarı mesajı görüntüler. 16 ' dan fazla renge sahip bir görüntü kullanırsanız (görüntüyü düzenlemek için harici bir düzenleyici kullanarak), uygulama beklenmedik şekilde davranabilir.

Araç çubuğu düğmeleri varsayılan olarak itme düğmelerini taklit et. Ancak, araç çubuğu düğmeleri de onay kutusu düğmelerini veya radyo düğmelerini taklit edebilir. Onay kutusu düğmelerinin üç durumu vardır: işaretlendi, temizlendi ve belirsiz. Radyo düğmelerinin yalnızca iki durumu vardır: işaretlendi ve temizlendi.

Tek bir düğme veya ayırıcı stilini bir diziye işaret etmeden ayarlamak için, stili almak için [GetButtonStyle](#getbuttonstyle) ' ı çağırın ve ardından `SetButtons`yerine [SetButtonStyle](#setbuttonstyle) ' ı çağırın. çalışma zamanında bir düğmenin stilini değiştirmek istediğinizde `SetButtonStyle` en yararlı seçenektir.

Bir düğme üzerinde görünecek metin atamak için, düğme üzerinde görünecek metni almak üzere [GetButtonText](#getbuttontext) komutunu çağırın ve sonra metni ayarlamak Için [SetButtonText](#setbuttontext) öğesini çağırın.

Bir onay kutusu düğmesi oluşturmak için, bunu stil TBBS_CHECKBOX atayın veya bir ON_UPDATE_COMMAND_UI işleyicisinde `CCmdUI` nesnesinin `SetCheck` üye işlevini kullanın. `SetCheck` çağırmak, bir basma kutusunu onay kutusu düğmesine dönüştürür. İşaretsiz için 0, Checked için 1 veya belirsiz için 2 bağımsız değişkenini geçirin `SetCheck`.

Bir radyo düğmesi oluşturmak için bir ON_UPDATE_COMMAND_UI işleyicisinden [CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesinin [SetRadio](../../mfc/reference/ccmdui-class.md#setradio) üye işlevini çağırın. Checked için 0 bağımsız değişkenini işaretsiz veya sıfır dışında bir değere `SetRadio` geçirin. Radyo grubunun birbirini dışlayan davranışı sağlamak için gruptaki tüm düğmeler için ON_UPDATE_COMMAND_UI İşleyicileriniz olmalıdır.

`CToolBar`kullanma hakkında daha fazla bilgi için bkz. [MFC araç çubuğu uygulama](../../mfc/mfc-toolbar-implementation.md) ve [teknik notta 31: denetim çubukları](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CToolBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

##  <a name="commandtoindex"></a>CToolBar:: Commandtoındex

Bu üye işlevi, komut KIMLIĞI `nIDFind`eşleşen 0 konumundan başlayarak ilk araç çubuğu düğmesinin dizinini döndürür.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parametreler

*Nıdfind*<br/>
Bir araç çubuğu düğmesinin komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin dizini veya hiçbir düğme verilen komut KIMLIĞINE sahip değilse-1.

##  <a name="create"></a>CToolBar:: Create

Bu üye işlevi bir Windows araç çubuğu (alt pencere) oluşturur ve `CToolBar` nesnesiyle ilişkilendirir.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Araç çubuğunun üst öğesi olan pencerenin işaretçisi.

*dwStyle*<br/>
Araç çubuğu stili. Desteklenen ek araç çubuğu stilleri şunlardır:

- CBRS_TOP denetim çubuğu, çerçeve penceresinin en üstünde.

- CBRS_BOTTOM denetim çubuğu, çerçeve penceresinin en altında.

- Üst yeniden boyutlandırıldığında CBRS_NOALIGN denetim çubuğu yeniden konumlandırılmaz.

- CBRS_TOOLTIPS denetim çubuğu araç ipuçlarını görüntüler.

- CBRS_SIZE_DYNAMIC denetim çubuğu dinamiktir.

- CBRS_SIZE_FIXED denetim çubuğu düzeltildi.

- CBRS_FLOATING denetim çubuğu kayar.

- CBRS_FLYBY durum çubuğunda düğme hakkında bilgi görüntülenir.

- CBRS_HIDE_INPLACE denetim çubuğu kullanıcıya gösterilmez.

*NID*<br/>
Araç çubuğunun alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca, araç çubuğu yüksekliğini varsayılan bir değere ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]

##  <a name="createex"></a>CToolBar:: CreateEx

Bir Windows araç çubuğu (alt pencere) oluşturmak ve `CToolBar` nesnesiyle ilişkilendirmek için bu işlevi çağırın.

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
Araç çubuğunun üst öğesi olan pencerenin işaretçisi.

*dwCtrlStyle*<br/>
Gömülü [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) nesnesinin oluşturulmasına yönelik ek stiller. Varsayılan olarak, bu değer TBSTYLE_FLAT olarak ayarlanır. Araç çubuğu stillerinin tüm listesi için bkz. *dwStyle*.

*dwStyle*<br/>
Araç çubuğu stili. Uygun stillerin listesi için Windows SDK [araç çubuğu denetimi ve düğme stilleri](/windows/win32/Controls/toolbar-control-and-button-styles) ' ne bakın.

*Rckenarlýklar*<br/>
Araç çubuğu pencere kenarlıklarının genişliklerini tanımlayan bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi. Bu kenarlıklar varsayılan olarak 0, 0, 0, 0 olarak ayarlanır ve bu sayede bir kenarlık olmadan bir araç çubuğu penceresi ile sonuçlanır.

*NID*<br/>
Araç çubuğunun alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca, araç çubuğu yüksekliğini varsayılan bir değere ayarlar.

Katıştırılmış araç çubuğu denetiminin oluşturulması sırasında bazı stillerin bulunması gerektiğinde, [oluşturma](#create)yerine `CreateEx`kullanın. Örneğin, Internet Explorer 4 araç çubuklarına &#124; benzer bir araç çubuğu oluşturmak için dwCtrlStyle öğesini tbstyle_flat tbstyle_transparent olarak ayarlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]

##  <a name="ctoolbar"></a>CToolBar:: CToolBar

Bu üye işlevi bir `CToolBar` nesnesi oluşturur ve varsayılan boyutları ayarlar.

```
CToolBar();
```

### <a name="remarks"></a>Açıklamalar

Araç çubuğu penceresini oluşturmak için üye [Oluştur](#create) işlevini çağırın.

##  <a name="getbuttoninfo"></a>CToolBar:: GetButtonInfo

Bu üye işlevi, denetim KIMLIĞI, stili ve araç çubuğu düğmesi veya ayırıcı tarafından belirtilen konumdaki ayırıcı için resim dizinini alır *.*

```
void GetButtonInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& iImage) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Bilgileri alınacak olan araç çubuğu düğmesinin veya ayırıcısının dizini.

*NID*<br/>
Düğmenin komut KIMLIĞINE ayarlanmış bir UINT öğesine başvuru.

*nStyle*<br/>
Düğme stiline ayarlanan bir UINT öğesine başvuru.

*IImage*<br/>
Bit eşlem içindeki düğme resminin dizinine ayarlanmış bir tamsayıya başvuru.

### <a name="remarks"></a>Açıklamalar

Bu değerler, *NID*, *nStyle*ve *IImage*tarafından başvurulan değişkenlere atanır. Görüntü dizini, görüntünün tüm araç çubuğu düğmelerinin görüntülerini içeren bit eşlemdeki konumudur. İlk görüntü 0 konumundayken.

*NIndex* bir ayırıcı belirtiyorsa, *IImage* piksel cinsinden ayırıcı genişliğe ayarlanır.

##  <a name="getbuttonstyle"></a>CToolBar:: GetButtonStyle

Araç çubuğundaki bir düğmenin veya ayırıcının stilini almak için bu üye işlevi çağırın.

```
UINT GetButtonStyle(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Alınacak araç çubuğu düğmesinin veya ayırıcı stilin dizini.

### <a name="return-value"></a>Dönüş Değeri

*NIndex*tarafından belirtilen düğme veya ayırıcısının stili.

### <a name="remarks"></a>Açıklamalar

Düğmenin stili, düğmenin nasıl göründüğünü ve kullanıcı girişine nasıl yanıt vereceğini belirler. Düğme stillerinin örnekleri için bkz. [SetButtonStyle](#setbuttonstyle) .

##  <a name="getbuttontext"></a>CToolBar:: GetButtonText

Bir düğme üzerinde görünen metni almak için bu üye işlevini çağırın.

```
CString GetButtonText(int nIndex) const;

void GetButtonText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Alınacak metnin dizini.

*rString*<br/>
Alınacak metni içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Düğme metnini içeren `CString` nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin ikinci formu, bir `CString` nesnesini dize metniyle doldurur.

##  <a name="getitemid"></a>CToolBar:: GetItemID

Bu üye işlevi, *nIndex*tarafından belirtilen düğme veya AYıRıCıNıN komut kimliğini döndürür.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
KIMLIĞI alınacak olan öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

*Nindex*tarafından belirtilen düğme veya AYıRıCıNıN komut kimliği.

### <a name="remarks"></a>Açıklamalar

Ayırıcılar ID_SEPARATOR döndürür.

##  <a name="getitemrect"></a>CToolBar:: GetItemRect

Bu üye işlevi, *nIndex*tarafından belirtilen düğme veya ayırıcının koordinatları Ile *lpRect* içinde yer alan `RECT` yapısını doldurur.

```
virtual void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Dikdörtgen koordinatları alınacak olan öğenin (düğme veya ayırıcı) dizini.

*lpRect*<br/>
Öğenin koordinatlarını içerecek olan [Rect](/windows/win32/api/windef/ns-windef-rect) yapısının adresi.

### <a name="remarks"></a>Açıklamalar

Koordinatlar, araç çubuğunun sol üst köşesine göre piksel cinsinden yapılır.

Bir Birleşik giriş kutusuyla veya başka bir denetimle değiştirmek istediğiniz ayıracının koordinatlarını almak için `GetItemRect` kullanın.

### <a name="example"></a>Örnek

  [CToolBar:: Setboyutlar](#setsizes)örneğine bakın.

##  <a name="gettoolbarctrl"></a>CToolBar:: GetToolBarCtrl

Bu üye işlevi, temel alınan ortak denetime doğrudan erişim sağlar.

```
CToolBarCtrl& GetToolBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CToolBarCtrl` nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Windows araç çubuğu ortak denetiminin işlevlerinden yararlanmak ve araç çubuğu özelleştirmesi için [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) desteğinin avantajlarından yararlanmak için `GetToolBarCtrl` kullanın.

Ortak denetimleri kullanma hakkında daha fazla bilgi için [Windows SDK makalesine ve](../../mfc/controls-mfc.md) [genel denetimlere](/windows/win32/Controls/common-controls-intro) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]

##  <a name="loadbitmap"></a>CToolBar:: LoadBitmap

`lpszResourceName` veya `nIDResource`tarafından belirtilen bit eşlemi yüklemek için bu üye işlevi çağırın.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Yüklenecek bit eşlemin kaynak adı işaretçisi.

*nIDResource*<br/>
Yüklenecek bit eşlemin kaynak KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bit eşlem, her bir araç çubuğu düğmesi için bir resim içermelidir. Görüntüler standart boyutta değilse (16 piksel genişliğinde ve 15 piksel yüksekliğinde), düğme boyutlarını ve bunların görüntülerini ayarlamak için [Setboyutlar](#setsizes) ' ı çağırın.

> [!WARNING]
> `CToolBar`, en fazla 16 renk olan bit eşlemleri destekler. Bir araç çubuğu düzenleyicisine bir görüntü yüklediğinizde, Visual Studio, gerekirse görüntüyü otomatik olarak 16 renkli bir bit eşlem 'e dönüştürür ve görüntü dönüştürülürse bir uyarı mesajı görüntüler. 16 ' dan fazla renge sahip bir görüntü kullanırsanız (görüntüyü düzenlemek için harici bir düzenleyici kullanarak), uygulama beklenmedik şekilde davranabilir.

##  <a name="loadtoolbar"></a>CToolBar:: LoadToolBar

*LpszResourceName* veya *nidresource*tarafından belirtilen araç çubuğunu yüklemek için bu üye işlevi çağırın.

```
BOOL LoadToolBar(LPCTSTR lpszResourceName);
BOOL LoadToolBar(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Yüklenecek araç çubuğunun kaynak adı işaretçisi.

*nIDResource*<br/>
Yüklenecek araç çubuğunun kaynak KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir araç çubuğu kaynağı oluşturma hakkında daha fazla bilgi için bkz. [Araç Çubuğu Düzenleyicisi](../../windows/toolbar-editor.md) .

### <a name="example"></a>Örnek

  [CToolBar:: CreateEx](#createex)örneğine bakın.

##  <a name="setbitmap"></a>CToolBar:: SetBit eşlem

Araç çubuğunun bit eşlem resmini ayarlamak için bu üye işlevi çağırın.

```
BOOL SetBitmap(HBITMAP hbmImageWell);
```

### <a name="parameters"></a>Parametreler

*Hbmımagewell*<br/>
Bir araç çubuğuyla ilişkili bir bit eşlem görüntüsünün tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Örneğin, Kullanıcı bir düğmenin eylemini değiştiren bir belge üzerinde bir eylem gerçekleştirdikten sonra bit eşlenmiş görüntüyü değiştirmek için `SetBitmap` çağırın.

##  <a name="setbuttoninfo"></a>CToolBar:: SetButtonInfo

Düğmenin komut KIMLIĞINI, stilini ve resim numarasını ayarlamak için bu üye işlevini çağırın.

```
void SetButtonInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int iImage);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Hangi bilgilerin ayarlanacağı düğme veya ayırıcısının sıfır tabanlı dizini.

*NID*<br/>
Düğmenin komut KIMLIĞININ ayarlandığı değer.

*nStyle*<br/>
Yeni düğme stili. Aşağıdaki düğme stilleri desteklenir:

- TBBS_BUTTON standart basma düğmesi (varsayılan)

- TBBS_SEPARATOR ayırıcısı

- TBBS_CHECKBOX otomatik onay kutusu düğmesi

- TBBS_GROUP düğme grubunun başlangıcını Işaretler

- TBBS_CHECKGROUP bir onay kutusu düğme grubunun başlangıcını Işaretler

- TBBS_DROPDOWN açılır liste düğmesi oluşturur.

- TBBS_AUTOSIZE düğmenin genişliği, resmin boyutunun değil, düğme metni temel alınarak hesaplanır.

- Düğme metninde ilişkili bir Hızlandırıcı öneki olmayacak TBBS_NOPREFIX.

*IImage*<br/>
Düğmenin bit eşlem içindeki görüntüsü için yeni dizin.

### <a name="remarks"></a>Açıklamalar

Stili TBBS_SEPARATOR olan ayırıcılar için, bu işlev ayırıcıdaki genişliği *IImage*içinde depolanan değere ayarlar.

> [!NOTE]
>  Düğme durumlarını *nStyle* parametresini kullanarak da ayarlayabilirsiniz; Ancak, düğme durumları [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) işleyicisi tarafından denetlendiğinden, `SetButtonInfo` kullanarak ayarladığınız herhangi bir durum, bir sonraki boşta işleme sırasında kaybedilir. Daha fazla bilgi için bkz. [Kullanıcı arabirimi nesnelerini güncelleştirme](../../mfc/how-to-update-user-interface-objects.md) ve [TN031: denetim çubukları](../../mfc/tn031-control-bars.md) .

Bit eşlem görüntüleri ve düğmeleri hakkında daha fazla bilgi için bkz. [CToolBar](../../mfc/reference/ctoolbar-class.md) genel bakış ve [CToolBar:: LoadBitmap](#loadbitmap).

##  <a name="setbuttons"></a>CToolBar:: SetButtons

Bu üye işlevi, her bir araç çubuğu düğmesinin komut KIMLIĞINI dizi *lpIDArray*karşılık gelen öğesi tarafından belirtilen değere ayarlar.

```
BOOL SetButtons(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parametreler

*lpIDArray*<br/>
Komut kimlikleri dizisine yönelik işaretçi. Boş düğme ayırmak için NULL olabilir.

*nIDCount*<br/>
Dizide *lpIDArray*tarafından işaret edilen öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Dizinin bir öğesi ID_SEPARATOR değeri içeriyorsa, araç çubuğunun ilgili konumunda bir ayırıcı oluşturulur. Bu işlev Ayrıca her düğmenin stilini TBBS_BUTTON ve her ayırıcı stilini TBBS_SEPARATOR olarak ayarlar ve her düğmeye bir görüntü dizini atar. Görüntü dizini düğmenin bit eşlem içindeki resminin konumunu belirtir.

Bu işlev ayırıcılar için görüntü dizinleri atamadığı için bit eşlemdeki ayırıcılar için hesap yapmanız gerekmez. Araç çubuğundayken 0, 1 ve 3 konumunda düğmeler varsa ve 2 konumundaki bir ayırıcı varsa, bit eşleminizdeki 0, 1 ve 2 konumlarındaki görüntüler sırasıyla 0, 1 ve 3 konumlarda bulunan düğmelere atanır.

*LPIDARRAY* null ise, bu Işlev *nIDCount*tarafından belirtilen öğe sayısı için alan ayırır. Her öğenin özniteliklerini ayarlamak için [SetButtonInfo](#setbuttoninfo) kullanın.

##  <a name="setbuttonstyle"></a>CToolBar:: SetButtonStyle

Düğme veya ayırıcısının stilini veya grup düğmelerini ayarlamak için bu üye işlevini çağırın.

```
void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Bilgileri ayarlanacak düğme veya ayıracının dizini.

*nStyle*<br/>
Düğme stili. Aşağıdaki düğme stilleri desteklenir:

- TBBS_BUTTON standart basma düğmesi (varsayılan)

- TBBS_SEPARATOR ayırıcısı

- TBBS_CHECKBOX otomatik onay kutusu düğmesi

- TBBS_GROUP düğme grubunun başlangıcını Işaretler

- TBBS_CHECKGROUP bir onay kutusu düğme grubunun başlangıcını Işaretler

- TBBS_DROPDOWN açılır liste düğmesi oluşturur

- TBBS_AUTOSIZE düğmenin genişliği, düğmenin boyutunda değil, düğme metne göre hesaplanacak

- Düğme metninde ilişkili bir Hızlandırıcı öneki olmayacak TBBS_NOPREFIX

### <a name="remarks"></a>Açıklamalar

Düğmenin stili, düğmenin nasıl göründüğünü ve kullanıcı girişine nasıl yanıt vereceğini belirler.

`SetButtonStyle`çağrılmadan önce, düğme veya ayırıcı stilini almak için [GetButtonStyle](#getbuttonstyle) üye işlevini çağırın.

> [!NOTE]
>  Düğme durumlarını *nStyle* parametresini kullanarak da ayarlayabilirsiniz; Ancak, düğme durumları [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) işleyicisi tarafından denetlendiğinden, `SetButtonStyle` kullanarak ayarladığınız herhangi bir durum, bir sonraki boşta işleme sırasında kaybedilir. Daha fazla bilgi için bkz. [Kullanıcı arabirimi nesnelerini güncelleştirme](../../mfc/how-to-update-user-interface-objects.md) ve [TN031: denetim çubukları](../../mfc/tn031-control-bars.md) .

##  <a name="setbuttontext"></a>CToolBar:: SetButtonText

Düğmeye metin ayarlamak için bu işlevi çağırın.

```
BOOL SetButtonText(
    int nIndex,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Metni ayarlanacak düğmenin dizini.

*lpszText*<br/>
Bir düğme üzerinde ayarlanacak metni gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

  [CToolBar:: GetToolBarCtrl](#gettoolbarctrl)örneğine bakın.

##  <a name="setheight"></a>CToolBar:: SetHeight

Bu üye işlevi, araç çubuğunun yüksekliğini *Cyheight*olarak belirtilen piksel olarak ayarlar.

```
void SetHeight(int cyHeight);
```

### <a name="parameters"></a>Parametreler

*cyHeight*<br/>
Araç çubuğunun piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

[Setboyutları](#setsizes)çağırdıktan sonra, Standart araç çubuğu yüksekliğini geçersiz kılmak için bu üye işlevini kullanın. Yükseklik çok küçükse düğmeler en alta kırpılacak.

Bu işlev çağrılmaması halinde, çerçeve, araç çubuğunun yüksekliğini anlamak için düğmenin boyutunu kullanır.

##  <a name="setsizes"></a>CToolBar:: Setboyutlar

Araç çubuğunun düğmelerini *sizeButton*'da belirtilen boyuta piksel olarak ayarlamak için bu üye işlevini çağırın.

```
void SetSizes(
    SIZE sizeButton,
    SIZE sizeImage);
```

### <a name="parameters"></a>Parametreler

*sizeButton*<br/>
Her düğmenin piksel cinsinden boyutu.

*sizeImage*<br/>
Her resmin piksel cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

*SizeImage* parametresi, Toolbar 'ın bit eşlemdeki görüntülerin piksel cinsinden boyutunu içermelidir. *SizeButton* içindeki Boyutlar, görüntüyü ve 6 piksel ekstra genişlik ve yükseklik ve 6 piksel ekstra bir şekilde tutmak için yeterli olmalıdır. Bu işlev ayrıca araç çubuğu yüksekliğini düğmelere uyacak şekilde ayarlar.

Bu üye işlevini yalnızca, düğme ve resim boyutlarına yönelik *yazılım tasarımı önerileri Için Windows arabirim yönergeleri* ' ni takip eden araç çubukları için çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl Sınıfı](../../mfc/reference/ctoolbarctrl-class.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
