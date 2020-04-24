---
title: AFX_GLOBAL_DATA Yapısı
ms.date: 11/04/2016
f1_keywords:
- AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::CleanUp
- AFXGLOBALS/AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
- AFXGLOBALS/AFX_GLOBAL_DATA::DrawParentBackground
- AFXGLOBALS/AFX_GLOBAL_DATA::DrawTextOnGlass
- AFXGLOBALS/AFX_GLOBAL_DATA::ExcludeTag
- AFXGLOBALS/AFX_GLOBAL_DATA::GetColor
- AFXGLOBALS/AFX_GLOBAL_DATA::GetDirect2dFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::GetHandCursor
- AFXGLOBALS/AFX_GLOBAL_DATA::GetITaskbarList
- AFXGLOBALS/AFX_GLOBAL_DATA::GetITaskbarList3
- AFXGLOBALS/AFX_GLOBAL_DATA::GetNonClientMetrics
- AFXGLOBALS/AFX_GLOBAL_DATA::GetShellAutohideBars
- AFXGLOBALS/AFX_GLOBAL_DATA::GetTextHeight
- AFXGLOBALS/AFX_GLOBAL_DATA::GetWICFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::GetWriteFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::InitD2D
- AFXGLOBALS/AFX_GLOBAL_DATA::Is32BitIcons
- AFXGLOBALS/AFX_GLOBAL_DATA::IsD2DInitialized
- AFXGLOBALS/AFX_GLOBAL_DATA::IsDwmCompositionEnabled
- AFXGLOBALS/AFX_GLOBAL_DATA::IsHighContrastMode
- AFXGLOBALS/AFX_GLOBAL_DATA::OnSettingChange
- AFXGLOBALS/AFX_GLOBAL_DATA::RegisterWindowClass
- AFXGLOBALS/AFX_GLOBAL_DATA::ReleaseTaskBarRefs
- AFXGLOBALS/AFX_GLOBAL_DATA::Resume
- AFXGLOBALS/AFX_GLOBAL_DATA::SetLayeredAttrib
- AFXGLOBALS/AFX_GLOBAL_DATA::SetMenuFont
- AFXGLOBALS/AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
- AFXGLOBALS/AFX_GLOBAL_DATA::UpdateFonts
- AFXGLOBALS/AFX_GLOBAL_DATA::UpdateSysColors
- AFXGLOBALS/AFX_GLOBAL_DATA::EnableAccessibilitySupport
- AFXGLOBALS/AFX_GLOBAL_DATA::IsAccessibilitySupport
- AFXGLOBALS/AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
- AFXGLOBALS/AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
- AFXGLOBALS/AFX_GLOBAL_DATA::bIsWindows7
- AFXGLOBALS/AFX_GLOBAL_DATA::clrActiveCaptionGradient
- AFXGLOBALS/AFX_GLOBAL_DATA::clrInactiveCaptionGradient
- AFXGLOBALS/AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
- AFXGLOBALS/AFX_GLOBAL_DATA::m_bUseSystemFont
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurHand
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurStretch
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurStretchVert
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hiconTool
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
helpviewer_keywords:
- AFX_GLOBAL_DATA structure [MFC]
- AFX_GLOBAL_DATA constructor
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
ms.openlocfilehash: 0361d535a31526c5f7b79fdd4eab046dad0435cc
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752878"
---
# <a name="afx_global_data-structure"></a>AFX_GLOBAL_DATA Yapısı

Yapı, `AFX_GLOBAL_DATA` çerçeveyi yönetmek veya uygulamanızın görünümünü ve davranışını özelleştirmek için kullanılan alanları ve yöntemleri içerir.

## <a name="syntax"></a>Sözdizimi

