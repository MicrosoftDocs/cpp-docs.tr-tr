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
ms.openlocfilehash: 70d700197e3d249812e8b09a2cba744a0fbc9803
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649286"
---
# <a name="cstatusbar-class"></a>CStatusBar sınıfı

Metin çıkış bölmeleri veya "göstergeler" satırına sahip bir denetim çubuğu

## <a name="syntax"></a>Sözdizimi

```
class CStatusBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStatusBar::CStatusBar](#cstatusbar)|Oluşturur bir `CStatusBar` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStatusBar::CommandToIndex](#commandtoindex)|Verilen göstergesi kimliği için dizinini alır|
|[CStatusBar::Create](#create)|Durum çubuğu oluşturur, ekler `CStatusBar` nesnesi ve ilk yazı tipi ve çubuk yüksekliği ayarlar.|
|[CStatusBar::CreateEx](#createex)|Oluşturur bir `CStatusBar` embedded için ek stilleri nesnesiyle `CStatusBarCtrl` nesne.|
|[CStatusBar::DrawItem](#drawitem)|Görsel bir özelliği bir özelleştirilmiş çizimli durum çubuğu denetim değişikliklerinin çağrılır.|
|[CStatusBar::GetItemID](#getitemid)|Belirli bir dizin için göstergesinin Kimliğini alır.|
|[CStatusBar::GetItemRect](#getitemrect)|Alır, belirli bir dizin için dikdörtgen görüntüler.|
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Gösterge kimliği, stil ve genişlik için belirli bir dizini alır.|
|[CStatusBar::GetPaneStyle](#getpanestyle)|Gösterge stili için belirli bir dizini alır.|
|[CStatusBar::GetPaneText](#getpanetext)|Gösterge Metni belirli bir dizini için alır.|
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|Temel alınan bir ortak denetimi doğrudan erişim sağlar.|
|[CStatusBar::SetIndicators](#setindicators)|Gösterge kimlikleri ayarlar.|
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Gösterge kimliği, stil ve genişlik belirtilen dizin için ayarlar.|
|[CStatusBar::SetPaneStyle](#setpanestyle)|Belirtilen dizin için gösterge stilini ayarlar.|
|[CStatusBar::SetPaneText](#setpanetext)|Gösterge metni belirtilen dizin için ayarlar.|

## <a name="remarks"></a>Açıklamalar

Çıkış bölmeleri, ileti satırları ve durum göstergesi olarak sık kullanılan bloblardır. Seçili bir menü komutunu kısaca açıklayan menü yardım iletisini satırları ve SCROLL LOCK, NUM LOCK ve diğer anahtarlar durumunu gösteren göstergeleri verilebilir.

[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl), bir üye işlevi yeni MFC 4.0 için durum çubuğu özelleştirme ve ek işlevsellik için Windows ortak denetim destek avantajlarından yararlanmanıza olanak tanır. `CStatusBar` üye işlevleri, çoğu Windows ortak denetimleri işlevlerini sağlar; Ancak, çağırdığınızda `GetStatusBarCtrl`, Windows 95/98 durum çubuğu özellikleri daha da, durum çubukları verebilirsiniz. Çağırdığınızda `GetStatusBarCtrl`, bir başvuru döndürür bir `CStatusBarCtrl` nesne. Bkz: [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Windows ortak denetimleri kullanma araç çubukları tasarlama hakkında daha fazla bilgi için. Ortak Denetimler hakkında daha fazla genel bilgi için bkz: [ortak denetimleri](/windows/desktop/Controls/common-controls-intro) Windows SDK.

Framework 0 konumundaki en soldaki göstergesi olan bir dizi göstergesini bilgilerini depolar. Durum çubuğu oluşturduğunuzda, dize framework ile ilgili göstergeler ilişkilendirir kimlikleri dizisi kullanın. Ardından, bir göstergesi erişmek için dize kimliği ya da dizin kullanabilirsiniz.

Varsayılan olarak, ilk göstergesi "elastik": diğer bölmeler sağa hizalı olmasını sağlamak, diğer göstergesi bölmeler tarafından kullanılmayan durum çubuğu uzunluğu kaplar.

Durum çubuğu oluşturmak için aşağıdaki adımları izleyin:

1. Oluşturmak `CStatusBar` nesne.

1. Çağrı [Oluştur](#create) (veya [CreateEx](#createex)) durum çubuğu penceresi oluştur ve buna eklemek için işlevi `CStatusBar` nesne.

1. Çağrı [SetIndicators](#setindicators) dize kimliği her göstergesi ile ilişkilendirilecek.

İçinde bir durum çubuğu bölmesinin metnini güncelleştirme üç yolu vardır:

1. Çağrı [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) metin bölmesinde 0 yalnızca güncelleştirilecek.

1. Çağrı [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) durum çubuğunun on_update_command_uı işleyicisi.

1. Çağrı [SetPaneText](#setpanetext) metnin herhangi bir bölme için güncelleştirilecek.

Çağrı [SetPaneStyle](#setpanestyle) bir durum çubuğu bölmesinin stilini güncelleştirilecek.

Kullanma hakkında daha fazla bilgi için `CStatusBar`, makaleye göz atın [MFC'de durum çubuğu uygulaması](../../mfc/status-bar-implementation-in-mfc.md) ve [Teknik Not 31: denetim çubukları](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

##  <a name="commandtoindex"></a>  CStatusBar::CommandToIndex

Belirli bir kimliği için göstergesinin dizinini alır

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parametreler

*nIDFind*<br/>
Alınacak dizini olan göstergesi kimliği dizesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa göstergesi dizinini; başarılı olursa -1.

### <a name="remarks"></a>Açıklamalar

İlk göstergesi dizini 0'dır.

##  <a name="create"></a>  CStatusBar::Create

Bir durum çubuğu (alt pencere) oluşturur ve bunu ile ilişkilendirir `CStatusBar` nesne.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
İşaretçi [CWnd](../../mfc/reference/cwnd-class.md) olan Windows penceresi durum çubuğunun üst nesne.

*dwStyle*<br/>
Durum çubuğu stili. Standart Windows yanı sıra [stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles), bu stilleri desteklenir.

- Çerçeve penceresinin üst kısmındaki CBRS_TOP denetim çubuğudur.

- Çerçeve penceresinin alt kısmında CBRS_BOTTOM denetim çubuğu bulunmaktadır.

- Üst yeniden boyutlandırıldığında CBRS_NOALIGN denetim çubuğu yeniden konumlandırıldığında değil.

*nID*<br/>
Araç çubuğunun alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca, ilk yazı tipini ayarlar ve durumunu ayarlar için varsayılan değer çubuğunun yüksekliği.

##  <a name="createex"></a>  CStatusBar::CreateEx

Bir durum çubuğu (alt pencere) oluşturun ve ilişkilendirmek için bu işlevi çağırın `CStatusBar` nesne.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
İşaretçi [CWnd](../../mfc/reference/cwnd-class.md) olan Windows penceresi durum çubuğunun üst nesne.

*dwCtrlStyle*<br/>
Katıştırılmış oluşturulması için ek stilleri [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) nesne. Varsayılan bir durum çubuğu olmadan boyutlandırma tutamacı veya araç ipucu belirtir destekler. Durum çubuğu stilleri desteklenen şunlardır:

- Durum çubuğunun sağ ucunda boyutlandırma tutamacı SBARS_SIZEGRIP durum çubuğu denetimi içerir. Boyutlandırma tutamacı için boyutlandırma kenarlığı benzer. Bu kullanıcı,'a tıklayın ve ana pencereyi yeniden boyutlandırmak için sürükleyin dikdörtgen bir alandır.

- SBT_TOOLTIPS durum çubuğunun araç ipuçlarını destekler.

Bu stilleri hakkında ayrıntılı bilgi için bkz. [cstatusbarctrl ayarları](../../mfc/settings-for-the-cstatusbarctrl.md).

*dwStyle*<br/>
Durum çubuğu stili. Varsayılan görünür durum çubuğu çerçeve penceresinin en altında oluşturulması belirtir. Durum çubuğu denetim stilleri listelenen herhangi bir birleşimini uygulamak [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create). Ancak, bu parametre, her zaman WS_CHILD ve ws_vısıble stilleri içermelidir.

*nID*<br/>
Alt penceresi durum çubuğunun kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev ayrıca ilk yazı tipini ayarlar ve durumunu ayarlar için varsayılan değer çubuğunun yüksekliği.

Kullanım `CreateEx`, yerine [Oluştur](#create), belirli stilleri katıştırılmış durum çubuğu denetimi oluşturma sırasında mevcut olması gerekir. Örneğin, *dwCtrlStyle* bir durum çubuğu nesnesinde araç ipuçları görüntülenecek SBT_TOOLTIPS için.

##  <a name="cstatusbar"></a>  CStatusBar::CStatusBar

Oluşturur bir `CStatusBar` nesne, gerekirse varsayılan durum çubuğu yazı oluşturur ve varsayılan değerlere yazı tipi özelliklerini ayarlar.

```
CStatusBar();
```

##  <a name="drawitem"></a>  CStatusBar::DrawItem

Bu üye işlevi bir sahip tarafından çizilmiş durum çubuğu değişiklikleri görsel bir özelliği, framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Bir işaretçi bir [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) gerekli çizim türü hakkında bilgi içeren yapısı.

### <a name="remarks"></a>Açıklamalar

`itemAction` Üyesi `DRAWITEMSTRUCT` gerçekleştirilecek çizim eylemi yapısını tanımlar. Sahip çizim için çizim uygulamak için bu üye işlevi geçersiz kılma `CStatusBar` nesne. Uygulama görünen bağlam sağlanan için seçilen tüm grafik cihaz arabirimi (GDI) nesneleri geri yüklemeniz gerekir *lpDrawItemStruct* bu üye işlevinin sona ermeden önce.

##  <a name="getitemid"></a>  CStatusBar::GetItemID

Tarafından belirtilen gösterge Kimliğini döndürür *nIndex*.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Alınacak Kimliğine sahip göstergesi dizini.

### <a name="return-value"></a>Dönüş Değeri

Kimliği tarafından belirtilen göstergenin *nIndex*.

##  <a name="getitemrect"></a>  CStatusBar::GetItemRect

Tarafından belirtilen göstergenin koordinat kopyalar *nIndex* işaret ettiği yapısında *lpRect*.

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Gösterge dikdörtgeni koordinatları alınacak olan dizini.

*lpRect*<br/>
İşaret eden bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) tarafından belirtilen göstergenin koordinat alacak nesne *nIndex*.

### <a name="remarks"></a>Açıklamalar

Durum çubuğunun sol üst köşesine göre piksel cinsinden koordinatları.

##  <a name="getpaneinfo"></a>  CStatusBar::GetPaneInfo

Kümeleri *nID*, *nStyle*, ve *cxWidth* kimliği, stil ve genişlik tarafından belirtilen konumda göstergesi bölmesinin için *nIndex*.

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Alınacak olan bilgilerdir bölmesinde dizini.

*nID*<br/>
Bölmenin Kimliğine ayarlanmış bir UINT başvuru.

*nStyle*<br/>
Bölmesinin stilini ayarlayın bir UINT başvuru.

*cxWidth*<br/>
Başvuru bölmesinin genişliğe ayarlanmış bir tamsayı.

##  <a name="getpanestyle"></a>  CStatusBar::GetPaneStyle

Bir durum çubuğu bölmesinin stilini almak için bu üye işlevini çağırın.

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Alınacak olan stilidir bölmesinde dizini.

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen durum çubuğu bölmesinin stilini *nIndex*.

### <a name="remarks"></a>Açıklamalar

Nasıl bölmesi görünür bir bölmesinin stilini belirler.

Durum çubukları için kullanılabilir stilleri bir listesi için bkz. [Oluştur](#create).

##  <a name="getpanetext"></a>  CStatusBar::GetPaneText

Bir durum çubuğu bölmesinde görüntülenen metni almak için bu üye işlevini çağırın.

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Alınacak metni olan bölmesinde dizini.

*rString*<br/>
Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) alınacak metni içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

A `CString` bölmedeki metin içeren nesne.

### <a name="remarks"></a>Açıklamalar

İkinci form, bu üye işlev dolgular bir `CString` dize metin içeren nesne.

##  <a name="getstatusbarctrl"></a>  CStatusBar::GetStatusBarCtrl

Bu üye işlevi, temel alınan bir ortak denetimi doğrudan erişim sağlar.

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru içeren bir [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Kullanım `GetStatusBarCtrl` Windows ortak durum çubuğu denetimi işlevlerini avantajlarından yararlanın ve Destek avantajlarından yararlanmak için [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) durum çubuğu özelleştirmesi sağlar. Örneğin, ortak denetimi kullanarak, durum çubuğundaki boyutlandırma tutamacı içeren bir stil belirtebilir veya ana pencerenin istemci alanının üstünde görünen durum çubuğu olan bir stil belirtebilirsiniz.

Ortak Denetimler hakkında daha fazla genel bilgi için bkz: [ortak denetimleri](/windows/desktop/Controls/common-controls-intro) Windows SDK.

##  <a name="setindicators"></a>  CStatusBar::SetIndicators

Her göstergenin Kimliğine karşılık gelen bir dizi öğesi tarafından belirtilen değere ayarlar *lpIDArray*her kimliği tarafından belirtilen dize kaynağı yükler ve göstergenin metin dizesi olarak ayarlar.

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parametreler

*lpIDArray*<br/>
Kimlikleri bir dizi için işaretçi.

*nIDCount*<br/>
Dizideki öğelerin sayısı tarafından işaret edilen *lpIDArray*.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo

Belirtilen gösterge bölmesinde yeni bir kimliği, stil ve genişlik ayarlar.

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Ayarlanacak stilini olan gösterge bölmesini dizini.

*nID*<br/>
Gösterge bölmesindeki yeni kimliği.

*nStyle*<br/>
Gösterge bölmesindeki yeni stili.

*cxWidth*<br/>
Gösterge bölmesini için yeni genişlik.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki göstergesi stilleri desteklenir:

- 3B kenarlık bölmesinde etrafında SBPS_NOBORDERS yok.

- SBPS_POPOUT ters kenarlık metin "yükseklikteki böylece."

- SBPS_DISABLED yapmak metin olmayan çizin.

- Kullanılmayan alanı doldurmak için SBPS_STRETCH Esnetme bölmesi. Durum çubuğu başına yalnızca bir bölme bu stil olabilir.

- SBPS_NORMAL Hayır esnetme, kenarlıklar veya açılır.

##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle

Bir durum çubuğu bölmesinin stilini ayarlamak için bu üye işlevini çağırın.

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Dizin bölmesinin stilini ayarlanması sağlamaktır.

*nStyle*<br/>
Stil bölmesinin stilini ayarlanması sağlamaktır.

### <a name="remarks"></a>Açıklamalar

Nasıl bölmesi görünür bir bölmesinin stilini belirler.

Durum çubukları için kullanılabilir stilleri bir listesi için bkz. [SetPaneInfo](#setpaneinfo).

##  <a name="setpanetext"></a>  CStatusBar::SetPaneText

İşaret ettiği dizeyi bölmesinde metnini ayarlamak için bu üye işlevi çağrısı *lpszNewText*.

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Ayarlanacak metni olan bölmesinde dizini.

*lpszNewText*<br/>
Yeni bölmesinde metin işaretçisi.

*bgüncelleştirmesinin*<br/>
TRUE ise metin ayarlandıktan sonra bölmesinde geçersiz kılınır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra `SetPaneText`, yeni metin durum çubuğunda görüntülemek için bir kullanıcı arabirimini güncelleştirme işleyicisi eklemeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek CTRLBARS](../../visual-cpp-samples.md)<br/>
[MFC örnek DLGCBR32](../../visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStatusBarCtrl Sınıfı](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
