---
title: "CPrintDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintDialog
- AFXDLGS/CPrintDialog
- AFXDLGS/CPrintDialog::CPrintDialog
- AFXDLGS/CPrintDialog::CreatePrinterDC
- AFXDLGS/CPrintDialog::DoModal
- AFXDLGS/CPrintDialog::GetCopies
- AFXDLGS/CPrintDialog::GetDefaults
- AFXDLGS/CPrintDialog::GetDeviceName
- AFXDLGS/CPrintDialog::GetDevMode
- AFXDLGS/CPrintDialog::GetDriverName
- AFXDLGS/CPrintDialog::GetFromPage
- AFXDLGS/CPrintDialog::GetPortName
- AFXDLGS/CPrintDialog::GetPrinterDC
- AFXDLGS/CPrintDialog::GetToPage
- AFXDLGS/CPrintDialog::PrintAll
- AFXDLGS/CPrintDialog::PrintCollate
- AFXDLGS/CPrintDialog::PrintRange
- AFXDLGS/CPrintDialog::PrintSelection
- AFXDLGS/CPrintDialog::m_pd
dev_langs: C++
helpviewer_keywords:
- CPrintDialog [MFC], CPrintDialog
- CPrintDialog [MFC], CreatePrinterDC
- CPrintDialog [MFC], DoModal
- CPrintDialog [MFC], GetCopies
- CPrintDialog [MFC], GetDefaults
- CPrintDialog [MFC], GetDeviceName
- CPrintDialog [MFC], GetDevMode
- CPrintDialog [MFC], GetDriverName
- CPrintDialog [MFC], GetFromPage
- CPrintDialog [MFC], GetPortName
- CPrintDialog [MFC], GetPrinterDC
- CPrintDialog [MFC], GetToPage
- CPrintDialog [MFC], PrintAll
- CPrintDialog [MFC], PrintCollate
- CPrintDialog [MFC], PrintRange
- CPrintDialog [MFC], PrintSelection
- CPrintDialog [MFC], m_pd
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 653cdc4580862288d98600603c1b45526ea38675
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cprintdialog-class"></a>CPrintDialog sınıfı
Yazdırma için Windows ortak iletişim kutusu tarafından sağlanan hizmetlerin yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPrintDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPrintDialog::CPrintDialog](#cprintdialog)|Oluşturan bir `CPrintDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Yazdır iletişim kutusu görüntülenmeden yazıcı cihaz bağlamı oluşturur.|  
|[CPrintDialog::DoModal](#domodal)|İletişim kutusu görüntüler ve bir seçim yapmasına olanak tanır.|  
|[CPrintDialog::GetCopies](#getcopies)|İstenen kopya sayısını alır.|  
|[CPrintDialog::GetDefaults](#getdefaults)|Cihaz Varsayılanları iletişim kutusu görüntülenmeden alır.|  
|[CPrintDialog::GetDeviceName](#getdevicename)|Şu anda seçili yazıcı aygıtının adını alır.|  
|[CPrintDialog::GetDevMode](#getdevmode)|Alır `DEVMODE` yapısı.|  
|[CPrintDialog::GetDriverName](#getdrivername)|Şu anda seçili yazıcı sürücüsünün adını alır.|  
|[CPrintDialog::GetFromPage](#getfrompage)|Yazdırma aralığı başlangıç sayfasının alır.|  
|[CPrintDialog::GetPortName](#getportname)|Şu anda seçili yazıcı bağlantı noktasını adını alır.|  
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Yazıcı cihaz bağlamı için bir tanıtıcı alır.|  
|[CPrintDialog::GetToPage](#gettopage)|Yazdırma aralığın bitiş sayfayı alır.|  
|[CPrintDialog::PrintAll](#printall)|Belgenin tüm sayfaları yazdırmak belirler.|  
|[CPrintDialog::PrintCollate](#printcollate)|Harmanlanmış kopya istenen belirler.|  
|[CPrintDialog::PrintRange](#printrange)|Belirtilen aralığını sayfa yazdırmak belirler.|  
|[CPrintDialog::PrintSelection](#printselection)|Yalnızca seçili öğeleri yazdırmak belirler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPrintDialog::m_pd](#m_pd)|Özelleştirmek için kullanılan bir yapı bir `CPrintDialog` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ortak yazdırma iletişim kutuları yazdırma ve baskı Kurulum iletişim kutuları Windows standartları ile tutarlı bir şekilde uygulama için kolay bir yol sağlar.  
  
> [!NOTE]
>  `CPrintDialogEx` Sınıfı Windows 2000 yazdırma özellik sayfası tarafından sağlanan hizmetlerin yalıtır. Daha fazla bilgi için bkz: [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) genel bakış.  
  
 `CPrintDialog`kişinin işlevselliği, tarafından kılınan [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), her ikisi de Kurulum ve sayfa yapısı yazdırmak için ortak bir iletişim kutusu ile sağlamak için tasarlanmıştır.  
  
 Yazdırma işlemi, uygulamanız için pek çok görünüşünün işlemek için çerçevesi güvenebilirsiniz. Bu durumda, framework otomatik olarak yazdırma için Windows ortak iletişim kutusu görüntüler. Ayrıca, uygulamanız için yazdırma framework tanıtıcıya sahip ancak kendi yazdırma iletişim kutusunda ortak yazdırma iletişim kutusuyla geçersiz. Yazdırma görevlerini işlemek için framework kullanma hakkında daha fazla bilgi için bkz: [yazdırma](../../mfc/printing.md).  
  
 Framework'ün katılımı olmadan yazdırma işlemek için uygulamanızın istiyorsanız kullanabileceğiniz `CPrintDialog` sağlanan Oluşturucusu ile "olduğu gibi" sınıf ya da kendi iletişim sınıfından türetilen `CPrintDialog` ve gereksinimlerinize uygun olarak bir oluşturucu yazma. Sınıfından türetilen her iki durumda da, bu iletişim kutularından standart MFC iletişim kutuları gibi davranacak `CCommonDialog`.  
  
 Kullanılacak bir `CPrintDialog` nesne, öncelikle nesnesini kullanarak oluşturmanız `CPrintDialog` Oluşturucusu. İletişim kutusu oluşturulan sonra ayarlamak veya herhangi bir değer değiştirmek [m_pd](#m_pd) yapısı, iletişim kutusunun denetimlerinin değerlerini başlatılamadı. `m_pd` Yapısıdır türü [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843). Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
 Kendi tanıtıcıları belirtmezseniz `m_pd` için **hDevMode** ve **hDevNames** üyeleri, Windows işlevi çağırma özen **GlobalFree** bu tanıtıcıları için iletişim kutusu tamamladığınızda. Framework'ün yazıcı ayarları uygulama tarafından sağlanan kullanırken `CWinApp::OnFilePrintSetup`, bu tanıtıcıları serbest gerekmez. İşleyiciler tarafından korunur `CWinApp` ve de serbest `CWinApp`'s yıkıcı. Yalnızca bu tanıtıcıları kullanırken boşaltmak gerekli olan `CPrintDialog` tek başına.  
  
 İletişim kutusu denetimleri başlatılıyor sonra çağrı `DoModal` üye işlevi iletişim kutusunu görüntülemek ve yazdırma seçeneklerini seçmek kullanıcı izin vermek için. `DoModal`Kullanıcı Tamam seçili olup olmadığını döndürür ( **IDOK**) veya iptal ( **IDCANCEL**) düğmesi.  
  
 Varsa `DoModal` döndürür **IDOK**, aşağıdakilerden birini kullanabilirsiniz `CPrintDialog`ait kullanıcı tarafından giriş bilgilerini almak için üye işlevleri.  
  
 `CPrintDialog::GetDefaults` Üye işlevi geçerli yazıcı Varsayılanları iletişim kutusu görüntülenmeden almak için yararlıdır. Bu üye işlevi, kullanıcı etkileşimi gerektirir.  
  
 Windows kullanabilirsiniz **CommDlgExtendedError** işlevi iletişim kutusunu başlatma sırasında bir hata olup olmadığını belirlemek ve hata hakkında daha fazla bilgi için. Bu işlev hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
 `CPrintDialog`üzerinde COMMDLG kullanır. Windows 3.1 ve sonraki sürümleri ile birlikte gelen DLL dosyası.  
  
 Özelleştir iletişim kutusu için bir sınıf türetin `CPrintDialog`, özel iletişim şablonu sağlayın ve genişletilmiş denetimlerden bildirim iletilerini işlemek için ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler için temel sınıf aktarılmalıdır. Kanca işlevini özelleştirme gerekli değildir.  
  
 Farklı iletişim kutusu Yazdır ya da Yazdırma ayarı olup olmamasına bağlı olarak aynı iletiyi işlemek için her iletişim kutusu için bir sınıf türetilmesi gerekir. Ayrıca Windows geçersiz kılmanız gerekir **AttachOnSetup** yazıcı ayarları düğme içinde Yazdır iletişim kutusu seçili olduğunda, yeni bir iletişim kutusu oluşturulmasını işleyen işlevi.  
  
 Kullanma hakkında daha fazla bilgi için `CPrintDialog`, bkz: [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdlgs.h  
  
##  <a name="cprintdialog"></a>CPrintDialog::CPrintDialog  
 Bir Windows yazdırma ya da Sayfa Yapısı iletişim nesnesi oluşturur.  
  
```  
CPrintDialog(
    BOOL bPrintSetupOnly,  
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `bPrintSetupOnly`  
 Standart Windows Yazdır iletişim kutusu veya Sayfa Yapısı iletişim kutusu görüntülenip görüntülenmeyeceğini belirtir. Bu parametre kümesine **TRUE** standart Windows Yazdırma Ayarı iletişim kutusunu görüntüleyin. Ayarlamak **FALSE** Windows yazdırma iletişim kutusunu görüntüleyin. Varsa `bPrintSetupOnly` olan **yanlış**, yazıcı ayarları seçenek düğmesi hala yazdırma iletişim kutusunda görüntülenir.  
  
 `dwFlags`  
 Bit düzeyinde OR işleci kullanılarak birleştirilen iletişim kutusu ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayraklar. Örneğin, **PD_ALLPAGES** bayrağını belgenin tüm sayfalar için varsayılan yazdırma aralığı ayarlar. Bkz: [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) bu bayrakları hakkında daha fazla bilgi için Windows SDK'sı yapısında.  
  
 `pParentWnd`  
 İletişim kutusunun üst veya sahibi penceresi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi yalnızca nesnesi oluşturur. Kullanım `DoModal` iletişim kutusunu görüntülemek için üye işlevi.  
  
 Oluşturucu çağırdığınızda unutmayın `bPrintSetupOnly` kümesine **FALSE**, **PD_RETURNDC** bayrağı otomatik olarak kullanılır. Çağırdıktan sonra `DoModal`, `GetDefaults`, veya `GetPrinterDC`, yazıcı DC içinde döndürülen `m_pd.hDC`. Bu DC çağrısıyla boşaltılması [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) çağıran tarafından `CPrintDialog`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>CPrintDialog::CreatePrinterDC  
 Bir yazıcı cihaz bağlamı (DC) oluşturur [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) ve [DEVNAMES](../../mfc/reference/devnames-structure.md) yapıları.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan yazıcı cihaz bağlamına işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu DC geçerli yazıcı DC olduğu varsayılır ve daha önce edindiğiniz diğer yazıcı DC'leri kullanıcı tarafından silinmesi gerekir. Bu işlev çağrılır ve Yazdır iletişim kutusu görüntülemeden elde edilen etki alanı denetleyicisi kullanılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]  
  
##  <a name="domodal"></a>CPrintDialog::DoModal  
 Windows ortak Yazdır iletişim kutusu görüntüler ve kullanıcının kopyalar, sayfa aralığı sayısı gibi çeşitli yazdırma seçeneklerini seçmesini sağlar ve kopya Harmanlanmış.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **IDOK** veya **IDCANCEL**. Varsa **IDCANCEL** olan döndürülen Windows çağrısı [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) işlevi bir hata oluşup oluşmadığını belirleyin.  
  
 **IDOK** ve **IDCANCEL** kullanıcı Tamam'ı veya iptal düğmesine seçili olmadığını gösterecek sabittir.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli yazdırma iletişim seçenekleri başlatmak istiyorsanız `m_pd` yapısı, bu çağırmadan önce yapmanız gerektiğini `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
 Çağırdıktan sonra `DoModal`, diğer üye ayarları veya kullanıcı tarafından bilgi giriş iletişim kutusuna almak için işlevleri çağırabilir.  
  
 Oluşturucu çağırdığınızda unutmayın `bPrintSetupOnly` kümesine **FALSE**, **PD_RETURNDC** bayrağı otomatik olarak kullanılır. Çağırdıktan sonra `DoModal`, `GetDefaults`, veya `GetPrinterDC`, yazıcı DC içinde döndürülen `m_pd.hDC`. Bu DC çağrısıyla boşaltılması [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) çağıran tarafından `CPrintDialog`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPrintDialog::CreatePrinterDC](#createprinterdc).  
  
##  <a name="getcopies"></a>CPrintDialog::GetCopies  
 İstenen kopya sayısını alır.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İstenen kopya sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` istenen kopya sayısı alınamadı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPrintDialog::PrintCollate](#printcollate).  
  
##  <a name="getdefaults"></a>CPrintDialog::GetDefaults  
 Varsayılan yazıcının cihaz Varsayılanları iletişim kutusu görüntülenmeden alır.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Alınan değerleri yerleştirilir `m_pd` yapısı.  
  
 Bazı durumlarda, bu işlevi çağrısı çağıracak [Oluşturucusu](#cprintdialog) için `CPrintDialog` ile `bPrintSetupOnly` kümesine **FALSE**. Bu durumda, bir yazıcı DC ve **hDevNames** ve **hDevMode** (iki tanıtıcıları bulunan `m_pd` veri üyesi) otomatik olarak ayrılır.  
  
 Varsa Oluşturucusu `CPrintDialog` ile çağrıldı `bPrintSetupOnly` kümesine **FALSE**, bu işlevi değil yalnızca döndürür **hDevNames** ve **hDevMode** (yer **m_pd.hDevNames** ve **m_pd.hDevMode**) çağırana, ancak aynı zamanda bir yazıcıya DC döndürür **m_pd.hDC**. Yazıcı DC silme ve Windows çağırmak için arayan sorumluluğundadır [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) işlevi ile işiniz bittiğinde tanıtıcıları üzerinde `CPrintDialog` nesnesi.  
  
### <a name="example"></a>Örnek  
 Bu kod parçası varsayılan yazıcının cihaz bağlamı alır ve yazıcının inç başına nokta çözümleme kullanıcıya bildirir. (Bu öznitelik yazıcının yeteneklerini genellikle DPI adlandırılır.)  
  
 [!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]  
  
##  <a name="getdevicename"></a>CPrintDialog::GetDeviceName  
 Şu anda seçili yazıcı aygıtının adını alır.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazıcının adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra [DoModal](#domodal) şu anda seçili yazıcının veya çağırdıktan sonra adı almak için [GetDefaults](#getdefaults) varsayılan yazıcının geçerli cihaz Varsayılanları alınamadı. Bir işaretçi kullanmak `CString` tarafından döndürülen nesne `GetDeviceName` değeri olarak `lpszDeviceName` çağrıda [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
### <a name="example"></a>Örnek  
 Bu kod parçası, kullanıcının varsayılan yazıcı adı ve bağlantı noktası, yazıcının kullandığı biriktirici adı ile birlikte bağlı gösterir. Kod diyor, bir ileti kutusu gösterebilir "HP LaserJet IIIP açıktır varsayılan yazıcı \\winspool kullanarak \server\share", örneğin.  
  
 [!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]  
  
##  <a name="getdevmode"></a>CPrintDialog::GetDevMode  
 Alır `DEVMODE` yapısı.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 [Aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) aygıt başlatma ve bir yazıcı sürücüsü ortamı hakkında bilgi içeren veri yapısı. Bu yapı Windows tarafından gerçekleştirilecek bellek kilidini açmanız gerekir [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows SDK'ın açıklanan işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra [DoModal](#domodal) veya [GetDefaults](#getdefaults) yazdırma aygıtı hakkında bilgi almak için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPrintDialog::PrintCollate](#printcollate).  
  
##  <a name="getdrivername"></a>CPrintDialog::GetDriverName  
 Şu anda seçili yazıcı sürücüsünün adını alır.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` sistem tarafından tanımlanan sürücü adı belirtme.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra [DoModal](#domodal) veya [GetDefaults](#getdefaults) sistem tarafından tanımlanan yazıcı aygıt sürücüsünün adını almak için. Bir işaretçi kullanmak `CString` tarafından döndürülen nesne `GetDriverName` değeri olarak `lpszDriverName` çağrıda [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPrintDialog::GetDeviceName](#getdevicename).  
  
##  <a name="getfrompage"></a>CPrintDialog::GetFromPage  
 Yazdırma aralığı başlangıç sayfasının alır.  
  
```  
int GetFromPage() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlangıç sayfa aralığında yazdırılmak üzere sayfa sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` aralığın başlangıç sayfa numarasını yazdırılması sayfaların alınamadı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="getportname"></a>CPrintDialog::GetPortName  
 Şu anda seçili yazıcı bağlantı noktasını adını alır.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda seçili yazıcı bağlantı noktası adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra [DoModal](#domodal) veya [GetDefaults](#getdefaults) şu anda seçili yazıcı bağlantı noktası adı alınamadı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPrintDialog::GetDeviceName](#getdevicename).  
  
##  <a name="getprinterdc"></a>CPrintDialog::GetPrinterDC  
 Yazıcı cihaz bağlamı için bir tanıtıcı alır.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa yazıcı cihaz bağlamı için bir tanıtıcı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bPrintSetupOnly` parametresinin `CPrintDialog` Oluşturucusu edildi **FALSE** (Yazdır iletişim kutusu görüntülenir gösteren), ardından `GetPrinterDC` yazıcı cihaz bağlamı için bir işleyici döner. Windows çağırmalısınız [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) işiniz bittiğinde cihaz bağlamı silmek için işlevi kullanıyor.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]  
  
##  <a name="gettopage"></a>CPrintDialog::GetToPage  
 Yazdırma aralığın bitiş sayfayı alır.  
  
```  
int GetToPage() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bitiş sayfa aralığında yazdırılmak üzere sayfa sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` bitiş sayfa aralığında yazdırılmak üzere sayfa sayısı alınamadı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="m_pd"></a>CPrintDialog::m_pd  
 Üyeleri iletişim nesnesinin özelliklerini depolamak yapısı.  
  
```  
PRINTDLG& m_pd;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma sonrasında bir `CPrintDialog` nesne kullanabileceğiniz `m_pd` çağırmadan önce iletişim kutusu çeşitli yönlerini ayarlamak için [DoModal](#domodal) üye işlevi. Daha fazla bilgi için `m_pd` yapısı için bkz: [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Windows SDK'sındaki.  
  
 Değiştirirseniz `m_pd` veri üyesi doğrudan herhangi varsayılan davranışı geçersiz kılar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]  
  
##  <a name="printall"></a>CPrintDialog::PrintAll  
 Belgenin tüm sayfaları yazdırmak belirler.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belgedeki tüm sayfaları yazdırılması varsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` belgedeki tüm sayfaları yazdırmak karar vermek için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="printcollate"></a>CPrintDialog::PrintCollate  
 Harmanlanmış kopya istenen belirler.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı iletişim kutusundaki collate onay kutusunu seçerse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` yazıcı belgenin yazdırılan tüm kopyalarını collate olup olmadığını belirlemek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]  
  
##  <a name="printrange"></a>CPrintDialog::PrintRange  
 Belirtilen aralığını sayfa yazdırmak belirler.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belgedeki sayfa aralığı yalnızca yazdırılması için sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` belgedeki sayfaları yalnızca bir dizi yazdırmak karar vermek için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="printselection"></a>CPrintDialog::PrintSelection  
 Yalnızca seçili öğeleri yazdırmak belirler.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili öğeleri yazdırılmak üzere, yalnızca sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` yalnızca şu anda seçili öğeleri yazdırmak karar vermek için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPrintDialog::m_pd](#m_pd).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek DIBLOOK](../../visual-cpp-samples.md)   
 [CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CPrintInfo Yapısı](../../mfc/reference/cprintinfo-structure.md)
