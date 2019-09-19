---
title: CWinApp sınıfı
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
ms.openlocfilehash: e65ad8b5d8b14ff747adc55b517d9e695d9cbb66
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095747"
---
# <a name="cwinapp-class"></a>CWinApp sınıfı

Windows uygulama nesnesini türettiğiniz temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CWinApp : public CWinThread
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWinApp:: CWinApp](#cwinapp)|Bir `CWinApp` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinApp:: AddDocTemplate](#adddoctemplate)|Uygulamanın kullanılabilir belge şablonları listesine bir belge şablonu ekler.|
|[CWinApp:: AddToRecentFileList](#addtorecentfilelist)|En son kullanılan (MRU) dosya listesine bir dosya adı ekler.|
|[CWinApp:: ApplicationRecoveryCallback](#applicationrecoverycallback)|Uygulama beklenmedik şekilde çıkıldığında Framework tarafından çağırılır.|
|[CWinApp:: CloseAllDocuments](#closealldocuments)|Tüm açık belgeleri kapatır.|
|[CWinApp:: CreatePrinterDC](#createprinterdc)|Bir yazıcı cihaz bağlamı oluşturur.|
|[CWinApp::D elRegTree](#delregtree)|Belirtilen bir anahtarı ve tüm alt anahtarlarını siler.|
|[CWinApp::D oMessageBox](#domessagebox)|Uygulama için [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) uygular.|
|[CWinApp::D oWaitCursor](#dowaitcursor)|Bekleme imlecini açar ve kapatır.|
|[CWinApp:: EnableD2DSupport](#enabled2dsupport)|Uygulama D2D desteğini sunar. Ana pencere başlatılmadan önce bu yöntemi çağırın.|
|[CWinApp:: EnableHtmlHelp](#enablehtmlhelp)|Uygulama için WinHelp yerine HTMLHelp uygular.|
|[CWinApp:: enabletaskbarınter](#enabletaskbarinteraction)|Görev çubuğu etkileşimini izin vermez.|
|[CWinApp:: ExitInstance](#exitinstance)|Uygulamanız sonlandırıldığında temizlemek için geçersiz kılın.|
|[CWinApp:: GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|Uygulama kurtarma yönteminin giriş parametresini alır.|
|[CWinApp:: GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Yeniden başlatma yöneticisinin kurtarma geri çağırma işlevinin döndürmesini bekleyeceği sürenin uzunluğunu döndürür.|
|[CWinApp:: GetApplicationRestartFlags](#getapplicationrestartflags)|Yeniden başlatma yöneticisinin bayraklarını döndürür.|
|[CWinApp:: GetAppRegistryKey](#getappregistrykey)|HKEY_CURRENT_USER\\"Software" \RegistryKey\ProfileName. için anahtar döndürür|
|[CWinApp:: GetDataRecoveryHandler](#getdatarecoveryhandler)|Uygulamanın bu örneği için veri kurtarma işleyicisini alır.|
|[CWinApp:: GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|İlk belge şablonunun konumunu alır.|
|[CWinApp:: GetHelpMode](#gethelpmode)|Uygulama tarafından kullanılan yardım türünü alır.|
|[CWinApp:: GetNextDocTemplate](#getnextdoctemplate)|Belge şablonunun konumunu alır. Yinelemeli olarak kullanılabilir.|
|[CWinApp:: GetPrinterDeviceDefaults](#getprinterdevicedefaults)|Yazıcı cihazının varsayılan değerlerini alır.|
|[CWinApp:: GetProfileBinary](#getprofilebinary)|Uygulamanın içindeki bir girdiden ikili verileri alır. INı dosyası.|
|[CWinApp:: GetProfileInt](#getprofileint)|Uygulamanın içindeki bir girdiden bir tamsayı alır. INı dosyası.|
|[CWinApp:: GetProfileString](#getprofilestring)|Uygulamanın içindeki bir girdiden bir dize alır. INı dosyası.|
|[CWinApp:: GetSectionKey](#getsectionkey)|HKEY_CURRENT_USER\\"Software" \RegistryKey\AppName\lpszSection. için anahtar döndürür|
|[CWinApp:: HideApplication](#hideapplication)|Tüm belgeleri kapatmadan önce uygulamayı gizler.|
|[CWinApp:: HtmlHelp](#htmlhelp)|`HTMLHelp` Windows işlevini çağırır.|
|[CWinApp:: InitInstance](#initinstance)|Pencere nesnelerinizi oluşturma gibi Windows örnek başlatmayı gerçekleştirmek için geçersiz kılın.|
|[CWinApp:: Istaskbarınteractionenabled](#istaskbarinteractionenabled)|Windows 7 görev çubuğu etkileşiminin etkinleştirilip etkinleştirilmeyeceğini belirtir.|
|[CWinApp:: LoadCursor](#loadcursor)|Bir imleç kaynağı yükler.|
|[CWinApp:: LoadIcon](#loadicon)|Bir simge kaynağı yükler.|
|[CWinApp:: LoadOEMCursor](#loadoemcursor)|**OCR_** sabitlerinin Windows 'da belirtdiği BIR Windows OEM önceden tanımlı imleç yükler. Olsun.|
|[CWinApp:: LoadOEMIcon](#loadoemicon)|**OIC_** sabitlerinin Windows 'da belirtilerinin önceden tanımlanmış BIR Windows OEM simgesini yükler. Olsun.|
|[CWinApp:: LoadStandardCursor](#loadstandardcursor)|**IDC_** sabitlerinin Windows 'da belirtdiği bir Windows önceden tanımlı imleç yükler. Olsun.|
|[CWinApp:: LoadStandardIcon](#loadstandardicon)|**IDI_** sabitlerinin Windows 'da belirtilerinin önceden tanımlanmış bir simgesini yükler. Olsun.|
|[CWinApp:: Ondalıklar Decommand](#onddecommand)|Dinamik veri değişimi (DDE) yürütme komutuna yanıt olarak Framework tarafından çağırılır.|
|[CWinApp:: OnIdle](#onidle)|Uygulamaya özgü boşta kalma süresi işlemini gerçekleştirmek için geçersiz kılın.|
|[CWinApp:: OpenDocumentFile](#opendocumentfile)|Bir dosyadan belge açmak için Framework tarafından çağırılır.|
|[CWinApp::P arseCommandLine](#parsecommandline)|Komut satırında bağımsız parametreleri ve bayrakları ayrıştırır.|
|[CWinApp::P reTranslateMessage](#pretranslatemessage)|İletileri, [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)Windows işlevlerine dağıtılmadan önce filtreler.|
|[CWinApp::P rocessMessageFilter](#processmessagefilter)|Uygulamaya ulaşmadan önce belirli iletileri keser.|
|[CWinApp::P rocessShellCommand](#processshellcommand)|Komut satırı bağımsız değişkenlerini ve bayraklarını işler.|
|[CWinApp::P rocessWndProcException](#processwndprocexception)|Uygulamanın iletisi ve komut işleyicileri tarafından oluşturulan işlenmemiş özel durumları karşılar.|
|[CWinApp:: Register](#register)|Özelleştirilmiş kayıt gerçekleştirir.|
|[CWinApp:: RegisterWithRestartManager](#registerwithrestartmanager)|Uygulamayı yeniden başlatma yöneticisiyle kaydeder.|
|[CWinApp:: ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|Yeniden başlatma yöneticisinin, uygulamanın beklenmedik şekilde çıkıldığında açık olan dosyaları yeniden açıp açamayacağını belirler.|
|[CWinApp:: RestartInstance](#restartinstance)|Yeniden başlatma Yöneticisi tarafından başlatılan uygulama yeniden başlatmasını işler.|
|[CWinApp:: RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|Yeniden başlatma yöneticisinin uygulamayı yeniden başlattığında otomatik kaydedilen dosyaları geri yükleme olup olmadığını belirler.|
|[CWinApp:: Run](#run)|Varsayılan ileti döngüsünü çalıştırır. İleti döngüsünü özelleştirmek için geçersiz kılın.|
|[CWinApp:: RunAutomated](#runautomated)|**/Automation** seçeneği için uygulamanın komut satırını sınar. Kullanımdan kalktı. Bunun yerine, [ParseCommandLine](#parsecommandline)çağrıldıktan sonra [CCommandLineInfo:: m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) içindeki değeri kullanın.|
|[CWinApp:: RunEmbedded](#runembedded)|**/Katıştırma** seçeneği için uygulamanın komut satırını sınar. Kullanımdan kalktı. Bunun yerine, [ParseCommandLine](#parsecommandline)çağrıldıktan sonra [CCommandLineInfo:: m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) içindeki değeri kullanın.|
|[CWinApp:: SaveAllModified](#saveallmodified)|Kullanıcının tüm değiştirilen belgeleri kaydetmesini ister.|
|[CWinApp:: SelectPrinter](#selectprinter)|Daha önce bir Yazdır iletişim kutusu aracılığıyla Kullanıcı tarafından belirtilen bir yazıcı seçer.|
|[CWinApp:: SetHelpMode](#sethelpmode)|Uygulama tarafından kullanılan yardım türünü ayarlar ve başlatır.|
|[CWinApp:: SupportsApplicationRecovery](#supportsapplicationrecovery)|Yeniden başlatma yöneticisinin beklenmedik bir şekilde çıkıldı bir uygulamayı kurtarıp kurtarmayacağını belirler.|
|[CWinApp:: Supportsautosaveatınterval](#supportsautosaveatinterval)|Restart Manager 'ın açık belgeleri düzenli bir aralıkta yeniden kaydedip kaydetmediğini belirler.|
|[CWinApp:: SupportsAutosaveAtRestart](#supportsautosaveatrestart)|Yeniden başlatma Yöneticisi 'nin, uygulama yeniden başlatıldığında açık olan tüm belgeleri açıp kaydetmeyeceğini belirler.|
|[CWinApp:: SupportsRestartManager](#supportsrestartmanager)|Uygulamanın yeniden başlatma yöneticisini destekleyip desteklemediğini belirler.|
|[CWinApp:: Unregister](#unregister)|`CWinApp` Nesne tarafından kaydedilmesi bilinen her şeyin kaydını siler.|
|[CWinApp:: WinHelp](#winhelp)|`WinHelp` Windows işlevini çağırır.|
|[CWinApp:: WriteProfileBinary](#writeprofilebinary)|İkili verileri uygulama içindeki bir girdiye yazar. INı dosyası.|
|[CWinApp:: WriteProfileInt](#writeprofileint)|Uygulamanın içindeki bir girdiye bir tamsayı yazar. INı dosyası.|
|[CWinApp:: WriteProfileString](#writeprofilestring)|Uygulamanın içindeki bir girdiye bir dize yazar. INı dosyası.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinApp:: EnableShellOpen](#enableshellopen)|Kullanıcının Windows Dosya Yöneticisi 'nden veri dosyaları açmasına olanak sağlar.|
|[CWinApp:: LoadStdProfileSettings](#loadstdprofilesettings)|Standart yükler. INı dosyası ayarları ve MRU dosya listesi özelliğini etkinleştirilir.|
|[CWinApp:: OnContextHelp](#oncontexthelp)|Uygulama içinde SHIFT + F1 yardımını işler.|
|[CWinApp:: OnFileNew](#onfilenew)|ID_FILE_NEW komutunu uygular.|
|[CWinApp:: OnFileOpen](#onfileopen)|ID_FILE_OPEN komutunu uygular.|
|[CWinApp:: OnFilePrintSetup](#onfileprintsetup)|ID_FILE_PRINT_SETUP komutunu uygular.|
|[CWinApp:: OnHelp](#onhelp)|Uygulama içinde F1 yardımını işler (geçerli bağlamı kullanarak).|
|[CWinApp:: OnHelpFinder](#onhelpfinder)|ID_HELP_FINDER ve ID_DEFAULT_HELP komutlarını işler.|
|[CWinApp:: OnHelpIndex](#onhelpindex)|ID_HELP_INDEX komutunu işler ve varsayılan bir yardım konusu sağlar.|
|[CWinApp:: OnHelpUsing](#onhelpusing)|ID_HELP_USING komutunu işler.|
|[CWinApp:: RegisterShellFileTypes](#registershellfiletypes)|Tüm uygulamanın belge türlerini Windows Dosya Yöneticisi ile kaydeder.|
|[CWinApp:: Setappıd](#setappid)|Uygulamanın uygulama kullanıcı modeli KIMLIĞINI açık olarak ayarlar. Bu yöntem, Kullanıcı arabirimi kullanıcıya sunulmadan önce çağrılmalıdır (uygulama Oluşturucusu en iyi yer olur).|
|[CWinApp:: SetRegistryKey](#setregistrykey)|Uygulama ayarlarının yerine kayıt defterinde depolanmasına neden olur. INı dosyaları.|
|[CWinApp:: UnregisterShellFileTypes](#unregistershellfiletypes)|Windows Dosya Yöneticisi ile tüm uygulamanın belge türlerini siler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CWinApp:: m_bHelpMode](#m_bhelpmode)|Kullanıcının Yardım bağlam modunda olup olmadığını gösterir (genellikle SHIFT + F1 ile çağrılır).|
|[CWinApp:: m_eHelpType](#m_ehelptype)|Uygulama tarafından kullanılan yardım türünü belirtir.|
|[CWinApp:: m_hInstance](#m_hinstance)|Uygulamanın geçerli örneğini tanımlar.|
|[CWinApp:: m_lpCmdLine](#m_lpcmdline)|Uygulamanın komut satırını belirten, null ile sonlandırılmış bir dizeye işaret eder.|
|[CWinApp:: m_nCmdShow](#m_ncmdshow)|Pencerenin başlangıçta nasıl gösterileceğini belirtir.|
|[CWinApp:: m_pActiveWnd](#m_pactivewnd)|Bir OLE sunucusu yerinde etkin olduğunda kapsayıcı uygulamasının ana penceresine yönelik işaretçi.|
|[CWinApp:: m_pszAppID](#m_pszappid)|Uygulama kullanıcı modeli KIMLIĞI.|
|[CWinApp:: m_pszAppName](#m_pszappname)|Uygulamanın adını belirtir.|
|[CWinApp:: m_pszExeName](#m_pszexename)|Uygulamanın modül adı.|
|[CWinApp:: m_pszHelpFilePath](#m_pszhelpfilepath)|Uygulamanın Yardım dosyasının yolu.|
|[CWinApp:: m_pszProfileName](#m_pszprofilename)|Uygulamanın. INI dosya adı.|
|[CWinApp:: m_pszRegistryKey](#m_pszregistrykey)|Uygulama profili ayarlarını depolamaya yönelik tam kayıt defteri anahtarını belirlemede kullanılır.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CWinApp:: m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Yeniden başlatma yöneticisinin nasıl davranacağını belirleme bayrakları.|
|[CWinApp:: m_nAutosaveInterval](#m_nautosaveinterval)|Saniye cinsinden, oto kaydetme arasındaki süre uzunluğu.|
|[CWinApp:: m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Uygulama için veri kurtarma işleyicisine yönelik işaretçi.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama nesnesi, uygulamanızı (ve her örneğini) başlatmak için ve uygulamayı çalıştırmak için üye işlevleri sağlar.

Microsoft Foundation sınıfları kullanan her uygulama, öğesinden `CWinApp`türetilmiş bir nesne içerebilir. Bu nesne, diğer C++ genel nesneler oluşturulduğunda oluşturulur ve Windows, Microsoft Foundation Class Kitaplığı tarafından sağlanan `WinMain` işlevi çağırdığında zaten kullanılabilir. Türetilmiş `CWinApp` nesneniz genel düzeyde bildirin.

Öğesinden `CWinApp`bir uygulama sınıfı türettiğinizde, uygulamanızın ana pencere nesnesini oluşturmak için [InitInstance](#initinstance) üye işlevini geçersiz kılın.

`CWinApp` Üye işlevlerine ek olarak, Microsoft Foundation Class Kitaplığı `CWinApp` nesneniz ve diğer genel bilgilere erişmek için aşağıdaki genel işlevleri sağlar:

- [AfxGetApp](application-information-and-management.md#afxgetapp) `CWinApp` Nesnesine bir işaretçi alır.

- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) Geçerli uygulama örneğine bir tanıtıcı edinir.

- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) Uygulamanın kaynaklarına yönelik bir tanıtıcı edinir.

- [AfxGetAppName](application-information-and-management.md#afxgetappname) Uygulamanın adını içeren bir dize için bir işaretçi alır. Alternatif olarak, `CWinApp` nesne işaretçiniz varsa uygulamanın adını almak için kullanın `m_pszExeName` .

Bkz [. CWinApp: Aşağıdaki genel bir](../../mfc/cwinapp-the-application-class.md) bakış da dahil olmak `CWinApp` üzere sınıf üzerinde daha fazla için uygulama sınıfı:

- `CWinApp`-Uygulama Sihirbazı tarafından yazılan türetilmiş kod.

- `CWinApp`uygulamanızın yürütme dizisindeki rolü.

- `CWinApp`öğesinin varsayılan üye işlev uygulamaları.

- `CWinApp`öğesinin anahtar geçersiz kılınabilen.

`m_hPrevInstance` Veri üyesi artık yok. Uygulamanın başka bir örneğinin çalışıp çalışmadığını anlamak için adlandırılmış bir mutex kullanın. Mutex 'i açmak başarısız olursa uygulamanın başka bir örneği çalışır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="adddoctemplate"></a>CWinApp:: AddDocTemplate

Uygulamanın koruduğu kullanılabilir belge şablonlarının listesine bir belge şablonu eklemek için bu üye işlevi çağırın.

```
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>Parametreler

*pTemplate*<br/>
Eklenecek öğesine yönelik `CDocTemplate` bir işaretçi.

### <a name="remarks"></a>Açıklamalar

[RegisterShellFileTypes](#registershellfiletypes)çağrısı yapmadan önce tüm belge şablonlarını bir uygulamaya eklemelisiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

##  <a name="addtorecentfilelist"></a>CWinApp:: AddToRecentFileList

MRU dosya listesine *lpszPathName* eklemek için bu üye işlevi çağırın.

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Dosyanın yolu.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini kullanmadan önce geçerli MRU dosya listesini yüklemek için [LoadStdProfileSettings](#loadstdprofilesettings) üye işlevini çağırmanız gerekir.

Framework bir dosyayı açtığında bu üye işlevi çağırır veya dosyayı yeni bir adla kaydetmek için farklı Kaydet komutunu yürütür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

##  <a name="applicationrecoverycallback"></a>CWinApp:: ApplicationRecoveryCallback

Uygulama beklenmedik şekilde çıkıldığında Framework tarafından çağırılır.

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>Parametreler

*lpvParam*<br/>
'ndaki Gelecekte kullanılmak üzere ayrılmıştır.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa 0; bir hata oluşursa sıfır dışı.

### <a name="remarks"></a>Açıklamalar

Uygulamanız yeniden başlatma yöneticisini destekliyorsa, uygulamanız beklenmedik şekilde çıkış yaparken Framework bu işlevi çağırır.

Varsayılan uygulama `ApplicationRecoveryCallback` , `CDataRecoveryHandler` Şu anda açık olan belgelerin listesini kayıt defterine kaydetmek için kullanır. Bu yöntem hiçbir dosyayı otomatik olarak içermez.

Davranışı özelleştirmek için, türetilmiş bir [CWinApp sınıfında](../../mfc/reference/cwinapp-class.md) bu işlevi geçersiz kılın veya kendi uygulama kurtarma yönteminizi [CWinApp:: RegisterWithRestartManager](#registerwithrestartmanager)öğesine parametre olarak geçirin.

##  <a name="closealldocuments"></a>CWinApp:: CloseAllDocuments

Çıkmadan önce tüm açık belgeleri kapatmak için bu üye işlevi çağırın.

```
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Parametreler

*bEndSession*<br/>
Windows oturumunun sonlandırılmadığını belirtir. Oturumun sonlandırılması doğru olur; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`CloseAllDocuments`önce [HideApplication](#hideapplication) öğesini çağırın.

##  <a name="createprinterdc"></a>CWinApp:: CreatePrinterDC

Seçili yazıcıdan bir yazıcı cihaz bağlamı (DC) oluşturmak için bu üye işlevi çağırın.

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
Bir yazıcı cihaz bağlamına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yazıcı cihaz bağlamı başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CreatePrinterDC`başvuruya göre geçirdiğiniz cihaz bağlamını başlatır, böylece yazdırmak için kullanabilirsiniz.

İşlev başarılı olursa, yazdırmayı bitirdiğinizde cihaz bağlamını yok etmeniz gerekir. [CDC](../../mfc/reference/cdc-class.md) nesnesinin yıkıcısında bunu yapmasına izin verebilir veya [CDC::D eletedc](../../mfc/reference/cdc-class.md#deletedc)çağırarak bunu açıkça yapabilirsiniz.

##  <a name="cwinapp"></a>CWinApp:: CWinApp

Bir `CWinApp` nesne oluşturur ve uygulama adı olarak depolanacak *lpszAppName* geçirir.

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszAppName*<br/>
Windows 'un kullandığı uygulama adını içeren, null ile sonlandırılmış bir dize. Bu bağımsız değişken sağlanmazsa veya null ise, `CWinApp` AFX_IDS_APP_TITLE kaynak dizesini veya yürütülebilir dosyanın dosya adını kullanır.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıfınızın bir genel nesnesini `CWinApp`oluşturmanız gerekir. Uygulamanızda yalnızca bir `CWinApp` nesne olabilir. Oluşturucu `CWinApp` nesnesine`WinMain` bir işaretçi depolayarak uygulamayı başlatmak ve çalıştırmak için nesnenin üye işlevlerini çağırabilir.

##  <a name="delregtree"></a>CWinApp::D elRegTree

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
Kayıt defteri anahtarı için tanıtıcı.

*strKeyName*<br/>
Silinecek kayıt defteri anahtarının adı.

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS olur. İşlev başarısız olursa, dönüş değeri, Winerror. h içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Belirtilen anahtarı ve alt anahtarlarını silmek için bu işlevi çağırın.

##  <a name="domessagebox"></a>CWinApp::D oMessageBox

Framework, [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)genel işlevi için bir ileti kutusu uygulamak üzere bu üye işlevini çağırır.

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>Parametreler

*lpszPrompt*<br/>
İleti kutusundaki metnin adresi.

*nTür*<br/>
İleti kutusu [stili](../../mfc/reference/styles-used-by-mfc.md#message-box-styles).

*nIDPrompt*<br/>
Yardım bağlamı dizesinin dizini.

### <a name="return-value"></a>Dönüş Değeri

İle `AfxMessageBox`aynı değerleri döndürür.

### <a name="remarks"></a>Açıklamalar

İleti kutusu açmak için bu üye işlevini çağırmayın; Bunun `AfxMessageBox` yerine kullanın.

Uygulama genelinde `AfxMessageBox` çağrılarınızın işlenmesini özelleştirmek için bu üye işlevi geçersiz kılın.

##  <a name="dowaitcursor"></a>CWinApp::D oWaitCursor

Bu üye işlevi, [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget:: BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget:: EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)ve [CCmdTarget:: RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)öğesini uygulamak için çerçeve tarafından çağırılır.

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>Parametreler

*nCode*<br/>
Bu parametre 1 ise, bir bekleme imleci belirir. 0 ise, bekleme imleci başvuru sayısını arttırmadan geri yüklenir. -1 ise bekleme imleci sonlanır.

### <a name="remarks"></a>Açıklamalar

Varsayılan değer kum saati imlecini uygular. `DoWaitCursor`başvuru sayısını tutar. Pozitif olduğunda, kum saati imleci görüntülenir.

Normalde doğrudan çağırmayın `DoWaitCursor` , Bekleme imlecini değiştirmek veya bekleme imleci görüntülenirken ek işlem yapmak için bu üye işlevi geçersiz kılabilirsiniz.

Bekleme imleci uygulamak için daha kolay, daha kolay bir yol için kullanın `CWaitCursor`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

##  <a name="enabled2dsupport"></a>CWinApp:: EnableD2DSupport

Visual Studio 2010 SP1 gereklidir.

Uygulama D2D desteğini sunar. Ana pencere başlatılmadan önce bu yöntemi çağırın.

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Parametreler

*d2dFactoryType*<br/>
D2D fabrikasının ve oluşturduğu kaynakların iş parçacığı modeli.

*writeFactoryType*<br/>
Yazma fabrikası nesnesinin paylaşılıp paylaşılmayacağını veya yalıtılacağını belirten bir değer

### <a name="return-value"></a>Dönüş Değeri

D2D desteği etkinse TRUE, değilse FALSE döndürür.

##  <a name="enablehtmlhelp"></a>CWinApp:: EnableHtmlHelp

Uygulamanızın yardımı için HTMLHelp 'ı kullanmak üzere türetilmiş sınıfınızın oluşturucusunun `CWinApp`içinden bu üye işlevi çağırın.

```
void EnableHtmlHelp();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="enableshellopen"></a>CWinApp:: EnableShellOpen

Uygulamanızın kullanıcılarına Windows Dosya Yöneticisi 'nin içinden `InitInstance` dosyaları çift tıkladıklarında veri dosyalarını açmasını sağlamak için, genellikle geçersiz kılmanızda bu işlevi çağırın.

```
void EnableShellOpen();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevle birlikte member işlevini çağırın veya bir belirtin. `RegisterShellFileTypes` Belge türlerinin el ile kaydedilmesi için uygulamanızın bulunduğu REG dosyası.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

##  <a name="enabletaskbarinteraction"></a>CWinApp:: enabletaskbarınter

Görev çubuğu etkileşimini izin vermez.

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
Windows 7 görev çubuğu ile etkileşimin etkinleştirilip etkinleştirilmeyeceğini belirtir (TRUE) veya devre dışı (FALSE).

### <a name="return-value"></a>Dönüş Değeri

Görev çubuğu etkileşimi etkinleştirilüyorsa veya devre dışı bırakılmışsa, TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ana pencere oluşturulmadan önce çağrılmalıdır, aksi takdirde yanlış bir değer verir.

##  <a name="exitinstance"></a>CWinApp:: ExitInstance

Uygulamanın bu örneğinden çıkmak için `Run` üye işlev içinden Framework tarafından çağırılır.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın çıkış kodu; 0 hata olmadığını ve 0 ' dan büyük değerlerin bir hata olduğunu gösterir. Bu değer, öğesinden `WinMain`dönüş değeri olarak kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi herhangi bir yerde, `Run` ancak member işlevinin içinde çağırmayın.

Bu işlevin varsayılan uygulaması çerçeve seçeneklerini uygulamanın öğesine yazar. INı dosyası. Uygulamanız sonlandırıldığında temizlemek için bu işlevi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

##  <a name="getapplicationrecoveryparameter"></a>CWinApp:: GetApplicationRecoveryParameter

Uygulama kurtarma yönteminin giriş parametresini alır.

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama kurtarma yöntemi için varsayılan giriş parametresi.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan davranışı NULL değerini döndürür.

Daha fazla bilgi için bkz. [CWinApp:: ApplicationRecoveryCallback](#applicationrecoverycallback).

##  <a name="getapplicationrecoverypinginterval"></a>CWinApp:: GetApplicationRecoveryPingInterval

Yeniden başlatma yöneticisinin kurtarma geri çağırma işlevinin döndürmesini bekleyeceği sürenin uzunluğunu döndürür.

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>Dönüş Değeri

Sürenin milisaniye cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma Yöneticisi ile kaydedilen bir uygulama beklenmedik bir şekilde çıktığında, uygulama açık belgeleri kaydetmeye çalışır ve kurtarma geri çağırma işlevini çağırır. Varsayılan kurtarma geri çağırma işlevi [CWinApp:: ApplicationRecoveryCallback](#applicationrecoverycallback).

Çerçeve kurtarma geri çağırma işlevinin dönmesi için beklediği sürenin ping aralığıdır. Ping aralığını, için `CWinApp::GetApplicationRecoveryPingInterval` `RegisterWithRestartManager`özel bir değer sağlayarak veya üzerine yazarak özelleştirebilirsiniz.

##  <a name="getapplicationrestartflags"></a>CWinApp:: GetApplicationRestartFlags

Yeniden başlatma yöneticisinin bayraklarını döndürür.

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>Dönüş Değeri

Yeniden başlatma Yöneticisi bayrakları. Varsayılan uygulama 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma Yöneticisi için bayrakların varsayılan uygulama üzerinde hiçbir etkisi yoktur. Bunlar ileride kullanılmak üzere sağlanır.

Bir uygulamayı, [CWinApp:: RegisterWithRestartManager](#registerwithrestartmanager)kullanarak yeniden başlatma yöneticisiyle kaydettiğinizde bayrakları ayarlarsınız.

Yeniden başlatma Yöneticisi bayrakları için olası değerler şunlardır:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="getappregistrykey"></a>CWinApp:: GetAppRegistryKey

HKEY_CURRENT_USER\\"Software" \RegistryKey\ProfileName. için anahtarı döndürür

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*pTM*<br/>
Bir `CAtlTransactionManager` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa uygulama anahtarı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

##  <a name="getdatarecoveryhandler"></a>CWinApp:: GetDataRecoveryHandler

Uygulamanın bu örneği için veri kurtarma işleyicisini alır.

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın bu örneği için veri kurtarma işleyicisi.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma yöneticisini kullanan her uygulama, [CDataRecoveryHandler sınıfının](../../mfc/reference/cdatarecoveryhandler-class.md)bir örneğine sahip olmalıdır. Bu sınıf, açık belgeleri izlemenin yanı sıra dosyaları yeniden kaydetmeye sorumludur. Davranışı, `CDataRecoveryHandler` yeniden başlatma yöneticisinin yapılandırmasına bağlıdır. Daha fazla bilgi için bkz. [CDataRecoveryHandler Class](../../mfc/reference/cdatarecoveryhandler-class.md).

Bu yöntem, Windows Vista 'dan önceki işletim sistemlerinde NULL döndürür. Yeniden başlatma Yöneticisi, Windows Vista 'dan önceki işletim sistemlerinde desteklenmez.

Uygulamanın Şu anda bir veri kurtarma işleyicisi yoksa, bu yöntem bir tane oluşturur ve ona bir işaretçi döndürür.

##  <a name="getfirstdoctemplateposition"></a>CWinApp:: GetFirstDocTemplatePosition

Uygulamadaki ilk belge şablonunun konumunu alır.

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Liste boşsa NULL.

### <a name="remarks"></a>Açıklamalar

İlk [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesini almak Için [GetNextDocTemplate](#getnextdoctemplate) çağrısında döndürülen konum değerini kullanın.

##  <a name="gethelpmode"></a>CWinApp:: GetHelpMode

Uygulama tarafından kullanılan yardım türünü alır.

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama tarafından kullanılan yardım türü. Daha fazla bilgi için bkz. [CWinApp:: m_eHelpType](#m_ehelptype) .

##  <a name="getnextdoctemplate"></a>CWinApp:: GetNextDocTemplate

*POS*tarafından tanımlanan belge şablonunu alır, ardından *POS* 'u konum değerine ayarlar.

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Önceki bir `GetNextDocTemplate` veya [GetFirstDocTemplatePosition](#getfirstdoctemplateposition)çağrısı tarafından döndürülen bir konum değerine başvuru. Değer, bu çağrının bir sonraki konumuna güncelleştirilir.

### <a name="return-value"></a>Dönüş Değeri

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`GetNextDocTemplate` Bir`GetFirstDocTemplatePosition`çağrısıyla ilk konumu oluşturursanız bir ileri yineleme döngüsünde kullanabilirsiniz.

KONUM değerinin geçerli olduğundan emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Alınan belge şablonu son kullanılabilir ise, *POS* 'un yenı değeri null olarak ayarlanır.

##  <a name="getprinterdevicedefaults"></a>CWinApp:: GetPrinterDeviceDefaults

Yazdırma için bir yazıcı cihaz bağlamı hazırlamak üzere bu üye işlevi çağırın.

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>Parametreler

*pPrintDlg*<br/>
[PrintDlg](/windows/win32/api/commdlg/ns-commdlg-printdlga) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Geçerli yazıcı varsayılanlarını Windows 'tan alır. INı dosyası gereklidir veya yazdırma kurulumunda Kullanıcı tarafından ayarlanan son yazıcı yapılandırmasını kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

##  <a name="getprofilebinary"></a>CWinApp:: GetProfileBinary

Uygulamanın kayıt defterinin veya belirtilen bölümündeki bir girdiden ikili verileri almak için bu üye işlevini çağırın. INı dosyası.

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Girişi içeren bölümü belirten, null ile sonlandırılmış bir dizeye işaret eder.

*lpszEntry*<br/>
Değeri alınacak olan girişi içeren, null ile sonlandırılmış bir dizeye işaret eder.

*ppData*<br/>
Verilerin adresini alacak bir işaretçiye işaret eder.

*pBytes*<br/>
Verilerin boyutunu (bayt cinsinden) alacak bir UINT öğesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi büyük/küçük harfe duyarlı değildir, bu nedenle *lpszSection* ve *lpszEntry* parametrelerindeki dizeler büyük/küçük harf bakımından farklı olabilir.

> [!NOTE]
> `GetProfileBinary`bir arabellek ayırır ve \* *ppData*içinde adresini döndürür. Çağıran, **delete []** kullanılarak arabelleği boşaltmaktan sorumludur.

> [!IMPORTANT]
> Bu işlev tarafından döndürülen verilerin NULL sonlandırılacağı ve çağıranın doğrulama gerçekleştirmesi gerekir. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

Ek bir örnek için bkz. [CWinApp:: WriteProfileBinary](#writeprofilebinary).

##  <a name="getprofileint"></a>CWinApp:: GetProfileInt

Uygulamanın kayıt defterinin veya belirtilen bölümündeki bir girdinin içindeki bir tamsayı değerini almak için bu üye işlevini çağırın. INı dosyası.

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Girişi içeren bölümü belirten, null ile sonlandırılmış bir dizeye işaret eder.

*lpszEntry*<br/>
Değeri alınacak olan girişi içeren, null ile sonlandırılmış bir dizeye işaret eder.

*nVarsayılan*<br/>
Çerçeve girişi bulamazsa döndürülecek varsayılan değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, belirtilen girdiyi izleyen dizenin tamsayı değeri. Dönüş değeri, işlev girişi bulamazsa *nDefault* parametresinin değeridir. Belirtilen girişe karşılık gelen değer bir tamsayı değilse, dönüş değeri 0 ' dır.

Bu üye işlevi, içindeki değeri için onaltılı gösterimi destekler. INı dosyası. İşaretli bir tamsayı aldığınızda, değeri bir **int**'e atamalısınız.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi büyük/küçük harfe duyarlı değildir, bu nedenle *lpszSection* ve *lpszEntry* parametrelerindeki dizeler büyük/küçük harf bakımından farklı olabilir.

> [!IMPORTANT]
> Bu işlev tarafından döndürülen verilerin NULL sonlandırılacağı ve çağıranın doğrulama gerçekleştirmesi gerekir. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

Ek bir örnek için bkz. [CWinApp:: WriteProfileInt](#writeprofileint).

##  <a name="getprofilestring"></a>CWinApp:: GetProfileString

Uygulamanın kayıt defterinde veya belirtilen bölüm içindeki bir girdiyle ilişkili dizeyi almak için bu üye işlevini çağırın. INı dosyası.

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Girişi içeren bölümü belirten, null ile sonlandırılmış bir dizeye işaret eder.

*lpszEntry*<br/>
Dizesi alınacak olan girişi içeren, null ile sonlandırılmış bir dizeye işaret eder. Bu değer NULL olmamalıdır.

*lpszDefault*<br/>
Giriş başlatma dosyasında bulunamazsa, belirtilen girdinin varsayılan dize değerine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri, uygulamanın bir dizesidir. Dize bulunamazsa ıNı dosyası veya *lpszDefault* . Çerçeve tarafından desteklenen en fazla dize uzunluğu _MAX_PATH 'dir. *LPSZDEFAULT* null ise, dönüş değeri boş bir dizedir.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
> Bu işlev tarafından döndürülen verilerin NULL sonlandırılacağı ve çağıranın doğrulama gerçekleştirmesi gerekir. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Diğer bir örnek için, [CWinApp:: GetProfileInt](#getprofileint)örneğine bakın.

##  <a name="getsectionkey"></a>CWinApp:: GetSectionKey

HKEY_CURRENT_USER\\"Software" \RegistryKey\AppName\lpszSection. için anahtarı döndürür

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Elde edilecek anahtarın adı.

*pTM*<br/>
Bir `CAtlTransactionManager` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa bölüm anahtarı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

##  <a name="hideapplication"></a>CWinApp:: HideApplication

Açık belgeleri kapatmadan önce bir uygulamayı gizlemek için bu üye işlevini çağırın.

```
void HideApplication();
```

##  <a name="htmlhelp"></a>CWinApp:: HtmlHelp

HTMLHelp uygulamasını çağırmak için bu üye işlevini çağırın.

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>Parametreler

*dwData*<br/>
Ek verileri belirtir. Kullanılan değer *nCmd* parametresinin değerine bağlıdır. Varsayılan olarak `0x000F` [HH_HELP_CONTEXT](/previous-versions/windows/desktop/htmlhelp/hh-help-context-command)anlamına gelir.

*nCmd*<br/>
İstenen yardım türünü belirtir. Olası değerlerin bir listesi ve *dwData* parametresini nasıl etkilediği için, Windows SDK [htmlhelpw](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpw) veya [Htmlhelpa](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpa) API işlevlerinde açıklanan *uıcommand* parametresine bakın. 

### <a name="remarks"></a>Açıklamalar

Çerçeve, HTMLHelp uygulamasını çağırmak için de bu işlevi çağırır.

Uygulamanız sonlandırıldığında, çerçeve, HTMLHelp uygulamasını otomatik olarak kapatır.

##  <a name="initinstance"></a>CWinApp:: InitInstance

Windows aynı programın birkaç kopyasının aynı anda çalışmasına izin verir.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Uygulama başlatma kavramsal olarak iki bölüme ayrılmıştır: program ilk kez çalıştırıldığında gerçekleştirilen tek seferlik uygulama başlatma ve ilk kez çalıştırılan bir programın bir kopyası çalıştığında çalışan örnek başlatma. Framework 'ün uygulamasının uygulanması `WinMain` bu işlevi çağırır.

Uygulamanızın `InitInstance` Windows altında çalışan her yeni örneğini başlatmak için geçersiz kılın. Genellikle, ana pencere `InitInstance` nesnenizi oluşturmak için geçersiz kılınır ve `CWinThread::m_pMainWnd` veri üyesini bu pencereye işaret etmek üzere ayarlarsınız. Bu üye işlevi geçersiz kılma hakkında daha fazla bilgi için [bkz. CWinApp: Uygulama sınıfı](../../mfc/cwinapp-the-application-class.md).

> [!NOTE]
> MFC uygulamalarının tek iş parçacıklı grup (STA) olarak başlatılması gerekir. `InitInstance` Geçersiz kılmada [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) öğesini çağırırsanız, COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED yerine) belirtin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

##  <a name="istaskbarinteractionenabled"></a>CWinApp:: Istaskbarınteractionenabled

Windows 7 görev çubuğu etkileşiminin etkinleştirilip etkinleştirilmeyeceğini belirtir.

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>Dönüş Değeri

Çağrılırsa true, `EnableTaskbarInteraction` işletim sistemi Windows 7 veya daha yükseliyse, doğru döndürür.

### <a name="remarks"></a>Açıklamalar

Görev çubuğu etkileşimi, MDI uygulamasının MDI alt öğelerinin içeriğini fare işaretçisi uygulama görev çubuğu düğmesinin üzerindeyken görüntülenen ayrı sekmeli küçük resimlerde gösterdiği anlamına gelir.

##  <a name="loadcursor"></a>CWinApp:: LoadCursor

*LpszResourceName* tarafından adlandırılan veya geçerli yürütülebilir dosyadan *nIDResource* tarafından belirtilen imleç kaynağını yükler.

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
İmleç kaynağının adını içeren, null ile sonlandırılmış bir dizeye işaret eder. Bu bağımsız değişken için `CString` bir kullanabilirsiniz.

*nIDResource*<br/>
İmleç kaynağının KIMLIĞI. Kaynak listesi için Windows SDK [LoadCursor](/windows/win32/api/winuser/nf-winuser-loadcursorw) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa imlecin bir tutamacı. Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

`LoadCursor`imleci yalnızca daha önce yüklenmemiş ise belleğe yükler; Aksi takdirde, mevcut kaynağın bir tanıtıcısını alır.

Önceden tanımlanmış Windows imleçler 'e erişmek için [LoadStandardCursor](#loadstandardcursor) veya [LoadOEMCursor](#loadoemcursor) member işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

##  <a name="loadicon"></a>CWinApp:: LoadIcon

*LpszResourceName* tarafından adlandırılan veya yürütülebilir dosyadan *nIDResource* tarafından belirtilen simge kaynağını yükler.

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Simge kaynağının adını içeren, null ile sonlandırılmış bir dizeye işaret eder. Ayrıca, bu bağımsız değişken `CString` için de kullanabilirsiniz.

*nIDResource*<br/>
Simge kaynağının KIMLIK numarası.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simgeye yönelik bir tanıtıcı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

`LoadIcon`yalnızca daha önce yüklenmemiş olan simgeyi yükler; Aksi takdirde, mevcut kaynağın bir tanıtıcısını alır.

Önceden tanımlanmış Windows simgelerine erişmek için [Loadstandardıon](#loadstandardicon) veya [LoadOEMIcon](#loadoemicon) member işlevini kullanabilirsiniz.

> [!NOTE]
> Bu üye işlevi, yalnızca boyutu SM_CXICON ve SM_CYICON sistem ölçüm değerlerine uyan bir simge yükleyebilen [loadıcon](/windows/win32/api/winuser/nf-winuser-loadiconw)Win32 API işlevini çağırır.

##  <a name="loadoemcursor"></a>CWinApp:: LoadOEMCursor

*Nıdcursor*tarafından belirtilen Windows önceden tanımlanmış imleç kaynağını yükler.

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>Parametreler

*Nıdcursor*<br/>
Önceden tanımlanmış bir Windows imlecini belirten bir **OCR_** manifest sabit tanımlayıcısı. WINDOWS 'daki `#define OEMRESOURCE` **OCR_** sabitlerine erişebilmek için önce `#include \<afxwin.h>` sahip olmanız gerekir. Olsun.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa imlecin bir tutamacı. Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış Windows imleçler 'e erişmek için [](#loadstandardcursor) veyaLoadStandardCursorüyeişlevini`LoadOEMCursor` kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

##  <a name="loadoemicon"></a>CWinApp:: LoadOEMIcon

*Nidicon*tarafından belirtilen Windows önceden tanımlanmış simge kaynağını yükler.

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>Parametreler

*nIDIcon*<br/>
Önceden tanımlanmış bir Windows simgesi belirten bir **OIC_** manifest sabit tanımlayıcısı. WINDOWS 'daki `#define OEMRESOURCE` **OIC_** sabitlerine erişmeniz gerekir `#include \<afxwin.h>` . Olsun.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simgeye yönelik bir tanıtıcı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış `LoadOEMIcon` Windows simgelerine erişmek için ya da [loadstandardicon](#loadstandardicon) üye işlevini kullanın.

##  <a name="loadstandardcursor"></a>CWinApp:: LoadStandardCursor

*LpszCursorName* tarafından belirlenen Windows öntanımlı imleç kaynağını yükler.

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>Parametreler

*lpszCursorName*<br/>
Önceden tanımlanmış bir Windows imlecini belirten bir **IDC_** manifest sabit tanımlayıcısı. Bu tanımlayıcılar WINDOWS 'da tanımlanmıştır. Olsun. Aşağıdaki listede *lpszCursorName*için olası önceden tanımlanmış değerler ve anlamları gösterilmektedir:

- IDC_ARROW Standart ok imleci

- IDC_IBEAM standart metin ekleme imleci

- Windows zaman alan bir görev gerçekleştirdiğinde kullanılan IDC_WAIT kum saati imleci

- Seçim için IDC_CROSS çapraz-saç imleci

- Düz IDC_UPARROW ok

- IDC_SIZE artık kullanılmıyor ve desteklenmiyor; IDC_SIZEALL kullanma

- Dört noktalı ok IDC_SIZEALL. Pencereyi yeniden boyutlandırmak için kullanılacak imleç.

- IDC_ICON artık kullanılmıyor ve desteklenmiyor. IDC_ARROW kullanın.

- Sol üst ve sağ alt uçta IDC_SIZENWSE Iki uçlu ok

- Sağ üst ve sol alt uçta IDC_SIZENESW Iki uçlu ok

- IDC_SIZEWE yatay iki uçlu ok

- IDC_SIZENS dikey iki uçlu ok

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa imlecin bir tutamacı. Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış Windows [](#loadoemcursor) imleçler 'e erişmek için veyaLoadOEMCursorüyeişlevini`LoadStandardCursor` kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

##  <a name="loadstandardicon"></a>CWinApp:: LoadStandardIcon

*LpszIconName* tarafından belirlenen Windows önceden tanımlanmış simge kaynağını yükler.

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>Parametreler

*lpszIconName*<br/>
Önceden tanımlanmış bir pencere simgesi belirten bir bildirim sabiti tanımlayıcısı. Bu tanımlayıcılar WINDOWS 'da tanımlanmıştır. Olsun. Önceden tanımlanmış olabilecek değerlerin ve açıklamalarının listesi için, Windows SDK [LoadIcon](/windows/win32/api/winuser/nf-winuser-loadiconw) Içindeki *Lpiconname* parametresine bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simgeye yönelik bir tanıtıcı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış Windows [](#loadoemicon) simgelerine erişmek için veyaLoadOEMIconmemberişlevini`LoadStandardIcon` kullanın.

##  <a name="loadstdprofilesettings"></a>CWinApp:: LoadStdProfileSettings

En son kullanılan (MRU) dosyaların ve son önizleme durumunun listesini etkinleştirmek ve yüklemek için [InitInstance](#initinstance) üye işlevinin içinden bu üye işlevini çağırın.

```
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>Parametreler

*nMaxMRU*<br/>
İzlemek için son kullanılan dosya sayısı.

### <a name="remarks"></a>Açıklamalar

*NMaxMRU* 0 Ise, MRU listesi korunmaz.

##  <a name="m_bhelpmode"></a>CWinApp:: m_bHelpMode

Uygulama yardım bağlam modundaysa doğru (genel olarak SHIFT + F1 ile çağrılır); Aksi halde yanlış.

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>Açıklamalar

Yardım bağlam modunda, imleç bir soru işareti haline gelir ve Kullanıcı bunu ekran ile taşıyabilirler. Yardım modundayken özel işleme uygulamak istiyorsanız bu bayrağı inceleyin. `m_bHelpMode`BOOL türünde genel bir değişkendir.

##  <a name="m_dwrestartmanagersupportflags"></a>CWinApp:: m_dwRestartManagerSupportFlags

Yeniden başlatma yöneticisinin nasıl davranacağını belirleme bayrakları.

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma Yöneticisi 'ni etkinleştirmek için istediğiniz `m_dwRestartManagerSupportFlags` davranışa ayarlayın. Aşağıdaki tabloda kullanılabilen bayraklar gösterilmektedir.

|||
|-|-|
|Bayrağı|Açıklama|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|Uygulama, [CWinApp:: RegisterWithRestartManager](#registerwithrestartmanager)kullanılarak kaydedilir. Yeniden başlatma Yöneticisi, beklenmedik şekilde çıkılırken uygulamayı yeniden başlatmaktan sorumludur.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY|Uygulama yeniden başlatma yöneticisiyle kaydedilir ve yeniden başlatma Yöneticisi, uygulamayı yeniden başlattığında kurtarma geri çağırma işlevini çağırır. Varsayılan kurtarma geri çağırma işlevi [CWinApp:: ApplicationRecoveryCallback](#applicationrecoverycallback).|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|Otomatik kaydetme etkin ve yeniden başlatma Yöneticisi, uygulama yeniden başlatıldığında açık olan tüm belgeleri otomatik olarak kaydeder.|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|Otomatik kaydetme etkin ve yeniden başlatma Yöneticisi, tüm açık belgeleri düzenli bir aralıkta otomatik olarak kaydeder. Aralık, [CWinApp:: m_nAutosaveInterval](#m_nautosaveinterval)tarafından tanımlanır.|
|- AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|Yeniden başlatma Yöneticisi, beklenmeyen bir çıkışta uygulamayı yeniden başlattıktan sonra önceden açık belgeleri açar. [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md) , açık belgelerin listesini depolamayı ve geri yüklemeyi yönetir.|
|- AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|Yeniden başlatma Yöneticisi, uygulamayı yeniden başlattıktan sonra kullanıcıdan otomatik kaydedilmiş dosyaları geri yüklemesini ister. `CDataRecoveryHandler` Sınıfı kullanıcıyı sorgular.|
|- AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_SUPPORT_RECOVER ve AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES birleşimi.|
|- AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL ve AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES birleşimi.|
|- AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES ve AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES birleşimi.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|UNION ofAFX_RESTART_MANAGER_SUPPORT_RECOVERY, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES ve AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|

##  <a name="m_ehelptype"></a>CWinApp:: m_eHelpType

Bu veri üyesinin türü, `CWinApp` sınıfında tanımlanan, numaralandırılmış tür AFX_HELP_TYPE.

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>Açıklamalar

AFX_HELP_TYPE numaralandırması aşağıdaki gibi tanımlanır:

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- Uygulamanın yardımını HTML Yardımı olarak ayarlamak için, [SetHelpMode](#sethelpmode) çağırın ve belirtin `afxHTMLHelp`.

- Uygulamanın yardımını WinHelp, çağırın `SetHelpMode` ve belirtin `afxWinHelp`olarak ayarlayın.

##  <a name="m_hinstance"></a>CWinApp:: m_hInstance

Windows`WinMain`tarafından geçirilen *HINSTANCE* parametresine karşılık gelir.

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>Açıklamalar

`m_hInstance` Veri üyesi, Windows altında çalışan uygulamanın geçerli örneğine yönelik bir tanıtıcıdır. Bu, [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)genel işlevi tarafından döndürülür. `m_hInstance`, HıNSTANCE türünde ortak bir değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

##  <a name="m_lpcmdline"></a>CWinApp:: m_lpCmdLine

Windows`WinMain`tarafından geçirilen *lpcmdline* parametresine karşılık gelir.

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>Açıklamalar

Uygulamanın komut satırını belirten, null ile sonlandırılmış bir dizeye işaret eder. Kullanıcının `m_lpCmdLine` uygulama başlatıldığında girdiği tüm komut satırı bağımsız değişkenlerine erişmek için kullanın. `m_lpCmdLine`, LPTSTR türünde genel bir değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="m_nautosaveinterval"></a>CWinApp:: m_nAutosaveInterval

Saniye cinsinden, oto kaydetme arasındaki süre uzunluğu.

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma yöneticisini, açık belgeleri ayarlanan aralıklarda otomatik olarak yeniden açacak şekilde yapılandırabilirsiniz. Uygulamanız dosyaları otomatik olarak içermiyorsa, bu parametrenin hiçbir etkisi yoktur.

##  <a name="m_ncmdshow"></a>CWinApp:: m_nCmdShow

Windows`WinMain`tarafından geçilen *nCmdShow* parametresine karşılık gelir.

```
int m_nCmdShow;
```

### <a name="remarks"></a>Açıklamalar

Uygulamanızın ana penceresi `m_nCmdShow` için [CWnd:: ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) ' i çağırdığınızda bağımsız değişken olarak geçmelisiniz. `m_nCmdShow`, **int**türünde genel bir değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

##  <a name="m_pactivewnd"></a>CWinApp:: m_pActiveWnd

OLE sunucusu uygulamanızın yerinde etkinleştirildiği OLE kapsayıcı uygulamasının ana penceresine bir işaretçi depolamak için bu veri üyesini kullanın.

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi NULL ise, uygulama yerinde etkin değildir.

Çerçeve penceresi bir OLE kapsayıcı uygulaması tarafından etkinleştirildiğinde Framework bu üye değişkenini ayarlar.

##  <a name="m_pdatarecoveryhandler"></a>CWinApp:: m_pDataRecoveryHandler

Uygulama için veri kurtarma işleyicisine yönelik işaretçi.

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>Açıklamalar

Bir uygulamanın veri kurtarma işleyicisi açık belgeleri izler ve onları yeniden kaydeder. Çerçeve, bir uygulama beklenmedik bir şekilde çıktıktan sonra yeniden başlatıldığında otomatik kaydedilmiş dosyaları geri yüklemek için veri kurtarma işleyicisini kullanır. Daha fazla bilgi için bkz. [CDataRecoveryHandler Class](../../mfc/reference/cdatarecoveryhandler-class.md).

##  <a name="m_pszappname"></a>CWinApp:: m_pszAppName

Uygulamanın adını belirtir.

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>Açıklamalar

Uygulama adı, [CWinApp](#cwinapp) oluşturucusuna geçirilen parametreden veya BELIRTILMEMIŞSE, AFX_IDS_APP_TITLE kimlikli kaynak dizesine gelebilir. Uygulama adı kaynakta bulunamazsa programın öğesinden gelir. EXE dosya adı.

[AfxGetAppName](application-information-and-management.md#afxgetappname)genel işlevi tarafından döndürüldü. `m_pszAppName`**const char**<strong>\*</strong>türünde ortak bir değişkendir.

> [!NOTE]
> `m_pszAppName`' A bir değer atarsanız, yığın üzerinde dinamik olarak ayrılmalıdır. Yıkıcı `CWinApp` , bu işaretçiyle **Free**() öğesini çağırır. Ayırma işlemi için `_tcsdup`() çalışma zamanı kitaplığı işlevini kullanmak istersiniz. Ayrıca, yeni bir değer atamadan önce geçerli işaretçiyle ilişkili belleği boşaltın. Örneğin:

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

##  <a name="m_pszexename"></a>CWinApp:: m_pszExeName

Uzantı olmadan uygulamanın yürütülebilir dosyasının adını içerir.

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>Açıklamalar

[M_pszAppName](#m_pszappname)aksine, bu ad boşluk içeremez. `m_pszExeName`**const char**<strong>\*</strong>türünde ortak bir değişkendir.

> [!NOTE]
> `m_pszExeName`' A bir değer atarsanız, yığın üzerinde dinamik olarak ayrılmalıdır. Yıkıcı `CWinApp` , bu işaretçiyle **Free**() öğesini çağırır. Ayırma işlemi için `_tcsdup`() çalışma zamanı kitaplığı işlevini kullanmak istersiniz. Ayrıca, yeni bir değer atamadan önce geçerli işaretçiyle ilişkili belleği boşaltın. Örneğin:

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

##  <a name="m_pszhelpfilepath"></a>CWinApp:: m_pszHelpFilePath

Uygulamanın Yardım dosyasının yolunu içerir.

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak Framework, "ile `m_pszHelpFilePath` uygulamanın adı ile başlatılır. HLP "eklendi. Yardım dosyasının adını değiştirmek için, istenen yardım dosyasının tüm `m_pszHelpFilePath` adını içeren bir dizeye işaret olarak ayarlayın. Bunu yapmak için uygun bir yer, uygulamanın [InitInstance](#initinstance) işlevidir. `m_pszHelpFilePath`**const char**<strong>\*</strong>türünde ortak bir değişkendir.

> [!NOTE]
> `m_pszHelpFilePath`' A bir değer atarsanız, yığın üzerinde dinamik olarak ayrılmalıdır. Yıkıcı `CWinApp` , bu işaretçiyle **Free**() öğesini çağırır. Ayırma işlemi için `_tcsdup`() çalışma zamanı kitaplığı işlevini kullanmak istersiniz. Ayrıca, yeni bir değer atamadan önce geçerli işaretçiyle ilişkili belleği boşaltın. Örneğin:

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

##  <a name="m_pszprofilename"></a>CWinApp:: m_pszProfileName

Uygulamanın adını içerir. INı dosyası.

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>Açıklamalar

`m_pszProfileName`**const char**<strong>\*</strong>türünde ortak bir değişkendir.

> [!NOTE]
> `m_pszProfileName`' A bir değer atarsanız, yığın üzerinde dinamik olarak ayrılmalıdır. Yıkıcı `CWinApp` , bu işaretçiyle **Free**() öğesini çağırır. Ayırma işlemi için `_tcsdup`() çalışma zamanı kitaplığı işlevini kullanmak istersiniz. Ayrıca, yeni bir değer atamadan önce geçerli işaretçiyle ilişkili belleği boşaltın. Örneğin:

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

##  <a name="m_pszregistrykey"></a>CWinApp:: m_pszRegistryKey

Kayıt defteri veya ıNı dosyasında, uygulama profili ayarlarının nerede depolandığını belirlemekte kullanılır.

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>Açıklamalar

Normalde, bu veri üyesi salt okunurdur.

- Değer bir kayıt defteri anahtarında depolanır. Uygulama profili ayarının adı aşağıdaki kayıt defteri anahtarına eklenir: HKEY_CURRENT_USER/yazılım/LocalAppWizard-üretilen/.

`m_pszRegistryKey`' A bir değer atarsanız, yığın üzerinde dinamik olarak ayrılmalıdır. Yıkıcı `CWinApp` , bu işaretçiyle **Free**() öğesini çağırır. Ayırma işlemi için `_tcsdup`() çalışma zamanı kitaplığı işlevini kullanmak istersiniz. Ayrıca, yeni bir değer atamadan önce geçerli işaretçiyle ilişkili belleği boşaltın. Örneğin:

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

##  <a name="m_pszappid"></a>CWinApp:: m_pszAppID

Uygulama kullanıcı modeli KIMLIĞI.

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="oncontexthelp"></a>CWinApp:: OnContextHelp

Uygulama içinde SHIFT + F1 yardımını işler.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi etkinleştirmek `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` için `CWinApp` sınıf ileti haritanızda bir ifade eklemeniz ve genellikle SHIFT + F1 ' de bir Hızlandırıcı tablo girişi eklemeniz gerekir.

`OnContextHelp`uygulamayı yardım moduna geçirir. İmleç ok ve soru işaretine dönüşür ve Kullanıcı daha sonra fare işaretçisini taşıyabilir ve bir iletişim kutusu, pencere, menü ya da komut düğmesi seçmek için sol fare düğmesine basabilir. Bu üye işlevi imlecin altındaki nesnenin yardım bağlamını alır ve bu yardım bağlamıyla WinHelp Windows işlevini çağırır.

##  <a name="onddecommand"></a>CWinApp:: Ondalıklar Decommand

Ana çerçeve penceresi bir DDE yürütme iletisi aldığında Framework tarafından çağırılır.

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>Parametreler

*lpszCommand*<br/>
Uygulama tarafından alınan bir DDE komut dizesini işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Komut işlenirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, komutun bir belgeyi açmaya yönelik bir istek olup olmadığını denetler ve varsa belirtilen belgeyi açar. Windows Dosya Yöneticisi genellikle Kullanıcı bir veri dosyasına çift tıkladığında bu tür DDE komut dizelerini gönderir. Yazdırılacak komut gibi diğer DDE yürütme komutlarını işlemek için bu işlevi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

##  <a name="onfilenew"></a>CWinApp:: OnFileNew

ID_FILE_NEW komutunu uygular.

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi etkinleştirmek `ON_COMMAND( ID_FILE_NEW, OnFileNew )` için `CWinApp` sınıf ileti haritanızda bir ifade eklemeniz gerekir. Etkinleştirilirse, bu işlev dosya yeni komutunun yürütülmesini işler.

Varsayılan davranış hakkında bilgi edinmek ve bu üye işlevin nasıl geçersiz kılınacağını gösteren yönergeler için bkz. [Teknik notun 22](../../mfc/tn022-standard-commands-implementation.md) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileopen"></a>CWinApp:: OnFileOpen

ID_FILE_OPEN komutunu uygular.

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi etkinleştirmek `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` için `CWinApp` sınıf ileti haritanızda bir ifade eklemeniz gerekir. Etkinleştirilirse, bu işlev dosya aç komutunun yürütülmesini işler.

Bu üye işlevi geçersiz kılma hakkında daha fazla bilgi için bkz. [Teknik notun 22](../../mfc/tn022-standard-commands-implementation.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileprintsetup"></a>CWinApp:: OnFilePrintSetup

ID_FILE_PRINT_SETUP komutunu uygular.

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi etkinleştirmek `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` için `CWinApp` sınıf ileti haritanızda bir ifade eklemeniz gerekir. Etkinleştirilirse, bu işlev Dosya Yazdır komutunun yürütülmesini işler.

Bu üye işlevi geçersiz kılma hakkında daha fazla bilgi için bkz. [Teknik notun 22](../../mfc/tn022-standard-commands-implementation.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onhelp"></a>CWinApp:: OnHelp

Uygulama içinde F1 yardımını işler (geçerli bağlamı kullanarak).

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>Açıklamalar

Genellikle F1 tuşu için kısayol tuşu girdisi de ekleyeceksiniz. F1 tuşunun etkinleştirilmesi, gereksinim değil yalnızca bir kuraldır.

Bu üye işlevi etkinleştirmek `ON_COMMAND( ID_HELP, OnHelp )` için `CWinApp` sınıf ileti haritanızda bir ifade eklemeniz gerekir. Etkinleştirilirse, Kullanıcı F1 tuşuna bastığında Framework tarafından çağırılır.

Bu ileti işleyici işlevinin varsayılan uygulanması, geçerli pencereye, iletişim kutusuna veya menü öğesine karşılık gelen yardım bağlamını belirler ve ardından WINHELP çağırır. EXE. Şu anda kullanılabilir bağlam yoksa, işlev varsayılan bağlamı kullanır.

Yardım bağlamını Şu anda odağa sahip olan pencere, iletişim kutusu, menü öğesi veya araç çubuğu düğmesinden başka bir şeye ayarlamak için bu üye işlevi geçersiz kılın. İstenen `WinHelp` yardım bağlamı kimliğiyle çağırın.

##  <a name="onhelpfinder"></a>CWinApp:: OnHelpFinder

ID_HELP_FINDER ve ID_DEFAULT_HELP komutlarını işler.

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi etkinleştirmek `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` için `CWinApp` sınıf ileti haritanızda bir ifade eklemeniz gerekir. Etkinleştirilirse, uygulamanın kullanıcısı standart `WinHelp` **HELP_FINDER** konusuyla çağırmak için Yardım Bulucu komutunu seçtiğinde, çerçeve bu ileti işleyicisi işlevini çağırır.

##  <a name="onhelpindex"></a>CWinApp:: OnHelpIndex

ID_HELP_INDEX komutunu işler ve varsayılan bir yardım konusu sağlar.

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi etkinleştirmek `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` için `CWinApp` sınıf ileti haritanızda bir ifade eklemeniz gerekir. Etkinleştirilirse, uygulamanızın kullanıcısı standart `WinHelp` **HELP_INDEX** konusuyla çağırmak üzere Yardım dizini komutunu seçtiğinde, çerçeve bu ileti işleyicisi işlevini çağırır.

##  <a name="onhelpusing"></a>CWinApp:: OnHelpUsing

ID_HELP_USING komutunu işler.

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi etkinleştirmek `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` için `CWinApp` sınıf ileti haritanızda bir ifade eklemeniz gerekir. Uygulama kullanıcısı, uygulamayı standart `WinHelp` **HELP_HELPONHELP** konusuyla çağırmak için yardım using komutunu seçtiğinde Framework bu ileti işleyicisi işlevini çağırır.

##  <a name="onidle"></a>CWinApp:: OnIdle

Boş zamanlı işleme gerçekleştirmek için bu üye işlevini geçersiz kılın.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Parametreler

*lCount*<br/>
Uygulamanın ileti kuyruğu boş olduğunda `OnIdle` her seferinde arttırılan bir sayaç. Bu sayı, her yeni ileti işlendiğinde 0 ' a sıfırlanır. Uygulamanın bir iletiyi işlemeden boşta kaldığı sürenin göreli uzunluğunu öğrenmek için *lCount* parametresini kullanabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Daha fazla boş işlem süresi almak için sıfır dışında; daha fazla boş süre gerekmiyorsa 0.

### <a name="remarks"></a>Açıklamalar

`OnIdle`, uygulamanın ileti sırası boş olduğunda varsayılan ileti döngüsünde çağrılır. Kendi arka plan boşta işleyici görevlerinizi çağırmak için geçersiz kılmanızı kullanın.

`OnIdle`boş işlem süresi gerekmediğini belirtmek için 0 döndürmelidir. Her seferinde `OnIdle` bir ileti sırası boş olduğunda *lCount* parametresi artırılır ve her yeni ileti işlendiğinde 0 ' a sıfırlanır. Bu sayıya göre farklı boşta yordamlarınızı çağırabilirsiniz.

Aşağıdaki, boşta döngüsü işlemeyi özetler:

1. Microsoft Foundation Class Kitaplığı ileti döngüsü ileti kuyruğunu denetler ve bekleyen ileti bulmadığını belirlerse, uygulama nesnesini çağırır `OnIdle` ve *lCount* bağımsız değişkeni olarak 0 sağlar.

2. `OnIdle`bazı işlemleri gerçekleştirir ve daha fazla işlem yapmak için yeniden çağrılması gerektiğini göstermek için sıfır dışında bir değer döndürür.

3. İleti döngüsü ileti kuyruğunu yeniden denetler. Bekleyen bir ileti yoksa, *lCount* bağımsız `OnIdle` değişkenini arttırın ve sonra yeniden çağırır.

4. Sonuç olarak `OnIdle` , tüm boşta görevlerinin işlenmesini tamamlar ve 0 döndürür. Bu ileti döngüsüne ileti kuyruğundan bir sonraki ileti `OnIdle` alınana kadar çağrıyı durdurmasını söyler. bu noktada, boşta kalma döngüsü 0 olarak ayarlanan bağımsız değişkenle birlikte yeniden başlatılır.

Uygulamanız, tarafından döndürülünceye kadar `OnIdle` `OnIdle` Kullanıcı girdisini işleyemediği için uzun görevleri gerçekleştirmeyin.

> [!NOTE]
> Varsayılan `OnIdle` Updates komutu, menü öğeleri ve araç çubuğu düğmeleri gibi kullanıcı arabirimi nesneleri ve iç veri yapısını temizleme işlemini gerçekleştirir. Bu nedenle, öğesini geçersiz `OnIdle`kılarsınız, geçersiz `CWinApp::OnIdle` kılınan sürümünüzde `lCount` ile çağırmanız gerekir. İlk olarak tüm temel sınıf boşta işlemeyi çağırın (yani, taban sınıf `OnIdle` 0 döndürülünceye kadar). Temel sınıf işleme tamamlanmadan önce iş yapmanız gerekiyorsa, çalışmanız için uygun *lCount* değerini seçmek üzere temel sınıf uygulamasını gözden geçirin.

İleti sırasından bir ileti alındıktan `OnIdle` sonra çağrılması istemiyorsanız, [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage)geçersiz kılabilirsiniz. Bir uygulama çok kısa bir Zamanlayıcı ayarlandıysa veya sistem WM_SYSTIMER iletisini `OnIdle` gönderiyorsa, tekrar tekrar çağrılacaktır ve performansı düşürür.

### <a name="example"></a>Örnek

Aşağıdaki iki örnek nasıl kullanılacağını `OnIdle`göstermektedir. İlk örnek, görevlerin önceliklerini belirlemek için *lCount* bağımsız değişkenini kullanarak iki boş görevi işler. İlk görev yüksek önceliğe sahiptir ve mümkün olduğunda bunu yapmanız gerekir. İkinci görev daha az önemlidir ve yalnızca Kullanıcı girişinde uzun bir duraklama olduğunda yapılmalıdır. Öğesinin `OnIdle`temel sınıf sürümüne çağrı yapın. İkinci örnek, farklı önceliklere sahip bir boş görev grubunu yönetir.

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

##  <a name="opendocumentfile"></a>CWinApp:: OpenDocumentFile

Framework, uygulamanın adlandırılmış [CDocument](../../mfc/reference/cdocument-class.md) dosyasını açmak için bu yöntemi çağırır.

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
'ndaki Açılacak dosyanın adı.

*bAddToMRU*<br/>
'ndaki TRUE, belgenin en son dosyalardan biri olduğunu belirtir; FALSE, belgenin en son dosyalardan biri olmadığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda bir `CDocument` işaretçisi; Aksi takdirde null.

### <a name="remarks"></a>Açıklamalar

Bu ada sahip bir belge zaten açıksa, bu belgeyi içeren ilk çerçeve penceresi odağı alır. Bir uygulama birden çok belge şablonunu destekliyorsa, çerçeve belgeyi yüklemeye çalışmak üzere uygun belge şablonunu bulmak için dosya adı uzantısını kullanır. Başarılı olursa belge şablonu, belge için bir çerçeve penceresi ve görünümü oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="parsecommandline"></a>CWinApp::P arseCommandLine

Komut satırını ayrıştırmak ve parametreleri birer birer, [CCommandLineInfo::P Arseparad](../../mfc/reference/ccommandlineinfo-class.md#parseparam)öğesine göndermek için bu üye işlevini çağırın.

```
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Parametreler

*Rcmınfo*<br/>
[CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Uygulama Sihirbazı 'nı kullanarak yeni bir MFC projesi başlattığınızda, uygulama Sihirbazı `CCommandLineInfo`yerel bir örneğini oluşturur ve sonra [InitInstance](#initinstance) üye işlevini `ParseCommandLine` çağırır `ProcessShellCommand` . Komut satırı aşağıda açıklanan yolu izler:

1. İçinde `InitInstance`oluşturulduktan sonra `CCommandLineInfo` , nesnesi öğesine `ParseCommandLine`geçirilir.

2. `ParseCommandLine`sonra her `CCommandLineInfo::ParseParam` parametre için bir kez tekrar tekrar çağırır.

3. `ParseParam`daha sonra [ProcessShellCommand](#processshellcommand)öğesine geçirilen nesneyidoldurur.`CCommandLineInfo`

4. `ProcessShellCommand`komut satırı bağımsız değişkenlerini ve bayraklarını işler.

Gerektiğinde doğrudan çağırabileceğinizi `ParseCommandLine` unutmayın.

Komut satırı bayraklarının bir açıklaması için bkz. [CCommandLineInfo:: m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).

##  <a name="pretranslatemessage"></a>CWinApp::P reTranslateMessage

Pencere iletilerini [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce filtrelemek için bu işlevi geçersiz kılın varsayılan uygulama kısayol tuşu çevirisini gerçekleştirir, bu nedenle şunu çağırmanız `CWinApp::PreTranslateMessage`gerekirgeçersiz kılınan sürümdeki üye işlevi.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
İşlenecek iletiyi içeren bir [msg](/windows/win32/api/winuser/ns-winuser-msg) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti içinde `PreTranslateMessage` tam olarak işlendiyse ve daha fazla işlenmemelidir. İleti normal şekilde işlenirse sıfır.

##  <a name="processmessagefilter"></a>CWinApp::P rocessMessageFilter

Framework 'ün kanca işlevi, belirli Windows iletilerini filtrelemek ve bunlara yanıt vermek için bu üye işlevini çağırır.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*kodudur*<br/>
Bir kanca kodu belirtir. Bu üye işlevi, *lpMsg* 'in nasıl işleyeceğini anlamak için kodu kullanır.

*lpMsg*<br/>
Windows [msg](/windows/win32/api/winuser/ns-winuser-msg)structuralbir işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kanca işlevi, olayları uygulamanın normal ileti işlemeye gönderilmeden önce işler.

Bu gelişmiş özelliği geçersiz kılarsınız, Framework 'ün kanca işlemesini sürdürmek için temel sınıf sürümü çağırdığınızdan emin olun.

##  <a name="processshellcommand"></a>CWinApp::P rocessShellCommand

Bu üye işlevi, *rcmınfo*tarafından tanımlanan `CCommandLineInfo` nesneden geçirilen parametreleri kabul etmek için [InitInstance](#initinstance) tarafından çağırılır ve belirtilen eylemi gerçekleştirir.

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Parametreler

*Rcmınfo*<br/>
[CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) nesnesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Kabuk komutu başarıyla işlendiyse sıfır dışı. 0 ise, [InitInstance](#initinstance)'dan false döndürün.

### <a name="remarks"></a>Açıklamalar

Uygulama Sihirbazı 'nı kullanarak yeni bir MFC projesi başlattığınızda, uygulama Sihirbazı yerel `CCommandLineInfo`bir örneğini oluşturur ve sonra `InitInstance` üye işlevinde ve [ParseCommandLine](#parsecommandline) öğesini çağırır `ProcessShellCommand` . Komut satırı aşağıda açıklanan yolu izler:

1. İçinde `InitInstance`oluşturulduktan sonra `CCommandLineInfo` , nesnesi öğesine `ParseCommandLine`geçirilir.

2. `ParseCommandLine`daha sonra her parametre için bir kez olmak üzere [CCommandLineInfo::P Arseparae](../../mfc/reference/ccommandlineinfo-class.md#parseparam) olarak çağırır.

3. `ParseParam`nesneyi doldurur ve sonra öğesine `ProcessShellCommand`geçirilir. `CCommandLineInfo`

4. `ProcessShellCommand`komut satırı bağımsız değişkenlerini ve bayraklarını işler.

`CCommandLineInfo` [CCommandLineInfo:: m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)tarafından tanımlanan nesnenin veri üyeleri, `CCommandLineInfo` sınıfı içinde tanımlanan, aşağıdaki numaralandırılmış türde.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };
```

Bu değerlerin her birinin kısa bir açıklaması için bkz `CCommandLineInfo::m_nShellCommand`.

##  <a name="processwndprocexception"></a>CWinApp::P rocessWndProcException

Bu üye işlevi, işleyici uygulamanızın iletisinden veya komut işleyicilerinden birinde oluşturulan bir özel durumu yakaaramadiğinde Bu üye işlevini çağırır.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*e*<br/>
Yakalanamayan özel durum işaretçisi.

*pMsg*<br/>
Framework 'ün özel durum oluşturmasını sağlayan Windows iletisi hakkında bilgi içeren bir [msg](/windows/win32/api/winuser/ns-winuser-msg).

### <a name="return-value"></a>Dönüş Değeri

Windows 'a döndürülmesi gereken değer. Normalde bu Windows iletileri için 0L, komut iletileri için 1L (TRUE).

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini doğrudan çağırmayın.

Bu üye işlevinin varsayılan uygulamasında bir ileti kutusu oluşturulur. Yakalanmayan özel durum bir menü, araç çubuğu veya hızlandırıcı komut hatası ile kaynaklanıyorsa ileti kutusunda bir "komut başarısız oldu" iletisi görüntülenir. Aksi halde, "Iç uygulama hatası" iletisini görüntüler.

Özel durumlarınızın genel işlemesini sağlamak için bu üye işlevini geçersiz kılın. Yalnızca ileti kutusunun görüntülenmesini istiyorsanız temel işlevi çağırın.

##  <a name="register"></a>CWinApp:: Register

Tarafından `RegisterShellFileTypes`işlenmemiş tüm kayıt görevlerini gerçekleştirir.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan farklı, başarılı olma; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama yalnızca TRUE değerini döndürür. Özelleştirilmiş herhangi bir kayıt adımını sağlamak için bu işlevi geçersiz kılın.

##  <a name="registershellfiletypes"></a>CWinApp:: RegisterShellFileTypes

Tüm uygulamanızın belge türlerini Windows Dosya Yöneticisi ile kaydetmek için bu üye işlevi çağırın.

```
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>Parametreler

*bCompat*<br/>
'ndaki DOĞRU, Kullanıcı tarafından doğrudan kabuktan dosya yazdırabilmesine veya dosyayı bir yazıcı nesnesine sürükleyerek kabuk komutlarının yazdırma ve yazdırma için kayıt girişlerini ekler. Ayrıca bir DefaultIcon anahtarı ekler. Bu parametre, geri uyumluluk için varsayılan olarak FALSE 'TUR.

### <a name="remarks"></a>Açıklamalar

Bu, kullanıcının Dosya Yöneticisi içinden çift tıklayarak uygulamanız tarafından oluşturulan bir veri dosyasını açmasına olanak sağlar. Uygulamanızdaki `RegisterShellFileTypes` belge şablonlarının her biri için [AddDocTemplate öğesini](#adddoctemplate) çağırdıktan sonra çağırın. Ayrıca, `RegisterShellFileTypes`çağırdığınızda [EnableShellOpen](#enableshellopen) üye işlevini çağırın.

`RegisterShellFileTypes`uygulamanın koruduğu [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnelerinin listesi boyunca yinelenir ve her belge şablonu için Windows 'un dosya ilişkilendirmeleri için tuttuğu kayıt veritabanına giriş ekler. Dosya Yöneticisi bu girdileri kullanıcı çift tıkladığında bir veri dosyası açmak için kullanır. Bu, gönderme gereksinimini ortadan kaldırır. Uygulamanızın bulunduğu REG dosyası.

> [!NOTE]
> `RegisterShellFileTypes`yalnızca Kullanıcı programı yönetici haklarıyla çalıştırıyorsa çalışır. Programın yönetici hakları yoksa, kayıt defteri anahtarlarını değiştiremez.

Kayıt veritabanı zaten başka bir dosya türüyle verilen bir dosya adı uzantısını ilişkilendirirse, yeni ilişkilendirme oluşturulmaz. Bu bilgileri kaydetmek için gereken dizelerin biçim sınıfınabakın.`CDocTemplate`

##  <a name="registerwithrestartmanager"></a>CWinApp:: RegisterWithRestartManager

Uygulamayı yeniden başlatma yöneticisiyle kaydeder.

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
|*bRegisterRecoveryCallback*|'ndaki TRUE, uygulamanın bu örneğinin bir kurtarma geri çağırma işlevi kullandığını gösterir; FALSE, olmadığını gösterir. Uygulama beklenmedik bir şekilde çıktığında, çerçeve kurtarma geri çağırma işlevini çağırır. Daha fazla bilgi için bkz. [CWinApp:: ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*strRestartIdentifier*|'ndaki Yeniden başlatma Yöneticisi 'nin bu örneğini tanımlayan benzersiz dize. Yeniden başlatma Yöneticisi tanımlayıcısı, bir uygulamanın her örneği için benzersizdir.|
|*Pwzcommanddoğrgs*|'ndaki Komut satırından ek bağımsız değişkenler içeren bir dize.|
|*dwRestartFlags*|'ndaki Yeniden başlatma Yöneticisi için isteğe bağlı bayraklar. Daha fazla bilgi için, açıklamalar bölümüne bakın.|
|*pRecoveryCallback*|'ndaki Kurtarma geri çağırma işlevi. Bu işlev, girdi olarak bir LPVOID parametresi almalıdır ve bir DWORD döndürmelidir. Varsayılan kurtarma geri çağırma işlevi `CWinApp::ApplicationRecoveryCallback`.|
|*lpvParam*|'ndaki Kurtarma geri çağırma işlevinin giriş parametresi. Daha fazla bilgi için bkz. [CWinApp:: ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*dwPingInterval*|'ndaki Yeniden başlatma yöneticisinin kurtarma geri çağırma işlevinin döndürmesini bekleyeceği sürenin uzunluğu. Bu parametre milisaniyedir.|
|*dwCallbackFlags*|'ndaki Kurtarma geri çağırma işlevine geçirilen bayraklar. Daha sonraki kullanımlar için ayrılmıştır.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

Uygulamanız, dosyaları yeniden kaydetmeye yönelik varsayılan MFC uygulamasını kullanıyorsa, basit sürümünü `RegisterWithRestartManager`kullanmanız gerekir. Uygulamanızın otomatik kaydetme davranışını özelleştirmek `RegisterWithRestartManager` istiyorsanız, karmaşık sürümünü kullanın.

Bu yöntemi *strRestartIdentifier*için boş bir dize ile çağırırsanız, `RegisterWithRestartManager` restart Manager 'ın bu örneği için benzersiz bir tanımlayıcı dizesi oluşturur.

Bir uygulama beklenmedik bir şekilde çıktığında, yeniden başlatma Yöneticisi uygulamayı komut satırından yeniden başlatır ve isteğe bağlı bağımsız değişken olarak benzersiz yeniden başlatma tanımlayıcısı sağlar. Bu senaryoda, çerçeve iki kez çağırır `RegisterWithRestartManager` . İlk çağrı, bir dize tanımlayıcısı için boş bir dize ile [CWinApp:: InitInstance](#initinstance) 'tan geliyor. Ardından, [CWinApp::P rocessshellcommand](#processshellcommand) öğesini benzersiz yeniden `RegisterWithRestartManager` başlatma tanımlayıcısıyla çağırır.

Yeniden başlatma Yöneticisi ile bir uygulamayı kaydettikten sonra, yeniden başlatma Yöneticisi uygulamayı izler. Uygulama beklenmedik bir şekilde çıkıyorsa, yeniden başlatma Yöneticisi kapatma işlemi sırasında kurtarma geri çağırma işlevini çağırır. Yeniden başlatma Yöneticisi, kurtarma geri çağırma işlevinden bir yanıt için *dwPingInterval* değerini bekler. Kurtarma geri çağırma işlevi bu süre içinde yanıt vermezse, kurtarma geri çağırma işlevini yürütmeden uygulamadan çıkar.

Varsayılan olarak, dwRestartFlags desteklenmez ancak gelecekte kullanılmak üzere sağlanır. *DwRestartFlags* için olası değerler şunlardır:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="reopenpreviousfilesatrestart"></a>CWinApp:: ReopenPreviousFilesAtRestart

Yeniden başlatma yöneticisinin, uygulamanın beklenmedik şekilde çıkıldığında açık olan dosyaları yeniden açıp açamayacağını belirler.

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, restart Manager 'ın önceden açık dosyaları yeniden açmasını gösterir; FALSE, restart Manager 'ın olmadığını gösterir.

##  <a name="restartinstance"></a>CWinApp:: RestartInstance

Yeniden başlatma Yöneticisi tarafından başlatılan uygulama yeniden başlatmasını işler.

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Veri kurtarma işleyicisi daha önce açık belgeleri açarsa doğru. Veri kurtarma işleyicisinin bir hatası varsa veya önceden açık belge yoksa FALSE.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma Yöneticisi bir uygulamayı yeniden başlattığında, çerçeve bu yöntemi çağırır. Bu yöntem, veri kurtarma işleyicisini alır ve otomatik kaydedilen dosyaları geri yükler. Bu yöntem, kullanıcının otomatik kaydedilmiş dosyaları geri yüklemek isteyip istemediğini anlamak için [CDataRecoveryHandler:: RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) öğesini çağırır.

[CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) açık belge olmadığını belirlerse, bu yöntem false döndürür. Açık belge yoksa, uygulama normalde başlatılır.

##  <a name="restoreautosavedfilesatrestart"></a>CWinApp:: RestoreAutosavedFilesAtRestart

Yeniden başlatma yöneticisinin uygulamayı yeniden başlattığında otomatik kaydedilen dosyaları geri yükleme olup olmadığını belirler.

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, restart Manager 'ın otomatik kaydedilmiş dosyaları geri yüklediği anlamına gelir; FALSE, restart Manager 'ın olmadığını gösterir.

##  <a name="run"></a>CWinApp:: Run

Varsayılan bir ileti döngüsü sağlar.

```
virtual int Run();
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından`WinMain`döndürülen bir **int** değeri.

### <a name="remarks"></a>Açıklamalar

`Run`uygulama bir WM_QUIT iletisi alana kadar Windows iletilerini alır ve gönderir. Uygulamanın ileti sırası şu anda hiçbir ileti içermiyorsa, `Run` boşta kalma süresi işlemini gerçekleştirmek için [OnIdle](#onidle) çağırır. Gelen iletiler, özel işleme için [PreTranslateMessage](#pretranslatemessage) üye işlevine, ardından standart klavye çevirisi için Windows işlevine `TranslateMessage` gider `DispatchMessage` ; son olarak, Windows işlevi çağırılır.

`Run`nadiren geçersiz kılındı, ancak özel davranış sağlamak için geçersiz kılabilirsiniz.

##  <a name="runautomated"></a>CWinApp:: RunAutomated

Sunucu uygulamasının bir istemci uygulaması tarafından başlatılıp başlatılmayacağını gösteren " **/Automation**" veya " **-Automation**" seçeneğinin bulunup bulunmadığını öğrenmek için bu işlevi çağırın.

```
BOOL RunAutomated();
```

### <a name="return-value"></a>Dönüş Değeri

Seçenek bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsa, seçenek komut satırından kaldırılır. OLE Otomasyonu hakkında daha fazla bilgi için [Otomasyon sunucuları](../../mfc/automation-servers.md)makalesine bakın.

##  <a name="runembedded"></a>CWinApp:: RunEmbedded

Sunucu uygulamasının bir istemci uygulaması tarafından başlatılıp başlatılmayacağını gösteren " **/gömme**" veya " **-gömme**" seçeneğinin bulunup bulunmadığını öğrenmek için bu işlevi çağırın.

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>Dönüş Değeri

Seçenek bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsa, seçenek komut satırından kaldırılır. Ekleme hakkında daha fazla bilgi için bkz. Makale [sunucuları: Sunucu](../../mfc/servers-implementing-a-server.md)uygulama.

##  <a name="saveallmodified"></a>CWinApp:: SaveAllModified

Uygulamanın ana çerçeve penceresi kapandığınızda veya bir WM_QUERYENDSESSION iletisi aracılığıyla tüm belgeleri kaydetmek için Framework tarafından çağırılır.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın sonlandırılması güvenli değilse sıfır dışında; uygulamayı sonlandırmak için güvenli değilse 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin varsayılan uygulaması, [CDocument:: SaveModified](../../mfc/reference/cdocument-class.md#savemodified) üye işlevini çağırarak uygulamadaki tüm değiştirilen belgelere sırayla çağırır.

##  <a name="selectprinter"></a>CWinApp:: SelectPrinter

Belirli bir yazıcı seçmek için bu üye işlevini çağırın ve Yazdır Iletişim kutusunda daha önce seçilmiş olan yazıcıyı serbest bırakın.

```
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>Parametreler

*hDevNames*<br/>
Belirli bir yazıcının sürücüsünü, cihazını ve çıkış bağlantı noktası adlarını tanımlayan bir [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)için tanıtıcı.

*hDevMode*<br/>
Bir yazıcı cihazının cihaz başlatması ve ortamı hakkındaki bilgileri belirten bir [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) yapısına yönelik bir tanıtıcı.

*bFreeOld*<br/>
Önceden seçili olan yazıcıyı serbest bırakır.

### <a name="remarks"></a>Açıklamalar

Her iki *hDevMode* ve *hDevNames* null ise, `SelectPrinter` geçerli varsayılan yazıcıyı kullanır.

##  <a name="sethelpmode"></a>CWinApp:: SetHelpMode

Uygulamanın yardım türünü ayarlar.

```
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>Parametreler

*eHelpType*<br/>
Kullanılacak yardım türünü belirtir. Daha fazla bilgi için bkz. [CWinApp:: m_eHelpType](#m_ehelptype) .

### <a name="remarks"></a>Açıklamalar

Uygulamanın yardım türünü ayarlar.

Uygulamanızın yardım türünü HTMLHelp olarak ayarlamak için [EnableHTMLHelp](#enablehtmlhelp)öğesini çağırabilirsiniz. ' İ çağırdığınızda `EnableHTMLHelp`, uygulamanızın yardım uygulaması olarak HTMLHelp kullanması gerekir. WinHelp 'yi kullanmak için değiştirmek istiyorsanız, *eHelpType* öğesini `afxWinHelp`çağırıp `SetHelpMode` olarak ayarlayabilirsiniz.

##  <a name="setregistrykey"></a>CWinApp:: SetRegistryKey

Uygulama ayarlarının ıNı dosyaları yerine kayıt defterinde depolanmasına neden olur.

```
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>Parametreler

*lpszRegistryKey*<br/>
Anahtarın adını içeren bir dize işaretçisi.

*Nıdregistrykey*<br/>
Kayıt defteri anahtarının adını içeren bir dize kaynağının KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu işlev,daha sonra öğesinin `GetProfileInt` `WriteProfileInt` `GetProfileString` ,`CWinApp`, ve `WriteProfileString` üye işlevleri tarafından kullanılan m_pszRegistryKey öğesini ayarlar. Bu işlev çağrılırsa, en son kullanılanlar (MRU) dosyalarının listesi de kayıt defterinde saklanır. Kayıt defteri anahtarı genellikle şirketin adıdır. Aşağıdaki formun bir anahtarında depolanır: HKEY_CURRENT_USER\Software\\< şirket adı\>\\< uygulama adı\><bölümadı\><değer\>adı.\\\\

##  <a name="supportsapplicationrecovery"></a>CWinApp:: SupportsApplicationRecovery

Yeniden başlatma yöneticisinin beklenmedik bir şekilde çıkıldı bir uygulamayı kurtarıp kurtarmayacağını belirler.

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, restart Manager 'ın uygulamayı kurtardığını gösterir; FALSE, restart Manager 'ın olmadığını gösterir.

##  <a name="supportsautosaveatinterval"></a>CWinApp:: Supportsautosaveatınterval

Restart Manager 'ın açık belgeleri düzenli bir aralıkta yeniden kaydedip kaydetmediğini belirler.

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, restart Manager 'ın açık belgeleri açmasını belirtir; FALSE, restart Manager 'ın olmadığını gösterir.

##  <a name="supportsautosaveatrestart"></a>CWinApp:: SupportsAutosaveAtRestart

Yeniden başlatma Yöneticisi 'nin, uygulama yeniden başlatıldığında açık olan tüm belgeleri açıp kaydetmeyeceğini belirler.

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma yöneticisinin uygulama yeniden başlatıldığında açık belgeleri açmasını belirtir; FALSE, restart Manager 'ın olmadığını gösterir.

##  <a name="supportsrestartmanager"></a>CWinApp:: SupportsRestartManager

Uygulamanın yeniden başlatma yöneticisini destekleyip desteklemediğini belirler.

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, uygulamanın yeniden başlatma yöneticisini desteklediğini belirtir; FALSE, uygulamanın olmadığını gösterir.

##  <a name="unregister"></a>CWinApp:: Unregister

Uygulama nesnesi tarafından kaydedilen tüm dosyaların kaydını siler.

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan farklı, başarılı olma; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlevi, uygulama nesnesi ve Register işlevi tarafından gerçekleştirilen kaydı geri alır. [](#register) `Unregister` Normalde, her iki işlev MFC tarafından örtük olarak çağrılır ve bu nedenle kodunuzda görünmez.

Özel kayıt silme adımları gerçekleştirmek için bu işlevi geçersiz kılın.

##  <a name="unregistershellfiletypes"></a>CWinApp:: UnregisterShellFileTypes

Tüm uygulamanızın belge türlerinin Windows Dosya Yöneticisi ile kaydını silmek için bu üye işlevi çağırın.

```
void UnregisterShellFileTypes();
```

##  <a name="winhelp"></a>CWinApp:: WinHelp

WinHelp uygulamasını çağırmak için bu üye işlevini çağırın.

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>Parametreler

*dwData*<br/>
Ek verileri belirtir. Kullanılan değer *nCmd* parametresinin değerine bağlıdır.

*nCmd*<br/>
İstenen yardım türünü belirtir. Olası değerler listesi ve bunların *dwData* parametresini nasıl etkilediği hakkında bilgi Için, [WinHelp](/windows/win32/api/winuser/nf-winuser-winhelpw) Windows işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Framework, WinHelp uygulamasını çağırmak için de bu işlevi çağırır.

Uygulamanız sonlandırıldığında, çerçeve WinHelp uygulamasını otomatik olarak kapatır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

##  <a name="writeprofilebinary"></a>CWinApp:: WriteProfileBinary

Uygulamanın kayıt defterinin veya belirtilen bölümüne ikili verileri yazmak için bu üye işlevi çağırın. INı dosyası.

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Girişi içeren bölümü belirten, null ile sonlandırılmış bir dizeye işaret eder. Bölüm yoksa, oluşturulur. Bölümün adı büyük/küçük harfe bağımsızdır; dize, büyük ve küçük harflerin herhangi bir birleşimi olabilir.

*lpszEntry*<br/>
Değerin yazılacağı girişi içeren, null ile sonlandırılmış bir dizeye işaret eder. Giriş belirtilen bölümde yoksa, oluşturulur.

*pData*<br/>
Yazılacak verileri işaret eder.

*nBytes*<br/>
Yazılacak bayt sayısını içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

Bu örnek, `CWinApp* pApp = AfxGetApp();` bir MFC uygulamasındaki herhangi bir işlevden kullanılabilecek bir `WriteProfileBinary` yöntemi `GetProfileBinary` gösteren CWinApp sınıfına ulaşmak için kullanır.

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

Başka bir örnek için, [CWinApp:: GetProfileBinary](#getprofilebinary)örneğine bakın.

##  <a name="writeprofileint"></a>CWinApp:: WriteProfileInt

Uygulamanın kayıt defterinin veya belirtilen bölümüne belirtilen değeri yazmak için bu üye işlevi çağırın. INı dosyası.

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Girişi içeren bölümü belirten, null ile sonlandırılmış bir dizeye işaret eder. Bölüm yoksa, oluşturulur. Bölümün adı büyük/küçük harfe bağımsızdır; dize, büyük ve küçük harflerin herhangi bir birleşimi olabilir.

*lpszEntry*<br/>
Değerin yazılacağı girişi içeren, null ile sonlandırılmış bir dizeye işaret eder. Giriş belirtilen bölümde yoksa, oluşturulur.

*nDeğer*<br/>
Yazılacak değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

Bu örnek `WriteProfileString`, `CWinApp* pApp = AfxGetApp();` `WriteProfileInt` ,,`GetProfileInt` ve bir MFC uygulamasındaki herhangi bir işlevden kullanılabilecek bir yöntemi gösteren CWinApp sınıfına ulaşmak için kullanır. `GetProfileString`

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Diğer bir örnek için, [CWinApp:: GetProfileInt](#getprofileint)örneğine bakın.

##  <a name="writeprofilestring"></a>CWinApp:: WriteProfileString

Belirtilen dizeyi uygulamanın kayıt defterinin belirtilen bölümüne yazmak için bu üye işlevi çağırın. INı dosyası.

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Girişi içeren bölümü belirten, null ile sonlandırılmış bir dizeye işaret eder. Bölüm yoksa, oluşturulur. Bölümün adı büyük/küçük harfe bağımsızdır; dize, büyük ve küçük harflerin herhangi bir birleşimi olabilir.

*lpszEntry*<br/>
Değerin yazılacağı girişi içeren, null ile sonlandırılmış bir dizeye işaret eder. Giriş belirtilen bölümde yoksa, oluşturulur. Bu parametre NULL ise, *lpszSection* tarafından belirtilen bölüm silinir.

*lpszValue*<br/>
Yazılacak dizeyi işaret eder. Bu parametre NULL ise, *lpszEntry* parametresi tarafından belirtilen girdi silinir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Diğer bir örnek için, [CWinApp:: GetProfileInt](#getprofileint)örneğine bakın.

##  <a name="setappid"></a>CWinApp:: Setappıd

Uygulamanın uygulama kullanıcı modeli KIMLIĞINI açık olarak ayarlar. Bu yöntem, kullanıcıya herhangi bir kullanıcı arabirimi sunulmadan önce çağrılmalıdır (uygulama Oluşturucusu en iyi yer olur).

```
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>Parametreler

*Lpcszappıd*<br/>
Uygulamanın kullanıcı modeli KIMLIĞINI belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[CWinThread Sınıfı](../../mfc/reference/cwinthread-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme](../../mfc/how-to-add-restart-manager-support.md)
