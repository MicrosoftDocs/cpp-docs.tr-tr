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
ms.openlocfilehash: 9b6a462cf359bbd31958509c4fe7d0d71e490d11
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694315"
---
# <a name="afxglobaldata-structure"></a>AFX_GLOBAL_DATA Yapısı

`AFX_GLOBAL_DATA` Yapısı, alanları ve framework yönetmek veya uygulamanızın davranışını ve görünümünü özelleştirmek için kullanılan yöntemleri içerir.

## <a name="syntax"></a>Sözdizimi

```
struct AFX_GLOBAL_DATA
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|Oluşturur bir `AFX_GLOBAL_DATA` yapısı.|
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[AFX_GLOBAL_DATA::CleanUp](#cleanup)|Fırçalar, yazı tipleri ve DLL'ler gibi framework tarafından ayrılan kaynakları serbest bırakır.|
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#d2d1makerotatematrix)|Belirtilen bir nokta etrafında bir belirtilen açıyla döndüren döndürme dönüşümü oluşturur.|
|[AFX_GLOBAL_DATA::DrawParentBackground](#drawparentbackground)|Belirtilen alanda bir denetimin üst arka planı çizer.|
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#drawtextonglass)|Belirtilen metni belirtilen tema görsel stilde çizer.|
|[AFX_GLOBAL_DATA::ExcludeTag](#excludetag)|Belirtilen XML etiket çifti belirtilen arabellek kaldırır.|
|[AFX_GLOBAL_DATA::GetColor](#getcolor)|Belirtilen kullanıcı arabirimi öğesi geçerli rengini alır.|
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#getdirect2dfactory)|Bir işaretçi döndürür `ID2D1Factory` genel verilerde depolanan arabirimi. Arabirim başlatılmadı ise oluşturulur ve varsayılan parametrelere sahip.|
|[AFX_GLOBAL_DATA::GetHandCursor](#gethandcursor)|Bir yandan benzer önceden tanımlanmış imleci alır ve tanıtıcısı `IDC_HAND`.|
|[AFX_GLOBAL_DATA::GetITaskbarList](#getitaskbarlist)|Oluşturur ve genel verilerde ITaskBarList arabirimi için bir işaretçi depolar.|
|[AFX_GLOBAL_DATA::GetITaskbarList3](#getitaskbarlist3)|Oluşturur ve genel verilerde ITaskBarList3 arabirimi için bir işaretçi depolar.|
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#getnonclientmetrics)|İstemci olmayan alanındayken nonminimized Windows ile ilişkili ölçümleri alır.|
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#getshellautohidebars)|Kabuk otomatik konumlarını çubukları Gizle belirler.|
|[AFX_GLOBAL_DATA::GetTextHeight](#gettextheight)|Geçerli yazı tipi, metin karakterleri yüksekliğini alır.|
|[AFX_GLOBAL_DATA::GetWICFactory](#getwicfactory)|Bir işaretçi döndürür `IWICImagingFactory` genel verilerde depolanan arabirimi. Arabirim başlatılmadı ise oluşturulur ve varsayılan parametrelere sahip.|
|[AFX_GLOBAL_DATA::GetWriteFactory](#getwritefactory)|Bir işaretçi döndürür `IDWriteFactory` genel verilerde depolanan arabirimi. Arabirim başlatılmadı ise oluşturulur ve varsayılan parametrelere sahip.|
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|Başlatır `D2D`, `DirectWrite`, ve `WIC` üreteçleri. Ana pencereyi başlatılmadan önce bu yöntemi çağırın.|
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|Önceden tanımlanmış 32-bit simgeler desteklenip desteklenmediğini gösterir.|
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|Belirler olmadığını `D2D` başlatıldı.|
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#isdwmcompositionenabled)|Windows çağırmak için basit bir yol sağlar [Dwmıscompositionenabled](/windows/desktop/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) yöntemi.|
|[AFX_GLOBAL_DATA::IsHighContrastMode](#ishighcontrastmode)|Görüntüleri yüksek karşıtlık, şu anda gösterilip gösterilmediğini gösterir.|
|[AFX_GLOBAL_DATA::OnSettingChange](#onsettingchange)|Desktop'ın menü animasyon ve görev autohide özellikleri geçerli durumunu algılar.|
|[AFX_GLOBAL_DATA::RegisterWindowClass](#registerwindowclass)|Belirtilen MFC pencere sınıfını kaydeder.|
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#releasetaskbarrefs)|Arabirimleri GetITaskbarList ve GetITaskbarList3 yöntemleri elde edilen serbest bırakır.|
|[AFX_GLOBAL_DATA::Resume](#resume)|Windows Destek yöntemlere erişmek iç işlev işaretçileri yeniden başlatır [temalar ve görsel stilleri](/windows/desktop/Controls/visual-styles-overview).|
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#setlayeredattrib)|Windows çağırmak için basit bir yol sağlar [SetLayeredWindowAttributes](/windows/desktop/api/winuser/nf-winuser-setlayeredwindowattributes) yöntemi.|
|[AFX_GLOBAL_DATA::SetMenuFont](#setmenufont)|Belirtilen mantıksal yazı tipi oluşturur.|
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#shellcreateitemfromparsingname)|Oluşturur ve bir kabuk öğesi nesnesi ayrıştırma adından başlatır.|
|[AFX_GLOBAL_DATA::UpdateFonts](#updatefonts)|Framework tarafından kullanılan mantıksal yazı tiplerinin reintializes.|
|[AFX_GLOBAL_DATA::UpdateSysColors](#updatesyscolors)|Renkler, renk derinliği, Fırçalar, kalemler ve framework tarafından kullanılan görüntüleri başlatır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)|Etkinleştirir veya Microsoft Active Accessibility desteğini devre dışı bırakır. Etkin Erişilebilirlik kullanıcı arabirimi öğeleri hakkında bilgi kullanıma sunmak için güvenilir yöntemleri sağlar.|
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)|Microsoft Active Accessibility desteği etkin olup olmadığını gösterir.|
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#iswindowslayersupportavailable)|Katmanlı windows işletim sistemini destekleyip desteklemediğini belirtir.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#bisosalphablendingsupport)|Geçerli işletim sistemi alfa karıştırma destekleyip desteklemediğini belirtir.|
|[AFX_GLOBAL_DATA::bIsWindows7](#biswindows7)|Uygulama altında Windows 7 işletim sistemi veya üzeri yürütülmekte olan olup olmadığını gösterir|
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#clractivecaptiongradient)|Etkin Başlık gradyan rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.|
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#clrinactivecaptiongradient)|Etkin olmayan etkin başlık gradyan rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.|
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#m_busebuiltin32biticons)|Çerçevenin önceden tanımlanmış 32 bit renk simgelerinin genişliğini veya daha düşük bir çözünürlüğe simgelerini kullanıp kullanmadığını belirtir.|
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#m_busesystemfont)|Sistem yazı tipini menüleri, araç çubukları ve şeritler için kullanılıp kullanılmayacağını belirtir.|
|[AFX_GLOBAL_DATA::m_hcurHand](#m_hcurhand)|Tanıtıcı elde imleci için depolar.|
|[AFX_GLOBAL_DATA::m_hcurStretch](#m_hcurstretch)|Yatay imleç esnetme için tanıtıcı depolar.|
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#m_hcurstretchvert)|Esnetme dikey imleç için tanıtıcı depolar.|
|[AFX_GLOBAL_DATA::m_hiconTool](#m_hicontool)|Aracı simge tanıtıcı depolar.|
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#m_nautohidetoolbarmargin)|En soldaki autohide araç çubuğundan takma çubuğu sol tarafına uzaklığını belirtir.|
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#m_nautohidetoolbarspacing)|Otomatik Gizle araç çubukları arasındaki boşluğu belirtir.|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#m_ndragframethicknessdock)|Sabitlenmiş durum iletişim kurmak için kullanılan Sürükle çerçeve kalınlığı belirtir.|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#m_ndragframethicknessfloat)|Kayan duruma iletişim kurmak için kullanılan Sürükle çerçeve kalınlığı belirtir.|

### <a name="remarks"></a>Açıklamalar

Verilerin çoğu `AFX_GLOBAL_DATA` yapısı, uygulamanız başlatıldığında başlatılır.

### <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`AFX_GLOBAL_DATA`

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxglobals.h

### <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

## <a name="bisosalphablendingsupport"></a> AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport

İşletim sistemi alfa karıştırma destekleyip desteklemediğini belirtir.

```
BOOL  bIsOSAlphaBlendingSupport;
```

### <a name="remarks"></a>Açıklamalar

TRUE, alfa karıştırma desteklendiğini gösterir; Aksi takdirde FALSE.

## <a name="cleanup"></a> AFX_GLOBAL_DATA::CleanUp

Fırçalar, yazı tipleri ve DLL'ler gibi framework tarafından ayrılan kaynakları serbest bırakır.

```
void CleanUp();
```

## <a name="d2d1makerotatematrix"></a> AFX_GLOBAL_DATA::D2D1MakeRotateMatrix

Belirtilen bir nokta etrafında bir belirtilen açıyla döndüren döndürme dönüşümü oluşturur.

```
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,
    D2D1_POINT_2F center,
    D2D1_MATRIX_3X2_F *matrix);
