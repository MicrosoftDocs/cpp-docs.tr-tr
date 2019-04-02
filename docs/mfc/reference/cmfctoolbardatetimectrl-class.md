---
title: CMFCToolBarDateTimeCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
helpviewer_keywords:
- CMFCToolBarDateTimeCtrl [MFC], CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], CanBeStretched
- CMFCToolBarDateTimeCtrl [MFC], CopyFrom
- CMFCToolBarButton [MFC], ExportToMenuButton
- CMFCToolBarDateTimeCtrl [MFC], GetByCmd
- CMFCToolBarDateTimeCtrl [MFC], GetDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], GetHwnd
- CMFCToolBarDateTimeCtrl [MFC], GetTime
- CMFCToolBarDateTimeCtrl [MFC], GetTimeAll
- CMFCToolBarDateTimeCtrl [MFC], HaveHotBorder
- CMFCToolBarDateTimeCtrl [MFC], NotifyCommand
- CMFCToolBarDateTimeCtrl [MFC], OnAddToCustomizePage
- CMFCToolBarDateTimeCtrl [MFC], OnChangeParentWnd
- CMFCToolBarDateTimeCtrl [MFC], OnClick
- CMFCToolBarDateTimeCtrl [MFC], OnCtlColor
- CMFCToolBarDateTimeCtrl [MFC], OnGlobalFontsChanged
- CMFCToolBarDateTimeCtrl [MFC], OnMove
- CMFCToolBarDateTimeCtrl [MFC], OnShow
- CMFCToolBarDateTimeCtrl [MFC], OnUpdateToolTip
- CMFCToolBarDateTimeCtrl [MFC], SetTime
- CMFCToolBarDateTimeCtrl [MFC], SetTimeAll
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
ms.openlocfilehash: dfe1d3dc058371dd13cc335968b9c3a89e057da2
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776056"
---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl sınıfı

