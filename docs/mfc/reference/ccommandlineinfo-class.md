---
title: CCommandLineInfo Sınıfı
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
ms.openlocfilehash: 0b4d5e5d253f2eb10388a69286d21e2190826eba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369457"
---
# <a name="ccommandlineinfo-class"></a>CCommandLineInfo Sınıfı

Uygulama başlatmada komut satırını ayrıştirmada yardımcı olur.

## <a name="syntax"></a>Sözdizimi

```
class CCommandLineInfo : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CCommandLineInfo::ccommandlineinfo](#ccommandlineinfo)|Varsayılan `CCommandLineInfo` bir nesne oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCommandLineInfo::ParseParam](#parseparam)|Tek tek parametreleri ayrıştmak için bu geri aramayı geçersiz kılın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|Komut satırı `/Automation` seçeneğinin bulunduğunu gösterir.|
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|Komut satırı `/Embedding` seçeneğinin bulunduğunu gösterir.|
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|Sıçrama ekranının gösterilip gösterilmediğini gösterir.|
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|İşlenecek kabuk komutunu gösterir.|
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|Kabuk komutu Yazdır'a yazdırılırsa sürücü adını gösterir; aksi takdirde boş.|
|[CCommandLineInfo::m_strFileName](#m_strfilename)|Açılacak veya yazdırılacak dosya adını gösterir; kabuk komutu Yeni veya DDE ise boş.|
|[CCommandLineInfo::m_strPortName](#m_strportname)|Kabuk komutu Yazdır'a yazdırılırsa bağlantı noktası adını gösterir; aksi takdirde boş.|
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|Kabuk komutu Yazdır Yazdır'sa yazıcı adını gösterir; aksi takdirde boş.|
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|Yeniden başlatma yöneticisi uygulamayı yeniden başlatsa, yeniden başlatma yöneticisi için benzersiz yeniden başlatma tanımlayıcısını gösterir.|

## <a name="remarks"></a>Açıklamalar

Bir MFC uygulaması genellikle uygulama nesnesinin [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) işlevinde bu sınıfın yerel bir örneğini oluşturur. Bu nesne daha sonra [CWinApp geçirilir::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), hangi tekrar tekrar `CCommandLineInfo` nesnedoldurmak için [ParseParam](#parseparam) çağırır. Nesne `CCommandLineInfo` daha sonra komut satırı bağımsız değişkenlerini ve bayraklarını işlemek için [CWinApp::ProcessShellCommand'a](../../mfc/reference/cwinapp-class.md#processshellcommand) geçirilir.

Aşağıdaki komut satırı seçeneklerini ve parametrelerini kapsüllemek için bu nesneyi kullanabilirsiniz:

|Komut satırı bağımsız değişkeni|Komut çalıştırılan|
|----------------------------|----------------------|
|*App*|Yeni dosya.|
|*uygulama* dosya adı|Dosyayı açın.|
|*uygulama* `/p` dosya adı|Dosyayı varsayılan yazıcıya yazdırın.|
|*uygulama* `/pt` dosya adı yazıcı sürücü bağlantı noktası|Dosyayı belirtilen yazıcıya yazdırın.|
|*uygulama*`/dde`|Başlatın ve DDE komutunu bekleyin.|
|*uygulama*`/Automation`|OLE otomasyon sunucusu olarak başlayın.|
|*uygulama*`/Embedding`|Katıştılı bir OLE öğesini yeniden başlatmak için başlatın.|
|*uygulama*`/Register`<br /><br /> *uygulama*`/Regserver`|Herhangi bir kayıt görevini yerine getirmesi için başvuruyu bildirir.|
|*uygulama*`/Unregister`<br /><br /> *uygulama*`/Unregserver`|Kayıt dışı görevleri yerine getirmesi için başvuruyu bildirir.|

Diğer bayrakları ve `CCommandLineInfo` parametre değerlerini işlemek için yeni bir sınıf türetin. Yeni bayrakları işlemek için [ParseParam'ı](#parseparam) geçersiz kılın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CCommandLineInfo`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="ccommandlineinfoccommandlineinfo"></a><a name="ccommandlineinfo"></a>CCommandLineInfo::ccommandlineinfo

Bu oluşturucu varsayılan `CCommandLineInfo` değerleri olan bir nesne oluşturur.

