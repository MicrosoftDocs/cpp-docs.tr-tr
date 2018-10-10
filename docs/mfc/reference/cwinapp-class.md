---
title: CWinApp sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6c7d961119d4fe25652601ebe5e423be898f49e
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890744"
---
# <a name="cwinapp-class"></a>CWinApp sınıfı

Bir Windows uygulama nesnesi türettiğiniz taban sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class CWinApp : public CWinThread
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWinApp::CWinApp](#cwinapp)|Oluşturur bir `CWinApp` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinApp::AddDocTemplate](#adddoctemplate)|Bir belge şablonu, uygulamanın kullanılabilir şablonların listesine ekler.|
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|Bir dosya adı en son kullanılan (MRU) dosya listesine ekler.|
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|Uygulama beklenmedik bir şekilde çıktığında framework tarafından çağırılır.|
|[CWinApp::CloseAllDocuments](#closealldocuments)|Bütün açık belgeleri kapatır.|
|[CWinApp::CreatePrinterDC](#createprinterdc)|Bir yazıcı cihaz bağlamı oluşturur.|
|[CWinApp::DelRegTree](#delregtree)|Belirtilen anahtar ve tüm alt anahtarlarını siler.|
|[CWinApp::DoMessageBox](#domessagebox)|Implements [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) uygulama için.|
|[CWinApp::DoWaitCursor](#dowaitcursor)|Bekleme imleci açıp kapatır.|
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|Uygulama D2D desteği sağlar. Ana pencereyi başlatılmadan önce bu yöntemi çağırın.|
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|WinHelp yerine uygulama için HTMLHelp uygular.|
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|Görev etkileşim sağlar.|
|[CWinApp::ExitInstance](#exitinstance)|Uygulamanızı sonlandırıldığında temizlemek için geçersiz kılın.|
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|Uygulama kurtarma yöntemi giriş parametresi alır.|
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Kurtarma için geri dönmek geri çağırma işlevi yeniden başlatma Yöneticisi bekleyeceği sürenin uzunluğunu döndürür.|
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|Bayrakları için yeniden başlatma Yöneticisi döndürür.|
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|HKEY_CURRENT_USER anahtarı döndürür\\"Yazılım" \RegistryKey\ProfileName.|
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|Uygulamanın bu örneği için veri kurtarma işleyici alır.|
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|Belge şablonu ilk konumunu alır.|
|[CWinApp::GetHelpMode](#gethelpmode)|Uygulama tarafından kullanılan Yardım türünü alır.|
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|Bir belge şablonu konumunu alır. Kullanılan yinelemeli olarak olabilir.|
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|Yazıcı cihazı varsayılanlarını alır.|
|[CWinApp::GetProfileBinary](#getprofilebinary)|Bir uygulamanın girişinde ikili verileri alır. INI dosyası.|
|[CWinApp::GetProfileInt](#getprofileint)|Bir tamsayı uygulamanın bir girdi alır. INI dosyası.|
|[CWinApp::GetProfileString](#getprofilestring)|Bir uygulamanın girişinde bir dize alır. INI dosyası.|
|[CWinApp::GetSectionKey](#getsectionkey)|HKEY_CURRENT_USER anahtarı döndürür\\"Yazılım" \RegistryKey\AppName\lpszSection.|
|[CWinApp::HideApplication](#hideapplication)|Tüm belgeleri kapatmadan önce uygulamayı gizler.|
|[CWinApp::HtmlHelp](#htmlhelp)|Çağrıları `HTMLHelp` Windows işlevi.|
|[Afxenablecontrolcontainer](#initinstance)|Pencere nesnelerinizi oluşturma gibi Windows örneği başlatma gerçekleştirmek için geçersiz kılın.|
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Windows 7 görev etkileşim etkinleştirilip etkinleştirilmeyeceğini belirtir.|
|[CWinApp::LoadCursor](#loadcursor)|İmleç kaynak yükler.|
|[CWinApp::LoadIcon](#loadicon)|Bir simge kaynağı yükler.|
|[CWinApp::LoadOEMCursor](#loadoemcursor)|Yükleri Windows OEM imleç önceden tanımlanmış, **OCR_** sabitleri WINDOWS belirtin. H|
|[CWinApp::LoadOEMIcon](#loadoemicon)|Bir Windows OEM önceden tanımlanmış simge yükler, **OIC_** sabitleri WINDOWS belirtin. H|
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|Yükleri bir Windows imleç önceden tanımlanmış, **IDC_** sabitleri WINDOWS belirtin. H|
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Bir Windows önceden tanımlanmış simge yükler, **IDI_** sabitleri WINDOWS belirtin. H|
|[CWinApp::OnDDECommand](#onddecommand)|Adlı Değişimi (DDE) yanıt olarak dinamik bir veri çerçevesi tarafından komutu yürütün.|
|[CWinApp::OnIdle](#onidle)|Uygulamaya özgü boşta kalma süresi işleme gerçekleştirmek için geçersiz kılın.|
|[CWinApp::OpenDocumentFile](#opendocumentfile)|Bir dosyadan bir belgeyi açmak için framework tarafından çağırılır.|
|[CWinApp::ParseCommandLine](#parsecommandline)|Bağımsız parametreleri ve komut satırı bayrakları ayrıştırır.|
|[CWinApp::PreTranslateMessage](#pretranslatemessage)|Windows işlevleri için dağıtılmadan önce iletileri filtreler [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).|
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|Uygulamaya ulaşmadan önce belirli iletileri kesintiye uğratır.|
|[CWinApp::ProcessShellCommand](#processshellcommand)|Komut satırı bağımsız değişkenleri ve bayrakları işler.|
|[CWinApp::ProcessWndProcException](#processwndprocexception)|Uygulamanın iletiyi ve komut işleyicileri tarafından oluşturulan tüm işlenmeyen özel durumları yakalar.|
|[CWinApp::Register](#register)|Özelleştirilmiş kayıt gerçekleştirir.|
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|Uygulama yeniden başlatma Yöneticisi ile kaydeder.|
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|Yeniden başlatma Yöneticisi uygulama beklenmedik bir şekilde çıkıldı açık dosyalar açana olup olmadığını belirler.|
|[CWinApp::RestartInstance](#restartinstance)|Bir uygulama yeniden başlatma yeniden başlatma Yöneticisi tarafından başlatılan işler.|
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|Uygulama yeniden başlatıldığında yeniden başlatma Yöneticisi'ni otomatik olarak kaydedilmiş dosyaları geri yükler olup olmadığını belirler.|
|[CWinApp::Run](#run)|Varsayılan mesaj döngüsünü çalıştırır. İleti döngüsünden özelleştirmek için geçersiz kılın.|
|[CWinApp::RunAutomated](#runautomated)|Uygulamanın komut satırı testleri **/Automation** seçeneği. Kullanımdan kalktı. Bunun yerine, değeri kullandığınızdan [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) arama sonra [ParseCommandLine](#parsecommandline).|
|[CWinApp::RunEmbedded](#runembedded)|Uygulamanın komut satırı testleri **/Embedding** seçeneği. Kullanımdan kalktı. Bunun yerine, değeri kullandığınızdan [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) arama sonra [ParseCommandLine](#parsecommandline).|
|[CWinApp::SaveAllModified](#saveallmodified)|Değiştirilen tüm belgeleri kaydetmek için kullanıcıya sorar.|
|[CWinApp::SelectPrinter](#selectprinter)|Daha önce bir yazdırma iletişim kutusu ile bir kullanıcı tarafından belirtilen yazıcı seçer.|
|[CWinApp::SetHelpMode](#sethelpmode)|Ayarlar ve bu tür bir uygulama tarafından kullanılan Yardım başlatır.|
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|Yeniden başlatma Yöneticisi beklenmedik şekilde çıkıldı uygulamanın kurtarır olup olmadığını belirler.|
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|Yeniden başlatma Yöneticisi kapanıyorsa düzenli aralıklarla belgeler açık olup olmadığını belirler.|
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|Belirler olmadığını yeniden başlatma Yöneticisi kapanıyorsa tüm açık belgeleri uygulama yeniden başlatıldığında.|
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|Uygulama yeniden başlatma Yöneticisi destekleyip desteklemediğini belirler.|
|[CWinApp::Unregister](#unregister)|Her şeyi tarafından kayıtlı olduğu bilinen kaydını siler `CWinApp` nesne.|
|[CWinApp::WinHelp](#winhelp)|Çağrıları `WinHelp` Windows işlevi.|
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|Uygulamanın içindeki bir girdiye ikili verileri yazar. INI dosyası.|
|[CWinApp::WriteProfileInt](#writeprofileint)|İçinde uygulamanın bir giriş için bir tamsayı yazar. INI dosyası.|
|[CWinApp::WriteProfileString](#writeprofilestring)|İçinde uygulamanın bir giriş için bir dize yazar. INI dosyası.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinApp::EnableShellOpen](#enableshellopen)|Windows Dosya Yöneticisi'nden veri dosyalarını açmak kullanıcının sağlar.|
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|Standart yükler. INI dosyası ayarlarının ve etkinleştirir MRU Listesi özelliği dosya.|
|[CWinApp::OnContextHelp](#oncontexthelp)|SHIFT + F1 Yardım uygulama içinde işler.|
|[CWinApp::OnFileNew](#onfilenew)|Id_fıle_new komutu uygular.|
|[CWinApp::OnFileOpen](#onfileopen)|Id_fıle_open komutu uygular.|
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|Id_fıle_prınt_setup komutu uygular.|
|[CWinApp::OnHelp](#onhelp)|F1 Yardımı (geçerli bağlamı kullanarak) uygulama içinde işler.|
|[CWinApp::OnHelpFinder](#onhelpfinder)|ID_HELP_FINDER ve ıd_default_help komutları işler.|
|[CWinApp::OnHelpIndex](#onhelpindex)|Id_help_ındex komutu işleyen ve varsayılan Yardım konusunun sağlar.|
|[CWinApp::OnHelpUsing](#onhelpusing)|Id_help_usıng komutu işler.|
|[Otomatik olarak InitInstance](#registershellfiletypes)|Uygulamanın tüm belge türü Windows Dosya Yöneticisi ile kaydeder.|
|[CWinApp::SetAppID](#setappid)|Açıkça uygulama kullanıcı modeli kimliği, uygulama için ayarlar. Herhangi bir kullanıcı arabirimi (en iyi uygulama Oluşturucu yerdir) kullanıcıya görüntülenmeden önce bu yöntem çağrılmalıdır.|
|[CWinApp::SetRegistryKey](#setregistrykey)|Uygulama ayarları yerine kayıt defterinde depolanmış neden olur. INİ dosyaları.|
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|Uygulamanın tüm belge türleri ile Windows Dosya Yöneticisi kaydını siler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CWinApp::m_bHelpMode](#m_bhelpmode)|Yardım içeriği modu (SHIFT + F1'e genellikle çağrılır) kullanıcının olup olmadığını gösterir.|
|[CWinApp::m_eHelpType](#m_ehelptype)|Uygulama tarafından kullanılan Yardım türünü belirtir.|
|[CWinApp::m_hInstance](#m_hinstance)|Uygulamanın geçerli örneğini tanımlar.|
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|Uygulama için komut satırını belirtir. boş sonlandırılmış dizeye işaret eder.|
|[CWinApp::m_nCmdShow](#m_ncmdshow)|Nasıl pencere ilk başta gösterilecek belirtir.|
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|OLE sunucusu yerinde etkin olduğunda kapsayıcı uygulamanın ana pencere işaretçisi.|
|[CWinApp::m_pszAppID](#m_pszappid)|Uygulama kullanıcı modeli kimliği|
|[CWinApp::m_pszAppName](#m_pszappname)|Uygulamanın adını belirtir.|
|[CWinApp::m_pszExeName](#m_pszexename)|Uygulama modülü adı.|
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|Uygulamanın Yardım dosyasının yolu.|
|[CWinApp::m_pszProfileName](#m_pszprofilename)|Uygulamanın. INI dosya adı.|
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|Uygulama profili ayarları depolamak için tam kayıt defteri anahtarı belirlemek için kullanılır.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Yeniden başlatma Yöneticisi'ni nasıl davranacağını belirleyen bayrak.|
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|Kapanıyorsa arasındaki milisaniye cinsinden süre uzunluğu.|
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Uygulama için veri kurtarma işleyicisi işaretçisi.|

## <a name="remarks"></a>Açıklamalar

Uygulama nesnesi, uygulamanızın (ve her örneğini) başlatma ve uygulamayı çalıştıran üye işlevleri sağlar.

Microsoft Foundation sınıfları kullanan her bir uygulamanın yalnızca türetilen bir nesne içerebilir `CWinApp`. Bu nesne diğer C++ genel nesneler oluşturulduğunda oluşturulur ve zaten Windows çağırdığında kullanılabilir `WinMain` Microsoft Foundation Class Kitaplığı tarafından sağlanan işlev. Türetilmiş bildirmek `CWinApp` genel düzeyde nesne.

Bir uygulama sınıfından türetilen zaman `CWinApp`, geçersiz kılma [InitInstance](#initinstance) uygulamanın ana pencere nesnesi oluşturmak için üye işlevi.

Ek olarak `CWinApp` üye işlevleri, Microsoft Foundation Class Kitaplığı erişmek için aşağıdaki genel işlevler sağlar, `CWinApp` nesne ve diğer genel bilgiler:

- [AfxGetApp](application-information-and-management.md#afxgetapp) bir işaretçi sağlar `CWinApp` nesne.

- [Afxgetınstancehandle](application-information-and-management.md#afxgetinstancehandle) geçerli uygulama örneği için bir tanıtıcı elde eder.

- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) uygulamanın kaynaklarına yönelik bir tanıtıcı elde eder.

- [AfxGetAppName](application-information-and-management.md#afxgetappname) uygulamanın adını içeren bir dize için bir işaretçi alır. Alternatif olarak, bir işaretçi varsa `CWinApp` nesnesi `m_pszExeName` uygulamanın adı.

Bkz: [CWinApp: uygulama sınıfı](../../mfc/cwinapp-the-application-class.md) hakkında daha fazla bilgi `CWinApp` sınıfı, aşağıdaki genel bir bakış da dahil olmak üzere:

- `CWinApp`-Uygulama Sihirbazı tarafından yazılan kodu türetilmiş.

- `CWinApp`kullanıcının rolde uygulamanızın yürütme sırası.

- `CWinApp`varsayılan üye işlev uygulamaları güçlendirin.

- `CWinApp`ın anahtar geçersiz kılınabilen öğelerle ilgili.

`m_hPrevInstance` Veri üyesi artık yok. Uygulamanın başka bir örneğini çalışıp çalışmadığını belirlemek için adlandırılmış mutex kullanın. Mutex açma başarısız olursa, herhangi bir çalışan uygulama örnekleri vardır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="adddoctemplate"></a>  CWinApp::AddDocTemplate

Bir belge şablonu uygulama tutan kullanılabilir şablonların listesini eklemek için bu üye işlevini çağırın.

```
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>Parametreler

*pTemplate*<br/>
Bir işaretçi `CDocTemplate` eklenecek.

### <a name="remarks"></a>Açıklamalar

Tüm belge şablonları uygulamaya çağırmadan önce eklemelisiniz [RegisterShellFileTypes](#registershellfiletypes).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

##  <a name="addtorecentfilelist"></a>  CWinApp::AddToRecentFileList

Eklemek için bu üye işlevi çağrısı *lpszPathName* MRU dosya listesi.

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Dosya yolu.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız [LoadStdProfileSettings](#loadstdprofilesettings) üye işlevi, bu üye işlevini kullanmadan önce geçerli MRU dosya listesi yüklenemedi.

Bir dosya açar veya bir dosyayı yeni bir adla kaydetmek için Kaydet komutunu yürütür framework bu üye işlevini çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

##  <a name="applicationrecoverycallback"></a>  CWinApp::ApplicationRecoveryCallback

Uygulama beklenmedik bir şekilde çıktığında framework tarafından çağırılır.

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>Parametreler

*lpvParam*<br/>
[in] Gelecekte kullanılmak üzere ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa 0; bir hata oluşursa sıfır.

### <a name="remarks"></a>Açıklamalar

Uygulamanızı yeniden başlatma Yöneticisi destekliyorsa, framework beklenmedik bir şekilde uygulamanız çıkış yaptığında bu işlevi çağırır.

Varsayılan uygulaması `ApplicationRecoveryCallback` kullanan `CDataRecoveryHandler` açık belgelerin listesini kayıt defterine kaydetmek için. Bu yöntem herhangi bir dosya değil otomatik kaydetme yapar.

Davranışını özelleştirmek için bu işlev türetilen bir geçersiz kılma [CWinApp sınıfı](../../mfc/reference/cwinapp-class.md) veya kendi uygulama kurtarma yöntemi için parametre olarak geçirmek [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).

##  <a name="closealldocuments"></a>  CWinApp::CloseAllDocuments

Çıkmadan önce tüm açık belgeleri kapatmak için bu üye işlevini çağırın.

```
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Parametreler

*bEndSession*<br/>
Windows oturum sona olup olmadığını belirtir. Oturum sona erdi, TRUE ise. Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Çağrı [HideApplication](#hideapplication) çağırmadan önce `CloseAllDocuments`.

##  <a name="createprinterdc"></a>  CWinApp::CreatePrinterDC

Seçili yazıcıdan bir yazıcı cihaz bağlamı (DC) oluşturmak için bu üye işlevini çağırın.

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>Parametreler

*DC*<br/>
Bir yazıcı cihaz bağlamına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yazıcı cihaz bağlamı başarıyla oluşturulursa, sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`CreatePrinterDC` yazdırmak üzere kullanabilmeniz için başvuru ile geçirdiğiniz cihaz bağlamını başlatır.

İşlev başarılı ise, yazdırma tamamladıktan sonra cihaz bağlamı imha etmeniz gerekir. Yok edicisinde sağlayabilirsiniz [CDC](../../mfc/reference/cdc-class.md) nesne yapmak veya bunu açıkça çağırarak yapabilirsiniz [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc).

##  <a name="cwinapp"></a>  CWinApp::CWinApp

Oluşturur bir `CWinApp` nesne ve geçişleri *lpszAppName* uygulama adı olarak depolanacak.

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszAppName*<br/>
Windows kullanan uygulama adını içeren bir null ile sonlandırılmış dize. Bu bağımsız değişken sağlanmazsa veya NULL ise `CWinApp` AFX_IDS_APP_TITLE kaynak dizesi veya yürütülebilir dosyasının dosya adını kullanır.

### <a name="remarks"></a>Açıklamalar

Genel bir nesne oluşturmak, `CWinApp`-türetilmiş sınıf. Tek sahip `CWinApp` uygulamanızdaki bir nesne. Oluşturucuya yönelik bir işaretçi depolayan `CWinApp` nesne böylece `WinMain` nesnenin üyesi başlatmak ve uygulamayı çalıştırmak için işlevleri çağırabilir.

##  <a name="delregtree"></a>  CWinApp::DelRegTree

Belirli kayıt defteri anahtarını ve tüm alt anahtarlarını siler.

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
Kayıt defteri anahtarına işleyin.

*strKeyName*<br/>
Silinecek kayıt defteri anahtarı adı.

*pTM*<br/>
CAtlTransactionManager nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürülen değer ERROR_SUCCESS olur. İşlev başarısız olursa, döndürülen değer wınerror içinde tanımlanan bir sıfır olmayan hata kodudur.

### <a name="remarks"></a>Açıklamalar

Belirtilen anahtarı ve onun alt anahtarlarında silmek için bu işlevi çağırın.

##  <a name="domessagebox"></a>  CWinApp::DoMessageBox

Framework genel işlevine yönelik bir ileti kutusu uygulamak için bu üye işlevi çağıran [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox).

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>Parametreler

*lpszPrompt*<br/>
İleti kutusu metni adresi.

*nTür*<br/>
İleti kutusu [stil](../../mfc/reference/styles-used-by-mfc.md#message-box-styles).

*nIDPrompt*<br/>
Yardım içerik dizesi için bir dizin.

### <a name="return-value"></a>Dönüş Değeri

Aynı değerleri döndürür `AfxMessageBox`.

### <a name="remarks"></a>Açıklamalar

Bir ileti kutusu açmak için bu üye işlevini çağırmayın; kullanma `AfxMessageBox` yerine.

Bu üye işlevi, birçok farklı uygulama işlenmesini özelleştirmek için geçersiz kılma `AfxMessageBox` çağırır.

##  <a name="dowaitcursor"></a>  CWinApp::DoWaitCursor

Bu üye işlevi uygulamak için framework tarafından çağrılan [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), ve [ CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>Parametreler

*nCode*<br/>
Bu parametre, 1 ise, bekleme imlecini görünür. 0 ise, bekleme imleci başvuru sayısını artırmadan geri yüklenir. -1, bekleme imleci sona erer.

### <a name="remarks"></a>Açıklamalar

Varsayılan bir kum saati imleç uygular. `DoWaitCursor` bir başvuru sayısını tutar. Pozitif, imleci kum saati gösterilir.

Değil normalde çağırırsınız sırada `DoWaitCursor` doğrudan bekleme imleci değiştirmek için ya da bekleme imleci görüntülenirken ek işleme yapmak için bu üye işlevi geçersiz.

Bekleme imlecini uygulamak bir kolay, daha kolay şekilde için kullanmak `CWaitCursor`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

##  <a name="enabled2dsupport"></a>  CWinApp::EnableD2DSupport

Visual Studio 2010 SP1 gereklidir.

Uygulama D2D desteği sağlar. Ana pencereyi başlatılmadan önce bu yöntemi çağırın.

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Parametreler

*d2dFactoryType*<br/>
D2D Fabrika ve kaynakları iş parçacığı modeli oluşturur.

*writeFactoryType*<br/>
Yazma üretecini paylaşılan veya yalıtılmış olup olmadığını belirten bir değeri

### <a name="return-value"></a>Dönüş Değeri

D2D destek aksi etkinleştirilmişse, FALSE - ise TRUE döndürür

##  <a name="enablehtmlhelp"></a>  CWinApp::EnableHtmlHelp

Oluşturucusunun içinde bu üye işlevini çağırın, `CWinApp`-türetilmiş sınıf HTMLHelp uygulamanızın yardım için kullanılacak.

```
void EnableHtmlHelp();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="enableshellopen"></a>  CWinApp::EnableShellOpen

Bu işlev, genellikle çağırmanıza, `InitInstance` bunlar içinde Windows Dosya Yöneticisi dosyalarından çift tıkladığınızda, veri dosyalarını açmak, uygulamanızın kullanıcıları etkinleştirmek için geçersiz kılma.

```
void EnableShellOpen();
```

### <a name="remarks"></a>Açıklamalar

Çağrı `RegisterShellFileTypes` üye bu işlevle birlikte çalışması veya sağlayan bir. Belge türü el ile kayıt için REG dosyası uygulamanızla.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

##  <a name="enabletaskbarinteraction"></a>  CWinApp::EnableTaskbarInteraction

Görev etkileşim sağlar.

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
Windows 7 görev etkileşim (TRUE) etkinleştirilmesi gerekir veya devre dışı (FALSE) olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Görev etkileşim etkin veya devre dışı, TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ana pencereyi oluşturulmasını önce çağrılmalıdır, aksi takdirde, onaylar ve false değerini döndürür.

##  <a name="exitinstance"></a>  CWinApp::ExitInstance

İçinden framework tarafından çağırılır `Run` uygulamanın bu örneği çıkmak için üye işlevi.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın çıkış kodu; 0 hata olduğunu gösterir ve değerleri 0'dan büyük bir hata gösterir. Bu değer, dönüş değeri olarak kullanılır `WinMain`.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi ancak içinde her yerden çağırmayın `Run` üye işlevi.

Bu işlev varsayılan uygulamasını framework seçenekleri uygulamanın yazar. INI dosyası. Bu işlev uygulamanızı sonlandırıldığında temizlemek için geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

##  <a name="getapplicationrecoveryparameter"></a>  CWinApp::GetApplicationRecoveryParameter

Uygulama kurtarma yöntemi giriş parametresi alır.

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama kurtarma yöntemi için varsayılan giriş parametresi.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan davranışını NULL döndürür.

Daha fazla bilgi için [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).

##  <a name="getapplicationrecoverypinginterval"></a>  CWinApp::GetApplicationRecoveryPingInterval

Kurtarma için geri dönmek geri çağırma işlevi yeniden başlatma Yöneticisi bekleyeceği sürenin uzunluğunu döndürür.

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>Dönüş Değeri

Sürenin milisaniye cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

İle yeniden başlatma Yöneticisi çıkar beklenmedik bir şekilde kayıtlı bir uygulama, uygulama açık belgeleri kaydetmek çalışır ve Kurtarma geri çağırma işlevini çağırır. Varsayılan kurtarma geri çağırma işlevidir [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).

Kurtarma için geri dönmek geri çağırma işlevi framework bekleyeceği sürenin uzunluğunu ping aralığıdır. Ping aralığı geçersiz kılarak özelleştirebileceğiniz `CWinApp::GetApplicationRecoveryPingInterval` veya özel bir değere sağlayarak `RegisterWithRestartManager`.

##  <a name="getapplicationrestartflags"></a>  CWinApp::GetApplicationRestartFlags

Bayrakları için yeniden başlatma Yöneticisi döndürür.

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>Dönüş Değeri

Yeniden başlatma Yöneticisi işaretler. Varsayılan uygulama, 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma Yöneticisi bayrakları bir varsayılan uygulama etkisi yoktur. Bunlar, gelecekte kullanılmak üzere sağlanır.

Kullanarak uygulama yeniden başlatma Yöneticisi ile kaydettiğinizde bayrakları ayarlanmış [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).

Yeniden başlatma Yöneticisi bayrakları için olası değerler aşağıdaki gibidir:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="getappregistrykey"></a>  CWinApp::GetAppRegistryKey

HKEY_CURRENT_USER anahtarı döndürür\\"Yazılım" \RegistryKey\ProfileName.

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*pTM*<br/>
İşaretçi bir `CAtlTransactionManager` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa uygulama anahtarı bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

##  <a name="getdatarecoveryhandler"></a>  CWinApp::GetDataRecoveryHandler

Uygulamanın bu örneği için veri kurtarma işleyici alır.

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın bu örneği için veri kurtarma işleyici.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma Yöneticisi'ni kullanan her bir uygulamanın bir örneğine sahip olması [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md). Bu sınıf, açık belgeler veya otomatik kaydetmeyi dosyaları izlemekten sorumludur. Davranışını `CDataRecoveryHandler` yeniden başlatma yöneticisinin yapılandırmasına bağlıdır. Daha fazla bilgi için [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md).

Bu yöntem, Windows Vista öncesi işletim sistemlerinde NULL değer döndürür. Yeniden başlatma Yöneticisi Windows Vista öncesi işletim sistemlerinde desteklenmiyor.

Uygulama şu anda veri kurtarma işleyicisi sahip değilse bu yöntem bir tane oluşturur ve bir işaretçi döndürür.

##  <a name="getfirstdoctemplateposition"></a>  CWinApp::GetFirstDocTemplatePosition

Uygulama ilk belge şablonu konumunu alır.

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılan konum değeri; Liste boş ise NULL değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bir çağrıda döndürülen konum değer kullanım [GetNextDocTemplate](#getnextdoctemplate) ilk almak için [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesne.

##  <a name="gethelpmode"></a>  CWinApp::GetHelpMode

Uygulama tarafından kullanılan Yardım türünü alır.

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama tarafından kullanılan Yardım türü. Bkz: [CWinApp::m_eHelpType](#m_ehelptype) daha fazla bilgi için.

##  <a name="getnextdoctemplate"></a>  CWinApp::GetNextDocTemplate

Tarafından tanımlanan belge şablonunu alır *pos*, ardından ayarlar *pos* konum değeri.

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen bir konum değeri başvurusu `GetNextDocTemplate` veya [GetFirstDocTemplatePosition](#getfirstdoctemplateposition). Değer, bu çağrı tarafından sonraki konumuna güncelleştirilir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz `GetNextDocTemplate` çağrısıyla ilk konumunu kurarsanız ileriye doğru yineleme döngüsünde `GetFirstDocTemplatePosition`.

KONUM değeri, geçerli olduğundan emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

En son alınan belge şablonunu ise kullanılabilir, ardından yeni değeri *pos* NULL olarak ayarlandı.

##  <a name="getprinterdevicedefaults"></a>  CWinApp::GetPrinterDeviceDefaults

Bir yazıcıya yazdırma için cihaz bağlamı hazırlamak için bu üye işlevini çağırın.

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>Parametreler

*pPrintDlg*<br/>
Bir işaretçi bir [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Geçerli bir yazıcı varsayılan Windows alır. INI gerektiğinde dosya veya yazdırma kurulumunda bir kullanıcı tarafından ayarlanan son yazıcı yapılandırmasını kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

##  <a name="getprofilebinary"></a>  CWinApp::GetProfileBinary

Uygulamanın kayıt defteri belirtilen bölümü içindeki bir giriş ikili verileri almak için bu üye işlevini çağırın veya. INI dosyası.

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Giriş içeren bölümü belirten bir boş sonlandırılmış dizeye işaret eder.

*lpszEntry*<br/>
Değeri alınacak girdisi içeren bir boş sonlandırılmış dizeye işaret eder.

*ppData*<br/>
Verilerin adresi alacak bir işaretçi işaret eder.

*pBytes*<br/>
Veri (bayt cinsinden) boyutunu alacak bir UINT işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi büyük/küçük harfe duyarlı, bu nedenle değil dizelerde *lpszSection* ve *lpszEntry* parametreleri durumda farklı olabilir.

> [!NOTE]
> `GetProfileBinary` bir arabelleği ayırır ve onun adresini döndürür \* *ppData*. Arabellek kullanarak boşaltma için çağıran sorumludur **delete []**.

> [!IMPORTANT]
> Bu işlev tarafından döndürülen veriler sonlandırıldı mutlaka NULL değil ve çağıran doğrulaması gerçekleştirmeniz gerekir. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

Ek bir örnek için bkz. [CWinApp::WriteProfileBinary](#writeprofilebinary).

##  <a name="getprofileint"></a>  CWinApp::GetProfileInt

Uygulamanın kayıt defteri belirtilen bölümü içindeki bir giriş bir tamsayı değerini almak için bu üye işlevini çağırın veya. INI dosyası.

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Giriş içeren bölümü belirten bir boş sonlandırılmış dizeye işaret eder.

*lpszEntry*<br/>
Değeri alınacak girdisi içeren bir boş sonlandırılmış dizeye işaret eder.

*Nvarsayılan*<br/>
Framework giriş bulamazsanız, döndürülecek varsayılan bir değer belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa izleyen belirtilen giriş dizesini bir tamsayı değeri. Dönüş değeri değeri *Nvarsayılan* işlev giriş bulamazsa parametresi. Belirtilen girişe karşılık gelen değer bir tamsayı değilse, dönüş değeri 0'dır.

Bu üye işlevi onaltılık gösterim değeri destekler. INI dosyası. İmzalı bir tamsayı aldığınızda, değerde atamalısınız bir **int**.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi büyük/küçük harfe duyarlı, bu nedenle değil dizelerde *lpszSection* ve *lpszEntry* parametreleri durumda farklı olabilir.

> [!IMPORTANT]
> Bu işlev tarafından döndürülen veriler sonlandırıldı mutlaka NULL değil ve çağıran doğrulaması gerçekleştirmeniz gerekir. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

Ek bir örnek için bkz. [CWinApp::WriteProfileInt](#writeprofileint).

##  <a name="getprofilestring"></a>  CWinApp::GetProfileString

Uygulamanın kayıt defterinde belirtilen bölüm içinde bir girişi ile ilişkili dizeyi almak için bu üye işlevi çağrısı veya. INI dosyası.

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Giriş içeren bölümü belirten bir boş sonlandırılmış dizeye işaret eder.

*lpszEntry*<br/>
Alınacak olan dize girdisi içeren bir boş sonlandırılmış dizeye işaret eder. Bu değer NULL olmamalıdır.

*lpszDefault*<br/>
Giriş başlatma dosyası bulunamazsa belirtilen giriş için varsayılan dize değerini işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın dizeden dönüş değeridir. INI dosyası veya *lpszDefault* dize bulunamazsa. Framework tarafından desteklenen maksimum dize uzunluğu _MAX_PATH ' dir. Varsa *lpszDefault* , Null dönüş değeri boş bir dizedir.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
> Bu işlev tarafından döndürülen veriler sonlandırıldı mutlaka NULL değil ve çağıran doğrulaması gerçekleştirmeniz gerekir. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Başka bir örnek için örneğin bakın [CWinApp::GetProfileInt](#getprofileint).

##  <a name="getsectionkey"></a>  CWinApp::GetSectionKey

HKEY_CURRENT_USER anahtarı döndürür\\"Yazılım" \RegistryKey\AppName\lpszSection.

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Alınacağı anahtarın adı.

*pTM*<br/>
İşaretçi bir `CAtlTransactionManager` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa bölüm anahtarı bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

##  <a name="hideapplication"></a>  CWinApp::HideApplication

Açık belgeler kapatmadan önce uygulamanın gizlemek için bu üye işlevini çağırın.

```
void HideApplication();
```

##  <a name="htmlhelp"></a>  CWinApp::HtmlHelp

HTMLHelp uygulamasını çağırmak için bu üye işlevini çağırın.

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>Parametreler

*dwData*<br/>
Ek veri belirtir. Kullanılan değer değerine bağlıdır *nCmd* parametresi.

*nCmd*<br/>
Yardım talep türünü belirtir. Olası değerler ve bunların nasıl etkileyeceğini listesini *dwData* parametresi bkz *uCommand* hakkında HTMLHelp API işlevi Windows SDK'sındaki açıklanan parametresi.

### <a name="remarks"></a>Açıklamalar

Framework de HTMLHelp uygulamasını çağırmak için bu işlevi çağırır.

Uygulamanızı sonlandırıldığında framework HTMLHelp uygulama otomatik olarak kapatılacak.

##  <a name="initinstance"></a>  Afxenablecontrolcontainer

Windows, birden çok kopyasını aynı anda çalıştırmak için aynı programın sağlar.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulama başlatma kavramsal olarak iki bölümlere ayrılmıştır: ilk işiniz tek seferlik uygulama başlatma süresi program çalıştırılır ve her çalışan örneği başlatma süresi bir kopyasını ilk kez dahil olmak üzere programı çalıştırır. Framework'ün uygulamasını `WinMain` bu işlevi çağırır.

Geçersiz kılma `InitInstance` uygulamanızın altında Windows çalıştıran her yeni örneği başlatmak için. Genellikle, geçersiz kılmanız `InitInstance` , ana pencere nesnesi oluşturmak ve ayarlamak için `CWinThread::m_pMainWnd` pencereye işaret edecek şekilde veri üyesi. Bu üye işlevi geçersiz kılma hakkında daha fazla bilgi için bkz: [CWinApp: uygulama sınıfı](../../mfc/cwinapp-the-application-class.md).

> [!NOTE]
> MFC uygulamaları tek iş parçacıklı grup (STA) başlatılması gerekir. Eğer [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) içinde `InitInstance` geçersiz kılmak, COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED yerine) belirtin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

##  <a name="istaskbarinteractionenabled"></a>  CWinApp::IsTaskbarInteractionEnabled

Windows 7 görev etkileşim etkinleştirilip etkinleştirilmeyeceğini belirtir.

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür `EnableTaskbarInteraction` çağrıldıktan ve Windows 7 veya üzeri işletim sistemidir.

### <a name="remarks"></a>Açıklamalar

Görev etkileşim MDI uygulaması resimlerde uygulama görev düğmenin üzerine fare işaretçisi olduğunda görüntülenen ayrı sekmeli MDI içeriğini görüntüler anlamına gelir.

##  <a name="loadcursor"></a>  CWinApp::LoadCursor

İmleç kaynak tarafından adlandırılan yükler *lpszResourceName* ya da tarafından belirtilen *nIDResource* geçerli bir yürütülebilir dosya.

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
İmleç kaynağının adını içeren bir boş sonlandırılmış dizeye işaret eder. Kullanabileceğiniz bir `CString` bu bağımsız değişkeni.

*nIDResource*<br/>
İmleç kaynağının kimliği. Kaynakların listesi için bkz. [LoadCursor](/windows/desktop/api/winuser/nf-winuser-loadcursora) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bir imleç için bir tanıtıcı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

`LoadCursor` yalnızca, daha önce yüklenmemiş olan, imleç belleğe; Aksi takdirde, mevcut kaynağı işleyicisini alır.

Kullanım [LoadStandardCursor](#loadstandardcursor) veya [LoadOEMCursor](#loadoemcursor) önceden tanımlanmış bir Windows imleç erişmek için üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

##  <a name="loadicon"></a>  CWinApp::LoadIcon

Tarafından adlandırılan simge kaynağı yükler *lpszResourceName* ya da tarafından belirtilen *nIDResource* yürütülebilir dosya.

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Simge kaynağının adını içeren bir boş sonlandırılmış dizeye işaret eder. Ayrıca bir `CString` bu bağımsız değişkeni.

*nIDResource*<br/>
Simge kaynağı kimliği sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simge tanıtıcı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

`LoadIcon` yalnızca, daha önce yüklenmemiş olan simge yükler; Aksi takdirde, mevcut kaynağı işleyicisini alır.

Kullanabileceğiniz [LoadStandardIcon](#loadstandardicon) veya [LoadOEMIcon](#loadoemicon) önceden tanımlanmış Windows simgeleri erişmek için üye işlevi.

> [!NOTE]
> Bu üye işlevi Win32 API işlevini çağırır [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona), hangi yalnızca yükleyebilirsiniz simge boyutu SM_CXICON ve SM_CYICON sistem ölçüm değerleri için uyar.

##  <a name="loadoemcursor"></a>  CWinApp::LoadOEMCursor

Yükleri Windows imleç kaynak tarafından belirtilen önceden tanımlanmış *nIDCursor*.

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>Parametreler

*nIDCursor*<br/>
Bir **OCR_** önceden tanımlanmış bir Windows imleç belirten sabit tanımlayıcısı bildirim. Olmalıdır `#define OEMRESOURCE` önce `#include \<afxwin.h>` erişim kazanmak için **OCR_** Windows sabitler. H

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bir imleç için bir tanıtıcı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Kullanım `LoadOEMCursor` veya [LoadStandardCursor](#loadstandardcursor) önceden tanımlanmış bir Windows imleç erişmek için üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

##  <a name="loadoemicon"></a>  CWinApp::LoadOEMIcon

Yükleri Windows önceden tanımlanmış simge kaynağı tarafından belirtilen *nIDIcon*.

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>Parametreler

*nIDIcon*<br/>
Bir **OIC_** önceden tanımlanmış bir Windows simge belirten sabit tanımlayıcısı bildirim. Olmalıdır `#define OEMRESOURCE` önce `#include \<afxwin.h>` erişimi **OIC_** Windows sabitler. H

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simge tanıtıcı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Kullanım `LoadOEMIcon` veya [LoadStandardIcon](#loadstandardicon) önceden tanımlanmış Windows simgeleri erişmek için üye işlevi.

##  <a name="loadstandardcursor"></a>  CWinApp::LoadStandardCursor

Yükleri Windows imleç kaynak önceden tanımlanmış, *lpszCursorName* belirtir.

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>Parametreler

*lpszCursorName*<br/>
Bir **IDC_** önceden tanımlanmış bir Windows imleç belirten sabit tanımlayıcısı bildirim. Bu tanımlayıcılar, WİNDOWS'da tanımlanır. H Aşağıdaki liste önceden tanımlanmış değerlerden ve anlamı gösterir *lpszCursorName*:

- IDC_ARROW standart ok imleci

- IDC_IBEAM standart metin ekleme imleci

- Windows zaman alan bir görev gerçekleştirdiğinde kullanılan IDC_WAIT kum saati imleç

- IDC_CROSS artı imleç seçimi

- Doğrudan yukarı bakan IDC_UPARROW oku

- IDC_SIZE eski ve desteklenmeyen; IDC_SIZEALL kullanın

- IDC_SIZEALL bir dört yönlü oka. Bir pencereyi yeniden boyutlandırmak için imleç.

- IDC_ICON eski ve desteklenmeyen. IDC_ARROW kullanın.

- Sol ve sağ alt ucu ile IDC_SIZENWSE iki başlı oka

- Sol üst köşedeki sağ ve alt ucu ile IDC_SIZENESW iki başlı oka

- İki başlı oka IDC_SIZEWE yatay

- İki başlı oka IDC_SIZENS dikey

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bir imleç için bir tanıtıcı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Kullanım `LoadStandardCursor` veya [LoadOEMCursor](#loadoemcursor) önceden tanımlanmış bir Windows imleç erişmek için üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

##  <a name="loadstandardicon"></a>  CWinApp::LoadStandardIcon

Yükleri Windows önceden tanımlanmış simge kaynağı, *lpszIconName* belirtir.

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>Parametreler

*lpszIconName*<br/>
Önceden tanımlanmış bir Windows simge belirten bir bildirim sabit tanımlayıcısı. Bu tanımlayıcılar, WİNDOWS'da tanımlanır. H Önceden tanımlanmış değerlerden ve açıklamalarının listesi için bkz. *lpIconName* parametresinde [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simge tanıtıcı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Kullanım `LoadStandardIcon` veya [LoadOEMIcon](#loadoemicon) önceden tanımlanmış Windows simgeleri erişmek için üye işlevi.

##  <a name="loadstdprofilesettings"></a>  CWinApp::LoadStdProfileSettings

Bu üye işlev içinden çağırmak [InitInstance](#initinstance) etkinleştirmek ve en son kullanılan (MRU) dosya listesi ve en son durumu Önizleme için üye işlevi.

```
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>Parametreler

*nMaxMRU*<br/>
İzlemek için son kullanılan dosya sayısı.

### <a name="remarks"></a>Açıklamalar

Varsa *nMaxMRU* 0 ise, hiçbir MRU Listesi korunur.

##  <a name="m_bhelpmode"></a>  CWinApp::m_bHelpMode

Uygulama (standart olarak çağrılan olan üst karakter + F1); Yardım içeriğini modunda ise TRUE Aksi durumda FALSE.

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>Açıklamalar

Yardım içeriği modunda, bir soru işareti imleç haline gelir ve kullanıcı hakkında ekranı taşıyabilirsiniz. Özel işleme Yardım modundayken uygulamak istiyorsanız, bu bayrak inceleyin. `m_bHelpMode` BOOL türü genel bir değişkendir.

##  <a name="m_dwrestartmanagersupportflags"></a>  CWinApp::m_dwRestartManagerSupportFlags

Yeniden başlatma Yöneticisi'ni nasıl davranacağını belirleyen bayrak.

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma Yöneticisi'ni etkinleştirmek için `m_dwRestartManagerSupportFlags` istediğiniz davranışı. Aşağıdaki tabloda kullanılabilir bayrakları gösterilmektedir.

|||
|-|-|
|Bayrağı|Açıklama|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|Uygulamayı kullanarak kayıtlı [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager). Beklenmedik bir şekilde çıkarsa, bir uygulamayı yeniden başlatma için yeniden başlatma Yöneticisi sorumludur.|
|-AFX_RESTART_MANAGER_SUPPORT_RECOVERY|Uygulama yeniden başlatma Yöneticisi ile kaydedilir ve uygulama yeniden başlatıldığında, yeniden başlatma Yöneticisi Kurtarma geri çağırma işlevini çağırır. Varsayılan kurtarma geri çağırma işlevidir [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|-AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|Otomatik kaydetme etkinleştirilmişse ve yeniden başlatma Yöneticisi kapanıyorsa tüm açık belgeleri uygulama yeniden başlatıldığında.|
|-AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|Otomatik kaydetme etkinleştirilmişse ve yeniden başlatma Yöneticisi kapanıyorsa düzenli aralıklarla tüm açık belgeleri. Aralığı tarafından tanımlanan [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval).|
|-AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|Yeniden başlatma Yöneticisi, daha önce açık belgeler beklenmeyen bir çıkış uygulamadan yeniden başlattıktan sonra açılır. [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md) açık belgelerin listesini depolamak ve bunları geri işler.|
|-AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|Yeniden başlatma Yöneticisi uygulama yeniden başlatıldıktan sonra otomatik olarak kaydedilmiş dosyaları geri yükleme için kullanıcıya sorar. `CDataRecoveryHandler` Sınıfı kullanıcı sorgular.|
|-AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|AFX_RESTART_MANAGER_SUPPORT_RESTART AFX_RESTART_MANAGER_SUPPORT_RECOVER ve AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES birleşimi.|
|-AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL ve AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES birleşimi.|
|-AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES ve AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES birleşimi.|
|-AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|Birleşim ofAFX_RESTART_MANAGER_SUPPORT_RECOVERY, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES ve AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|

##  <a name="m_ehelptype"></a>  CWinApp::m_eHelpType

Bu veri üyesi numaralandırılmış tür içinde tanımlanan AFX_HELP_TYPE türüdür `CWinApp` sınıfı.

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>Açıklamalar

AFX_HELP_TYPE numaralandırması şu şekilde tanımlanır:

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- HTML Yardımı için uygulamanın Yardım ayarlamak için çağrı [SetHelpMode](#sethelpmode) belirtin `afxHTMLHelp`.

- WinHelp uygulamanın Yardım ayarlamak için çağrı `SetHelpMode` belirtin `afxWinHelp`.

##  <a name="m_hinstance"></a>  CWinApp::m_hInstance

Karşılık gelen *HINSTANCE* parametresi geçirilmesi için Windows tarafından `WinMain`.

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>Açıklamalar

`m_hInstance` Veri üyesi olan Windows altında çalışan uygulamanın geçerli örneği için bir tanıtıcı. Bu genel işlevin döndürdüğü [Afxgetınstancehandle](application-information-and-management.md#afxgetinstancehandle). `m_hInstance` HINSTANCE türünde genel bir değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

##  <a name="m_lpcmdline"></a>  CWinApp::m_lpCmdLine

Karşılık gelen *lpCmdLine* parametresi geçirilmesi için Windows tarafından `WinMain`.

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>Açıklamalar

Uygulama için komut satırını belirtir. boş sonlandırılmış dizeye işaret eder. Kullanım `m_lpCmdLine` herhangi bir komut satırı bağımsız değişkeni, uygulama başlatıldığında girilen kullanıcı erişmek için. `m_lpCmdLine` tür LPTSTR genel bir değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="m_nautosaveinterval"></a>  CWinApp::m_nAutosaveInterval

Kapanıyorsa arasındaki milisaniye cinsinden süre uzunluğu.

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>Açıklamalar

Belirli aralıklarla otomatik kaydetme açık belgeler için yeniden başlatma Yöneticisi'ni yapılandırabilirsiniz. Uygulamanız otomatik kaydetme dosyaları değil varsa, bu parametre bir etkisi yoktur.

##  <a name="m_ncmdshow"></a>  CWinApp::m_nCmdShow

Karşılık gelen *nCmdShow* parametresi geçirilmesi için Windows tarafından `WinMain`.

```
int m_nCmdShow;
```

### <a name="remarks"></a>Açıklamalar

Geçirmeniz `m_nCmdShow` çağırdığınızda bir bağımsız değişken olarak [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) uygulamanızın ana penceresi için. `m_nCmdShow` türü genel değişkenidir **int**.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

##  <a name="m_pactivewnd"></a>  CWinApp::m_pActiveWnd

Bu veri üyesi, OLE sunucusu uygulama etkinleştirildi yerinde OLE kapsayıcı uygulamanın ana penceresi için bir işaretçi depolamak için kullanın.

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi NULL ise, uygulama yerinde etkin değil.

Çerçeve penceresi yerinde bir OLE kapsayıcı uygulama tarafından etkinleştirilmiş olduğunda framework bu üye değişkenini ayarlar.

##  <a name="m_pdatarecoveryhandler"></a>  CWinApp::m_pDataRecoveryHandler

Uygulama için veri kurtarma işleyicisi işaretçisi.

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>Açıklamalar

Bir uygulamanın veri kurtarma işleyicisi izler açık belgeler veya kapanıyorsa bunları. Çerçeve, beklenmedik bir şekilde çıktıktan sonra bir uygulama başlatıldığında otomatik olarak kaydedilmiş dosyaları geri yüklemek için veri kurtarma işleyicisi kullanır. Daha fazla bilgi için [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md).

##  <a name="m_pszappname"></a>  CWinApp::m_pszAppName

Uygulamanın adını belirtir.

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>Açıklamalar

Uygulama adı için geçirilen parametre gelebilir [CWinApp](#cwinapp) Oluşturucusu veya kaynak dizesi, kimliği AFX_IDS_APP_TITLE ile belirtilmezse. Uygulama adı, kaynak bulunmazsa, programın gelir. EXE dosya adı.

Genel işlevin döndürdüğü [AfxGetAppName](application-information-and-management.md#afxgetappname). `m_pszAppName` türü genel değişkenidir **const char**<strong>\*</strong>.

> [!NOTE]
> Bir değer atamanız durumunda `m_pszAppName`, yığında dinamik olarak ayrılmalıdır. `CWinApp` Yıkıcı çağrıları **ücretsiz**(this işaretçisi ile). Çoğu kullanmak istediğiniz `_tcsdup`ayırma yapmak için çalışma zamanı kitaplığı işlevi (). Ayrıca, yeni bir değer atamadan önce geçerli bir işaretçi ile ilişkilendirilmiş bellek boşaltın. Örneğin:

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

##  <a name="m_pszexename"></a>  CWinApp::m_pszExeName

Uzantısız uygulamanın yürütülebilir dosya adını içerir.

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>Açıklamalar

Farklı [m_pszAppName](#m_pszappname), bu adı boşluk içeremez. `m_pszExeName` türü genel değişkenidir **const char**<strong>\*</strong>.

> [!NOTE]
> Bir değer atamanız durumunda `m_pszExeName`, yığında dinamik olarak ayrılmalıdır. `CWinApp` Yıkıcı çağrıları **ücretsiz**(this işaretçisi ile). Çoğu kullanmak istediğiniz `_tcsdup`ayırma yapmak için çalışma zamanı kitaplığı işlevi (). Ayrıca, yeni bir değer atamadan önce geçerli bir işaretçi ile ilişkilendirilmiş bellek boşaltın. Örneğin:

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

##  <a name="m_pszhelpfilepath"></a>  CWinApp::m_pszHelpFilePath

Uygulamanın Yardım dosyasının yolunu içerir.

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve başlatır `m_pszHelpFilePath` uygulama adına ". HLP"eklenir. Yardım dosyası adını değiştirmek için Ayarla `m_pszHelpFilePath` istenen Yardım dosyasının tam adı içeren bir dize için yönlendirin. Bunu yapmak için kullanışlı bir uygulamanın yerdir [InitInstance](#initinstance) işlevi. `m_pszHelpFilePath` türü genel değişkenidir **const char**<strong>\*</strong>.

> [!NOTE]
> Bir değer atamanız durumunda `m_pszHelpFilePath`, yığında dinamik olarak ayrılmalıdır. `CWinApp` Yıkıcı çağrıları **ücretsiz**(this işaretçisi ile). Çoğu kullanmak istediğiniz `_tcsdup`ayırma yapmak için çalışma zamanı kitaplığı işlevi (). Ayrıca, yeni bir değer atamadan önce geçerli bir işaretçi ile ilişkilendirilmiş bellek boşaltın. Örneğin:

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

##  <a name="m_pszprofilename"></a>  CWinApp::m_pszProfileName

Uygulamanın adını içerir. INI dosyası.

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>Açıklamalar

`m_pszProfileName` türü genel değişkenidir **const char**<strong>\*</strong>.

> [!NOTE]
> Bir değer atamanız durumunda `m_pszProfileName`, yığında dinamik olarak ayrılmalıdır. `CWinApp` Yıkıcı çağrıları **ücretsiz**(this işaretçisi ile). Çoğu kullanmak istediğiniz `_tcsdup`ayırma yapmak için çalışma zamanı kitaplığı işlevi (). Ayrıca, yeni bir değer atamadan önce geçerli bir işaretçi ile ilişkilendirilmiş bellek boşaltın. Örneğin:

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

##  <a name="m_pszregistrykey"></a>  CWinApp::m_pszRegistryKey

Kayıt defteri veya INI dosyası, uygulama profili ayarları, depolanan belirlemek için kullanılır.

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>Açıklamalar

Normalde, bu veri üyesi, salt okunur olarak kabul edilir.

- Değer bir kayıt defteri anahtarında depolanır. Uygulama profili ayarının adını aşağıdaki kayıt defteri anahtarı eklenir: HKEY_CURRENT_USER/yazılım/LocalAppWizard tarafından üretilen /.

Bir değer atamanız durumunda `m_pszRegistryKey`, yığında dinamik olarak ayrılmalıdır. `CWinApp` Yıkıcı çağrıları **ücretsiz**(this işaretçisi ile). Çoğu kullanmak istediğiniz `_tcsdup`ayırma yapmak için çalışma zamanı kitaplığı işlevi (). Ayrıca, yeni bir değer atamadan önce geçerli bir işaretçi ile ilişkilendirilmiş bellek boşaltın. Örneğin:

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

##  <a name="m_pszappid"></a>  CWinApp::m_pszAppID

Uygulama kullanıcı modeli kimliği

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="oncontexthelp"></a>  CWinApp::OnContextHelp

SHIFT + F1 Yardım uygulama içinde işler.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Açıklamalar

Eklemelisiniz bir `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` deyimi, `CWinApp` sınıf ileti eşlemesi ve Hızlandırıcı tablosu girişini, genellikle üst karakter + bu üye işlevini etkinleştirmek için F1, ayrıca ekleyin.

`OnContextHelp` Yardım modu uygulamaya koyar. İmleç değişiklikleri bir ok, soru işareti ve kullanıcının fare işaretçisini ve bir iletişim kutusu, pencere, menü ya da komut düğmesi seçmek için farenin sol düğmesine basın. Bu üye işlevi, imleç altındaki Nesne Yardım içeriğini alır ve bu Yardım bağlamı ile Windows WinHelp işlevini çağırır.

##  <a name="onddecommand"></a>  CWinApp::OnDDECommand

Ana çerçeve penceresine DDE aldığında framework tarafından çağırılır. ileti yürütün.

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>Parametreler

*lpszCommand*<br/>
Uygulama tarafından alınan DDE komut dizesi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Komut işlenen olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, komutu bir belgeyi açmak için bir istek ve bu durumda, belirtilen belge açılır olup olmadığını denetler. Kullanıcı bir veri dosyası tıkladığında Windows Dosya Yöneticisi gibi DDE komut dizeleri genellikle gönderir. Geçersiz kılma diğer DDE işlemek için bu işlevi yazdırmak için komutu gibi komutları yürütün.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

##  <a name="onfilenew"></a>  CWinApp::OnFileNew

Id_fıle_new komutu uygular.

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>Açıklamalar

Eklemelisiniz bir `ON_COMMAND( ID_FILE_NEW, OnFileNew )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Etkinleştirilirse, bu işlev, dosya yeni komutunun yürütülmesi işler.

Bkz: [Teknik Not 22](../../mfc/tn022-standard-commands-implementation.md) varsayılan davranışı ve bu üye işlevi geçersiz kılma hakkında yönergeler hakkında bilgi için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileopen"></a>  CWinApp::OnFileOpen

Id_fıle_open komutu uygular.

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>Açıklamalar

Eklemelisiniz bir `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Etkinleştirilirse, bu işlev, Dosya Aç komutunun yürütülmesi işler.

Varsayılan davranış hakkında bilgi ve bu üye işlevi geçersiz kılma hakkında yönergeler için bkz: [Teknik Not 22](../../mfc/tn022-standard-commands-implementation.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileprintsetup"></a>  CWinApp::OnFilePrintSetup

Id_fıle_prınt_setup komutu uygular.

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>Açıklamalar

Eklemelisiniz bir `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Etkinleştirilirse, bu işlev dosya yazdırma komutun yürütülmesi işler.

Varsayılan davranış hakkında bilgi ve bu üye işlevi geçersiz kılma hakkında yönergeler için bkz: [Teknik Not 22](../../mfc/tn022-standard-commands-implementation.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onhelp"></a>  CWinApp::OnHelp

F1 Yardımı (geçerli bağlamı kullanarak) uygulama içinde işler.

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>Açıklamalar

Genellikle bir kısayol tuşu giriş için F1 tuşuna ekleyeceksiniz. Yalnızca bir kural, bir gereksinim F1 tuşuna etkinleştirmektir.

Eklemelisiniz bir `ON_COMMAND( ID_HELP, OnHelp )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Kullanıcı F1 tuşuna bastığında etkinleştirildiğinde framework tarafından çağırılır.

Bu ileti işleyicisi işlevin varsayılan uygulama, Yardım bağlamında geçerli pencere, iletişim kutusu veya menü öğesi için karşılık gelen ve ardından WINHELP çağıran belirler. EXE. Şu anda kullanılabilir içeriği yok ise, işlev varsayılan bağlamı kullanır.

Pencere, iletişim kutusu, menü öğesi veya o anda odağı içeren bir araç çubuğu düğmesi dışında Yardım bağlamı için bir şey ayarlamak için bu üye işlevi geçersiz kılar. Çağrı `WinHelp` istenen Yardım içerik kimliği

##  <a name="onhelpfinder"></a>  CWinApp::OnHelpFinder

ID_HELP_FINDER ve ıd_default_help komutları işler.

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>Açıklamalar

Eklemelisiniz bir `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Uygulamanızın kullanıcı çağrılacak yardımcı Bulucu komutu seçtiğinde etkinleştirilirse, framework bu ileti işleyicisi işlevini çağıran `WinHelp` standart **HELP_FINDER** konu.

##  <a name="onhelpindex"></a>  CWinApp::OnHelpIndex

Id_help_ındex komutu işleyen ve varsayılan Yardım konusunun sağlar.

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>Açıklamalar

Eklemelisiniz bir `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Uygulamanızın kullanıcı çağrılacak Yardım dizin komutu seçtiğinde etkinleştirilirse, framework bu ileti işleyicisi işlevini çağıran `WinHelp` standart **HELP_INDEX** konu.

##  <a name="onhelpusing"></a>  CWinApp::OnHelpUsing

Id_help_usıng komutu işler.

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>Açıklamalar

Eklemelisiniz bir `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Uygulamanızın kullanıcı çağırmak için Yardım'ı kullanarak komutu seçtiğinde framework bu ileti işleyicisi işlevini çağıran `WinHelp` standart uygulama **HELP_HELPONHELP** konu.

##  <a name="onidle"></a>  CWinApp::OnIdle

Boşta kalma süresi işleme gerçekleştirmek için bu üye işlevini geçersiz kılar.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Parametreler

*lCount*<br/>
Her bir sayaç artırılır `OnIdle` uygulamanın ileti kuyruğu boş olduğunda çağrılır. Bu sayı, yeni bir ileti işlendiği her zaman 0 olarak sıfırlanır. Kullanabileceğiniz *lCount* göreli uygulama işlenirken boş bir ileti olmadan sürenin uzunluğunu belirlemek için parametre.

### <a name="return-value"></a>Dönüş Değeri

Daha fazla boşta işleme süresi almak için sıfır olmayan; Daha fazla boşta kalma süresi gerekliyse 0.

### <a name="remarks"></a>Açıklamalar

`OnIdle` Varsayılan ileti döngüsü içinde uygulamanın ileti kuyruğu boş olduğunda çağrılır. Boşta işleyici görevler kendi arka plan çağırmak için geçersiz kılma kullanın.

`OnIdle` boş kalma işleme süresi gerekli olduğunu belirtmek için 0 döndürmelidir. *LCount* parametresi her zaman artırılır `OnIdle` ileti kuyruğu boş ve yeni bir ileti işlendiği her zaman 0 değerine Sıfırlanan çağrılır. Bu sayısına göre farklı boşta yordamları çağırabilirsiniz.

Boşta çevrim işleme özetlenmektedir:

1. Microsoft Foundation Class Kitaplığı'ndaki ileti döngüsü ileti sırasını denetler ve iletileri yok bulur, çağrı `OnIdle` uygulama nesnesi ve kaynakları 0 olarak *lCount* bağımsız değişken.

2. `OnIdle` Bazı işleme gerçekleştirir ve belirtmek için sıfır olmayan bir değer çağrılabilir yeniden yapmak için döndürür. daha fazla işleme.

3. İleti kuyruğuna bir ileti döngüsü yeniden denetler. İleti bekleyen ise çağırdığı `OnIdle` yeniden artan *lCount* bağımsız değişken.

4. Sonuç olarak, `OnIdle` boşta tüm görevleri işlemeyi tamamladığında ve 0 döndürür. Bu çağırma durdurmak için ileti döngüsü bildirir `OnIdle` sonraki iletiyi ileti sırasından alınana kadar bu noktada boşta döngü bağımsız değişkeni 0 olarak belirlenmiş ile yeniden başlatır.

Uzun süren görevleri sırasında gerçekleştirmeyin `OnIdle` uygulamanızın kullanıcı girişi kadar işleyemediği `OnIdle` döndürür.

> [!NOTE]
> Varsayılan uygulaması `OnIdle` güncelleştirmeleri komutunu menü öğeleri ve araç çubuğu düğmeleri gibi kullanıcı arabirimi nesneleri ve iç veri yapısı temizleme gerçekleştirir. Bu nedenle, kılarsanız `OnIdle`, çağırmalısınız `CWinApp::OnIdle` ile `lCount` geçersiz kılınan sürümünüzde. Tüm taban sınıfı boşta işleme çağırın (diğer bir deyişle, temel sınıf kadar `OnIdle` 0 döndürür). Temel sınıf işlem tamamlanmadan önce iş gerçekleştirmeniz gerekiyorsa, uygun seçmek için temel sınıf uygulamasını gözden *lCount* sırasında iş yapmak.

İstemiyorsanız, `OnIdle` ileti kuyruğundan alınan bir ileti olduğunda çağrılacak, kılabilirsiniz [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage). Uygulamanın çok kısa bir zamanlayıcı ayarlarsanız ya da sistem sonra WM_SYSTIMER iletisi göndererek `OnIdle` sürekli olarak adlandırılır ve performansı düşebilir.

### <a name="example"></a>Örnek

Aşağıdaki iki örnek nasıl kullanılacağını göstermek `OnIdle`. İlk örnek kullanarak iki boşta görevleri işler *lCount* görevleri önceliğini belirlemek için bağımsız değişken. Yüksek öncelikli ilk görevdir ve mümkün olduğunca yapmanız gerekir. İkinci görev, daha az önemlidir ve yalnızca kullanıcı girişi, uzun bir duraklama olduğunda yapılması gerekir. Temel sınıf sürümü çağrısı Not `OnIdle`. İkinci örnek birtakım farklı önceliklere sahip boşta görevlerini yönetir.

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

##  <a name="opendocumentfile"></a>  CWinApp::OpenDocumentFile

Framework adlandırılmış açmak için bu yöntemi çağırır [CDocument](../../mfc/reference/cdocument-class.md) uygulamanın dosyası.

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
[in] Açılması için dosyanın adı.

*bAddToMRU*<br/>
[in] Belgenin en son dosyaları biri TRUE gösterir; FALSE, belge en son dosyalardan biri değil gösterir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CDocument` başarılı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu ada sahip bir belge zaten açıksa, bu belgeyi içeren ilk çerçeve penceresinde odağı alırsınız. Bir uygulama birden çok belge şablonu destekliyorsa, framework belge denemek için uygun bir belge şablonu bulmak için dosya adı uzantısını kullanır. Başarılı olursa, belge şablonunu sonra bir çerçeve penceresi ve belge görünümü oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="parsecommandline"></a>  CWinApp::ParseCommandLine

Komut satırını Ayrıştır ve parametreleri teker teker çok göndermek için bu üye işlevi çağrısı [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam).

```
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Parametreler

*rCmdInfo*<br/>
Bir başvuru bir [Ccommandlineınfo](../../mfc/reference/ccommandlineinfo-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Uygulama Sihirbazı'nı kullanarak yeni bir MFC projesi başlattığınızda, Uygulama Sihirbazı'nı yerel bir örneğini oluşturur `CCommandLineInfo`ve sonra çağrı `ProcessShellCommand` ve `ParseCommandLine` içinde [InitInstance](#initinstance) üye işlevi. Bir komut satırı aşağıda açıklanan yol aşağıdaki gibidir:

1. Oluşturulmakta sonra `InitInstance`, `CCommandLineInfo` nesnesi `ParseCommandLine`.

2. `ParseCommandLine` Daha sonra çağırır `CCommandLineInfo::ParseParam` art arda, her parametre için bir kez.

3. `ParseParam` doldurur `CCommandLineInfo` ardından geçirilen nesne [ProcessShellCommand](#processshellcommand).

4. `ProcessShellCommand` komut satırı bağımsız değişkenleri ve bayrakları işler.

Çağırabilirsiniz Not `ParseCommandLine` doğrudan gerektiğinde.

Komut satırı bayrakları açıklaması için bkz: [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).

##  <a name="pretranslatemessage"></a>  CWinApp::PreTranslateMessage

Windows işlevleri için dağıtılmadan önce Filtre pencere iletileri için bu işlevi geçersiz kılma [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) kısayol tuşu varsayılan uygulama gerçekleştirir çağırmanız gerekir böylece çeviri `CWinApp::PreTranslateMessage` geçersiz kılınan sürümünüzde üye işlevi.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
Bir işaretçi bir [MSG](../../mfc/reference/msg-structure1.md) işlemek için bir ileti içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

İleti tam olarak işlendiği olursa sıfır dışı `PreTranslateMessage` ve daha fazla işlenmemesi. İleti normal yolla işleneceğini olursa sıfır.

##  <a name="processmessagefilter"></a>  CWinApp::ProcessMessageFilter

Bu üye işlevi, belirli Windows iletilere yanıt verir ve filtre framework'ün kanca işlevini çağırır.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*Kod*<br/>
Kanca kodu belirtir. Bu üye işlevi kod nasıl işleneceğini belirlemek için kullanır. *lpMsg.*

*lpMsg*<br/>
Bir Windows işaretçisi [MSG](../../mfc/reference/msg-structure1.md) yapısı.

### <a name="return-value"></a>Dönüş Değeri

İleti işleme olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulamanın normal ileti gönderilmeden önce olayları bir kanca işlevini işler işleme.

Bu gelişmiş özellik geçersiz kılarsanız, temel sınıf sürümü, framework'ün korumak için çağrılacak emin olun. işlem bağlama.

##  <a name="processshellcommand"></a>  CWinApp::ProcessShellCommand

Bu üye işlevi çağıran [InitInstance](#initinstance) gelen geçirilen parametreler kabul etmek için `CCommandLineInfo` tarafından tanımlanan nesne *rCmdInfo*ve belirtilen eylemi gerçekleştirir.

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Parametreler

*rCmdInfo*<br/>
Bir başvuru bir [Ccommandlineınfo](../../mfc/reference/ccommandlineinfo-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Kabuk komutu başarıyla işlenen olursa sıfır dışı. 0, FALSE döndürürse [InitInstance](#initinstance).

### <a name="remarks"></a>Açıklamalar

Uygulama Sihirbazı'nı kullanarak yeni bir MFC projesi başlattığınızda, Uygulama Sihirbazı'nı yerel bir örneğini oluşturur `CCommandLineInfo`ve sonra çağrı `ProcessShellCommand` ve [ParseCommandLine](#parsecommandline) içinde `InitInstance` üye işlevi. Bir komut satırı aşağıda açıklanan yol aşağıdaki gibidir:

1. Oluşturulmakta sonra `InitInstance`, `CCommandLineInfo` nesnesi `ParseCommandLine`.

2. `ParseCommandLine` Daha sonra çağırır [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) art arda, her parametre için bir kez.

3. `ParseParam` doldurur `CCommandLineInfo` ardından geçirilen nesne `ProcessShellCommand`.

4. `ProcessShellCommand` komut satırı bağımsız değişkenleri ve bayrakları işler.

Veri üyeleri `CCommandLineInfo` tarafından tanımlanan nesnesi [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), içinde tanımlanan aşağıdaki listeden seçimli türü olan `CCommandLineInfo` sınıfı.

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

##  <a name="processwndprocexception"></a>  CWinApp::ProcessWndProcException

Her birinde, uygulamanızın ileti veya komut işleyicisi bir özel durum işleyici yakalamaz framework bu üye işlevini çağırır.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*e*<br/>
Yakalanmayan bir özel durum işaretçisi.

*pMsg*<br/>
A [MSG](../../mfc/reference/msg-structure1.md) bir özel durum için framework neden windows iletisi hakkında bilgi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Windows için döndürülen değer. Normalde 0 L windows iletilerini 1 L (TRUE) için komut iletilerini budur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini doğrudan çağırmanız gerekmez.

Bu üye işlevini varsayılan uygulaması bir ileti kutusu oluşturur. Yakalanmayan Özel durum menü, araç veya Hızlandırıcı komut hatası kaynaklanıyorsa, bir "Komutu başarısız oldu" iletisi ileti kutusunu görüntüler; Aksi takdirde, bir "İç uygulama hatası" iletisi görüntüler.

Bu üye işlevi, özel durumlar genel işlenmesini sağlamak için geçersiz kılın. Görüntülenecek ileti kutusu isterseniz, yalnızca temel işlevlerini çağırın.

##  <a name="register"></a>  CWinApp::Register

Tarafından işlenmemiş herhangi bir kayıt görevi gerçekleştiren `RegisterShellFileTypes`.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama yalnızca, TRUE döndürür. Tüm özelleştirilmiş kayıt adımları sağlamak için bu işlevi geçersiz kılar.

##  <a name="registershellfiletypes"></a>  Otomatik olarak InitInstance

Uygulamanızın belge türlerinin tümü Windows Dosya Yöneticisi ile kaydetmek için bu üye işlevini çağırın.

```
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>Parametreler

*bCompat*<br/>
[in] TRUE, yazdırma ve yazdırma dosyaları doğrudan kabuğundan veya dosya için bir yazıcı nesnesi sürükleyerek yazdırmak bir kullanıcı izin vermek için Kabuk komutları için kayıt defteri girdileri ekler. Ayrıca, bir defaultIcon anahtar ekler. Varsayılan olarak, bu parametre FALSE olduğunda geriye dönük uyumluluk için.

### <a name="remarks"></a>Açıklamalar

Bu dosya Yöneticisi içinde çift tıklayarak buradan, uygulamanız tarafından oluşturulan bir veri dosyasını açmak kullanıcının sağlar. Çağrı `RegisterShellFileTypes` çağırdıktan sonra [AddDocTemplate](#adddoctemplate) uygulamanızdaki belge şablonlarının her biri için. Ayrıca [EnableShellOpen](#enableshellopen) üye işlevini çağırdığınızda `RegisterShellFileTypes`.

`RegisterShellFileTypes` listesi üzerinden yinelenir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) uygulama tutar ve her bir belge şablonu için girişler için dosya ilişkilendirmeleri Windows tutan kayıt veritabanına ekler, nesneleri. Dosya Yöneticisi bu girişleri kullanıcı tıkladığında bir veri dosyasını açmak için kullanır. Bu göndermeye ihtiyacını ortadan kaldıran bir. Uygulamanızla REG dosyası.

> [!NOTE]
> `RegisterShellFileTypes` kullanıcının yönetici haklarıyla program çalışıyorsa yalnızca çalışır. Program yönetici haklarına sahip değilse, kayıt defteri anahtarlarını değiştirilemiyor.

Kayıt defteri veritabanında, belirtilen dosya adı uzantısı zaten başka bir dosya türü ile ilişkilendirir. yeni bir ilişki oluşturulur. Bkz: `CDocTemplate` bu bilgileri kaydetmek gerekli olan dize biçimi için sınıf.

##  <a name="registerwithrestartmanager"></a>  CWinApp::RegisterWithRestartManager

Uygulama yeniden başlatma Yöneticisi ile kaydeder.

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
|*bRegisterRecoveryCallback*|[in] TRUE, uygulamanın bu örneği bir kurtarma geri çağırma işlevini kullandığını gösterir; FALSE, mevcut olduğunu gösterir. Uygulama beklenmedik bir şekilde çıktığında framework Kurtarma geri çağırma işlevini çağırır. Daha fazla bilgi için [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*strRestartIdentifier*|[in] Bu örneği yeniden başlatma Yöneticisi'ni tanımlayan benzersiz dize. Yeniden başlatma Yöneticisi uygulamanın her örneği için benzersiz tanımlayıcısıdır.|
|*pwzCommandLineArgs*|[in] Komut satırından herhangi bir ek bağımsız değişken içeren bir dize.|
|*dwRestartFlags*|[in] Yeniden başlatma Yöneticisi için isteğe bağlı bayraklar. Daha fazla bilgi için Açıklamalar bölümüne bakın.|
|*pRecoveryCallback*|[in] Kurtarma geri çağırma işlevi. Bu işlev, giriş olarak LPVOID parametre almaz ve bir DWORD döndürür. Varsayılan kurtarma geri çağırma işlevidir `CWinApp::ApplicationRecoveryCallback`.|
|*lpvParam*|[in] Kurtarma geri çağırma işlevi için giriş parametresi. Daha fazla bilgi için [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*dwPingInterval*|[in] Kurtarma için geri dönmek geri çağırma işlevi yeniden başlatma Yöneticisi bekleyeceği sürenin uzunluğunu. Bu parametre, milisaniye cinsindendir.|
|*dwCallbackFlags*|[in] Bayrakları Kurtarma geri çağırma işlevine geçirilen. Daha sonraki kullanımlar için ayrılmıştır.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK; Aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

Uygulamanızı otomatik kaydetmeyi dosyaları için varsayılan MFC uygulaması kullanıyorsa, basit bir sürümü kullanmalısınız `RegisterWithRestartManager`. Karmaşık kullanmanız `RegisterWithRestartManager` uygulamanız otomatik kaydetme davranışını özelleştirmek istiyorsanız.

Bu yöntem boş bir dize ile çağrı ise *strRestartIdentifier*, `RegisterWithRestartManager` Yöneticisi bu örneğini yeniden başlatmak için bir benzersiz tanımlayıcı dizesi oluşturur.

Bir uygulama beklenmedik bir şekilde çıktığında, yeniden başlatma Yöneticisi'ni komut satırından uygulamayı yeniden başlatır ve benzersiz tanımlayıcı isteğe bağlı bağımsız değişken olarak yeniden sağlar. Bu senaryoda, framework çağırır `RegisterWithRestartManager` iki kez. İlk çağrı geldiği [CWinApp::InitInstance](#initinstance) ile dize tanımlayıcısı için boş bir dize. Ardından, yöntem [CWinApp::ProcessShellCommand](#processshellcommand) çağrıları `RegisterWithRestartManager` yeniden benzersiz tanımlayıcısına sahip.

Yeniden başlatma Yöneticisi ile bir uygulamayı kaydettikten sonra uygulama yeniden başlatma Yöneticisi izler. Beklenmedik şekilde uygulamadan çıkar, yeniden başlatma Yöneticisi kapatma işlemi sırasında kurtarma geri çağırma işlevini çağırır. Yeniden başlatma Yöneticisi bekler *dwPingInterval* yanıt Kurtarma geri çağırma işlevi. Kurtarma geri çağırma işlevine bu süre içinde yanıt vermezse, Kurtarma geri çağırma işlevi çalıştırmadan uygulama kapanır.

Varsayılan olarak, dwRestartFlags desteklenmez ancak gelecekte kullanılmak üzere sağlanır. Olası değerler için *dwRestartFlags* aşağıdaki gibidir:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="reopenpreviousfilesatrestart"></a>  CWinApp::ReopenPreviousFilesAtRestart

Yeniden başlatma Yöneticisi uygulama beklenmedik bir şekilde çıkıldı açık dosyalar açana olup olmadığını belirler.

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma Yöneticisi'ni daha önce açık olan dosyaları açana gösterir; FALSE, yeniden başlatma Yöneticisi yok gösterir.

##  <a name="restartinstance"></a>  CWinApp::RestartInstance

Bir uygulama yeniden başlatma yeniden başlatma Yöneticisi tarafından başlatılan işler.

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Veri kurtarma işleyicisi daha önce açık belgeler açarsa TRUE; Veri kurtarma işleyicisi bir hata varsa veya daha önce açık belge yoksa FALSE.

### <a name="remarks"></a>Açıklamalar

Bir uygulama yeniden başlatma Yöneticisi yeniden başlatıldığında framework bu yöntemi çağırır. Bu yöntem, veri kurtarma işleyiciyi alır ve otomatik kaydedilmiş dosyaları geri yükler. Bu yöntemin çağırdığı [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) kullanıcı otomatik kaydedilmiş dosyaları geri yüklemek isteyip istemediğini belirlemek için.

Bu yöntem FALSE döndürür [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) hiçbir açık belgeler olduğunu belirler. Hiçbir açık belgeleri varsa, uygulama normal şekilde başlar.

##  <a name="restoreautosavedfilesatrestart"></a>  CWinApp::RestoreAutosavedFilesAtRestart

Uygulama yeniden başlatıldığında yeniden başlatma Yöneticisi'ni otomatik olarak kaydedilmiş dosyaları geri yükler olup olmadığını belirler.

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma Yöneticisi'ni otomatik olarak kaydedilmiş dosyaları geri yükler gösterir; FALSE, yeniden başlatma Yöneticisi yok gösterir.

##  <a name="run"></a>  CWinApp::Run

Bir varsayılan mesaj döngüsünü sağlar.

```
virtual int Run();
```

### <a name="return-value"></a>Dönüş Değeri

Bir **int** tarafından döndürülen değer `WinMain`.

### <a name="remarks"></a>Açıklamalar

`Run` edinme ve uygulama WM_QUIT ileti alıncaya kadar Windows iletileri gönderir. Uygulamanın ileti kuyruğu şu anda hiçbir ileti içeriyorsa `Run` çağrıları [ONIDLE](#onidle) boşta kalma süresi işlemini gerçekleştirmek için. Gelen iletiler Git [PreTranslateMessage](#pretranslatemessage) üye işlevi özel işleme ve ardından Windows işleve `TranslateMessage` standart klavye çevirisi; son olarak, `DispatchMessage` Windows işlevi çağrılır.

`Run` nadiren geçersiz kılınır, ancak özel davranış sağlamak üzere geçersiz kılabilirsiniz.

##  <a name="runautomated"></a>  CWinApp::RunAutomated

Belirlemek için bu işlevi çağırın olup olmadığını " **/Automation**"veya" **-Otomasyon**" seçeneği varsa, sunucu uygulaması istemci uygulama tarafından başlatılan olup olmadığını gösterir.

```
BOOL RunAutomated();
```

### <a name="return-value"></a>Dönüş Değeri

Seçenek bulunamadı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa, seçeneğin komut satırından kaldırıldı. OLE Otomasyonu hakkında daha fazla bilgi için bkz [otomasyon sunucuları](../../mfc/automation-servers.md).

##  <a name="runembedded"></a>  CWinApp::RunEmbedded

Belirlemek için bu işlevi çağırın olup olmadığını " **/Embedding**"veya" **-katıştırma**" seçeneği varsa, sunucu uygulaması istemci uygulama tarafından başlatılan olup olmadığını gösterir.

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>Dönüş Değeri

Seçenek bulunamadı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa, seçeneğin komut satırından kaldırıldı. Ekleme ile ilgili daha fazla bilgi için bkz [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md).

##  <a name="saveallmodified"></a>  CWinApp::SaveAllModified

WM_QUERYENDSESSION ileti veya uygulamanın ana çerçeve penceresinin kapatılması olduğunda tüm belgeleri kaydetmek için framework tarafından çağırılır.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamayı sonlandırmak güvenli olursa sıfır dışı; Uygulamayı sonlandırmak güvenli değilse 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini varsayılan uygulamasını çağırır [CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified) sırayla uygulamadaki tüm değiştirilen belgeler için üye işlevi.

##  <a name="selectprinter"></a>  CWinApp::SelectPrinter

Belirli bir yazıcı seçmek için bu üye işlevini çağırın ve yazdırma iletişim kutusundaki önceden seçilmiş olan yazıcı bırakın.

```
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>Parametreler

*hDevNames*<br/>
İçin bir tanıtıcı bir [DEVNAMES](../../mfc/reference/devnames-structure.md) sürücü, cihaz ve çıkış bağlantı noktası adları belirli bir yazıcı tanımlayan yapısı.

*hDevMode*<br/>
İçin bir tanıtıcı bir [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) cihaz başlatma ve yazıcı ortamı hakkında bilgi belirten yapısı.

*bFreeOld*<br/>
Önceden seçilen yazıcı serbest bırakır.

### <a name="remarks"></a>Açıklamalar

Her iki *hDevMode* ve *hDevNames* NULL olan `SelectPrinter` geçerli varsayılan yazıcıyı kullanır.

##  <a name="sethelpmode"></a>  CWinApp::SetHelpMode

Uygulamanın Yardım türünü ayarlar.

```
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>Parametreler

*eHelpType*<br/>
Kullanılacak Yardım türünü belirtir. Bkz: [CWinApp::m_eHelpType](#m_ehelptype) daha fazla bilgi için.

### <a name="remarks"></a>Açıklamalar

Uygulamanın Yardım türünü ayarlar.

Uygulamanızın Yardım türü HTMLHelp için ayarlanacak çağırabilirsiniz [EnableHTMLHelp](#enablehtmlhelp). Bir kez çağırmanız `EnableHTMLHelp`, uygulamanızı kendi Yardım uygulaması HTMLHelp kullanmanız gerekir. WinHelp kullanmak için değiştirmek istiyorsanız, çağırabilirsiniz `SetHelpMode` ayarlayıp *eHelpType* için `afxWinHelp`.

##  <a name="setregistrykey"></a>  CWinApp::SetRegistryKey

INİ dosyaları yerine kayıt defterinde saklanan uygulama ayarları neden olur.

```
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>Parametreler

*lpszRegistryKey*<br/>
Anahtar adını içeren bir dize işaretçisi.

*nIDRegistryKey*<br/>
Kayıt defteri anahtarı adını içeren dize kaynağının kimliği.

### <a name="remarks"></a>Açıklamalar

Bu işlev ayarlar *m_pszRegistryKey*, ardından kullanılan tarafından `GetProfileInt`, `GetProfileString`, `WriteProfileInt`, ve `WriteProfileString` üye işlevlerinin `CWinApp`. Bu işlev çağrılırsa, en son kullanılan (MRU) dosya listesi de kayıt defterinde depolanır. Kayıt defteri anahtarı genellikle bir şirketin adıdır. Aşağıdaki biçimde bir anahtarında depolanır: HKEY_CURRENT_USER\Software\\< şirket adı\>\\< Uygulama adı\>\\< bölüm adı\>\\< değer ad\>.

##  <a name="supportsapplicationrecovery"></a>  CWinApp::SupportsApplicationRecovery

Yeniden başlatma Yöneticisi beklenmedik şekilde çıkıldı uygulamanın kurtarır olup olmadığını belirler.

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, uygulama yeniden başlatma Yöneticisi kurtarır gösterir; FALSE, yeniden başlatma Yöneticisi yok gösterir.

##  <a name="supportsautosaveatinterval"></a>  CWinApp::SupportsAutosaveAtInterval

Yeniden başlatma Yöneticisi kapanıyorsa düzenli aralıklarla belgeler açık olup olmadığını belirler.

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma Yöneticisi kapanıyorsa açık belgeleri gösterir; FALSE, yeniden başlatma Yöneticisi yok gösterir.

##  <a name="supportsautosaveatrestart"></a>  CWinApp::SupportsAutosaveAtRestart

Belirler olmadığını yeniden başlatma Yöneticisi kapanıyorsa tüm açık belgeleri uygulama yeniden başlatıldığında.

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, uygulama yeniden başlatıldığında, yeniden başlatma Yöneticisi kapanıyorsa belgeleri Aç gösterir; FALSE, yeniden başlatma Yöneticisi yok gösterir.

##  <a name="supportsrestartmanager"></a>  CWinApp::SupportsRestartManager

Uygulama yeniden başlatma Yöneticisi destekleyip desteklemediğini belirler.

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma Yöneticisi uygulamanın desteklediği gösterir; FALSE, uygulama daha önceden gösterir.

##  <a name="unregister"></a>  CWinApp::Unregister

Uygulama nesnesi tarafından kayıtlı tüm dosyaları kaydını siler.

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`Unregister` İşlevi uygulama nesnesi tarafından gerçekleştirilen kaydı alır ve [kaydetme](#register) işlevi. Normalde, her iki işlev MFC tarafından örtük olarak çağırılamaz ve bu nedenle kodunuzda görünmez.

Özel kayıt silme adımları için bu işlevi geçersiz kılar.

##  <a name="unregistershellfiletypes"></a>  CWinApp::UnregisterShellFileTypes

Tüm Windows Dosya Yöneticisi ile uygulamanızın belge türlerinin kaydını kaldırmak için bu üye işlevini çağırın.

```
void UnregisterShellFileTypes();
```

##  <a name="winhelp"></a>  CWinApp::WinHelp

WinHelp uygulamasını çağırmak için bu üye işlevini çağırın.

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>Parametreler

*dwData*<br/>
Ek veri belirtir. Kullanılan değer değerine bağlıdır *nCmd* parametresi.

*nCmd*<br/>
Yardım talep türünü belirtir. Olası değerler ve bunların nasıl etkileyeceğini listesini *dwData* parametresi bkz [WinHelp](/windows/desktop/api/winuser/nf-winuser-winhelpa) Windows işlevi.

### <a name="remarks"></a>Açıklamalar

Framework de WinHelp uygulamasını çağırmak için bu işlevi çağırır.

Uygulamanızı sonlandırıldığında framework otomatik olarak WinHelp uygulamasını kapatın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

##  <a name="writeprofilebinary"></a>  CWinApp::WriteProfileBinary

Uygulamanın kayıt defteri belirtilen bölüme ikili veri yazmak için bu üye işlevini çağırın veya. INI dosyası.

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Giriş içeren bölümü belirten bir boş sonlandırılmış dizeye işaret eder. Bölüm yoksa, oluşturulur. Bölüm çalışması bağımsız adıdır; dize, herhangi bir bileşimini büyük ve küçük harf olabilir.

*lpszEntry*<br/>
Değeri yazılacak giriş içeren null ile sonlandırılmış bir dize işaret eder. Giriş belirtilen bölümde yoksa, oluşturulur.

*pData*<br/>
Yazılacak veri işaret eder.

*nBytes*<br/>
Yazılacak bayt sayısını içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

Bu örnekte `CWinApp* pApp = AfxGetApp();` CWinApp sınıfı bir yol gösteren almak için `WriteProfileBinary` ve `GetProfileBinary` MFC uygulamasında herhangi bir işlevden kullanılabilir.

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

Başka bir örnek için örneğin bakın [CWinApp::GetProfileBinary](#getprofilebinary).

##  <a name="writeprofileint"></a>  CWinApp::WriteProfileInt

Uygulamanın kayıt defteri belirtilen bölüme belirtilen değeri yazmak için bu üye işlevini çağırın veya. INI dosyası.

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Giriş içeren bölümü belirten bir boş sonlandırılmış dizeye işaret eder. Bölüm yoksa, oluşturulur. Bölüm çalışması bağımsız adıdır; dize, herhangi bir bileşimini büyük ve küçük harf olabilir.

*lpszEntry*<br/>
Değeri yazılacak giriş içeren null ile sonlandırılmış bir dize işaret eder. Giriş belirtilen bölümde yoksa, oluşturulur.

*nDeğer*<br/>
Yazılacak değer içeriyor.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

Bu örnekte `CWinApp* pApp = AfxGetApp();` CWinApp sınıfı bir yol gösteren almak için `WriteProfileString`, `WriteProfileInt`, `GetProfileString`, ve `GetProfileInt` MFC uygulamasında herhangi bir işlevden kullanılabilir.

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Başka bir örnek için örneğin bakın [CWinApp::GetProfileInt](#getprofileint).

##  <a name="writeprofilestring"></a>  CWinApp::WriteProfileString

Uygulamanın kayıt defteri belirtilen bölüm içinde belirtilen dize yazmak için bu üye işlevini çağırın veya. INI dosyası.

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>Parametreler

*lpszSection*<br/>
Giriş içeren bölümü belirten bir boş sonlandırılmış dizeye işaret eder. Bölüm yoksa, oluşturulur. Bölüm çalışması bağımsız adıdır; dize, herhangi bir bileşimini büyük ve küçük harf olabilir.

*lpszEntry*<br/>
Değeri yazılacak giriş içeren null ile sonlandırılmış bir dize işaret eder. Giriş belirtilen bölümde yoksa, oluşturulur. Bu parametre NULL ise, bölümü tarafından belirtilen *lpszSection* silinir.

*lpszValue*<br/>
Yazılacak dize işaret eder. Bu parametre NULL ise, giriş tarafından belirtilen *lpszEntry* parametresi silinir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Başka bir örnek için örneğin bakın [CWinApp::GetProfileInt](#getprofileint).

##  <a name="setappid"></a>  CWinApp::SetAppID

Açıkça uygulama kullanıcı modeli kimliği, uygulama için ayarlar. Herhangi bir kullanıcı arabirimi (en iyi uygulama Oluşturucu yerdir) kullanıcıya görüntülenmeden önce bu yöntem çağrılmalıdır.

```
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>Parametreler

*lpcszAppID*<br/>
Uygulama kullanıcı Model kimliğini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[CWinThread Sınıfı](../../mfc/reference/cwinthread-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme](../../mfc/how-to-add-restart-manager-support.md)
