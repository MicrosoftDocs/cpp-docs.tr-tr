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
ms.openlocfilehash: 7ab6a240a403e70446ebc1860474f6cb9e1d71e3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504768"
---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl sınıfı

Tarih ve saat seçici denetimi içeren bir araç çubuğu düğmesi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl:: CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|Bir `CMFCToolBarDateTimeCtrl` nesnesi oluşturur.|
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl:: Canbeesnetilen](#canbestretched)|Kullanıcının özelleştirme sırasında düğmeyi uzatılamayacağını belirtir. ( [CMFCToolBarButton:: Canbeesnei](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)geçersiz kılar.)|
|[CMFCToolBarDateTimeCtrl:: CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar. ( [CMFCToolBarButton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Daha sonraki kullanımlar için ayrılmıştır.|
|[CMFCToolBarButton:: Exporttomenubtan](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Araç çubuğu düğmesinden bir menüye metin kopyalar.|
|`CMFCToolBarDateTimeCtrl::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|[CMFCToolBarDateTimeCtrl:: GetByCmd](#getbycmd)|Uygulamadaki belirtilen komut `CMFCToolBarDateTimeCtrl` kimliğine sahip ilk nesneyi alır.|
|[CMFCToolBarDateTimeCtrl:: GetDateTimeCtrl](#getdatetimectrl)|Tarih ve saat Seçici denetimine bir işaretçi döndürür.|
|[CMFCToolBarDateTimeCtrl:: GetHwnd](#gethwnd)|Araç çubuğu düğmesiyle ilişkili pencere tanıtıcısını alır. ( [CMFCToolBarButton:: GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).) öğesini geçersiz kılar|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCToolBarDateTimeCtrl:: GetTime](#gettime)|Tarih ve saat seçici denetiminden seçilen saati alır ve belirtilen bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına koyar.|
|[CMFCToolBarDateTimeCtrl:: GetTimeAll](#gettimeall)|Belirtilen komut KIMLIĞINE sahip olan zaman Seçicisi denetim düğmesinden seçilen saati döndürür.|
|[CMFCToolBarDateTimeCtrl:: HaveHotBorder](#havehotborder)|Kullanıcı düğmeyi seçtiğinde düğme kenarlığının görüntülenip görüntülenmeyeceğini belirler. ( [CMFCToolBarButton:: HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder)geçersiz kılar.)|
|[CMFCToolBarDateTimeCtrl:: NotifyCommand](#notifycommand)|Düğmenin [WM_COMMAND](/windows/win32/menurc/wm-command) iletisini işlemediğini belirtir. ( [CMFCToolBarButton:: NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).) öğesini geçersiz kılar|
|[CMFCToolBarDateTimeCtrl:: OnAddToCustomizePage](#onaddtocustomizepage)|Düğme bir **Özelleştirme** iletişim kutusuna eklendiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).) öğesini geçersiz kılar|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Belirtilen cihaz bağlamı ve yerleştirme durumu için düğmenin boyutunu hesaplamak üzere Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).) öğesini geçersiz kılar|
|[CMFCToolBarDateTimeCtrl:: OnChangeParentWnd](#onchangeparentwnd)|Düğme yeni bir araç çubuğuna eklendiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)geçersiz kılar.)|
|[CMFCToolBarDateTimeCtrl:: OnClick](#onclick)|Kullanıcı denetime tıkladığında Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)geçersiz kılar.)|
|[CMFCToolBarDateTimeCtrl:: OnCtlColor](#onctlcolor)|Ana araç çubuğu bir WM_CTLCOLOR iletisini işlediğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).) öğesini geçersiz kılar|
|`CMFCToolBarDateTimeCtrl::OnDraw`|Belirtilen stilleri ve seçenekleri kullanarak düğmeyi çizmek için Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw)geçersiz kılar.)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|**Özelleştirme** Iletişim kutusunun **Komutlar** bölmesinde düğme çizmek için Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).) öğesini geçersiz kılar|
|[CMFCToolBarDateTimeCtrl:: OnGlobalFontsChanged](#onglobalfontschanged)|Genel yazı tipi değiştirildiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)geçersiz kılınır.)|
|[CMFCToolBarDateTimeCtrl:: OnMove](#onmove)|Ana araç çubuğu taşırken Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)geçersiz kılar.)|
|[CMFCToolBarDateTimeCtrl:: OnShow](#onshow)|Düğme görünür veya görünmez hale geldiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).) öğesini geçersiz kılar|
|`CMFCToolBarDateTimeCtrl::OnSize`|Ana araç çubuğu boyutunu veya konumunu değiştirdiğinde Framework tarafından çağırılır ve bu değişiklik düğmenin boyutunu değiştirmesine neden olur. ( [CMFCToolBarButton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)geçersiz kılar.)|
|[CMFCToolBarDateTimeCtrl:: OnUpdateToolTip](#onupdatetooltip)|Ana araç çubuğu kendi araç ipucu metnini güncelleştirdiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)' i geçersiz kılar.)|
|`CMFCToolBarDateTimeCtrl::Serialize`|Bu nesneyi bir arşivden okur veya bir arşive yazar, ( [CMFCToolBarButton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)geçersiz kılar)|
|`CMFCToolBarDateTimeCtrl::SetStyle`|Araç çubuğu düğmesinin stilini ayarlar. ( [CMFCToolBarButton:: SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)geçersiz kılar)|
|[CMFCToolBarDateTimeCtrl:: SetTime](#settime)|Saat seçici denetimindeki saat ve tarihi ayarlar.|
|[CMFCToolBarDateTimeCtrl:: SetTimeAll](#settimeall)|Belirli bir komut KIMLIĞINE sahip olan zaman seçici denetiminin tüm örneklerinde saat ve Tarih ayarlar.|

## <a name="remarks"></a>Açıklamalar

Tarih ve saat seçici denetiminin nasıl kullanılacağına ilişkin bir örnek için, bkz. ToolbarDateTimePicker örnek projesi. Araç çubuklarına denetim düğmeleri ekleme hakkında daha fazla bilgi için bkz [. İzlenecek yol: Denetimleri araç çubuklarına](../../mfc/walkthrough-putting-controls-on-toolbars.md)yerleştirme.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbardatetimectrl. h

##  <a name="canbestretched"></a>CMFCToolBarDateTimeCtrl:: Canbeesnetilen

Kullanıcının özelleştirme sırasında düğmeyi uzatılamayacağını belirtir.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve özelleştirme sırasında kullanıcının bir araç çubuğu düğmesini uzamasına izin vermez. Bu yöntem, kullanıcının özelleştirme sırasında bir tarih ve saat araç çubuğu düğmesini genişlemesine izin vererek temel sınıf uygulamasını ( [CMFCToolBarButton:: Canbeesnetilmiş](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) genişletir.

##  <a name="cmfctoolbardatetimectrl"></a>CMFCToolBarDateTimeCtrl:: CMFCToolBarDateTimeCtrl

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) nesnesini oluşturur ve başlatır.

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>Parametreler

*Uııd*<br/>
'ndaki Denetim KIMLIĞI.

*IImage*<br/>
'ndaki Araç çubuğunun `CMFCToolBarImages` nesnesindeki görüntünün dizini.

*dwStyle*<br/>
'ndaki Kullanıcı düğmeye tıkladığında oluşturulan `CMFCToolBarDateTimeCtrlImpl` pencerenin stili.

*ıwidth*<br/>
'ndaki Denetimin genişliği (piksel cinsinden).

### <a name="remarks"></a>Açıklamalar

Bu nesne, sistem tarihi ve saatine göre başlatılır. İç `CMFCToolBarDateTimeCtrlImpl` nesnenin pencere stili, *dwStyle* parametresini ve WS_CHILD ve WS_VISIBLE stillerini içerir. Bu stilleri kullanarak `CMFCToolBarDateTimeCtrl::SetStyle`değiştiremezsiniz. Denetimin`CMFCToolBarDateTimeCtrl` stilini değiştirmek için kullanın `SetStyle` .

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCToolBarDateTimeCtrl` sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir. Bu kod parçacığı, [araç çubuğu tarih saat seçici örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

##  <a name="copyfrom"></a>CMFCToolBarDateTimeCtrl:: CopyFrom

Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*YN*<br/>
'ndaki Kopyalanacak kaynak düğmesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu araç çubuğu düğmesine başka bir araç çubuğu düğmesi kopyalamak için bu yöntemi çağırın. *src* türünde `CMFCToolBarDateTimeCtrl`olmalıdır.

##  <a name="exporttomenubutton"></a>CMFCToolBarDateTimeCtrl:: Exporttomenubtan

Araç çubuğu düğmesinden bir menüye metin kopyalar.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parametreler

*menuButton*<br/>
'ndaki Hedef menü düğmesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetimin komut KIMLIĞIYLE ilişkili dize kaynağını yükleyerek temel sınıf uygulamasını ( [CMFCToolBarButton:: Exporttomenubtan](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) geçersiz kılar. Dize kaynakları hakkında daha fazla bilgi için bkz. [CStringT:: LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).

##  <a name="getbycmd"></a>CMFCToolBarDateTimeCtrl:: GetByCmd

Uygulamadaki belirtilen komut `CMFCToolBarDateTimeCtrl` kimliğine sahip ilk nesneyi alır.

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Alınacak düğmenin komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komut `CMFCToolBarDateTimeCtrl` kimliğine sahip uygulamadaki ilk nesne veya belirtilen komut kimliğine sahip olmayan bir `CMFCToolBarDateTimeCtrl` nesne yoksa null.

### <a name="remarks"></a>Açıklamalar

Bu paylaşılan yardımcı program yöntemi, belirli bir komut KIMLIĞINE sahip olan zaman seçici denetiminin tüm örneklerinin saat ve tarihini ayarlamak veya almak için [CMFCToolBarDateTimeCtrl:: SetTimeAll](#settimeall) ve [CMFCToolBarDateTimeCtrl:: GetTimeAll](#gettimeall) gibi yöntemler tarafından kullanılır.

##  <a name="getdatetimectrl"></a>CMFCToolBarDateTimeCtrl:: GetDateTimeCtrl

Tarih ve saat Seçici denetimine bir işaretçi döndürür.

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saat Seçici denetimine yönelik bir işaretçi; ya da denetim yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bir araç çubuğuna `CMFCToolBarDateTimeCtrl` nesne `m_pWndDateTime` eklediğinizde, sınıfveriüyesinibaşlatır.`CMFCToolBarDateTimeCtrl`

##  <a name="gethwnd"></a>CMFCToolBarDateTimeCtrl:: GetHwnd

Araç çubuğu düğmesiyle ilişkili pencere tanıtıcısını alır.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saat araç çubuğu düğmesiyle ilişkilendirilen pencere tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CMFCToolBarButton:: GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) metodunu geçersiz kılar.

##  <a name="gettime"></a>CMFCToolBarDateTimeCtrl:: GetTime

İlişkili tarih ve saat seçici denetiminden seçilen saati alır ve belirtilen bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına koyar

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Parametreler

*timeDest*<br/>
dışı İlk aşırı yüklemede, sistem saati bilgilerini alacak bir [Coeldatetime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi. İkinci aşırı yüklemede, sistem saati bilgilerini alacak bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi.

*pTimeDest*<br/>
dışı Sistem saati bilgilerini almak için [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi. NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yüklemede, zaman [Colandatetime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine başarıyla yazılmışsa, sıfır dışında; Aksi takdirde 0. İkinci ve üçüncü aşırı yüklerde, dönüş değeri, [Nmdatetimechange](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) yapısında ayarlanan dwFlag üyesine eşit olan bir DWORD değeridir.

### <a name="remarks"></a>Açıklamalar

Yöntemi, tarih ve saat seçicisinin tarih ve saat olarak ayarlandığını belirtmek için [Nmdatetimechange](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) yapısı üye dwFlags değerini ayarlar. Değer GDT_NONE eşitse, Denetim `no date` Status olarak ayarlanır ve DTS_SHOWNONE stilini kullanır. Döndürülen değer GDT_VALID eşitse, sistem saati hedef konumda başarıyla depolanır.

##  <a name="gettimeall"></a>CMFCToolBarDateTimeCtrl:: GetTimeAll

Belirtilen komut KIMLIĞINE sahip olan zaman Seçicisi denetim düğmesinden Kullanıcı tarafından seçilen zamanı döndürür.

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

*Uımd*<br/>
'ndaki Bir araç çubuğu düğmesinin komut KIMLIĞINI belirtir.

*timeDest*<br/>
dışı İlk aşırı yüklemede, sistem saati bilgilerini alacak bir [Coeldatetime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi. İkinci aşırı yüklemede, sistem saati bilgilerini alacak bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi.

*pTimeDest*<br/>
dışı Sistem saati bilgilerini almak için [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi. NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

Çerçeve, *Uıicmd*komut kimliğiyle eşleşen bir araç çubuğu düğmesi bulamazsa, ilk aşırı yüklemede döndürülen değer sıfırdır ve diğer aşırı yüklerde GDT_NONE. Araç çubuğu düğmesi bulunursa, dönüş değeri, Bu düğmedeki [CMFCToolBarDateTimeCtrl:: GetTime](#gettime) çağrısından gelen dönüş değeri ile aynıdır. Bir diğer nedenle geçerli bir tarih döndürmediğini belirten `GetTime` , düğme bulunduğunda sıfır veya GDT_NONE dönüş değeri oluşabilir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen komut KIMLIĞINE sahip bir araç çubuğu düğmesine bakar ve bu düğme üzerinde [CMFCToolBarDateTimeCtrl:: GetTime](#gettime) yöntemini çağırır.

##  <a name="havehotborder"></a>CMFCToolBarDateTimeCtrl:: HaveHotBorder

Kullanıcı düğmeyi seçtiğinde düğme kenarlığının görüntülenip görüntülenmeyeceğini belirler.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili olduğunda bir düğme kenarlığını görüntülüyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetim görünür durumdaysa sıfır dışında bir değer döndürür.

##  <a name="notifycommand"></a>CMFCToolBarDateTimeCtrl:: NotifyCommand

Düğmenin [WM_COMMAND](/windows/win32/menurc/wm-command) iletisini işlemediğini belirtir.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parametreler

*iNotifyCode*<br/>
'ndaki Komutuyla ilişkili bildirim iletisi.

### <a name="return-value"></a>Dönüş Değeri

Düğme WM_COMMAND iletisini işliyorsa TRUE, iletinin üst araç çubuğu tarafından işlenmesi gerektiğini belirtmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Framework, ana pencereye bir [WM_COMMAND](/windows/win32/menurc/wm-command) iletisi göndermek üzere olduğunda bu yöntemi çağırır.

Bu yöntem, [DTN_DATETIMECHANGE](/windows/win32/Controls/dtn-datetimechange) bildirimini işleyerek temel sınıf uygulamasını ( [CMFCToolBarButton:: NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) genişletir. İç zaman durumunu güncelleştirir ve aynı komut kimlikli tüm `CMFCToolBarDateTimeCtrl` nesnelerin saat özelliğini günceller.

##  <a name="onaddtocustomizepage"></a>CMFCToolBarDateTimeCtrl:: OnAddToCustomizePage

Düğme bir **Özelleştirme** iletişim kutusuna eklendiğinde Framework tarafından çağırılır.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu nesneyle aynı komut KIMLIĞINE sahip herhangi bir araç çubuğundaki ilk tarih ve saat denetiminden özellikleri kopyalayarak, [CMFCToolBarButton:: OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)temel sınıf uygulamasını genişletir. Hiçbir araç çubuğu bu nesneyle aynı komut KIMLIĞINE sahip bir tarih ve saat denetimine sahip değilse, bu yöntem hiçbir şey yapmaz.

**Özelleştirme** iletişim kutusu hakkında daha fazla bilgi için bkz. [CMFCToolBarsCustomizeDialog Class](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

##  <a name="onchangeparentwnd"></a>CMFCToolBarDateTimeCtrl:: OnChangeParentWnd

Düğme yeni bir araç çubuğuna eklendiğinde Framework tarafından çağırılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Yeni üst pencere.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CMFCToolBarDateTimeCtrlImpl` nesneyi yeniden oluşturarak temel sınıf uygulamasını ( [CMFCToolBarButton:: OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) geçersiz kılar.

##  <a name="onclick"></a>CMFCToolBarDateTimeCtrl:: OnClick

Kullanıcı denetime tıkladığında Framework tarafından çağırılır.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Kullanılmayan.

*bDelay*<br/>
'ndaki Kullanılmayan.

### <a name="return-value"></a>Dönüş Değeri

Düğme tıklama iletisini işliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CMFCToolBarDateTimeCtrlImpl` nesne görünür durumdaysa sıfır dışında bir değer döndürerek, [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)temel sınıf uygulamasını geçersiz kılar.

##  <a name="onctlcolor"></a>CMFCToolBarDateTimeCtrl:: OnCtlColor

Ana araç çubuğu bir WM_CTLCOLOR iletisini işlediğinde Framework tarafından çağırılır.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Düğmeyi görüntüleyen cihaz bağlamı.

*nCtlColor*<br/>
'ndaki Kullanılmayan.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin arka planını boyamak için çerçevenin kullandığı küresel fırçaya yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen cihaz bağlamının metin ve arka plan renklerini sırasıyla genel metin ve arka plan renkleriyle ayarlayarak [CMFCToolBarButton:: OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)temel sınıf uygulamasını geçersiz kılar.

Uygulamanız için kullanılabilen genel seçenekler hakkında daha fazla bilgi için bkz. [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onglobalfontschanged"></a>CMFCToolBarDateTimeCtrl:: OnGlobalFontsChanged

Genel yazı tipi değiştirildiğinde Framework tarafından çağırılır.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetimin yazı tipini genel yazı tipi ile değiştirerek temel sınıf uygulamasını ( [CMFCToolBarButton:: OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) genişletir.

Uygulamanız için kullanılabilen genel seçenekler hakkında daha fazla bilgi için bkz. [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onmove"></a>CMFCToolBarDateTimeCtrl:: OnMove

Ana araç çubuğu taşırken Framework tarafından çağırılır.

```
virtual void OnMove();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CMFCToolBarDateTimeCtrlImpl` nesnenin konumunu güncelleştirerek varsayılan sınıf uygulamasını ( [CMFCToolBarButton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) geçersiz kılar.

##  <a name="onshow"></a>CMFCToolBarDateTimeCtrl:: OnShow

Düğme görünür veya görünmez hale geldiğinde Framework tarafından çağırılır.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
'ndaki Düğmenin görünür olup olmadığını belirtir. Bu parametre TRUE ise, düğme görünür olur. Aksi takdirde, düğme görünür değildir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *BSHOW* true ise düğmeyi görüntüleyerek temel sınıf uygulamasını ( [CMFCToolBarButton:: OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) genişletir. Aksi takdirde, bu yöntem düğmeyi gizler.

##  <a name="onsize"></a>CMFCToolBarDateTimeCtrl:: OnSize

Ana araç çubuğu boyutunu veya konumunu değiştirdiğinde Framework tarafından çağırılır ve bu değişiklik düğmenin boyutunu değiştirmesine neden olur.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parametreler

*iSize*<br/>
'ndaki Düğmenin piksel cinsinden yeni genişliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CMFCToolBarDateTimeCtrlImpl` nesnenin boyutunu ve konumunu güncelleştirerek varsayılan sınıf uygulamasını ( [CMFCToolBarButton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) geçersiz kılar.

##  <a name="onupdatetooltip"></a>CMFCToolBarDateTimeCtrl:: OnUpdateToolTip

Ana araç çubuğu kendi araç ipucu metnini güncelleştirdiğinde Framework tarafından çağırılır.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Üst pencere.

*ıbuttonındex*<br/>
'ndaki Ana düğme koleksiyonundaki düğmenin sıfır tabanlı dizini.

*wndToolTip*<br/>
'ndaki Araç ipucu metnini görüntüleyen denetim.

*üstbilgisine*<br/>
dışı Güncelleştirilmiş araç ipucu metnini alan nesne.`CString`

### <a name="return-value"></a>Dönüş Değeri

Yöntem araç ipucu metnini güncelleştirse sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, düğme ile ilişkili araç ipucu metnini görüntüleyerek temel sınıf uygulamasını ( [CMFCToolBarButton:: OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) genişletir. Düğme yatay olarak yerleştirilmemişse, bu yöntem hiçbir şey yapmaz ve FALSE döndürür.

##  <a name="settime"></a>CMFCToolBarDateTimeCtrl:: SetTime

Saat seçici denetimindeki saat ve tarihi ayarlar.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Parametreler

*Timeneni*<br/>
'ndaki İlk sürümde, denetimin ayarlanacağı saati içeren bir [Colandatetime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine bir başvuru. İkinci sürümde, denetimin ayarlanacağı saati içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine yönelik bir işaretçi.

*Ptimeneni*<br/>
'ndaki Denetimin ayarlanacağı saati içeren [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir tarih ve saat seçici denetimindeki süreyi [CDateTimeCtrl:: setTime](../../mfc/reference/cdatetimectrl-class.md#settime)çağırarak ayarlar.

##  <a name="settimeall"></a>CMFCToolBarDateTimeCtrl:: SetTimeAll

Belirli bir komut KIMLIĞINE sahip olan zaman seçici denetiminin tüm örneklerinde saat ve Tarih ayarlar.

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

*Uımd*<br/>
'ndaki Bir araç çubuğu düğmesinin komut KIMLIĞINI belirtir.

*Timeneni*<br/>
'ndaki İlk sürümde, denetimin ayarlanacağı saati içeren bir [Copadatetime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi. İkinci sürümde, denetimin ayarlanacağı saati içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine yönelik bir işaretçi.

*Ptimeneni*<br/>
'ndaki Denetimin ayarlanacağı saati içeren [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen komut KIMLIĞIYLE bir araç çubuğu düğmesine bakar ve [CMFCToolBarDateTimeCtrl:: SetTime](#settime)çağırarak tarih ve saat seçici denetimindeki saati ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
