---
title: CWinApp Sınıfı
ms.date: 07/15/2019
f1_keywords:
- CWinApp
- AFXWIN/CWinApp
- AFXWIN/CWinApp::CWinApp
- AFXWIN/CWinApp::AddDocTemplate
- AFXWIN/CWinApp::AddToRecentFileList
- AFXWIN/CWinApp::ApplicationRecoveryCallback
- AFXWIN/CWinApp::CloseAllDocuments
- AFXWIN/CWinApp::CreatePrinterDC
- AFXWIN/CWinApp::DelRegTree
- AFXWIN/CWinApp::DoMessageBox
- AFXWIN/CWinApp::DoWaitCursor
- AFXWIN/CWinApp::EnableD2DSupport
- AFXWIN/CWinApp::EnableHtmlHelp
- AFXWIN/CWinApp::EnableTaskbarInteraction
- AFXWIN/CWinApp::ExitInstance
- AFXWIN/CWinApp::GetApplicationRecoveryParameter
- AFXWIN/CWinApp::GetApplicationRecoveryPingInterval
- AFXWIN/CWinApp::GetApplicationRestartFlags
- AFXWIN/CWinApp::GetAppRegistryKey
- AFXWIN/CWinApp::GetDataRecoveryHandler
- AFXWIN/CWinApp::GetFirstDocTemplatePosition
- AFXWIN/CWinApp::GetHelpMode
- AFXWIN/CWinApp::GetNextDocTemplate
- AFXWIN/CWinApp::GetPrinterDeviceDefaults
- AFXWIN/CWinApp::GetProfileBinary
- AFXWIN/CWinApp::GetProfileInt
- AFXWIN/CWinApp::GetProfileString
- AFXWIN/CWinApp::GetSectionKey
- AFXWIN/CWinApp::HideApplication
- AFXWIN/CWinApp::HtmlHelp
- AFXWIN/CWinApp::InitInstance
- AFXWIN/CWinApp::IsTaskbarInteractionEnabled
- AFXWIN/CWinApp::LoadCursor
- AFXWIN/CWinApp::LoadIcon
- AFXWIN/CWinApp::LoadOEMCursor
- AFXWIN/CWinApp::LoadOEMIcon
- AFXWIN/CWinApp::LoadStandardCursor
- AFXWIN/CWinApp::LoadStandardIcon
- AFXWIN/CWinApp::OnDDECommand
- AFXWIN/CWinApp::OnIdle
- AFXWIN/CWinApp::OpenDocumentFile
- AFXWIN/CWinApp::ParseCommandLine
- AFXWIN/CWinApp::PreTranslateMessage
- AFXWIN/CWinApp::ProcessMessageFilter
- AFXWIN/CWinApp::ProcessShellCommand
- AFXWIN/CWinApp::ProcessWndProcException
- AFXWIN/CWinApp::Register
- AFXWIN/CWinApp::RegisterWithRestartManager
- AFXWIN/CWinApp::ReopenPreviousFilesAtRestart
- AFXWIN/CWinApp::RestartInstance
- AFXWIN/CWinApp::RestoreAutosavedFilesAtRestart
- AFXWIN/CWinApp::Run
- AFXWIN/CWinApp::RunAutomated
- AFXWIN/CWinApp::RunEmbedded
- AFXWIN/CWinApp::SaveAllModified
- AFXWIN/CWinApp::SelectPrinter
- AFXWIN/CWinApp::SetHelpMode
- AFXWIN/CWinApp::SupportsApplicationRecovery
- AFXWIN/CWinApp::SupportsAutosaveAtInterval
- AFXWIN/CWinApp::SupportsAutosaveAtRestart
- AFXWIN/CWinApp::SupportsRestartManager
- AFXWIN/CWinApp::Unregister
- AFXWIN/CWinApp::WinHelp
- AFXWIN/CWinApp::WriteProfileBinary
- AFXWIN/CWinApp::WriteProfileInt
- AFXWIN/CWinApp::WriteProfileString
- AFXWIN/CWinApp::EnableShellOpen
- AFXWIN/CWinApp::LoadStdProfileSettings
- AFXWIN/CWinApp::OnContextHelp
- AFXWIN/CWinApp::OnFileNew
- AFXWIN/CWinApp::OnFileOpen
- AFXWIN/CWinApp::OnFilePrintSetup
- AFXWIN/CWinApp::OnHelp
- AFXWIN/CWinApp::OnHelpFinder
- AFXWIN/CWinApp::OnHelpIndex
- AFXWIN/CWinApp::OnHelpUsing
- AFXWIN/CWinApp::RegisterShellFileTypes
- AFXWIN/CWinApp::SetAppID
- AFXWIN/CWinApp::SetRegistryKey
- AFXWIN/CWinApp::UnregisterShellFileTypes
- AFXWIN/CWinApp::m_bHelpMode
- AFXWIN/CWinApp::m_eHelpType
- AFXWIN/CWinApp::m_hInstance
- AFXWIN/CWinApp::m_lpCmdLine
- AFXWIN/CWinApp::m_nCmdShow
- AFXWIN/CWinApp::m_pActiveWnd
- AFXWIN/CWinApp::m_pszAppID
- AFXWIN/CWinApp::m_pszAppName
- AFXWIN/CWinApp::m_pszExeName
- AFXWIN/CWinApp::m_pszHelpFilePath
- AFXWIN/CWinApp::m_pszProfileName
- AFXWIN/CWinApp::m_pszRegistryKey
- AFXWIN/CWinApp::m_dwRestartManagerSupportFlags
- AFXWIN/CWinApp::m_nAutosaveInterval
- AFXWIN/CWinApp::m_pDataRecoveryHandler
helpviewer_keywords:
- CWinApp [MFC], CWinApp
- CWinApp [MFC], AddDocTemplate
- CWinApp [MFC], AddToRecentFileList
- CWinApp [MFC], ApplicationRecoveryCallback
- CWinApp [MFC], CloseAllDocuments
- CWinApp [MFC], CreatePrinterDC
- CWinApp [MFC], DelRegTree
- CWinApp [MFC], DoMessageBox
- CWinApp [MFC], DoWaitCursor
- CWinApp [MFC], EnableD2DSupport
- CWinApp [MFC], EnableHtmlHelp
- CWinApp [MFC], EnableTaskbarInteraction
- CWinApp [MFC], ExitInstance
- CWinApp [MFC], GetApplicationRecoveryParameter
- CWinApp [MFC], GetApplicationRecoveryPingInterval
- CWinApp [MFC], GetApplicationRestartFlags
- CWinApp [MFC], GetAppRegistryKey
- CWinApp [MFC], GetDataRecoveryHandler
- CWinApp [MFC], GetFirstDocTemplatePosition
- CWinApp [MFC], GetHelpMode
- CWinApp [MFC], GetNextDocTemplate
- CWinApp [MFC], GetPrinterDeviceDefaults
- CWinApp [MFC], GetProfileBinary
- CWinApp [MFC], GetProfileInt
- CWinApp [MFC], GetProfileString
- CWinApp [MFC], GetSectionKey
- CWinApp [MFC], HideApplication
- CWinApp [MFC], HtmlHelp
- CWinApp [MFC], InitInstance
- CWinApp [MFC], IsTaskbarInteractionEnabled
- CWinApp [MFC], LoadCursor
- CWinApp [MFC], LoadIcon
- CWinApp [MFC], LoadOEMCursor
- CWinApp [MFC], LoadOEMIcon
- CWinApp [MFC], LoadStandardCursor
- CWinApp [MFC], LoadStandardIcon
- CWinApp [MFC], OnDDECommand
- CWinApp [MFC], OnIdle
- CWinApp [MFC], OpenDocumentFile
- CWinApp [MFC], ParseCommandLine
- CWinApp [MFC], PreTranslateMessage
- CWinApp [MFC], ProcessMessageFilter
- CWinApp [MFC], ProcessShellCommand
- CWinApp [MFC], ProcessWndProcException
- CWinApp [MFC], Register
- CWinApp [MFC], RegisterWithRestartManager
- CWinApp [MFC], ReopenPreviousFilesAtRestart
- CWinApp [MFC], RestartInstance
- CWinApp [MFC], RestoreAutosavedFilesAtRestart
- CWinApp [MFC], Run
- CWinApp [MFC], RunAutomated
- CWinApp [MFC], RunEmbedded
- CWinApp [MFC], SaveAllModified
- CWinApp [MFC], SelectPrinter
- CWinApp [MFC], SetHelpMode
- CWinApp [MFC], SupportsApplicationRecovery
- CWinApp [MFC], SupportsAutosaveAtInterval
- CWinApp [MFC], SupportsAutosaveAtRestart
- CWinApp [MFC], SupportsRestartManager
- CWinApp [MFC], Unregister
- CWinApp [MFC], WinHelp
- CWinApp [MFC], WriteProfileBinary
- CWinApp [MFC], WriteProfileInt
- CWinApp [MFC], WriteProfileString
- CWinApp [MFC], EnableShellOpen
- CWinApp [MFC], LoadStdProfileSettings
- CWinApp [MFC], OnContextHelp
- CWinApp [MFC], OnFileNew
- CWinApp [MFC], OnFileOpen
- CWinApp [MFC], OnFilePrintSetup
- CWinApp [MFC], OnHelp
- CWinApp [MFC], OnHelpFinder
- CWinApp [MFC], OnHelpIndex
- CWinApp [MFC], OnHelpUsing
- CWinApp [MFC], RegisterShellFileTypes
- CWinApp [MFC], SetAppID
- CWinApp [MFC], SetRegistryKey
- CWinApp [MFC], UnregisterShellFileTypes
- CWinApp [MFC], m_bHelpMode
- CWinApp [MFC], m_eHelpType
- CWinApp [MFC], m_hInstance
- CWinApp [MFC], m_lpCmdLine
- CWinApp [MFC], m_nCmdShow
- CWinApp [MFC], m_pActiveWnd
- CWinApp [MFC], m_pszAppID
- CWinApp [MFC], m_pszAppName
- CWinApp [MFC], m_pszExeName
- CWinApp [MFC], m_pszHelpFilePath
- CWinApp [MFC], m_pszProfileName
- CWinApp [MFC], m_pszRegistryKey
- CWinApp [MFC], m_dwRestartManagerSupportFlags
- CWinApp [MFC], m_nAutosaveInterval
- CWinApp [MFC], m_pDataRecoveryHandler
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
ms.openlocfilehash: 946de5768829330f84b826a1fc9b2f6278847357
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366828"
---
# <a name="cwinapp-class"></a>CWinApp Sınıfı

