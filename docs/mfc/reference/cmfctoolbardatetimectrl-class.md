---
title: CMFCToolBarDateTimeCtrl Sınıfı
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
ms.openlocfilehash: 9aebd55f19a6687554d8d8378ef84ed5932025a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372172"
---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl Sınıfı

Tarih ve saat seçici denetimi içeren araç çubuğu düğmesi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CMFCToolBarTimeCtrl](#cmfctoolbardatetimectrl)|Bir `CMFCToolBarDateTimeCtrl` nesne inşa eder.|
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|Özelleştirme sırasında bir kullanıcının düğmeyi esnetleyip genişletemeyeceğini belirtir. [(Overrides CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar. [(CMFCToolBarButton geçersiz kılar::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Daha sonraki kullanımlar için ayrılmıştır.|
|[CMFCToolBarButton::ExporttomenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Araç çubuğu düğmesinden menüye metni kopyalar.|
|`CMFCToolBarDateTimeCtrl::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|Belirtilen komut `CMFCToolBarDateTimeCtrl` kimliğine sahip uygulamada ilk nesneyi alır.|
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Tarih ve saat seçici denetimine bir işaretçi döndürür.|
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Araç çubuğu düğmesiyle ilişkili pencere tutamacını alır. (Geçersiz kılar [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Seçilen saati bir tarih ve saat seçici denetiminden alır ve belirli bir [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına koyar.|
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Belirtilen komut kimliğine sahip zaman seçici denetim düğmesinden seçilen zamanı döndürür.|
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Kullanıcı düğmeyi seçtiğinde düğmenin kenarlığı görüntülenip görüntülenmediğini belirler. (Geçersiz kılar [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarDateTimeCtrl::Komut Bildir](#notifycommand)|Düğmenin [WM_COMMAND](/windows/win32/menurc/wm-command) iletiyi çalışıp belirtir. [(CMFCToolBarButton geçersiz kılar::Command Command](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|**Özelleştir** iletişim kutusuna düğme eklendiğinde çerçeve tarafından çağrılır. [(CmFCToolBarButton geçersiz kılar::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Belirtilen aygıt bağlamı ve yerleştirme durumu için düğmenin boyutunu hesaplamak için çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Düğme yeni bir araç çubuğuna takıldığında çerçeve tarafından çağrılır. [(Üstyüklemeler CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Kullanıcı denetimi tıklattığında çerçeve tarafından çağrılır. [(Overrides CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|Üst araç çubuğu bir WM_CTLCOLOR iletisi işlediğinde çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarDateTimeCtrl::OnDraw`|Belirtilen stilleri ve seçenekleri kullanarak düğmeyi çizmek için çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|**Özelleştir** iletişim kutusunun **Komutlar** bölmesinde düğmeyi çizmek için çerçeve tarafından çağrılır. [(Overrides CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsDeğiştirildi](#onglobalfontschanged)|Genel yazı tipi değiştiğinde çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Ana araç çubuğu hareket ettiğinde çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarDateTimeCtrl::AçıkGöster](#onshow)|Düğme görünür veya görünmez olduğunda çerçeve tarafından çağrılır. [(CmFCToolBarButton geçersiz kılar::AçıkShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|`CMFCToolBarDateTimeCtrl::OnSize`|Ana araç çubuğu boyutunu veya konumunu değiştirdiğinde ve bu değişiklik düğmenin boyutunu değiştirmesine neden olduğunda çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Üst araç çubuğu araç ipucu metnini güncelleştirirken çerçeve tarafından çağrılır. [(Overrides CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarDateTimeCtrl::Serialize`|Bu nesneyi bir arşivden okur veya arşive yazar, [(CMFCToolBarButton'ı geçersiz kılar::Serialize .)](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)|
|`CMFCToolBarDateTimeCtrl::SetStyle`|Araç çubuğu düğmesinin stilini ayarlar. [(CMFCToolBarButton geçersiz kılar::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|Saat seçici denetiminde saati ve tarihi ayarlar.|
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Belirli bir komut kimliğine sahip zaman seçici denetiminin tüm örneklerinde saati ve tarihi ayarlar.|

## <a name="remarks"></a>Açıklamalar

Tarih ve saat seçici denetiminin nasıl kullanılacağına bir örnek için ToolbarDateTimePicker örnek projesine bakın. Araç çubuklarına denetim düğmeleri nasıl ekleyeceğiniz hakkında bilgi için Bkz. [Walkthrough: Denetimleri Araç Çubuklarına Koyma](../../mfc/walkthrough-putting-controls-on-toolbars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbardatetimectrl.h

## <a name="cmfctoolbardatetimectrlcanbestretched"></a><a name="canbestretched"></a>CMFCToolBarDateTimeCtrl::CanBeStretched

Özelleştirme sırasında bir kullanıcının düğmeyi esnetleyip genişletemeyeceğini belirtir.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve kullanıcıözelleştirme sırasında bir araç çubuğu düğmesini germek için izin vermez. Bu yöntem, kullanıcının özelleştirme sırasında bir tarih ve saat araç çubuğu düğmesini esnetmesine izin vererek taban sınıf uygulamasını [(CMFCToolBarButton::CanBeStretched)](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)genişletir.

## <a name="cmfctoolbardatetimectrlcmfctoolbardatetimectrl"></a><a name="cmfctoolbardatetimectrl"></a>CMFCToolBarDateTimeCtrl::CMFCToolBarTimeCtrl

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) nesnesi oluşturur ve başharfe fünyeler.

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[içinde] Kontrol kimliği.

*ıımage*<br/>
[içinde] Araç çubuğunun `CMFCToolBarImages` nesnesindeki görüntünün dizini.

*Dwstyle*<br/>
[içinde] Kullanıcı düğmeyi `CMFCToolBarDateTimeCtrlImpl` tıklattığında oluşturulan pencerenin stili.

*iGenişlik*<br/>
[içinde] Denetimin genişliği, piksel olarak.

### <a name="remarks"></a>Açıklamalar

Bu nesne sistem tarih ve saatine başharfle başharfe işlenir. İç `CMFCToolBarDateTimeCtrlImpl` nesnenin pencere stili *dwStyle* parametresini ve WS_CHILD ve WS_VISIBLE stilleri içerir. Bu stilleri kullanarak `CMFCToolBarDateTimeCtrl::SetStyle`değiştiremezsiniz. Denetim `SetStyle` in stilini `CMFCToolBarDateTimeCtrl` değiştirmek için kullanın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCToolBarDateTimeCtrl` nasıl inşa edilebildiğini gösterir. Bu kod parçacığı Araç Çubuğu [Tarih Seçici örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

## <a name="cmfctoolbardatetimectrlcopyfrom"></a><a name="copyfrom"></a>CMFCToolBarDateTimeCtrl::CopyFrom

Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[içinde] Kopyalamak için kaynak düğmesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Başka bir araç çubuğu düğmesini bu araç çubuğu düğmesine kopyalamak için bu yöntemi arayın. *src* türünde `CMFCToolBarDateTimeCtrl`olmalıdır.

## <a name="cmfctoolbardatetimectrlexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolBarDateTimeCtrl::ExportToMenuButton

Araç çubuğu düğmesinden menüye metni kopyalar.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parametreler

*menüDüğme*<br/>
[içinde] Hedef menü düğmesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetimin komut kimliğiyle ilişkili dize kaynağını yükleyerek taban sınıf uygulamasını [(CMFCToolBarButton::ExportToMenuButton)](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)geçersiz kılar. Dize kaynakları hakkında daha fazla bilgi için [Bkz. CStringT::LoadString.](../../atl-mfc-shared/reference/cstringt-class.md#loadstring)

## <a name="cmfctoolbardatetimectrlgetbycmd"></a><a name="getbycmd"></a>CMFCToolBarDateTimeCtrl::GetByCmd

Belirtilen komut `CMFCToolBarDateTimeCtrl` kimliğine sahip uygulamada ilk nesneyi alır.

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Alınacak düğmenin komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen `CMFCToolBarDateTimeCtrl` komut kimliğine sahip olan uygulamada ilk nesne `CMFCToolBarDateTimeCtrl` veya belirtilen komut kimliğine sahip olmayan nesneler varsa NULL.

### <a name="remarks"></a>Açıklamalar

Bu paylaşılan yardımcı program yöntemi [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) ve [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) ayarlamak veya belirli bir komut kimliği ne zaman seçici kontrolü tüm örneklerinin zaman ve tarih almak gibi yöntemlerle kullanılır.

## <a name="cmfctoolbardatetimectrlgetdatetimectrl"></a><a name="getdatetimectrl"></a>CMFCToolBarDateTimeCtrl::GetDateTimeCtrl

Tarih ve saat seçici denetimine bir işaretçi döndürür.

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saat seçici denetimi için bir işaretçi; veya denetim yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCToolBarDateTimeCtrl` `CMFCToolBarDateTimeCtrl` nesne araç `m_pWndDateTime` çubuğuna bir nesne eklediğinizde sınıf veri üyesini başlatılmasını.

## <a name="cmfctoolbardatetimectrlgethwnd"></a><a name="gethwnd"></a>CMFCToolBarDateTimeCtrl::GetHwnd

Araç çubuğu düğmesiyle ilişkili pencere tutamacını alır.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saat araç çubuğu düğmesiyle ilişkili pencere tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CMFCToolBarButton geçersiz kılar::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) yöntemi.

## <a name="cmfctoolbardatetimectrlgettime"></a><a name="gettime"></a>CMFCToolBarDateTimeCtrl::GetTime

İlişkili tarih ve saat seçici denetiminden seçilen zamanı alır ve belirli bir [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına koyar

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Parametreler

*timeDest*<br/>
[çıkış] İlk aşırı yüklemede, sistem zaman bilgilerini alacak bir [COleDateTime Class](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi. İkinci aşırı yüklemede, sistem zaman bilgilerini alacak bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi.

*pTimeDest*<br/>
[çıkış] Sistem zaman bilgilerini almak için [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına bir işaretçi. NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

[COleDateTime Class](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine başarıyla yazıldığında, ilk aşırı yüklemede sıfır olmayan; aksi takdirde 0. İkinci ve üçüncü aşırı yüklemelerde, iade değeri [NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) yapısında ayarlanan dwFlag üyesine eşit bir DWORD'dür.

### <a name="remarks"></a>Açıklamalar

Yöntem, tarih ve saat seçicinin tarih ve saat olarak ayarlanıp ayarlanmadığını belirtmek için [NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) yapısı üye dwFlags'i ayarlar. Değer GDT_NONE eşitse, denetim `no date` duruma ayarlanır ve DTS_SHOWNONE stilini kullanır. Döndürülen değer GDT_VALID eşitse, sistem süresi hedef konumda başarıyla depolanır.

## <a name="cmfctoolbardatetimectrlgettimeall"></a><a name="gettimeall"></a>CMFCToolBarDateTimeCtrl::GetTimeAll

Kullanıcı tarafından seçilen süreyi, belirli bir komut kimliğine sahip zaman seçici kontrol düğmesinden döndürür.

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
[içinde] Araç çubuğu düğmesinin komut kimliğini belirtir.

*timeDest*<br/>
[çıkış] İlk aşırı yüklemede, sistem zaman bilgilerini alacak bir [COleDateTime Class](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi. İkinci aşırı yüklemede, sistem zaman bilgilerini alacak bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi.

*pTimeDest*<br/>
[çıkış] Sistem zaman bilgilerini almak için [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına bir işaretçi. NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

Çerçeve komut kimliği *uiCmd*eşleşen bir araç çubuğu düğmesi bulamazsa, iade değeri ilk aşırı yükleme sıfır ve diğer aşırı yüklerde GDT_NONE. Araç çubuğu düğmesi bulunursa, iade değeri [CMFCToolBarTimeCtrl::GetTime](#gettime) bu düğmeye bir çağrıdan dönüş değeri ile aynıdır. Düğme bulunduğunda sıfır veya GDT_NONE dönüş değeri oluşabilir ve bu `GetTime` da çağrının başka bir nedenle geçerli bir tarih döndürmediğini gösterir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen komut kimliğine sahip bir araç çubuğu düğmesini arar ve [CMFCToolBarDateTimeCtrl::GetTime](#gettime) yöntemini bu düğmede arar.

## <a name="cmfctoolbardatetimectrlhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarDateTimeCtrl::HaveHotBorder

Kullanıcı düğmeyi seçtiğinde düğmenin kenarlığı görüntülenip görüntülenmediğini belirler.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir düğme seçildiğinde kenarlığını görüntülerse sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Denetim görünürse, bu yöntem sıfır olmayan bir değer döndürür.

## <a name="cmfctoolbardatetimectrlnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarDateTimeCtrl::Komut Bildir

Düğmenin [WM_COMMAND](/windows/win32/menurc/wm-command) iletiyi çalışıp belirtir.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parametreler

*iNotifyCode*<br/>
[içinde] Komutla ilişkili bildirim iletisi.

### <a name="return-value"></a>Dönüş Değeri

Doğru düğme, iletinin WM_COMMAND işlerse veya iletinin üst araç çubuğu tarafından işletilmesi gerektiğini belirtmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Çerçeve, üst pencereye [WM_COMMAND](/windows/win32/menurc/wm-command) iletisi göndermek üzereyken bu yöntemi çağırır.

Bu [yöntem, DTN_DATETIMECHANGE](/windows/win32/Controls/dtn-datetimechange) bildirimini işleyerek taban sınıf uygulamasını [(CMFCToolBarButton::NotifyCommand)](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)genişletir. Dahili zaman durumunu güncelleştirir ve tüm `CMFCToolBarDateTimeCtrl` nesnelerin zaman özelliğini aynı komut kimliğiyle güncelleştirir.

## <a name="cmfctoolbardatetimectrlonaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarDateTimeCtrl::OnAddToCustomizePage

**Özelleştir** iletişim kutusuna düğme eklendiğinde çerçeve tarafından çağrılır.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu nesneyle aynı komut kimliğine sahip herhangi bir araç çubuğundaki ilk tarih ve saat denetimindeki özellikleri kopyalayarak taban sınıf uygulaması [CMFCToolBarButton::OnAddToCustomizePage'i](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)genişletir. Hiçbir araç çubuğunda bu nesneyle aynı komut kimliğine sahip bir tarih ve saat denetimi varsa, bu yöntem hiçbir işe yarar.

**Özelleştir** iletişim kutusu hakkında daha fazla bilgi için [CMFCToolBarsCustomizeDialog Class'a](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)bakın.

## <a name="cmfctoolbardatetimectrlonchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarDateTimeCtrl::OnChangeParentWnd

Düğme yeni bir araç çubuğuna takıldığında çerçeve tarafından çağrılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Yeni ana pencere.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CMFCToolBarDateTimeCtrlImpl` nesneyi yeniden oluşturarak taban sınıf uygulamasını [(CMFCToolBarButton::OnChangeParentWnd)](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)geçersiz kılar.

## <a name="cmfctoolbardatetimectrlonclick"></a><a name="onclick"></a>CMFCToolBarDateTimeCtrl::OnClick

Kullanıcı denetimi tıklattığında çerçeve tarafından çağrılır.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Kullanılma -yan.

*bGecikme*<br/>
[içinde] Kullanılma -yan.

### <a name="return-value"></a>Dönüş Değeri

Düğme tıklama iletisini işlerse sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CMFCToolBarDateTimeCtrlImpl` nesne görünürse sıfır olmayan bir değer döndürerek taban sınıf uygulaması, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)geçersiz kılar.

## <a name="cmfctoolbardatetimectrlonctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarDateTimeCtrl::OnCtlColor

Üst araç çubuğu bir WM_CTLCOLOR iletisi işlediğinde çerçeve tarafından çağrılır.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Düğmeyi görüntüleyen aygıt bağlamı.

*nCtlColor*<br/>
[içinde] Kullanılma -yan.

### <a name="return-value"></a>Dönüş Değeri

Çerçeve düğmesinin arka planını boyamak için kullandığı genel fırçanın tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, sağlanan aygıt bağlamının metin ve arka plan renklerini sırasıyla genel metin ve arka plan renklerine ayarlayarak taban sınıf uygulaması [CMFCToolBarButton::OnCtlColor'u](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)geçersiz kılar.

Uygulamanızda kullanılabilen genel seçenekler hakkında daha fazla bilgi için [AFX_GLOBAL_DATA Yapısı'na](../../mfc/reference/afx-global-data-structure.md)bakın.

## <a name="cmfctoolbardatetimectrlonglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarDateTimeCtrl::OnGlobalFontsDeğiştirildi

Genel yazı tipi değiştiğinde çerçeve tarafından çağrılır.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetimin yazı tipini genel yazı tipiyle değiştirerek taban sınıf uygulamasını [(CMFCToolBarButton::OnGlobalFontsChanged)](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)genişletir.

Uygulamanızda kullanılabilen genel seçenekler hakkında daha fazla bilgi için [AFX_GLOBAL_DATA Yapısı'na](../../mfc/reference/afx-global-data-structure.md)bakın.

## <a name="cmfctoolbardatetimectrlonmove"></a><a name="onmove"></a>CMFCToolBarDateTimeCtrl::OnMove

Ana araç çubuğu hareket ettiğinde çerçeve tarafından çağrılır.

```
virtual void OnMove();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CMFCToolBarDateTimeCtrlImpl` nesnenin konumunu güncelleştirerek varsayılan sınıf uygulamasını [(CMFCToolBarButton::OnMove)](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)geçersiz kılar.

## <a name="cmfctoolbardatetimectrlonshow"></a><a name="onshow"></a>CMFCToolBarDateTimeCtrl::AçıkGöster

Düğme görünür veya görünmez olduğunda çerçeve tarafından çağrılır.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
[içinde] Düğmenin görünür olup olmadığını belirtir. Bu parametre TRUE ise, düğme görünür. Aksi takdirde, düğme görünmez.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *bShow* DOĞRU ise düğmeyi görüntüleyerek taban sınıf uygulamasını [(CMFCToolBarButton::OnShow)](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)genişletir. Aksi takdirde, bu yöntem düğmeyi gizler.

## <a name="cmfctoolbardatetimectrlonsize"></a><a name="onsize"></a>CMFCToolBarDateTimeCtrl::OnSize

Ana araç çubuğu boyutunu veya konumunu değiştirdiğinde ve bu değişiklik düğmenin boyutunu değiştirmesine neden olduğunda çerçeve tarafından çağrılır.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parametreler

*iSize*<br/>
[içinde] Düğmenin yeni genişliği, pikselolarak.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CMFCToolBarDateTimeCtrlImpl` nesnenin boyutunu ve konumunu güncelleştirerek varsayılan sınıf uygulamasını [(CMFCToolBarButton::OnSize)](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)geçersiz kılar.

## <a name="cmfctoolbardatetimectrlonupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarDateTimeCtrl::OnUpdateToolTip

Üst araç çubuğu araç ipucu metnini güncelleştirirken çerçeve tarafından çağrılır.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Ana pencere.

*iButtonIndex*<br/>
[içinde] Üst düğme koleksiyonundaki düğmenin sıfır tabanlı dizini.

*wndToolTip*<br/>
[içinde] Araç ipucu metnini görüntüleyen denetim.

*Str*<br/>
[çıkış] Güncelleştirilmiş araç ipucu metnini alan bir `CString` nesne.

### <a name="return-value"></a>Dönüş Değeri

Yöntem araç ipucu metnini güncelleştirirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, düğmeyle ilişkili araç ipucu metnini görüntüleyerek taban sınıf uygulamasını [(CMFCToolBarButton::OnUpdateToolTip)](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)genişletir. Düğme yatay olarak sabitlenmezse, bu yöntem hiçbir şey yapmaz ve FALSE döndürür.

## <a name="cmfctoolbardatetimectrlsettime"></a><a name="settime"></a>CMFCToolBarDateTimeCtrl::SetTime

Saat seçici denetiminde saati ve tarihi ayarlar.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Parametreler

*zamanYeni*<br/>
[içinde] İlk sürümde, denetimin ayarlanacağı zamanı içeren bir [COleDateTime Class](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine başvuru. İkinci sürümde, denetimin ayarlanacağı zamanı içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine işaretçi.

*pTimeYeni*<br/>
[içinde] Denetimin ayarlanacağı zamanı içeren [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[CDateTimeCtrl::SetTime'ı](../../mfc/reference/cdatetimectrl-class.md#settime)arayarak tarih ve saat seçici denetimindeki zamanı ayarlar.

## <a name="cmfctoolbardatetimectrlsettimeall"></a><a name="settimeall"></a>CMFCToolBarDateTimeCtrl::SetTimeAll

Belirli bir komut kimliğine sahip zaman seçici denetiminin tüm örneklerinde saati ve tarihi ayarlar.

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
[içinde] Araç çubuğu düğmesinin komut kimliğini belirtir.

*zamanYeni*<br/>
[içinde] İlk sürümde, denetimin ayarlanacağı zamanı içeren bir [COleDateTime Class](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi. İkinci sürümde, denetimin ayarlanacağı zamanı içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine işaretçi.

*pTimeYeni*<br/>
[içinde] Denetimin ayarlanacağı zamanı içeren [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen komut kimliğine sahip bir araç çubuğu düğmesini arar ve [CMFCToolBarTimeTimeCtrl:SetTime'ı](#settime)arayarak tarih ve saat seçici denetiminde saati ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
