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
- AFXGLOBALS/AFX_GLOBAL_DATA::IsD2DInitialized
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
ms.openlocfilehash: dda3056cbed18ef93e09b52cd9d0a6b00e1db177
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507749"
---
# <a name="afx_global_data-structure"></a>AFX_GLOBAL_DATA Yapısı

`AFX_GLOBAL_DATA` Yapı, Framework 'ü yönetmek veya uygulamanızın görünümünü ve davranışını özelleştirmek için kullanılan alanları ve yöntemleri içerir.

## <a name="syntax"></a>Sözdizimi

```
struct AFX_GLOBAL_DATA
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|Bir `AFX_GLOBAL_DATA` yapı oluşturur.|
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[AFX_GLOBAL_DATA:: CleanUp](#cleanup)|Çerçeve tarafından ayrılan, fırçalar, yazı tipleri ve DLL 'Ler gibi kaynakları serbest bırakır.|
|[AFX_GLOBAL_DATA::D 2D1MakeRotateMatrix](#d2d1makerotatematrix)|Belirtilen bir nokta etrafında belirtilen açıyla döndüren bir döndürme dönüştürmesi oluşturur.|
|[AFX_GLOBAL_DATA::D rawParentBackground](#drawparentbackground)|Belirtilen alanda bir denetimin üstünün arka planını çizer.|
|[AFX_GLOBAL_DATA::D Rawtextoncam](#drawtextonglass)|Belirtilen metni belirtilen temanın görsel stilinde çizer.|
|[AFX_GLOBAL_DATA:: ExcludeTag](#excludetag)|Belirtilen bir arabelleğin belirtilen XML etiketi çiftini kaldırır.|
|[AFX_GLOBAL_DATA:: GetColor](#getcolor)|Belirtilen kullanıcı arabirimi öğesinin geçerli rengini alır.|
|[AFX_GLOBAL_DATA:: GetDirect2dFactory](#getdirect2dfactory)|Genel verilerde depolanan `ID2D1Factory` arabirime yönelik bir işaretçi döndürür. Arabirim başlatılmamışsa, oluşturulur ve Varsayılan parametrelere sahiptir.|
|[AFX_GLOBAL_DATA:: GetHandCursor](#gethandcursor)|Bir el ile benzeyen ve tanımlayıcısı `IDC_HAND`olan önceden tanımlanmış imleci alır.|
|[AFX_GLOBAL_DATA:: GetITaskbarList](#getitaskbarlist)|Genel verilerde bir ITaskBarList arabirimine yönelik bir işaretçi oluşturur ve depolar.|
|[AFX_GLOBAL_DATA::GetITaskbarList3](#getitaskbarlist3)|Genel verilerde bir ITaskBarList3 arabirimine yönelik bir işaretçi oluşturur ve depolar.|
|[AFX_GLOBAL_DATA:: Getnonclientmetrikleri](#getnonclientmetrics)|Küçültülmüş olmayan pencerelerin istemci olmayan alanıyla ilişkili ölçümleri alır.|
|[AFX_GLOBAL_DATA:: Getshellautohideçubuklarının](#getshellautohidebars)|Kabuk otomatik gizleme çubuklarının konumlarını belirler.|
|[AFX_GLOBAL_DATA:: GetTextHeight](#gettextheight)|Geçerli yazı tipindeki metin karakterlerinin yüksekliğini alır.|
|[AFX_GLOBAL_DATA:: GetWICFactory](#getwicfactory)|Genel verilerde depolanan `IWICImagingFactory` arabirime yönelik bir işaretçi döndürür. Arabirim başlatılmamışsa, oluşturulur ve Varsayılan parametrelere sahiptir.|
|[AFX_GLOBAL_DATA:: GetWriteFactory](#getwritefactory)|Genel verilerde depolanan `IDWriteFactory` arabirime yönelik bir işaretçi döndürür. Arabirim başlatılmamışsa, oluşturulur ve Varsayılan parametrelere sahiptir.|
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|, `D2D` `DirectWrite`Ve fabrikaları`WIC` başlatır. Ana pencere başlatılmadan önce bu yöntemi çağırın.|
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|Önceden tanımlanmış 32 bitlik simgelerin desteklenip desteklenmediğini gösterir.|
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|' `D2D` Nin başlatılmış olup olmadığını belirler.|
|[AFX_GLOBAL_DATA:: Isdwmkompozisyontionenabled](#isdwmcompositionenabled)|Windows [Dwmiskompozisyontionenabled](/windows/win32/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) yöntemini çağırmak için basit bir yol sağlar.|
|[AFX_GLOBAL_DATA:: ıshighınstmode](#ishighcontrastmode)|Görüntülerin Şu anda yüksek karşıtlıkta görüntülenip görüntülenmediğini gösterir.|
|[AFX_GLOBAL_DATA:: OnSettingChange](#onsettingchange)|Masaüstünün menü animasyon ve görev çubuğu otomatik gizleme özelliklerinin geçerli durumunu algılar.|
|[AFX_GLOBAL_DATA:: RegisterWindowClass](#registerwindowclass)|Belirtilen MFC pencere sınıfını kaydeder.|
|[AFX_GLOBAL_DATA:: ReleaseTaskBarRefs](#releasetaskbarrefs)|GetITaskbarList ve GetITaskbarList3 yöntemleriyle elde edilen arabirimleri yayınlar.|
|[AFX_GLOBAL_DATA:: özgeçmişi](#resume)|Windows [temalarını ve görsel stilleri](/windows/win32/Controls/visual-styles-overview)destekleyen yöntemlere erişen iç işlev işaretçileri yeniden başlatılır.|
|[AFX_GLOBAL_DATA:: SetLayeredAttrib](#setlayeredattrib)|Windows [SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes) yöntemini çağırmak için basit bir yol sağlar.|
|[AFX_GLOBAL_DATA:: SetMenuFont](#setmenufont)|Belirtilen mantıksal yazı tipini oluşturur.|
|[AFX_GLOBAL_DATA:: Shellcreateıtemfromparsingname](#shellcreateitemfromparsingname)|Ayrıştırma adından bir kabuk öğesi nesnesi oluşturur ve başlatır.|
|[AFX_GLOBAL_DATA:: UpdateFonts](#updatefonts)|Framework tarafından kullanılan mantıksal yazı tiplerini yeniden başlatır.|
|[AFX_GLOBAL_DATA:: UpdateSysColors](#updatesyscolors)|Çerçeve tarafından kullanılan renkleri, renk derinliğini, fırçaları, kalemleri ve görüntüleri başlatır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)|Microsoft Etkin Erişilebilirlik desteğini etkinleştirilir veya devre dışı bırakır. Etkin Erişilebilirlik, Kullanıcı arabirimi öğeleriyle ilgili bilgileri açığa çıkarmak için güvenilir yöntemler sağlar.|
|[AFX_GLOBAL_DATA:: IsAccessibilitySupport](#isaccessibilitysupport)|Microsoft Etkin Erişilebilirlik desteğinin etkin olup olmadığını gösterir.|
|[AFX_GLOBAL_DATA:: ıswindowslayersupportavailable](#iswindowslayersupportavailable)|İşletim sisteminin katmanlı pencereleri destekleyip desteklemediğini gösterir.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#bisosalphablendingsupport)|Geçerli işletim sisteminin Alfa karıştırmasını destekleyip desteklemediğini gösterir.|
|[AFX_GLOBAL_DATA::bIsWindows7](#biswindows7)|Uygulamanın Windows 7 işletim sistemi veya üzeri kapsamında yürütülüp yürütülmediğini belirtir|
|[AFX_GLOBAL_DATA:: clrActiveCaptionGradient](#clractivecaptiongradient)|Etkin açıklamalı alt yazısının gradyan rengini belirtir. Genellikle yerleştirme bölmeleri için kullanılır.|
|[AFX_GLOBAL_DATA:: clrInactiveCaptionGradient](#clrinactivecaptiongradient)|Etkin olmayan etkin açıklamalı alt yazısının gradyan rengini belirtir. Genellikle yerleştirme bölmeleri için kullanılır.|
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#m_busebuiltin32biticons)|Çerçevenin önceden tanımlanmış 32 bit renk simgeleri mi yoksa daha düşük bir çözümlemenin simgelerini mi kullanacağını gösterir.|
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#m_busesystemfont)|Menüler, araç çubukları ve şeritler için bir sistem yazı tipinin kullanılıp kullanılmadığını gösterir.|
|[AFX_GLOBAL_DATA::m_hcurHand](#m_hcurhand)|El imleci için tanıtıcıyı depolar.|
|[AFX_GLOBAL_DATA::m_hcurStretch](#m_hcurstretch)|Yatay Esnetme imleci için tanıtıcıyı depolar.|
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#m_hcurstretchvert)|Dikey Esnetme imleci için tanıtıcıyı depolar.|
|[AFX_GLOBAL_DATA::m_hiconTool](#m_hicontool)|Araç simgesinin tanıtıcısını depolar.|
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#m_nautohidetoolbarmargin)|Yerleştirme çubuğunun sol tarafında bulunan en sol otomatik gizle araç çubuğundan boşluğu belirtir.|
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#m_nautohidetoolbarspacing)|Otomatik gizleme araç çubukları arasındaki boşluğu belirtir.|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#m_ndragframethicknessdock)|Sabitlenmiş durumu iletmek için kullanılan sürükleme çerçevesinin kalınlığını belirtir.|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#m_ndragframethicknessfloat)|Kayan durumu iletmek için kullanılan sürükleme çerçevesinin kalınlığını belirtir.|

### <a name="remarks"></a>Açıklamalar

`AFX_GLOBAL_DATA` Yapı içindeki verilerin çoğu uygulamanız başlatıldığında başlatılır.

### <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`AFX_GLOBAL_DATA`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxglobals. h

## <a name="bisosalphablendingsupport"></a>AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport

İşletim sisteminin Alfa karıştırmasını destekleyip desteklemediğini gösterir.

```
BOOL  bIsOSAlphaBlendingSupport;
```

### <a name="remarks"></a>Açıklamalar

TRUE, Alfa karıştırmasını desteklenen gösterir; Aksi takdirde, FALSE.

## <a name="cleanup"></a>AFX_GLOBAL_DATA:: CleanUp

Çerçeve tarafından ayrılan, fırçalar, yazı tipleri ve DLL 'Ler gibi kaynakları serbest bırakır.

```
void CleanUp();
```

## <a name="d2d1makerotatematrix"></a>AFX_GLOBAL_DATA::D 2D1MakeRotateMatrix

Belirtilen bir nokta etrafında belirtilen açıyla döndüren bir döndürme dönüştürmesi oluşturur.

```
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,
    D2D1_POINT_2F center,
    D2D1_MATRIX_3X2_F *matrix);