Bir tarih ve Saat Seçici denetimini içeren bir araç çubuğu düğmesi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|Oluşturur bir `CMFCToolBarDateTimeCtrl` nesne.|
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|Bir kullanıcı, düğme özelleştirme sırasında esnetme olup olmadığını belirtir. (Geçersiz kılmaları [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesi özelliklerini geçerli düğmeyi kopyalar. (Geçersiz kılmaları [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Daha sonraki kullanımlar için ayrılmıştır.|
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Menüye araç çubuğu düğmesi metni kopyalar.|
|`CMFCToolBarDateTimeCtrl::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|İlk alır `CMFCToolBarDateTimeCtrl` belirtilen komut kimliği olan bir uygulama nesnesi|
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Tarih ve Saat Seçici denetimine bir işaretçi döndürür.|
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Araç çubuğu düğmesi ile ilişkili olan bir pencere tutucu alır. (Geçersiz kılmaları [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Bir tarih ve saat seçici denetimi seçili zaman alır ve belirtilen koyar [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) yapısı.|
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Saat Seçici denetimini düğmesinden belirtilen komut kimliği vardır. seçilen zamanda döndürür|
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Bir kullanıcı bir düğmeyi seçtiğinde düğme bir kenarlık görüntülenip görüntülenmeyeceğini belirler. (Geçersiz kılmaları [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|Düğme işler olup olmadığını belirtir [WM_COMMAND](/windows/desktop/menurc/wm-command) ileti. (Geçersiz kılmaları [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|Framework tarafından düğmenin eklendiğinde çağırılır bir **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Yerleştirme durumu ve belirtilen bir cihaz bağlamı için düğmenin boyutunu hesaplamak için framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Yeni bir araç çubuğu düğmesi eklendiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Kullanıcı denetime tıkladığında framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|Üst araç çubuğunda WM_CTLCOLOR iletisi işlediğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarDateTimeCtrl::OnDraw`|Belirtilen stillerini ve seçeneklerini kullanarak bir düğme çizmek için framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Düğme çizim için framework tarafından çağırılır **komutları** bölmesinde **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|Genel yazı tipi değiştiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Üst araç çubuğunda hareket ettiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|Düğme olduğunda görünür veya gizli framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|`CMFCToolBarDateTimeCtrl::OnSize`|Üst araç çubuğunda boyutunu değiştirir veya konumu ve bu değişiklik neden boyutunu değiştirmek düğmeyi framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Üst araç çubuğunda, araç ipucu metni güncelleştirdiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarDateTimeCtrl::Serialize`|Bu nesne bir arşivden okur veya arşive, yazar (geçersiz kılmaları [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarDateTimeCtrl::SetStyle`|Araç çubuğu düğmesini stilini ayarlar. (Geçersiz kılmaları [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|Tarih Saat Seçici denetiminde ayarlar.|
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Tarih ve saat belirtilen komut kimliği olan tüm durumlarda saat seçici denetimi değerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

ToolbarDateTimePicker örnek proje bir tarih ve Saat Seçici denetimini kullanma örneği için bkz. Araç çubuklarına denetimi düğmeleri ekleme hakkında daha fazla bilgi için bkz: [izlenecek yol: Araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtoolbardatetimectrl.h

##  <a name="canbestretched"></a>  CMFCToolBarDateTimeCtrl::CanBeStretched

Bir kullanıcı, düğme özelleştirme sırasında esnetme olup olmadığını belirtir.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem, TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve sırasında özelleştirme araç çubuğu düğmesi uzatmak kullanıcı izin vermiyor. Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) kullanıcının bir tarih ve saat araç çubuğu düğmesini özelleştirme sırasında esnetme sağlayarak.

##  <a name="cmfctoolbardatetimectrl"></a>  CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl

Oluşturur ve başlatır bir [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) nesne.

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[in] Denetim kimliği.

*iImage*<br/>
[in] Araç çubuğunun, görüntünün dizinini `CMFCToolBarImages` nesne.

*dwStyle*<br/>
[in] Stilini `CMFCToolBarDateTimeCtrlImpl` pencere, kullanıcı düğmeye tıkladığında oluşturulur.

*iWidth*<br/>
[in] Denetimin piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

Bu nesne için sistem tarihi ve saati başlatılır. Pencere stili iç `CMFCToolBarDateTimeCtrlImpl` nesneyi içeren *dwStyle* parametresi ve WS_CHILD ve ws_vısıble stilleri. Bu stiller değiştiremezsiniz `CMFCToolBarDateTimeCtrl::SetStyle`. Kullanım `SetStyle` stilini değiştirmek için `CMFCToolBarDateTimeCtrl` denetimi.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCToolBarDateTimeCtrl` sınıfı. Bu kod parçacığı parçasıdır [araç tarih saat Seçici örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

##  <a name="copyfrom"></a>  CMFCToolBarDateTimeCtrl::CopyFrom

Başka bir araç çubuğu düğmesi özelliklerini geçerli düğmeyi kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[in] Kopyalanacak kaynak düğmesini başvuru.

### <a name="remarks"></a>Açıklamalar

Bu araç çubuğu düğmesi için başka bir araç çubuğu düğmesini kopyalama için bu yöntemi çağırın. *src* türünde olmalıdır `CMFCToolBarDateTimeCtrl`.

##  <a name="exporttomenubutton"></a>  CMFCToolBarDateTimeCtrl::ExportToMenuButton

Menüye araç çubuğu düğmesi metni kopyalar.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parametreler

*MenuButton*<br/>
[in] Hedef menü düğmesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem, TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu metodu geçersiz kılar ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) tarafından denetim komut kimliği ile ilişkili dize kaynağı yükleniyor. Dize kaynakları hakkında daha fazla bilgi için bkz: [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).

##  <a name="getbycmd"></a>  CMFCToolBarDateTimeCtrl::GetByCmd

İlk alır `CMFCToolBarDateTimeCtrl` belirtilen komut kimliği olan bir uygulama nesnesi

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[in] Komut Kimliği Al düğmesi.

### <a name="return-value"></a>Dönüş Değeri

İlk `CMFCToolBarDateTimeCtrl` Hayır ise belirtilen komut kimliği veya boş olan uygulamayı nesnesinde `CMFCToolBarDateTimeCtrl` nesneler sahip belirtilen komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu paylaşılan yardımcı yöntem gibi yöntemler tarafından kullanılan [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) ve [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) ayarlayın veya zaman tüm örneklerinin tarih ve saat Belirtilen komut kimliğine sahip seçici denetimi

##  <a name="getdatetimectrl"></a>  CMFCToolBarDateTimeCtrl::GetDateTimeCtrl

Tarih ve Saat Seçici denetimine bir işaretçi döndürür.

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saat seçici denetimi için bir işaretçi; ya da denetimi mevcut değilse NULL.

### <a name="remarks"></a>Açıklamalar

`CMFCToolBarDateTimeCtrl` Sınıfı başlatır `m_pWndDateTime` eklediğinizde veri üyesi bir `CMFCToolBarDateTimeCtrl` nesnesine bir araç.

##  <a name="gethwnd"></a>  CMFCToolBarDateTimeCtrl::GetHwnd

Araç çubuğu düğmesi ile ilişkili olan bir pencere tutucu alır.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saat araç çubuğu düğmesi ile ilişkili pencere tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bu metot geçersiz kılmaları [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) yöntemi.

##  <a name="gettime"></a>  CMFCToolBarDateTimeCtrl::GetTime

Seçilen zamanda ilişkili tarih ve Saat Seçici denetiminin alır ve belirtilen koyar [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) yapısı

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Parametreler

*timeDest*<br/>
[out] İlk aşırı yükleme içinde bir [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) sistem saat bilgilerini alacak nesne. İkinci aşırı yükleme, bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) sistem saat bilgilerini alacak nesne.

*pTimeDest*<br/>
[out] Bir işaretçi [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) sistem saat bilgilerini almak için yapısı. NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yükleme, zaman başarıyla yazılır, sıfır olmayan, [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) nesne; Aksi durumda 0. İkinci ve üçüncü aşırı belirlenip dwFlag üye eşit olan bir DWORD dönüş değeri olduğu [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) yapısı.

### <a name="remarks"></a>Açıklamalar

Yöntem kümeleri [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) yapı üyesi CertOpenStore tarih ve Saat Seçici bir tarih ve saat için ayarlanmış olup olmadığını belirtmek için. Değer GDT_NONE eşitse, denetimin kümesine `no date` durumu ve DTS_SHOWNONE stili kullanır. Döndürülen değer GDT_VALID eşitse, sistem saati başarıyla hedef konumda depolanır.

##  <a name="gettimeall"></a>  CMFCToolBarDateTimeCtrl::GetTimeAll

Belirtilen komut kimliğe sahip zaman seçici denetimi düğmesini kullanıcı tarafından seçilen noktaya döndürür

```
static BOOL GetTimeAll(
    UINT uiCmd,
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeDest);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[in] Bir araç çubuğu düğmesinin komut kimliğini belirtir.

*timeDest*<br/>
[out] İlk aşırı yükleme içinde bir [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) sistem saat bilgilerini alacak nesne. İkinci aşırı yükleme, bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) sistem saat bilgilerini alacak nesne.

*pTimeDest*<br/>
[out] Bir işaretçi [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) sistem saat bilgilerini almak için yapısı. NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

Framework komut kimlik eşleştiren bir araç çubuğu düğmesi bulamazsanız *uiCmd*, ilk aşırı yükleme sıfır ve diğer aşırı yüklemeler de GDT_NONE değer döndürülür. Araç çubuğu düğmesini bulunursa, dönüş değeri bir çağrıdan dönüş değeri aynıdır [CMFCToolBarDateTimeCtrl::GetTime](#gettime) bu düğmesine. Dönüş değeri sıfır veya GDT_NONE düğmesi, olduğunu belirten bulunduğunda oluşabilir çağrısı `GetTime` diğer bir neden için geçerli bir tarih döndürmedi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem çağrıları ve belirtilen komut kimliği olan bir araç çubuğu düğmesi görünür [CMFCToolBarDateTimeCtrl::GetTime](#gettime) bu düğmeyi yöntemi.

##  <a name="havehotborder"></a>  CMFCToolBarDateTimeCtrl::HaveHotBorder

Bir kullanıcı bir düğmeyi seçtiğinde düğme bir kenarlık görüntülenip görüntülenmeyeceğini belirler.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir düğme seçildiğinde kenarlığını görüntüler olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Denetimin görünür olması halinde bu yöntem, sıfır olmayan bir değer döndürür.

##  <a name="notifycommand"></a>  CMFCToolBarDateTimeCtrl::NotifyCommand

Düğme işler olup olmadığını belirtir [WM_COMMAND](/windows/desktop/menurc/wm-command) ileti.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parametreler

*iNotifyCode*<br/>
[in] Komutu ile ilişkili bir uyarı iletisi.

### <a name="return-value"></a>Dönüş Değeri

WM_COMMAND ileti veya yanlış ileti üst araç tarafından ele alınması gerektiğini göstermek için düğmeyi işler TRUE.

### <a name="remarks"></a>Açıklamalar

Göndermek üzere olduğunda framework bu yöntemi çağıran bir [WM_COMMAND](/windows/desktop/menurc/wm-command) üst penceresine ileti.

Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) işleme tarafından [dtn_datetımechange](/windows/desktop/Controls/dtn-datetimechange) bildirim. İç zaman durumunu güncelleştirir ve tüm zaman özellik güncelleştirmeleri `CMFCToolBarDateTimeCtrl` nesnelerle aynı komut kimliği.

##  <a name="onaddtocustomizepage"></a>  CMFCToolBarDateTimeCtrl::OnAddToCustomizePage

Framework tarafından düğmenin eklendiğinde çağırılır bir **Özelleştir** iletişim kutusu.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), göre ilk tarihten özelliklerini kopyalama ve bu nesneninkiyle aynı komutu Kimliğine sahip herhangi bir araç çubuğu denetiminde zaman. Bu yöntem, hiçbir araç bu nesneninkiyle aynı komut kimliği olan bir tarih ve saat denetim varsa, hiçbir şey yapmaz.

Hakkında daha fazla bilgi için **Özelleştir** iletişim kutusu, bkz: [CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

##  <a name="onchangeparentwnd"></a>  CMFCToolBarDateTimeCtrl::OnChangeParentWnd

Yeni bir araç çubuğu düğmesi eklendiğinde framework tarafından çağırılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[in] Yeni üst pencere.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu metodu geçersiz kılar ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) iç yeniden tarafından `CMFCToolBarDateTimeCtrlImpl` nesne.

##  <a name="onclick"></a>  CMFCToolBarDateTimeCtrl::OnClick

Kullanıcı denetime tıkladığında framework tarafından çağırılır.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
[in] Kullanılmayan.

*bDelay*<br/>
[in] Kullanılmayan.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin click iletiyi işler olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu metodu geçersiz kılar [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), sıfır dışında bir değeri varsa döndürerek iç `CMFCToolBarDateTimeCtrlImpl` nesne görünür.

##  <a name="onctlcolor"></a>  CMFCToolBarDateTimeCtrl::OnCtlColor

Üst araç çubuğunda WM_CTLCOLOR iletisi işlediğinde framework tarafından çağırılır.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Düğme görüntüler cihaz bağlamı.

*nCtlColor*<br/>
[in] Kullanılmayan.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin arka plan boyama için framework kullanan genel fırçasına tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu metodu geçersiz kılar [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor), göre metin ayarlama ve arka plan genel metin için sağlanan cihaz bağlamının renkleri ve arka plan renklerini, sırasıyla.

Uygulamanız için mevcut olan genel seçenekleri hakkında daha fazla bilgi için bkz. [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onglobalfontschanged"></a>  CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged

Genel yazı tipi değiştiğinde framework tarafından çağırılır.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) genel yazı tipini, yazı tipini denetimi değiştirerek.

Uygulamanız için mevcut olan genel seçenekleri hakkında daha fazla bilgi için bkz. [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onmove"></a>  CMFCToolBarDateTimeCtrl::OnMove

Üst araç çubuğunda hareket ettiğinde framework tarafından çağırılır.

```
virtual void OnMove();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan sınıf uygulamasını bu metodu geçersiz kılar ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) iç konumunu güncelleştirerek `CMFCToolBarDateTimeCtrlImpl` nesne.

##  <a name="onshow"></a>  CMFCToolBarDateTimeCtrl::OnShow

Düğme olduğunda görünür veya gizli framework tarafından çağırılır.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bBilgi Göster*<br/>
[in] Düğmenin görünür olup olmadığını belirtir. Bu parametre TRUE ise, düğmeyi görülebilir. Aksi halde düğme görünür değil.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)), düğmeyi görüntüleyerek *bBilgi Göster* true'dur. Aksi takdirde, bu yöntem düğmesi gizlenir.

##  <a name="onsize"></a>  CMFCToolBarDateTimeCtrl::OnSize

Üst araç çubuğunda boyutunu değiştirir veya konumu ve bu değişiklik neden boyutunu değiştirmek düğmeyi framework tarafından çağırılır.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parametreler

*iSize*<br/>
[in] Yeni piksel cinsinden düğmenin genişliği.

### <a name="remarks"></a>Açıklamalar

Varsayılan sınıf uygulamasını bu metodu geçersiz kılar ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) boyutunu ve konumunu iç güncelleştirerek `CMFCToolBarDateTimeCtrlImpl` nesne.

##  <a name="onupdatetooltip"></a>  CMFCToolBarDateTimeCtrl::OnUpdateToolTip

Üst araç çubuğunda, araç ipucu metni güncelleştirdiğinde framework tarafından çağırılır.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[in] Üst pencere.

*iButtonIndex*<br/>
[in] Düğmenin üst düğme koleksiyondaki sıfır tabanlı dizini.

*wndToolTip*<br/>
[in] Araç ipucu metnini görüntüleyen denetim.

*str*<br/>
[out] A `CString` güncelleştirilmiş araç ipucunu alan nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Araç İpucu metni yöntemi güncelleştirmeleri olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) görüntüleyerek düğmesi ile ilişkili olan araç ipucu metni. Düğmenin yatay olarak yuvalanmış değilse bu yöntem, hiçbir şey yapmaz ve false değerini döndürür.

##  <a name="settime"></a>  CMFCToolBarDateTimeCtrl::SetTime

Tarih Saat Seçici denetiminde ayarlar.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Parametreler

*timeNew*<br/>
[in] İlk sürümünde, bir başvuru bir [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) için Denetim ayarlanacak zaman içeren nesne. İkinci sürümünde, bir işaretçi bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) olduğu denetim ayarlanacak zaman içeren nesne.

*pTimeNew*<br/>
[in] Bir işaretçi [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) için Denetim ayarlanacak zamanı içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırarak bir tarih ve Saat Seçici denetiminde süreyi ayarlar [CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime).

##  <a name="settimeall"></a>  CMFCToolBarDateTimeCtrl::SetTimeAll

Tarih ve saat belirtilen komut kimliği olan tüm durumlarda saat seçici denetimi değerini ayarlar.

```
static BOOL SetTimeAll(
    UINT uiCmd,
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[in] Bir araç çubuğu düğmesinin komut kimliğini belirtir.

*timeNew*<br/>
[in] İlk sürümünde, bir [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) için Denetim ayarlanacak zaman içeren nesne. İkinci sürümünde, bir işaretçi bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) olduğu denetim ayarlanacak zaman içeren nesne.

*pTimeNew*<br/>
[in] Bir işaretçi [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) için Denetim ayarlanacak zamanı içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen komut kimliği ile bir araç çubuğu düğmesi arar ve çağırarak bir tarih ve Saat Seçici denetiminde süreyi ayarlar [CMFCToolBarDateTimeCtrl::SetTime](#settime).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[İzlenecek yol: Araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