```
struct AFX_GLOBAL_DATA
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|Bir `AFX_GLOBAL_DATA` yapı inşa eder.|
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[AFX_GLOBAL_DATA::Temizleme](#cleanup)|Fırçalar, yazı tipleri ve DL'ler gibi çerçeve tarafından ayrılan kaynakları yayımlar.|
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#d2d1makerotatematrix)|Belirli bir nokta etrafında belirli bir açıyla dönen bir döndürme dönüşümü oluşturur.|
|[AFX_GLOBAL_DATA::DrawParentBackground](#drawparentbackground)|Belirtilen alanda bir denetimin üst arka planını çizer.|
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#drawtextonglass)|Belirtilen metnin görsel stilinde belirtilen metni çizer.|
|[AFX_GLOBAL_DATA::ExcludeTag](#excludetag)|Belirtilen XML etiket çiftini belirtilen arabellekten kaldırır.|
|[AFX_GLOBAL_DATA::GetColor](#getcolor)|Belirtilen kullanıcı arabirimi öğesinin geçerli rengini alır.|
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#getdirect2dfactory)|Genel verilerde `ID2D1Factory` depolanan arabirime bir işaretçi döndürür. Arabirim baş harfe getirilmezse, oluşturulur ve varsayılan parametrelere sahiptir.|
|[AFX_GLOBAL_DATA::GetHandCursor](#gethandcursor)|Bir ele benzeyen ve tanımlayıcısı olan önceden tanımlanmış imleci `IDC_HAND`alır.|
|[AFX_GLOBAL_DATA::GetITaskbarList](#getitaskbarlist)|ITaskBarList arabirimi için bir işaretçi oluşturur ve küresel verilerde depolar.|
|[AFX_GLOBAL_DATA::GetITaskbarList3](#getitaskbarlist3)|ITaskBarList3 arabirimine işaretçi oluşturur ve küresel verilerde depolar.|
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#getnonclientmetrics)|Küçülmeyen pencerelerin istemci olmayan alanıyla ilişkili ölçümleri alır.|
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#getshellautohidebars)|Shell otomatik gizleme çubuklarının konumlarını belirler.|
|[AFX_GLOBAL_DATA::GetTextHeight](#gettextheight)|Geçerli yazı tipindeki metin karakterlerinin yüksekliğini alır.|
|[AFX_GLOBAL_DATA::GetWICFactory](#getwicfactory)|Genel verilerde `IWICImagingFactory` depolanan arabirime bir işaretçi döndürür. Arabirim baş harfe getirilmezse, oluşturulur ve varsayılan parametrelere sahiptir.|
|[AFX_GLOBAL_DATA::GetWriteFactory](#getwritefactory)|Genel verilerde `IDWriteFactory` depolanan arabirime bir işaretçi döndürür. Arabirim baş harfe getirilmezse, oluşturulur ve varsayılan parametrelere sahiptir.|
|[AFX_GLOBAL_DATA::InitD2D](#initd2d)|Initializes `D2D` `DirectWrite`, `WIC` ve fabrikalar. Ana pencere başharfe basılmadan önce bu yöntemi arayın.|
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|Önceden tanımlanmış 32 bit simgelerin desteklenip desteklenmediğini gösterir.|
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|Başharfin `D2D` inip başharfe başlamayacağını belirler.|
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#isdwmcompositionenabled)|Windows [DwmIsCompositionEnabled](/windows/win32/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) yöntemini aramak için basit bir yol sağlar.|
|[AFX_GLOBAL_DATA::IsHighContrastMode](#ishighcontrastmode)|Görüntülerin şu anda yüksek kontrastta görüntülenip görüntülenmediğini gösterir.|
|[AFX_GLOBAL_DATA::OnSettingChange](#onsettingchange)|Masaüstünün menü animasyonu ve görev çubuğu otomatik hide özelliklerinin geçerli durumunu algılar.|
|[AFX_GLOBAL_DATA::RegisterWindowClass](#registerwindowclass)|Belirtilen MFC pencere sınıfını kaydeder.|
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#releasetaskbarrefs)|GetITaskbarList ve GetITaskbarList3 yöntemleri ile elde edilen arabirimleri yayımlar.|
|[AFX_GLOBAL_DATA::Özgeçmiş](#resume)|Windows [temalarını ve görsel stilleri](/windows/win32/Controls/visual-styles-overview)destekleyen yöntemlere erişen dahili işlev işaretçilerini yeniden başharfize eder.|
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#setlayeredattrib)|Windows [SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes) yöntemini aramak için basit bir yol sağlar.|
|[AFX_GLOBAL_DATA::SetMenuFont](#setmenufont)|Belirtilen mantıksal yazı tipini oluşturur.|
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#shellcreateitemfromparsingname)|Ayrıştırma adından bir Shell öğesi nesnesi oluşturur ve baş harfe ait hale gelirse.|
|[AFX_GLOBAL_DATA::UpdateFonts](#updatefonts)|Çerçeve tarafından kullanılan mantıksal yazı tiplerini reintialize eder.|
|[AFX_GLOBAL_DATA::UpdateSysColors](#updatesyscolors)|Çerçeve tarafından kullanılan renkleri, renk derinliğini, fırçaları, kalemleri ve görüntüleri başolarak karşılar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)|Microsoft Etkin Erişilebilirlik desteğini etkinleştirir veya devre dışı kılabilir. Etkin Erişilebilirlik, kullanıcı arabirimi öğeleri hakkında bilgi açığa çıkarmak için güvenilir yöntemler sağlar.|
|[AFX_GLOBAL_DATA::ErişilebilirlikDesteği](#isaccessibilitysupport)|Microsoft Etkin Erişilebilirlik desteğinin etkin olup olmadığını gösterir.|
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#iswindowslayersupportavailable)|İşletim sisteminin katmanlı pencereleri destekleyip desteklemediğini gösterir.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#bisosalphablendingsupport)|Geçerli işletim sisteminin alfa karıştırmayı destekleyip desteklemediğini gösterir.|
|[AFX_GLOBAL_DATA::bIsWindows7](#biswindows7)|Uygulamanın Windows 7 işletim sistemi altında mı yoksa daha yüksek mi yürütüldedildiğini gösterir|
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#clractivecaptiongradient)|Etkin resim yazısının degrade rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.|
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#clrinactivecaptiongradient)|Etkin olmayan etkin altyazının degrade rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.|
|[AFX_GLOBAL_DATA:m_bUseBuiltIn32BitIcons](#m_busebuiltin32biticons)|Çerçevenin önceden tanımlanmış 32 bit renk simgeleri mi yoksa daha düşük çözünürlük simgeleri mi kullandığını gösterir.|
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#m_busesystemfont)|Menüler, araç çubukları ve şeritler için sistem yazı tipinin kullanılıp kullanılmadığını gösterir.|
|[AFX_GLOBAL_DATA:m_hcurHand](#m_hcurhand)|El imleciiçin tutamacı saklar.|
|[AFX_GLOBAL_DATA:m_hcurStretch](#m_hcurstretch)|Yatay streç imleci için tutamacı saklar.|
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#m_hcurstretchvert)|Dikey streç imleci için tutamacı saklar.|
|[AFX_GLOBAL_DATA:m_hiconTool](#m_hicontool)|Araç simgesinin tutamacını depolar.|
|[AFX_GLOBAL_DATA:m_nAutoHideToolBarMargin](#m_nautohidetoolbarmargin)|Dengeleme çubuğunun sol tarafına giden en sol otomatik hide araç çubuğundan mahsup ilerler.|
|[AFX_GLOBAL_DATA:m_nAutoHideToolBarSpacing](#m_nautohidetoolbarspacing)|Otomatik hide araç çubukları arasındaki boşluğu belirtir.|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#m_ndragframethicknessdock)|Kenetlenmiş durumu iletmek için kullanılan sürükleme çerçevesinin kalınlığını belirtir.|
|[AFX_GLOBAL_DATA:m_nDragFrameThicknessFloat](#m_ndragframethicknessfloat)|Kayan durumu iletmek için kullanılan sürükleme çerçevesinin kalınlığını belirtir.|

### <a name="remarks"></a>Açıklamalar

Uygulamanız başladığında yapıdaki `AFX_GLOBAL_DATA` verilerin çoğu başlatılır.

### <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`AFX_GLOBAL_DATA`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxglobals.h

## <a name="afx_global_databisosalphablendingsupport"></a><a name="bisosalphablendingsupport"></a>AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport

İşletim sisteminin alfa karıştırmayı destekleyip desteklemediğini gösterir.

```
BOOL  bIsOSAlphaBlendingSupport;
```

### <a name="remarks"></a>Açıklamalar

TRUE alfa karıştırma nın desteklenir olduğunu gösterir; aksi takdirde, YANLIŞ.

## <a name="afx_global_datacleanup"></a><a name="cleanup"></a>AFX_GLOBAL_DATA::Temizleme

Fırçalar, yazı tipleri ve DL'ler gibi çerçeve tarafından ayrılan kaynakları yayımlar.

```cpp
void CleanUp();
```

## <a name="afx_global_datad2d1makerotatematrix"></a><a name="d2d1makerotatematrix"></a>AFX_GLOBAL_DATA::D2D1MakeRotateMatrix

Belirli bir nokta etrafında belirli bir açıyla dönen bir döndürme dönüşümü oluşturur.

```
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,
    D2D1_POINT_2F center,
    D2D1_MATRIX_3X2_F *matrix);
