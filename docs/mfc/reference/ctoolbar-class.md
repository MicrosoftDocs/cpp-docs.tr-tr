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
ms.openlocfilehash: 938df6599ca3bfec3e08e77d7a60106133f54324
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178544"
---
# <a name="ctoolbar-class"></a>CToolBar sınıfı

Bit eşlemli düğmeler ve isteğe bağlı ayırıcılar içeren bir satırın sahip denetim çubukları.

## <a name="syntax"></a>Sözdizimi

```
class CToolBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CToolBar::CToolBar](#ctoolbar)|Oluşturur bir `CToolBar` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CToolBar::CommandToIndex](#commandtoindex)|Belirtilen komut kimliği. bir düğmeyle indisini döndürür|
|[CToolBar::Create](#create)|Windows araç çubuğu oluşturur ve ona ekler `CToolBar` nesne.|
|[CToolBar::CreateEx](#createex)|Oluşturur bir `CToolBar` embedded için ek stilleri nesnesiyle `CToolBarCtrl` nesne.|
|[CToolBar::GetButtonInfo](#getbuttoninfo)|Kimliği, stili ve bir düğmeyi görüntü sayısını alır.|
|[CToolBar::GetButtonStyle](#getbuttonstyle)|Bir düğmenin stilini alır.|
|[CToolBar::GetButtonText](#getbuttontext)|Bir düğme üzerinde görünen metni alır.|
|[CToolBar::GetItemID](#getitemid)|Bir düğme veya ayırıcı verilen dizindeki komut Kimliğini döndürür.|
|[CToolBar::GetItemRect](#getitemrect)|Belirtilen dizindeki öğe için görünen dikdörtgen alır.|
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|Temel alınan bir ortak denetimi doğrudan erişim sağlar.|
|[CToolBar::LoadBitmap](#loadbitmap)|Bit eşlem bit eşlem düğmesi görüntüleri içeren yükler.|
|[CToolBar::LoadToolBar](#loadtoolbar)|Kaynak Düzenleyicisi ile oluşturulmuş bir araç çubuğu kaynağı yükler.|
|[CToolBar::SetBitmap](#setbitmap)|Bit eşlemli görüntüyü ayarlar.|
|[CToolBar::SetButtonInfo](#setbuttoninfo)|Kimliği, stili ve bir düğmeyi görüntü sayısını ayarlar.|
|[CToolBar::SetButtons](#setbuttons)|Stilleri ve bit eşlem düğmesi yansımalar dizinini Ayarlar düğmesi.|
|[CToolBar::SetButtonStyle](#setbuttonstyle)|Bir düğmenin stilini ayarlar.|
|[CToolBar::SetButtonText](#setbuttontext)|Bir düğme üzerinde görünen metin ayarlar.|
|[CToolBar::SetHeight](#setheight)|Araç çubuğunun yüksekliği ayarlar.|
|[CToolBar::SetSizes](#setsizes)|Düğmeler ve bunların bit eşlemler boyutunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

Düğmeleri pushbuttons, onay kutusu düğmeleri veya radyo düğmeleri gibi davranabilir. `CToolBar` sınıfından türetilen çerçeve pencere nesneleri genellikle katıştırılmış üyeleri nesnelerdir [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md).

[CToolBar::GetToolBarCtrl](#gettoolbarctrl), üye işlevi yeni MFC 4.0 için araç çubuğu özelleştirme ve ek işlevsellik için Windows ortak denetim destek avantajlarından yararlanmak sağlar. `CToolBar` üye işlevleri, çoğu Windows ortak denetimleri işlevlerini sağlar; Ancak, çağırdığınızda `GetToolBarCtrl`, çubuklarınızı Windows 95/98 araç çubukları özelliklerini daha da verebilirsiniz. Çağırdığınızda `GetToolBarCtrl`, bir başvuru döndürür bir `CToolBarCtrl` nesne. Bkz: [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) Windows ortak denetimleri kullanma araç çubukları tasarlama hakkında daha fazla bilgi için. Ortak Denetimler hakkında daha fazla genel bilgi için bkz: [ortak denetimleri](/windows/desktop/Controls/common-controls-intro) Windows SDK.

Visual C++ araç oluşturmak için iki yöntem sunar. Kaynak Düzenleyicisi'ni kullanarak bir araç çubuğu kaynağı oluşturmak için aşağıdaki adımları izleyin:

1. Araç çubuğu kaynağı oluşturun.

1. Oluşturmak `CToolBar` nesne.

1. Çağrı [Oluştur](#create) (veya [CreateEx](#createex)) Windows araç çubuğu oluşturma ve buna eklemek için işlevi `CToolBar` nesne.

1. Çağrı [LoadToolBar](#loadtoolbar) araç çubuğu kaynağı yüklenemedi.

Aksi takdirde, aşağıdaki adımları izleyin:

1. Oluşturmak `CToolBar` nesne.

1. Çağrı [Oluştur](#create) (veya [CreateEx](#createex)) Windows araç çubuğu oluşturma ve buna eklemek için işlevi `CToolBar` nesne.

1. Çağrı [LoadBitmap](#loadbitmap) araç çubuğu düğmesi görüntüleri içeren bit eşlem yüklenemiyor.

1. Çağrı [SetButtons](#setbuttons) düğme stilini ayarlayın ve her düğme bit eşlemde görüntü ile ilişkilendirin.

Araç çubuğunda düğme resimlerini her düğme için bir görüntü içermelidir bir bit eşlem alınmıştır. Tüm görüntüleri, aynı boyutta olmalıdır; 16 piksel genişliğinde ve 15 piksel yüksekliğinde varsayılan değerdir. Görüntüler, bit eşlem yan yana olmalıdır.

`SetButtons` İşlev denetimi kimlikleri ve dizideki öğelerin sayısını belirten bir tamsayı dizisi için bir işaretçi alır. İşlevi, karşılık gelen öğe dizinin değerine her düğmenin Kimliğini ayarlar ve her düğme bit eşleminde düğmenin görüntü konumu belirtir bir görüntü dizini atar. Bir dizi öğesine ID_SEPARATOR değeri varsa, hiçbir görüntü dizini atanır.

Bit eşlem resmi genellikle sipariş ekrandaki çizileceğini ancak kullanabilirsiniz sırasıdır [SetButtonInfo](#setbuttoninfo) görüntü sırası ve çizim sırası arasındaki ilişkiyi değiştirmek için işlevi.

Tüm bir araç çubuğu düğmeleri aynı boyuttadır. Varsayılan değer 24 x 22, dağıtabilirler pikseldir *yazılım tasarımı için Windows arabirimi yönergelerine*. Görüntü ve düğme boyutları arasında ek alan, görüntünün çevresine bir kenarlık oluşturmak için kullanılır.

Her düğmesi bir görüntü vardır. Çeşitli durumları düğmesi ve stilleri (basılı yukarı, aşağı, devre dışı, aşağı devre dışı bırakılmış ve belirsiz), bir görüntüden oluşturulur. Bit eşlemler herhangi bir renk olabilse de, siyah, gri görüntülerle en iyi sonuçlar elde edebilirsiniz.

> [!WARNING]
> `CToolBar` bit eşlemler 16 renk en fazla destekler. Görüntüyü bir araç çubuğu Düzenleyicisi'ne yüklemek, Visual Studio otomatik olarak görüntü 16 renk bit eşleme, gerekirse dönüştürür ve görüntü dönüştürdüyseniz bir uyarı iletisi görüntüler. Görüntüyü (görüntü düzenlemek için bir dış düzenleyici kullanarak), 16'dan fazla renklerle kullanırsanız, uygulama beklenmedik şekilde davranabilir.

Araç çubuğu düğmeleri, varsayılan olarak pushbuttons taklit edin. Ancak, araç çubuğu düğmeleri de düğmeler onay kutusu veya radyo düğmeleri taklit. Onay kutusu düğmeleri, üç durumu vardır: işaretli, temizlenen ve belirsiz. Radyo düğmeleri yalnızca iki durum vardır: işaretli ve temizlenir.

Bir diziye işaret eden olmadan, bir düğmeye veya ayıraç stili ayarlamak için çağrı [GetButtonStyle](#getbuttonstyle) stili almak ve ardından çağırmak için [SetButtonStyle](#setbuttonstyle) yerine `SetButtons`. `SetButtonStyle` Çalışma zamanında bir düğmenin stilini değiştirmek istediğiniz zaman en kullanışlıdır.

Arama çubuğunda görüntülenecek metni atamak [GetButtonText](#getbuttontext) düğme üzerinde görünen ve ardından çağırmak üzere metin almak için [SetButtonText](#setbuttontext) metnini ayarlamak için.

Bir onay kutusu düğmesi oluşturma, TBBS_CHECKBOX stili atama veya kullanmak için bir `CCmdUI` nesnenin `SetCheck` on_update_command_uı işleyicisindeki üye işlevi. Çağırma `SetCheck` bir onay kutusu düğmesi bir basma düğmesi dönüşür. Geçirmek `SetCheck` bir bağımsız değişkeni 0 işaretli 1 için işaretli ya da 2 için belirsiz.

Bir radyo düğmesi oluşturmak için arama bir [Ccmduı](../../mfc/reference/ccmdui-class.md) nesnenin [SetRadio](../../mfc/reference/ccmdui-class.md#setradio) on_update_command_uı işleyicisinden üye işlevi. Geçirmek `SetRadio` denetlenmeyen ve iade için sıfır için 0 bağımsız değişken. Radyo grubun birbirini dışlayan davranışı sağlamak için gruptaki tüm düğmeler on_update_command_uı işleyicileri olması gerekir.

Kullanma hakkında daha fazla bilgi için `CToolBar`, makaleye göz atın [MFC araç çubuğu uygulaması](../../mfc/mfc-toolbar-implementation.md) ve [Teknik Not 31: Denetim çubukları](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CToolBar`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

