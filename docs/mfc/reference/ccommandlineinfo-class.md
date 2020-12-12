---
description: 'Daha fazla bilgi edinin: CCommandLineInfo sınıfı'
title: CCommandLineInfo sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 4c26ae86608725caa61ad4d1077bed01a3f40385
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227929"
---
# <a name="ccommandlineinfo-class"></a>CCommandLineInfo sınıfı

Uygulama başlangıcında komut satırını ayrıştırmaya yardımcı olur.

## <a name="syntax"></a>Syntax

```
class CCommandLineInfo : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCommandLineInfo:: CCommandLineInfo](#ccommandlineinfo)|Varsayılan bir `CCommandLineInfo` nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCommandLineInfo::P Arseparad](#parseparam)|Tek tek parametreleri ayrıştırmak için bu geri aramayı geçersiz kılın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCommandLineInfo:: m_bRunAutomated](#m_brunautomated)|Komut satırı seçeneğinin olduğunu gösterir `/Automation` .|
|[CCommandLineInfo:: m_bRunEmbedded](#m_brunembedded)|Komut satırı seçeneğinin olduğunu gösterir `/Embedding` .|
|[CCommandLineInfo:: m_bShowSplash](#m_bshowsplash)|Giriş ekranının gösterilip gösterilmeyeceğini gösterir.|
|[CCommandLineInfo:: m_nShellCommand](#m_nshellcommand)|İşlenecek kabuk komutunu gösterir.|
|[CCommandLineInfo:: m_strDriverName](#m_strdrivername)|Kabuk komutu yazdırılmazsa sürücü adını belirtir; Aksi halde boş.|
|[CCommandLineInfo:: m_strFileName](#m_strfilename)|Açılacak veya yazdırılacak dosya adını belirtir; Kabuk komutu yeni veya DDE ise boştur.|
|[CCommandLineInfo:: m_strPortName](#m_strportname)|Kabuk komutu yazdırılmazsa bağlantı noktası adını belirtir; Aksi halde boş.|
|[CCommandLineInfo:: m_strPrinterName](#m_strprintername)|Kabuk komutu yazdırılmazsa yazıcı adını belirtir; Aksi halde boş.|
|[CCommandLineInfo:: m_strRestartIdentifier](#m_strrestartidentifier)|Yeniden başlatma Yöneticisi uygulamayı yeniden başlattıktan sonra yeniden başlatma Yöneticisi için benzersiz yeniden başlatma tanımlayıcısını gösterir.|

## <a name="remarks"></a>Açıklamalar

Bir MFC uygulaması genellikle uygulama nesnesinin [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) işlevinde bu sınıfın yerel bir örneğini oluşturur. Bu nesne daha sonra [CWinApp::P arseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)öğesine geçirilir, bu da nesneyi dolduracak şekilde [parseparad](#parseparam) çağırır `CCommandLineInfo` . `CCommandLineInfo`Nesne daha sonra, komut satırı bağımsız değişkenlerini ve bayraklarını işlemek Için [CWinApp::P rocessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) 'e geçirilir.

Aşağıdaki komut satırı seçeneklerini ve parametreleri kapsüllemek için bu nesneyi kullanabilirsiniz:

|Komut satırı bağımsız değişkeni|Komut yürütüldü|
|----------------------------|----------------------|
|*uygulamanızda*|Yeni dosya.|
|*uygulama* dosya adı|Dosyayı açın.|
|*uygulama* `/p` kısaltın|Dosyayı varsayılan yazıcıda yazdır.|
|*uygulama* `/pt` dosya adı yazıcı sürücüsü bağlantı noktası|Dosyayı belirtilen yazıcıya yazdır.|
|*uygulama*`/dde`|Başlat ve await DDE komutu.|
|*uygulama*`/Automation`|Bir OLE Otomasyonu sunucusu olarak başlatın.|
|*uygulama*`/Embedding`|Katıştırılmış OLE öğesini düzenlemek için başlatın.|
|*uygulama*`/Register`<br /><br /> *uygulama*`/Regserver`|Herhangi bir kayıt görevini gerçekleştirmek için uygulamaya bildirir.|
|*uygulama*`/Unregister`<br /><br /> *uygulama*`/Unregserver`|Uygulamayı kayıt kaldırma görevlerini gerçekleştirecek şekilde bilgilendirir.|

`CCommandLineInfo`Diğer bayrakları ve parametre değerlerini işlemek için öğesinden yeni bir sınıf türet. Yeni bayrakları işlemek için [Parseparad](#parseparam) 'yi geçersiz kılın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CCommandLineInfo`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="ccommandlineinfoccommandlineinfo"></a><a name="ccommandlineinfo"></a> CCommandLineInfo:: CCommandLineInfo

