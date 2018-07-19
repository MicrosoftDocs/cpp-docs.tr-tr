---
title: Ccommandlineınfo sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
dev_langs:
- C++
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b0f48f1b845f84804a3d9f14992fa61a46de12b
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336315"
---
# <a name="ccommandlineinfo-class"></a>Ccommandlineınfo sınıfı
Uygulama başlangıcında komut satırını ayrıştırma Yardımcıları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|Varsayılan yapıları `CCommandLineInfo` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCommandLineInfo::ParseParam](#parseparam)|Bu geri çağırma bağımsız parametreleri ayrıştırmak için geçersiz kılın.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|Komut satırı belirtir `/Automation` seçeneği bulunamadı.|  
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|Komut satırı belirtir `/Embedding` seçeneği bulunamadı.|  
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|Giriş ekranı gösterilmesi gerekip gerekmediğini gösterir.|  
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|İşlenecek Kabuk komutu belirtir.|  
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|Sürücüyü belirten Kabuk komutu Yazdır; ise adı Aksi takdirde boş.|  
|[CCommandLineInfo::m_strFileName](#m_strfilename)|Açılan kopyalanamayacağı veya dosya adını gösterir. Kabuk komutu yeni veya DDE ise boş.|  
|[CCommandLineInfo::m_strPortName](#m_strportname)|Bağlantı noktasını belirten Kabuk komutu Yazdır; ise adı Aksi takdirde boş.|  
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|Yazıcı gösterir Kabuk komutu Yazdır; ise adı Aksi takdirde boş.|  
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|Uygulama yeniden başlatma Yöneticisi'ni yeniden için yeniden başlatma Yöneticisi yeniden benzersiz tanımlayıcısını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir MFC uygulaması genellikle bu sınıfta yerel bir örneğini oluşturur [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) işlevi, uygulama nesnesi. Bu nesne için geçirilir [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), sürekli olarak çağıran [ParseParam](#parseparam) doldurmak için `CCommandLineInfo` nesne. `CCommandLineInfo` Nesne için geçirilen ardından [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) bayrakları ve komut satırı bağımsız değişkenleri işlemek için.  
  
 Bu nesne, aşağıdaki komut satırı seçeneklerini ve parametrelerini yalıtılacak kullanabilirsiniz:  
  
|komut satırı bağımsız değişkeni|Yürütülen komut|  
|----------------------------|----------------------|  
|*Uygulama*|Yeni dosya.|  
|*Uygulama* dosya adı|Dosya Aç.|  
|*Uygulama* `/p` dosya adı|Varsayılan yazıcı dosyaya yazdırır.|  
|*Uygulama* `/pt` filename yazıcı sürücüsü bağlantı noktası|Dosya belirtilen yazıcıya yazdırın.|  
|*Uygulama* `/dde`|Başlatma ve await DDE komutu.|  
|*Uygulama* `/Automation`|OLE Otomasyon sunucusu Başlat.|  
|*Uygulama* `/Embedding`|Katıştırılmış OLE öğesini düzenlemek Başlat.|  
|*Uygulama* `/Register`<br /><br /> *Uygulama* `/Regserver`|Herhangi bir kayıt görevlerini gerçekleştirmek için uygulama bildirir.|  
|*Uygulama* `/Unregister`<br /><br /> *Uygulama* `/Unregserver`|Herhangi bir kayıt silme görevi gerçekleştirmek için uygulama bildirir.|  
  
 Öğesinden yeni bir sınıf türetin `CCommandLineInfo` diğer bayraklar ve parametre değerlerini işlemek için. Geçersiz kılma [ParseParam](#parseparam) yeni bayrakları işlemek için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="ccommandlineinfo"></a>  CCommandLineInfo::CCommandLineInfo  
 Bu oluşturucu bir `CCommandLineInfo` varsayılan değerleri olan nesne.  
  
```  
CCommandLineInfo();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Giriş ekranı göstermek için varsayılan değer ( `m_bShowSplash=TRUE`) ve Dosya menüsünden Yeni bir komut yürütmek için ( `m_nShellCommand` **NewFile =**).  
  
 Uygulama framework çağrıları [ParseParam](#parseparam) veri üyeleri, bu nesnenin doldurmak için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]  
  
##  <a name="m_brunautomated"></a>  CCommandLineInfo::m_bRunAutomated  
 Bildiren `/Automation` bayrağı, komut satırında bulundu.  
  
```  
BOOL m_bRunAutomated;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise bu OLE Otomasyon sunucusu başlatılması anlamına gelir.  
  
##  <a name="m_brunembedded"></a>  CCommandLineInfo::m_bRunEmbedded  
 Bildiren `/Embedding` bayrağı, komut satırında bulundu.  
  
```  
BOOL m_bRunEmbedded;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise bu katıştırılmış bir OLE öğesini düzenleme için başlatılması anlamına gelir.  
  
##  <a name="m_bshowsplash"></a>  CCommandLineInfo::m_bShowSplash  
 Karşılama ekranında görüntülenmesi gerektiğini gösterir.  
  
```  
BOOL m_bShowSplash;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise bu, bu uygulama için giriş ekranı başlatma sırasında gösterilecek anlamına gelir. Varsayılan uygulaması [ParseParam](#parseparam) bu veri üyesi gerekirse TRUE ayarlar [m_nShellCommand](#m_nshellcommand) eşittir `CCommandLineInfo::FileNew`.  
  
##  <a name="m_nshellcommand"></a>  CCommandLineInfo::m_nShellCommand  
 Uygulamanın bu örneği için kabuk komutu belirtir.  
  
```  
m_nShellCommand;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu veri üyesi için tanımlanan aşağıdaki numaralandırılmış türü türüdür `CCommandLineInfo` sınıfı.  
  
```  
enum {  
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1  
    };  
```  
  
 Bu değerleri kısa bir açıklaması için aşağıdaki listeye bakın.  
  
- `CCommandLineInfo::FileNew` Dosya adı, komut satırında bulunamadığını gösterir.  
  
- `CCommandLineInfo::FileOpen` Bir dosya adı komut satırında bulundu ve komut satırında aşağıdaki bayraklar hiçbiri bulunamadı gösterir: `/p`, `/pt`, `/dde`.  
  
- `CCommandLineInfo::FilePrint` Bildiren `/p` bayrağı, komut satırında bulundu.  
  
- `CCommandLineInfo::FilePrintTo` Bildiren `/pt` bayrağı, komut satırında bulundu.  
  
- `CCommandLineInfo::FileDDE` Bildiren `/dde` bayrağı, komut satırında bulundu.  
  
- `CCommandLineInfo::AppRegister` Bildiren `/Register` veya `/Regserver` bayrağı, komut satırında bulundu ve uygulamayı kaydetmek için istendi.  
  
- `CCommandLineInfo::AppUnregister` Bildiren `/Unregister` veya `/Unregserver` uygulama sorulan kaydını kaldırmak için.  
  
- `CCommandLineInfo::RestartByRestartManager` Uygulama yeniden başlatma Yöneticisi tarafından yeniden başlatıldı gösterir.  
  
- `CCommandLineInfo::FileNothing` Başlangıçta yeni bir MDI alt penceresinin görüntülenmesini devre dışı bırakır. Tasarım gereği, Uygulama Sihirbazı tarafından oluşturulan MDI uygulamaları başlangıçta yeni bir alt pencere görüntüler. Bu özelliği devre dışı bırakmak için bir uygulama kullanabilirsiniz `CCommandLineInfo::FileNothing` çağırdığında Kabuk komutu olarak [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand). `ProcessShellCommand` çağıran `InitInstance( )` tüm `CWinApp` türetilmiş sınıflar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]  
  
##  <a name="m_strdrivername"></a>  CCommandLineInfo::m_strDriverName  
 Komut satırında üçüncü bayrağı olmayan parametresinin değerini depolar.  
  
```  
CString m_strDriverName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu parametre genellikle yazıcı sürücüsü yazdırma için kabuk komut adıdır. Varsayılan uygulaması [ParseParam](#parseparam) bu veri üyesi yalnızca, ayarlar `/pt` bayrağı, komut satırında bulundu.  
  
##  <a name="m_strfilename"></a>  CCommandLineInfo::m_strFileName  
 Komut satırında ilk bayrağı olmayan parametresinin değerini depolar.  
  
```  
CString m_strFileName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu parametre genellikle açmak için dosyaya adıdır.  
  
##  <a name="m_strportname"></a>  CCommandLineInfo::m_strPortName  
 Komut satırında dördüncü bayrağı olmayan parametresinin değerini depolar.  
  
```  
CString m_strPortName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu parametre genellikle yazıcı bağlantı noktasını yazdırma için kabuk komut adıdır. Varsayılan uygulaması [ParseParam](#parseparam) bu veri üyesi yalnızca, ayarlar `/pt` bayrağı, komut satırında bulundu.  
  
##  <a name="m_strprintername"></a>  CCommandLineInfo::m_strPrinterName  
 Komut satırında ikinci bayrağı olmayan parametresinin değerini depolar.  
  
```  
CString m_strPrinterName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu parametre genellikle yazıcıya yazdırma için kabuk komut adıdır. Varsayılan uygulaması [ParseParam](#parseparam) bu veri üyesi yalnızca, ayarlar `/pt` bayrağı, komut satırında bulundu.  
  
##  <a name="m_strrestartidentifier"></a>  CCommandLineInfo::m_strRestartIdentifier  
 Benzersiz tanımlayıcı komut satırında yeniden başlatın.  
  
```  
CString m_strRestartIdentifier;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma olarak uygulamanın her örneği için benzersiz tanımlayıcısıdır.  
  
 Yeniden başlatma Yöneticisi uygulama kapanır ve yeniden başlatmak için yapılandırılmışsa, yeniden başlatma Yöneticisi uygulama yeniden başlatma tanımlayıcısı ile komut satırından isteğe bağlı bir parametre olarak yürütür. Yeniden başlatma Yöneticisi'ni yeniden tanımlayıcısı kullandığında, uygulama daha önce açık belgeleri yeniden Aç ve otomatik kaydedilmiş dosyalarını kurtarın.  
  
##  <a name="parseparam"></a>  CCommandLineInfo::ParseParam  
 Framework komut satırından bağımsız parametreleri ayrıştırma/yorumlamak için bu işlevi çağırır. Dosyanın ikinci sürümü ilkinden yalnızca Unicode projelerinde.  
  
```  
virtual void ParseParam(
    const char* pszParam,  
    BOOL bFlag,  
    BOOL bLast);

 
virtual void ParseParam(
    const TCHAR* pszParam,  
    BOOL bFlag,  
    BOOL bLast);
```  
  
### <a name="parameters"></a>Parametreler  
 *pszParam*  
 Parametresi veya bayrak.  
  
 *bFlag*  
 Belirtir olup olmadığını *pszParam* bir parametre veya bir bayrak.  
  
 *Ölçekteydi*  
 Bu son parametresi veya komut satırı bayrağı olup olmadığını gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) çağrıları `ParseParam` kez her parametre veya komut satırı bayrağı için bağımsız değişken geçirme *pszParam*. İlk karakter parametresinin değeri ise bir ' **-**'veya' **/**', kaldırılmadan sonra ve *bFlag* TRUE olarak ayarlayın. Son parametre ayrıştırılırken *Ölçekteydi* TRUE olarak ayarlayın.  
  
 Bu işlev varsayılan uygulamasını aşağıdaki bayraklar tanır: `/p`, `/pt`, `/dde`, `/Automation`, ve `/Embedding`aşağıdaki tabloda gösterildiği gibi:  
  
|komut satırı bağımsız değişkeni|Yürütülen komut|  
|----------------------------|----------------------|  
|*Uygulama*|Yeni dosya.|  
|*Uygulama* dosya adı|Dosya Aç.|  
|*Uygulama* `/p` dosya adı|Varsayılan yazıcı dosyaya yazdırır.|  
|*Uygulama* `/pt` filename yazıcı sürücüsü bağlantı noktası|Dosya belirtilen yazıcıya yazdırın.|  
|*Uygulama* `/dde`|Başlatma ve await DDE komutu.|  
|*Uygulama* `/Automation`|OLE Otomasyon sunucusu Başlat.|  
|*Uygulama* `/Embedding`|Katıştırılmış OLE öğesini düzenlemek Başlat.|  
|*Uygulama* `/Register`<br /><br /> *Uygulama* `/Regserver`|Herhangi bir kayıt görevlerini gerçekleştirmek için uygulama bildirir.|  
|*Uygulama* `/Unregister`<br /><br /> *Uygulama* `/Unregserver`|Herhangi bir kayıt silme görevi gerçekleştirmek için uygulama bildirir.|  
  
 Bu bilgiler saklanır [m_bRunAutomated](#m_brunautomated), [m_bRunEmbedded](#m_brunembedded), ve [m_nShellCommand](#m_nshellcommand). Bayrakları ya da bir eğik işaretlenir ' **/**'veya kısa çizgi' **-**'.  
  
 Varsayılan Uygulama ilk bayrağı olmayan parametrede koyar [m_strFileName](#m_strfilename). Durumunda, `/pt` bayrağı, varsayılan uygulama koyar, ikinci üçüncü ve dördüncü bayrağı olmayan parametreleri [m_strPrinterName](#m_strprintername), [m_strDriverName](#m_strdrivername), ve [m_ strPortName](#m_strportname)sırasıyla.  
  
 Varsayılan uygulama ayrıca ayarlar [m_bShowSplash](#m_bshowsplash) yalnızca yeni bir dosya olması durumunda true. Yeni bir dosya söz konusu olduğunda, kullanıcı uygulamayı içeren eylem duruma getirdi. Kabuk kullanarak mevcut dosyaları açma dahil olmak üzere diğer herhangi bir durumda da, bir kullanıcı eylemi dosyayı doğrudan ilgilidir. Bir belge odaklı bakış açısına giriş ekranı başlatılıyor uygulama duyurmaktan gerekmez.  
  
 Bu işlev diğer bayrağı ve parametre değerlerini işlemek için türetilmiş sınıf içinde geçersiz kılar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)   
 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)