```
CCommandLineInfo();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan değer sıçrama ekranını `m_bShowSplash=TRUE`( ) göstermek ve Dosya menüsünde `m_nShellCommand`Yeni komutu yürütmektir ( **=NewFile**).

Uygulama çerçevesi, bu nesnenin veri üyelerini doldurmak için [ParseParam](#parseparam) çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

## <a name="ccommandlineinfom_brunautomated"></a><a name="m_brunautomated"></a>CCommandLineInfo::m_bRunAutomated

Bayrağın `/Automation` komut satırında bulunduğunu gösterir.

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, bu bir OLE otomasyon sunucusu olarak başlamak anlamına gelir.

## <a name="ccommandlineinfom_brunembedded"></a><a name="m_brunembedded"></a>CCommandLineInfo::m_bRunEmbedded

Bayrağın `/Embedding` komut satırında bulunduğunu gösterir.

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, bu katıştırılmış bir OLE öğeyi düzenlemek için başlatın anlamına gelir.

## <a name="ccommandlineinfom_bshowsplash"></a><a name="m_bshowsplash"></a>CCommandLineInfo::m_bShowSplash

Sıçrama ekranının görüntülenmesi gerektiğini gösterir.

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, bu uygulama için sıçrama ekranı başlangıç sırasında görüntülenmesi gerektiği anlamına gelir. [ParseParam'ın](#parseparam) varsayılan uygulaması, [m_nShellCommand](#m_nshellcommand) eşitse, `CCommandLineInfo::FileNew`bu veri üyesini TRUE olarak ayarlar.

## <a name="ccommandlineinfom_nshellcommand"></a><a name="m_nshellcommand"></a>CCommandLineInfo::m_nShellCommand

Uygulamanın bu örneği için kabuk komutunu gösterir.

```
m_nShellCommand;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesinin türü, `CCommandLineInfo` sınıfta tanımlanan aşağıdaki numaralandırılmış türüdür.

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

- `CCommandLineInfo::FileNew`Komut satırında dosya adı bulunmadığını gösterir.

- `CCommandLineInfo::FileOpen`Komut satırında bir dosya adı bulunduğunu ve komut satırında aşağıdaki bayraklardan `/p`hiçbirinin bulunmadığını gösterir: , `/pt` `/dde`.

- `CCommandLineInfo::FilePrint`Bayrağın `/p` komut satırında bulunduğunu gösterir.

- `CCommandLineInfo::FilePrintTo`Bayrağın `/pt` komut satırında bulunduğunu gösterir.

- `CCommandLineInfo::FileDDE`Bayrağın `/dde` komut satırında bulunduğunu gösterir.

- `CCommandLineInfo::AppRegister`Komut satırında `/Regserver` bayrağın `/Register` bulunduğunu ve uygulamanın kaydedilmesinin istendiğini gösterir.

- `CCommandLineInfo::AppUnregister`Veya `/Unregister` `/Unregserver` uygulamanın kaydının silindiğini gösterir.

- `CCommandLineInfo::RestartByRestartManager`Uygulamanın yeniden başlat yöneticisi tarafından yeniden başlatıldığını gösterir.