##  <a name="commandtoindex"></a>  CToolBar::CommandToIndex

Bu üye işlevi komut kimliği eşleşen 0 konumunda başlayan ilk araç çubuğu düğmesini indisini döndürür `nIDFind`.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parametreler

*nIDFind*<br/>
Araç çubuğu düğmesi komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Düğme veya hiçbir düğmesi belirtilen komut kimliği yoksa -1 dizini

##  <a name="create"></a>  CToolBar::Create

Bu üye işlevi bir Windows araç çubuğu (alt pencere) oluşturur ve bunu ile ilişkilendirir `CToolBar` nesne.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Araç çubuğunun üst penceresine işaretçisi.

*dwStyle*<br/>
Araç çubuğu stili. Desteklenen ek toolbar stilleri şunlardır:

- Çerçeve penceresinin üst kısmındaki CBRS_TOP denetim çubuğudur.

- Çerçeve penceresinin alt kısmında CBRS_BOTTOM denetim çubuğu bulunmaktadır.

- Üst yeniden boyutlandırıldığında CBRS_NOALIGN denetim çubuğu yeniden konumlandırıldığında değil.

- Cbrs_tooltıps denetim çubuğunun araç ipuçlarını gösterir.

- Cbrs_sıze_dynamıc denetim çubuğu dinamiktir.