Windows uygulama nesnesi türettiğiniz taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CWinApp : public CWinThread
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Cwinapp::cwinapp](#cwinapp)|Bir `CWinApp` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CwinApp::AdddocTemplate](#adddoctemplate)|Uygulamanın kullanılabilir belge şablonları listesine bir belge şablonu ekler.|
|[Cwinapp::addtorecentfilelist](#addtorecentfilelist)|En son kullanılan (MRU) dosya listesine bir dosya adı ekler.|
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|Uygulama beklenmedik bir şekilde çıktığında çerçeve tarafından çağrılır.|
|[CwinApp::CloseAllDocuments](#closealldocuments)|Tüm açık belgeleri kapatır.|
|[CwinApp:CreatePrinterDC](#createprinterdc)|Bir yazıcı aygıtı bağlamı oluşturur.|
|[CWinApp::DelRegTree](#delregtree)|Belirtilen anahtarı ve tüm alt tuşlarını siler.|
|[CWinApp::DoMessageBox](#domessagebox)|Uygulama için [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) uygular.|
|[CWinApp::DoWaitCursor](#dowaitcursor)|Bekleme imlecini açar ve kapatır.|
|[Cwinapp::EnableD2DSupport](#enabled2dsupport)|Uygulama D2D desteği sağlar. Ana pencere başharfe basılmadan önce bu yöntemi arayın.|
|[Cwinapp::EnablehtmlHelp](#enablehtmlhelp)|WinHelp yerine uygulama için HTMLHelp uygular.|
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|Görev Çubuğu etkileşimini sağlar.|
|[CwinApp::ExitInstance](#exitinstance)|Uygulamanız sona erdiğinde temizlemek için geçersiz kılın.|
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|Uygulama kurtarma yöntemi için giriş parametresini alır.|
|[Cwinapp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Yeniden başlatma yöneticisinin kurtarma geri çağırma işlevinin dönmesini beklediği süreyi verir.|
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|Yeniden başlatma yöneticisi için bayrakları döndürür.|
|[CWinApp:GetAppRegistryKey](#getappregistrykey)|"Yazılım"\RegistryKey\ProfileNameHKEY_CURRENT_USER\\anahtarını döndürür.|
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|Uygulamanın bu örneği için veri kurtarma işleyicisi alır.|
|[CwinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|İlk belge şablonunun konumunu alır.|
|[Cwinapp::GetHelpMode](#gethelpmode)|Uygulama tarafından kullanılan yardım türünü alır.|
|[Cwinapp::GetNextdocTemplate](#getnextdoctemplate)|Belge şablonunun konumunu alır. Özyinelemeli olarak kullanılabilir.|
|[CWinApp::GetPrinterDeviceVarsayılan](#getprinterdevicedefaults)|Yazıcı aygıtıvarsayılanlarını alır.|
|[Cwinapp::GetProfileBinary](#getprofilebinary)|Uygulamanın girişindeki bir girişten ikili veri alır. INI dosyası.|
|[CWinApp:GetProfileInt](#getprofileint)|Uygulamanın girişindeki bir girişten bir sonsayı alır. INI dosyası.|
|[CwinApp::GetProfileString](#getprofilestring)|Uygulamanın girişindeki bir girişten bir dize alır. INI dosyası.|
|[Cwinapp::GetSectionKey](#getsectionkey)|"Yazılım"\RegistryKey\AppName\lpszSection HKEY_CURRENT_USER\\anahtarını döndürür.|
|[CwinApp::HideApplication](#hideapplication)|Tüm belgeleri kapatmadan önce uygulamayı gizler.|
|[Cwinapp::htmlYardım](#htmlhelp)|`HTMLHelp` Windows işlevini çağırır.|
|[CWinApp::InitInstance](#initinstance)|Pencere nesneleri oluşturma gibi Windows örnek başlatma gerçekleştirmek için geçersiz kılma.|
|[CWinApp::IsTaskbarInteractionEtkin](#istaskbarinteractionenabled)|Windows 7 Görev Çubuğu etkileşiminin etkin olup olmadığını söyler.|
|[CWinApp::LoadCursor](#loadcursor)|İmleç kaynağı yükler.|
|[Cwinapp::loadicon](#loadicon)|Bir simge kaynağı yükler.|
|[CWinApp::LoadOEMCursor](#loadoemcursor)|**Windows'da OCR_** sabitlerinin belirttiği önceden tanımlanmış bir imleç yükler. H.|
|[Cwinapp::loadoemicon](#loadoemicon)|windows sabitlerinin windows'da belirttiği **OIC_** sabitlerinin önceden tanımlanmış bir simgesini yükler. H.|
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|windows sabitlerinin **IDC_** belirttiği önceden tanımlanmış bir imleç yükler. H.|
|[Cwinapp:loadstandardicon](#loadstandardicon)|windows sabitlerinde **IDI_** sabitlerinin belirttiği önceden tanımlanmış bir Windows simgesi yükler. H.|
|[Cwinapp::OnDDEKomut](#onddecommand)|Dinamik bir veri alışverişi (DDE) yürütme komutu yanıt olarak çerçeve tarafından çağrılan.|
|[Cwinapp::onidle](#onidle)|Uygulamaya özgü boşta zaman işlemesi gerçekleştirmek için geçersiz kılın.|
|[CwinApp::OpenDocumentFile](#opendocumentfile)|Bir dosyadan belge açmak için çerçeve tarafından çağrılır.|
|[CWinApp::ParseCommandLine](#parsecommandline)|Komut satırındaki tek tek parametreleri ve bayrakları parses.|
|[CWinApp::PreTranslateMessage](#pretranslatemessage)|İletileri Windows işlevlerine gönderilmeden önce filtreler [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage).|
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|Uygulamaya ulaşmadan önce belirli iletileri yakalar.|
|[CWinApp::ProcessShellCommand](#processshellcommand)|Komut satırı bağımsız değişkenlerini ve bayraklarını işler.|
|[CWinApp::ProcessWndProcException](#processwndprocexception)|Uygulamanın iletisi ve komut işleyicileri tarafından atılan tüm işlenmemiş özel durumları yakalar.|
|[CwinApp::Kayıt Ol](#register)|Özelleştirilmiş kayıt gerçekleştirir.|
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|Uygulamayı yeniden başlatma yöneticisine kaydeder.|
|[CWinApp::YenidenAçmaPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|Uygulama beklenmedik bir şekilde çıktığında yeniden başlat yöneticisinin açık olan dosyaları yeniden açıp açmadığını belirler.|
|[CWinApp::RestartInstance](#restartinstance)|Yeniden başlatma yöneticisi tarafından başlatılan bir uygulama yeniden başlatılır.|
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|Uygulamayı yeniden başlatTığında yeniden başlat yöneticisinin otomatik olarak kaydedilen dosyaları geri yükleyip geri yüklemediğini belirler.|
|[CwinApp::Çalıştır](#run)|Varsayılan ileti döngüsüçalıştırın. İleti döngüsüözelleştirmek için geçersiz kılma.|
|[CwinApp::RunAutomated](#runautomated)|**/Automation** seçeneği için uygulamanın komut satırını sınar. Kullanımdan kalktı. Bunun yerine, [CCommandLineInfo değeri kullanın::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) [ParseCommandLine](#parsecommandline)aradıktan sonra .|
|[Cwinapp::RunEmbedded](#runembedded)|**/Gömme** seçeneği için uygulamanın komut satırını sınar. Kullanımdan kalktı. Bunun yerine, [CCommandLineInfo değerini kullanın::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) [ParseCommandLine](#parsecommandline)çağırdıktan sonra .|
|[Cwinapp::SaveAllModi](#saveallmodified)|Kullanıcıdan değiştirilen tüm belgeleri kaydetmesini ister.|
|[CwinApp::Selectprinter](#selectprinter)|Yazdırma iletişim kutusu aracılığıyla kullanıcı tarafından daha önce belirtilen bir yazıcıyı seçer.|
|[Cwinapp:SetHelpMode](#sethelpmode)|Uygulama tarafından kullanılan yardım türünü ayarlar ve başlatir.|
|[CwinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|Yeniden başlatma yöneticisinin beklenmeyen bir şekilde çıkan bir uygulamayı kurtarıp kurtarmayacağını belirler.|
|[CWinApp::DesteklerAutosaveAtInterval](#supportsautosaveatinterval)|Yeniden başlatma yöneticisinin açık belgeleri düzenli aralıklarla otomatik olarak kaydedip kaydetmediğini belirler.|
|[CWinApp::DesteklerAutosaveAtRestart](#supportsautosaveatrestart)|Uygulama yeniden başlatıldığında yeniden başlatma yöneticisinin açık belgeleri otomatik olarak kaydedip kaydetmediğini belirler.|
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|Uygulamanın yeniden başlatma yöneticisini destekleyip desteklemediğini belirler.|
|[CWinApp::Kayıt Dışı](#unregister)|`CWinApp` Nesne tarafından kaydolduğu bilinen her şeyi kaydeder.|
|[Cwinapp::WinHelp](#winhelp)|`WinHelp` Windows işlevini çağırır.|
|[CwinApp::WriteProfileBinary](#writeprofilebinary)|Uygulamanın bir girişine ikili veri yazar. INI dosyası.|
|[CWinApp::WriteProfileInt](#writeprofileint)|Uygulamanın girişine bir sonda yazar. INI dosyası.|
|[CwinApp::WriteProfileString](#writeprofilestring)|Uygulamanın bir girişine bir dize yazar. INI dosyası.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CwinApp::EnableShellOpen](#enableshellopen)|Kullanıcının Windows Dosya Yöneticisi'nden veri dosyalarını açmasına olanak tanır.|
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|Yükler standart . INI dosya ayarları ve MRU dosya listesi özelliğini sağlar.|
|[Cwinapp::OncontextHelp](#oncontexthelp)|Uygulama içinde SHIFT+F1 Yardımını işler.|
|[Cwinapp::OnfileNew](#onfilenew)|ID_FILE_NEW komutunu uygular.|
|[Cwinapp::OnfileOpen](#onfileopen)|ID_FILE_OPEN komutunu uygular.|
|[Cwinapp::OnfileprintSetup](#onfileprintsetup)|ID_FILE_PRINT_SETUP komutunu uygular.|
|[Cwinapp::OnHelp](#onhelp)|Uygulama içinde F1 Yardım işler (geçerli bağlamı kullanarak).|
|[CWinApp::OnHelpFinder](#onhelpfinder)|ID_HELP_FINDER ve ID_DEFAULT_HELP komutlarını işler.|
|[Cwinapp::OnHelpIndex](#onhelpindex)|ID_HELP_INDEX komutunu işler ve varsayılan bir Yardım konusu sağlar.|
|[Cwinapp::OnHelpUsing](#onhelpusing)|ID_HELP_USING komutunu işler.|
|[Cwinapp:RegisterShellFileTypes](#registershellfiletypes)|Uygulamanın tüm belge türlerini Windows Dosya Yöneticisi'ne kaydeder.|
|[CwinApp:SetAppID](#setappid)|Uygulama için Uygulama Kullanıcı Modeli Kimliğini açıkça ayarlar. Bu yöntem, herhangi bir kullanıcı arabirimi kullanıcıya sunulmadan önce çağrılmalıdır (en iyi yer uygulama oluşturucusudur).|
|[CWinApp::SetRegistryKey](#setregistrykey)|Uygulama ayarlarının kayıt defterinde ' yerine depolanılmasına neden olur. INI dosyaları.|
|[CWinApp::Kayıt DışıShellFileTypes](#unregistershellfiletypes)|Windows Dosya Yöneticisi ile tüm uygulamanın belge türlerinin kaydını açar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CWinApp::m_bHelpMode](#m_bhelpmode)|Kullanıcının Yardım bağlamı modunda olup olmadığını gösterir (genellikle SHIFT+F1 ile çağrılır).|
|[CWinApp::m_eHelpType](#m_ehelptype)|Uygulama tarafından kullanılan yardım türünü belirtir.|
|[CWinApp:m_hInstance](#m_hinstance)|Uygulamanın geçerli örneğini tanımlar.|
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|Uygulama için komut satırını belirten null-sonlandırılan dizeyi işaret edin.|
|[CWinApp:m_nCmdShow](#m_ncmdshow)|Pencerenin başlangıçta nasıl gösterilebildiğini belirtir.|
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|OLE sunucusu yerinde etkin olduğunda kapsayıcı uygulamasının ana penceresini işaretleyin.|
|[CWinApp::m_pszAppID](#m_pszappid)|Uygulama Kullanıcı Modeli Kimliği.|
|[CWinApp:m_pszAppName](#m_pszappname)|Uygulamanın adını belirtir.|
|[CWinApp::m_pszExeName](#m_pszexename)|Uygulamanın modül adı.|
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|Uygulamanın Yardım dosyasına giden yol.|
|[CWinApp:m_pszProfileName](#m_pszprofilename)|Uygulamanın. INI dosya adı.|
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|Uygulama profili ayarlarını depolamak için tam kayıt defteri anahtarını belirlemek için kullanılır.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Yeniden başlatma yöneticisinin nasıl tepkieceğini belirleyen bayraklar.|
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|Otomatik kaydetmeler arasındaki milisaniye cinsinden sürenin uzunluğu.|
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Uygulama için veri kurtarma işleyicisini işaretçi.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama nesnesi, uygulamanızı (ve her örneğini) başlatmave uygulamayı çalıştırmak için üye işlevler sağlar.

Microsoft Foundation sınıflarını kullanan her uygulama, yalnızca `CWinApp`bir nesne yi içerebiliyor. Bu nesne, diğer C++ global nesneleri oluşturulduğunda oluşturulur ve `WinMain` Windows Microsoft Hazırlık Sınıfı Kitaplığı tarafından sağlanan işlevi aradığında zaten kullanılabilir. Türetilen `CWinApp` nesnenizi genel düzeyde bildirin.

Bir uygulama sınıfı `CWinApp`türettiğinizde, uygulamanızın ana pencere nesnesini oluşturmak için [InitInstance](#initinstance) üye işlevini geçersiz kılın.

`CWinApp` Üye işlevlere ek olarak, Microsoft Foundation Class Library nesnenize `CWinApp` ve diğer genel bilgilere erişmek için aşağıdaki genel işlevleri sağlar:

- [AfxGetApp](application-information-and-management.md#afxgetapp) `CWinApp` Nesneye bir işaretçi alır.

- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) Geçerli uygulama örneğine bir tanıtıcı elde eder.

- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) Uygulamanın kaynaklarına bir tanıtıcı elde eder.

- [AfxGetAppName](application-information-and-management.md#afxgetappname) Uygulamanın adını içeren bir dize işaretçisi alır. Alternatif olarak, `CWinApp` nesneye işaretçiniz varsa, uygulamanın adını almak için kullanın. `m_pszExeName`

Bkz. [CWinApp:](../../mfc/cwinapp-the-application-class.md) `CWinApp` Aşağıdakilerin genel görünümü de dahil olmak üzere, sınıf hakkında daha fazla bilgi için Uygulama Sınıfı:

- `CWinApp`-Uygulama Sihirbazı tarafından yazılmış türetilmiş kod.

- `CWinApp`'nin uygulamanızın yürütme sekansındaki rolü.

- `CWinApp`'ın varsayılan üye işlev uygulamaları.

- `CWinApp`'Anahtar geçersiz.

Veri `m_hPrevInstance` üyesi artık yok. Uygulamanın başka bir örneğinin çalışıp çalışmadığını belirlemek için, adlı bir mutex kullanın. Mutex'i açmak başarısız olursa, uygulamanın çalıştırılanın başka örneği yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwinthread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cwinappadddoctemplate"></a><a name="adddoctemplate"></a>CwinApp::AdddocTemplate

Uygulamanın koruduğu kullanılabilir belge şablonları listesine belge şablonu eklemek için bu üye işlevi arayın.

```
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>Parametreler

*pTemplate*<br/>
Eklenecek işaretçi. `CDocTemplate`

### <a name="remarks"></a>Açıklamalar

[RegisterShellFileTypes'ı](#registershellfiletypes)aramadan önce tüm belge şablonlarını bir uygulamaya eklemelisiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

## <a name="cwinappaddtorecentfilelist"></a><a name="addtorecentfilelist"></a>Cwinapp::addtorecentfilelist

MRU dosya listesine *lpszPathName* eklemek için bu üye işlevini arayın.

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Dosyanın yolu.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini kullanmadan önce geçerli MRU dosya listesini yüklemek için [LoadStdProfileSettings](#loadstdprofilesettings) üye işlevini aramalısınız.

Çerçeve, bir dosyayı açtığında bu üye işlevi çağırır veya yeni bir ada sahip bir dosyayı kaydetmek için Farklı Kaydet komutunu çalıştırıyor.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

## <a name="cwinappapplicationrecoverycallback"></a><a name="applicationrecoverycallback"></a>CWinApp::ApplicationRecoveryCallback

Uygulama beklenmedik bir şekilde çıktığında çerçeve tarafından çağrılır.

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>Parametreler

*lpvParam*<br/>
[içinde] İleride kullanım için ayrılmıştır.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa 0; bir hata oluşursa sıfır değildir.

### <a name="remarks"></a>Açıklamalar

Uygulamanız yeniden başlatma yöneticisini destekliyorsa, uygulamanız beklenmedik bir şekilde çıktığında çerçeve bu işlevi çağırır.

Varsayılan uygulama, `ApplicationRecoveryCallback` şu `CDataRecoveryHandler` anda açık olan belgelerin listesini kayıt defterine kaydetmek için kullanır. Bu yöntem, herhangi bir dosyayı otomatik kaydetmez.

Davranışı özelleştirmek için, türetilmiş bir [CWinApp Sınıfında](../../mfc/reference/cwinapp-class.md) bu işlevi geçersiz kılmak veya CWinApp için bir parametre olarak kendi uygulama kurtarma yöntemi [geçmek::RegisterWithRestartManager](#registerwithrestartmanager).

## <a name="cwinappclosealldocuments"></a><a name="closealldocuments"></a>CwinApp::CloseAllDocuments

Çıkmadan önce tüm açık belgeleri kapatmak için bu üye işlevini arayın.

```
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Parametreler

*bEndSession*<br/>
Windows oturumunun sona erdirilip sona ermediğini belirtir. Oturum sona erdiriliyorsa DOĞRUDUR; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Aramadan önce `CloseAllDocuments` [HideApplication'ı](#hideapplication) arayın.

## <a name="cwinappcreateprinterdc"></a><a name="createprinterdc"></a>CwinApp:CreatePrinterDC

Seçili yazıcıdan bir yazıcı aygıtı bağlamı (DC) oluşturmak için bu üye işlevi arayın.

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>Parametreler

*Dc*<br/>
Yazıcı aygıtı bağlamına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yazıcı aygıtı bağlamı başarıyla oluşturulursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CreatePrinterDC`başvuruyla geçtiğiniz aygıt bağlamını başlangıç olarak aparat eder, böylece yazdırmak için kullanabilirsiniz.

İşlev başarılı olursa, yazdırmayı tamamladığınızda aygıt bağlamını yok etmelisiniz. [CDC](../../mfc/reference/cdc-class.md) nesnesinin yıkıcı bunu izin verebilir, ya da açıkça CDC arayarak [yapabilirsiniz::DeleteDC](../../mfc/reference/cdc-class.md#deletedc).

## <a name="cwinappcwinapp"></a><a name="cwinapp"></a>Cwinapp::cwinapp

Bir `CWinApp` nesne inşa eder ve uygulama adı olarak depolanacak *lpszAppName* geçer.

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszAppName*<br/>
Windows'un kullandığı uygulama adını içeren geçersiz sonlandırılmış dize. Bu bağımsız değişken sağlanmazsa veya `CWinApp` NULL ise, AFX_IDS_APP_TITLE kaynak dizesini veya yürütülebilir dosyanın dosya adını kullanır.

### <a name="remarks"></a>Açıklamalar

Türemiş sınıfınızın `CWinApp`bir global nesnesini oluşturmalısınız. Uygulamanızda yalnızca `CWinApp` bir nesne olabilir. Oluşturucu, nesneye `CWinApp` bir işaretçi `WinMain` depolar, böylece uygulamayı başlatmave çalıştırmak için nesnenin üye işlevlerini çağırabilir.

## <a name="cwinappdelregtree"></a><a name="delregtree"></a>CWinApp::DelRegTree

Belirli bir kayıt defteri anahtarını ve tüm alt anahtarlarını siler.

```
LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName);

LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*hParentKey*<br/>
Kayıt defteri anahtarına işle.

*strKeyName*<br/>
Silinecek kayıt defteri anahtarının adı.

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri ERROR_SUCCESS. İşlev başarısız olursa, iade değeri Winerror.h'de tanımlanan sıfır olmayan bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Belirtilen anahtarı ve alt anahtarlarını silmek için bu işlevi arayın.

## <a name="cwinappdomessagebox"></a><a name="domessagebox"></a>CWinApp::DoMessageBox

Çerçeve, bu üye işlevi global işlev [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)için bir ileti kutusu uygulamak için çağırır.

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>Parametreler

*lpszPrompt*<br/>
İleti kutusundaki metnin adresi.

*nTipi*<br/>
İleti kutusu [stili.](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)

*nIDPrompt*<br/>
Yardım bağlamı dizesi için bir dizin.

### <a name="return-value"></a>Dönüş Değeri

Aynı değerleri `AfxMessageBox`.

### <a name="remarks"></a>Açıklamalar

İleti kutusunu açmak için bu üye işlevini aramayın; bunun `AfxMessageBox` yerine kullanın.

Uygulamaların uygulama genelindeki arama işlemesini özelleştirmek `AfxMessageBox` için bu üye işlevini geçersiz kılın.

## <a name="cwinappdowaitcursor"></a><a name="dowaitcursor"></a>CWinApp::DoWaitCursor

Bu üye işlev [CWaitCursor](../../mfc/reference/cwaitcursor-class.md)uygulamak için çerçeve tarafından denir , [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), ve [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>Parametreler

*Ncode*<br/>
Bu parametre 1 ise, bir bekleme imleci görüntülenir. 0 ise, bekleme imleci başvuru sayısını artımsız geri yüklenir. -1 ise, bekleme imleci sona erer.

### <a name="remarks"></a>Açıklamalar

Varsayılan bir kum saati imleci uygular. `DoWaitCursor`bir başvuru sayısını korur. Pozitif olduğunda, kum saati imleci görüntülenir.

Normalde doğrudan aramazsanız `DoWaitCursor` da, bekleme imlecini değiştirmek veya bekleme imleci görüntülenirken ek işlem yapmak için bu üye işlevi geçersiz kılabilirsiniz.

Bekleme imlecini uygulamanın daha kolay ve daha kolay `CWaitCursor`bir yolu için kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

## <a name="cwinappenabled2dsupport"></a><a name="enabled2dsupport"></a>Cwinapp::EnableD2DSupport

Visual Studio 2010 SP1 gereklidir.

Uygulama D2D desteği sağlar. Ana pencere başharfe basılmadan önce bu yöntemi arayın.

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Parametreler

*d2dFactoryType*<br/>
D2D fabrikasının iş parçacığı modeli ve oluşturduğu kaynaklar.

*yazmaFactoryType*<br/>
Yazma fabrikası nesnesinin paylaşılıp paylaşılmayacağını veya yalıtılıp yalıtılmayacağını belirten bir değer

### <a name="return-value"></a>Dönüş Değeri

D2D desteği etkinse TRUE döndürür, FALSE - aksi takdirde

## <a name="cwinappenablehtmlhelp"></a><a name="enablehtmlhelp"></a>Cwinapp::EnablehtmlHelp

Uygulamanızın yardımı için HTMLHelp'i `CWinApp`kullanmak için bu üye işlevini türetilmiş sınıfınızın oluşturucusundan çağırın.

```
void EnableHtmlHelp();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cwinappenableshellopen"></a><a name="enableshellopen"></a>CwinApp::EnableShellOpen

Uygulamanızın kullanıcılarının Windows `InitInstance` Dosya Yöneticisi'nin içinden dosyaları çift tıklattıklarında veri dosyalarını açmalarını sağlamak için genellikle geçersiz kılmanızdan bu işlevi arayın.

```
void EnableShellOpen();
```

### <a name="remarks"></a>Açıklamalar

`RegisterShellFileTypes` Üye işlevi bu işlevle birlikte çağırın veya bir . Belge türlerinin manuel kayıt için başvuru ile REG dosyası.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

## <a name="cwinappenabletaskbarinteraction"></a><a name="enabletaskbarinteraction"></a>CWinApp::EnableTaskbarInteraction

Görev Çubuğu etkileşimini sağlar.

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Windows 7 görev çubuğuyla etkileşimin etkin mi yoksa devre dışı mı (FALSE) olması gerektiğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Görev çubuğu etkileşimi etkinleştirilebilir veya devre dışı atılabilirse TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ana pencerenin oluşturulmasından önce çağrılmalıdır, aksi takdirde iddia ve FALSE döndürür.

## <a name="cwinappexitinstance"></a><a name="exitinstance"></a>CwinApp::ExitInstance

Uygulamanın bu örneğinden `Run` çıkmak için üye işlev in içinden çerçeve tarafından çağrılır.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın çıkış kodu; 0 hata olmadığını gösterir ve 0'dan büyük değerler hata gösterir. Bu değer, 'den gelen `WinMain`iade değeri olarak kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini üye işlevin `Run` içinde değil, herhangi bir yerden aramayın.

Bu işlevin varsayılan uygulaması, uygulamanın çerçeve seçeneklerini yazar. INI dosyası. Uygulamanız sona erdiğinde temizlemek için bu işlevi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

## <a name="cwinappgetapplicationrecoveryparameter"></a><a name="getapplicationrecoveryparameter"></a>CWinApp::GetApplicationRecoveryParameter

Uygulama kurtarma yöntemi için giriş parametresini alır.

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama kurtarma yöntemi için varsayılan giriş parametresi.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan davranışı NULL döndürür.

Daha fazla bilgi için [Bkz. CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).

## <a name="cwinappgetapplicationrecoverypinginterval"></a><a name="getapplicationrecoverypinginterval"></a>Cwinapp::GetApplicationRecoveryPingInterval

Yeniden başlatma yöneticisinin kurtarma geri çağırma işlevinin dönmesini beklediği süreyi verir.

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>Dönüş Değeri

Milisaniye cinsinden sürenin uzunluğu.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma yöneticisine kayıtlı bir uygulama beklenmedik bir şekilde çıktığında, uygulama açık belgeleri kaydetmeye çalışır ve kurtarma geri arama işlevini çağırır. Varsayılan kurtarma geri arama işlevi [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)olduğunu.

Çerçevenin kurtarma geri arama işlevinin döndürülmesini beklediği sürenin uzunluğu ping aralığıdır. Ping aralığını geçersiz kılarak `CWinApp::GetApplicationRecoveryPingInterval` veya 'ye `RegisterWithRestartManager`özel bir değer sağlayarak özelleştirebilirsiniz.

## <a name="cwinappgetapplicationrestartflags"></a><a name="getapplicationrestartflags"></a>CWinApp::GetApplicationRestartFlags

Yeniden başlatma yöneticisi için bayrakları döndürür.

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>Dönüş Değeri

Yeniden başlatma yöneticisinin bayrakları. Varsayılan uygulama 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma yöneticisinin bayraklarının varsayılan uygulamayla hiçbir etkisi yoktur. İleride kullanım için sağlanır.

CWinApp kullanarak uygulamayı yeniden başlat yöneticisine kaydettiğinizde bayrakları [ayarlarsınız::RegisterWithRestartManager](#registerwithrestartmanager).

Yeniden başlatma yöneticisi bayrakları için olası değerler aşağıdaki gibidir:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

## <a name="cwinappgetappregistrykey"></a><a name="getappregistrykey"></a>CWinApp:GetAppRegistryKey

"Software"\RegistryKey\ProfileName HKEY_CURRENT_USER\\anahtarını döndürür.

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*pTM*<br/>
Bir `CAtlTransactionManager` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa uygulama anahtarı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cwinappgetdatarecoveryhandler"></a><a name="getdatarecoveryhandler"></a>CWinApp::GetDataRecoveryHandler

Uygulamanın bu örneği için veri kurtarma işleyicisi alır.

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın bu örneği için veri kurtarma işleyicisi.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma yöneticisini kullanan her [uygulamacdataRecoveryHandler Sınıfının](../../mfc/reference/cdatarecoveryhandler-class.md)bir örneğine sahip olmalıdır. Bu sınıf, açık belgeleri izlemekve dosyaları otomatik kaydetmeden sorumludur. `CDataRecoveryHandler` Davranışı yeniden başlatma yöneticisinin yapılandırmabağlıdır. Daha fazla bilgi için [CDataRecoveryHandler Sınıfı'na](../../mfc/reference/cdatarecoveryhandler-class.md)bakın.

Bu yöntem, Windows Vista'dan daha önce işletim sistemlerinde NULL döndürür. Yeniden başlatma yöneticisi, işletim sistemlerinde Windows Vista'dan önce desteklenmez.

Uygulama şu anda bir veri kurtarma işleyicisi yoksa, bu yöntem bir tane oluşturur ve bir işaretçi döndürür.

## <a name="cwinappgetfirstdoctemplateposition"></a><a name="getfirstdoctemplateposition"></a>CwinApp::GetFirstDocTemplatePosition

Uygulamadaki ilk belge şablonunun konumunu alır.

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilecek bir POSITION değeri; Liste boşsa NULL.

### <a name="remarks"></a>Açıklamalar

İlk [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesini almak için [GetNextDocTemplate'e](#getnextdoctemplate) yapılan çağrıda döndürülen KONUM değerini kullanın.

## <a name="cwinappgethelpmode"></a><a name="gethelpmode"></a>Cwinapp::GetHelpMode

Uygulama tarafından kullanılan yardım türünü alır.

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama tarafından kullanılan yardım türü. Daha fazla bilgi için [CWinApp::m_eHelpType'a](#m_ehelptype) bakın.

## <a name="cwinappgetnextdoctemplate"></a><a name="getnextdoctemplate"></a>Cwinapp::GetNextdocTemplate

*Pos*tarafından tanımlanan belge şablonunu alır, sonra *POS* değerini ayarlar.

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Önceki bir aramayla döndürülen bir `GetNextDocTemplate` POSITION değerine veya [GetFirstDocTemplatePosition'e](#getfirstdoctemplateposition)yapılan başvuru. Değer bu çağrı ile bir sonraki konuma güncelleştirilir.

### <a name="return-value"></a>Dönüş Değeri

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir çağrı `GetNextDocTemplate` ile ilk konumu kurarsanız, bir ileri yineleme `GetFirstDocTemplatePosition`döngüsünde kullanabilirsiniz.

POSITION değerinizin geçerli olduğundan emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Alınan belge şablonu en son kullanılabilir sayılsa, *pos'un* yeni değeri NULL olarak ayarlanır.

## <a name="cwinappgetprinterdevicedefaults"></a><a name="getprinterdevicedefaults"></a>CWinApp::GetPrinterDeviceVarsayılan

Yazdırmaiçin bir yazıcı aygıtı bağlamı hazırlamak için bu üye işlevi arayın.

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>Parametreler

*pPrintDlg*<br/>
[PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Geçerli yazıcı varsayılanlarını Windows'dan alır. INI dosya gerektiğinde veya Yazdırma Kurulumu kullanıcı tarafından ayarlanan son yazıcı yapılandırmasını kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

## <a name="cwinappgetprofilebinary"></a><a name="getprofilebinary"></a>Cwinapp::GetProfileBinary

Uygulamanın kayıt defterinin belirli bir bölümündeki bir girişten ikili veri almak için bu üye işlevi arayın veya . INI dosyası.

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>Parametreler

*lpszBölüm*<br/>
Girişi içeren bölümü belirten null-sonlandırılan dizeyi işaret eder.

*lpszEntry*<br/>
Değeri alınacak girişi içeren null-sonlandırılan dizeyi işaret ediyor.

*ppData*<br/>
Verilerin adresini alacak bir işaretçiye işaret eder.

*pBayt*<br/>
Verilerin boyutunu (baytolarak) alacak bir UINT'ye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev büyük/küçük harf duyarlı değildir, bu nedenle *lpszSection* ve *lpszEntry* parametrelerindeki dizeleri farklı olabilir.

> [!NOTE]
> `GetProfileBinary`bir arabellek ayırır ve \* *adresini ppData'da*döndürür. Arayan, **delete [] kullanarak**arabelleği serbest bırakın.

> [!IMPORTANT]
> Bu işlev tarafından döndürülen veriler mutlaka NULL sonlandırıldı ve arayan doğrulama gerçekleştirmesi gerekir. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

Ek bir örnek için Bkz. [CWinApp::WriteProfileBinary](#writeprofilebinary).

## <a name="cwinappgetprofileint"></a><a name="getprofileint"></a>CWinApp:GetProfileInt

Uygulamanın kayıt defterinin belirli bir bölümündeki bir girişten bir tamsayı değerini almak için bu üye işlevi arayın veya . INI dosyası.

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>Parametreler

*lpszBölüm*<br/>
Girişi içeren bölümü belirten null-sonlandırılan dizeyi işaret eder.

*lpszEntry*<br/>
Değeri alınacak girişi içeren null-sonlandırılan dizeyi işaret ediyor.

*nVarsayılan*<br/>
Çerçeve girişi bulamıyorsa, dönmek için varsayılan değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, belirtilen girişi izleyen dizenin gerçek değeri. İşlev girişi bulamazsa, iade değeri *nDefault* parametresinin değeridir. Belirtilen girişe karşılık gelen değer tamsayı değilse, iade değeri 0'dır.

Bu üye işlev, değer için hexadecimal gösterimi destekler. INI dosyası. İmzalı bir tamsayı aldığınızda, değeri bir **inte'ye**dökmeniz gerekir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev büyük/küçük harf duyarlı değildir, bu nedenle *lpszSection* ve *lpszEntry* parametrelerindeki dizeleri farklı olabilir.

> [!IMPORTANT]
> Bu işlev tarafından döndürülen veriler mutlaka NULL sonlandırıldı ve arayan doğrulama gerçekleştirmesi gerekir. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

Ek bir örnek için Bkz. [CWinApp::WriteProfileInt](#writeprofileint).

## <a name="cwinappgetprofilestring"></a><a name="getprofilestring"></a>CwinApp::GetProfileString

Uygulamanın kayıt defterinde belirtilen bölümde bir girişle ilişkili dizeyi almak için bu üye işlevi arayın veya . INI dosyası.

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszBölüm*<br/>
Girişi içeren bölümü belirten null-sonlandırılan dizeyi işaret eder.

*lpszEntry*<br/>
Dizesi alınacak girişi içeren null-sonlandırılan dizeyi işaret edin. Bu değer NULL olmamalıdır.

*lpszVarsayılan*<br/>
Giriş başlatma dosyasında bulunamıyorsa, verilen giriş için varsayılan dize değerine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İade değeri, uygulamanın dizesi. Dize bulunamıyorsa INI dosyası veya *lpszDefault.* Çerçeve tarafından desteklenen maksimum dize uzunluğu _MAX_PATH. *lpszDefault* NULL ise, iade değeri boş bir dizedir.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
> Bu işlev tarafından döndürülen veriler mutlaka NULL sonlandırıldı ve arayan doğrulama gerçekleştirmesi gerekir. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Başka bir örnek için, CWinApp örneğine [bakın::GetProfileInt](#getprofileint).

## <a name="cwinappgetsectionkey"></a><a name="getsectionkey"></a>Cwinapp::GetSectionKey

"Yazılım"\RegistryKey\AppName\lpszSection HKEY_CURRENT_USER\\için anahtarı döndürür.

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszBölüm*<br/>
Elde edilecek anahtarın adı.

*pTM*<br/>
Bir `CAtlTransactionManager` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa bölüm tuşu; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cwinapphideapplication"></a><a name="hideapplication"></a>CwinApp::HideApplication

Açık belgeleri kapatmadan önce bir uygulamayı gizlemek için bu üye işlevi arayın.

```
void HideApplication();
```

## <a name="cwinapphtmlhelp"></a><a name="htmlhelp"></a>Cwinapp::htmlYardım

HTMLHelp uygulamasını çağırmak için bu üye işlevini arayın.

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>Parametreler

*Dwdata*<br/>
Ek veriler belirtir. Kullanılan değer *nCmd* parametresinin değerine bağlıdır. Varsayılan lar `0x000F` HH_HELP_CONTEXT [anlamına](/previous-versions/windows/desktop/htmlhelp/hh-help-context-command)gelir.

*nCmd*<br/>
İstenen yardım türünü belirtir. Olası değerlerin listesi ve *bunların dwData* parametresini nasıl etkilediği için, Windows SDK'daki [HtmlHelpW veya HtmlHelpA](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpw) API işlevlerinde açıklanan *uCommand* parametresine bakın. [HtmlHelpA](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpa)

### <a name="remarks"></a>Açıklamalar

Çerçeve ayrıca HTMLHelp uygulamasını çağırmak için bu işlevi çağırır.

Uygulamanız sona erdiğinde çerçeve HTMLHelp uygulamasını otomatik olarak kapatır.

## <a name="cwinappinitinstance"></a><a name="initinstance"></a>CWinApp::InitInstance

Windows, aynı programın birkaç kopyasının aynı anda çalışmasına izin verir.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Uygulama başlatma kavramsal olarak iki bölüme ayrılır: program ilk kez çalıştığında yapılan bir kerelik uygulama başlatma ve ilk kez de dahil olmak üzere programın her bir kopyası çalıştığında çalışan örnek başlatma. Çerçevenin `WinMain` uygulanması bu işlevi çağırır.

Windows `InitInstance` altında çalışan uygulamanızın her yeni örneğini başlatmayı geçersiz kılmak için geçersiz kılın. Genellikle, ana pencere `InitInstance` nesnenizi oluşturmak ve veri `CWinThread::m_pMainWnd` üyesini bu pencereye işaret etmek üzere ayarlamak için geçersiz kılarsınız. Bu üye işlevini geçersiz kılma hakkında daha fazla bilgi için [CWinApp: Application Class'](../../mfc/cwinapp-the-application-class.md)a bakın.

> [!NOTE]
> MFC uygulamaları tek dişli daire (STA) olarak başharfe getirilmelidir. Geçersiz kılmada `InitInstance` [CoInitializeEx'i](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) ararsanız, COINIT_APARTMENTTHREADED belirtin (COINIT_MULTITHREADED yerine).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

## <a name="cwinappistaskbarinteractionenabled"></a><a name="istaskbarinteractionenabled"></a>CWinApp::IsTaskbarInteractionEtkin

Windows 7 Görev Çubuğu etkileşiminin etkin olup olmadığını söyler.

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>Dönüş Değeri

Çağrıldıysa `EnableTaskbarInteraction` ve İşletim Sistemi Windows 7 veya daha yüksekse TRUE'yu döndürür.

### <a name="remarks"></a>Açıklamalar

Görev Çubuğu etkileşimi, MDI uygulamasının fare işaretçisi uygulama görev çubuğu düğmesinin üzerindeyken görünen ayrı sekmeli küçük resimlerde MDI alt çocuklarının içeriğini görüntülediğinde anlamına gelir.

## <a name="cwinapploadcursor"></a><a name="loadcursor"></a>CWinApp::LoadCursor

*LpszResourceName* tarafından adlandırılmış veya *nIDResource* tarafından belirtilen imleç kaynağını geçerli yürütülebilir dosyadan yükler.

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
İmleç kaynağının adını içeren null-sonlandırılan dizeişaret eder. Bu argüman `CString` için bir kullanabilirsiniz.

*nIDKaynak*<br/>
İmleç kaynağının kimliği. Kaynak listesi için Windows SDK'daki [LoadCursor](/windows/win32/api/winuser/nf-winuser-loadcursorw) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa imlecin tutamacı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

`LoadCursor`imleci yalnızca daha önce yüklenmediyse belleğe yükler; aksi takdirde, varolan kaynağın bir tutamacı alır.

Önceden tanımlanmış Windows imleçlerine erişmek için [LoadStandardCursor](#loadstandardcursor) veya [LoadOEMCursor](#loadoemcursor) üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

## <a name="cwinapploadicon"></a><a name="loadicon"></a>Cwinapp::loadicon

*LpszResourceName* tarafından adlandırılan veya *nIDResource* tarafından çalıştırılabilir dosyadan belirtilen simge kaynağını yükler.

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Simge kaynağının adını içeren null-sonlandırılan dizeyi işaret edin. Bu bağımsız değişken `CString` için de a kullanabilirsiniz.

*nIDKaynak*<br/>
Simge kaynağının kimlik numarası.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simgeye bir tanıtıcı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

`LoadIcon`simgeyi yalnızca daha önce yüklenmemişse yükler; aksi takdirde, varolan kaynağın bir tutamacı alır.

Önceden tanımlanmış Windows simgelerine erişmek için [LoadStandardIcon](#loadstandardicon) veya [LoadOEMIcon](#loadoemicon) üye işlevini kullanabilirsiniz.

> [!NOTE]
> Bu üye işlev, yalnızca boyutu SM_CXICON ve SM_CYICON sistem metrik değerlerine uygun bir simge yükleyebilen Win32 API işlevini [LoadIcon](/windows/win32/api/winuser/nf-winuser-loadiconw)olarak adlandırır.

## <a name="cwinapploadoemcursor"></a><a name="loadoemcursor"></a>CWinApp::LoadOEMCursor

*nIDCursor*tarafından belirtilen Windows önceden tanımlanmış imleç kaynağını yükler.

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>Parametreler

*nIDCursor*<br/>
Önceden tanımlanmış bir Windows imleci belirten **bir OCR_,** sabit tanımlayıcıyı gösterir. WINDOWS'daki `#define OEMRESOURCE` `#include \<afxwin.h>` **OCR_** sabitlerine erişmek için önce sahip olmalısınız. H.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa imlecin tutamacı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Önceden `LoadOEMCursor` tanımlanmış Windows imleçlerine erişmek için veya [LoadStandardCursor](#loadstandardcursor) üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

## <a name="cwinapploadoemicon"></a><a name="loadoemicon"></a>Cwinapp::loadoemicon

*nIDIcon*tarafından belirtilen Windows önceden tanımlanmış simge kaynağını yükler.

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>Parametreler

*nIDIcon*<br/>
Önceden tanımlanmış bir Windows simgesi belirten **bir OIC_,** sabit tanımlayıcıyı gösterir. WINDOWS'daki `#define OEMRESOURCE` `#include \<afxwin.h>` **OIC_** sabitlerine erişmek için önce sahip olmalısınız. H.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simgeye bir tanıtıcı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Önceden `LoadOEMIcon` tanımlanmış Windows simgelerine erişmek için veya [LoadStandardIcon](#loadstandardicon) üye işlevini kullanın.

## <a name="cwinapploadstandardcursor"></a><a name="loadstandardcursor"></a>CWinApp::LoadStandardCursor

*LpszCursorName'nin* belirttiği Windows önceden tanımlanmış imleç kaynağını yükler.

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>Parametreler

*lpszCursorName*<br/>
Önceden tanımlanmış bir Windows imleci belirten **IDC_** bir bildirim sabit tanımlayıcı. Bu tanımlayıcılar WINDOWS'da tanımlanır. H. Aşağıdaki liste *lpszCursorName*için olası önceden tanımlanmış değerleri ve anlamları gösterir:

- IDC_ARROW Standart ok imleci

- IDC_IBEAM Standart metin ekleme imleci

- Windows zaman alan bir görevi yerine getirirken kullanılan IDC_WAIT Kum Saati imleci kullanılır

- seçim için IDC_CROSS Çapraz saç imleci

- IDC_UPARROW Düz yukarı işaret eden ok

- IDC_SIZE Eski ve desteklenmeyen; IDC_SIZEALL kullanın

- IDC_SIZEALL Dört köşeli bir ok. Bir pencereyi yeniden boyutlandırmak için kullanılacak imleç.

- IDC_ICON Eski ve desteklenmeyen. IDC_ARROW kullan.

- IDC_SIZENWSE Sol üst ve sağ altta uçları olan iki başlı ok

- IDC_SIZENESW Sağ üst ve alt sol uçları ile iki başlı ok

- IDC_SIZEWE Yatay iki başlı ok

- IDC_SIZENS Dikey iki başlı ok

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa imlecin tutamacı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Önceden `LoadStandardCursor` tanımlanmış Windows imleçlerine erişmek için veya [LoadOEMCursor](#loadoemcursor) üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

## <a name="cwinapploadstandardicon"></a><a name="loadstandardicon"></a>Cwinapp:loadstandardicon

*LpszIconName'nin* belirttiği Windows önceden tanımlanmış simge kaynağını yükler.

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>Parametreler

*lpszIconName*<br/>
Önceden tanımlanmış bir Windows simgesi belirten bir bildirim sabit tanımlayıcısı. Bu tanımlayıcılar WINDOWS'da tanımlanır. H. Olası önceden tanımlanmış değerlerin ve açıklamalarının listesi için Windows SDK'daki [LoadIcon'daki](/windows/win32/api/winuser/nf-winuser-loadiconw) *lpIconName* parametresini görün.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simgeye bir tanıtıcı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Önceden `LoadStandardIcon` tanımlanmış Windows simgelerine erişmek için veya [LoadOEMIcon](#loadoemicon) üye işlevini kullanın.

## <a name="cwinapploadstdprofilesettings"></a><a name="loadstdprofilesettings"></a>CWinApp::LoadStdProfileSettings

En son kullanılan (MRU) dosyaların listesini ve son önizleme durumunu etkinleştirmek ve yüklemek için InitInstance üye işlevini [initInstance](#initinstance) üye işlevi içinden arayın.

```
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>Parametreler

*nMaxMRU*<br/>
İzlemek için son kullanılan dosyaların sayısı.

### <a name="remarks"></a>Açıklamalar

*nMaxMRU* 0 ise, MRU listesi tutulamaz.

## <a name="cwinappm_bhelpmode"></a><a name="m_bhelpmode"></a>CWinApp::m_bHelpMode

Uygulama Yardım bağlamı modundaysa TRUE (geleneksel olarak SHIFT + F1 ile çağrılır); aksi takdirde YANLIŞ.

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>Açıklamalar

Yardım bağlamı modunda imleç bir soru işareti haline gelir ve kullanıcı bunu ekran adedine taşıyabilir. Yardım modundayken özel işleme uygulamak istiyorsanız bu bayrağı inceleyin. `m_bHelpMode`bool tipinin ortak değişkenidir.

## <a name="cwinappm_dwrestartmanagersupportflags"></a><a name="m_dwrestartmanagersupportflags"></a>CWinApp::m_dwRestartManagerSupportFlags

Yeniden başlatma yöneticisinin nasıl tepkieceğini belirleyen bayraklar.

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma yöneticisini etkinleştirmek için istediğiniz davranışa ayarlayın. `m_dwRestartManagerSupportFlags` Aşağıdaki tabloda kullanılabilir bayrakları gösterilmektedir.

|||
|-|-|
|Bayrak|Açıklama|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|Uygulama [CWinApp kullanılarak kaydedilir::RegisterWithRestartManager](#registerwithrestartmanager). Yeniden başlatma yöneticisi, beklenmedik bir şekilde çıkarsa uygulamayı yeniden başlatmaktan sorumludur.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY|Uygulama yeniden başlatma yöneticisine kaydedilir ve uygulamayı yeniden başlattığında yeniden başlatma yöneticisi kurtarma geri arama işlevini çağırır. Varsayılan kurtarma geri arama işlevi [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)olduğunu.|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|Otomatik kaydetme etkindir ve yeniden başlatma yöneticisi uygulama yeniden başlatıldığında açık belgeleri otomatik olarak kaydeder.|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|Otomatik kaydetme etkinleştirilir ve yeniden başlatma yöneticisi açık belgeleri düzenli aralıklarla otomatik olarak kaydeder. Aralık [CWinApp tarafından tanımlanır::m_nAutosaveInterval](#m_nautosaveinterval).|
|- AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|Yeniden başlatma yöneticisi, uygulamayı beklenmeyen bir çıkıştan yeniden başlattıktan sonra daha önce açık olan belgeleri açar. [CDataRecoveryHandler Sınıfı,](../../mfc/reference/cdatarecoveryhandler-class.md) açık belgelerin listesini depolamayı ve bunları geri getiriyi işler.|
|- AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|Yeniden başlatma yöneticisi, kullanıcıdan uygulamayı yeniden başlattıktan sonra otomatik olarak kaydedilen dosyaları geri yüklemesini ister. Sınıf `CDataRecoveryHandler` kullanıcıyı sorgular.|
|- AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_SUPPORT_RECOVER ve AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES birliği.|
|- AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL ve AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES birliği.|
|- AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES ve AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES birliği.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|Sendika ofAFX_RESTART_MANAGER_SUPPORT_RECOVERY, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES ve AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|

## <a name="cwinappm_ehelptype"></a><a name="m_ehelptype"></a>CWinApp::m_eHelpType

Bu veri üyesinin türü, `CWinApp` sınıf içinde tanımlanan numaralandırılmış tür AFX_HELP_TYPE dir.

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>Açıklamalar

numaralandırma AFX_HELP_TYPE aşağıdaki gibi tanımlanır:

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- Uygulamanın yardımını HTML Yardımı'na ayarlamak için [SetHelpMode'u](#sethelpmode) arayın ve belirtin. `afxHTMLHelp`

- Uygulamanın yardımını WinHelp'e ayarlamak `SetHelpMode` için `afxWinHelp`arayın ve belirtin.

## <a name="cwinappm_hinstance"></a><a name="m_hinstance"></a>CWinApp:m_hInstance

Windows tarafından geçirilen *hInstance* parametresine `WinMain`karşılık gelir.

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>Açıklamalar

Veri `m_hInstance` üyesi, Windows altında çalışan uygulamanın geçerli örneğine bir tanıtıcıdır. Bu global fonksiyon [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)tarafından döndürülür. `m_hInstance`hinstance türünün ortak değişkenidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

## <a name="cwinappm_lpcmdline"></a><a name="m_lpcmdline"></a>CWinApp::m_lpCmdLine

Windows tarafından 'a geçirilen *lpCmdLine* `WinMain`parametresine karşılık gelir.

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>Açıklamalar

Uygulama için komut satırını belirten null-sonlandırılan dizeyi işaret edin. Uygulama `m_lpCmdLine` başlatıldığında kullanıcının girdiği komut satırı bağımsız değişkenlerine erişmek için kullanın. `m_lpCmdLine`tip LPTSTR bir ortak değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

## <a name="cwinappm_nautosaveinterval"></a><a name="m_nautosaveinterval"></a>CWinApp::m_nAutosaveInterval

Otomatik kaydetmeler arasındaki milisaniye cinsinden sürenin uzunluğu.

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>Açıklamalar

Açık belgeleri belirli aralıklarla otomatik olarak kaydetmek için yeniden başlat yöneticisini yapılandırabilirsiniz. Uygulamanız dosyaları otomatik olarak kaydetmiyorsa, bu parametrenin hiçbir etkisi yoktur.

## <a name="cwinappm_ncmdshow"></a><a name="m_ncmdshow"></a>CWinApp:m_nCmdShow

Windows tarafından ''ye geçirilen *nCmdShow* parametresine `WinMain`karşılık gelir.

```
int m_nCmdShow;
```

### <a name="remarks"></a>Açıklamalar

CWnd'yi aradiğinizde bağımsız değişken olarak geçmelisiniz::Uygulamanızın `m_nCmdShow` ana penceresi için [ShowWindow.](../../mfc/reference/cwnd-class.md#showwindow) `m_nCmdShow`türü **int**bir ortak değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

## <a name="cwinappm_pactivewnd"></a><a name="m_pactivewnd"></a>CWinApp::m_pActiveWnd

OLE sunucu uygulamanızı yerinde etkinleştirdiren OLE kapsayıcı uygulamasının ana penceresine işaretçi depolamak için bu veri üyesini kullanın.

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi NULL ise, uygulama yerinde etkin değildir.

Çerçeve penceresi bir OLE kapsayıcı uygulaması tarafından yerinde etkinleştirildiğinde çerçeve bu üye değişkeni ayarlar.

## <a name="cwinappm_pdatarecoveryhandler"></a><a name="m_pdatarecoveryhandler"></a>CWinApp::m_pDataRecoveryHandler

Uygulama için veri kurtarma işleyicisini işaretçi.

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>Açıklamalar

Bir uygulamanın veri kurtarma işleyicisi açık belgeleri izler ve bunları otomatik olarak kaydeder. Framework, bir uygulama beklenmeyen bir şekilde çıktıktan sonra yeniden başlatıldığında otomatik olarak kaydedilen dosyaları geri yüklemek için veri kurtarma işleyicisini kullanır. Daha fazla bilgi için [CDataRecoveryHandler Sınıfı'na](../../mfc/reference/cdatarecoveryhandler-class.md)bakın.

## <a name="cwinappm_pszappname"></a><a name="m_pszappname"></a>CWinApp:m_pszAppName

Uygulamanın adını belirtir.

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>Açıklamalar

Uygulama [adı, CWinApp](#cwinapp) oluşturucuya geçirilen parametreden veya belirtilmemişse, AFX_IDS_APP_TITLE kimliği içeren kaynak dizesinden gelebilir. Uygulama adı kaynakta bulunamazsa, programın. EXE dosya adı.

Küresel fonksiyon [AfxGetAppName](application-information-and-management.md#afxgetappname)tarafından döndürülür. `m_pszAppName`tür **const char**<strong>\*</strong>bir ortak değişkendir.

> [!NOTE]
> Bir değer `m_pszAppName`atarsanız, yığına dinamik olarak ayrılması gerekir. Yıkıcı `CWinApp` bu işaretçi ile **ücretsiz**( ) çağırır. Birçok ayırma yapmak `_tcsdup`için ( ) çalışma zamanı kitaplığı işlevini kullanmak istiyorum. Ayrıca, yeni bir değer atamadan önce geçerli işaretçiyle ilişkili belleği serbest leştirin. Örneğin:

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

## <a name="cwinappm_pszexename"></a><a name="m_pszexename"></a>CWinApp::m_pszExeName

Uzantıolmadan uygulamanın yürütülebilir dosyasının adını içerir.

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>Açıklamalar

[m_pszAppName](#m_pszappname)aksine, bu ad boşlukları içeremez. `m_pszExeName`tür **const char**<strong>\*</strong>bir ortak değişkendir.

> [!NOTE]
> Bir değer `m_pszExeName`atarsanız, yığına dinamik olarak ayrılması gerekir. Yıkıcı `CWinApp` bu işaretçi ile **ücretsiz**( ) çağırır. Birçok ayırma yapmak `_tcsdup`için ( ) çalışma zamanı kitaplığı işlevini kullanmak istiyorum. Ayrıca, yeni bir değer atamadan önce geçerli işaretçiyle ilişkili belleği serbest leştirin. Örneğin:

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

## <a name="cwinappm_pszhelpfilepath"></a><a name="m_pszhelpfilepath"></a>CWinApp::m_pszHelpFilePath

Uygulamanın Yardım dosyasına giden yolu içerir.

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve "ile uygulamanın adını başlatır. `m_pszHelpFilePath` HLP" ekinde. Yardım dosyasının adını değiştirmek `m_pszHelpFilePath` için, istenen yardım dosyasının tam adını içeren bir dize işaret ayarlayın. Bunu yapmak için uygun bir yer uygulamanın [InitInstance](#initinstance) işlevindedir. `m_pszHelpFilePath`tür **const char**<strong>\*</strong>bir ortak değişkendir.

> [!NOTE]
> Bir değer `m_pszHelpFilePath`atarsanız, yığına dinamik olarak ayrılması gerekir. Yıkıcı `CWinApp` bu işaretçi ile **ücretsiz**( ) çağırır. Birçok ayırma yapmak `_tcsdup`için ( ) çalışma zamanı kitaplığı işlevini kullanmak istiyorum. Ayrıca, yeni bir değer atamadan önce geçerli işaretçiyle ilişkili belleği serbest leştirin. Örneğin:

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

## <a name="cwinappm_pszprofilename"></a><a name="m_pszprofilename"></a>CWinApp:m_pszProfileName

Uygulamanın adını içerir. INI dosyası.

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>Açıklamalar

`m_pszProfileName`tür **const char**<strong>\*</strong>bir ortak değişkendir.

> [!NOTE]
> Bir değer `m_pszProfileName`atarsanız, yığına dinamik olarak ayrılması gerekir. Yıkıcı `CWinApp` bu işaretçi ile **ücretsiz**( ) çağırır. Birçok ayırma yapmak `_tcsdup`için ( ) çalışma zamanı kitaplığı işlevini kullanmak istiyorum. Ayrıca, yeni bir değer atamadan önce geçerli işaretçiyle ilişkili belleği serbest leştirin. Örneğin:

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

## <a name="cwinappm_pszregistrykey"></a><a name="m_pszregistrykey"></a>CWinApp::m_pszRegistryKey

Kayıt defteri veya INI dosyasında uygulama profili ayarlarının nerede depolandığınızı belirlemek için kullanılır.

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>Açıklamalar

Normalde, bu veri üyesi salt okunur olarak kabul edilir.

- Değer bir kayıt defteri anahtarına depolanır. Uygulama profili ayarının adı aşağıdaki kayıt defteri anahtarına eklenir: HKEY_CURRENT_USER/Software/LocalAppWizard-Generated/.

Bir değer `m_pszRegistryKey`atarsanız, yığına dinamik olarak ayrılması gerekir. Yıkıcı `CWinApp` bu işaretçi ile **ücretsiz**( ) çağırır. Birçok ayırma yapmak `_tcsdup`için ( ) çalışma zamanı kitaplığı işlevini kullanmak istiyorum. Ayrıca, yeni bir değer atamadan önce geçerli işaretçiyle ilişkili belleği serbest leştirin. Örneğin:

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

## <a name="cwinappm_pszappid"></a><a name="m_pszappid"></a>CWinApp::m_pszAppID

Uygulama Kullanıcı Modeli Kimliği.

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cwinapponcontexthelp"></a><a name="oncontexthelp"></a>Cwinapp::OncontextHelp

Uygulama içinde SHIFT+F1 Yardımını işler.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Açıklamalar

Bu üye `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` işlevi etkinleştirmek için sınıf ileti eşleme haritanıza `CWinApp` bir deyim eklemeniz ve ayrıca bu üye işlevi etkinleştirmek için genellikle SHIFT+F1 olan bir hızlandırıcı tablo girişi eklemeniz gerekir.

`OnContextHelp`uygulamayı Yardım moduna sokar. İmleç bir ok ve soru işaretine dönüşür ve kullanıcı daha sonra fare işaretçisini taşıyabilir ve iletişim kutusu, pencere, menü veya komut düğmesini seçmek için sol fare düğmesine basabilir. Bu üye işlev imlecin altındaki nesnenin Yardım bağlamını alır ve windows işlevini Bu Yardım bağlamıyla WinHelp olarak çağırır.

## <a name="cwinapponddecommand"></a><a name="onddecommand"></a>Cwinapp::OnDDEKomut

Ana çerçeve penceresi Bir DDE yürütme iletisi aldığında çerçeve tarafından çağrılır.

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>Parametreler

*lpszKomut*<br/>
Uygulama tarafından alınan bir DDE komut dizesini işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Komut işlenirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, komutun belgeyi açma isteği olup olmadığını denetler ve varsa belirtilen belgeyi açar. Windows Dosya Yöneticisi, kullanıcı bir veri dosyasını çift tıklattığında genellikle bu tür DDE komut dizeleri gönderir. Yazdırma komutu gibi diğer DDE yürütme komutlarını işlemek için bu işlevi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

## <a name="cwinapponfilenew"></a><a name="onfilenew"></a>Cwinapp::OnfileNew

ID_FILE_NEW komutunu uygular.

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>Açıklamalar

Bu üye `ON_COMMAND( ID_FILE_NEW, OnFileNew )` işlevi etkinleştirmek için sınıf ileti haritanıza bir deyim eklemeniz `CWinApp` gerekir. Etkinse, bu işlev Yeni Dosya komutunun yürütülmesini işler.

Varsayılan davranış ve bu üye işlevinin nasıl geçersiz kılınıp sürtünmeye çalışılabilen yönergeler hakkında bilgi için [Teknik Not 22'ye](../../mfc/tn022-standard-commands-implementation.md) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponfileopen"></a><a name="onfileopen"></a>Cwinapp::OnfileOpen

ID_FILE_OPEN komutunu uygular.

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>Açıklamalar

Bu üye `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` işlevi etkinleştirmek için sınıf ileti haritanıza bir deyim eklemeniz `CWinApp` gerekir. Etkinleştirilirse, bu işlev Dosya Aç komutunun yürütülmesini işler.

Varsayılan davranış ve bu üye işlevinin nasıl geçersiz kılınıp sürtüldünyon kılavuzu hakkında bilgi için [Teknik Not 22'ye](../../mfc/tn022-standard-commands-implementation.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponfileprintsetup"></a><a name="onfileprintsetup"></a>Cwinapp::OnfileprintSetup

ID_FILE_PRINT_SETUP komutunu uygular.

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>Açıklamalar

Bu üye `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` işlevi etkinleştirmek için sınıf ileti haritanıza bir deyim eklemeniz `CWinApp` gerekir. Etkinse, bu işlev Dosya Yazdır komutunun yürütülmesini işler.

Varsayılan davranış ve bu üye işlevinin nasıl geçersiz kılınıp sürtüldünyon kılavuzu hakkında bilgi için [Teknik Not 22'ye](../../mfc/tn022-standard-commands-implementation.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponhelp"></a><a name="onhelp"></a>Cwinapp::OnHelp

Uygulama içinde F1 Yardım işler (geçerli bağlamı kullanarak).

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>Açıklamalar

Genellikle f1 tuşu için bir hızlandırıcı anahtarı girişi de eklersiniz. F1 anahtarını etkinleştirmek yalnızca bir kuraldır, gereklilik değildir.

Bu üye `ON_COMMAND( ID_HELP, OnHelp )` işlevi etkinleştirmek için sınıf ileti haritanıza bir deyim eklemeniz `CWinApp` gerekir. Etkinleştirilirse, kullanıcı F1 tuşuna bastığında çerçeve tarafından çağrılır.

Bu ileti işleyiciişlevinin varsayılan uygulaması, geçerli pencereye, iletişim kutusuna veya menü öğesine karşılık gelen Yardım bağlamını belirler ve ardından WINHELP'i çağırır. Exe. Şu anda kullanılabilir bağlam yoksa, işlev varsayılan bağlamı kullanır.

Yardım bağlamını pencere, iletişim kutusu, menü öğesi veya araç çubuğu düğmesi dışında bir şeye ayarlamak için bu üye işlevini geçersiz kılın. İstenilen Yardım bağlam kimliğiyle arayın. `WinHelp`

## <a name="cwinapponhelpfinder"></a><a name="onhelpfinder"></a>CWinApp::OnHelpFinder

ID_HELP_FINDER ve ID_DEFAULT_HELP komutlarını işler.

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>Açıklamalar

Bu üye `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` işlevi etkinleştirmek için sınıf ileti haritanıza bir deyim eklemeniz `CWinApp` gerekir. Etkinleştirilmişse, uygulamanızın kullanıcısı standart `WinHelp` **HELP_FINDER** konusuyla birlikte çağırmak için Yardım Bulucu komutunu seçtiğinde çerçeve bu ileti işleyicisi işlevini çağırır.

## <a name="cwinapponhelpindex"></a><a name="onhelpindex"></a>Cwinapp::OnHelpIndex

ID_HELP_INDEX komutunu işler ve varsayılan bir Yardım konusu sağlar.

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>Açıklamalar

Bu üye `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` işlevi etkinleştirmek için sınıf ileti haritanıza bir deyim eklemeniz `CWinApp` gerekir. Etkinse, uygulamanızın kullanıcısı standart `WinHelp` **HELP_INDEX** konusuyla çağırmak için Yardım Dizini komutunu seçtiğinde çerçeve bu ileti işleyicisi işlevini çağırır.

## <a name="cwinapponhelpusing"></a><a name="onhelpusing"></a>Cwinapp::OnHelpUsing

ID_HELP_USING komutunu işler.

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>Açıklamalar

Bu üye `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` işlevi etkinleştirmek için sınıf ileti haritanıza bir deyim eklemeniz `CWinApp` gerekir. Uygulamanızın `WinHelp` kullanıcısı, uygulamayı standart **HELP_HELPONHELP** konusuyla çağırmak için Yardım Kullanma komutunu seçtiğinde çerçeve bu ileti işleyicisi işlevini çağırır.

## <a name="cwinapponidle"></a><a name="onidle"></a>Cwinapp::onidle

Boşta zamanlı işleme gerçekleştirmek için bu üye işlevi geçersiz kılın.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Parametreler

*lSay*<br/>
Uygulamanın ileti sırası boşolduğunda her seferinde `OnIdle` artıya eklenen sayaç çağrılır. Bu sayı, yeni bir ileti her işlenirken 0'a sıfırlanır. İleti işlemeden uygulamanın boşta kalma süresini belirlemek için *lCount* parametresini kullanabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Daha fazla boşta işlem süresi almak için sıfır olmayan; Daha fazla boşta zaman gerekiyorsa 0.

### <a name="remarks"></a>Açıklamalar

`OnIdle`uygulamanın ileti sırası boş olduğunda varsayılan ileti döngüsünde çağrılır. Kendi arka plan boşta işleyici görevlerinizi çağırmak için geçersiz kılmanızı kullanın.

`OnIdle`boşta işlem süresi gerekmediğini belirtmek için 0 döndürmelidir. İleti sırası boşolduğunda ve yeni bir `OnIdle` ileti her işlendiğinde 0'a sıfırlandığında *lCount* parametresi her seferinde artışla çağrılır. Bu sayıya göre farklı boşta yordamlarınızı arayabilirsiniz.

Aşağıdaki boşta döngü işleme özetler:

1. Microsoft Hazırlık Sınıfı Kitaplığı'ndaki ileti döngüsü ileti sırasını denetler `OnIdle` ve bekleyen iletiler bulamazsa, uygulama nesnesini çağırır ve *lCount* bağımsız değişkeni olarak 0'ı karşılar.

2. `OnIdle`bazı işleme gerçekleştirir ve daha fazla işlem yapmak için yeniden çağrılması gerektiğini belirtmek için sıfır olmayan bir değer döndürür.

3. İleti döngüsü ileti sırasını yeniden denetler. Bekleyen ileti yoksa, `OnIdle` *lCount* bağımsız değişkenini artımlı olarak yeniden arar.

4. Sonunda, `OnIdle` tüm boşta kalan görevleri işlemeyi tamamlar ve 0 döndürür. Bu, ileti sırası alınana kadar aramayı `OnIdle` durdurmasını söyler ve bu noktada boşta kalan döngü bağımsız değişken olarak ayarlanmış olarak yeniden başlar.

Uygulamanız geri dönene `OnIdle` kadar `OnIdle` kullanıcı girişini işleyemediği için uzun görevleri gerçekleştirin.

> [!NOTE]
> Güncelleştirmelerin `OnIdle` varsayılan uygulaması, menü öğeleri ve araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerine komut verir ve iç veri yapısı temizlemesini gerçekleştirir. Bu nedenle, geçersiz `OnIdle`kılarsanız, `CWinApp::OnIdle` geçersiz `lCount` kılınan sürümünde ile aramanız gerekir. İlk olarak tüm taban sınıf boşta işleme (yani, taban sınıf `OnIdle` 0 döndürene kadar) çağırın. Taban sınıf işleme tamamlanmadan önce çalışma gerçekleştirmeniz gerekiyorsa, işinizi yapmak için uygun *lCount'ı* seçmek için taban sınıf uygulamasını gözden geçirin.

İleti kuyruğundan `OnIdle` bir ileti alındığı zaman çağrılmak istemiyorsanız, [CWinThreadIsIdleMessage'ı](../../mfc/reference/cwinthread-class.md#isidlemessage)geçersiz kılabilirsiniz. Bir uygulama çok kısa bir zamanlayıcı ayarlamışsa veya sistem `OnIdle` WM_SYSTIMER iletigönderiyorsa, art arda çağrılır ve performansı düşürür.

### <a name="example"></a>Örnek

Aşağıdaki iki örnek, nasıl `OnIdle`kullanılacağını gösterir. İlk örnek, görevleri önceliklendirmek için *lCount* bağımsız değişkenini kullanarak iki boşta görevi işler. İlk görev yüksek önceliklidir ve bunu mümkün olduğunca yapmalısınız. İkinci görev daha az önemlidir ve yalnızca kullanıcı girişinde uzun bir duraklama olduğunda yapılmalıdır. 'nin taban sınıf sürümüne `OnIdle`yapılan çağrıya dikkat edin. İkinci örnek, farklı önceliklere sahip boşta kalan bir görev grubunu yönetir.

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

## <a name="cwinappopendocumentfile"></a><a name="opendocumentfile"></a>CwinApp::OpenDocumentFile

Çerçeve, uygulama için adlandırılmış [CDocument](../../mfc/reference/cdocument-class.md) dosyasını açmak için bu yöntemi çağırır.

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
[içinde] Açılacak dosyanın adı.

*bAddToMRU*<br/>
[içinde] TRUE, belgenin en son dosyalardan biri olduğunu gösterir; FALSE, belgenin en son dosyalardan biri olmadığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CDocument` için bir işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu ada sahip bir belge zaten açıksa, bu belgeyi içeren ilk çerçeve penceresi odağı alır. Bir uygulama birden çok belge şablonu destekliyorsa, çerçeve belgeyi yüklemeye çalışmak için uygun belge şablonunu bulmak için dosya adı uzantısını kullanır. Başarılı olursa, belge şablonu belge için bir çerçeve penceresi ve görünüm oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

## <a name="cwinappparsecommandline"></a><a name="parsecommandline"></a>CWinApp::ParseCommandLine

Komut satırını ayrışdırmak ve parametreleri teker teker [CCommandLineInfo::ParseParam'e](../../mfc/reference/ccommandlineinfo-class.md#parseparam)göndermek için bu üye işlevini arayın.

```
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Parametreler

*rCmdInfo*<br/>
[CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Uygulama Sihirbazı'nı kullanarak yeni bir MFC projesi başlattığınızda, `CCommandLineInfo`Uygulama Sihirbazı `ProcessShellCommand` `ParseCommandLine` yerel bir örneği oluşturur ve ardından [initInstance](#initinstance) üye işlevinde çağırır. Bir komut satırı aşağıda açıklanan yolu izler:

1. Oluşturulduktan sonra `InitInstance`, `CCommandLineInfo` nesne `ParseCommandLine`ye geçirilir.

2. `ParseCommandLine`sonra `CCommandLineInfo::ParseParam` her parametre için bir kez, tekrar tekrar çağırır.

3. `ParseParam``CCommandLineInfo` sonra [ProcessShellCommand](#processshellcommand)geçirilir nesne, doldurur.

4. `ProcessShellCommand`komut satırı bağımsız değişkenlerini ve bayraklarını işler.

Gerektiğinde doğrudan arayabilirsiniz `ParseCommandLine` unutmayın.

Komut satırı bayraklarının açıklaması için [CCommandLineInfo::m_nShellCommand'](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)e bakın.

## <a name="cwinapppretranslatemessage"></a><a name="pretranslatemessage"></a>CWinApp::PreTranslateMessage

Windows işlevleriNe gönderilmeden önce pencere iletilerini filtrelemek için bu işlevi geçersiz kılın [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Varsayılan `CWinApp::PreTranslateMessage` uygulama hızlandırıcı anahtar çevirisi gerçekleştirir, bu nedenle geçersiz kılınan sürümdeki üye işlevi aramanız gerekir.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
İşletilen iletiyi içeren bir [MSG](/windows/win32/api/winuser/ns-winuser-msg) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti tam olarak `PreTranslateMessage` işlenmişse ve daha fazla işlenmemeliyse sıfıra inmez. İleti normal şekilde işlenirse sıfır.

## <a name="cwinappprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinApp::ProcessMessageFilter

Framework'ün kanca işlevi, belirli Windows iletilerini filtrelemek ve bunlara yanıt vermek için bu üye işlevi çağırır.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*Kod*<br/>
Bir kanca kodu belirtir. Bu üye işlev *lpMsg* nasıl işlenir belirlemek için kodu kullanır.

*lpMsg*<br/>
Windows [MSG](/windows/win32/api/winuser/ns-winuser-msg)tructure için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kanca işlevi, uygulamanın normal ileti işlemesine gönderilmeden önce olayları işler.

Bu gelişmiş özelliği geçersiz kılarsanız, çerçevenin kanca işlemesini sürdürmek için taban sınıf sürümünü aradığından emin olun.

## <a name="cwinappprocessshellcommand"></a><a name="processshellcommand"></a>CWinApp::ProcessShellCommand

Bu üye işlev, *rCmdInfo*tarafından tanımlanan `CCommandLineInfo` nesneden geçirilen parametreleri kabul etmek ve belirtilen eylemi gerçekleştirmek için [InitInstance](#initinstance) tarafından çağrılır.

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Parametreler

*rCmdInfo*<br/>
[CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Kabuk komutu başarıyla işlenirse sıfıra inme. 0 ise, [InitInstance'dan](#initinstance)FALSE'u döndürün.

### <a name="remarks"></a>Açıklamalar

Uygulama Sihirbazı'nı kullanarak yeni bir MFC projesi başlattığınızda, `CCommandLineInfo`Uygulama Sihirbazı `ProcessShellCommand` `InitInstance` üye işlevinde yerel bir ', ve sonra çağrı ve [ParseCommandLine'ı](#parsecommandline) oluşturur. Bir komut satırı aşağıda açıklanan yolu izler:

1. Oluşturulduktan sonra `InitInstance`, `CCommandLineInfo` nesne `ParseCommandLine`ye geçirilir.

2. `ParseCommandLine`sonra [ccommandLineInfo::ParseParam'i](../../mfc/reference/ccommandlineinfo-class.md#parseparam) tekrar tekrar, her parametre için bir kez arar.

3. `ParseParam`sonra ' `CCommandLineInfo` ya geçirilen nesneyi `ProcessShellCommand`doldurur.

4. `ProcessShellCommand`komut satırı bağımsız değişkenlerini ve bayraklarını işler.

[CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)tarafından tanımlanan `CCommandLineInfo` `CCommandLineInfo` nesnenin veri üyeleri, sınıf içinde tanımlanan aşağıdaki numaralandırılmış türlerdir.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };
```

Bu değerlerin her birinin kısa bir `CCommandLineInfo::m_nShellCommand`açıklaması için bkz.

## <a name="cwinappprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinApp::ProcessWndProcException

Çerçeve, işleyici, uygulamanızın iletisindeki veya komut işleyicilerinden birine atılan bir özel durum yakalamadığında bu üye işlevi çağırır.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*E*<br/>
Yakalanmamış bir özel durum için bir işaretçi.

*pMsg*<br/>
Çerçevenin özel durum atmasını sağlayan windows iletisi hakkında bilgi içeren bir [MSG](/windows/win32/api/winuser/ns-winuser-msg)tructure.

### <a name="return-value"></a>Dönüş Değeri

Windows'a döndürülmesi gereken değer. Normalde bu windows iletileri için 0L, komut iletileri için 1L (TRUE).

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi doğrudan aramayın.

Bu üye işlevin varsayılan uygulaması bir ileti kutusu oluşturur. Yakalanmamış özel durum bir menü, araç çubuğu veya hızlandırıcı komut uyruğu ndan kaynaklanıyorsa, ileti kutusu "Komut başarısız oldu" iletisi görüntüler; aksi takdirde, bir "İç uygulama hatası" iletisi görüntüler.

Özel durumlarınızın genel olarak işlenmesini sağlamak için bu üye işlevini geçersiz kılın. İleti kutusunun görüntülenmesini istiyorsanız yalnızca temel işlevselliği arayın.

## <a name="cwinappregister"></a><a name="register"></a>CwinApp::Kayıt Ol

`RegisterShellFileTypes`Tarafından işlenmemiş tüm kayıt görevlerini gerçekleştirir.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız başarı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama sadece TRUE döndürür. Özelleştirilmiş kayıt adımları sağlamak için bu işlevi geçersiz kılın.

## <a name="cwinappregistershellfiletypes"></a><a name="registershellfiletypes"></a>Cwinapp:RegisterShellFileTypes

Uygulamanızın tüm belge türlerini Windows Dosya Yöneticisi'ne kaydetmek için bu üye işlevini arayın.

```
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>Parametreler

*bCompat*<br/>
[içinde] TRUE, kullanıcının dosyaları doğrudan kabuktan yazdırmasına veya dosyayı bir yazıcı nesnesine sürükleyerek yazdırma komutları için kayıt girişleri ekler. Ayrıca bir DefaultIcon tuşu ekler. Varsayılan olarak, bu parametre geriye dönük uyumluluk için FALSE'dur.

### <a name="remarks"></a>Açıklamalar

Bu, kullanıcının Dosya Yöneticisi'nin içinden çift tıklayarak uygulamanız tarafından oluşturulan bir veri dosyasını açmasına olanak tanır. Uygulamanızdaki belge şablonlarının her biri için `RegisterShellFileTypes` [AddDocTemplate'i](#adddoctemplate) aradıktan sonra arayın. Ayrıca aradiğinizde [EnableShellOpen](#enableshellopen) üye `RegisterShellFileTypes`işlevini de arayın.

`RegisterShellFileTypes`uygulamanın koruduğu [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesneleri listesinden geçer ve her belge şablonu için Windows'un dosya ilişkilendirmeleri için koruduğu kayıt veritabanına girişler ekler. Dosya Yöneticisi, kullanıcı iki kez tıkladığında bir veri dosyasını açmak için bu girişleri kullanır. Bu bir gemi ihtiyacını ortadan kaldırır . Başvurunuzla birlikte REG dosyası.

> [!NOTE]
> `RegisterShellFileTypes`yalnızca kullanıcı programı yönetici haklarıyla çalıştırıyorsa çalışır. Programın yönetici hakları yoksa, kayıt defteri anahtarlarını değiştiremez.

Kayıt veritabanı zaten belirli bir dosya adı uzantısını başka bir dosya türüyle ilişkilendirmişse, yeni bir ilişkilendirme oluşturulmaz. Bu `CDocTemplate` bilgileri kaydetmek için gereken dizeleri biçimi için sınıfa bakın.

## <a name="cwinappregisterwithrestartmanager"></a><a name="registerwithrestartmanager"></a>CWinApp::RegisterWithRestartManager

Uygulamayı yeniden başlatma yöneticisine kaydeder.

```
virtual HRESULT RegisterWithRestartManager(
    BOOL bRegisterRecoveryCallback,
    const CString& strRestartIdentifier);

virtual HRESULT RegisterWithRestartManager(
    LPCWSTR pwzCommandLineArgs,
    DWORD dwRestartFlags,
    APPLICATION_RECOVERY_CALLBACK pRecoveryCallback,
    LPVOID lpvParam,
    DWORD dwPingInterval,
    DWORD dwCallbackFlags);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*bRegisterRecoveryCallback*|[içinde] TRUE, uygulamanın bu örneğinin bir kurtarma geri arama işlevi kullandığını gösterir; FALSE olmadığını gösterir. Uygulama beklenmedik bir şekilde çıktığında, çerçeve kurtarma geri arama işlevini çağırır. Daha fazla bilgi için [Bkz. CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*strRestartIdentifier*|[içinde] Yeniden başlatma yöneticisinin bu örneğini tanımlayan benzersiz dize. Yeniden başlatma yöneticisi tanımlayıcısı, bir uygulamanın her örneği için benzersizdir.|
|*pwzCommandLineArgs*|[içinde] Komut satırından herhangi bir ekstra bağımsız değişken içeren bir dize.|
|*dwRestartBayraklar*|[içinde] Yeniden başlatma yöneticisi için isteğe bağlı bayraklar. Daha fazla bilgi için Açıklamalar bölümüne bakın.|
|*pRecoveryCallback*|[içinde] Kurtarma geri arama işlevi. Bu işlev, giriş olarak bir LPVOID parametresi almalı ve bir DWORD döndürmelidir. Varsayılan kurtarma geri arama `CWinApp::ApplicationRecoveryCallback`işlevi.|
|*lpvParam*|[içinde] Kurtarma geri arama işlevi için giriş parametresi. Daha fazla bilgi için [Bkz. CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*dwPingInterval*|[içinde] Yeniden başlatma yöneticisinin kurtarma geri çağırma işlevinin dönmesini beklediği süre. Bu parametre milisaniye cinsindendir.|
|*dwCallbackBayraklar*|[içinde] Kurtarma geri arama işlevine geçirilen bayraklar. Daha sonraki kullanımlar için ayrılmıştır.|

### <a name="return-value"></a>Dönüş Değeri

yöntem başarılı olursa S_OK; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

Uygulamanız dosyaları otomatik kaydetmek için varsayılan MFC uygulamasını kullanıyorsa, `RegisterWithRestartManager`'nin basit sürümünü kullanmalısınız. Uygulamanızın otomatik `RegisterWithRestartManager` kaydetme davranışını özelleştirmek istiyorsanız karmaşık sürümünü kullanın.

Bu yöntemi *strRestartIdentifier*için boş bir `RegisterWithRestartManager` dize ile çağırırsanız, yeniden başlatma yöneticisinin bu örneği için benzersiz bir tanımlayıcı dize oluşturur.

Bir uygulama beklenmeyen bir şekilde çıktığında, yeniden başlat yöneticisi uygulamayı komut satırından yeniden başlatır ve isteğe bağlı bağımsız değişken olarak benzersiz yeniden başlatma tanımlayıcısını sağlar. Bu senaryoda, çerçeve `RegisterWithRestartManager` iki kez çağırır. İlk arama [CWinApp'tan geliyor::InitInstance](#initinstance) dize tanımlayıcısı için boş bir dize ile. Daha sonra, yöntem [CWinApp::ProcessShellCommand](#processshellcommand) benzersiz yeniden başlatma tanımlayıcısı ile çağırır. `RegisterWithRestartManager`

Bir uygulamayı yeniden başlatma yöneticisine kaydettirdikten sonra, yeniden başlatma yöneticisi uygulamayı izler. Uygulama beklenmeyen bir şekilde çıkarsa, yeniden başlatma yöneticisi kapatma işlemi sırasında kurtarma geri arama işlevini çağırır. Yeniden başlatma yöneticisi kurtarma geri arama işlevinden bir yanıt için *dwPingInterval* bekler. Kurtarma geri arama işlevi bu süre içinde yanıt vermezse, uygulama kurtarma geri arama işlevini yürütmeden çıkar.

Varsayılan olarak, dwRestartFlags desteklenmez, ancak gelecekteki kullanım için sağlanır. *dwRestartFlags* için olası değerler aşağıdaki gibidir:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

## <a name="cwinappreopenpreviousfilesatrestart"></a><a name="reopenpreviousfilesatrestart"></a>CWinApp::YenidenAçmaPreviousFilesAtRestart

Uygulama beklenmedik bir şekilde çıktığında yeniden başlat yöneticisinin açık olan dosyaları yeniden açıp açmadığını belirler.

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma yöneticisinin daha önce açılmış dosyaları yeniden açtığını gösterir; FALSE, yeniden başlatma yöneticisinin olmadığını gösterir.

## <a name="cwinapprestartinstance"></a><a name="restartinstance"></a>CWinApp::RestartInstance

Yeniden başlatma yöneticisi tarafından başlatılan bir uygulama yeniden başlatılır.

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Veri kurtarma işleyicisi daha önce açık belgeleri açarsa DOĞRU; Veri kurtarma işleyicisi bir hata varsa veya daha önce açık belgeler yoksa FALSE.

### <a name="remarks"></a>Açıklamalar

Yeniden başlat yöneticisi bir uygulamayı yeniden başlattığında, çerçeve bu yöntemi çağırır. Bu yöntem veri kurtarma işleyicisini alır ve otomatik olarak kaydedilen dosyaları geri yükler. Bu yöntem, kullanıcının otomatik olarak kaydedilen dosyaları geri yüklemek isteyip istemediğini belirlemek için [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) çağırır.

[CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) açık belge olmadığını belirlerse bu yöntem FALSE döndürür. Açık belge yoksa, başvuru normalde başlar.

## <a name="cwinapprestoreautosavedfilesatrestart"></a><a name="restoreautosavedfilesatrestart"></a>CWinApp::RestoreAutosavedFilesAtRestart

Uygulamayı yeniden başlatTığında yeniden başlat yöneticisinin otomatik olarak kaydedilen dosyaları geri yükleyip geri yüklemediğini belirler.

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma yöneticisinin otomatik olarak kaydedilen dosyaları geri yüklemediğini gösterir; FALSE, yeniden başlatma yöneticisinin olmadığını gösterir.

## <a name="cwinapprun"></a><a name="run"></a>CwinApp::Çalıştır

Varsayılan ileti döngüsü sağlar.

```
virtual int Run();
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından döndürülen **bir int** değeri `WinMain`

### <a name="remarks"></a>Açıklamalar

`Run`uygulama WM_QUIT bir ileti alana kadar Windows iletilerini alır ve gönderir. Uygulamanın ileti kuyruğunda şu anda `Run` ileti yoksa, [OnIdle'ı](#onidle) boşta zamanlı işleme gerçekleştirmeye çağırır. Gelen iletiler özel işleme için [PreTranslateMessage](#pretranslatemessage) üye işlevine ve `TranslateMessage` standart klavye çevirisi için Windows işlevine gider; son olarak, `DispatchMessage` Windows işlevi çağrılır.

`Run`nadiren geçersiz kılındı, ancak özel davranış sağlamak için geçersiz kılabilir.

## <a name="cwinapprunautomated"></a><a name="runautomated"></a>CwinApp::RunAutomated

Sunucu uygulamasının bir istemci uygulaması tarafından başlatılıp başlatılmadığını gösteren " **/Automation**" veya " **-Automation**" seçeneğinin mevcut olup olmadığını belirlemek için bu işlevi arayın.

```
BOOL RunAutomated();
```

### <a name="return-value"></a>Dönüş Değeri

Seçenek bulunursa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsa, seçenek komut satırından kaldırılır. OLE Automation hakkında daha fazla bilgi için [Otomasyon Sunucuları](../../mfc/automation-servers.md)makalesine bakın.

## <a name="cwinapprunembedded"></a><a name="runembedded"></a>Cwinapp::RunEmbedded

Sunucu uygulamasının istemci uygulaması tarafından başlatılıp başlatılmadığını gösteren " **/Embedding**" veya " **-Embedding**" seçeneğinin mevcut olup olmadığını belirlemek için bu işlevi arayın.

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>Dönüş Değeri

Seçenek bulunursa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsa, seçenek komut satırından kaldırılır. Gömme hakkında daha fazla bilgi için, makale [Sunucuları bakın: Bir Sunucu uygulama.](../../mfc/servers-implementing-a-server.md)

## <a name="cwinappsaveallmodified"></a><a name="saveallmodified"></a>Cwinapp::SaveAllModi

Uygulamanın ana çerçeve penceresi kapatıldığında veya WM_QUERYENDSESSION bir ileti aracılığıyla tüm belgeleri kaydetmek için çerçeve tarafından çağrılır.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamayı sonlandırmak için güvenli ise sıfır olmayan; 0 uygulamayı sonlandırmak için güvenli değilse.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin varsayılan uygulaması, uygulama daki tüm değiştirilmiş belgeler için sırayla [CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified) üye işlevini çağırır.

## <a name="cwinappselectprinter"></a><a name="selectprinter"></a>CwinApp::Selectprinter

Belirli bir yazıcı seçmek ve daha önce Yazdır İletişim kutusunda seçilen yazıcıyı serbest bırakmak için bu üye işlevi arayın.

```
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>Parametreler

*hDevNames*<br/>
Belirli bir yazıcının sürücü, aygıt ve çıkış bağlantı noktası adlarını tanımlayan [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)tructure için bir tutamaç.

*hDevMode*<br/>
Aygıt başlatma ve yazıcının ortamı hakkında bilgi belirten [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) yapısının tutamacı.

*bFreeOld*<br/>
Daha önce seçili yazıcıyı serbest sağlar.

### <a name="remarks"></a>Açıklamalar

Hem *hDevMode* hem de *hDevNames* NULL ise, `SelectPrinter` geçerli varsayılan yazıcıyı kullanır.

## <a name="cwinappsethelpmode"></a><a name="sethelpmode"></a>Cwinapp:SetHelpMode

Uygulamanın yardım türünü ayarlar.

```
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>Parametreler

*eHelpType*<br/>
Kullanılacak yardım türünü belirtir. Daha fazla bilgi için [CWinApp::m_eHelpType'a](#m_ehelptype) bakın.

### <a name="remarks"></a>Açıklamalar

Uygulamanın Yardım türünü ayarlar.

Uygulamanızın Yardım türünü HTMLHelp olarak ayarlamak için [EnableHTMLHelp'i](#enablehtmlhelp)arayabilirsiniz. Bir kez `EnableHTMLHelp`aradıktan sonra, uygulamanız yardım uygulaması olarak HTMLHelp kullanmanız gerekir. WinHelp'i kullanmak için değiştirmek istiyorsanız, `SetHelpMode` *eHelpType'ı* arayabilir ve `afxWinHelp`ayarlayabilirsiniz.

## <a name="cwinappsetregistrykey"></a><a name="setregistrykey"></a>CWinApp::SetRegistryKey

Uygulama ayarlarının INI dosyaları yerine kayıt defterinde depolanabılmasına neden olur.

```
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>Parametreler

*lpszRegistryKey*<br/>
Anahtarın adını içeren bir dize işaretçi.

*nIDRegistryKey*<br/>
Kayıt defteri anahtarının adını içeren bir dize kaynağının kimliği.

### <a name="remarks"></a>Açıklamalar

Bu *işlev, m_pszRegistryKey*ayarlar , `GetProfileInt`daha `GetProfileString` `WriteProfileInt`sonra `WriteProfileString` tarafından kullanılan `CWinApp`, , , ve üye işlevleri . Bu işlev çağrıldıysa, en son kullanılan (MRU) dosyaların listesi de kayıt defterinde depolanır. Kayıt defteri anahtarı genellikle bir şirketin adıdır. Aşağıdaki formun bir anahtar saklanır: HKEY_CURRENT_USER\Yazılım\\<\> \\ şirket adı\> \\<\> \\ uygulama adı\><bölüm adı<değer adı .

## <a name="cwinappsupportsapplicationrecovery"></a><a name="supportsapplicationrecovery"></a>CwinApp::SupportsApplicationRecovery

Yeniden başlatma yöneticisinin beklenmeyen bir şekilde çıkan bir uygulamayı kurtarıp kurtarmayacağını belirler.

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma yöneticisinin uygulamayı kurtartAiçlarını gösterir; FALSE, yeniden başlatma yöneticisinin olmadığını gösterir.

## <a name="cwinappsupportsautosaveatinterval"></a><a name="supportsautosaveatinterval"></a>CWinApp::DesteklerAutosaveAtInterval

Yeniden başlatma yöneticisinin açık belgeleri düzenli aralıklarla otomatik olarak kaydedip kaydetmediğini belirler.

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma yöneticisinin açık belgeleri otomatik olarak kaydedin; FALSE, yeniden başlatma yöneticisinin olmadığını gösterir.

## <a name="cwinappsupportsautosaveatrestart"></a><a name="supportsautosaveatrestart"></a>CWinApp::DesteklerAutosaveAtRestart

Uygulama yeniden başlatıldığında yeniden başlatma yöneticisinin açık belgeleri otomatik olarak kaydedip kaydetmediğini belirler.

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, uygulama yeniden başlatıldığında yeniden başlatma yöneticisinin açık belgeleri otomatik olarak kaydettiğinden; FALSE, yeniden başlatma yöneticisinin olmadığını gösterir.

## <a name="cwinappsupportsrestartmanager"></a><a name="supportsrestartmanager"></a>CWinApp::SupportsRestartManager

Uygulamanın yeniden başlatma yöneticisini destekleyip desteklemediğini belirler.

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, uygulamanın yeniden başlatma yöneticisini desteklediğini gösterir; FALSE, uygulamanın uygulamaolmadığını gösterir.

## <a name="cwinappunregister"></a><a name="unregister"></a>CWinApp::Kayıt Dışı

Uygulama nesnesi tarafından kayıtlı tüm dosyaların kaydını boşaltıyor.

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız başarı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlev, `Unregister` uygulama nesnesi ve [Kayıt](#register) işlevi tarafından gerçekleştirilen kaydı geri getirir. Normalde, her iki işlev de MFC tarafından dolaylı olarak çağrılır ve bu nedenle kodunuzda görünmez.

Özel kayıt dışı adımlar gerçekleştirmek için bu işlevi geçersiz kılın.

## <a name="cwinappunregistershellfiletypes"></a><a name="unregistershellfiletypes"></a>CWinApp::Kayıt DışıShellFileTypes

Uygulamanızın tüm belge türlerinin Windows Dosya Yöneticisi'ne kaydını açmak için bu üye işlevini arayın.

```
void UnregisterShellFileTypes();
```

## <a name="cwinappwinhelp"></a><a name="winhelp"></a>Cwinapp::WinHelp

WinHelp uygulamasını çağırmak için bu üye işlevini arayın.

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>Parametreler

*Dwdata*<br/>
Ek veriler belirtir. Kullanılan değer *nCmd* parametresinin değerine bağlıdır.

*nCmd*<br/>
İstenen yardım türünü belirtir. Olası değerlerin listesi ve *bunların dwData* parametresini nasıl etkilediği için [WinHelp](/windows/win32/api/winuser/nf-winuser-winhelpw) Windows işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Çerçeve ayrıca WinHelp uygulamasını çağırmak için bu işlevi çağırır.

Çerçeve, başvurunuz sona erdiğinde WinHelp uygulamasını otomatik olarak kapatır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

## <a name="cwinappwriteprofilebinary"></a><a name="writeprofilebinary"></a>CwinApp::WriteProfileBinary

Bu üye işlevi arayarak, uygulamanın kayıt defterinin belirtilen bölümüne ikili veri yazmaveya . INI dosyası.

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>Parametreler

*lpszBölüm*<br/>
Girişi içeren bölümü belirten null-sonlandırılan dizeyi işaret eder. Bölüm yoksa, oluşturulur. Bölümün adı büyük/küçük harften bağımsızdır; dize büyük harf ve küçük harflerin herhangi bir kombinasyonu olabilir.

*lpszEntry*<br/>
Değerin yazılmak üzere giridebini içeren null-sonlandırılan dizeyi işaret ediyor. Giriş belirtilen bölümde yoksa, oluşturulur.

*Pdata*<br/>
Yazılacak verilere işaret edin.

*nBayt*<br/>
Yazılacak bayt sayısını içerir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

Bu örnek, Bir MFC uygulamasındaki herhangi bir `WriteProfileBinary` `GetProfileBinary` işlevden kullanılabilen bir yolu gösteren CWinApp sınıfına girmek için kullanılır. `CWinApp* pApp = AfxGetApp();`

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

Başka bir örnek için, CWinApp örneğine [bakın:GetProfileBinary.](#getprofilebinary)

## <a name="cwinappwriteprofileint"></a><a name="writeprofileint"></a>CWinApp::WriteProfileInt

Belirtilen değeri uygulamanın kayıt defterinin belirtilen bölümüne yazmak için bu üye işlevini arayın veya . INI dosyası.

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>Parametreler

*lpszBölüm*<br/>
Girişi içeren bölümü belirten null-sonlandırılan dizeyi işaret eder. Bölüm yoksa, oluşturulur. Bölümün adı büyük/küçük harften bağımsızdır; dize büyük harf ve küçük harflerin herhangi bir kombinasyonu olabilir.

*lpszEntry*<br/>
Değerin yazılmak üzere giridebini içeren null-sonlandırılan dizeyi işaret ediyor. Giriş belirtilen bölümde yoksa, oluşturulur.

*nDeğer*<br/>
Yazılacak değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

Bu örnek, Bir MFC uygulamasındaki herhangi bir `WriteProfileString` `WriteProfileInt`işlevden kullanılabilen ve `GetProfileString` `GetProfileInt` kullanılabilen bir yolu gösteren CWinApp sınıfına girmek için kullanılır. `CWinApp* pApp = AfxGetApp();`

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Başka bir örnek için, CWinApp örneğine [bakın::GetProfileInt](#getprofileint).

## <a name="cwinappwriteprofilestring"></a><a name="writeprofilestring"></a>CwinApp::WriteProfileString

Belirtilen dizeyi uygulamanın kayıt defterinin belirtilen bölümüne yazmak için bu üye işlevi arayın veya . INI dosyası.

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>Parametreler

*lpszBölüm*<br/>
Girişi içeren bölümü belirten null-sonlandırılan dizeyi işaret eder. Bölüm yoksa, oluşturulur. Bölümün adı büyük/küçük harften bağımsızdır; dize büyük harf ve küçük harflerin herhangi bir kombinasyonu olabilir.

*lpszEntry*<br/>
Değerin yazılmak üzere giridebini içeren null-sonlandırılan dizeyi işaret ediyor. Giriş belirtilen bölümde yoksa, oluşturulur. Bu parametre NULL ise *lpszSection* tarafından belirtilen bölüm silinir.

*lpszValue*<br/>
Yazılacak dizeyi işaret edin. Bu parametre NULL ise, *lpszEntry* parametresi tarafından belirtilen giriş silinir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Başka bir örnek için, CWinApp örneğine [bakın::GetProfileInt](#getprofileint).

## <a name="cwinappsetappid"></a><a name="setappid"></a>CwinApp:SetAppID

Uygulama için Uygulama Kullanıcı Modeli Kimliğini açıkça ayarlar. Bu yöntem, herhangi bir kullanıcı arabirimi kullanıcıya sunulmadan önce çağrılmalıdır (en iyi yer uygulama oluşturucusudur).

```
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>Parametreler

*lpcszAppID*<br/>
Uygulama Kullanıcı Modeli Kimliğini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[CWinThread Sınıfı](../../mfc/reference/cwinthread-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme](../../mfc/how-to-add-restart-manager-support.md)