Bu Oluşturucu `CCommandLineInfo` varsayılan değerlere sahip bir nesne oluşturur.

```
CCommandLineInfo();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan değer, giriş ekranını ( `m_bShowSplash=TRUE` ) göstermek ve Dosya menüsünde Yeni komutu yürütmek ( `m_nShellCommand` **= NewFile**).

Uygulama çerçevesi, bu nesnenin veri üyelerini dolduracak şekilde [Parseparad](#parseparam) çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

## <a name="ccommandlineinfom_brunautomated"></a><a name="m_brunautomated"></a> CCommandLineInfo:: m_bRunAutomated

`/Automation`Bayrağın komut satırında bulunduğunu gösterir.

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>Açıklamalar

DOĞRU ise, bu, bir OLE Otomasyonu sunucusu olarak başlar.

## <a name="ccommandlineinfom_brunembedded"></a><a name="m_brunembedded"></a> CCommandLineInfo:: m_bRunEmbedded

`/Embedding`Bayrağın komut satırında bulunduğunu gösterir.

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, bu, katıştırılmış OLE öğesinin düzenlenmesinin başlaması anlamına gelir.

## <a name="ccommandlineinfom_bshowsplash"></a><a name="m_bshowsplash"></a> CCommandLineInfo:: m_bShowSplash

Giriş ekranının gösterilmesi gerektiğini gösterir.

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>Açıklamalar

Bu değer TRUE ise, bu uygulamanın giriş ekranının başlangıç sırasında görüntülenmesi gerektiği anlamına gelir. [M_nShellCommand](#m_nshellcommand) eşitse, [parseparad](#parseparam) 'nin varsayılan UYGULANMASı bu veri üyesini true olarak ayarlar `CCommandLineInfo::FileNew` .

## <a name="ccommandlineinfom_nshellcommand"></a><a name="m_nshellcommand"></a> CCommandLineInfo:: m_nShellCommand

Uygulamanın bu örneği için kabuk komutunu gösterir.

```
m_nShellCommand;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesinin türü, sınıfında tanımlanmış olan aşağıdaki numaralandırılmış türüdür `CCommandLineInfo` .

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

Bu değerlerin kısa bir açıklaması için aşağıdaki listeye bakın.

- `CCommandLineInfo::FileNew` Komut satırında hiçbir dosya adı bulunamadığını gösterir.

- `CCommandLineInfo::FileOpen` Komut satırında bir dosya adı bulunduğunu ve komut satırında aşağıdaki bayraklardan hiçbirinin bulunamadığını gösterir: `/p` , `/pt` , `/dde` .

- `CCommandLineInfo::FilePrint``/p`Bayrağın komut satırında bulunduğunu gösterir.

- `CCommandLineInfo::FilePrintTo``/pt`Bayrağın komut satırında bulunduğunu gösterir.

- `CCommandLineInfo::FileDDE``/dde`Bayrağın komut satırında bulunduğunu gösterir.

- `CCommandLineInfo::AppRegister``/Register`Or `/Regserver` bayrağının komut satırında bulunduğunu ve uygulamanın kaydolduğu sorulur.