- Cbrs_sıze_fıxed denetim çubuğu sabittir.

- CBRS_FLOATING denetim çubuğu kayan.

- CBRS_FLYBY durum çubuğu düğme hakkındaki bilgileri görüntüler.

- Kullanıcıya CBRS_HIDE_INPLACE denetim çubuğu görüntülenmez.

*nID*<br/>
Araç çubuğunun alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca araç yüksekliği için varsayılan bir değer ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]

##  <a name="createex"></a>  CToolBar::CreateEx

Bir Windows araç çubuğu (alt pencere) oluşturun ve bunu ile ilişkilendirmek için bu işlevi çağırın `CToolBar` nesne.

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
Araç çubuğunun üst penceresine işaretçisi.

*dwCtrlStyle*<br/>
Katıştırılmış oluşturulması için ek stilleri [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) nesne. Varsayılan olarak, bu değer için TBSTYLE_FLAT ayarlanır. Toolbar stilleri tam bir listesi için bkz. *dwStyle*.

*dwStyle*<br/>
Araç çubuğu stili. Bkz: [araç çubuğu denetimi ve düğme stilleri](/windows/desktop/Controls/toolbar-control-and-button-styles) uygun stilleri bir listesi için Windows SDK.

*rcBorders*<br/>
A [CRect](../../atl-mfc-shared/reference/crect-class.md) araç penceresi kenarlık genişliğini tanımlayan nesne. Bu kenarlıkları böylece hiçbir kenarlık ile bir araç penceresi sonuçta varsayılan olarak 0,0,0,0 için ayarlanır.

