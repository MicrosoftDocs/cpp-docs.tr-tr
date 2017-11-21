---
title: "CFontDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
dev_langs: C++
helpviewer_keywords:
- CFontDialog [MFC], CFontDialog
- CFontDialog [MFC], DoModal
- CFontDialog [MFC], GetCharFormat
- CFontDialog [MFC], GetColor
- CFontDialog [MFC], GetCurrentFont
- CFontDialog [MFC], GetFaceName
- CFontDialog [MFC], GetSize
- CFontDialog [MFC], GetStyleName
- CFontDialog [MFC], GetWeight
- CFontDialog [MFC], IsBold
- CFontDialog [MFC], IsItalic
- CFontDialog [MFC], IsStrikeOut
- CFontDialog [MFC], IsUnderline
- CFontDialog [MFC], m_cf
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 854dd5e55a645f831b53a2d3c06bf5666c60db23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cfontdialog-class"></a>CFontDialog sınıfı
Bir yazı tipi seçimi iletişim kutusu uygulamanıza eklemenizi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFontDialog::CFontDialog](#cfontdialog)|Oluşturan bir `CFontDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFontDialog::DoModal](#domodal)|İletişim kutusu görüntüler ve bir seçim yapmasına olanak tanır.|  
|[CFontDialog::GetCharFormat](#getcharformat)|Karakter biçimlendirme seçili yazı tipini alır.|  
|[CFontDialog::GetColor](#getcolor)|Seçili yazı tipi rengini döndürür.|  
|[CFontDialog::GetCurrentFont](#getcurrentfont)|Şu anda seçili font özelliklerini atar bir `LOGFONT` yapısı.|  
|[CFontDialog::GetFaceName](#getfacename)|Seçili yazı tipi yüz adını döndürür.|  
|[CFontDialog::GetSize](#getsize)|Seçili yazı tipinin punto boyutunu döndürür.|  
|[CFontDialog::GetStyleName](#getstylename)|Seçili yazı tipi stili adını döndürür.|  
|[CFontDialog::GetWeight](#getweight)|Seçilen yazı tipini döndüren.|  
|[CFontDialog::IsBold](#isbold)|Yazı tipi kalın olup olmadığını belirler.|  
|[CFontDialog::IsItalic](#isitalic)|Yazı tipi italik olup olmadığını belirler.|  
|[CFontDialog::IsStrikeOut](#isstrikeout)|Yazı tipi çizili ile görüntülenip görüntülenmeyeceğini belirler.|  
|[CFontDialog::IsUnderline](#isunderline)|Yazı tipinin altı çizili olup olmadığını belirler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFontDialog::m_cf](#m_cf)|Özelleştirmek için kullanılan bir yapı bir `CFontDialog` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `CFontDialog` nesne sistemde yüklü yazı tiplerini listesini içeren bir iletişim kutusu değil. Kullanıcı belirli bir yazı tipi listeden seçebilir ve bu seçimi daha sonra geri uygulamaya bildirilir.  
  
 Oluşturmak için bir `CFontDialog` nesnesi, sağlanan bir oluşturucu kullanın veya yeni bir alt sınıf türetin ve kendi özel Oluşturucu kullanın.  
  
 Bir kez bir `CFontDialog` nesne oluşturulan, kullanabileceğiniz `m_cf` yapısı değerleri veya iletişim kutusu denetimleri durumlarını başlatılamadı. [M_cf](#m_cf) yapısıdır türü [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832). Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
 İletişim nesnenin denetimleri başlatma sonra çağrı `DoModal` üye işlevi iletişim kutusunu görüntülemek ve kullanıcının bir yazı tipi seçmesine izin vermek için. `DoModal`Kullanıcı Tamam seçili olup olmadığını döndürür ( **IDOK**) veya iptal ( **IDCANCEL**) düğmesi.  
  
 Varsa `DoModal` döndürür **IDOK**, aşağıdakilerden birini kullanabilirsiniz `CFontDialog`ait kullanıcı tarafından giriş bilgilerini almak için üye işlevleri.  
  
 Windows kullanabilirsiniz [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) işlevi iletişim kutusunu başlatma sırasında bir hata olup olmadığını belirlemek ve hata hakkında daha fazla bilgi için. Bu işlev hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
 `CFontDialog`üzerinde COMMDLG kullanır. Windows 3.1 ve sonraki sürümleri ile birlikte gelen DLL dosyası.  
  
 Özelleştir iletişim kutusu için bir sınıf türetin `CFontDialog`, özel iletişim şablonu sağlayın ve genişletilmiş denetimlerden bildirim iletilerini işlemek için bir ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler için temel sınıf geçirilmesi gerekir.  
  
 Kanca işlevini özelleştirme gerekli değildir.  
  
 Kullanma hakkında daha fazla bilgi için `CFontDialog`, bkz: [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFontDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdlgs.h  
  
##  <a name="cfontdialog"></a>CFontDialog::CFontDialog  
 Oluşturan bir `CFontDialog` nesnesi.  
  
```  
CFontDialog(
    LPLOGFONT lplfInitial = NULL,  
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,  
    CDC* pdcPrinter = NULL,  
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,  
    DWORD dwFlags = CF_SCREENFONTS,  
    CDC* pdcPrinter = NULL,  
    CWnd* pParentWnd = NULL);  
```  
  
### <a name="parameters"></a>Parametreler  
 m`plfInitial`  
 Bir işaretçi bir [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) bazı yazı tipinin özelliklerini ayarlamanıza olanak tanır veri yapısı.  
  
 `charFormat`  
 Bir işaretçi bir [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) bazı yazı tipinin özellikleri zengin bir ayarlamanıza olanak tanır veri yapısı düzenleme denetimi.  
  
 `dwFlags`  
 Bir veya daha fazla seçin yazı tipi bayraklarını belirtir. Bir veya daha fazla hazır değer bit düzeyinde OR işleci kullanılarak birleştirilebilir. Değiştirirseniz `m_cf.Flag`s yapısı üye, varsayılan davranışı korumanız için değişikliklerinizi bit düzeyinde OR işleci kullandığınızdan emin olun. Bu bayrakların her hakkında daha fazla bilgi için açıklamasına bakın [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) Windows SDK'sındaki yapısı.  
  
 pdcPrinter  
 Bir yazıcı cihaz bağlamı için bir işaretçi. Belirttiğinizde, bu parametre seçilmesi olduğu yazı tiplerini yazıcı için bir yazıcı cihaz bağlamı işaret eder.  
  
 `pParentWnd`  
 Yazı tipi iletişim kutusunun üst veya sahibi penceresi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucusu üyeleri içinde otomatik olarak doldurur Not `CHOOSEFONT` yapısı. Varsayılandan farklı bir yazı tipi iletişim kutusu istiyorsanız yalnızca bunlar değiştirmeniz gerekir.  
  
> [!NOTE]
>  Denetim desteği yok zengin düzenleme olduğunda bu işlev ilk sürümü yalnızca mevcut.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>CFontDialog::DoModal  
 Windows ortak yazı tipi iletişim kutusu görüntülemek ve bir yazı tipi seçmesine izin vermek için bu işlevini çağırın.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **IDOK** veya **IDCANCEL**. Varsa **IDCANCEL** olan döndürülen Windows çağrısı [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) işlevi bir hata oluşup oluşmadığını belirleyin.  
  
 **IDOK** ve **IDCANCEL** kullanıcı Tamam'ı veya iptal düğmesine seçili olmadığını gösterecek sabittir.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli yazı tipi iletişim kutusu denetimleri başlatmak istiyorsanız [m_cf](#m_cf) yapısı, bu çağırmadan önce yapmanız gerektiğini `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
 Varsa `DoModal` döndürür **IDOK**, diğer üye ayarları veya kullanıcı tarafından bilgi giriş iletişim kutusuna almak için işlevleri çağırabilir.  
  
### <a name="example"></a>Örnek  
  Örnekler için bkz: [CFontDialog::CFontDialog](#cfontdialog) ve [CFontDialog::GetColor](#getcolor).  
  
##  <a name="getcharformat"></a>CFontDialog::GetCharFormat  
 Karakter biçimlendirme seçili yazı tipini alır.  
  
```  
void GetCharFormat(CHARFORMAT& cf) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `cf`  
 A [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) seçili yazı tipini karakter biçimlendirme hakkında bilgi içeren yapısı.  
  
##  <a name="getcolor"></a>CFontDialog::GetColor  
 Seçili yazı tipi rengini almak için bu işlevini çağırın.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazı tipi rengi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]  
  
##  <a name="getcurrentfont"></a>CFontDialog::GetCurrentFont  
 Şu anda seçili yazı tipi özelliklerini üyelerine atamak için bu işlevi çağırmak bir [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) yapısı.  
  
```  
void GetCurrentFont(LPLOGFONT lplf);
```  
  
### <a name="parameters"></a>Parametreler  
 *lplf*  
 Bir işaretçi bir `LOGFONT` yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Diğer `CFontDialog` üye işlevleri, geçerli yazı tipi tek tek özelliklere erişmek için sağlanır.  
  
 Bu işlev çağrısı sırasında çağrılırsa [DoModal](#domodal), geçerli seçim zaman döndürür (hangi kullanıcı görür veya sahip iletişim kutusunda değiştirildi). Bu işlev çağrısı yapıldıktan sonra çağrılırsa `DoModal` (yalnızca `DoModal` döndürür **IDOK**), aslında seçili kullanıcı döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]  
  
##  <a name="getfacename"></a>CFontDialog::GetFaceName  
 Seçili yazı tipinin yüz adını almak için bu işlevini çağırın.  
  
```  
CString GetFaceName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazı tipinin yüz adını `CFontDialog` iletişim kutusu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]  
  
##  <a name="getsize"></a>CFontDialog::GetSize  
 Seçili yazı tipi boyutunu almak için bu işlevini çağırın.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Onda noktasının yazı tipinin boyutu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]  
  
##  <a name="getstylename"></a>CFontDialog::GetStyleName  
 Seçili yazı tipi stili adını almak için bu işlevini çağırın.  
  
```  
CString GetStyleName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazı tipi stili adı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]  
  
##  <a name="getweight"></a>CFontDialog::GetWeight  
 Seçili yazı tipinin kalınlığı almak için bu işlevini çağırın.  
  
```  
int GetWeight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazı tipi ağırlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir yazı tipi ağırlığı hakkında daha fazla bilgi için bkz: [CFont::CreateFont](../../mfc/reference/cfont-class.md#createfont).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]  
  
##  <a name="isbold"></a>CFontDialog::IsBold  
 Seçili yazı tipi kalın olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL IsBold() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazı tipi etkin kalın karakteristiğini varsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]  
  
##  <a name="isitalic"></a>CFontDialog::IsItalic  
 Seçilen yazı tipini italik olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL IsItalic() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazı tipi etkin italik karakteristiğini varsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]  
  
##  <a name="isstrikeout"></a>CFontDialog::IsStrikeOut  
 Seçili yazı tipi ile üstü çizili görüntüleniyorsa belirlemek için bu işlevini çağırın.  
  
```  
BOOL IsStrikeOut() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazı tipi etkin çizili karakteristiğini varsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]  
  
##  <a name="isunderline"></a>CFontDialog::IsUnderline  
 Seçili yazı tipi çizilir belirlemek için bu işlevini çağırın.  
  
```  
BOOL IsUnderline() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazı tipi etkin altı çizili karakteristiğini varsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]  
  
##  <a name="m_cf"></a>CFontDialog::m_cf  
 Üyeleri iletişim nesnesinin özelliklerini depolamak yapısı.  
  
```  
CHOOSEFONT m_cf;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma sonrasında bir `CFontDialog` nesne kullanabileceğiniz `m_cf` çağırmadan önce iletişim kutusu çeşitli yönlerini değiştirmek için `DoModal` üye işlevi. Bu yapı hakkında daha fazla bilgi için bkz: [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek HIERSVR](../../visual-cpp-samples.md)   
 [CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)