```

### <a name="parameters"></a>Parametreler

*açısı*<br/>
Saat yönünde döndürme açısı (derece cinsinden).

*merkezinden*<br/>
Hangi noktada döndürüleceğini.

*Matrisin*<br/>
Bu yöntem döndüğünde, yeni döndürme dönüşümünü içerir. Bu parametre için depolama alanı ayırmanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK, aksi takdirde bir hata değeri döndürür.

## <a name="drawparentbackground"></a>AFX_GLOBAL_DATA::D rawParentBackground

Belirtilen alanda bir denetimin üstünün arka planını çizer.

```
BOOL DrawParentBackground(
    CWnd* pWnd,
    CDC* pDC,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Bir denetimin penceresine yönelik işaretçi.

*Kökündeki*<br/>
'ndaki Cihaz bağlamı işaretçisi.

*lpRect*<br/>
'ndaki Çizilecek alanı sınıralan dikdörtgenin işaretçisi. Varsayılan değer NULL.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

## <a name="drawtextonglass"></a>AFX_GLOBAL_DATA::D Rawtextoncam

Belirtilen metni belirtilen temanın görsel stilinde çizer.

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

*hTheme*<br/>
'ndaki Pencerenin Tema verilerine veya NULL değere işleyin. Çerçeve, bu parametre NULL değilse ve Temalar destekleniyorsa metni çizmek için belirtilen temayı kullanır. Aksi halde, çerçeve metni çizmek için bir tema kullanmaz.

Bir HTHEME oluşturmak için [OpenThemeData](/windows/win32/api/uxtheme/nf-uxtheme-openthemedata) yöntemini kullanın.

*Kökündeki*<br/>
'ndaki Cihaz bağlamı işaretçisi.

*ıpartıd*<br/>
'ndaki İstenen metin görünümüne sahip olan denetim bölümü. Daha fazla bilgi için bkz. [bölümler ve durumlar](/windows/win32/controls/parts-and-states)'Daki tablonun parçalar sütunu. Bu değer 0 ise, metin varsayılan yazı tipinde çizilir veya cihaz bağlamına seçilen bir yazı tipidir.

*iStateId*<br/>
'ndaki İstenen metin görünümüne sahip denetim durumu. Daha fazla bilgi için bkz. [bölümler ve eyaletler](/windows/win32/controls/parts-and-states)tablosunun durumlar sütunu.

*strText*<br/>
'ndaki Çizilecek metin.

*Rect*<br/>
'ndaki Belirtilen metnin çizildiği alanın sınırı.

*dwFlags*<br/>
'ndaki Belirtilen metnin nasıl çizildiğini belirten bir bit düzeyinde birleşim (veya) bayrakları.

*HTheme* parametresi `NULL` ya da Temalar desteklenmiyorsa ve etkinleştirilmezse, [CDC::D rawtext](../../mfc/reference/cdc-class.md#drawtext) yönteminin *nFormat* parametresi geçerli bayrakları açıklar. Temalar destekleniyorsa, [DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex) yönteminin *dwFlags* parametresi geçerli bayrakları açıklar.

*Nparlayan boyutu*<br/>
'ndaki Belirtilen metni çizmeden önce arka planda çizilen bir ışıma efektinin boyutu. Varsayılan değer 0’dır.

*clrText*<br/>
'ndaki Belirtilen metnin çizildiği renk. Varsayılan değer varsayılan renktir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen metni çizmek için bir tema kullanılıyorsa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir tema, bir uygulamanın görsel stilini tanımlar. Bir tema, *hTheme* parametresi null ise ya da [DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex) yöntemi desteklenmiyorsa veya [Masaüstü Pencere Yöneticisi](/windows/win32/dwm/dwm-overview) (dwm) birleşimi devre dışıysa metin çizmek için kullanılmaz.

## <a name="enableaccessibilitysupport"></a>AFX_GLOBAL_DATA::EnableAccessibilitySupport

Microsoft Etkin Erişilebilirlik desteğini etkinleştirilir veya devre dışı bırakır.

```
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Erişilebilirlik desteğini etkinleştirmek için TRUE; Erişilebilirlik desteğini devre dışı bırakmak için FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

Etkin Erişilebilirlik, programların ve Windows işletim sisteminin yardımcı teknoloji ürünleriyle birlikte çalışma yöntemini artıran COM tabanlı bir teknolojidir. Kullanıcı arabirimi öğeleriyle ilgili bilgileri açığa çıkarmak için güvenilir yöntemler sağlar. Ancak, Microsoft UI Otomasyonu adlı daha yeni bir erişilebilirlik modeli artık kullanılabilir. İki teknolojinin karşılaştırması için bkz. [UI Otomasyonu ve Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility).

Microsoft Etkin Erişilebilirlik desteğinin etkin olup olmadığını anlamak için [AFX_GLOBAL_DATA:: IsAccessibilitySupport](#isaccessibilitysupport) yöntemini kullanın.

## <a name="excludetag"></a>AFX_GLOBAL_DATA:: ExcludeTag

Belirtilen bir arabelleğin belirtilen XML etiketi çiftini kaldırır.

```
BOOL ExcludeTag(
    CString& strBuffer,
    LPCTSTR lpszTag,
    CString& strTag,
    BOOL bIsCharsList = FALSE);
```

### <a name="parameters"></a>Parametreler

*strBuffer*<br/>
'ndaki Metin arabelleği.

*lpszTag*<br/>
'ndaki Açılış ve kapanış XML etiketlerinin bir çiftinin adı.

*strTag*<br/>
dışı Bu yöntem döndüğünde, *strTag* parametresi *lpszTag* parametresi tarafından ADLANDıRıLAN açılış ve kapanış XML etiketleri arasındaki metni içerir. Baştaki veya sondaki boşluklar sonuçtan kırpılır.

*bIsCharsList*<br/>
'ndaki *StrTag* parametresindeki kaçış karakterlerinin sembollerini gerçek kaçış karakterlerine dönüştürmek için true; Dönüştürme gerçekleştirmediğinden yanlış. Varsayılan değer FALSE 'dur. Daha fazla bilgi için bkz. açıklamalar.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir XML etiket çifti, belirtilen arabellekte bir metin çalıştırmasının başlangıcını ve sonunu belirten adlandırılmış açılış ve kapanış etiketlerinden oluşur. *StrBuffer* parametresi, arabelleği belirtir ve *LPSZTAG* parametresi, XML etiketlerinin adını belirtir.

Belirtilen arabellekteki bir kaçış karakterleri kümesini kodlamak için aşağıdaki tablodaki sembolleri kullanın. *StrTag* parametresindeki sembolleri gerçek kaçış karakterlerine dönüştürmek Için *bıcharslist* parametresi için true değerini belirtin. Aşağıdaki tablo, simge ve kaçış karakter dizelerini belirtmek için [_T ()](../../c-runtime-library/data-type-mappings.md) makrosunu kullanır.

|Sembol|Atlatma karakteri|
|------------|----------------------|
|_T ("\\\t")|_T ("\t")|
|_T ("\\\n")|_T ("\n")|
|_T ("\\\r")|_T ("\r")|
|_T ("\\\b")|_T ("\b")|
|_T ("LT")|_T ("\<")|
|_T ("GT")|_T (">")|
|_T ("AMP")|_T ("&")|

## <a name="getcolor"></a>AFX_GLOBAL_DATA:: GetColor

Belirtilen kullanıcı arabirimi öğesinin geçerli rengini alır.

```
COLORREF GetColor(int nColor);
```

### <a name="parameters"></a>Parametreler

*nColor*<br/>
'ndaki Rengi alınan bir kullanıcı arabirimi öğesini belirten bir değer. Geçerli değerlerin listesi için bkz. [Getsyscbir](/windows/win32/api/winuser/nf-winuser-getsyscolor) yönteminin *nindex* parametresi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen kullanıcı arabirimi öğesinin RGB renk değeri. Daha fazla bilgi için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

*NColor* parametresi aralık dışında ise, dönüş değeri sıfırdır. Sıfır de geçerli bir RGB değeri olduğundan, geçerli işletim sistemi tarafından bir sistem renginin desteklenip desteklenmediğini anlamak için bu yöntemi kullanamazsınız. Bunun yerine, renk desteklenmiyorsa NULL döndüren [GetSysColorBrush](/windows/win32/api/winuser/nf-winuser-getsyscolorbrush) metodunu kullanın.

## <a name="getdirect2dfactory"></a>AFX_GLOBAL_DATA:: GetDirect2dFactory

Genel verilerde depolanan ID2D1Factory arabirimine yönelik bir işaretçi döndürür. Arabirim başlatılmamışsa, oluşturulur ve Varsayılan parametrelere sahiptir.

```
ID2D1Factory* GetDirect2dFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika işleminin başarılı olması durumunda ID2D1Factory arabirimine yönelik bir işaretçi, oluşturma başarısız olursa veya geçerli Işlem sisteminin D2D desteği yoksa NULL.

## <a name="gethandcursor"></a>AFX_GLOBAL_DATA:: GetHandCursor

Bir el ile benzeyen ve tanımlayıcısı IDC_HAND olan önceden tanımlanmış imleci alır.

```
HCURSOR GetHandCursor();
```

### <a name="return-value"></a>Dönüş Değeri

El işaretçisinin tutamacı.

## <a name="getnonclientmetrics"></a>AFX_GLOBAL_DATA:: Getnonclientmetrikleri

Küçültülmüş olmayan pencerelerin istemci olmayan alanıyla ilişkili ölçümleri alır.

```
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```

### <a name="parameters"></a>Parametreler

*bilgisine*<br/>
[in, out] Simge dışı olmayan bir pencerenin istemci olmayan alanıyla ilişkili ölçeklenebilir ölçümleri içeren [clientmetrik](/windows/win32/api/winuser/ns-winuser-nonclientmetricsw) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

## <a name="gettextheight"></a>AFX_GLOBAL_DATA:: GetTextHeight

Geçerli yazı tipindeki metin karakterlerinin yüksekliğini alır.

```
int GetTextHeight(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parametreler

*bHorz*<br/>
'ndaki Metin yatay olarak çalıştırıldığında karakterlerin yüksekliğini almak için TRUE; Metin dikey olarak çalıştırıldığında karakterlerin yüksekliğini almak için FALSE. Varsayılan değer TRUE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Geçerli yazı tipinin, Ascender öğesinden kendi Descender ölçülerek ölçülen yüksekliği.

## <a name="getwicfactory"></a>AFX_GLOBAL_DATA:: GetWICFactory

Genel verilerde depolanan ı' ıimagingfactory arabirimine bir işaretçi döndürür. Arabirim başlatılmamışsa, oluşturulur ve Varsayılan parametrelere sahiptir.

```
IWICImagingFactory* GetWICFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Bir fabrika işleminin başarılı olması veya oluşturma Işlemi başarısız olursa veya geçerli Işlem sisteminde WIC desteği yoksa, ıimabgingfactory arabirimine yönelik bir işaretçi.

## <a name="getwritefactory"></a>AFX_GLOBAL_DATA:: GetWriteFactory

Genel verilerde depolanan IDWriteFactory arabirimine bir işaretçi döndürür. Arabirim başlatılmamışsa, oluşturulur ve Varsayılan parametrelere sahiptir.

```
IDWriteFactory* GetWriteFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika başarılı bir şekilde oluşturulduğunda IDWriteFactory arabirimine yönelik bir işaretçi veya oluşturma başarısız olursa veya geçerli Işlem sisteminin DirectWrite desteği yoksa NULL.

## <a name="initd2d"></a>AFX_GLOBAL_DATA::InitD2D

D2D, DirectWrite ve WIC fabrikalarını başlatır. Ana pencere başlatılmadan önce bu yöntemi çağırın.

```
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Parametreler

*d2dFactoryType*<br/>
D2D fabrikasının ve oluşturduğu kaynakların iş parçacığı modeli.

*writeFactoryType*<br/>
Yazma fabrikası nesnesinin paylaşılıp paylaşılmayacağını veya yalıtılacağını belirten bir değer

### <a name="return-value"></a>Dönüş Değeri

Fabrikalar ınitiallalizrd ise TRUE, değilse FALSE döndürür

## <a name="is32biticons"></a>AFX_GLOBAL_DATA::Is32BitIcons

Önceden tanımlanmış 32 bitlik simgelerin desteklenip desteklenmediğini gösterir.

```
BOOL Is32BitIcons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Önceden tanımlanmış 32 bit simgeler destekleniyorsa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, çerçeve 32 bitlik yerleşik simgeleri destekliyorsa ve işletim sistemi piksel başına 16 bit ya da daha fazlasını destekliyorsa ve görüntüler yüksek bir karşıtlıkta görüntülenmiyorsa TRUE döndürür.

## <a name="isaccessibilitysupport"></a>AFX_GLOBAL_DATA:: IsAccessibilitySupport

Microsoft Etkin Erişilebilirlik desteğinin etkin olup olmadığını gösterir.

```
BOOL IsAccessibilitySupport() const;
```

### <a name="return-value"></a>Dönüş Değeri

Erişilebilirlik desteği etkinse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Microsoft Etkin Erişilebilirlik, uygulamaları erişilebilir hale getirmek için daha önceki bir çözümdür. Microsoft UI Otomasyonu, Microsoft Windows için yeni erişilebilirlik modelidir ve yardımcı teknoloji ürünlerinin ve otomatikleştirilmiş test araçlarının ihtiyaçlarını karşılamak üzere tasarlanmıştır.

Etkin Erişilebilirlik desteğini etkinleştirmek veya devre dışı bırakmak için [AFX_GLOBAL_DATA:: EnableAccessibilitySupport](#enableaccessibilitysupport) metodunu kullanın.

## <a name="isd2dinitialized"></a>AFX_GLOBAL_DATA::IsD2DInitialized

D2D 'in başlatılmış olup olmadığını belirler

```
BOOL IsD2DInitialized() const;
```

### <a name="return-value"></a>Dönüş Değeri

D2D başlatılmışsa TRUE; Aksi halde yanlış.

## <a name="isdwmcompositionenabled"></a>AFX_GLOBAL_DATA:: Isdwmkompozisyontionenabled

Windows [Dwmiskompozisyontionenabled](/windows/win32/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) yöntemini çağırmak için basit bir yol sağlar.

```
BOOL IsDwmCompositionEnabled();
```

### <a name="return-value"></a>Dönüş Değeri

[Masaüstü Pencere Yöneticisi](/windows/win32/dwm/dwm-overview) (dwm) oluşturma etkinse true; Aksi takdirde, FALSE.

## <a name="ishighcontrastmode"></a>AFX_GLOBAL_DATA:: ıshighınstmode

Görüntülerin Şu anda yüksek karşıtlıkta görüntülenip görüntülenmediğini gösterir.
```
BOOL IsHighContrastMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntüler şu anda siyah veya beyaz yüksek karşıtlık modunda görüntüleniyorsa doğru. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Siyah yüksek karşıtlık modunda, ışığın karşısındaki kenarlar beyazdır ve arka plan siyah olur. Beyaz yüksek karşıtlık modunda, ışığın karşısındaki kenarlar siyah ve arka plan da beyazdır.

## <a name="iswindowslayersupportavailable"></a>AFX_GLOBAL_DATA:: ıswindowslayersupportavailable

İşletim sisteminin katmanlı pencereleri destekleyip desteklemediğini gösterir.

```
BOOL IsWindowsLayerSupportAvailable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Katmanlı pencereler destekleniyorsa, doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Katmanlı pencereler destekleniyorsa, *akıllı yerleştirme* işaretçileri katmanlı pencereler kullanır.

## <a name="m_busebuiltin32biticons"></a>AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons

Çerçevenin önceden tanımlanmış 32 bit renk simgeleri mi yoksa daha düşük bir çözümlemenin simgelerini mi kullanacağını gösterir.

```
BOOL  m_bUseBuiltIn32BitIcons;
```

### <a name="remarks"></a>Açıklamalar

TRUE, Framework 'ün 32 bitlik renk simgeleri kullanmasını belirtir; FALSE, daha düşük çözünürlüklü simgeler belirtir. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu bu üyeyi doğru olarak başlatır.

Bu üyenin uygulama başlangıcında ayarlanması gerekir.

## <a name="m_busesystemfont"></a>AFX_GLOBAL_DATA::m_bUseSystemFont

Menüler, araç çubukları ve şeritler için bir sistem yazı tipinin kullanılıp kullanılmadığını gösterir.

```
BOOL m_bUseSystemFont;
```

### <a name="remarks"></a>Açıklamalar

DOĞRU, bir sistem yazı tipinin kullanılacağını belirtir; Aksi takdirde, FALSE. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu bu üyeyi false olarak başlatır.

Bu üyeyi test etmek, Framework 'ün kullanılacak yazı tipini belirlemesi için tek yol değildir. Bu `AFX_GLOBAL_DATA::UpdateFonts` Yöntem, menülere, araç çubuklarına ve şeritlere uygulanabilecek görsel stilleri belirlemek için varsayılan ve alternatif yazı tiplerini de sınar.

## <a name="m_hcurhand"></a>AFX_GLOBAL_DATA::m_hcurHand

El imleci için tanıtıcıyı depolar.

```
HCURSOR m_hcurHand;
```

## <a name="m_hcurstretch"></a>AFX_GLOBAL_DATA::m_hcurStretch

Yatay Esnetme imleci için tanıtıcıyı depolar.

```
HCURSOR m_hcurStretch;
```

## <a name="m_hcurstretchvert"></a>AFX_GLOBAL_DATA::m_hcurStretchVert

Dikey Esnetme imleci için tanıtıcıyı depolar.

```
HCURSOR m_hcurStretchVert;
```

## <a name="m_hicontool"></a>AFX_GLOBAL_DATA::m_hiconTool

Araç simgesinin tanıtıcısını depolar.

```
HICON m_hiconTool;
```

## <a name="m_nautohidetoolbarmargin"></a>AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin

En soldaki otomatik gizle araç çubuğundan, yerleştirme çubuğunun sol tarafına olan sapmayı belirtir.

```
int  m_nAutoHideToolBarMargin;
```

### <a name="remarks"></a>Açıklamalar

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu bu üyeyi 4 piksel olarak başlatır.

## <a name="m_nautohidetoolbarspacing"></a>AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing

Otomatik gizleme araç çubukları arasındaki boşluğu belirtir.

```
int   m_nAutoHideToolBarSpacing;
```

### <a name="remarks"></a>Açıklamalar

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu bu üyeyi 14 piksel olarak başlatır.

## <a name="m_ndragframethicknessdock"></a>AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Sabitlenmiş durumu göstermek için kullanılan sürükleme çerçevesinin kalınlığını belirtir.

```
int  m_nDragFrameThicknessDock;
```

### <a name="remarks"></a>Açıklamalar

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu bu üyeyi 3 piksel olarak başlatır.

## <a name="m_ndragframethicknessfloat"></a>AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat

Kayan durumu göstermek için kullanılan sürükleme çerçevesinin kalınlığını belirtir.

```
int  m_nDragFrameThicknessFloat;
```

### <a name="remarks"></a>Açıklamalar

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu bu üyeyi 4 piksel olarak başlatır.

## <a name="onsettingchange"></a>AFX_GLOBAL_DATA:: OnSettingChange

Masaüstünün menü animasyon ve görev çubuğu otomatik gizleme özelliklerinin geçerli durumunu algılar.

```
void OnSettingChange();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, çerçeve değişkenlerini kullanıcının masaüstünün belirli özniteliklerinin durumuna ayarlar. Bu yöntem, menü animasyonu, menü Soldur ve görev çubuğunun otomatik gizleme özelliklerinin geçerli durumunu algılar.

## <a name="registerwindowclass"></a>AFX_GLOBAL_DATA:: RegisterWindowClass

Belirtilen MFC pencere sınıfını kaydeder.

```
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```

### <a name="parameters"></a>Parametreler

*lpszClassNamePrefix*<br/>
'ndaki Kayıt yapılacak pencere sınıfının adı.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa kayıtlı sınıfın tam adı; Aksi takdirde, [kaynak özel durumu](exception-processing.md#afxthrowresourceexception).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri, *lpszClassNamePrefix* parametre dizesinin iki nokta ile ayrılmış listesidir ve geçerli uygulama örneğinin tanıtıcılarının onaltılık metin gösterimleridir; tanımlayıcısı IDC_ARROW olan ok imleci olan uygulama imleci. ve arka plan Fırçası. MFC pencere sınıflarını kaydetme hakkında daha fazla bilgi için bkz. [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass).

## <a name="resume"></a>AFX_GLOBAL_DATA:: özgeçmişi

Windows temalarını ve görsel stilleri destekleyen yöntemlere erişen iç işlev işaretçileri yeniden başlatılır.

```
BOOL Resume();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE. Bu yöntem, hata ayıklama modunda bu yöntemin başarısız olup olmadığını onaylar.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Framework [WM_POWERBROADCAST](/windows/win32/Power/wm-powerbroadcast) iletisini aldığında çağrılır.

## <a name="setlayeredattrib"></a>AFX_GLOBAL_DATA:: SetLayeredAttrib

Windows [SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes) yöntemini çağırmak için basit bir yol sağlar.

```
BOOL SetLayeredAttrib(
    HWND hwnd,
    COLORREF crKey,
    BYTE bAlpha,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki Katmanlı pencerenin tutamacı.

*crKey*<br/>
'ndaki [Masaüstü Pencere Yöneticisi](/windows/win32/dwm/dwm-overview) katmanlı pencereyi oluşturmak için kullandığı saydamlık rengi.

*bAlpha*<br/>
'ndaki Katmanlı pencerenin opaklığını anlatmak için kullanılan alfa değeri.

*dwFlags*<br/>
'ndaki Hangi yöntem parametrelerinin kullanılacağını belirten bir bit düzeyinde birleşim (veya). *CrKey* parametresini saydamlık rengi olarak kullanmak için LWA_COLORKEY belirtin. Katmanlı pencerenin opaklığını belirlemek için *bAlpha* parametresini kullanmak üzere LWA_ALPHA belirtin.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

## <a name="setmenufont"></a>AFX_GLOBAL_DATA:: SetMenuFont

Belirtilen mantıksal yazı tipini oluşturur.

```
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
'ndaki Bir fontun özniteliklerini içeren bir yapıya yönelik işaretçi.

*bHorz*<br/>
'ndaki Metnin yatay olarak çalışacağını belirtmek için TRUE; Metnin dikey olarak çalıştığını belirtmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE. Bu yöntem, hata ayıklama modunda bu yöntemin başarısız olup olmadığını onaylar.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, varsayılan menü öğelerinde kullanılan yatay bir düzenli yazı tipi, altı çizili yazı tipi ve kalın yazı tipi oluşturur. Bu yöntem, isteğe bağlı olarak normal bir dikey yazı tipi oluşturur. Mantıksal yazı tipleri hakkında daha fazla bilgi için bkz. [CFont:: CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect).

## <a name="updatefonts"></a>AFX_GLOBAL_DATA:: UpdateFonts

Framework tarafından kullanılan mantıksal yazı tiplerini yeniden başlatır.

```
void UpdateFonts();
```

### <a name="remarks"></a>Açıklamalar

Mantıksal yazı tipleri hakkında daha fazla bilgi için `CFont::CreateFontIndirect`bkz.

## <a name="updatesyscolors"></a>AFX_GLOBAL_DATA:: UpdateSysColors

Çerçeve tarafından kullanılan renkleri, renk derinliğini, fırçaları, kalemleri ve görüntüleri başlatır.

```
void UpdateSysColors();
```

## <a name="biswindows7"></a>AFX_GLOBAL_DATA::bIsWindows7

Uygulamanın Windows 7 veya sonraki sürümlerinde yürütülüp yürütülmediğini belirtir.

```
BOOL bIsWindows7;
```

## <a name="clractivecaptiongradient"></a>AFX_GLOBAL_DATA:: clrActiveCaptionGradient

Etkin açıklamalı alt yazısının gradyan rengini belirtir. Genellikle yerleştirme bölmeleri için kullanılır.

```
COLORREF clrActiveCaptionGradient;
```

## <a name="clrinactivecaptiongradient"></a>AFX_GLOBAL_DATA:: clrInactiveCaptionGradient

Etkin olmayan açıklamalı alt yazısının gradyan rengini belirtir. Genellikle yerleştirme bölmeleri için kullanılır.

```
COLORREF clrInactiveCaptionGradient;
```

## <a name="getitaskbarlist"></a>AFX_GLOBAL_DATA:: GetITaskbarList

Genel verilerde `ITaskBarList` arabirime yönelik bir işaretçi oluşturur ve depolar.

```
ITaskbarList *GetITaskbarList();
```

### <a name="return-value"></a>Dönüş Değeri

Görev çubuğu listesi nesnesinin `ITaskbarList` oluşturulması başarılı olursa arabirime yönelik bir işaretçi. Oluşturma başarısız olursa veya geçerli Işletim sistemi Windows 7 ' den azsa NULL olur.

## <a name="getitaskbarlist3"></a>AFX_GLOBAL_DATA::GetITaskbarList3

Genel verilerde `ITaskBarList3` arabirime yönelik bir işaretçi oluşturur ve depolar.

```
ITaskbarList3 *GetITaskbarList3();
```

### <a name="return-value"></a>Dönüş Değeri

Görev çubuğu listesi nesnesinin `ITaskbarList3` oluşturulması başarılı olursa arabirime yönelik bir işaretçi. Oluşturma başarısız olursa veya geçerli Işletim sistemi Windows 7 ' den azsa NULL olur.

## <a name="getshellautohidebars"></a>AFX_GLOBAL_DATA:: Getshellautohideçubuklarının

Kabuk otomatik gizleme çubuklarının konumlarını belirler.

```
int GetShellAutohideBars();
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizleme çubuklarının konumlarını belirten kodlanmış bayraklar içeren bir tamsayı değeri. Aşağıdaki değerleri birleştirebilirler: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.

## <a name="releasetaskbarrefs"></a>AFX_GLOBAL_DATA:: ReleaseTaskBarRefs

`GetITaskbarList` Ve`GetITaskbarList3` yöntemleri aracılığıyla elde edilen arabirimleri yayınlar.

```
void ReleaseTaskBarRefs();
```

## <a name="shellcreateitemfromparsingname"></a>AFX_GLOBAL_DATA:: Shellcreateıtemfromparsingname

Ayrıştırma adından bir kabuk öğesi nesnesi oluşturur ve başlatır.

```
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,
    IBindCtx *pbc,
    REFIID riid,
    void **ppv);
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
'ndaki Görünen ad işaretçisi.

*PBC*<br/>
Ayrıştırma işlemini denetleyen bağlama bağlamına yönelik bir işaretçi.

*riıd*<br/>
Arabirim KIMLIĞINE başvuru.

*PPV*<br/>
dışı Bu işlev döndüğünde, *riıd*içinde istenen arabirim işaretçisini içerir. Bu genellikle `IShellItem` veya `IShellItem2`olur.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür; Aksi halde bir hata değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../hierarchy-chart.md)<br/>
[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](structures-styles-callbacks-and-message-maps.md)<br/>
[COLORREF](/windows/win32/gdi/colorref)<br/>
[Parçalar ve durumlar](/windows/win32/controls/parts-and-states)<br/>
[CDC::DrawText](cdc-class.md#drawtext)<br/>
[DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex)<br/>
[Masaüstü Pencere Yöneticisi](/windows/win32/dwm/dwm-overview)<br/>
[DWM birleşimini etkinleştirin ve denetleyin](/windows/win32/dwm/composition-ovw)<br/>
[UI Otomasyonu ve Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)<br/>
[Getsyscrenkli Işlevi](/windows/win32/api/winuser/nf-winuser-getsyscolor)<br/>
[GetSysColorBrush](/windows/win32/api/winuser/nf-winuser-getsyscolorbrush)<br/>
[CLIENTNONÖLÇÜM yapısı](/windows/win32/api/winuser/ns-winuser-nonclientmetricsw)<br/>
[AfxRegisterClass](application-information-and-management.md#afxregisterclass)<br/>
[AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)<br/>
[SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes)
