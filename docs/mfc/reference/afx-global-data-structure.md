---
title: "AFX_GLOBAL_DATA yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AFX_GLOBAL_DATA
dev_langs: C++
helpviewer_keywords:
- AFX_GLOBAL_DATA structure [MFC]
- AFX_GLOBAL_DATA constructor
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 68b4a5ba27d4fcb6fcaac7c80662d778c7cbbca7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="afxglobaldata-structure"></a>AFX_GLOBAL_DATA Yapısı
`AFX_GLOBAL_DATA` Yapısı alanları ve framework yönetmek veya uygulamanızın davranışını ve görünümünü özelleştirmek için kullanılan yöntemleri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct AFX_GLOBAL_DATA  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|Oluşturan bir `AFX_GLOBAL_DATA` yapısı.|  
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::CleanUp](#cleanup)|Fırçalar, yazı tipleri ve DLL'ler gibi framework tarafından ayrılan kaynakları serbest bırakır.|  
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#d2d1makerotatematrix)|Belirtilen açıda belirtilen bir nokta çevresinde döndüğü döndürme dönüşümü oluşturur.|  
|[AFX_GLOBAL_DATA::DrawParentBackground](#drawparentbackground)|Bir denetimin üst arka planı, belirtilen bölgede çizer.|  
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#drawtextonglass)|Belirtilen metni belirtilen tema görsel stilde çizer.|  
|[AFX_GLOBAL_DATA::ExcludeTag](#excludetag)|Belirtilen XML etiket çifti belirtilen arabelleğinden kaldırır.|  
|[AFX_GLOBAL_DATA::GetColor](#getcolor)|Belirtilen kullanıcı arabirimi öğesi geçerli rengi alır.|  
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#getdirect2dfactory)|Bir işaretçi döndürür `ID2D1Factory` genel verilerde depolanan arabirimi. Arabirim başlatılmadı, oluşturulur ve varsayılan sahiptir.|  
|[AFX_GLOBAL_DATA::GetHandCursor](#gethandcursor)|Bir yandan benzer önceden tanımlanmış imleci alır ve tanıtıcısı `IDC_HAND`.|  
|[AFX_GLOBAL_DATA::GetITaskbarList](#getitaskbarlist)|Oluşturur ve genel verilerde ITaskBarList arayüzü için bir işaretçi depolar.|  
|[AFX_GLOBAL_DATA::GetITaskbarList3](#getitaskbarlist3)|Oluşturur ve genel verilerde ITaskBarList3 arayüzü için bir işaretçi depolar.|  
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#getnonclientmetrics)|Nonminimized windows nonclient alanla ilgili ölçümleri alır.|  
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#getshellautohidebars)|Kabuk otomatik konumlarını çubukları Gizle belirler.|  
|[AFX_GLOBAL_DATA::GetTextHeight](#gettextheight)|Geçerli yazı tipi metin karakter yüksekliğini alır.|  
|[AFX_GLOBAL_DATA::GetWICFactory](#getwicfactory)|Bir işaretçi döndürür `IWICImagingFactory` genel verilerde depolanan arabirimi. Arabirim başlatılmadı, oluşturulur ve varsayılan sahiptir.|  
|[AFX_GLOBAL_DATA::GetWriteFactory](#getwritefactory)|Bir işaretçi döndürür `IDWriteFactory` genel verilerde depolanan arabirimi. Arabirim başlatılmadı, oluşturulur ve varsayılan sahiptir.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|Başlatır `D2D`, `DirectWrite`, ve `WIC` üreteçleri. Ana pencerede başlatılmadan önce bu yöntemi çağırın.|  
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|Önceden tanımlanmış 32-bit simgeler desteklenip desteklenmediğini gösterir.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|Belirler olup olmadığını `D2D` başlatıldı.|  
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#isdwmcompositionenabled)|Windows çağırmak için basit bir yöntem sunar [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) yöntemi.|  
|[AFX_GLOBAL_DATA::IsHighContrastMode](#ishighcontrastmode)|Görüntüleri şu anda yüksek karşıtlıklı görüntülenip görüntülenmeyeceğini gösterir.|  
|[AFX_GLOBAL_DATA::OnSettingChange](#onsettingchange)|Masaüstünün menü animasyon ve görev autohide özellikleri geçerli durumunu algılar.|  
|[AFX_GLOBAL_DATA::RegisterWindowClass](#registerwindowclass)|Belirtilen MFC pencere sınıfı kaydeder.|  
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#releasetaskbarrefs)|GetITaskbarList ve GetITaskbarList3 yöntemleri elde arabirimleri serbest bırakır.|  
|[AFX_GLOBAL_DATA::Resume](#resume)|Windows Destek yöntemleri erişim iç işlev işaretçilerini yeniden başlatır [temalar ve görsel stiller](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx).|  
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#setlayeredattrib)|Windows çağırmak için basit bir yöntem sunar [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) yöntemi.|  
|[AFX_GLOBAL_DATA::SetMenuFont](#setmenufont)|Belirtilen mantıksal yazı tipi oluşturur.|  
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#shellcreateitemfromparsingname)|Oluşturur ve bir kabuk öğesi nesnesi ayrıştırma adından başlatır.|  
|[AFX_GLOBAL_DATA::UpdateFonts](#updatefonts)|Çerçevesi tarafından kullanılan mantıksal yazı tiplerini reintializes.|  
|[AFX_GLOBAL_DATA::UpdateSysColors](#updatesyscolors)|Renkleri, renk derinliği, Fırçalar, kalemler ve çerçevesi tarafından kullanılan görüntüleri başlatır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)|Etkinleştirir veya Microsoft Active Accessibility desteğini devre dışı bırakır. Etkin Erişilebilirlik kullanıcı arabirimi öğeleri hakkında bilgi gösterme güvenilir yöntemlerini sağlar.|  
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)|Microsoft Active Accessibility desteği etkinleştirilip etkinleştirilmeyeceğini gösterir.|  
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#iswindowslayersupportavailable)|İşletim sistemi katmanlı windows destekleyip desteklemediğini belirtir.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#bisosalphablendingsupport)|Alfa karıştırma geçerli işletim sistemini destekleyip desteklemediğini belirtir.|  
|[AFX_GLOBAL_DATA::bIsWindows7](#biswindows7)|Uygulamayı Windows 7 işletim sistemi altında ya da daha yüksek yürütülmekte olan olup olmadığını gösterir|  
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#clractivecaptiongradient)|Etkin resim yazısı gradyan rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.|  
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#clrinactivecaptiongradient)|Etkin olmayan etkin başlık gradyan rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.|  
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#m_busebuiltin32biticons)|Framework önceden tanımlanmış 32-bit renk simgeler veya daha düşük çözünürlüğü simgeler kullanıp kullanmadığını belirtir.|  
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#m_busesystemfont)|Bir sistem yazı tipi menüleri, araç çubukları ve Şerit için kullanılıp kullanılmayacağını belirtir.|  
|[AFX_GLOBAL_DATA::m_hcurHand](#m_hcurhand)|Tanıtıcı el imleci için depolar.|  
|[AFX_GLOBAL_DATA::m_hcurStretch](#m_hcurstretch)|Yatay uzatma imleci tanıtıcı depolar.|  
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#m_hcurstretchvert)|Dikey uzatma imleci tanıtıcı depolar.|  
|[AFX_GLOBAL_DATA::m_hiconTool](#m_hicontool)|Aracı simgesi tanıtıcı depolar.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#m_nautohidetoolbarmargin)|Soldaki autohide araç çubuğundan takma çubuğu sol tarafına uzaklığını belirtir.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#m_nautohidetoolbarspacing)|Autohide araç çubukları arasındaki boşluğu belirtir.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#m_ndragframethicknessdock)|Yerleşik durumu iletişim kurmak için kullanılan sürükleme çerçeve kalınlığını belirtir.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#m_ndragframethicknessfloat)|Kayan durumu iletişim kurmak için kullanılan sürükleme çerçeve kalınlığını belirtir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Verilerin çoğu `AFX_GLOBAL_DATA` yapısı, uygulama başlatıldığında başlatılır.  
  
### <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `AFX_GLOBAL_DATA`   
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxglobals.h  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


## <a name="bisosalphablendingsupport"></a>AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
İşletim sistemi Alfa karışım destekleyip desteklemediğini belirtir.  
  
  
```  
BOOL  bIsOSAlphaBlendingSupport;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `TRUE`alfa karıştırma desteklendiğini gösterir; Aksi takdirde `FALSE`.  
  

## <a name="cleanup"></a>AFX_GLOBAL_DATA::CleanUp
Fırçalar, yazı tipleri ve DLL'ler gibi framework tarafından ayrılan kaynakları serbest bırakır.  
  
  
```  
void CleanUp();
```  
## <a name="d2d1makerotatematrix"></a>AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
Belirtilen açıda belirtilen bir nokta çevresinde döndüğü döndürme dönüşümü oluşturur.  
  
  
```  
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,  
    D2D1_POINT_2F center,  
    D2D1_MATRIX_3X2_F *matrix);
```  
  
### <a name="parameters"></a>Parametreler   
 `angle`  
 Saat yönünde bir döndürme, derece cinsinden açı.  
  
 `center`  
 Hangi döndürmek hakkında noktası.  
  
 `matrix`  
 Bu yöntem döndürüldüğünde, yeni döndürme dönüşümü içerir. Bu parametre için depolama ayırmanız gerekir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aksi takdirde, S_OK başarılı olursa ya da bir hata değeri döndürür.  
  
## <a name="drawparentbackground"></a>AFX_GLOBAL_DATA::DrawParentBackground
Bir denetimin üst arka planı, belirtilen bölgede çizer.  
  
  
```  
BOOL DrawParentBackground(
    CWnd* pWnd,   
    CDC* pDC,   
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler   
 [in]`pWnd`  
 Bir denetimin penceresi işaretçi.  
  
 [in]`pDC`  
 Bir cihaz bağlamı işaretçi.  
  
 [in]`lpRect`  
 Bir dikdörtgen çizmek için alan bounds işaretçi. Varsayılan değer `NULL` şeklindedir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
## <a name="drawtextonglass"></a>AFX_GLOBAL_DATA::DrawTextOnGlass
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
 [in]`hTheme`  
 Bir pencere tema verileri işlemek veya `NULL`. Bu parametre değilse metnini çizmek için belirtilen tema çerçevesi kullanır `NULL` ve Temalar desteklenir. Aksi takdirde, framework metnini çizmek için bir tema kullanmaz.  
  
 Kullanım [OpenThemeData](http://msdn.microsoft.com/library/windows/desktop/bb759821) yöntemi oluşturmak için bir `HTHEME`.  
  
 [in]`pDC`  
 Bir cihaz bağlamı işaretçi.  
  
 [in]`iPartId`  
 İstenen metin görünümü sahip denetim bölümü. Daha fazla bilgi için tablonun bölümleri sütununa bakın [bölümler ve durumlar](http://msdn.microsoft.com/library/windows/desktop/bb773210). Bu değer 0 ise, metin varsayılan yazı tipi ya da cihaz bağlamına seçili bir yazı tipi çizilir.  
  
 [in]`iStateId`  
 İstenen metin görünümü sahip denetim durumu. Daha fazla bilgi için tablo durumları sütununa bakın [bölümler ve durumlar](http://msdn.microsoft.com/library/windows/desktop/bb773210).  
  
 [in]`strText`  
 Çizmek için metin.  
  
 [in]`rect`  
 Belirtilen metni çizilen alanı sınır.  
  
 [in]`dwFlags`  
 Bitsel bir birleşimi (veya), belirtilen metnin nasıl çizilir belirten işaretler.  
  
 Varsa `hTheme` parametresi `NULL` veya Temalar değil desteklenen ve etkinleştirilirse, `nFormat` parametresinin [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) yöntemi geçerli bayraklar açıklar. Temalar destekleniyorsa, `dwFlags` parametresinin [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) yöntemi geçerli bayraklar açıklar.  
  
 [in]`nGlowSize`  
 Belirtilen metin çizme önce arka planda çizilmiş parlama efekti boyutu. Varsayılan değer 0’dır.  
  
 [in]`clrText`  
 Belirtilen metni çizilen rengi. Varsayılan rengini varsayılan değerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Belirtilen metni çizmek için bir tema kullandıysanız; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tema uygulama görsel stilini tanımlar. Bir tema, metin çizmek için kullanılan değil `hTheme` parametresi `NULL`, veya [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) yöntemi desteklenmiyor veya [Masaüstü Pencere Yöneticisi](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) birleşim devre dışı bırakıldı .  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [Bölümler ve durumlar](http://msdn.microsoft.com/library/windows/desktop/bb773210)   
 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)   
 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317)   
 [Masaüstü Pencere Yöneticisi](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Etkinleştirme ve denetim DWM oluşturma](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="enableaccessibilitysupport"></a>AFX_GLOBAL_DATA::EnableAccessibilitySupport
Etkinleştirir veya Microsoft Active Accessibility desteğini devre dışı bırakır.  
  
  
```  
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler   
 [in]`bEnable`  
 `TRUE`Erişilebilirlik desteğini etkinleştirmek için; `FALSE` erişilebilirlik desteği devre dışı bırakmak için. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkin Erişilebilirlik şekilde programları ve Windows işletim sistemi iş yardımcı teknoloji ürünlerinin birlikte artıran bir COM tabanlı bir teknolojidir. Kullanıcı arabirimi öğeleri hakkında bilgi gösterme için güvenilir yöntemleri sağlar. Ancak, Microsoft UI Otomasyonu adlı yeni bir erişilebilirlik modeli şimdi kullanılabilir. İki teknolojiyi karşılaştırması için bkz: [UI Otomasyonu ve Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility).  
  
 Kullanım [AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport) Microsoft Active Accessibility desteği etkin olup olmadığını belirlemek amacıyla yöntemi.  
  
 
### <a name="see-also"></a>Ayrıca Bkz.  
 [UI Otomasyonu ve Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)   
 [AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)

## <a name="excludetag"></a>AFX_GLOBAL_DATA::ExcludeTag
Belirtilen XML etiket çifti belirtilen arabelleğinden kaldırır.  
  
  
```  
BOOL ExcludeTag(
    CString& strBuffer,  
    LPCTSTR lpszTag,  
    CString& strTag,  
    BOOL bIsCharsList = FALSE);
```  
  
### <a name="parameters"></a>Parametreler   
 [in]`strBuffer`  
 Metin arabelleği.  
  
 [in]`lpszTag`  
 Açma ve kapatma XML etiketleri çifti adı.  
  
 [out]`strTag`  
 Bu yöntem döndürüldüğünde, `strTag` parametresi içerir açma ve kapatma XML arasında tarafından adlı etiket metni `lpszTag` parametresi. Başında veya sonunda boşluk sonucundan kırpılır.  
  
 [in]`bIsCharsList`  
 `TRUE`çıkış karakterleri simgelerini dönüştürmek için `strTag` gerçek kaçış karakterleri; parametresine `FALSE` dönüştürme işlemi yapmayacak şekilde. Varsayılan değer `FALSE`. Daha fazla bilgi için açıklamalar bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir XML etiket çifti açma ve kapama başlangıç ve bitiş belirtilen arabellek içindeki metnin bir çalışma belirtmek etiketlerini adlı oluşur. `strBuffer` Parametresi, arabellek belirtir ve `lpszTag` parametresi XML etiket adını belirtir.  
  
 Simgeler aşağıdaki tabloda belirtilen arabelleği kaçış karakterleri kodlayın için kullanın. Belirtin `TRUE` için `bIsCharsList` sembolleri dönüştürmek için parametre `strTag` gerçek kaçış karakterleri içine parametresi. Aşağıdaki tabloda kullanır [_T()](../../c-runtime-library/data-type-mappings.md) simgenin belirtmek ve karakter dizelerini kaçınmak için makrosu.  
  
|Simgesi|Atlatma karakteri|  
|------------|----------------------|  
|_T ("\\\t")|_T("\t")|  
|_T ("\\\n")|_T("\n")|  
|_T ("\\\r")|_T("\r")|  
|_T ("\\\b")|_T("\b")|  
|_T("LT")|_T ("\<")|  
|_T("GT")|_T(">")|  
|_T("AMP")|_T("&")|  
  
## <a name="getcolor"></a>AFX_GLOBAL_DATA::GetColor
Belirtilen kullanıcı arabirimi öğesi geçerli rengi alır.  
  
  
```  
COLORREF GetColor(int nColor);
```  
  
### <a name="parameters"></a>Parametreler   
 [in]`nColor`  
 Bir kullanıcı arabirimi öğesi, renk alınır belirten bir değer. Geçerli değerler listesi için bkz: `nIndex` parametresinin [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen kullanıcı arabirimi öğesi RGB renk değeri. Daha fazla bilgi için açıklamalar bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `nColor` parametre aralık dışında dönüş değeri sıfır. Sıfır da geçerli bir RGB değer olduğundan, sistem rengi geçerli işletim sistemi tarafından desteklenip desteklenmediğini belirlemek için bu yöntemi kullanamazsınız. Bunun yerine, kullanın [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927) döndürür yöntemi `NULL` rengi desteklenmiyorsa.  
  
### <a name="see-also"></a>Ayrıca Bkz.  

 [GetSysColor işlevi](http://msdn.microsoft.com/library/windows/desktop/ms724371)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927)

## <a name="getdirect2dfactory"></a>AFX_GLOBAL_DATA::GetDirect2dFactory
 Genel verilerde depolanan ID2D1Factory arabirimine bir işaretçi döndürür. Arabirim başlatılmadı, oluşturulur ve varsayılan sahiptir.  
  
  
```  
ID2D1Factory* GetDirect2dFactory();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir fabrikası oluşturma başarılı ya da oluşturma başarısız olursa NULL ID2D1Factory arabirimi veya geçerli işletim sistemi için bir işaretçi D2D destek zorunda kalmaz.  
  
## <a name="gethandcursor"></a>AFX_GLOBAL_DATA::GetHandCursor
Bir yandan benzer önceden tanımlanmış imleci alır ve tanıtıcısı `IDC_HAND`.  
  
  
```  
HCURSOR GetHandCursor();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Elle imleci işleci.  

## <a name="getnonclientmetrics"></a>AFX_GLOBAL_DATA::GetNonClientMetrics
Nonminimized windows nonclient alanla ilgili ölçümleri alır.  
  
  
```  
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```  
  
### <a name="parameters"></a>Parametreler   
 [içinde out]`info`  
 A [NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175) nonminimized penceresi nonclient alanıyla ilişkili ölçeklenebilir ölçümleri içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
 
  
### <a name="see-also"></a>Ayrıca Bkz.   
 [NONCLIENTMETRICS yapısı](http://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="gettextheight"></a>AFX_GLOBAL_DATA::GetTextHeight
 Geçerli yazı tipi metin karakter yüksekliğini alır.  
  
  
```  
int GetTextHeight(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parametreler   
 [in]`bHorz`  
 `TRUE`metnin yatay olarak çalıştığında karakterlerin yüksekliği almak için; `FALSE` metin dikey olarak çalıştığında karakterlerin yüksekliği alınamadı. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kendi ascender kendi descender ölçülür geçerli yazı yüksekliği.  
  
## <a name="getwicfactory"></a>AFX_GLOBAL_DATA::GetWICFactory
Genel verilerde depolanan IWICImagingFactory arabirimine bir işaretçi döndürür. Arabirim başlatılmadı, oluşturulur ve varsayılan sahiptir.  
  
  
```  
IWICImagingFactory* GetWICFactory();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir fabrikası oluşturma başarılı ya da oluşturma başarısız olursa NULL IWICImagingFactory arabirimi veya geçerli işletim sistemi için bir işaretçi WIC destek zorunda kalmaz.  
  
## <a name="getwritefactory"></a>AFX_GLOBAL_DATA::GetWriteFactory
Genel verilerde depolanan IDWriteFactory arabirimine bir işaretçi döndürür. Arabirim başlatılmadı, oluşturulur ve varsayılan sahiptir.  
  
  
```  
IDWriteFactory* GetWriteFactory();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir fabrikası oluşturma başarılı ya da oluşturma başarısız olursa NULL IDWriteFactory arabirimi veya geçerli işletim sistemi için bir işaretçi DirectWrite destek zorunda kalmaz.  
 
## <a name="initd2d"></a>AFX_GLOBAL_DATA::InitD2D
D2D, DirectWrite ve WIC oluşturucuları başlatır. Ana pencerede başlatılmadan önce bu yöntemi çağırın.  
  
  
```  
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>Parametreler   
 `d2dFactoryType`  
 D2D Fabrika ve kaynakları iş parçacığı modeli oluşturur.  
  
 `writeFactoryType`  
 Yazma üretecini paylaşılan veya ayrılmış belirten bir değer  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE oluşturucuları intilalizrd, FALSE - Aksi durumda olup olmadığını döndürür  
  
## <a name="is32biticons"></a>AFX_GLOBAL_DATA::Is32BitIcons
Önceden tanımlanmış 32-bit simgeler desteklenip desteklenmediğini gösterir.  
  
  
```  
BOOL Is32BitIcons() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`önceden tanımlanmış 32-bit simgeler destekleniyorsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem `TRUE` framework 32-bit yerleşik simgeler destekliyorsa ve işletim sistemi 16 bit / piksel veya daha fazla destekliyorsa ve görüntüleri yüksek karşıtlıklı görüntülenmiyorsa.  
  
## <a name="isaccessibilitysupport"></a>AFX_GLOBAL_DATA::IsAccessibilitySupport
Microsoft Active Accessibility desteği etkinleştirilip etkinleştirilmeyeceğini gösterir.  
  
  
```  
BOOL IsAccessibilitySupport() const; 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Erişilebilirlik desteğini etkinleştirdiyseniz; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Microsoft Active Accessibility uygulamaları erişilebilir hale getirme için önceki çözüm bulunuyordu. Microsoft UI Otomasyonu Microsoft Windows için yeni erişilebilirlik modeldir ve yardımcı teknoloji ürünlerinin gereksinimlerini ele almak için tasarlanmıştır ve test araçları otomatik.   
  
 Kullanım [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport) etkinleştirme veya devre dışı Active Accessibility desteği yöntemi.  
  

### <a name="see-also"></a>Ayrıca Bkz.  
 [UI Otomasyonu ve Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)

## <a name="isd2dinitialized"></a>AFX_GLOBAL_DATA::IsD2DInitialized
 D2D başlatılmış olup olmadığını belirler  
  
  
```  
BOOL IsD2DInitialized() const; 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 D2D başlatıldı TRUE; Aksi takdirde FALSE.  
  
## <a name="isdwmcompositionenabled"></a>AFX_GLOBAL_DATA::IsDwmCompositionEnabled
Windows çağırmak için basit bir yöntem sunar [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) yöntemi.  
  
  
```  
BOOL IsDwmCompositionEnabled();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa [Masaüstü Pencere Yöneticisi](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) oluşturma, etkin Aksi takdirde `FALSE`.  
  
### <a name="see-also"></a>Ayrıca Bkz.    
 [Masaüstü Pencere Yöneticisi](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Etkinleştirme ve denetim DWM oluşturma](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="ishighcontrastmode"></a>AFX_GLOBAL_DATA::IsHighContrastMode
 Görüntüleri şu anda yüksek karşıtlıklı görüntülenip görüntülenmeyeceğini gösterir.    
```  
BOOL IsHighContrastMode() const; 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`görüntüleri şu anda siyah veya beyaz yüksek karşıtlık modunda görüntüleniyorsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Siyah yüksek karşıtlık modunda ışık karşılıklı kenarları beyaz ve arka plan siyah. Beyaz yüksek karşıtlık modunda ışık karşılıklı kenarları siyah ve arka planı beyaz.  
  
## <a name="iswindowslayersupportavailable"></a>AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
İşletim sistemi katmanlı windows destekleyip desteklemediğini belirtir.  
  
  
```  
BOOL IsWindowsLayerSupportAvailable() const; 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Katmanlı windows destekleniyorsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Katmanlı windows destekleniyorsa, *akıllı yerleştirme* katmanlı windows işaretlerinin kullanın.  
  
## <a name="m_busebuiltin32biticons"></a>AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
Framework önceden tanımlanmış 32-bit renk simgeler veya daha düşük çözünürlüğü simgeler kullanıp kullanmadığını belirtir.  
  
  
```  
BOOL  m_bUseBuiltIn32BitIcons;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `TRUE`framework 32-bit renk simgeler kullandığını belirtir; `FALSE` daha düşük çözünürlük simgeleri belirtir. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye başlatır `TRUE`.  
  
 Bu üye, uygulama başlatma sırasında ayarlamanız gerekir.  
  
## <a name="m_busesystemfont"></a>AFX_GLOBAL_DATA::m_bUseSystemFont
Bir sistem yazı tipi menüleri, araç çubukları ve Şerit için kullanılıp kullanılmayacağını belirtir.  
  
  
```  
BOOL m_bUseSystemFont;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `TRUE`bir sistem yazı tipi kullanılacağını belirtir; Aksi takdirde `FALSE`. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye başlatır `FALSE`.  
  
 Bu üye sınama kullanılacak yazı tipini belirlemek çerçevesi için tek yolu değil. `AFX_GLOBAL_DATA::UpdateFonts` Yöntemi ayrıca hangi görsel stiller menüleri, araç çubukları ve Şerit uygulanacak kullanılabilir olduğunu belirlemek için varsayılan ve alternatif yazı tipleri sınar.  
  
## <a name="m_hcurhand"></a>AFX_GLOBAL_DATA::m_hcurHand
Tanıtıcı el imleci için depolar.  
  
  
```  
HCURSOR m_hcurHand;  
```  
  
## <a name="m_hcurstretch"></a>AFX_GLOBAL_DATA::m_hcurStretch
Yatay uzatma imleci tanıtıcı depolar.  
  
  
```  
HCURSOR m_hcurStretch;  
```  

## <a name="m_hcurstretchvert"></a>AFX_GLOBAL_DATA::m_hcurStretchVert
Dikey uzatma imleci tanıtıcı depolar.  
  
  
```  
HCURSOR m_hcurStretchVert;  
```  
  
## <a name="m_hicontool"></a>AFX_GLOBAL_DATA::m_hiconTool
Aracı simgesi tanıtıcı depolar.  
  
  
```  
HICON m_hiconTool;  
```  
## <a name="m_nautohidetoolbarmargin"></a>AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
Soldaki autohide araç çubuğundan yerleştirme çubuğu sol tarafına uzaklığını belirtir.  
  
  
```  
int  m_nAutoHideToolBarMargin;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye 4 piksel başlatır.  
  
## <a name="m_nautohidetoolbarspacing"></a>AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
Autohide araç çubukları arasındaki boşluğu belirtir.  
  
  
```  
int   m_nAutoHideToolBarSpacing;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye 14 piksel başlatır.  
  
## <a name="m_ndragframethicknessdock"></a>AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Yerleşik durumu göstermek için kullanılan sürükleme çerçeve kalınlığını belirtir.  
  
  
```  
int  m_nDragFrameThicknessDock;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye 3 piksel başlatır.  
  
## <a name="m_ndragframethicknessfloat"></a>AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
Kayan durumu göstermek için kullanılan sürükleme çerçeve kalınlığını belirtir.  
  
  
```  
int  m_nDragFrameThicknessFloat;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Oluşturucu, bu üye 4 piksel başlatır.  
  
## <a name="onsettingchange"></a>AFX_GLOBAL_DATA::OnSettingChange
Masaüstünün menü animasyon ve görev autohide özellikleri geçerli durumunu algılar.  
  
  
```  
void OnSettingChange();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, kullanıcının masaüstü belirli özniteliklerini durumuna framework değişkenlerini ayarlar. Bu yöntem menü animasyon, menü yavaşça ve görev çubuğunda autohide özellikleri geçerli durumunu algılar.  
  
## <a name="registerwindowclass"></a>AFX_GLOBAL_DATA::RegisterWindowClass
Belirtilen MFC pencere sınıfı kaydeder.  
  
  
```  
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```  
  
### <a name="parameters"></a>Parametreler   
 [in]`lpszClassNamePrefix`  
 Kaydetmek için pencere sınıfı adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa kayıtlı sınıf tam adını; Aksi halde, bir [kaynak özel durumu](http://msdn.microsoft.com/library/ddd99292-819b-4fa4-8371-b1954ed5856d).  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değerini virgülle ayrılmış listesidir `lpszClassNamePrefix` parametre dizesi ve geçerli tanıtıcıları onaltılık metin temsilleridir uygulaması örneği; olan tanımlayıcısıdır IDC_ARROW; ok imleç uygulama imleci ve arka plan Fırçası. MFC pencere sınıflarını kaydetme hakkında daha fazla bilgi için bkz: [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass).  
  
### <a name="see-also"></a>Ayrıca Bkz.    
 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)   
 [AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="resume"></a>AFX_GLOBAL_DATA::Resume
 Windows temaları ve görsel stiller desteği yöntemleri erişim iç işlev işaretçilerini yeniden başlatır. 
  
  
```  
BOOL Resume();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`. Hata ayıklama modunda bu yöntem, bu yöntem başarısız olup olmadığını onaylar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem framework aldığında çağrılır [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) ileti.  
  
## <a name="setlayeredattrib"></a>AFX_GLOBAL_DATA::SetLayeredAttrib
Windows çağırmak için basit bir yöntem sunar [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) yöntemi.  
  
  
```  
BOOL SetLayeredAttrib(
    HWND hwnd,  
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parametreler   
 [in]`hwnd`  
 Katmanlı penceresine işleyin.  
  
 [in]`crKey`  
 Saydamlık rengi anahtar [Masaüstü Pencere Yöneticisi](http://msdn.microsoft.com/library/windows/desktop/aa969540) katmanlı pencere oluşturmak için kullanır.  
  
 [in]`bAlpha`  
 Katmanlı pencere geçirgenliğini tanımlamak için kullanılan alfa değeri.  
  
 [in]`dwFlags`  
 Bitsel bir birleşimi (veya) kullanmak üzere hangi yöntemi parametreleri belirtin bayrakları. Kullanılacak LWA_COLORKEY belirtin `crKey` parametre olarak saydamlık rengi. Kullanılacak LWA_ALPHA belirtin `bAlpha` katmanlı pencere geçirgenliğini belirlemek için parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.   
 
### <a name="see-also"></a>Ayrıca Bkz.   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)

## <a name="setmenufont"></a>AFX_GLOBAL_DATA::SetMenuFont
Belirtilen mantıksal yazı tipi oluşturur.  
  
  
```  
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler   
 [in]`lpLogFont`  
 Bir yazı tipi özniteliklerini içeren bir yapı işaretçi.  
  
 [in]`bHorz`  
 `TRUE`metnin yatay olarak çalıştığını belirtmek için; `FALSE` metnin dikey olarak çalıştığını belirtmek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`. Hata ayıklama modunda bu yöntem, bu yöntem başarısız olup olmadığını onaylar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yatay normal bir yazı olan altı çizili bir yazı tipi oluşturur ve bir kalın yazı tipini varsayılan menü öğeleri kullanılır. Bu yöntem, isteğe bağlı olarak normal dikey yazı tipi oluşturur. Mantıksal yazı tipleri hakkında daha fazla bilgi için bkz: [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect).  
  
## <a name="updatefonts"></a>AFX_GLOBAL_DATA::UpdateFonts
Çerçevesi tarafından kullanılan mantıksal yazı tiplerini reintializes.  
  
  
```  
void UpdateFonts();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Mantıksal yazı tipleri hakkında daha fazla bilgi için bkz: `CFont::CreateFontIndirect`.  
  
## <a name="updatesyscolors"></a>AFX_GLOBAL_DATA::UpdateSysColors
Renkleri, renk derinliği, Fırçalar, kalemler ve çerçevesi tarafından kullanılan görüntüleri başlatır.  
  
  
```  
void UpdateSysColors();
```  
  
## <a name="biswindows7"></a>AFX_GLOBAL_DATA::bIsWindows7
Uygulamanın altında Windows 7 veya üzeri yürütülmekte olan olup olmadığını gösterir.  
  
  
```  
BOOL bIsWindows7;  
```  
  
## <a name="clractivecaptiongradient"></a>AFX_GLOBAL_DATA::clrActiveCaptionGradient
Etkin resim yazısı gradyan rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.  
  
  
```  
COLORREF clrActiveCaptionGradient;  
```  
  
## <a name="clrinactivecaptiongradient"></a>AFX_GLOBAL_DATA::clrInactiveCaptionGradient
Etkin olmayan başlık gradyan rengini belirtir. Genellikle bölmeleri yerleştirme için kullanılır.  
  
  
```  
COLORREF clrInactiveCaptionGradient;  
```  
  
## <a name="getitaskbarlist"></a>AFX_GLOBAL_DATA::GetITaskbarList
Oluşturur ve genel verilerde gösteren bir işaretçi depolar `ITaskBarList` arabirimi.  
  
  
```  
ITaskbarList *GetITaskbarList();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `ITaskbarList` liste nesnesi çubuğu görevi oluşturma işlemi başarılı olursa; arabirimi `NULL` oluşturma başarısız olursa veya geçerli işletim sistemini Windows 7'den düşükse.  
  
## <a name="getitaskbarlist3"></a>AFX_GLOBAL_DATA::GetITaskbarList3
Oluşturur ve genel verilerde gösteren bir işaretçi depolar `ITaskBarList3` arabirimi.  
  
  
```  
ITaskbarList3 *GetITaskbarList3();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `ITaskbarList3` liste nesnesi çubuğu görevi oluşturma işlemi başarılı olursa; arabirimi `NULL` oluşturma başarısız olursa veya geçerli işletim sistemini Windows 7'den düşükse.  
  
## <a name="getshellautohidebars"></a>AFX_GLOBAL_DATA::GetShellAutohideBars
Kabuk otomatik konumlarını çubukları Gizle belirler.  
  
  
```  
int GetShellAutohideBars();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tamsayı değeri otomatik konumlarını belirtin kodlanmış bayraklarla çubukları gizleyin. Aşağıdaki değerleri birleştirmek: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.  
  
## <a name="releasetaskbarrefs"></a>AFX_GLOBAL_DATA::ReleaseTaskBarRefs
Serbest arabirimleri aracılığıyla elde `GetITaskbarList` ve `GetITaskbarList3` yöntemleri.  
  
  
```  
void ReleaseTaskBarRefs();
```  
  
## <a name="shellcreateitemfromparsingname"></a>AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
Oluşturur ve bir kabuk öğesi nesnesi ayrıştırma adından başlatır.  
  
  
```  
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,  
    IBindCtx *pbc,  
    REFIID riid,  
    void **ppv);
```  
  
### <a name="parameters"></a>Parametreler   
 `pszPath`  
 [in] Bir görünen ad için bir işaretçi.  
  
 `pbc`  
 Ayrıştırma işlemi denetleyen bir bağlama bağlamı için bir işaretçi.  
  
 `riid`  
 Bir arabirim kimliği başvurusu  
  
 `ppv`  
 [out] Bu işlevi döndüğünde, istenen arabirim işaretçisi içeren `riid`. Bu genellikle olacaktır `IShellItem` veya `IShellItem2`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa; S_OK döndürür Aksi takdirde bir hata değeri.  

