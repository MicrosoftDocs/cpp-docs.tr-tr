---
title: "CCommandLineInfo sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0b59297015a6fcda8eb689193b2d968d5763654d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccommandlineinfo-class"></a>CCommandLineInfo sınıfı
Uygulama başlangıç komut satırında Ayrıştırma sırasında yardımları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|Varsayılan yapıları `CCommandLineInfo` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCommandLineInfo::ParseParam](#parseparam)|Bu geri çağırma bağımsız parametreleri ayrıştırmak için geçersiz kılar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|Komut satırı gösterir `/Automation` seçeneği bulundu.|  
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|Komut satırı gösterir `/Embedding` seçeneği bulundu.|  
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|Karşılama ekranı gösterilmesi gerekip gerekmediğini gösterir.|  
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|İşlenmek üzere Kabuk komut gösterir.|  
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|Sürücü gösterir Kabuk komut yazdırma; istiyorsanız adı Aksi takdirde boş.|  
|[CCommandLineInfo::m_strFileName](#m_strfilename)|Açılacak veya yazdırılan dosya adını gösterir; Kabuk komutu yeni veya DDE ise boş.|  
|[CCommandLineInfo::m_strPortName](#m_strportname)|Bağlantı noktası belirten Kabuk komut yazdırma; istiyorsanız adı Aksi takdirde boş.|  
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|Yazıcı gösterir Kabuk komut yazdırma; istiyorsanız adı Aksi takdirde boş.|  
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|Uygulama yeniden başlatma Yöneticisi'ni yeniden, benzersiz yeniden tanımlayıcısı için yeniden başlatma Yöneticisi'ni belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 MFC uygulaması genellikle bu sınıfta yerel bir örneğini oluşturacak [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) , uygulama nesnesinin işlevi. Bu nesne sonra geçirilir [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), art arda çağıran [ParseParam](#parseparam) doldurmak için `CCommandLineInfo` nesnesi. `CCommandLineInfo` Nesne için geçirilen sonra [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) bayrakları ve komut satırı bağımsız değişkenleri işlemek için.  
  
 Aşağıdaki komut satırı seçenekleri ve parametreleri kapsüllemek için bu nesneyi kullanabilirsiniz:  
  
|Komut satırı bağımsız değişkeni|Yürütülen komut|  
|----------------------------|----------------------|  
|*Uygulama*|Yeni dosya.|  
|*Uygulama* dosya adı|Dosya Aç.|  
|*Uygulama* `/p` dosya adı|Dosyayı varsayılan yazıcıya yazdırın.|  
|*Uygulama* `/pt` filename yazıcı sürücüsü bağlantı noktası|Belirtilen yazıcı dosyaya yazdırın.|  
|*Uygulama*`/dde`|Başlatma ve DDE komutu bekler.|  
|*Uygulama*`/Automation`|OLE Otomasyon sunucusu olarak başlat.|  
|*Uygulama*`/Embedding`|Katıştırılmış OLE öğeyi düzenlemek başlatma.|  
|*Uygulama*`/Register`<br /><br /> *Uygulama*`/Regserver`|Herhangi bir kayıt görevi gerçekleştirmek için uygulama bildirir.|  
|*Uygulama*`/Unregister`<br /><br /> *Uygulama*`/Unregserver`|Herhangi bir kayıt silme görevi gerçekleştirmek için uygulama bildirir.|  
  
 Öğesinden yeni bir sınıf türetin `CCommandLineInfo` diğer bayrakları ve parametre değerlerini işlemek için. Geçersiz kılma [ParseParam](#parseparam) yeni bayrakları işlemek için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="ccommandlineinfo"></a>CCommandLineInfo::CCommandLineInfo  
 Bu oluşturucu oluşturur bir `CCommandLineInfo` varsayılan değerleri içeren nesne.  
  
```  
CCommandLineInfo();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Giriş ekranı göstermek için varsayılan değer ( `m_bShowSplash=TRUE`) ve Dosya menüsünde Yeni komutu yürütülemedi ( `m_nShellCommand` **NewFile =**).  
  
 Uygulama framework çağrıları [ParseParam](#parseparam) bu nesnenin veri üyeleri doldurmak için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]  
  
##  <a name="m_brunautomated"></a>CCommandLineInfo::m_bRunAutomated  
 Belirten `/Automation` bayrağı, komut satırında bulundu.  
  
```  
BOOL m_bRunAutomated;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, bu OLE Otomasyon sunucusu olarak başlatma anlamına gelir.  
  
##  <a name="m_brunembedded"></a>CCommandLineInfo::m_bRunEmbedded  
 Belirten `/Embedding` bayrağı, komut satırında bulundu.  
  
```  
BOOL m_bRunEmbedded;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, bu katıştırılmış OLE öğeyi düzenleme için başlatma anlamına gelir.  
  
##  <a name="m_bshowsplash"></a>CCommandLineInfo::m_bShowSplash  
 Giriş ekranı görüntüleneceğini gösterir.  
  
```  
BOOL m_bShowSplash;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, bu uygulama başlatma sırasında görüntülenmesi için bu ekranı anlamına gelir. Varsayılan uygulaması [ParseParam](#parseparam) bu veri üyesi ayarlar `TRUE` varsa [m_nShellCommand](#m_nshellcommand) eşittir `CCommandLineInfo::FileNew`.  
  
##  <a name="m_nshellcommand"></a>CCommandLineInfo::m_nShellCommand  
 Bu örnek uygulama için kabuk komut gösterir.  
  
```  
m_nShellCommand;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türü bu veri üyesi için tanımlanan aşağıdaki numaralandırılmış türü olan `CCommandLineInfo` sınıfı.  
  
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
  
- `CCommandLineInfo::FileNew`Hiçbir dosya adı komut satırında bulundu gösterir.  
  
- `CCommandLineInfo::FileOpen`Komut satırında bir dosya adı bulundu ve aşağıdaki bayraklar hiçbiri komut satırında bulundu gösterir: `/p`, `/pt`, `/dde`.  
  
- `CCommandLineInfo::FilePrint`Belirten `/p` bayrağı, komut satırında bulundu.  
  
- `CCommandLineInfo::FilePrintTo`Belirten `/pt` bayrağı, komut satırında bulundu.  
  
- `CCommandLineInfo::FileDDE`Belirten `/dde` bayrağı, komut satırında bulundu.  
  
- `CCommandLineInfo::AppRegister`Belirten `/Register` veya `/Regserver` bayrağı, komut satırında bulundu ve uygulama kaydetmeniz istenir.  
  
- `CCommandLineInfo::AppUnregister`Belirten `/Unregister` veya `/Unregserver` uygulama sorulan kaydı silinemedi.  
  
- `CCommandLineInfo::RestartByRestartManager`Uygulama yeniden başlatma Yöneticisi tarafından başlatıldı gösterir.  
  
- `CCommandLineInfo::FileNothing`Başlangıçta yeni bir MDI alt pencere görüntülemeyi devre dışı bırakır. Tasarım gereği, Uygulama Sihirbazı tarafından oluşturulan MDI uygulamaları başlatma sırasında yeni bir alt pencere görüntüler. Bu özelliği devre dışı bırakmak için bir uygulamanın kullanabileceği `CCommandLineInfo::FileNothing` çağırdığında Kabuk komut olarak [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand). `ProcessShellCommand`tarafından çağrılır `InitInstance( )` tüm `CWinApp` türetilmiş sınıfları.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]  
  
##  <a name="m_strdrivername"></a>CCommandLineInfo::m_strDriverName  
 Komut satırında üçüncü bayrağı olmayan parametresinin değerini depolar.  
  
```  
CString m_strDriverName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu parametre genellikle yazıcı sürücüsü için bir yazdırma için kabuk komut adıdır. Varsayılan uygulaması [ParseParam](#parseparam) bu veri üye yalnızca, ayarlar `/pt` bayrağı, komut satırında bulundu.  
  
##  <a name="m_strfilename"></a>CCommandLineInfo::m_strFileName  
 Komut satırında ilk bayrağı olmayan parametresinin değerini depolar.  
  
```  
CString m_strFileName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu parametre genellikle açmak için dosyaya adıdır.  
  
##  <a name="m_strportname"></a>CCommandLineInfo::m_strPortName  
 Komut satırında dördüncü bayrağı olmayan parametresinin değerini depolar.  
  
```  
CString m_strPortName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu parametre genellikle yazıcı bağlantı noktasının bir yazdırma için kabuk komut adıdır. Varsayılan uygulaması [ParseParam](#parseparam) bu veri üye yalnızca, ayarlar `/pt` bayrağı, komut satırında bulundu.  
  
##  <a name="m_strprintername"></a>CCommandLineInfo::m_strPrinterName  
 Komut satırında ikinci bayrağı olmayan parametresinin değerini depolar.  
  
```  
CString m_strPrinterName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu parametre genellikle yazıcının yazdırma için kabuk komut adıdır. Varsayılan uygulaması [ParseParam](#parseparam) bu veri üye yalnızca, ayarlar `/pt` bayrağı, komut satırında bulundu.  
  
##  <a name="m_strrestartidentifier"></a>CCommandLineInfo::m_strRestartIdentifier  
 Benzersiz tanımlayıcı komut satırında yeniden başlatın.  
  
```  
CString m_strRestartIdentifier;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma tanımlayıcısı, uygulamayı her örneği için benzersiz değil.  
  
 Yeniden başlatma Yöneticisi uygulamadan çıkar ve yeniden başlatmak için yapılandırılmışsa, yeniden başlatma Yöneticisi uygulama yeniden başlatma tanımlayıcıyla komut satırından isteğe bağlı bir parametre yürütür. Yeniden başlatma Yöneticisi'ni yeniden tanımlayıcı kullandığında, uygulama önceden açık belgeleri yeniden açın ve otomatik olarak kaydedilmiş dosyalarını kurtarın.  
  
##  <a name="parseparam"></a>CCommandLineInfo::ParseParam  
 Framework komut satırından bağımsız parametreleri ayrıştırma/yorumlamak için bu işlevi çağırır. İkinci sürümü birinciden farklı yalnızca Unicode projelerinde.  
  
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
 `pszParam`  
 Bir parametre veya bayrak.  
  
 *bFlag*  
 Gösterir olup olmadığını `pszParam` bir parametre veya bir bayrak.  
  
 `bLast`  
 Bu son parametresi komut satırında bayrağı olup olmadığını gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) çağrıları `ParseParam` kez her bir parametre veya komut satırında bayrak için bağımsız değişken geçirme `pszParam`. İlk karakter parametresinin ise bir '  **-** 'veya'  **/** ', sonra kaldırılmadan ve *bFlag* ayarlanır `TRUE`. Son parametre ayrıştırılırken `bLast` ayarlanır `TRUE`.  
  
 Bu işlev varsayılan uygulaması aşağıdaki bayraklar tanır: `/p`, `/pt`, `/dde`, `/Automation`, ve `/Embedding`aşağıdaki tabloda gösterildiği gibi:  
  
|Komut satırı bağımsız değişkeni|Yürütülen komut|  
|----------------------------|----------------------|  
|*Uygulama*|Yeni dosya.|  
|*Uygulama* dosya adı|Dosya Aç.|  
|*Uygulama* `/p` dosya adı|Dosyayı varsayılan yazıcıya yazdırın.|  
|*Uygulama* `/pt` filename yazıcı sürücüsü bağlantı noktası|Belirtilen yazıcı dosyaya yazdırın.|  
|*Uygulama*`/dde`|Başlatma ve DDE komutu bekler.|  
|*Uygulama*`/Automation`|OLE Otomasyon sunucusu olarak başlat.|  
|*Uygulama*`/Embedding`|Katıştırılmış OLE öğeyi düzenlemek başlatma.|  
|*Uygulama*`/Register`<br /><br /> *Uygulama*`/Regserver`|Herhangi bir kayıt görevi gerçekleştirmek için uygulama bildirir.|  
|*Uygulama*`/Unregister`<br /><br /> *Uygulama*`/Unregserver`|Herhangi bir kayıt silme görevi gerçekleştirmek için uygulama bildirir.|  
  
 Bu bilgiler depolanır [m_bRunAutomated](#m_brunautomated), [m_bRunEmbedded](#m_brunembedded), ve [m_nShellCommand](#m_nshellcommand). Bayrakları ya da bir eğik işaretlenir '  **/** 'veya tire'  **-** '.  
  
 Varsayılan Uygulama ilk bayrağı olmayan parametre içine yerleştirir [m_strFileName](#m_strfilename). Durumunda `/pt` bayrak varsayılan uygulama koyar ikinci üçüncü ve dördüncü bayrağı olmayan parametreleri [m_strPrinterName](#m_strprintername), [m_strDriverName](#m_strdrivername), ve [m_ strPortName](#m_strportname)sırasıyla.  
  
 Varsayılan uygulama ayrıca ayarlar [m_bShowSplash](#m_bshowsplash) için `TRUE` yalnızca söz konusu olduğunda yeni bir dosya. Yeni bir dosya söz konusu olduğunda, kullanıcının uygulamanın kendisinin içeren eylem duruma getirdi. Kabuğu'nu kullanarak var olan dosyaları açma dahil olmak üzere diğer herhangi bir durumda da, bir kullanıcı eylemi doğrudan dosyası içerir. Bir belge merkezli bakış açısına giriş ekranı başlamasını uygulama Duyurusu gerekmez.  
  
 Bu işlev diğer bayrağı ve parametre değerlerini işlemek için türetilmiş sınıf içinde geçersiz kılar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)   
 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)