- `CCommandLineInfo::AppUnregister``/Unregister`Ya da `/Unregserver` uygulamanın kaydını kaldırmanız istendiğini belirtir.

- `CCommandLineInfo::RestartByRestartManager` Uygulamanın yeniden başlatma Yöneticisi tarafından yeniden başlatıldığını belirtir.

- `CCommandLineInfo::FileNothing` Başlangıçta yeni bir MDI alt penceresinin görüntülenmesini kapatır. Tasarım, uygulama Sihirbazı tarafından oluşturulan MDI uygulamaları başlangıçta yeni bir alt pencere görüntüler. Bu özelliği devre dışı bırakmak için, bir uygulama `CCommandLineInfo::FileNothing` [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)çağırdığında kabuk komutu olarak kullanılabilir. `ProcessShellCommand``InitInstance( )`tüm `CWinApp` türetilmiş sınıfların tarafından çağırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

## <a name="ccommandlineinfom_strdrivername"></a><a name="m_strdrivername"></a> CCommandLineInfo:: m_strDriverName

Komut satırındaki üçüncü bayrak olmayan parametrenin değerini depolar.

```
CString m_strDriverName;
```

### <a name="remarks"></a>Açıklamalar

Bu parametre genellikle, bir Shell 'e Yazdır komutuna ait yazıcı sürücüsünün adıdır. Varsayılan [Parseparae](#parseparam) uygulanması, bu veri üyesini yalnızca `/pt` bayrak komut satırında bulunursa ayarlar.

## <a name="ccommandlineinfom_strfilename"></a><a name="m_strfilename"></a> CCommandLineInfo:: m_strFileName

Komut satırında bayrak olmayan ilk parametresinin değerini depolar.

```
CString m_strFileName;
```

### <a name="remarks"></a>Açıklamalar

Bu parametre genellikle açılacak dosyanın adıdır.

## <a name="ccommandlineinfom_strportname"></a><a name="m_strportname"></a> CCommandLineInfo:: m_strPortName

Komut satırında dördüncü bayrak olmayan parametrenin değerini depolar.

```
CString m_strPortName;
```

### <a name="remarks"></a>Açıklamalar

Bu parametre genellikle, bir Shell 'e Yazdır komutuna ait yazıcı bağlantı noktasının adıdır. Varsayılan [Parseparae](#parseparam) uygulanması, bu veri üyesini yalnızca `/pt` bayrak komut satırında bulunursa ayarlar.

## <a name="ccommandlineinfom_strprintername"></a><a name="m_strprintername"></a> CCommandLineInfo:: m_strPrinterName

Komut satırında bayrak olmayan ikinci parametrenin değerini depolar.

```
CString m_strPrinterName;
```

### <a name="remarks"></a>Açıklamalar

Bu parametre genellikle, bir Shell 'e Yazdır komutuna ait yazıcının adıdır. Varsayılan [Parseparae](#parseparam) uygulanması, bu veri üyesini yalnızca `/pt` bayrak komut satırında bulunursa ayarlar.

## <a name="ccommandlineinfom_strrestartidentifier"></a><a name="m_strrestartidentifier"></a> CCommandLineInfo:: m_strRestartIdentifier

Komut satırındaki benzersiz yeniden başlatma tanımlayıcısı.

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma tanımlayıcısı, uygulamanın her örneği için benzersizdir.

Yeniden başlatma Yöneticisi uygulamadan çıkıp yeniden başlatılacak şekilde yapılandırıldıysa, yeniden başlatma Yöneticisi uygulamayı yeniden başlatma tanımlayıcısı ile komut satırından bir isteğe bağlı parametre olarak yürütür. Yeniden başlatma Yöneticisi yeniden başlatma kimliğini kullandığında, uygulama daha önce açık olan belgeleri yeniden açabilir ve otomatik kaydedilmiş dosyaları kurtarabilir.