```

### <a name="parameters"></a>Parametreler

*Açı*<br/>
Saat yönünde bir döndürme derece cinsinden açı.

*Merkezi*<br/>
Döndürmek istediğiniz hakkında noktası.

*Matris*<br/>
Bu yöntem döndürüldüğünde, yeni döndürme dönüşümü içerir. Bu parametre için depolama ayırmanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Aksi S_OK başarılı olursa ya da bir hata değeri döndürür.

## <a name="drawparentbackground"></a> AFX_GLOBAL_DATA::DrawParentBackground

Belirtilen alanda bir denetimin üst arka planı çizer.

```
BOOL DrawParentBackground(
    CWnd* pWnd,
    CDC* pDC,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
[in] Bir denetimin pencere işaretçisi.

*pDC*<br/>
[in] Bir cihaz bağlamı işaretçisi.

*lpRect*<br/>
[in] Alanın, çizmek için sınırların bir dikdörtgen işaretçisi. Varsayılan değer NULL olur.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

## <a name="drawtextonglass"></a> AFX_GLOBAL_DATA::DrawTextOnGlass

Belirtilen metni belirtilen tema görsel stilde çizer.

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
[in] Bir pencerenin tema verileri işlemek veya NULL. Çerçeve, bu parametre NULL değilse ve Temalar desteklenen metnini çizmek için belirtilen tema kullanır. Aksi takdirde, framework metnini çizmek için bir tema kullanmaz.

Kullanım [OpenThemeData](/windows/desktop/api/uxtheme/nf-uxtheme-openthemedata) bir HTHEME oluşturmak için yöntemi.

*pDC*<br/>
[in] Bir cihaz bağlamı işaretçisi.

*iPartId*<br/>
[in] İstenen metin görünümü olan denetim bölümü. Daha fazla bilgi için tablonun bölümleri sütununu görmek [bölümler ve durumlar](/windows/desktop/controls/parts-and-states). Bu değer 0 ise, varsayılan yazı tipi veya bir yazı tipi cihaz bağlamına seçili metni çizilir.

*iStateId*<br/>
[in] İstenen metin görünümü olan denetim durumu. Daha fazla bilgi için bkz: durumları sütun tablonun [bölümler ve durumlar](/windows/desktop/controls/parts-and-states).

*strText*<br/>
[in] Çizmek için metin.

*Rect*<br/>
[in] Belirtilen metin çizilen alanın sınır.

*CertOpenStore*<br/>
[in] Bitsel bir birleşimi (veya) belirtilen metnin nasıl çizilmeden belirten bayraklar.

Varsa *hTheme* parametresi `NULL` veya Temalar desteklenmez ve etkin *nFormat* parametresinin [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) yöntemi geçerli açıklar bayrakları. Temalar destekleniyorsa, *CertOpenStore* parametresinin [DrawThemeTextEx](/windows/desktop/api/uxtheme/nf-uxtheme-drawthemetextex) yöntemi geçerli bayrakları açıklar.

*nGlowSize*<br/>
[in] Belirtilen metin çizmeden önce arka plan üzerine çizilmiş bir parlaklık efekti boyutu. Varsayılan değer 0’dır.

*clrText*<br/>
[in] Belirtilen metin çizilen rengi. Varsayılan renk varsayılan değerdir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen metni çizmek için bir tema kullanılıyorsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir tema, bir uygulamanın görsel stil tanımlar. Bir tema, metin çizmek için kullanılan değil *hTheme* parametredir NULL veya [DrawThemeTextEx](/windows/desktop/api/uxtheme/nf-uxtheme-drawthemetextex) yöntemi desteklenmiyor veya [Masaüstü Pencere Yöneticisi](/windows/desktop/dwm/dwm-overview) (DWM) kompozisyonu devre dışı bırakıldı.

### <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COLORREF](/windows/desktop/gdi/colorref)<br/>
[Bölümler ve durumlar](/windows/desktop/controls/parts-and-states)<br/>
[CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)<br/>
[DrawThemeTextEx](/windows/desktop/api/uxtheme/nf-uxtheme-drawthemetextex)<br/>
[Masaüstü Pencere Yöneticisi](/windows/desktop/dwm/dwm-overview)<br/>
[DWM bileşimini etkinleştir ve denetle](/windows/desktop/dwm/composition-ovw)

## <a name="enableaccessibilitysupport"></a> AFX_GLOBAL_DATA::EnableAccessibilitySupport

Etkinleştirir veya Microsoft Active Accessibility desteğini devre dışı bırakır.

```
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Erişilebilirlik desteğini etkinleştirmek için TRUE; Erişilebilirlik desteği devre dışı bırakmak için FALSE. Varsayılan değer True'dur.

### <a name="remarks"></a>Açıklamalar

Etkin Erişilebilirlik şekilde programları ve Windows işletim sistemi iş yardımcı teknoloji ürünlerinin birlikte geliştiren bir COM tabanlı bir teknolojidir. Bu, kullanıcı arabirimi öğeleri hakkında bilgi kullanıma sunmak için güvenilir yöntemleri sağlar. Ancak, Microsoft UI Otomasyonu adlı yeni bir erişilebilirlik modeli kullanıma sunulmuştur. İki teknolojileri karşılaştırması için bkz: [UI Otomasyonu ve Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility).

Kullanım [AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport) Microsoft Active Accessibility desteği etkin olup olmadığını belirlemek için yöntemi.

### <a name="see-also"></a>Ayrıca Bkz.

[UI Otomasyonu ve Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)<br/>
[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)

## <a name="excludetag"></a> AFX_GLOBAL_DATA::ExcludeTag

Belirtilen XML etiket çifti belirtilen arabellek kaldırır.

```
BOOL ExcludeTag(
    CString& strBuffer,
    LPCTSTR lpszTag,
    CString& strTag,
    BOOL bIsCharsList = FALSE);
```

### <a name="parameters"></a>Parametreler

*strBuffer*<br/>
[in] Metin arabelleği.

*lpszTag*<br/>
[in] Açma ve kapama XML etiketlerini çiftinin adı.

*strTag*<br/>
[out] Bu yöntem döndürüldüğünde, *strTag* parametresi tarafından adlandırılan etiketleri açılış ve kapanış XML arasında olan metni içeren *lpszTag* parametresi. Tüm başta veya sonda boşluk sonuçtan kırpılır.

*bIsCharsList*<br/>
[in] Çıkış karakterlerinin tanınmasından dönüştürme simgeleri true *strTag* gerçek kaçış karakterleri; parametresine Dönüştürme işlemleri için FALSE. Varsayılan değer FALSE olur. Daha fazla bilgi için açıklamalara bakın.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir XML etiket çifti açılış ve kapanış etiketlerinin başlangıç ve bitiş çalıştırma belirtilen arabellek metin gösteren adlı oluşur. *StrBuffer* arabellek parametre belirtir ve *lpszTag* parametresi, XML etiketlerini adını belirtir.

Simgeler aşağıdaki tabloda belirtilen arabellekteki kaçış karakterleri kodlayın için kullanın. DOĞRU belirtme *bIsCharsList* sembolleri dönüştürmek için parametre *strTag* gerçek kaçış karakterleri içine parametresi. Aşağıdaki tablo kullanan [_T()](../../c-runtime-library/data-type-mappings.md) sembol belirtin ve karakter dizeleri kaçış makrosu.

|Sembol|Atlatma karakteri|
|------------|----------------------|
|_T ("\\\t")|_T("\t")|
|_T ("\\\n")|_T("\n")|
|_T ("\\\r")|_T("\r")|
|_T ("\\\b")|_T("\b")|
|_T("LT")|_T ("\<")|
|_T("GT")|_T("&GT;")|
|_T("AMP")|_T("&AMP;")|

## <a name="getcolor"></a> AFX_GLOBAL_DATA::GetColor

Belirtilen kullanıcı arabirimi öğesi geçerli rengini alır.

```
COLORREF GetColor(int nColor);
```

### <a name="parameters"></a>Parametreler

*nColor*<br/>
[in] Bir kullanıcı arabirimi öğesi olan renk alınan belirten bir değeri. Geçerli değerlerin listesi için bkz. *nIndex* parametresinin [GetSysColor](/windows/desktop/api/winuser/nf-winuser-getsyscolor) yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen kullanıcı arabirimi öğesi RGB renk değeri. Daha fazla bilgi için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

Varsa *nColor* parametresi aralık dışında olduğundan, dönüş değeri sıfırdır. Sıfır da geçerli bir RGB değeri olduğundan, sistem rengi geçerli işletim sistemi tarafından desteklenip desteklenmediğini belirlemek için bu yöntemi kullanamazsınız. Bunun yerine, [GetSysColorBrush](/windows/desktop/api/winuser/nf-winuser-getsyscolorbrush) rengi desteklenmiyorsa NULL döndüren bir yöntem.

### <a name="see-also"></a>Ayrıca Bkz.

[GetSysColor işlevi](/windows/desktop/api/winuser/nf-winuser-getsyscolor)<br/>
[COLORREF](/windows/desktop/gdi/colorref)<br/>
[GetSysColorBrush](/windows/desktop/api/winuser/nf-winuser-getsyscolorbrush)

## <a name="getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory

Genel veriler ID2D1Factory arabirimi için bir işaretçi döndürür. Arabirim başlatılmadı ise oluşturulur ve varsayılan parametrelere sahip.

```
ID2D1Factory* GetDirect2dFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika oluşturulması başarılı ya da oluşturulması başarısız olursa NULL ID2D1Factory arabirimi veya geçerli işletim sistemi için bir işaretçi D2D desteği yok.

## <a name="gethandcursor"></a>  AFX_GLOBAL_DATA::GetHandCursor

Bir yandan benzer ve ayarlanmış bir tanımlayıcıdır IDC_HAND önceden tanımlanmış imleci alır.

```
HCURSOR GetHandCursor();
```

### <a name="return-value"></a>Dönüş Değeri

İmleci elde tanıtıcısını.

## <a name="getnonclientmetrics"></a> AFX_GLOBAL_DATA::GetNonClientMetrics

İstemci olmayan alanındayken nonminimized Windows ile ilişkili ölçümleri alır.

```
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```

### <a name="parameters"></a>Parametreler

*Bilgileri*<br/>
[out içinde] A [NONCLIENTMETRICS](/windows/desktop/api/winuser/ns-winuser-tagnonclientmetricsa) nonminimized pencerenin istemci olmayan alanın ile ilişkili ölçeklenebilir ölçümleri içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="see-also"></a>Ayrıca Bkz.

[NONCLIENTMETRICS yapısı](/windows/desktop/api/winuser/ns-winuser-tagnonclientmetricsa)

## <a name="gettextheight"></a> AFX_GLOBAL_DATA::GetTextHeight

Geçerli yazı tipi, metin karakterleri yüksekliğini alır.

```
int GetTextHeight(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parametreler

*bHorz*<br/>
[in] Metin yatay olarak çalıştığında karakterlerin yüksekliği almak için TRUE; Metin dikey olarak çalıştığında karakterlerin yüksekliği almak için FALSE. Varsayılan değer True'dur.

### <a name="return-value"></a>Dönüş Değeri

, Ascender için kendi descender ölçülür geçerli yazı yüksekliği.

## <a name="getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory

Genel veriler IWICImagingFactory arabirimi için bir işaretçi döndürür. Arabirim başlatılmadı ise oluşturulur ve varsayılan parametrelere sahip.

```
IWICImagingFactory* GetWICFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika oluşturulması başarılı ya da oluşturulması başarısız olursa NULL IWICImagingFactory arabirimi veya geçerli işletim sistemi için bir işaretçi WIC desteği yok.

## <a name="getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory

Genel veriler IDWriteFactory arabirimi için bir işaretçi döndürür. Arabirim başlatılmadı ise oluşturulur ve varsayılan parametrelere sahip.

```
IDWriteFactory* GetWriteFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Fabrika oluşturulması başarılı ya da oluşturulması başarısız olursa NULL IDWriteFactory arabirimi veya geçerli işletim sistemi için bir işaretçi DirectWrite desteği yok.

## <a name="initd2d"></a> AFX_GLOBAL_DATA::InitD2D

D2D ve DirectWrite WIC fabrikaları başlatır. Ana pencereyi başlatılmadan önce bu yöntemi çağırın.

```
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Parametreler

*d2dFactoryType*<br/>
D2D Fabrika ve kaynakları iş parçacığı modeli oluşturur.

*writeFactoryType*<br/>
Yazma üretecini paylaşılan veya yalıtılmış olup olmadığını belirten bir değeri

### <a name="return-value"></a>Dönüş Değeri

DOĞRU fabrikaları intilalizrd, FALSE - Aksi durumda olup olmadığını döndürür.

## <a name="is32biticons"></a> AFX_GLOBAL_DATA::Is32BitIcons

Önceden tanımlanmış 32-bit simgeler desteklenip desteklenmediğini gösterir.

```
BOOL Is32BitIcons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Önceden tanımlanmış 32-bit simgeler destekleniyorsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, framework 32-bit yerleşik simgeler, destekliyorsa ve işletim sistemi, 16 bit / piksel veya daha fazla destekliyorsa ve görüntüleri yüksek karşıtlık görüntülenmiyorsa TRUE döndürür.

## <a name="isaccessibilitysupport"></a> AFX_GLOBAL_DATA::IsAccessibilitySupport

Microsoft Active Accessibility desteği etkin olup olmadığını gösterir.

```
BOOL IsAccessibilitySupport() const;
```

### <a name="return-value"></a>Dönüş Değeri

Erişilebilirlik destek etkinse TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Microsoft Active Accessibility uygulamaları erişilebilir yapmak için önceki çözümü oldu. Microsoft UI Otomasyonu yeni erişilebilirlik model Microsoft Windows için yardımcı teknoloji ürünlerinin ihtiyaçlarınızı karşılamak üzere tasarlanmıştır ve otomatikleştirilmiş test araçları.

Kullanım [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport) etkinleştirme veya devre dışı Active Accessibility desteği yöntemi.

### <a name="see-also"></a>Ayrıca Bkz.

[UI Otomasyonu ve Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)

## <a name="isd2dinitialized"></a> AFX_GLOBAL_DATA::IsD2DInitialized

D2D başlatılmış olup olmadığını belirler

```
BOOL IsD2DInitialized() const;
```

### <a name="return-value"></a>Dönüş Değeri

D2D başlatıldı TRUE; Aksi durumda FALSE.

## <a name="isdwmcompositionenabled"></a> AFX_GLOBAL_DATA::IsDwmCompositionEnabled

Windows çağırmak için basit bir yol sağlar [Dwmıscompositionenabled](/windows/desktop/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) yöntemi.

```
BOOL IsDwmCompositionEnabled();
```

### <a name="return-value"></a>Dönüş Değeri

TRUE ise [Masaüstü Pencere Yöneticisi](/windows/desktop/dwm/dwm-overview) (DWM) kompozisyonu etkinse; Aksi takdirde FALSE.

### <a name="see-also"></a>Ayrıca Bkz.

[Masaüstü Pencere Yöneticisi](/windows/desktop/dwm/dwm-overview)<br/>
[DWM bileşimini etkinleştir ve denetle](/windows/desktop/dwm/composition-ovw)

## <a name="ishighcontrastmode"></a> AFX_GLOBAL_DATA::IsHighContrastMode

Görüntüleri yüksek karşıtlık, şu anda gösterilip gösterilmediğini gösterir.
```
BOOL IsHighContrastMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntüleri şu anda siyah veya beyaz yüksek karşıtlık modunda görüntüleniyorsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Siyah yüksek karşıtlık modunda beyaz ışık dönük kenarlar ve arka planı siyah. Beyaz yüksek karşıtlık modunda ışık dönük kenarlar için siyah olur ve arka planı beyaz.

## <a name="iswindowslayersupportavailable"></a> AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable

Katmanlı windows işletim sistemini destekleyip desteklemediğini belirtir.

```
BOOL IsWindowsLayerSupportAvailable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Katmanlı windows destekleniyorsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Katmanlı windows destekleniyorsa, *akıllı yerleştirme* işaretçileri katmanlı windows kullanın.

## <a name="m_busebuiltin32biticons"></a> AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons

Çerçevenin önceden tanımlanmış 32 bit renk simgelerinin genişliğini veya daha düşük bir çözünürlüğe simgelerini kullanıp kullanmadığını belirtir.

```
BOOL  m_bUseBuiltIn32BitIcons;
```

### <a name="remarks"></a>Açıklamalar

Framework 32 bit renk simgelerinin genişliğini kullanmasını TRUE belirtir. Daha düşük çözünürlüklü simgeleri FALSE belirtir. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye true başlatır.

Bu üye, uygulama başlangıcında ayarlamanız gerekir.

## <a name="m_busesystemfont"></a> AFX_GLOBAL_DATA::m_bUseSystemFont

Sistem yazı tipini menüleri, araç çubukları ve şeritler için kullanılıp kullanılmayacağını belirtir.

```
BOOL m_bUseSystemFont;
```

### <a name="remarks"></a>Açıklamalar

Sistem yazı tipini kullan TRUE belirtir; Aksi takdirde FALSE. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye yanlış başlatır.

Bu üye'test etme, kullanılacak yazı tipini belirlemek için framework tek yolu değil. `AFX_GLOBAL_DATA::UpdateFonts` Yöntemi ayrıca hangi görsel stilleri menüleri, araç çubukları ve şeritler için uygulanabilir olduğunu belirlemek için varsayılan ve alternatif yazı tipleri sınar.

## <a name="m_hcurhand"></a> AFX_GLOBAL_DATA::m_hcurHand

Tanıtıcı elde imleci için depolar.

```
HCURSOR m_hcurHand;
```

## <a name="m_hcurstretch"></a> AFX_GLOBAL_DATA::m_hcurStretch

Yatay imleç esnetme için tanıtıcı depolar.

```
HCURSOR m_hcurStretch;
```

## <a name="m_hcurstretchvert"></a> AFX_GLOBAL_DATA::m_hcurStretchVert

Esnetme dikey imleç için tanıtıcı depolar.

```
HCURSOR m_hcurStretchVert;
```

## <a name="m_hicontool"></a> AFX_GLOBAL_DATA::m_hiconTool

Aracı simge tanıtıcı depolar.

```
HICON m_hiconTool;
```

## <a name="m_nautohidetoolbarmargin"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin

En soldaki autohide araç çubuğundan dock çubuğunun sol tarafındaki uzaklığını belirtir.

```
int  m_nAutoHideToolBarMargin;
```

### <a name="remarks"></a>Açıklamalar

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye için 4 piksel başlatır.

## <a name="m_nautohidetoolbarspacing"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing

Otomatik Gizle araç çubukları arasındaki boşluğu belirtir.

```
int   m_nAutoHideToolBarSpacing;
```

### <a name="remarks"></a>Açıklamalar

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye için 14 piksel başlatır.

## <a name="m_ndragframethicknessdock"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Yerleşik durumunu göstermek için kullanılan Sürükle çerçeve kalınlığı belirtir.

```
int  m_nDragFrameThicknessDock;
```

### <a name="remarks"></a>Açıklamalar

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucusu 3 piksel bu üyeye başlatır.

## <a name="m_ndragframethicknessfloat"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat

Kayan durumunu göstermek için kullanılan Sürükle çerçeve kalınlığı belirtir.

```
int  m_nDragFrameThicknessFloat;
```

### <a name="remarks"></a>Açıklamalar

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye için 4 piksel başlatır.

## <a name="onsettingchange"></a> AFX_GLOBAL_DATA::OnSettingChange

Desktop'ın menü animasyon ve görev autohide özellikleri geçerli durumunu algılar.

```
void OnSettingChange();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcının masaüstü belirli bir öznitelik durumuna framework değişkenleri ayarlar. Bu yöntem, menü animasyon, menü fade ve görev çubuğunda autohide özellikleri geçerli durumunu algılar.

## <a name="registerwindowclass"></a> AFX_GLOBAL_DATA::RegisterWindowClass

Belirtilen MFC pencere sınıfını kaydeder.

```
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```

### <a name="parameters"></a>Parametreler

*lpszClassNamePrefix*<br/>
[in] Kaydedilecek pencere sınıfı adı.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa kayıtlı sınıfın tam adını; Aksi takdirde, bir [kaynak özel durum](exception-processing.md#afxthrowresourceexception).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri, virgülle ayrılmış listesidir *lpszClassNamePrefix* parametre dizesi ve geçerli uygulama örneğinin; tutamaçları onaltılı metin temsillerini ok uygulama imleci İmleç; olan bir tanımlayıcıdır IDC_ARROW ve arka plan Fırçası. MFC pencere sınıflarını kaydetme hakkında daha fazla bilgi için bkz. [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass).

### <a name="see-also"></a>Ayrıca Bkz.

[AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)<br/>
[AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="resume"></a> AFX_GLOBAL_DATA::Resume

Görsel stiller ve Windows temaları destekleyen yöntemlere erişmek iç işlev işaretçileri yeniden başlatır.

```
BOOL Resume();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE. Hata ayıklama modunda, bu yöntem, bu yöntem başarısız olup olmadığını onaylar.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, framework aldığında çağrılır [WM_POWERBROADCAST](/windows/desktop/Power/wm-powerbroadcast) ileti.

## <a name="setlayeredattrib"></a> AFX_GLOBAL_DATA::SetLayeredAttrib

Windows çağırmak için basit bir yol sağlar [SetLayeredWindowAttributes](/windows/desktop/api/winuser/nf-winuser-setlayeredwindowattributes) yöntemi.

```
BOOL SetLayeredAttrib(
    HWND hwnd,
    COLORREF crKey,
    BYTE bAlpha,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*HWND*<br/>
[in] Katmanlı penceresine işleyin.

*crKey*<br/>
[in] Saydamlık rengi anahtar [Masaüstü Pencere Yöneticisi](/windows/desktop/dwm/dwm-overview) katmanlı pencere oluşturmak için kullanır.

*bAlpha*<br/>
[in] Pencerenin katmanlı opaklığını açıklamak için kullanılan alfa değeri.

*CertOpenStore*<br/>
[in] Bitsel bir birleşimi (veya) kullanmak için hangi yöntemi parametrelerini belirten bayrak. Kullanılacak LWA_COLORKEY belirtin *crKey* parametre olarak saydam rengi. Kullanılacak LWA_ALPHA belirtin *bAlpha* katmanlı pencere opaklığını belirlemek için parametre.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="see-also"></a>Ayrıca Bkz.

[COLORREF](/windows/desktop/gdi/colorref)<br/>
[SetLayeredWindowAttributes](/windows/desktop/api/winuser/nf-winuser-setlayeredwindowattributes)

## <a name="setmenufont"></a> AFX_GLOBAL_DATA::SetMenuFont

Belirtilen mantıksal yazı tipi oluşturur.

```
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
[in] Bir yazı tipi özniteliklerini içeren bir yapıya yönelik işaretçi.

*bHorz*<br/>
[in] Metnin yatay olarak çalıştığını belirtmek için TRUE; FALSE metni dikey olarak çalışacağını belirtirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE. Hata ayıklama modunda, bu yöntem, bu yöntem başarısız olup olmadığını onaylar.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir yatay normal yazı tipi, altı çizili bir yazı tipi oluşturur ve bir kalın yazı menü öğeleri varsayılan kullanılır. Bu yöntem, isteğe bağlı olarak normal bir dikey yazı tipi oluşturur. Mantıksal yazı tipleri hakkında daha fazla bilgi için bkz: [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect).

## <a name="updatefonts"></a> AFX_GLOBAL_DATA::UpdateFonts

Framework tarafından kullanılan mantıksal yazı tiplerinin reintializes.

```
void UpdateFonts();
```

### <a name="remarks"></a>Açıklamalar

Mantıksal yazı tipleri hakkında daha fazla bilgi için bkz: `CFont::CreateFontIndirect`.

## <a name="updatesyscolors"></a> AFX_GLOBAL_DATA::UpdateSysColors

Renkler, renk derinliği, Fırçalar, kalemler ve framework tarafından kullanılan görüntüleri başlatır.

```
void UpdateSysColors();
```

## <a name="biswindows7"></a> AFX_GLOBAL_DATA::bIsWindows7

Uygulama altında Windows 7 veya üzeri yürütülmekte olan olup olmadığını gösterir.

```
BOOL bIsWindows7;
```

## <a name="clractivecaptiongradient"></a> AFX_GLOBAL_DATA::clrActiveCaptionGradient

Etkin Başlık gradyan rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.

```
COLORREF clrActiveCaptionGradient;
```

## <a name="clrinactivecaptiongradient"></a> AFX_GLOBAL_DATA::clrInactiveCaptionGradient

Etkin olmayan başlık gradyan rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.

```
COLORREF clrInactiveCaptionGradient;
```

## <a name="getitaskbarlist"></a> AFX_GLOBAL_DATA::GetITaskbarList

Oluşturur ve genel verilerde yönelik bir işaretçi depolayan `ITaskBarList` arabirimi.

```
ITaskbarList *GetITaskbarList();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `ITaskbarList` bir görev çubuğunda liste nesnesi oluşturma başarılı olursa; arabirimi Oluşturulması başarısız olursa veya geçerli işletim sistemi Windows 7'den küçükse null değerini DÖNDÜRÜR.

## <a name="getitaskbarlist3"></a> AFX_GLOBAL_DATA::GetITaskbarList3

Oluşturur ve genel verilerde yönelik bir işaretçi depolayan `ITaskBarList3` arabirimi.

```
ITaskbarList3 *GetITaskbarList3();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `ITaskbarList3` bir görev çubuğunda liste nesnesi oluşturma başarılı olursa; arabirimi Oluşturulması başarısız olursa veya geçerli işletim sistemi Windows 7'den küçükse null değerini DÖNDÜRÜR.

## <a name="getshellautohidebars"></a> AFX_GLOBAL_DATA::GetShellAutohideBars

Kabuk otomatik konumlarını çubukları Gizle belirler.

```
int GetShellAutohideBars();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tamsayı değeri otomatik konumlarını belirtin kodlanmış bayrağı ile çubukları gizleyin. Aşağıdaki değerleri birleştirmek: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.

## <a name="releasetaskbarrefs"></a> AFX_GLOBAL_DATA::ReleaseTaskBarRefs

Serbest arabirimler üzerinden alınan `GetITaskbarList` ve `GetITaskbarList3` yöntemleri.

```
void ReleaseTaskBarRefs();
```

## <a name="shellcreateitemfromparsingname"></a> AFX_GLOBAL_DATA::ShellCreateItemFromParsingName

Oluşturur ve bir kabuk öğesi nesnesi ayrıştırma adından başlatır.

```
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,
    IBindCtx *pbc,
    REFIID riid,
    void **ppv);
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
[in] Bir görünen ad için bir işaretçi.

*pbc*<br/>
Bir ayrıştırma işlemi denetleyen bir bağlama bağlamı için bir işaretçi.

*riid*<br/>
Başvuru için bir arabirim kimliği.

*ppv*<br/>
[out] Bu işlev döndürüldüğünde, istenen arabirim işaretçisi içerir *riid*. Bu genellikle olacaktır `IShellItem` veya `IShellItem2`.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa; başarılıysa S_OK döndürür Aksi takdirde bir hata değeri.