*nID*<br/>
Araç çubuğunun alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca araç yüksekliği için varsayılan bir değer ayarlar.

Kullanım `CreateEx`, yerine [Oluştur](#create), belirli stilleri katıştırılmış araç çubuğu denetiminin oluşturma sırasında mevcut olması gerekir. Örneğin, *dwCtrlStyle* TBSTYLE_FLAT için &#124; TBSTYLE_TRANSPARENT Internet Explorer 4 araç çubukları benzer bir araç çubuğu oluşturmak için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]

##  <a name="ctoolbar"></a>  CToolBar::CToolBar

Bu üye işlevi oluşturan bir `CToolBar` nesnesini ve varsayılan boyutları ayarlar.

```
CToolBar();
```

### <a name="remarks"></a>Açıklamalar

Çağrı [Oluştur](#create) araç penceresi oluşturmak için üye işlevi.

##  <a name="getbuttoninfo"></a>  CToolBar::GetButtonInfo

Denetim kimliği, stili ve araç çubuğu düğmesi ve ayırıcı tarafından belirtilen konumda görüntü dizini alır. Bu üye işlevi *nIndex.*

```
void GetButtonInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& iImage) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Araç çubuğu düğmesini veya ayırıcı alınacak olan bilgilerdir dizini.

*nID*<br/>
Düğmenin komut kimliği ayarlayan bir UINT başvuru.

*nStyle*<br/>
Stile düğmesinin ayarlanmış bir UINT başvuru.

*iImage*<br/>
Düğmenin görüntü bit eşlem içindeki dizini olarak ayarlanmış bir tamsayı başvuru.

### <a name="remarks"></a>Açıklamalar

Bu değerler tarafından başvurulan değişkenleri atanan *nID*, *nStyle*, ve *iImage*. Görüntü dizini görüntü içeren tüm araç çubuğu düğmeleri için görüntü bit eşlem içindeki konumudur. İlk 0 konumuna görüntüdür.

Varsa *nIndex* bir ayırıcı belirtir *iImage* ayırıcı genişliğini piksel cinsinden ayarlayın.

##  <a name="getbuttonstyle"></a>  CToolBar::GetButtonStyle

Bir düğme veya araç çubuğunda ayırıcı stilini almak için bu üye işlevini çağırın.

```
UINT GetButtonStyle(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Alınacak araç çubuğu düğmesini veya ayırıcı style dizini.

### <a name="return-value"></a>Dönüş Değeri

Düğme veya ayırıcı tarafından belirtilen stilini *nIndex*.

### <a name="remarks"></a>Açıklamalar

Düğme nasıl göründüğünü ve nasıl kullanıcı girişine yanıt veren bir düğmenin stilini belirler. Bkz: [SetButtonStyle](#setbuttonstyle) düğme stilleri örnekleri için.

##  <a name="getbuttontext"></a>  CToolBar::GetButtonText

Bir düğme üzerinde görünen metin almak için bu üye işlevini çağırın.

```
CString GetButtonText(int nIndex) const;

void GetButtonText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Alınacak metin dizini.

*rString*<br/>
Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) alınacak metni içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

A `CString` düğme metnini içeren nesne.

### <a name="remarks"></a>Açıklamalar

İkinci form, bu üye işlev dolgular bir `CString` dize metin içeren nesne.

##  <a name="getitemid"></a>  CToolBar::GetItemID

Bu üye işlevi döndürür düğmesine veya ayırıcı tarafından belirtilen komut kimliği *nIndex*.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Alınacak Kimliğine sahip öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Düğme veya ayırıcı tarafından belirtilen komut kimliği *nIndex*.

### <a name="remarks"></a>Açıklamalar

Ayırıcılar ID_SEPARATOR döndürür.

##  <a name="getitemrect"></a>  CToolBar::GetItemRect

Bu üye işlevi doldurur `RECT` adresini kapsanıyorsa yapısı *lpRect* düğme veya ayırıcı tarafından belirtilen koordinatları ile *nIndex*.

```
virtual void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Dikdörtgen koordinatları alınacak olan öğenin dizini (düğme veya ayırıcı).

*lpRect*<br/>
Adresi [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı öğenin koordinatlarını içerir.

### <a name="remarks"></a>Açıklamalar

Piksel araç çubuğunun sol üst köşesindeki göreli koordinatları.

Kullanım `GetItemRect` bir birleşik giriş kutusu ya da diğer denetim değiştirmek istediğiniz bir ayırıcı koordinatları alınacak.

### <a name="example"></a>Örnek

  Örneğin bakın [CToolBar::SetSizes](#setsizes).

##  <a name="gettoolbarctrl"></a>  CToolBar::GetToolBarCtrl

Bu üye işlevi, temel alınan bir ortak denetimi doğrudan erişim sağlar.

```
CToolBarCtrl& GetToolBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru bir `CToolBarCtrl` nesne.

### <a name="remarks"></a>Açıklamalar

Kullanım `GetToolBarCtrl` Windows araç çubuğu ortak denetim işlevlerini avantajlarından yararlanın ve Destek avantajlarından yararlanmak için [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) için araç çubuğu özelleştirmesini sağlar.

Ortak denetimleri kullanma hakkında daha fazla bilgi için bkz [denetimleri](../../mfc/controls-mfc.md) ve [ortak denetimleri](/windows/desktop/Controls/common-controls-intro) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]

##  <a name="loadbitmap"></a>  CToolBar::LoadBitmap

Tarafından belirtilen bit eşlem yüklemek için bu üye işlevi çağrısı `lpszResourceName` veya `nIDResource`.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Kaynak adı yüklenecek bit eşlemin işaretçisi.

*nIDResource*<br/>
Yüklenecek bit eşlemin kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Her araç çubuğu düğmesi için bir görüntü bit eşlem içermelidir. Görüntüleri standart boyutu (16 piksel genişliğinde ve 15 piksel yüksekliğinde) çağrısı değilse, [SetSizes](#setsizes) düğme boyutlarını ve resimlerinin ayarlamak için.

> [!WARNING]
> `CToolBar` bit eşlemler 16 renk en fazla destekler. Görüntüyü bir araç çubuğu Düzenleyicisi'ne yüklemek, Visual Studio otomatik olarak görüntü 16 renk bit eşleme, gerekirse dönüştürür ve görüntü dönüştürdüyseniz bir uyarı iletisi görüntüler. Görüntüyü (görüntü düzenlemek için bir dış düzenleyici kullanarak), 16'dan fazla renklerle kullanırsanız, uygulama beklenmedik şekilde davranabilir.

##  <a name="loadtoolbar"></a>  CToolBar::LoadToolBar

Tarafından belirtilen araç yüklemek için bu üye işlevi çağrısı *lpszResourceName* veya *nIDResource*.

```
BOOL LoadToolBar(LPCTSTR lpszResourceName);
BOOL LoadToolBar(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Kaynak adı araç çubuğunun yüklenecek işaretçisi.

*nIDResource*<br/>
Yüklenecek araç çubuğunun kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bkz: [araç çubuğu Düzenleyicisi](../../windows/toolbar-editor.md) içinde bir araç çubuğu kaynağı oluşturma hakkında daha fazla bilgi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CToolBar::CreateEx](#createex).

##  <a name="setbitmap"></a>  CToolBar::SetBitmap

Araç çubuğu için bit eşlem resmi ayarlamak için bu üye işlevini çağırın.

```
BOOL SetBitmap(HBITMAP hbmImageWell);
```

### <a name="parameters"></a>Parametreler

*hbmImageWell*<br/>
Bir araç çubuğu ile ilişkili olan bit eşlem görüntüsüne tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Örneğin, çağrı `SetBitmap` kullanıcı, bir düğmenin eylemi değiştiren bir belgeyi bir eylem gerçekleştirdikten sonra bit eşlemli resmi değiştirmek için.

##  <a name="setbuttoninfo"></a>  CToolBar::SetButtonInfo

Düğmenin komut kimliği, stili ve görüntü sayısı ayarlamak için bu üye işlevini çağırın.

```
void SetButtonInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int iImage);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Düğme veya bilgi ayarlanacak olduğu ayırıcı sıfır tabanlı dizini.

*nID*<br/>
Değer, düğmenin komut kimliği ayarlanır.

*nStyle*<br/>
Yeni düğme stili. Aşağıdaki düğme stilleri desteklenir:

- TBBS_BUTTON standart basma düğmesi (varsayılan)

- TBBS_SEPARATOR ayırıcı

- TBBS_CHECKBOX otomatik onay kutusu düğmesi

- TBBS_GROUP düğmesi grubu başlangıcını işaretler.

- TBBS_CHECKGROUP onay kutusu düğmesi grubu başlangıcını işaretler.

- Açılır liste düğmesinde TBBS_DROPDOWN oluşturur.

- Düğmenin genişliği hesaplanır TBBS_AUTOSIZE görüntüsünün boyutu değil, bir düğmenin metni temel.

- Düğme metnini TBBS_NOPREFIX kendisiyle ilişkilendirilmiş bir Hızlandırıcı öneki yoktur.

*iImage*<br/>
Düğmenin görüntü bit eşlem içindeki yeni dizini.

### <a name="remarks"></a>Açıklamalar

Depolanan değere piksel cinsinden TBBS_SEPARATOR stili olan ayırıcılar için bu işlevi ayırıcı'nın genişliğini ayarlar *iImage*.

> [!NOTE]
>  Düğme durumları kullanarak da ayarlayabilirsiniz *nStyle* parametre; ancak, düğme durumları tarafından denetlenir çünkü [on_update_command_uı](message-map-macros-mfc.md#on_update_command_ui) herhangi işleyici, durum kullanarak ayarladığınız `SetButtonInfo` kaybolacak sonraki boşta işleme sırasında. Bkz: [kullanıcı arabirimi nesnelerini güncelleştirme](../../mfc/how-to-update-user-interface-objects.md) ve [TN031: Denetim çubukları](../../mfc/tn031-control-bars.md) daha fazla bilgi için.

Bit eşlem resimleri ve düğmeleri hakkında daha fazla bilgi için bkz: [CToolBar](../../mfc/reference/ctoolbar-class.md) genel bakış ve [CToolBar::LoadBitmap](#loadbitmap).

##  <a name="setbuttons"></a>  CToolBar::SetButtons

Her araç çubuğu düğmesinin komut kimliği bu üye işlevi dizinin karşılık gelen öğe tarafından belirtilen değere ayarlar *lpIDArray*.

```
BOOL SetButtons(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parametreler

*lpIDArray*<br/>
Komut kimlikleri bir dizi için işaretçi. Boş düğme ayrılacak NULL olabilir.

*nIDCount*<br/>
Dizideki öğelerin sayısı tarafından işaret edilen *lpIDArray*.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir öğe dizinin ID_SEPARATOR değeri varsa, ayırıcı araç ilgili konumda oluşturulur. Bu işlev ayrıca TBBS_BUTTON ve TBBS_SEPARATOR stiline her ayırıcı'nın her bir düğmenin stilini ayarlar ve her düğme için resim dizini atar. Görüntü dizini düğmenin görüntü bit eşlem içindeki konumunu belirtir.

Bit eşlem ayırıcılar için bu işlevi ayırıcılar için görüntü dizinleri atamaz çünkü hesabı gerekmez. Araç pozisyon 0 düğmesi varsa, 1 ve 3 ve ayırıcı 2 konumundaki, görüntüler, bit eşlem içinde 0, 1 ve 2 konumlarda düğmeleri konumlarda 0, 1 ve 3, sırasıyla atanır.

Varsa *lpIDArray* NULL ise bu işlev tarafından belirtilen öğe sayısı için alanı ayırır *nIDCount*. Kullanım [SetButtonInfo](#setbuttoninfo) her öğenin öznitelikleri ayarlanamadı.

##  <a name="setbuttonstyle"></a>  CToolBar::SetButtonStyle

Bir düğme veya ayırıcı ya da Grup düğmeleri ayarlamak için bu üye işlevini çağırın.

```
void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Düğme veya ayarlanacak olan bilgilerdir ayırıcı dizini.

*nStyle*<br/>
Düğme stili. Aşağıdaki düğme stilleri desteklenir:

- TBBS_BUTTON standart basma düğmesi (varsayılan)

- TBBS_SEPARATOR ayırıcı

- TBBS_CHECKBOX otomatik onay kutusu düğmesi

- TBBS_GROUP düğmesi grubu başlangıcını işaretler.

- TBBS_CHECKGROUP onay kutusu düğmesi grubu başlangıcını işaretler.

- Açılır liste düğmesinde TBBS_DROPDOWN oluşturur

- Resmin boyutu değil, bir düğmenin metni düğmenin genişliği hesaplanır TBBS_AUTOSIZE dayalı

- Kendisiyle ilişkili bir Hızlandırıcı öneki TBBS_NOPREFIX düğme metnini olmaz

### <a name="remarks"></a>Açıklamalar

Düğme nasıl göründüğünü ve nasıl kullanıcı girişine yanıt veren bir düğmenin stilini belirler.

Çağırmadan önce `SetButtonStyle`, çağrı [GetButtonStyle](#getbuttonstyle) düğme veya ayırıcı stili almak için üye işlevi.

> [!NOTE]
>  Düğme durumları kullanarak da ayarlayabilirsiniz *nStyle* parametre; ancak, düğme durumları tarafından denetlenir çünkü [on_update_command_uı](message-map-macros-mfc.md#on_update_command_ui) herhangi işleyici, durum kullanarak ayarladığınız `SetButtonStyle` kaybolacak sonraki boşta işleme sırasında. Bkz: [kullanıcı arabirimi nesnelerini güncelleştirme](../../mfc/how-to-update-user-interface-objects.md) ve [TN031: Denetim çubukları](../../mfc/tn031-control-bars.md) daha fazla bilgi için.

##  <a name="setbuttontext"></a>  CToolBar::SetButtonText

Bir düğme metnini ayarlamak için bu işlevi çağırın.

```
BOOL SetButtonText(
    int nIndex,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Metni ayarlamak için olan düğme dizini.

*lpszText*<br/>
Metin bir düğme olarak işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

  Örneğin bakın [CToolBar::GetToolBarCtrl](#gettoolbarctrl).

##  <a name="setheight"></a>  CToolBar::SetHeight

Bu üye işlevi, araç çubuğunun yüksekliği, piksel cinsinden belirtilen değere ayarlar *cyHeight*.

```
void SetHeight(int cyHeight);
```

### <a name="parameters"></a>Parametreler

*cyHeight*<br/>
Araç çubuğunun piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

Arama sonra [SetSizes](#setsizes), standart araç çubuğu yüksekliği geçersiz kılmak için bu üye işlevi'ni kullanın. Yükseklik depolayamayacak kadar küçükse, düğmeler altındaki kırpılır.

Bu işlev çağrılır değil, framework düğmenin boyutunu araç yüksekliği belirlemek için kullanır.

##  <a name="setsizes"></a>  CToolBar::SetSizes

Belirtilen piksel cinsinden boyuta araç çubuğunun düğmeleri ayarlamak için bu üye işlevi çağrısı *sizeButton*.

```
void SetSizes(
    SIZE sizeButton,
    SIZE sizeImage);
```

### <a name="parameters"></a>Parametreler

*sizeButton*<br/>
Düğmelerin piksel cinsinden boyutu.

*sizeImage*<br/>
Her resminin piksel cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

*SizeImage* boyutunu piksel cinsinden araç çubuğunun bit eşlem resmi parametre içermelidir. Boyutlar *sizeButton* görüntünün yanı sıra 7 piksel cinsinden genişliği ek ve 6 piksel cinsinden yüksekliği ek tutmak yeterli olmalıdır. Bu işlev, ayrıca araç yüksekliğini düğmeleri ayarlar.

İzleyen değil yalnızca araç çubukları için bu üye işlevi çağrısı *yazılım tasarımı için Windows arabirimi yönergelerine* düğmesi ve görüntü boyutları için öneriler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek CTRLBARS](../../visual-cpp-samples.md)<br/>
[MFC örnek DLGCBR32](../../visual-cpp-samples.md)<br/>
[MFC örnek DOCKTOOL](../../visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl Sınıfı](../../mfc/reference/ctoolbarctrl-class.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