- `CCommandLineInfo::FileNothing`Başlangıçta yeni bir MDI alt penceresinin ekranını kapatır. Tasarım gereği, Uygulama Sihirbazı tarafından oluşturulan MDI uygulamaları başlangıç tarihinde yeni bir alt pencere görüntüler. Bu özelliği kapatmak için, bir `CCommandLineInfo::FileNothing` uygulama [ProcessShellCommand'ı](../../mfc/reference/cwinapp-class.md#processshellcommand)aradığında kabuk komutu olarak kullanabilir. `ProcessShellCommand`tüm `InitInstance( )` `CWinApp` türemiş sınıfların tarafından çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

## <a name="ccommandlineinfom_strdrivername"></a><a name="m_strdrivername"></a>CCommandLineInfo::m_strDriverName

Komut satırında üçüncü bayrak dışı parametrenin değerini depolar.

```
CString m_strDriverName;
```

### <a name="remarks"></a>Açıklamalar

Bu parametre genellikle Yazdırma için kabuk komutu için yazıcı sürücüsünün adıdır. [ParseParam'ın](#parseparam) varsayılan uygulaması, bu veri `/pt` üyesini yalnızca komut satırında bayrak bulunduğunda ayarlar.

## <a name="ccommandlineinfom_strfilename"></a><a name="m_strfilename"></a>CCommandLineInfo::m_strFileName

Komut satırında ilk bayrak dışı parametrenin değerini depolar.

```
CString m_strFileName;
```

### <a name="remarks"></a>Açıklamalar

Bu parametre genellikle açılacak dosyanın adıdır.

## <a name="ccommandlineinfom_strportname"></a><a name="m_strportname"></a>CCommandLineInfo::m_strPortName

Komut satırında dördüncü bayrak dışı parametrenin değerini depolar.

```
CString m_strPortName;
```

### <a name="remarks"></a>Açıklamalar

Bu parametre genellikle yazdırma için bir yazdırma komutu için yazıcı bağlantı noktasının adıdır. [ParseParam'ın](#parseparam) varsayılan uygulaması, bu veri `/pt` üyesini yalnızca komut satırında bayrak bulunduğunda ayarlar.

## <a name="ccommandlineinfom_strprintername"></a><a name="m_strprintername"></a>CCommandLineInfo::m_strPrinterName

İkinci bayrak dışı parametrenin değerini komut satırında depolar.

```
CString m_strPrinterName;
```

### <a name="remarks"></a>Açıklamalar

Bu parametre genellikle Yazdırma için yazdırma komutu için yazıcının adıdır. [ParseParam'ın](#parseparam) varsayılan uygulaması, bu veri `/pt` üyesini yalnızca komut satırında bayrak bulunduğunda ayarlar.

## <a name="ccommandlineinfom_strrestartidentifier"></a><a name="m_strrestartidentifier"></a>CCommandLineInfo::m_strRestartIdentifier

Komut satırındaki benzersiz yeniden başlatma tanımlayıcısı.

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma tanımlayıcısı, uygulamanın her örneği için benzersizdir.

Yeniden başlatma yöneticisi uygulamadan çıkar ve yeniden başlatmak için yapılandırılırsa, yeniden başlatma yöneticisi uygulamayı isteğe bağlı bir parametre olarak yeniden başlatma tanımlayıcısıyla komut satırından yürütür. Yeniden başlatma yöneticisi yeniden başlat tanımlayıcısını kullandığında, uygulama önceden açılmış belgeleri yeniden açabilir ve otomatik olarak kaydedilen dosyaları kurtarabilir.

## <a name="ccommandlineinfoparseparam"></a><a name="parseparam"></a>CCommandLineInfo::ParseParam

Çerçeve, bu işlevi komut satırından tek tek parametreleri ayrışdırmak/yorumlamak için çağırır. İkinci sürüm, yalnızca Unicode projelerinde ilk sürümden farklıdır.

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

*bBayrak*<br/>
*pszParam'ın* bir parametre mi yoksa bayrak mı olduğunu gösterir.

*Patlama*<br/>
Bunun komut satırındaki son parametre veya bayrak olup olmadığını gösterir.

### <a name="remarks"></a>Açıklamalar

[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) `ParseParam` komut satırında her parametre veya bayrak için bir kez çağırır, *pszParam*için argüman geçen . Parametrenin ilk karakteri bir ' **-**' veya **/**' ise, kaldırılır ve *bFlag* TRUE olarak ayarlanır. Son parametreyi ayrıştırırken, *bLast* TRUE olarak ayarlanır.

Bu işlevin varsayılan uygulaması aşağıdaki bayrakları `/p` `/pt`tanır: `/Automation`, `/Embedding` `/dde`, , ve , aşağıdaki tabloda gösterildiği gibi:

|Komut satırı bağımsız değişkeni|Komut çalıştırılan|
|----------------------------|----------------------|
|*App*|Yeni dosya.|
|*uygulama* dosya adı|Dosyayı açın.|
|*uygulama* `/p` dosya adı|Dosyayı varsayılan yazıcıya yazdırın.|
|*uygulama* `/pt` dosya adı yazıcı sürücü bağlantı noktası|Dosyayı belirtilen yazıcıya yazdırın.|
|*uygulama*`/dde`|Başlatın ve DDE komutunu bekleyin.|
|*uygulama*`/Automation`|OLE otomasyon sunucusu olarak başlayın.|
|*uygulama*`/Embedding`|Katıştılı bir OLE öğesini yeniden başlatmak için başlatın.|
|*uygulama*`/Register`<br /><br /> *uygulama*`/Regserver`|Herhangi bir kayıt görevini yerine getirmesi için başvuruyu bildirir.|
|*uygulama*`/Unregister`<br /><br /> *uygulama*`/Unregserver`|Kayıt dışı görevleri yerine getirmesi için başvuruyu bildirir.|

Bu bilgiler [m_bRunAutomated,](#m_brunautomated) [m_bRunEmbedded](#m_brunembedded)ve [m_nShellCommand](#m_nshellcommand)saklanır. Bayraklar bir ileri eğik **/** çizgi ' ' **-** veya tire ' ' ile işaretlenir.

Varsayılan uygulama, ilk bayrak dışı parametreyi [m_strFileName.](#m_strfilename) Bayrak söz konusu olduğunda, varsayılan uygulama ikinci, üçüncü ve dördüncü bayrak dışı parametreleri sırasıyla [m_strPrinterName,](#m_strprintername) [m_strDriverName](#m_strdrivername)ve m_strPortName koyar. [m_strPortName](#m_strportname) `/pt`

Varsayılan uygulama, [yalnızca](#m_bshowsplash) yeni bir dosya durumunda m_bShowSplash TRUE olarak da ayarlar. Yeni bir dosya söz konusu olduğunda, kullanıcı uygulamanın kendisini içeren bir eylemde bulunmuştur. Kabuk kullanarak varolan dosyaları açma da dahil olmak üzere başka bir durumda, kullanıcı eylemi doğrudan dosya içerir. Belge merkezli bir bakış açısıyla, sıçrama ekranının uygulamanın başladığını duyurmasına gerek yoktur.

Diğer bayrak ve parametre değerlerini işlemek için türemiş sınıfınızdaki bu işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)