## <a name="ccommandlineinfoparseparam"></a><a name="parseparam"></a> CCommandLineInfo::P Arseparad

Framework, komut satırından ayrı parametreleri ayrıştırmak/yorumlamak için bu işlevi çağırır. İkinci sürüm, yalnızca ilk Unicode projesinde farklılık gösterir.

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

*pszParam*<br/>
Parametre veya bayrak.

*bFlag*<br/>
*PszParam* 'ın bir parametre veya bayrak olup olmadığını gösterir.

*Ardı*<br/>
Bu, komut satırındaki Son parametre veya bayrak olup olmadığını gösterir.

### <a name="remarks"></a>Açıklamalar

[CWinApp::P arseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) , `ParseParam` komut satırındaki her bir parametre veya bayrak için bir kez çağırarak, bağımsız değişkenini *pszParam* öğesine geçirerek. Parametrenin ilk karakteri bir ' **-** ' veya ' **/** ' ise, kaldırılır ve *BFLAG* değeri true olarak ayarlanır. Son parametre ayrıştırılırken, bu değer *doğru olarak ayarlanır* .

Bu işlevin varsayılan uygulanması, aşağıdaki `/p` `/pt` `/dde` `/Automation` `/Embedding` tabloda gösterildiği gibi şu bayrakları tanır:,,, ve.

|Komut satırı bağımsız değişkeni|Komut yürütüldü|
|----------------------------|----------------------|
|*uygulamanızda*|Yeni dosya.|
|*uygulama* dosya adı|Dosyayı açın.|
|*uygulama* `/p` kısaltın|Dosyayı varsayılan yazıcıda yazdır.|
|*uygulama* `/pt` dosya adı yazıcı sürücüsü bağlantı noktası|Dosyayı belirtilen yazıcıya yazdır.|
|*uygulama*`/dde`|Başlat ve await DDE komutu.|
|*uygulama*`/Automation`|Bir OLE Otomasyonu sunucusu olarak başlatın.|
|*uygulama*`/Embedding`|Katıştırılmış OLE öğesini düzenlemek için başlatın.|
|*uygulama*`/Register`<br /><br /> *uygulama*`/Regserver`|Herhangi bir kayıt görevini gerçekleştirmek için uygulamaya bildirir.|
|*uygulama*`/Unregister`<br /><br /> *uygulama*`/Unregserver`|Uygulamayı kayıt kaldırma görevlerini gerçekleştirecek şekilde bilgilendirir.|

Bu bilgiler [m_bRunAutomated](#m_brunautomated), [m_bRunEmbedded](#m_brunembedded)ve [m_nShellCommand](#m_nshellcommand)depolanır. Bayraklar, eğik çizgi ' **/** ' veya tire ' ' ile işaretlenir **-** .

Varsayılan uygulama, ilk bayrak olmayan parametreyi [m_strFileName](#m_strfilename)içine koyar. Bayrak söz konusu olduğunda `/pt` , varsayılan uygulama ikinci, üçüncü ve dördüncü bayrak olmayan parametreleri sırasıyla [m_strPrinterName](#m_strprintername), [m_strDriverName](#m_strdrivername)ve [m_strPortName](#m_strportname)olarak koyar.

Varsayılan uygulama, yalnızca yeni bir dosya durumunda TRUE olarak [m_bShowSplash](#m_bshowsplash) de ayarlar. Yeni bir dosya söz konusu olduğunda, kullanıcı uygulamanın kendisini içeren eylemi gerçekleştirmiştir. Başka herhangi bir durumda, kabuğu kullanılarak mevcut dosyaları açmak da dahil olmak üzere, Kullanıcı eylemi dosyayı doğrudan içerir. Belge merkezli bir bakış halinde giriş ekranının, uygulamanın başlamasını duyurmak gerekmez.

Diğer bayrak ve parametre değerlerini işlemek için türetilmiş sınıfınıza bu işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWinApp::P arseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp::P rocessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)