```

### <a name="parameters"></a>Parametreler

*açı*<br/>
Saat yönünde dönüş açısı, derece olarak.

*Merkezi*<br/>
Döndürülecek nokta.

*Matris*<br/>
Bu yöntem döndüğünde, yeni döndürme dönüşüm içerir. Bu parametre için depolama alanı ayırmanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK veya aksi takdirde bir hata değeri verir.

## <a name="afx_global_datadrawparentbackground"></a><a name="drawparentbackground"></a>AFX_GLOBAL_DATA::DrawParentBackground

Belirtilen alanda bir denetimin üst arka planını çizer.

```
BOOL DrawParentBackground(
    CWnd* pWnd,
    CDC* pDC,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Denetim penceresine işaretçi.

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Lprect*<br/>
[içinde] Çizim için alanı sınırlayan bir dikdörtgen işaretçi. Varsayılan değer NULL'dur.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="afx_global_datadrawtextonglass"></a><a name="drawtextonglass"></a>AFX_GLOBAL_DATA::DrawTextOnGlass

Belirtilen metnin görsel stilinde belirtilen metni çizer.

```
BOOL DrawTextOnGlass(
    HTHEME hTheme,
    CDC* pDC,
    int iPartId,
    int iStateId,
    CString strText,
    CRect rect,
    DWORD dwFlags,
    int nGlowSize = 0,
    COLORREF clrText = (COLORREF)-1);
```

### <a name="parameters"></a>Parametreler

*hTema*<br/>
[içinde] Bir pencerenin tema verilerine veya NULL'a işle. Bu parametre NULL değilse ve temalar desteklenmişse, çerçeve metni çizmek için belirtilen temayı kullanır. Aksi takdirde, çerçeve metni çizmek için bir tema kullanmaz.

Bir HTHEME oluşturmak için [OpenThemeData](/windows/win32/api/uxtheme/nf-uxtheme-openthemedata) yöntemini kullanın.

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*iPartId*<br/>
[içinde] İstenilen metin görünümüne sahip denetim bölümü. Daha fazla bilgi için, [Tablonun Parçalar ve Durumlar'daki](/windows/win32/controls/parts-and-states)Parçalar sütununa bakın. Bu değer 0 ise, metin varsayılan yazı tipine veya aygıt bağlamına seçilen bir yazı tipine çizilir.

*iStateId*<br/>
[içinde] İstenilen metin görünümüne sahip denetim durumu. Daha fazla bilgi için, [Tablonun Bölgeler ve Durumlar'daki](/windows/win32/controls/parts-and-states)Devletler sütununa bakın.

*strText*<br/>
[içinde] Çizecek metin.

*Rect*<br/>
[içinde] Belirtilen metnin çizildiği alanın sınırı.

*Dwflags*<br/>
[içinde] Belirtilen metnin nasıl çizildiğini belirten bitwise birleşimi (VEYA).

*hTheme* parametresi `NULL` veya temalar desteklenmiyorsa ve etkinleştiriliyorsa, [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) yönteminin *nFormat* parametresi geçerli bayrakları açıklar. Temalar desteklenirse, [DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex) yönteminin *dwFlags* parametresi geçerli bayrakları açıklar.

*nGlowSize*<br/>
[içinde] Belirtilen metni çizmeden önce arka plana çizilen bir kızdırma efektinin boyutu. Varsayılan değer 0’dır.

*clrMetin*<br/>
[içinde] Belirtilen metnin çizildiği renk. Varsayılan değer varsayılan renktir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen metni çizmek için bir tema kullanılıyorsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Tema, bir uygulamanın görsel stilini tanımlar. *HTheme* parametresi NULL ise veya [DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex) yöntemi desteklenmiyorsa veya [Desktop Window Manager](/windows/win32/dwm/dwm-overview) (DWM) kompozisyonu devre dışı bırakılmışsa, bir tema metni çizmek için kullanılmaz.

## <a name="afx_global_dataenableaccessibilitysupport"></a><a name="enableaccessibilitysupport"></a>AFX_GLOBAL_DATA::EnableAccessibilitySupport

Microsoft Etkin Erişilebilirlik desteğini etkinleştirir veya devre dışı kılabilir.

```cpp
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Erişilebilirlik desteğini etkinleştirmek için TRUE; Erişilebilirlik desteğini devre dışı kılabilir. Varsayılan değer TRUE'dur.

### <a name="remarks"></a>Açıklamalar

Etkin Erişilebilirlik, programların ve Windows işletim sisteminin yardımcı teknoloji ürünleriyle birlikte çalışma biçimini iyileştiren COM tabanlı bir teknolojidir. Kullanıcı arabirimi öğeleri hakkında bilgi açığa çıkarmak için güvenilir yöntemler sağlar. Ancak, Microsoft UI Automation adı verilen yeni bir erişilebilirlik modeli artık kullanılabilir. İki teknolojinin karşılaştırılması için [UI Automation ve Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)bölümüne bakın.

Microsoft Active Accessibility desteğinin etkin olup olmadığını belirlemek için [AFX_GLOBAL_DATA::İş Erişilebilirlik Desteği](#isaccessibilitysupport) yöntemini kullanın.

## <a name="afx_global_dataexcludetag"></a><a name="excludetag"></a>AFX_GLOBAL_DATA::ExcludeTag

Belirtilen XML etiket çiftini belirtilen arabellekten kaldırır.

```
BOOL ExcludeTag(
    CString& strBuffer,
    LPCTSTR lpszTag,
    CString& strTag,
    BOOL bIsCharsList = FALSE);
```

### <a name="parameters"></a>Parametreler

*strBuffer*<br/>
[içinde] Metin arabelleği.

*lpszTag*<br/>
[içinde] XML etiketlerini açma ve kapatma çiftinin adı.

*strTag*<br/>
[çıkış] Bu yöntem döndüğünde, *strTag* parametresi *lpszTag* parametresi tarafından adlandırılmış xml etiketlerinin açılması ve kapatılması arasındaki metni içerir. Herhangi bir öncü veya sondaki beyaz boşluk sonuçtan kesilir.

*bIsCharsList*<br/>
[içinde] *TRUE strTag* parametredeki kaçış karakterleri için sembolleri gerçek kaçış karakterlerine dönüştürmek için; Dönüştürme gerçekleştirmek için YANLıŞ değil. Varsayılan değer FALSE'dur. Daha fazla bilgi için Açıklamalar'a bakın.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

XML etiket çifti, belirtilen arabellekteki bir metnin çalışmasının başlangıç ve bitişini gösteren adlandırılmış açılış ve kapanış etiketlerinden oluşur. *strBuffer* parametresi arabelleği belirtir ve *lpszTag* parametresi XML etiketlerinin adını belirtir.

Belirtilen arabellekteki kaçış karakterleri kümesini kodlamak için aşağıdaki tablodaki sembolleri kullanın. *strTag* parametresindeki sembolleri gerçek kaçış karakterlerine dönüştürmek için *bIsCharsList* parametresi için TRUE belirtin. Aşağıdaki tablo, simgeyi belirtmek ve karakter dizelerini kaçmak için [_T()](../../c-runtime-library/data-type-mappings.md) makroyu kullanır.

|Sembol|Atlatma karakteri|
|------------|----------------------|
|_T("\\\t")|_T("\t")|
|_T("\\\n")|_T("\n")|
|_T("\\\r")|_T("\r")|
|_T("\\\b")|_T("\b")|
|_T("LT")|_T("\<")|
|_T("GT")|_T(">")|
|_T("AMP")|_T("&")|

## <a name="afx_global_datagetcolor"></a><a name="getcolor"></a>AFX_GLOBAL_DATA::GetColor

Belirtilen kullanıcı arabirimi öğesinin geçerli rengini alır.

```
COLORREF GetColor(int nColor);
```

### <a name="parameters"></a>Parametreler

*nColor*<br/>
[içinde] Rengi alınan bir kullanıcı arabirimi öğesini belirten bir değer. Geçerli değerler listesi için [GetSysColor](/windows/win32/api/winuser/nf-winuser-getsyscolor) yönteminin *nIndex* parametresini görün.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen kullanıcı arabirimi öğesinin RGB renk değeri. Daha fazla bilgi için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

*nColor* parametresi aralık dışındaysa, iade değeri sıfırdır. Sıfır da geçerli bir RGB değeri olduğundan, sistem renginin geçerli işletim sistemi tarafından desteklenip desteklenmediğini belirlemek için bu yöntemi kullanamazsınız. Bunun yerine, renk desteklenmiyorsa NULL döndüren [GetSysColorBrush](/windows/win32/api/winuser/nf-winuser-getsyscolorbrush) yöntemini kullanın.

## <a name="afx_global_datagetdirect2dfactory"></a><a name="getdirect2dfactory"></a>AFX_GLOBAL_DATA::GetDirect2dFactory

Genel verilerde depolanan ID2D1Factory arabirimine bir işaretçi döndürür. Arabirim baş harfe getirilmezse, oluşturulur ve varsayılan parametrelere sahiptir.

```
ID2D1Factory* GetDirect2dFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Bir fabrika oluşturma başarılı olursa ID2D1Factory arabirimine işaretçi veya oluşturma başarısız olursa veya geçerli Çalışma Sistemi D2D desteği yoksa NULL.

## <a name="afx_global_datagethandcursor"></a><a name="gethandcursor"></a>AFX_GLOBAL_DATA::GetHandCursor

Bir ele benzeyen ve tanımlayıcısı IDC_HAND olan önceden tanımlanmış imleci alır.

```
HCURSOR GetHandCursor();
```

### <a name="return-value"></a>Dönüş Değeri

El imlecinin sapı.

## <a name="afx_global_datagetnonclientmetrics"></a><a name="getnonclientmetrics"></a>AFX_GLOBAL_DATA::GetNonClientMetrics

Küçülmeyen pencerelerin istemci olmayan alanıyla ilişkili ölçümleri alır.

```
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```

### <a name="parameters"></a>Parametreler

*Bilgi*<br/>
[içinde, dışarı] [NonCLIENTMETRICS](/windows/win32/api/winuser/ns-winuser-nonclientmetricsw) yapısı, küçültülmeyen bir pencerenin istemci olmayan alanıyla ilişkili ölçeklenebilir ölçümleri içerir.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="afx_global_datagettextheight"></a><a name="gettextheight"></a>AFX_GLOBAL_DATA::GetTextHeight

Geçerli yazı tipindeki metin karakterlerinin yüksekliğini alır.

```
int GetTextHeight(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parametreler

*bHorz*<br/>
[içinde] Metin yatay çalıştığında karakterlerin yüksekliğini almak için TRUE; Metin dikey çalıştığında karakterlerin yüksekliğini almak için FALSE. Varsayılan değer TRUE'dur.

### <a name="return-value"></a>Dönüş Değeri

Yükseleninden aldatan adedine kadar ölçülen geçerli yazı tipinin yüksekliği.

## <a name="afx_global_datagetwicfactory"></a><a name="getwicfactory"></a>AFX_GLOBAL_DATA::GetWICFactory

Genel verilerde depolanan IWICImagingFactory arabirimine bir işaretçi döndürür. Arabirim baş harfe getirilmezse, oluşturulur ve varsayılan parametrelere sahiptir.

```
IWICImagingFactory* GetWICFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Bir fabrika oluşturma başarılı olursa IWICImagingFactory arabirimi için bir işaretçi veya oluşturma başarısız olursa veya geçerli Çalışma Sistemi WIC desteği yoksa NULL.

## <a name="afx_global_datagetwritefactory"></a><a name="getwritefactory"></a>AFX_GLOBAL_DATA::GetWriteFactory

Genel verilerde depolanan IDWriteFactory arabirimine bir işaretçi döndürür. Arabirim baş harfe getirilmezse, oluşturulur ve varsayılan parametrelere sahiptir.

```
IDWriteFactory* GetWriteFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Bir fabrika oluşturma başarılı olursa IDWriteFactory arabirimine işaretçi veya oluşturma başarısız olursa veya geçerli İşlem Sistemi DirectWrite desteği yoksa NULL.

## <a name="afx_global_datainitd2d"></a><a name="initd2d"></a>AFX_GLOBAL_DATA::InitD2D

D2D, DirectWrite ve WIC fabrikalarını başharfe yönlendirir. Ana pencere başharfe basılmadan önce bu yöntemi arayın.

```
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Parametreler

*d2dFactoryType*<br/>
D2D fabrikasının iş parçacığı modeli ve oluşturduğu kaynaklar.

*yazmaFactoryType*<br/>
Yazma fabrikası nesnesinin paylaşılıp paylaşılmayacağını veya yalıtılıp yalıtılmayacağını belirten bir değer

### <a name="return-value"></a>Dönüş Değeri

Fabrikalar intilalizrd olsaydı DOĞRU döner, FALSE - aksi takdirde

## <a name="afx_global_datais32biticons"></a><a name="is32biticons"></a>AFX_GLOBAL_DATA::Is32BitIcons

Önceden tanımlanmış 32 bit simgelerin desteklenip desteklenmediğini gösterir.

```
BOOL Is32BitIcons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Önceden tanımlanmış 32 bit simgeler desteklenirse TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Çerçeve 32 bit yerleşik simgeleri destekliyorsa ve işletim sistemi piksel başına 16 bit veya daha fazlasını destekliyorsa ve görüntüler yüksek kontrastta görüntülenmiyorsa, bu yöntem TRUE döndürür.

## <a name="afx_global_dataisaccessibilitysupport"></a><a name="isaccessibilitysupport"></a>AFX_GLOBAL_DATA::ErişilebilirlikDesteği

Microsoft Etkin Erişilebilirlik desteğinin etkin olup olmadığını gösterir.

```
BOOL IsAccessibilitySupport() const;
```

### <a name="return-value"></a>Dönüş Değeri

Erişilebilirlik desteği etkinse TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Microsoft Active Accessibility, uygulamaları erişilebilir hale getirmek için daha önceki çözümdü. Microsoft UI Automation, Microsoft Windows için yeni erişilebilirlik modelidir ve yardımcı teknoloji ürünlerinin ve otomatik test araçlarının gereksinimlerini karşılamayı amaçlamaktadır.

Etkin Erişilebilirlik desteğini etkinleştirmek veya devre dışı kalmak için [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport) yöntemini kullanın.

## <a name="afx_global_dataisd2dinitialized"></a><a name="isd2dinitialized"></a>AFX_GLOBAL_DATA::IsD2DInitialized

D2D'nin baş harfe çevrilip başlanlaştırılmadığını belirler

```
BOOL IsD2DInitialized() const;
```

### <a name="return-value"></a>Dönüş Değeri

D2D başharfe basılsaydı DOĞRU; aksi takdirde YANLIŞ.

## <a name="afx_global_dataisdwmcompositionenabled"></a><a name="isdwmcompositionenabled"></a>AFX_GLOBAL_DATA::IsDwmCompositionEnabled

Windows [DwmIsCompositionEnabled](/windows/win32/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) yöntemini aramak için basit bir yol sağlar.

```
BOOL IsDwmCompositionEnabled();
```

### <a name="return-value"></a>Dönüş Değeri

Masaüstü [Pencere Yöneticisi](/windows/win32/dwm/dwm-overview) (DWM) kompozisyonu etkinse DOĞRU; aksi takdirde, YANLIŞ.

## <a name="afx_global_dataishighcontrastmode"></a><a name="ishighcontrastmode"></a>AFX_GLOBAL_DATA::IsHighContrastMode

Görüntülerin şu anda yüksek kontrastta görüntülenip görüntülenmediğini gösterir.

```
BOOL IsHighContrastMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntüler şu anda siyah veya beyaz yüksek kontrast modunda görüntüleniyorsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Siyah yüksek kontrast lı modda, ışığa bakan kenarlar beyaz, arka plan siyahtır. Beyaz yüksek kontrast modunda, ışığa bakan kenarlar siyah ve arka plan beyazdır.

## <a name="afx_global_dataiswindowslayersupportavailable"></a><a name="iswindowslayersupportavailable"></a>AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable

İşletim sisteminin katmanlı pencereleri destekleyip desteklemediğini gösterir.

```
BOOL IsWindowsLayerSupportAvailable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Katmanlı pencereler desteklenirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Katmanlı pencereler *desteklenirse, akıllı yerleştirme* işaretleri katmanlı pencereler kullanır.

## <a name="afx_global_datam_busebuiltin32biticons"></a><a name="m_busebuiltin32biticons"></a>AFX_GLOBAL_DATA:m_bUseBuiltIn32BitIcons

Çerçevenin önceden tanımlanmış 32 bit renk simgeleri mi yoksa daha düşük çözünürlük simgeleri mi kullandığını gösterir.

```
BOOL  m_bUseBuiltIn32BitIcons;
```

### <a name="remarks"></a>Açıklamalar

TRUE, çerçevenin 32 bit renk simgeleri kullandığını belirtir; FALSE, daha düşük çözünürlüklü simgeleri belirtir. Oluşturucu `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` bu üyeyi TRUE'ya başharfletir.

Bu üye uygulama başlangıç olarak ayarlanmalıdır.

## <a name="afx_global_datam_busesystemfont"></a><a name="m_busesystemfont"></a>AFX_GLOBAL_DATA::m_bUseSystemFont

Menüler, araç çubukları ve şeritler için sistem yazı tipinin kullanılıp kullanılmadığını gösterir.

```
BOOL m_bUseSystemFont;
```

### <a name="remarks"></a>Açıklamalar

TRUE bir sistem yazı tipi kullanmak için belirtir; aksi takdirde, YANLIŞ. Oluşturucu `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` bu üyeyi FALSE'a başharfletir.

Bu üyeyi sınamak, çerçevenin yazı tipini kullanmasının tek yolu değildir. Yöntem `AFX_GLOBAL_DATA::UpdateFonts` ayrıca, menülere, araç çubuklarına ve şeritlere uygulanacak görsel stilleri belirlemek için varsayılan ve alternatif yazı tiplerini de sınar.

## <a name="afx_global_datam_hcurhand"></a><a name="m_hcurhand"></a>AFX_GLOBAL_DATA:m_hcurHand

El imleciiçin tutamacı saklar.

```
HCURSOR m_hcurHand;
```

## <a name="afx_global_datam_hcurstretch"></a><a name="m_hcurstretch"></a>AFX_GLOBAL_DATA:m_hcurStretch

Yatay streç imleci için tutamacı saklar.

```
HCURSOR m_hcurStretch;
```

## <a name="afx_global_datam_hcurstretchvert"></a><a name="m_hcurstretchvert"></a>AFX_GLOBAL_DATA::m_hcurStretchVert

Dikey streç imleci için tutamacı saklar.

```
HCURSOR m_hcurStretchVert;
```

## <a name="afx_global_datam_hicontool"></a><a name="m_hicontool"></a>AFX_GLOBAL_DATA:m_hiconTool

Araç simgesinin tutamacını depolar.

```
HICON m_hiconTool;
```

## <a name="afx_global_datam_nautohidetoolbarmargin"></a><a name="m_nautohidetoolbarmargin"></a>AFX_GLOBAL_DATA:m_nAutoHideToolBarMargin

Ofset'i en soldaki otomatik hide araç çubuğundan dock çubuğunun sol tarafına kadar belirtir.

```
int  m_nAutoHideToolBarMargin;
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` bu üyeyi 4 piksele kadar başharfe alar.

## <a name="afx_global_datam_nautohidetoolbarspacing"></a><a name="m_nautohidetoolbarspacing"></a>AFX_GLOBAL_DATA:m_nAutoHideToolBarSpacing

Otomatik hide araç çubukları arasındaki boşluğu belirtir.

```
int   m_nAutoHideToolBarSpacing;
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` bu üyeyi 14 piksele aparat eder.

## <a name="afx_global_datam_ndragframethicknessdock"></a><a name="m_ndragframethicknessdock"></a>AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Kenetlenmiş durumu belirtmek için kullanılan sürükleme çerçevesinin kalınlığını belirtir.

```
int  m_nDragFrameThicknessDock;
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` bu üyeyi 3 piksele kadar başharfe alar.

## <a name="afx_global_datam_ndragframethicknessfloat"></a><a name="m_ndragframethicknessfloat"></a>AFX_GLOBAL_DATA:m_nDragFrameThicknessFloat

Kayan durumu belirtmek için kullanılan sürükleme çerçevesinin kalınlığını belirtir.

```
int  m_nDragFrameThicknessFloat;
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` bu üyeyi 4 piksele kadar başharfe alar.

## <a name="afx_global_dataonsettingchange"></a><a name="onsettingchange"></a>AFX_GLOBAL_DATA::OnSettingChange

Masaüstünün menü animasyonu ve görev çubuğu otomatik hide özelliklerinin geçerli durumunu algılar.

```cpp
void OnSettingChange();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, çerçeve değişkenlerini kullanıcının masaüstünün belirli özniteliklerinin durumuna ayarlar. Bu yöntem, menü animasyon, menü solukve görev çubuğu otomatik hide özellikleri geçerli durumunu algılar.

## <a name="afx_global_dataregisterwindowclass"></a><a name="registerwindowclass"></a>AFX_GLOBAL_DATA::RegisterWindowClass

Belirtilen MFC pencere sınıfını kaydeder.

```
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```

### <a name="parameters"></a>Parametreler

*lpszClassNameÖnek*<br/>
[içinde] Kaydolunacak pencere sınıfının adı.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa kayıtlı sınıfın nitelikli adı; aksi takdirde, bir [kaynak özel durum](exception-processing.md#afxthrowresourceexception).

### <a name="remarks"></a>Açıklamalar

İade değeri *lpszClassNamePrefix* parametre dizesinin iki nokta üst üste sınırlı bir listesi ve geçerli uygulama örneğinin tutamaçlarının hexadecimal metin gösterimleridir; tanımlayıcısı IDC_ARROW ok imleci olan uygulama imleci; ve arka plan fırçası. MFC pencere sınıflarını kaydetme hakkında daha fazla bilgi için [AfxRegisterClass'a](../../mfc/reference/application-information-and-management.md#afxregisterclass)bakın.

## <a name="afx_global_dataresume"></a><a name="resume"></a>AFX_GLOBAL_DATA::Özgeçmiş

Windows temalarını ve görsel stilleri destekleyen yöntemlere erişen dahili işlev işaretçilerini yeniden başharfize eder.

```
BOOL Resume();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ. Hata ayıklama modunda, bu yöntem başarısız olursa bu yöntem ileri sayılsın.

### <a name="remarks"></a>Açıklamalar

Çerçeve [WM_POWERBROADCAST](/windows/win32/Power/wm-powerbroadcast) iletisi aldığında bu yöntem çağrılır.

## <a name="afx_global_datasetlayeredattrib"></a><a name="setlayeredattrib"></a>AFX_GLOBAL_DATA::SetLayeredAttrib

Windows [SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes) yöntemini aramak için basit bir yol sağlar.

```
BOOL SetLayeredAttrib(
    HWND hwnd,
    COLORREF crKey,
    BYTE bAlpha,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] Katmanlı pencereye işleyin.

*crKey*<br/>
[içinde] [Masaüstü Pencere Yöneticisi'nin](/windows/win32/dwm/dwm-overview) katmanlı pencereyi oluşturmak için kullandığı saydamlık renk anahtarı.

*bAlfa*<br/>
[içinde] Katmanlı pencerenin opaklığını tanımlamak için kullanılan alfa değeri.

*Dwflags*<br/>
[içinde] Hangi yöntem parametrelerinin kullanılacağını belirten bir bitwise birleşimi (OR). *CrKey* parametresini saydamlık rengi olarak kullanmak için LWA_COLORKEY belirtin. Katmanlı pencerenin opaklığını belirlemek için *bAlpha* parametresini LWA_ALPHA kullanacağını belirtin.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="afx_global_datasetmenufont"></a><a name="setmenufont"></a>AFX_GLOBAL_DATA::SetMenuFont

Belirtilen mantıksal yazı tipini oluşturur.

```
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
[içinde] Yazı tipinin özniteliklerini içeren bir yapıyı işaretçi.

*bHorz*<br/>
[içinde] METNIN yatay olarak çalıştığını belirtmek için TRUE; Metnin dikey olarak çalıştığını belirtmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ. Hata ayıklama modunda, bu yöntem başarısız olursa bu yöntem ileri sayılsın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yatay bir normal yazı tipi, altı çizili bir yazı tipi ve varsayılan menü öğelerinde kullanılan kalın bir yazı tipi oluşturur. Bu yöntem isteğe bağlı olarak normal bir dikey yazı tipi oluşturur. Mantıksal yazı tipleri hakkında daha fazla bilgi için [Bkz. CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect).

## <a name="afx_global_dataupdatefonts"></a><a name="updatefonts"></a>AFX_GLOBAL_DATA::UpdateFonts

Çerçeve tarafından kullanılan mantıksal yazı tiplerini reintialize eder.

```cpp
void UpdateFonts();
```

### <a name="remarks"></a>Açıklamalar

Mantıksal yazı tipleri hakkında daha `CFont::CreateFontIndirect`fazla bilgi için bkz.

## <a name="afx_global_dataupdatesyscolors"></a><a name="updatesyscolors"></a>AFX_GLOBAL_DATA::UpdateSysColors

Çerçeve tarafından kullanılan renkleri, renk derinliğini, fırçaları, kalemleri ve görüntüleri başolarak karşılar.

```cpp
void UpdateSysColors();
```

## <a name="afx_global_databiswindows7"></a><a name="biswindows7"></a>AFX_GLOBAL_DATA::bIsWindows7

Uygulamanın Windows 7 veya daha yüksek altında yürütülüp yürütülmediğini gösterir.

```
BOOL bIsWindows7;
```

## <a name="afx_global_dataclractivecaptiongradient"></a><a name="clractivecaptiongradient"></a>AFX_GLOBAL_DATA::clrActiveCaptionGradient

Etkin resim yazısının degrade rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.

```
COLORREF clrActiveCaptionGradient;
```

## <a name="afx_global_dataclrinactivecaptiongradient"></a><a name="clrinactivecaptiongradient"></a>AFX_GLOBAL_DATA::clrInactiveCaptionGradient

Etkin olmayan başlığın degrade rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.

```
COLORREF clrInactiveCaptionGradient;
```

## <a name="afx_global_datagetitaskbarlist"></a><a name="getitaskbarlist"></a>AFX_GLOBAL_DATA::GetITaskbarList

Global verilerde `ITaskBarList` arabirime işaretçisi oluşturur ve depolar.

```
ITaskbarList *GetITaskbarList();
```

### <a name="return-value"></a>Dönüş Değeri

Görev çubuğu `ITaskbarList` listesi nesnesi oluşturulması başarılı olursa arabirimi işaretçisi; Oluşturma başarısız olursa veya geçerli İşlem Sistemi Windows 7'den küçükse NULL.

## <a name="afx_global_datagetitaskbarlist3"></a><a name="getitaskbarlist3"></a>AFX_GLOBAL_DATA::GetITaskbarList3

Global verilerde `ITaskBarList3` arabirime işaretçisi oluşturur ve depolar.

```
ITaskbarList3 *GetITaskbarList3();
```

### <a name="return-value"></a>Dönüş Değeri

Görev çubuğu `ITaskbarList3` listesi nesnesi oluşturulması başarılı olursa arabirimi işaretçisi; Oluşturma başarısız olursa veya geçerli İşlem Sistemi Windows 7'den küçükse NULL.

## <a name="afx_global_datagetshellautohidebars"></a><a name="getshellautohidebars"></a>AFX_GLOBAL_DATA::GetShellAutohideBars

Shell otomatik gizleme çubuklarının konumlarını belirler.

```
int GetShellAutohideBars();
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizleme çubuklarının konumlarını belirten kodlanmış bayraklara sahip bir sonda değeri. Aşağıdaki değerleri birleştirebilir: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.

## <a name="afx_global_datareleasetaskbarrefs"></a><a name="releasetaskbarrefs"></a>AFX_GLOBAL_DATA::ReleaseTaskBarRefs

Ve `GetITaskbarList` `GetITaskbarList3` yöntemler le elde edilen arabirimleri serbest bırakır.

```cpp
void ReleaseTaskBarRefs();
```

## <a name="afx_global_datashellcreateitemfromparsingname"></a><a name="shellcreateitemfromparsingname"></a>AFX_GLOBAL_DATA::ShellCreateItemFromParsingName

Ayrıştırma adından bir Shell öğesi nesnesi oluşturur ve baş harfe ait hale gelirse.

```
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,
    IBindCtx *pbc,
    REFIID riid,
    void **ppv);
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
[içinde] Görüntü adına işaretçi.

*Pbc*<br/>
Ayrışdırma işlemini denetleyen bağlama bağlamına işaretçi.

*Riid*<br/>
Arabirim kimliğine başvuru.

*Ppv*<br/>
[çıkış] Bu işlev döndüğünde, *riid'de*istenen arabirim işaretçisini içerir. Bu genellikle `IShellItem` olacaktır `IShellItem2`veya .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK verir; aksi takdirde bir hata değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../hierarchy-chart.md)<br/>
[Yapılar, Stiller, Geri Aramalar ve İleti Haritaları](structures-styles-callbacks-and-message-maps.md)<br/>
[Colorref](/windows/win32/gdi/colorref)<br/>
[Parçalar ve Durumlar](/windows/win32/controls/parts-and-states)<br/>
[CDC::DrawText](cdc-class.md#drawtext)<br/>
[DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex)<br/>
[Masaüstü Pencere Yöneticisi](/windows/win32/dwm/dwm-overview)<br/>
[DWM Kompozisyonu Etkinleştirme ve Denetleme](/windows/win32/dwm/composition-ovw)<br/>
[UI Otomasyonu ve Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)<br/>
[GetSysColor Fonksiyonu](/windows/win32/api/winuser/nf-winuser-getsyscolor)<br/>
[GetSysColorBrush](/windows/win32/api/winuser/nf-winuser-getsyscolorbrush)<br/>
[İsteNMEYEN METRIYAT Yapısı](/windows/win32/api/winuser/ns-winuser-nonclientmetricsw)<br/>
[AfxRegisterClass](application-information-and-management.md#afxregisterclass)<br/>
[AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)<br/>
[SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes)
