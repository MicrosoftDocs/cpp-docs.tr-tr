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
ms.openlocfilehash: 105e8860746c4de4086e9481b06417b186ddc9ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cwinapp-class"></a>CWinApp sınıfı
Bir Windows uygulama nesnesi türetilen temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CWinApp : public CWinThread  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinApp::CWinApp](#cwinapp)|Oluşturan bir `CWinApp` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinApp::AddDocTemplate](#adddoctemplate)|Belge şablonu uygulamanın kullanılabilir şablonların listesine ekler.|  
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|Bir dosya adı en son kullanılan (MRU) dosya listesine ekler.|  
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|Uygulama beklenmedik şekilde çıktığında çerçevesi tarafından çağrılır.|  
|[CWinApp::CloseAllDocuments](#closealldocuments)|Tüm açık belgeleri kapatır.|  
|[CWinApp::CreatePrinterDC](#createprinterdc)|Bir yazıcı cihaz bağlamı oluşturur.|  
|[CWinApp::DelRegTree](#delregtree)|Belirtilen anahtar ve tüm alt anahtarlarını siler.|  
|[CWinApp::DoMessageBox](#domessagebox)|Implements [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) uygulama için.|  
|[CWinApp::DoWaitCursor](#dowaitcursor)|Bekleme imleci açar ve kapatır.|  
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|Uygulamayı etkinleştirir `D2D` destekler. Ana pencerede başlatılmadan önce bu yöntemi çağırın.|  
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|WinHelp yerine uygulama için HTMLHelp uygular.|  
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|Görev etkileşim sağlar.|  
|[CWinApp::ExitInstance](#exitinstance)|Uygulamanızı sonlandırıldığında temizlemek için geçersiz kılın.|  
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|Uygulama kurtarma yöntemi için giriş parametresi alır.|  
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Kurtarma için dönmek geri çağırma işlevi yeniden başlatma Yöneticisi bekleyeceği süreyi döndürür.|  
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|Bayrakları için yeniden başlatma Yöneticisi döndürür.|  
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|HKEY_CURRENT_USER döndürür anahtar\\"Yazılım" \RegistryKey\ProfileName.|  
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|Veri kurtarma işleyicisi uygulamanın bu örneğini alır.|  
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|İlk belge şablonu konumunu alır.|  
|[CWinApp::GetHelpMode](#gethelpmode)|Uygulama tarafından kullanılan Yardım türünü alır.|  
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|Belge şablonu konumunu alır. Kullanılan yinelemeli olabilir.|  
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|Yazıcı aygıt varsayılanlarını alır.|  
|[CWinApp::GetProfileBinary](#getprofilebinary)|İkili veriler uygulamanın bir girdi alır. INI dosyası.|  
|[CWinApp::GetProfileInt](#getprofileint)|Tamsayı uygulamanın bir girdi alır. INI dosyası.|  
|[CWinApp::GetProfileString](#getprofilestring)|Uygulamanın bir girişe bir dize alır. INI dosyası.|  
|[CWinApp::GetSectionKey](#getsectionkey)|HKEY_CURRENT_USER döndürür anahtar\\"Yazılım" \RegistryKey\AppName\lpszSection.|  
|[CWinApp::HideApplication](#hideapplication)|Tüm belgeler kapatmadan önce uygulamayı gizler.|  
|[CWinApp::HtmlHelp](#htmlhelp)|Çağrıları `HTMLHelp` Windows işlevi.|  
|[CWinApp::InitInstance](#initinstance)|Pencere nesneleri oluşturma gibi Windows örneği başlatma gerçekleştirmek için geçersiz kılın.|  
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Windows 7 görev etkileşim etkin olup olmadığını bildirir.|  
|[CWinApp::LoadCursor](#loadcursor)|İmleç kaynak yükler.|  
|[CWinApp::LoadIcon](#loadicon)|Bir simge kaynak yükler.|  
|[CWinApp::LoadOEMCursor](#loadoemcursor)|Yükleri Windows OEM imleç önceden tanımlanmış, **OCR_** sabitleri WINDOWS belirtin. H.|  
|[CWinApp::LoadOEMIcon](#loadoemicon)|Windows OEM önceden tanımlanmış simge yükler, **OIC_** sabitleri WINDOWS belirtin. H.|  
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|Yükleri Windows imleç önceden tanımlanmış, **IDC_** sabitleri WINDOWS belirtin. H.|  
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Windows önceden tanımlanmış simge yükler, **IDI_** sabitleri WINDOWS belirtin. H.|  
|[CWinApp::OnDDECommand](#onddecommand)|Adlı Değişimi (DDE) yanıt olarak dinamik bir veri framework tarafından komutu yürütün.|  
|[CWinApp::OnIdle](#onidle)|Uygulamaya özgü boşta kalma süresi işlemini gerçekleştirmek için geçersiz kılın.|  
|[CWinApp::OpenDocumentFile](#opendocumentfile)|Bir dosyadan bir belgeyi açmaya çerçevesi tarafından çağrılır.|  
|[CWinApp::ParseCommandLine](#parsecommandline)|Tek tek parametreleri ve komut satırı bayrakları ayrıştırır.|  
|[CWinApp::PreTranslateMessage](#pretranslatemessage)|Windows işlevleri gönderilir önce iletileri filtreler [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|Uygulama düşmeden önce belirli iletileri kesintiye uğratır.|  
|[CWinApp::ProcessShellCommand](#processshellcommand)|Komut satırı bağımsız değişkenleri ve bayrakları işler.|  
|[CWinApp::ProcessWndProcException](#processwndprocexception)|Uygulamanın iletiyi ve komut işleyicileri tarafından oluşturulan tüm işlenmeyen özel durumları yakalar.|  
|[CWinApp::Register](#register)|Özelleştirilmiş kayıt gerçekleştirir.|  
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|Uygulama yeniden başlatma Yöneticisi ile kaydeder.|  
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|Yeniden başlatma Yöneticisi uygulama beklenmedik biçimde çıktı zaman açık olan dosyaları açana olup olmadığını belirler.|  
|[CWinApp::RestartInstance](#restartinstance)|Yeniden başlatma Yöneticisi tarafından başlatılan bir uygulama yeniden başlatma işler.|  
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|Uygulama yeniden başlatıldığında yeniden başlatma Yöneticisi'ni otomatik olarak kaydedilmiş dosyaları geri yükler olup olmadığını belirler.|  
|[CWinApp::Run](#run)|Varsayılan ileti döngüsü çalışır. İleti döngüsü özelleştirmek için geçersiz kılın.|  
|[CWinApp::RunAutomated](#runautomated)|Uygulamanın komut satırı testleri **/Automation** seçeneği. Kullanımdan kalktı. Bunun yerine, değeri kullanın [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) çağırdıktan sonra [ParseCommandLine](#parsecommandline).|  
|[CWinApp::RunEmbedded](#runembedded)|Uygulamanın komut satırı testleri **/katıştırma** seçeneği. Kullanımdan kalktı. Bunun yerine, değeri kullanın [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) çağırdıktan sonra [ParseCommandLine](#parsecommandline).|  
|[CWinApp::SaveAllModified](#saveallmodified)|Değiştirilen tüm belgeleri kaydetmek için kullanıcıya sorar.|  
|[CWinApp::SelectPrinter](#selectprinter)|Yazdır iletişim kutusu üzerinden bir kullanıcı tarafından daha önce belirtilen yazıcı seçer.|  
|[CWinApp::SetHelpMode](#sethelpmode)|Ayarlar ve uygulama tarafından kullanılan Yardım türü başlatır.|  
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|Yeniden başlatma Yöneticisi beklenmedik biçimde çıktı uygulamanın kurtarır olup olmadığını belirler.|  
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|Yeniden başlatma Yöneticisi autosaves düzenli aralıklarla belgeleri Aç olup olmadığını belirler.|  
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|Belirler olup olmadığını yeniden başlatma Yöneticisi autosaves tüm açık belgeleri uygulama yeniden başlatıldığında.|  
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|Uygulama yeniden başlatma Yöneticisi'ni destekleyip desteklemediğini belirler.|  
|[CWinApp::Unregister](#unregister)|Her şeyi tarafından kayıtlı olduğu bilinen kaydını siler `CWinApp` nesnesi.|  
|[CWinApp::WinHelp](#winhelp)|Çağrıları `WinHelp` Windows işlevi.|  
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|Uygulamanın içindeki bir girdiye ikili verileri yazar. INI dosyası.|  
|[CWinApp::WriteProfileInt](#writeprofileint)|Uygulamanın içindeki bir girdiye tamsayı yazar. INI dosyası.|  
|[CWinApp::WriteProfileString](#writeprofilestring)|Uygulamanın içindeki bir girdiye bir dize yazar. INI dosyası.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinApp::EnableShellOpen](#enableshellopen)|Windows Dosya Yöneticisi'nden veri dosyalarını açmasına olanak tanır.|  
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|Yükleri standart. Liste özelliğini dosya INİ dosyası ayarları ve MRU etkinleştirir.|  
|[CWinApp::OnContextHelp](#oncontexthelp)|SHIFT + F1 Yardımı uygulama içinde işler.|  
|[CWinApp::OnFileNew](#onfilenew)|Implements `ID_FILE_NEW` komutu.|  
|[CWinApp::OnFileOpen](#onfileopen)|Implements `ID_FILE_OPEN` komutu.|  
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|Implements `ID_FILE_PRINT_SETUP` komutu.|  
|[CWinApp::OnHelp](#onhelp)|F1 Yardımı (geçerli bağlamı kullanarak) uygulama içinde işler.|  
|[CWinApp::OnHelpFinder](#onhelpfinder)|İşleme `ID_HELP_FINDER` ve `ID_DEFAULT_HELP` komutları.|  
|[CWinApp::OnHelpIndex](#onhelpindex)|İşleme `ID_HELP_INDEX` komut ve varsayılan Yardım konusunun sağlar.|  
|[CWinApp::OnHelpUsing](#onhelpusing)|İşleme `ID_HELP_USING` komutu.|  
|[CWinApp::RegisterShellFileTypes](#registershellfiletypes)|Uygulamanın tüm belge türü Windows Dosya Yöneticisi ile kaydeder.|  
|[CWinApp::SetAppID](#setappid)|Açıkça uygulama kullanıcısı Model kimliği için uygulama ayarlar. Bu yöntem, herhangi bir kullanıcı arabirimi (en iyi uygulama Oluşturucusu yerdir) kullanıcıya görüntülenmeden önce çağrılmalıdır.|  
|[CWinApp::SetRegistryKey](#setregistrykey)|Uygulama ayarları yerine kayıt defterinde depolanan neden olur. INİ dosyaları.|  
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|Uygulamanın tüm belge türü ile Windows Dosya Yöneticisi kaydını siler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinApp::m_bHelpMode](#m_bhelpmode)|Kullanıcı (genellikle SHIFT + F1'e çağrılan) Yardım bağlamı modunda olup olmadığını gösterir.|  
|[CWinApp::m_eHelpType](#m_ehelptype)|Uygulama tarafından kullanılan Yardım türünü belirtir.|  
|[CWinApp::m_hInstance](#m_hinstance)|Uygulamanın geçerli örneğini tanımlar.|  
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|Noktaları null ile sonlandırılmış dizeye uygulama için komut satırını belirtir.|  
|[CWinApp::m_nCmdShow](#m_ncmdshow)|Nasıl penceresi başlangıçta gösterilecek belirtir.|  
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|OLE sunucu yerinde etkin olduğunda kapsayıcı uygulamanın ana penceresi işaretçi.|  
|[CWinApp::m_pszAppID](#m_pszappid)|Uygulama kullanıcı modeli kimliği|  
|[CWinApp::m_pszAppName](#m_pszappname)|Uygulamanın adını belirtir.|  
|[CWinApp::m_pszExeName](#m_pszexename)|Uygulama modülü adı.|  
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|Uygulamanın Yardım dosyasının yolu.|  
|[CWinApp::m_pszProfileName](#m_pszprofilename)|Uygulamanın. INI dosyası adı.|  
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|Uygulama profili ayarlarını depolamak için tam kayıt defteri anahtarı belirlemek için kullanılır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Yeniden başlatma Yöneticisi'ni nasıl davranacağını belirleyen bayrak.|  
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|Autosaves arasındaki milisaniye cinsinden süre uzunluğu.|  
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Uygulama için veri kurtarma işleyicisi işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulama nesnesi, uygulamanız (ve her örneği) başlatma ve uygulamayı çalıştırmak için üye işlevleri sağlar.  
  
 Microsoft Foundation sınıfları kullanan her bir uygulama yalnızca türetilmiş bir nesne içerebilir `CWinApp`. Bu nesne diğer C++ genel nesneler oluşturulan zaman oluşturulur ve Windows çağırdığında zaten kullanılabilir `WinMain` Microsoft Foundation Class Kitaplığı tarafından sağlanan işlev. Türetilmiş bildirme `CWinApp` genel düzeyde nesne.  
  
 Bir uygulama sınıfından türetilen zaman `CWinApp`, geçersiz kılma [InitInstance](#initinstance) uygulamanızın ana pencere nesnesi oluşturmak için üye işlevi.  
  
 Ek olarak `CWinApp` üye işlevleri Microsoft Foundation Class Kitaplığı erişmek için aşağıdaki genel işlevler sağlar, `CWinApp` nesne ve diğer genel bilgileri:  
  
- [AfxGetApp](application-information-and-management.md#afxgetapp) gösteren bir işaretçi alır `CWinApp` nesnesi.  
  
- [Afxgetınstancehandle](application-information-and-management.md#afxgetinstancehandle) geçerli uygulama örneği için bir tanıtıcı alır.  
  
- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) uygulamanın kaynakları için bir tanıtıcı alır.  
  
- [AfxGetAppName](application-information-and-management.md#afxgetappname) uygulamanın adını içeren bir dize için bir işaretçi alır. Alternatif olarak, bir işaretçi varsa `CWinApp` nesne, kullanın `m_pszExeName` uygulamanın adını almak için.  
  
 Bkz: [CWinApp: uygulama sınıfı](../../mfc/cwinapp-the-application-class.md) hakkında daha fazla bilgi için `CWinApp` sınıfı, aşağıdaki genel bir bakış da dahil olmak üzere:  
  
- `CWinApp`-Uygulama Sihirbazı tarafından yazılan kodu türetilmiş.  
  
- `CWinApp`Kullanıcının, uygulamanızın yürütme sırası rolünde.  
  
- `CWinApp`varsayılan üye fonksiyonu uygulamaları kullanıcının.  
  
- `CWinApp`ın anahtar geçersiz kılınabilir.  
  
 **M_hPrevInstance** veri üyesi artık yok. Önceki bir örneği algılama hakkında bilgi için `CWinApp`, Bilgi Bankası makalesi "Nasıl tanımlamak bir önceki örnek, bir uygulamaya" (KB106385) bkz: [ http://support.microsoft.com/default.aspxscid=kb; en-us; 106385](http://support.microsoft.com/default.aspxscid=kb;en-us;106385).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="adddoctemplate"></a>  CWinApp::AddDocTemplate  
 Belge şablonu uygulama tutan kullanılabilir şablonların listesine eklemek için bu üye işlevini çağırın.  
  
```  
void AddDocTemplate(CDocTemplate* pTemplate);
```  
  
### <a name="parameters"></a>Parametreler  
 `pTemplate`  
 Bir işaretçi `CDocTemplate` eklenecek.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm belge şablonları bir uygulamaya çağırmadan önce eklemelisiniz [RegisterShellFileTypes](#registershellfiletypes).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]  
  
##  <a name="addtorecentfilelist"></a>  CWinApp::AddToRecentFileList  
 Bu üye işlevi ekleme çağrısı `lpszPathName` MRU dosya listesi.  
  
```  
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszPathName`  
 Dosya yolu.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız [LoadStdProfileSettings](#loadstdprofilesettings) üye işlevi bu üye işlevi kullanmadan önce geçerli MRU dosya listesi yüklenemedi.  
  
 Bir dosyayı açtığında veya yeni bir adla bir dosya kaydetmek için Kaydet komutunu yürütür framework bu üye işlevi çağırır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]  
  
##  <a name="applicationrecoverycallback"></a>  CWinApp::ApplicationRecoveryCallback  
 Uygulama beklenmedik şekilde çıktığında çerçevesi tarafından çağrılır.  
  
```  
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpvParam`  
 Daha sonraki kullanımlar için ayrılmıştır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa 0; bir hata oluşursa, sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı yeniden başlatma Yöneticisi'ni destekliyorsa, uygulamanızın beklenmedik şekilde çıktığında framework bu işlevi çağırır.  
  
 Varsayılan uygulaması `ApplicationRecoveryCallback` kullanan `CDataRecoveryHandler` geçerli açık belgelerden listesi kayıt defterine kaydetmek için. Bu yöntem herhangi bir dosya değil otomatik kaydetme yapar.  
  
 Davranışını özelleştirmek için bu işleve türetilmiş bir geçersiz kılma [CWinApp sınıfı](../../mfc/reference/cwinapp-class.md) veya kendi uygulama kurtarma yöntemi için parametre olarak geçirmek [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).  
  
##  <a name="closealldocuments"></a>  CWinApp::CloseAllDocuments  
 Çıkmadan önce tüm açık belgeleri kapatmak için bu üye işlevini çağırın.  
  
```  
void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Parametreler  
 `bEndSession`  
 Windows oturumu sona erer olup olmadığını belirtir. Bu **TRUE** oturum varsa sona erdi; Aksi takdirde **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [HideApplication](#hideapplication) çağırmadan önce `CloseAllDocuments`.  
  
##  <a name="createprinterdc"></a>  CWinApp::CreatePrinterDC  
 Seçili yazıcıdan bir yazıcı cihaz bağlamı (DC) oluşturmak için bu üye işlevini çağırın.  
  
```  
BOOL CreatePrinterDC(CDC& dc);
```  
  
### <a name="parameters"></a>Parametreler  
 `dc`  
 Bir yazıcı cihaz bağlamı referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazıcı cihaz bağlamı başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `CreatePrinterDC` yazdırmak için kullanabilirsiniz, böylece, başvuruya göre geçirdiğiniz aygıt bağlamını başlatır.  
  
 Yazdırma tamamlandığında işlevi başarılı olursa, cihaz bağlamı destroy gerekir. Yıkıcısı sağlayabilirsiniz [CDC](../../mfc/reference/cdc-class.md) nesne yapın ya da açıkça çağırarak bunu yapabilirsiniz [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc).  
  
##  <a name="cwinapp"></a>  CWinApp::CWinApp  
 Oluşturan bir `CWinApp` nesne ve geçişleri `lpszAppName` uygulama adı olarak depolanacak.  
  
```  
CWinApp(LPCTSTR lpszAppName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszAppName`  
 Windows kullanan uygulama adı içeren bir null ile sonlandırılmış bir dize. Bu bağımsız değişken sağlanmadığında veya **NULL**, `CWinApp` kaynak dizesi kullanır **AFX_IDS_APP_TITLE** veya yürütülebilir bir dosyanın dosya adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir genel nesnesinin oluşturmalısınız, `CWinApp`-türetilmiş sınıf. Yalnızca bir bulunabilir `CWinApp` uygulamanızda nesnesi. Bir işaretçi Oluşturucusu depolar `CWinApp` nesne böylece `WinMain` nesnenin üye başlatın ve uygulamayı çalıştırmak için işlevleri çağırabilir.  
  
##  <a name="delregtree"></a>  CWinApp::DelRegTree  
 Belirli kayıt defteri anahtarının ve tüm alt anahtarlarını siler.  
  
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
 *hParentKey*  
 Kayıt defteri anahtarına işleyin.  
  
 *strKeyName*  
 Silinecek kayıt defteri anahtarı adı.  
  
 *pTM*  
 CAtlTransactionManager nesnesine işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. İşlev başarısız olursa, dönüş değeri Winerror.h'de içinde tanımlanan bir sıfır olmayan hata kodudur.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen anahtar ve alt anahtarlarından silmek için bu işlevini çağırın.  
  
##  <a name="domessagebox"></a>  CWinApp::DoMessageBox  
 Framework genel işlevi için bir ileti kutusu uygulamak için bu üye işlevini çağırması [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox).  
  
```  
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,  
    UINT nType,  
    UINT nIDPrompt);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszPrompt*  
 İleti kutusu metinde adresidir.  
  
 `nType`  
 İleti kutusu [stili](../../mfc/reference/styles-used-by-mfc.md#message-box-styles).  
  
 `nIDPrompt`  
 Yardım içerik dizesi için bir dizin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aynı değerlere döner `AfxMessageBox`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir ileti kutusu açmak için bu üye işlevini çağırmanız gerekmez; kullanmak `AfxMessageBox` yerine.  
  
 Bu üye işlevi, uygulama genelinde işlenmesini özelleştirmek için geçersiz kılma `AfxMessageBox` çağrıları.  
  
##  <a name="dowaitcursor"></a>  CWinApp::DoWaitCursor  
 Bu üye işlev uygulamak için çerçevesi tarafından çağrılır [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), ve [ CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
```  
virtual void DoWaitCursor(int nCode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nCode`  
 Bu parametre 1 ise, bir bekleme imleç görünür. 0 ise, bekleme imleci başvuru sayısı artırmadan geri yüklendi. -1, bekleme imleci sona erer.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan bir Kum Saati İmleci uygular. `DoWaitCursor` bir başvuru sayımı tutar. Pozitif kum saati imleci görüntülenir.  
  
 Değil normalde çağırırdı sırada `DoWaitCursor` doğrudan bu üye işlevi bekleme imleci değiştirmek için ya da bekleme imleci görüntülenirken ek işlem yapmak için geçersiz.  
  
 Bekleme imleç uygulamak için daha kolay ve daha kolay bir yol için kullanmak `CWaitCursor`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]  
  
##  <a name="enabled2dsupport"></a>  CWinApp::EnableD2DSupport  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 Uygulama D2D desteği sağlar. Ana pencerede başlatılmadan önce bu yöntemi çağırın.  
  
```  
BOOL EnableD2DSupport(
D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>Parametreler  
 `d2dFactoryType`  
 D2D Fabrika ve kaynakları iş parçacığı modeli oluşturur.  
  
 `writeFactoryType`  
 Yazma üretecini paylaşılan veya ayrılmış belirten bir değer  
  
### <a name="return-value"></a>Dönüş Değeri  
 D2D destek aksi etkinleştirilmişse, FALSE - ise TRUE döndürür  
  
##  <a name="enablehtmlhelp"></a>  CWinApp::EnableHtmlHelp  
 Oluşturucusunun içinde bu üye işlevini çağırın, `CWinApp`-türetilmiş sınıf HTMLHelp uygulamanızın yardım almak için kullanın.  
  
```  
void EnableHtmlHelp();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enableshellopen"></a>  CWinApp::EnableShellOpen  
 Çağırmanıza genellikle bu işlev, `InitInstance` dosyaları içinde Windows Dosya Yöneticisi'ni çift tıkladığınızda veri dosyalarını açmak, uygulamanızın kullanıcılarıyla etkinleştirmek için geçersiz kılın.  
  
```  
void EnableShellOpen();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `RegisterShellFileTypes` üyesi bu işleviyle birlikte işlev veya sağlayan bir. Belge türü el ile kayıt için kayıt defteri dosyası uygulamanız ile.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]  
  
##  <a name="enabletaskbarinteraction"></a>  CWinApp::EnableTaskbarInteraction  
 Görev etkileşim sağlar.  
  
```  
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bEnable`  
 Windows 7 görev etkileşim etkin olup olmadığını belirtir ( `TRUE`), ya da devre dışı ( `FALSE`).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` görev etkileşim etkin veya devre dışı.  
  
### <a name="remarks"></a>Açıklamalar  
 Ana penceresi oluşturması işleminden önce bu yöntemin çağrılması gerekir, aksi takdirde onaylar ve döndürür `FALSE`.  
  
##  <a name="exitinstance"></a>  CWinApp::ExitInstance  
 İçinden çerçevesi tarafından çağrılır **çalıştırmak** uygulama'nın bu örneğinin çıkmak için üye işlevi.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulamanın çıkış kodu; 0 hata olmadığını gösterir ve değerler 0'dan büyük bir hata gösterir. Gelen bir dönüş değeri olarak kullanılan bu değer `WinMain`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ancak içinde herhangi bir yerden çağırmayın **çalıştırmak** üye işlevi.  
  
 Bu işlev varsayılan uygulaması framework seçenekleri uygulamanın yazar. INI dosyası. Bu işlev, uygulamanızın sonlandırıldığında temizlemek için geçersiz kılar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]  
  
##  <a name="getapplicationrecoveryparameter"></a>  CWinApp::GetApplicationRecoveryParameter  
 Uygulama kurtarma yöntemi için giriş parametresi alır.  
  
```  
virtual LPVOID GetApplicationRecoveryParameter();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulama kurtarma yöntemi için varsayılan giriş parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan davranışını döndürür `NULL`.  
  
 Daha fazla bilgi için bkz: [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).  
  
##  <a name="getapplicationrecoverypinginterval"></a>  CWinApp::GetApplicationRecoveryPingInterval  
 Kurtarma için dönmek geri çağırma işlevi yeniden başlatma Yöneticisi bekleyeceği süreyi döndürür.  
  
```  
virtual DWORD GetApplicationRecoveryPingInterval();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sürenin milisaniye cinsinden uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma Yöneticisi çıkar ile beklenmedik bir şekilde kayıtlı bir uygulama, uygulama açık belgeleri kaydetmek çalışır ve Kurtarma geri çağırma işlevini çağırır. Varsayılan kurtarma geri çağırma işlevidir [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).  
  
 Kurtarma için dönmek geri çağırma işlevi framework bekleyeceği süreyi ping aralığıdır. Geçersiz kılarak ping aralığını özelleştirebilirsiniz `CWinApp::GetApplicationRecoveryPingInterval` veya özel bir değer sağlayarak `RegisterWithRestartManager`.  
  
##  <a name="getapplicationrestartflags"></a>  CWinApp::GetApplicationRestartFlags  
 Bayrakları için yeniden başlatma Yöneticisi döndürür.  
  
```  
virtual DWORD GetApplicationRestartFlags();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeniden başlatma Yöneticisi işaretler. Varsayılan uygulama 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma Yöneticisi bayrakları varsayılan uygulaması ile herhangi bir etkisi yoktur. Bunlar, gelecekte kullanılmak üzere sağlanır.  
  
 Kullanarak uygulama yeniden başlatma Yöneticisi ile kaydettiğinizde bayraklarını ayarlayın [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).  
  
 Yeniden başlatma Yöneticisi bayrakları için olası değerler şunlardır:  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="getappregistrykey"></a>  CWinApp::GetAppRegistryKey  
 HKEY_CURRENT_USER anahtarını döner\\"Yazılım" \RegistryKey\ProfileName.  
  
```  
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pTM`  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa uygulama anahtarı; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdatarecoveryhandler"></a>  CWinApp::GetDataRecoveryHandler  
 Veri kurtarma işleyicisi uygulamanın bu örneğini alır.  
  
```  
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu örnek uygulama için veri kurtarma işleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma Yöneticisi'ni kullanan her uygulamanın bir örneği olmalıdır [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md). Bu sınıf, açık belgeler veya otomatik kaydetmeyi dosyaları izlemekten sorumludur. Davranışını `CDataRecoveryHandler` yeniden başlatma Yöneticisi yapılandırmasına bağlıdır. Daha fazla bilgi için bkz: [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md).  
  
 Bu yöntem `NULL` Windows Vista'dan önceki işletim sistemlerinde. Yeniden başlatma Yöneticisi Windows Vista'dan önceki işletim sistemlerinde desteklenmiyor.  
  
 Uygulama şu anda bir veri kurtarma işleyicisi yoksa, bu yöntem tane oluşturur ve bir işaretçi döndürür.  
  
##  <a name="getfirstdoctemplateposition"></a>  CWinApp::GetFirstDocTemplatePosition  
 Uygulamayı ilk belge şablonu konumunu alır.  
  
```  
POSITION GetFirstDocTemplatePosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya nesne işaretçi alma; için kullanılan değer **NULL** liste boşsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım **konumu** döndürülen değer çağrıda [GetNextDocTemplate](#getnextdoctemplate) ilk almak için [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesi.  
  
##  <a name="gethelpmode"></a>  CWinApp::GetHelpMode  
 Uygulama tarafından kullanılan Yardım türünü alır.  
  
```  
AFX_HELP_TYPE GetHelpMode();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulama tarafından kullanılan Yardım türü. Bkz: [CWinApp::m_eHelpType](#m_ehelptype) daha fazla bilgi için.  
  
##  <a name="getnextdoctemplate"></a>  CWinApp::GetNextDocTemplate  
 Belge şablonu tarafından tanımlanan alır `pos`, ardından ayarlar `pos` için **konumu** değeri.  
  
```  
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Bir başvuru bir **konumu** önceki bir çağrı tarafından döndürülen değer `GetNextDocTemplate` veya [GetFirstDocTemplatePosition](#getfirstdoctemplateposition). Değer sonraki konumuna bu çağrısı tarafından güncelleştirilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `GetNextDocTemplate` çağrısıyla ilk konum kurarsanız ileriye doğru yineleme döngü `GetFirstDocTemplatePosition`.  
  
 Emin olmanız gerekir, **konumu** değeri geçerli. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Alınan belge şablonu son ise kullanılabilir, ardından yeni değeri `pos` ayarlanır **NULL**.  
  
##  <a name="getprinterdevicedefaults"></a>  CWinApp::GetPrinterDeviceDefaults  
 Bir yazıcıya yazdırma için cihaz bağlamı hazırlamak için bu üye işlevini çağırın.  
  
```  
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```  
  
### <a name="parameters"></a>Parametreler  
 *pPrintDlg*  
 Bir işaretçi bir [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli yazıcı Varsayılanları Windows'dan alır. INI gerektiğinde dosya veya yazdırma kurulumunda kullanıcı tarafından ayarlanan son yazıcı yapılandırmayı kullanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]  
  
##  <a name="getprofilebinary"></a>  CWinApp::GetProfileBinary  
 Uygulamanın kayıt defteri belirtilen bölümü içindeki bir giriş ikili veri almak için bu üye işlevini çağırın veya. INI dosyası.  
  
```  
BOOL GetProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszSection*  
 Noktaları null ile sonlandırılmış dizeye giriş içeren bölüm belirtir.  
  
 *lpszEntry*  
 Değeri alınacak girdisi içeren null ile sonlandırılmış bir dize noktalarına.  
  
 *ppData*  
 Veri adresi alacağı bir işaretçi işaret.  
  
 *pBytes*  
 Verilerin boyutunu (bayt) alacak bir UINT noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu büyük küçük harfe duyarlı, bu nedenle değil dizelerde *lpszSection* ve *lpszEntry* parametreleri durumda farklı olabilir.  
  
> [!NOTE]
> **GetProfileBinary** bir arabellek ayırır ve onun adresini döndürür \* *ppData*. Arabellek kullanarak boşaltma çağıran sorumludur **delete []**.  
  
> [!IMPORTANT]
>  Bu işlev tarafından döndürülen veri sonlandırıldı mutlaka NULL olmayan ve arayan doğrulama gerçekleştirmeniz gerekir. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]  
  
 Ek bir örnek için bkz: [CWinApp::WriteProfileBinary](#writeprofilebinary).  
  
##  <a name="getprofileint"></a>  CWinApp::GetProfileInt  
 Bir giriş uygulamanın kayıt defteri belirtilen bölümü içindeki tamsayı değerini almak için bu üye işlevini çağırın veya. INI dosyası.  
  
```  
UINT GetProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nDefault);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszSection`  
 Noktaları null ile sonlandırılmış dizeye giriş içeren bölüm belirtir.  
  
 `lpszEntry`  
 Değeri alınacak girdisi içeren null ile sonlandırılmış bir dize noktalarına.  
  
 `nDefault`  
 Framework giriş bulamazsanız, döndürülecek varsayılan bir değer belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, belirtilen giriş izleyen dizesinin tamsayı değeri. Dönüş değeri değeri `nDefault` işlevi giriş bulamazsa parametresi. Belirtilen girdiye karşılık gelen değer bir tamsayı değilse dönüş değeri 0'dır.  
  
 Bu üye işlevi değeri için onaltılık gösterimini destekler. INI dosyası. İmzalı bir tamsayı aldığınızda değerine atamalısınız bir `int`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu büyük küçük harfe duyarlı, bu nedenle değil dizelerde `lpszSection` ve `lpszEntry` parametreleri durumda farklı olabilir.  
  
> [!IMPORTANT]
>  Bu işlev tarafından döndürülen veri sonlandırıldı mutlaka NULL olmayan ve arayan doğrulama gerçekleştirmeniz gerekir. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]  
  
 Ek bir örnek için bkz: [CWinApp::WriteProfileInt](#writeprofileint).  
  
##  <a name="getprofilestring"></a>  CWinApp::GetProfileString  
 Uygulamanın kayıt defterinde belirtilen bölüm içerisinde bir girdi ile ilişkili dizesini almak için bu üye işlevini çağırın veya. INI dosyası.  
  
```  
CString GetProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszSection`  
 Noktaları null ile sonlandırılmış dizeye giriş içeren bölüm belirtir.  
  
 `lpszEntry`  
 İşaret eder, dize alınmasına izin girdisi içeren null ile sonlandırılmış bir dize. Bu değer olmamalıdır **NULL**.  
  
 `lpszDefault`  
 Giriş başlatma dosyasında bulunursa belirtilen giriş için varsayılan dize değeri noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri uygulamanın dizesi değeridir. INI dosyası veya `lpszDefault` dize bulunursa. Çerçeve tarafından desteklenen maksimum dize uzunluğu, `_MAX_PATH`. Varsa `lpszDefault` olan **NULL**, dönüş değeri boş bir dizedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!IMPORTANT]
>  Bu işlev tarafından döndürülen veri sonlandırıldı mutlaka NULL olmayan ve arayan doğrulama gerçekleştirmeniz gerekir. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Örneğin başka bir örnek için bkz [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="getsectionkey"></a>  CWinApp::GetSectionKey  
 HKEY_CURRENT_USER anahtarını döner\\"Yazılım" \RegistryKey\AppName\lpszSection.  
  
```  
HKEY GetSectionKey(
LPCTSTR lpszSection,  
CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszSection`  
 Alınması anahtarın adı.  
  
 `pTM`  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa bölüm anahtarı; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hideapplication"></a>  CWinApp::HideApplication  
 Açık belgeleri kapatmadan önce bir uygulama gizlemek için bu üye işlevini çağırın.  
  
```  
void HideApplication();
```  
  
##  <a name="htmlhelp"></a>  CWinApp::HtmlHelp  
 HTMLHelp uygulama çağırmak için bu üye işlevini çağırın.  
  
```  
virtual void HtmlHelp(
    DWORD_PTR dwData,  
    UINT nCmd = 0x000F);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwData`  
 Ek veri belirtir. Kullanılan değer değerine bağlıdır `nCmd` parametresi.  
  
 `nCmd`  
 İstenen Yardım türünü belirtir. Olası değerler ve nasıl etkilediklerini listesi `dwData` parametresi bkz `uCommand` hakkında HTMLHelp API işlevi Windows SDK'sındaki açıklanan parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework de HTMLHelp uygulama çağırmak için bu işlevi çağırır.  
  
 Uygulamanızı sonlandırıldığında framework HTMLHelp uygulama otomatik olarak kapatılır.  
  
##  <a name="initinstance"></a>  CWinApp::InitInstance  
 Windows aynı programın aynı anda çalıştırmak için çok sayıda kopyasını sağlar.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama başlatma kavramsal olarak iki bölüme ayrılmıştır: ilk yapılır tek seferlik uygulama başlatma zaman program çalıştırılır ve her çalışan örneği başlatma zaman bir kopyasını ilk kez dahil olmak üzere programı çalıştırır. Framework'ün uyarlamasını `WinMain` bu işlevi çağırır.  
  
 Geçersiz kılma `InitInstance` her Windows altında çalışan, uygulamanızın yeni bir örneğini başlatılamadı. Genellikle, kılmanız `InitInstance` ana penceresi nesnenizi oluşturduktan ve ayarlamak için `CWinThread::m_pMainWnd` pencereye işaret edecek şekilde veri üyesi. Bu üye işlevi geçersiz kılma ile ilgili daha fazla bilgi için bkz: [CWinApp: uygulama sınıfı](../../mfc/cwinapp-the-application-class.md).  
  
> [!NOTE]
>  MFC uygulamaları tek iş parçacıklı (STA) başlatılması gerekir. Çağırırsanız [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) içinde `InitInstance` geçersiz kılma, belirtin `COINIT_APARTMENTTHREADED` (yerine `COINIT_MULTITHREADED`). Daha fazla bilgi için bkz: MFC uygulaması olarak bir birden çok iş parçacıklı grup (828643) uygulama başlattığınızda yanıt vermiyor [ http://support.microsoft.com/default.aspxscid=kb; en-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]  
  
##  <a name="istaskbarinteractionenabled"></a>  CWinApp::IsTaskbarInteractionEnabled  
 Windows 7 görev etkileşim etkin olup olmadığını bildirir.  
  
```  
virtual BOOL IsTaskbarInteractionEnabled();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` varsa `EnableTaskbarInteraction` çağrıldı ve Windows 7 veya üstü işletim sistemidir.  
  
### <a name="remarks"></a>Açıklamalar  
 Görev etkileşim MDI uygulama fare işaretçisini uygulama görev çubuğu düğmesi olduğunda görüntülenen ayrı sekmeli küçük resimlerdeki MDI içeriğini görüntüler anlamına gelir.  
  
##  <a name="loadcursor"></a>  CWinApp::LoadCursor  
 Tarafından adlı imleç kaynak yükler `lpszResourceName` veya tarafından belirtilen `nIDResource` geçerli yürütülebilir dosya.  
  
```  
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszResourceName`  
 İmleç kaynağın adını içeren null ile sonlandırılmış bir dize noktalarına. Kullanabileceğiniz bir `CString` bu bağımsız değişken için.  
  
 `nIDResource`  
 İmleç kaynak kimliği. Kaynakların listesi için bkz: [LoadCursor](http://msdn.microsoft.com/library/windows/desktop/ms648391) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa bir imleç için bir tanıtıcı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 `LoadCursor` yalnızca, daha önce yüklenmemiş varsa imleci belleğe yükler; Aksi takdirde, mevcut kaynak tanıtıcısı alır.  
  
 Kullanım [LoadStandardCursor](#loadstandardcursor) veya [LoadOEMCursor](#loadoemcursor) önceden tanımlanmış Windows imleçler erişmek için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]  
  
##  <a name="loadicon"></a>  CWinApp::LoadIcon  
 Tarafından adlı simgesi Kaynak yükler `lpszResourceName` veya tarafından belirtilen `nIDResource` yürütülebilir dosya.  
  
```  
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszResourceName`  
 Simge kaynağın adını içeren null ile sonlandırılmış bir dize noktalarına. Aynı zamanda bir `CString` bu bağımsız değişken için.  
  
 `nIDResource`  
 Simge kaynak kimliği sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa bir simge için bir tanıtıcı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 `LoadIcon` yalnızca, daha önce yüklenmemiş simgesi yükler; Aksi takdirde, mevcut kaynak tanıtıcısı alır.  
  
 Kullanabileceğiniz [LoadStandardIcon](#loadstandardicon) veya [LoadOEMIcon](#loadoemicon) önceden tanımlanmış Windows simgeleri erişmek için üye işlevi.  
  
> [!NOTE]
>  Bu üye işlevi Win32 API işlev çağrılarını [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), hangi yalnızca yükleyebilirsiniz büyüklüğü uyan için bir simge **SM_CXICON** ve **SM_CYICON** sistem ölçüm değerleri.  
  
##  <a name="loadoemcursor"></a>  CWinApp::LoadOEMCursor  
 Yükleri Windows imleç kaynak tarafından belirtilen önceden tanımlanmış `nIDCursor`.  
  
```  
HCURSOR LoadOEMCursor(UINT nIDCursor) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDCursor`  
 Bir **OCR_** önceden tanımlanmış bir Windows imleç belirtir sabit tanımlayıcı bildirimi. Bilmeniz gereken **# OEMRESOURCE define** önce **#include \<afxwin.h >** erişmek için **OCR_** WINDOWS sabitler. H.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa bir imleç için bir tanıtıcı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `LoadOEMCursor` veya [LoadStandardCursor](#loadstandardcursor) önceden tanımlanmış Windows imleçler erişmek için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]  
  
 [!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]  
  
##  <a name="loadoemicon"></a>  CWinApp::LoadOEMIcon  
 Yükleri Windows önceden tanımlanmış simge kaynak tarafından belirtilen `nIDIcon`.  
  
```  
HICON LoadOEMIcon(UINT nIDIcon) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDIcon`  
 Bir **OIC_** önceden tanımlanmış bir Windows simgesi belirtir sabit tanımlayıcı bildirimi. Bilmeniz gereken **# OEMRESOURCE define** önce **#include \<afxwin.h >** erişmek için **OIC_** Windows sabitleri. H.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa bir simge için bir tanıtıcı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `LoadOEMIcon` veya [LoadStandardIcon](#loadstandardicon) önceden tanımlanmış Windows simgeleri erişmek için üye işlevi.  
  
##  <a name="loadstandardcursor"></a>  CWinApp::LoadStandardCursor  
 Yükleri Windows imleç kaynak önceden tanımlanmış, `lpszCursorName` belirtir.  
  
```  
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszCursorName`  
 Bir **IDC_** önceden tanımlanmış bir Windows imleç belirtir sabit tanımlayıcı bildirimi. Bu tanımlayıcı, WİNDOWS'da tanımlanır. H. Aşağıdaki liste olası önceden tanımlanmış değerler ve anlamı gösterir `lpszCursorName`:  
  
- **IDC_ARROW** standart ok imleç  
  
- **IDC_IBEAM** standart metin ekleme imleç  
  
- **IDC_WAIT** Windows uzun süren bir görevi gerçekleştirirken kullanılan kum saati imleç  
  
- **IDC_CROSS** artı şeklindeki imleç seçilmek  
  
- **IDC_UPARROW** işaret düz yukarı ok  
  
- **IDC_SIZE** kullanılmaz ve desteklenmeyen; kullanın **IDC_SIZEALL**  
  
- **IDC_SIZEALL** dört yönlü oka. Bir pencereyi yeniden boyutlandırmak için imleç.  
  
- **IDC_ICON** kullanılmaz ve desteklenmeyen. Kullanım **IDC_ARROW**.  
  
- **IDC_SIZENWSE** iki oka sol üst ve alt sağ uçta ile  
  
- **IDC_SIZENESW** iki oka sağ ve alt sol üst uçta ile  
  
- **IDC_SIZEWE** yatay iki başlı ok  
  
- **IDC_SIZENS** dikey iki başlı ok  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa bir imleç için bir tanıtıcı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `LoadStandardCursor` veya [LoadOEMCursor](#loadoemcursor) önceden tanımlanmış Windows imleçler erişmek için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]  
  
##  <a name="loadstandardicon"></a>  CWinApp::LoadStandardIcon  
 Yükleri Windows önceden tanımlanmış simge kaynak, `lpszIconName` belirtir.  
  
```  
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszIconName`  
 Önceden tanımlanmış bir Windows simgesi belirten bir bildirim sabit tanımlayıcısı. Bu tanımlayıcı, WİNDOWS'da tanımlanır. H. Olası önceden tanımlanmış değerler ve açıklamalarının listesi için bkz: *lpIconName* parametresinde [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa bir simge için bir tanıtıcı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `LoadStandardIcon` veya [LoadOEMIcon](#loadoemicon) önceden tanımlanmış Windows simgeleri erişmek için üye işlevi.  
  
##  <a name="loadstdprofilesettings"></a>  CWinApp::LoadStdProfileSettings  
 Bu üye işlevi içinden çağrısı [InitInstance](#initinstance) etkinleştirmek ve en son kullanılan (MRU) dosya listesini yüklemek ve en son durum önizlemek için üye işlevi.  
  
```  
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMaxMRU`  
 İzlemek için son kullanılan dosya sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `nMaxMRU` 0 olduğundan, hiçbir MRU Listesi korunur.  
  
##  <a name="m_bhelpmode"></a>  CWinApp::m_bHelpMode  
 **DOĞRU** uygulama (standart olarak çağrılan SHIFT + F1); Yardım bağlamı modundaysa, aksi takdirde **FALSE**.  
  
```  
BOOL m_bHelpMode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yardım içeriği modunda, imleci bir soru işareti haline gelir ve kullanıcı hakkında ekranı taşıyabilirsiniz. Özel işleme Yardım modundayken uygulamak istiyorsanız, bu bayrak inceleyin. `m_bHelpMode` tür genel bir değişkendir **BOOL**.  
  
##  <a name="m_dwrestartmanagersupportflags"></a>  CWinApp::m_dwRestartManagerSupportFlags  
 Yeniden başlatma Yöneticisi'ni nasıl davranacağını belirleyen bayrak.  
  
```  
DWORD m_dwRestartManagerSupportFlags;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma Yöneticisi'ni etkinleştirmek için ayarlanmış `m_dwRestartManagerSupportFlags` istediğiniz davranışı. Aşağıdaki tabloda kullanılabilir bayrakları gösterir.  
  
|||  
|-|-|  
|Bayrağı|Açıklama|  
|`AFX_RESTART_MANAGER_SUPPORT_RESTART`|Uygulamayı kullanarak kayıtlı [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager). Yeniden başlatma Yöneticisi beklenmedik şekilde bulunup bulunmadığını uygulamayı yeniden başlatma için sorumludur.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`|Uygulama yeniden başlatma Yöneticisi ile kaydedilir ve uygulama yeniden başlatıldığında yeniden başlatma Yöneticisi Kurtarma geri çağırma işlevini çağırır. Varsayılan kurtarma geri çağırma işlevidir [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`|Otomatik kaydetme etkinleştirildiğinde ve yeniden başlatma Yöneticisi autosaves tüm açık belgeleri uygulama yeniden başlatıldığında.|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`|Otomatik kaydetme etkinleştirildiğinde ve yeniden başlatma Yöneticisi autosaves düzenli aralıklarla tüm açık belgeleri. Aralık tarafından tanımlanan [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval).|  
|- `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`|Yeniden başlatma Yöneticisi beklenmeyen bir çıkış uygulamadan yeniden başlatıldıktan sonra önceden açık belgeler açılır. [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md) açık belgelerin listesini depolamak ve bunları geri işler.|  
|- `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`|Yeniden başlatma Yöneticisi uygulama yeniden başlatıldıktan sonra otomatik olarak kaydedilmiş dosyaların geri yüklemek için kullanıcıya sorar. `CDataRecoveryHandler` Sınıfı kullanıcı sorgular.|  
|- `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`|Birleşimi `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_SUPPORT_RECOVER`, ve `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS`|Birleşimi `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, ve `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS`|Birleşimi `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, ve `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS`|Birleşimi `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, ve `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
  
##  <a name="m_ehelptype"></a>  CWinApp::m_eHelpType  
 Bu veri üyesi türü numaralandırılmış türüdür **AFX_HELP_TYPE**, içinde tanımlanan `CWinApp` sınıfı.  
  
```  
AFX_HELP_TYPE m_eHelpType;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **AFX_HELP_TYPE** numaralandırması şu şekilde tanımlanır:  
  
```  
enum AFX_HELP_TYPE {  
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };  
```  
  
-   HTML Yardımı için uygulamanın Yardım ayarlamak için arama [SetHelpMode](#sethelpmode) ve belirtin **afxHTMLHelp**.  
  
-   WinHelp uygulamanın Yardım ayarlamak için arama `SetHelpMode` ve belirtin **afxWinHelp**.  
  
##  <a name="m_hinstance"></a>  CWinApp::m_hInstance  
 Karşılık gelen `hInstance` parametresine geçirilen Windows tarafından `WinMain`.  
  
```  
HINSTANCE m_hInstance;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_hInstance` Veri üyesi olan Windows altında çalışan uygulamanın geçerli örneği için bir tanıtıcı. Bu genel işlevi tarafından döndürülen [Afxgetınstancehandle](application-information-and-management.md#afxgetinstancehandle). `m_hInstance` tür genel bir değişkendir `HINSTANCE`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]  
  
##  <a name="m_lpcmdline"></a>  CWinApp::m_lpCmdLine  
 Karşılık gelen `lpCmdLine` parametresine geçirilen Windows tarafından `WinMain`.  
  
```  
LPTSTR m_lpCmdLine;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Noktaları null ile sonlandırılmış dizeye uygulama için komut satırını belirtir. Kullanım `m_lpCmdLine` uygulama başlatıldığında girilen kullanıcı herhangi bir komut satırı bağımsız değişkeni erişmek için. `m_lpCmdLine` tür genel bir değişkendir `LPTSTR`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="m_nautosaveinterval"></a>  CWinApp::m_nAutosaveInterval  
 Autosaves arasındaki milisaniye cinsinden süre uzunluğu.  
  
```  
int m_nAutosaveInterval;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirlenen aralıklarla otomatik kaydetme açık belgeler için yeniden başlatma Yöneticisi'ni yapılandırabilirsiniz. Uygulamanızın otomatik kaydetme dosyaları değil varsa, bu parametre bir etkisi yoktur.  
  
##  <a name="m_ncmdshow"></a>  CWinApp::m_nCmdShow  
 Karşılık gelen `nCmdShow` parametresine geçirilen Windows tarafından `WinMain`.  
  
```  
int m_nCmdShow;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçmesi `m_nCmdShow` çağırdığınızda bağımsız değişken olarak [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) uygulamanızın ana penceresi. `m_nCmdShow` tür genel bir değişkendir `int`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]  
  
##  <a name="m_pactivewnd"></a>  CWinApp::m_pActiveWnd  
 Bu veri üyesi, OLE sunucu uygulama etkinleştirilmiş yerinde OLE kapsayıcı uygulamanın ana penceresinde gösteren bir işaretçi depolamak için kullanın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu veri üyesi ise **NULL**, uygulama yerinde etkin değil.  
  
 Çerçeve penceresi yerinde bir OLE kapsayıcı uygulama tarafından etkinleştirilmiş olduğunda bu üye değişkeni framework ayarlar.  
  
##  <a name="m_pdatarecoveryhandler"></a>  CWinApp::m_pDataRecoveryHandler  
 Uygulama için veri kurtarma işleyicisi işaretçi.  
  
```  
CDataRecoveryHandler* m_pDataRecoveryHandler;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kurtarma işleyicisi uygulamanın izler açık belgeler veya autosaves bunları. Çerçeve veri kurtarma işleyicisi beklenmedik biçimde çıktıktan sonra bir uygulama başlatıldığında otomatik olarak kaydedilmiş dosyaların geri yüklemek için kullanır. Daha fazla bilgi için bkz: [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md).  
  
##  <a name="m_pszappname"></a>  CWinApp::m_pszAppName  
 Uygulamanın adını belirtir.  
  
```  
LPCTSTR m_pszAppName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama adı için geçirilen parametre gelebilir [CWinApp](#cwinapp) oluşturucusu, veya kimliğine sahip kaynak dizeye belirtilmezse **AFX_IDS_APP_TITLE**. Uygulama adı kaynak bulunmazsa, programın gelir. EXE dosya adı.  
  
 Genel işlevi tarafından döndürülen [AfxGetAppName](application-information-and-management.md#afxgetappname). `m_pszAppName` tür genel bir değişkendir **const char\***.  
  
> [!NOTE]
>  Bir değere atarsanız `m_pszAppName`, dinamik olarak öbek üzerinde ayrılmalıdır. `CWinApp` Yıkıcı çağrıları **ücretsiz**(this işaretçisi ile). Birçok kullanmak istediğiniz `_tcsdup`ayırma yapmak için çalışma zamanı kitaplığı işlevi (). Ayrıca, yeni bir değer atamadan önce geçerli işaretçisi ile ilişkilendirilmiş bellek boşaltın. Örneğin:  
  
 [!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]  
  
##  <a name="m_pszexename"></a>  CWinApp::m_pszExeName  
 Uygulamanın uzantısı olmayan bir yürütülebilir dosya adını içerir.  
  
```  
LPCTSTR m_pszExeName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Farklı [m_pszAppName](#m_pszappname), bu ad boşluk içeremez. `m_pszExeName` tür genel bir değişkendir **const char\***.  
  
> [!NOTE]
>  Bir değere atarsanız `m_pszExeName`, dinamik olarak öbek üzerinde ayrılmalıdır. `CWinApp` Yıkıcı çağrıları **ücretsiz**(this işaretçisi ile). Birçok kullanmak istediğiniz `_tcsdup`ayırma yapmak için çalışma zamanı kitaplığı işlevi (). Ayrıca, yeni bir değer atamadan önce geçerli işaretçisi ile ilişkilendirilmiş bellek boşaltın. Örneğin:  
  
 [!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]  
  
##  <a name="m_pszhelpfilepath"></a>  CWinApp::m_pszHelpFilePath  
 Uygulamanın Yardım dosyasının yolunu içerir.  
  
```  
LPCTSTR m_pszHelpFilePath;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, framework başlatır `m_pszHelpFilePath` uygulamayla adına ". HLP"eklenir. Yardım dosyasının adını değiştirmek için ayarlayın `m_pszHelpFilePath` istenen Yardım dosyasının tam adını içeren bir dize yönlendirin. Bunu yapmak için uygun bir uygulamanın içinde yerdir [InitInstance](#initinstance) işlevi. `m_pszHelpFilePath` tür genel bir değişkendir **const char\***.  
  
> [!NOTE]
>  Bir değere atarsanız `m_pszHelpFilePath`, dinamik olarak öbek üzerinde ayrılmalıdır. `CWinApp` Yıkıcı çağrıları **ücretsiz**(this işaretçisi ile). Birçok kullanmak istediğiniz `_tcsdup`ayırma yapmak için çalışma zamanı kitaplığı işlevi (). Ayrıca, yeni bir değer atamadan önce geçerli işaretçisi ile ilişkilendirilmiş bellek boşaltın. Örneğin:  
  
 [!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]  
  
##  <a name="m_pszprofilename"></a>  CWinApp::m_pszProfileName  
 Uygulamanın adını içerir. INI dosyası.  
  
```  
LPCTSTR m_pszProfileName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_pszProfileName` tür genel bir değişkendir **const char\***.  
  
> [!NOTE]
>  Bir değere atarsanız `m_pszProfileName`, dinamik olarak öbek üzerinde ayrılmalıdır. `CWinApp` Yıkıcı çağrıları **ücretsiz**(this işaretçisi ile). Birçok kullanmak istediğiniz `_tcsdup`ayırma yapmak için çalışma zamanı kitaplığı işlevi (). Ayrıca, yeni bir değer atamadan önce geçerli işaretçisi ile ilişkilendirilmiş bellek boşaltın. Örneğin:  
  
 [!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]  
  
##  <a name="m_pszregistrykey"></a>  CWinApp::m_pszRegistryKey  
 Kayıt defteri veya INI dosyası uygulama profili ayarları depolandığı belirlemek için kullanılır.  
  
```  
LPCTSTR m_pszRegistryKey;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Normalde, bu veri üyesi salt okunur olarak kabul edilir.  
  
-   Değer bir kayıt defteri anahtarında depolanır. Uygulama profili ayarının adını aşağıdaki kayıt defteri anahtarına eklenir: HKEY_CURRENT_USER/Software/LocalAppWizard-oluşturulan /.  
  
 Bir değere atarsanız `m_pszRegistryKey`, dinamik olarak öbek üzerinde ayrılmalıdır. `CWinApp` Yıkıcı çağrıları **ücretsiz**(this işaretçisi ile). Birçok kullanmak istediğiniz `_tcsdup`ayırma yapmak için çalışma zamanı kitaplığı işlevi (). Ayrıca, yeni bir değer atamadan önce geçerli işaretçisi ile ilişkilendirilmiş bellek boşaltın. Örneğin:  
  
 [!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]  
  
##  <a name="m_pszappid"></a>  CWinApp::m_pszAppID  
 Uygulama kullanıcı modeli kimliği  
  
```  
LPCTSTR m_pszAppID;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="oncontexthelp"></a>  CWinApp::OnContextHelp  
 SHIFT + F1 Yardımı uygulama içinde işler.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eklemelisiniz bir `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` deyimi, `CWinApp` sınıfı ileti eşlemesi ve ayrıca Hızlandırıcı tablosu girişini, genellikle SHIFT + bu üye işlevini etkinleştirmek için F1, ekleyin.  
  
 `OnContextHelp` Yardım modu uygulamaya koyar. İmleç değişiklikleri bir ok ve soru işareti ve kullanıcı fare işaretçisini ve iletişim kutusu, pencere, menü veya komut düğmesi seçmek için sol fare düğmesine basın. Bu üye işlevi imleç altındaki Nesne Yardım bağlamını alır ve bu Yardım bağlam Windows işleviyle WinHelp çağırır.  
  
##  <a name="onddecommand"></a>  CWinApp::OnDDECommand  
 Ana çerçeve penceresi bir DDE aldığında çerçevesi tarafından çağrılır ileti yürütün.  
  
```  
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszCommand*  
 Uygulama tarafından alınan DDE komut dizesi noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Komut işleniyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama komutu bir belgeyi açmak için bir istek varsa, belirtilen belge açılır olup olmadığını denetler ve. Kullanıcı bir veri dosyası tıklattığında Windows Dosya Yöneticisi gibi DDE komutu dizeleri genellikle gönderir. Geçersiz kılma diğer DDE işlemek için bu işlev yazdırmak için komutu gibi komutları yürütün.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]  
  
##  <a name="onfilenew"></a>  CWinApp::OnFileNew  
 Implements `ID_FILE_NEW` komutu.  
  
```  
afx_msg void OnFileNew();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eklemelisiniz bir `ON_COMMAND( ID_FILE_NEW, OnFileNew )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Etkinleştirilirse, bu işlev dosya yeni komutu yürütme işler.  
  
 Bkz: [Teknik Not 22](../../mfc/tn022-standard-commands-implementation.md) varsayılan davranışını ve bu üye işlevi geçersiz kılma konusunda rehberlik hakkında bilgi için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileopen"></a>  CWinApp::OnFileOpen  
 Implements `ID_FILE_OPEN` komutu.  
  
```  
afx_msg void OnFileOpen();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eklemelisiniz bir `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Etkinleştirilirse, bu işlev Dosya Aç komutu yürütme işler.  
  
 Varsayılan davranışı hakkında bilgi ve bu üye işlevi geçersiz kılmak nasıl hakkında yönergeler için bkz: [Teknik Not 22](../../mfc/tn022-standard-commands-implementation.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileprintsetup"></a>  CWinApp::OnFilePrintSetup  
 Implements **ıd_fıle_prınt_setup** komutu.  
  
```  
afx_msg void OnFilePrintSetup();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eklemelisiniz bir `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Etkinleştirilirse, bu işlev dosya Yazdır komutu yürütme işler.  
  
 Varsayılan davranışı hakkında bilgi ve bu üye işlevi geçersiz kılmak nasıl hakkında yönergeler için bkz: [Teknik Not 22](../../mfc/tn022-standard-commands-implementation.md).  
  
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
  
 Eklemelisiniz bir `ON_COMMAND( ID_HELP, OnHelp )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Kullanıcı F1 tuşuna bastığında etkinleştirilirse, çerçevesi tarafından çağrılır.  
  
 Bu ileti işleyicisi işlevi varsayılan uygulaması geçerli pencere, iletişim kutusu veya menü öğesi karşılık gelir ve WINHELP çağrıları Yardım bağlamı belirler. EXE. Bağlam şu anda kullanılabilir durumdaysa, işlevi varsayılan bağlamını kullanır.  
  
 Pencere, iletişim kutusu, menü öğesi veya odağa sahip araç çubuğu düğmesi dışında Yardım bağlamı için bir şeyler ayarlamak için bu üye işlevi geçersiz kılar. Çağrı `WinHelp` istenen ile içerik kimliğini Yardım  
  
##  <a name="onhelpfinder"></a>  CWinApp::OnHelpFinder  
 İşleme **ID_HELP_FINDER** ve **ıd_default_help** komutları.  
  
```  
afx_msg void OnHelpFinder();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eklemelisiniz bir `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Kullanıcı, uygulamanızın çağrılacak Yardım Bulucu komutu seçtiğinde etkinleştirilirse, framework bu ileti işleyicisi işlevi çağırır `WinHelp` standart **HELP_FINDER** konu.  
  
##  <a name="onhelpindex"></a>  CWinApp::OnHelpIndex  
 İşleme **ıd_help_ındex** komut ve varsayılan Yardım konusunun sağlar.  
  
```  
afx_msg void OnHelpIndex();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eklemelisiniz bir `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Kullanıcı, uygulamanızın çağrılacak Yardım dizini komutu seçtiğinde etkinleştirilirse, framework bu ileti işleyicisi işlevi çağırır `WinHelp` standart **HELP_INDEX** konu.  
  
##  <a name="onhelpusing"></a>  CWinApp::OnHelpUsing  
 İşleme **ıd_help_usıng** komutu.  
  
```  
afx_msg void OnHelpUsing();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eklemelisiniz bir `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` deyimi, `CWinApp` bu üye işlevini etkinleştirmek için ileti eşlemesi sınıfı. Kullanıcı, uygulamanızın çağırmak için Yardım'ı kullanarak komutunu seçtiğinde framework bu ileti işleyicisi işlevi çağırır `WinHelp` standart uygulama **HELP_HELPONHELP** konu.  
  
##  <a name="onidle"></a>  CWinApp::OnIdle  
 Boşta kalma süresi işlemini gerçekleştirmek için bu üye işlevi geçersiz kılar.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `lCount`  
 Bir sayaç artırılır her zaman `OnIdle` uygulamanın ileti sırası boş olduğunda çağrılır. Bu sayı, yeni bir ileti işlenen her zaman 0 olarak sıfırlanır. Kullanabileceğiniz `lCount` uygulama işlenirken boşta bir ileti olmadan göreli süreyi belirlemek için parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha fazla boşta işleme süresi almak için sıfır olmayan; Daha fazla boşta kalma süresi gerekirse 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnIdle` uygulamanın ileti sırası boş olduğunda varsayılan ileti döngüde adı verilir. Boşta işleyici görevler kendi arka plan çağırmak için geçersiz kılma kullanın.  
  
 `OnIdle` Boşta işleme zaman gerekli olduğunu göstermek için 0 değerini döndürmelidir. `lCount` Parametresi, her zaman artırılır `OnIdle` ileti sırası boş ve yeni bir ileti işlenir her zaman 0 olarak sıfırlar olduğunda çağrılır. Bu sayısına göre farklı boşta yordamları çağırabilirsiniz.  
  
 Boşta döngü işleme özetlenmektedir:  
  
1.  Microsoft Foundation Class Kitaplığı ileti döngüde ileti sırası denetler ve bekleyen iletiler Hayır bulur, çağıran `OnIdle` kaynakları 0 olarak ve uygulama nesnesi için `lCount` bağımsız değişkeni.  
  
2. `OnIdle` bir işlem gerçekleştirir ve belirtmek için sıfır olmayan bir değer çağrılabilir yeniden yapmak için döndürür başka bir işleme.  
  
3.  İleti döngüsü ileti sırası yeniden denetler. Hiçbir ileti bekleyen yoksa çağırır `OnIdle` yeniden artırma `lCount` bağımsız değişkeni.  
  
4.  Sonuç olarak, `OnIdle` tüm boşta görevlerinin işlemeyi tamamladıktan ve 0 döndürür. Bu arama durdurmak için ileti döngüsü söyler `OnIdle` sonraki iletiyi ileti kuyruğundan alınana kadar bu noktada boşta döngü 0 olarak ayarlayın bağımsız değişkeni ile yeniden başlatır.  
  
 Uzun görevleri sırasında gerçekleştirmeyin `OnIdle` uygulamanızı kadar kullanıcı girişi işleyemediği için `OnIdle` döndürür.  
  
> [!NOTE]
>  Varsayılan uygulaması `OnIdle` güncelleştirmeleri komutu menü öğeleri ve araç çubuğu düğmeleri gibi kullanıcı arabirimi nesneleri ve iç veri yapısına cleanup gerçekleştirir. Bu nedenle, geçersiz kılarsanız `OnIdle`, çağırmalısınız `CWinApp::OnIdle` ile `lCount` geçersiz kılınan sürümünüzde. Tüm temel sınıf boşta işleme ilk çağrı (diğer bir deyişle, temel sınıf kadar `OnIdle` 0 döndürür). Taban sınıfı işlem tamamlanmadan önce iş gerçekleştirmeniz gerekiyorsa, uygun seçmek için temel sınıf uygulamasını gözden `lCount` işleriniz için sırasında.  
  
 İstemiyorsanız, `OnIdle` ileti kuyruğundan alınan bir ileti olduğunda çağrılacak, kılabilirsiniz [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage). Bir uygulama çok kısa bir süre ölçer ayarladıysanız ya da sistem gönderiyorsa **WM_SYSTIMER** iletisi, ardından `OnIdle` sürekli olarak adlandırılır ve performansı düşebilir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki iki nasıl kullanılacağını örnekler `OnIdle`. İlk örnek kullanarak iki boşta görevleri işler `lCount` görevleri önceliğini belirlemek için bağımsız değişken. Yüksek öncelikli ilk görevdir ve mümkün olduğunca yapmalısınız. İkinci görev daha az önemlidir ve yalnızca kullanıcı girişi uzun bir duraklama olduğunda yapılması gerekir. Temel sınıf sürümü çağrısı Not `OnIdle`. İkinci örnek boşta görevlerinin farklı önceliklere sahip bir grup yönetir.  
  
 [!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]  
  
##  <a name="opendocumentfile"></a>  CWinApp::OpenDocumentFile  
 Framework adlandırılmış açmak için bu yöntemi çağırır [CDocument](../../mfc/reference/cdocument-class.md) uygulamanın dosyası.  
  
```  
virtual CDocument* OpenDocumentFile(
LPCTSTR lpszFileName  
BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszFileName`  
 Açılması için dosyanın adı.  
  
 [in] `bAddToMRU`  
 `TRUE` Belgenin en son dosyalardan biri olduğunu gösterir; `FALSE` belgenin en son dosyalardan biri olmadığını gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CDocument` başarılı; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ada sahip bir belge zaten açıksa, bu belgede ilk çerçeve penceresi odağı alır. Bir uygulama birden çok belge şablonu destekliyorsa, çerçeve dosya adı uzantısı belge yüklemeye için uygun belge şablonu bulmak için kullanır. Başarılı olursa, belge şablonu sonra bir çerçeve penceresi ve belge için görünüm oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="parsecommandline"></a>  CWinApp::ParseCommandLine  
 Komut satırında ayrıştırma ve parametreleri bir seferde bir çok göndermek için bu üye işlevini çağırın [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam).  
  
```  
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `rCmdInfo`  
 Bir başvuru bir [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama Sihirbazı'nı kullanarak yeni bir MFC projesine başlattığınızda, Uygulama Sihirbazı'nı yerel bir örneğini oluşturacak `CCommandLineInfo`ve ardından arama `ProcessShellCommand` ve `ParseCommandLine` içinde [InitInstance](#initinstance) üye işlevi. Bir komut satırı aşağıda açıklanan yol aşağıdaki gibidir:  
  
1.  Oluşturulmakta sonra `InitInstance`, `CCommandLineInfo` nesne iletilir `ParseCommandLine`.  
  
2. `ParseCommandLine` Daha sonra çağırır `CCommandLineInfo::ParseParam` sürekli olarak, her parametre için bir kez.  
  
3. `ParseParam` doldurur `CCommandLineInfo` sonra geçirilen nesne [ProcessShellCommand](#processshellcommand).  
  
4. `ProcessShellCommand` komut satırı bağımsız değişkenleri ve bayrakları işler.  
  
 Çağırabilirsiniz Not `ParseCommandLine` gerektiği gibi doğrudan.  
  
 Komut satırı bayrakları açıklaması için bkz: [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).  
  
##  <a name="pretranslatemessage"></a>  CWinApp::PreTranslateMessage  
 Windows işlevleri gönderilir önce penceresi iletilerine filtre uygulamak için bu işlevi geçersiz kılma [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) varsayılan uygulama Hızlandırıcı tuşu gerçekleştirir çağırmanız gerekir böylece çeviri `CWinApp::PreTranslateMessage` geçersiz kılınan sürümünüzde üye işlevi.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMsg`  
 Bir işaretçi bir [MSG](../../mfc/reference/msg-structure1.md) işlemek için ileti içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti tam işlenmiş, sıfır olmayan `PreTranslateMessage` ve daha fazla işlenmesi gerektiğini değil. İleti normal şekilde işlenmesi, sıfır.  
  
##  <a name="processmessagefilter"></a>  CWinApp::ProcessMessageFilter  
 Framework'ün kanca işlevini filtre ve belirli Windows iletilerini yanıtlamak için bu üye işlevi çağırır.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 `code`  
 Kanca kod belirtir. Bu üye işlev kodunu nasıl işleneceğini belirlemek üzere kullanır. `lpMsg.`  
  
 `lpMsg`  
 Windows için bir işaretçi [MSG](../../mfc/reference/msg-structure1.md) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işleniyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanın normal ileti gönderilmeden önce olayları kanca işlevini işler işleniyor.  
  
 Bu gelişmiş özellik geçersiz kılarsanız framework'ün korumak için temel sınıf sürüm çağırdığınızdan emin olun işleme bağlayın.  
  
##  <a name="processshellcommand"></a>  CWinApp::ProcessShellCommand  
 Bu üye fonksiyonu tarafından çağrılır [InitInstance](#initinstance) gelen geçirilen parametreler kabul etmek için `CCommandLineInfo` tarafından tanımlanan nesnesi `rCmdInfo`ve belirtilen eylemi gerçekleştirir.  
  
```  
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `rCmdInfo`  
 Bir başvuru bir [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kabuk komutu başarılı bir şekilde işlediğinde sıfır olmayan. 0 ise, dönüş **FALSE** gelen [InitInstance](#initinstance).  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama Sihirbazı'nı kullanarak yeni bir MFC projesine başlattığınızda, Uygulama Sihirbazı'nı yerel bir örneğini oluşturacak `CCommandLineInfo`ve ardından arama `ProcessShellCommand` ve [ParseCommandLine](#parsecommandline) içinde `InitInstance` üye işlevi. Bir komut satırı aşağıda açıklanan yol aşağıdaki gibidir:  
  
1.  Oluşturulmakta sonra `InitInstance`, `CCommandLineInfo` nesne iletilir `ParseCommandLine`.  
  
2. `ParseCommandLine` Daha sonra çağırır [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) sürekli olarak, her parametre için bir kez.  
  
3. `ParseParam` doldurur `CCommandLineInfo` sonra geçirilen nesne `ProcessShellCommand`.  
  
4. `ProcessShellCommand` komut satırı bağımsız değişkenleri ve bayrakları işler.  
  
 Veri üyeleri `CCommandLineInfo` tarafından tanımlanan nesnesi [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), içinde tanımlanan aşağıdaki numaralandırılmış türde olan `CCommandLineInfo` sınıfı.  
  
```  
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };  
```
  
 Bu değerlerin her birini, kısa bir açıklama için bkz: `CCommandLineInfo::m_nShellCommand`.  
  
##  <a name="processwndprocexception"></a>  CWinApp::ProcessWndProcException  
 İşleyici, uygulamanızın iletisi ya da komut işleyicileri birinde oluşturulan bir özel yakalamaz her framework bu üye işlevi çağırır.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 *e*  
 Yakalanmayan bir özel durum için bir işaretçi.  
  
 `pMsg`  
 A [MSG](../../mfc/reference/msg-structure1.md) framework bir özel durum nedeniyle windows iletisi hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Windows için döndürülen değer. Normalde bu 0 L windows iletilerini 1 M olur ( **TRUE**) komut iletileri için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi doğrudan çağırmayın.  
  
 Bu üye işlevi varsayılan uygulaması bir ileti kutusu oluşturur. Yakalanmayan Özel durum menü, araç veya Hızlandırıcı komutu hatasının kaynaklanıyorsa "Komutu başarısız oldu" iletisini ileti kutusu görüntüler; Aksi halde, bir "İç uygulama hatası" iletisi görüntüler.  
  
 Bu üye işlevi, özel durumların genel işleme sağlamak için geçersiz kılar. Görüntülenecek ileti kutusu isterseniz, yalnızca temel işlevselliğini çağırın.  
  
##  <a name="register"></a>  CWinApp::Register  
 Tarafından işlenmemiş herhangi bir kayıt görevi gerçekleştirir `RegisterShellFileTypes`.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, sadece TRUE değerini döndürür. Tüm özelleştirilmiş kayıt adımları sağlamak için bu işlevi geçersiz kılar.  
  
##  <a name="registershellfiletypes"></a>  CWinApp::RegisterShellFileTypes  
 Uygulamanızın belge türlerinin tümü Windows Dosya Yöneticisi ile kaydetmek için bu üye işlevini çağırın.  
  
```  
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bCompat`  
 `TRUE` Yazdırma ve yazdırma dosyaları doğrudan Kabuk veya dosyayı bir yazıcı nesnesi sürükleyerek yazdırmak bir kullanıcı izin vermek için Kabuk komutları için kayıt defteri girdileri ekler. Ayrıca, bir defaultIcon anahtar ekler. Varsayılan olarak, bu parametredir `FALSE` geriye dönük uyumluluk için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, ondan içinde Dosya Yöneticisi'ni çift tıklatarak, uygulamanız tarafından oluşturulan bir veri dosyası açmak kullanıcının sağlar. Çağrı `RegisterShellFileTypes` çağırdıktan sonra [AddDocTemplate](#adddoctemplate) her uygulamanızda belge şablonları. Ayrıca [EnableShellOpen](#enableshellopen) çağırdığınızda üye işlevi `RegisterShellFileTypes`.  
  
 `RegisterShellFileTypes` listesini tarar [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) uygulamayı tutar ve her belge şablonu için girişleri için dosya ilişkilendirmeleri Windows korur kayıt veritabanına ekler, nesneleri. Dosya Yöneticisi kullanıcı tıklattığında veri dosyasını açmak için bu girişleri kullanır. Bu dağıtmayı ihtiyacını ortadan kaldıran bir. Uygulamanız ile REG dosyası.  
  
> [!NOTE]
> `RegisterShellFileTypes` kullanıcının yönetici haklarına sahip program çalışıyorsa yalnızca çalışır. Program yönetici haklarına sahip değilse, kayıt defteri anahtarlarını değiştirilemiyor.  
  
 Kayıt veritabanı, belirtilen dosya adı uzantısı zaten başka bir dosya türü ile ilişkilendirir. varsa, yeni bir ilişki oluşturulur. Bkz: `CDocTemplate` biçimi için bir sınıf dizeleri bu bilgileri kaydetmek gerekli.  
  
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
|[in] `bRegisterRecoveryCallback`|`TRUE` Bu örnek uygulamanın bir kurtarma geri çağırma işlevini kullandığını gösterir; `FALSE` yok olduğunu gösterir. Uygulama beklenmedik şekilde çıktığında framework Kurtarma geri çağırma işlevini çağırır. Daha fazla bilgi için bkz: [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|[in] `strRestartIdentifier`|Bu örneği yeniden başlatma Yöneticisi'ni tanımlayan benzersiz bir dize. Yeniden başlatma Yöneticisi bir uygulama her örneği için benzersiz tanımlayıcısıdır.|  
|[in] `pwzCommandLineArgs`|Komut satırından herhangi bir ek bağımsız değişkeni içeren bir dize.|  
|[in] `dwRestartFlags`|Yeniden başlatma Yöneticisi için isteğe bağlı bayraklar. Daha fazla bilgi için Açıklamalar bölümüne bakın.|  
|[in] `pRecoveryCallback`|Kurtarma geri çağırma işlevi. Bu işlev gerçekleştirmeniz gereken bir `LPVOID` parametre olarak giriş ve return bir `DWORD`. Varsayılan kurtarma geri çağırma işlevidir `CWinApp::ApplicationRecoveryCallback`.|  
|[in] `lpvParam`|Giriş parametresi için Kurtarma geri çağırma işlevi. Daha fazla bilgi için bkz: [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|[in] `dwPingInterval`|Kurtarma için dönmek geri çağırma işlevi yeniden başlatma Yöneticisi bekleyeceği süreyi. Bu parametre milisaniye cinsindendir.|  
|[in] `dwCallbackFlags`|Bayrakları Kurtarma geri çağırma işlevine geçirildi. Daha sonraki kullanımlar için ayrılmıştır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK` yöntem başarılı olursa; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızın otomatik kaydetmeyi dosyaları için varsayılan MFC uygulaması kullanıyorsa, basit sürümünü kullanmalısınız `RegisterWithRestartManager`. Karmaşık sürümünü kullanmanız `RegisterWithRestartManager` uygulamanızın otomatik kaydetme davranışını özelleştirmek istiyorsanız.  
  
 Bu yöntem boş bir dize ile çağrısı yaparsanız `strRestartIdentifier`, `RegisterWithRestartManager` Yöneticisi yeniden, bu örneği için benzersiz kimlik dizesi oluşturur.  
  
 Bir uygulama beklenmedik şekilde çıktığında, yeniden başlatma Yöneticisi'ni komut satırından uygulamasını yeniden başlatır ve benzersiz tanımlayıcı isteğe bağlı bir bağımsız değişken olarak yeniden sağlar. Bu senaryoda, framework çağırması `RegisterWithRestartManager` iki kez. İlk çağrıda geldiği [CWinApp::InitInstance](#initinstance) ile dize tanımlayıcısı için boş bir dize. Ardından, yöntem [CWinApp::ProcessShellCommand](#processshellcommand) çağrıları `RegisterWithRestartManager` benzersiz yeniden tanımlayıcısına sahip.  
  
 Bir uygulamayı yeniden başlatma Yöneticisi ile kaydetme sonra uygulamayı yeniden başlatma Yöneticisi'ni izler. Uygulama beklenmedik şekilde bulunup bulunmadığını yeniden başlatma Yöneticisi kapatma işlemi sırasında kurtarma geri çağırma işlevini çağırır. Yeniden başlatma Yöneticisi bekler `dwPingInterval` yanıt Kurtarma geri çağırma işlevi. Kurtarma geri çağırma işlevi bu süre içinde yanıt vermezse, Kurtarma geri çağırma işlevi çalıştırmadan uygulamadan çıkar.  
  
 Varsayılan olarak, dwRestartFlags desteklenmez, ancak gelecekte kullanılmak üzere sağlanır. Olası değerler için `dwRestartFlags` aşağıdaki gibidir:  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="reopenpreviousfilesatrestart"></a>  CWinApp::ReopenPreviousFilesAtRestart  
 Yeniden başlatma Yöneticisi uygulama beklenmedik biçimde çıktı zaman açık olan dosyaları açana olup olmadığını belirler.  
  
```  
virtual BOOL ReopenPreviousFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yeniden başlatma Yöneticisi açana önceden açık dosyaların gösterir; `FALSE` yeniden başlatma Yöneticisi'ni desteklemez gösterir.  
  
##  <a name="restartinstance"></a>  CWinApp::RestartInstance  
 Yeniden başlatma Yöneticisi tarafından başlatılan bir uygulama yeniden başlatma işler.  
  
```  
virtual BOOL CWinApp::RestartInstance();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` veri kurtarma işleyicisi açarsa, daha önce belgeleri Aç; `FALSE` veri kurtarma işleyicisi bir hata varsa veya hiçbir önceden açık belgeler varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir uygulama yeniden başlatma Yöneticisi yeniden başlatıldığında, framework bu yöntemi çağırır. Bu yöntem, veri kurtarma işleyici alır ve otomatik olarak kaydedilmiş dosyaları geri yükler. Bu yöntemi çağırır [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) kullanıcı otomatik olarak kaydedilmiş dosyaları geri istediği olup olmadığını belirlemek için.  
  
 Bu yöntem `FALSE` varsa [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) hiçbir açık belgeler olduğunu belirler. Hiçbir açık belgeler olsaydı, uygulama genellikle başlar.  
  
##  <a name="restoreautosavedfilesatrestart"></a>  CWinApp::RestoreAutosavedFilesAtRestart  
 Uygulama yeniden başlatıldığında yeniden başlatma Yöneticisi'ni otomatik olarak kaydedilmiş dosyaları geri yükler olup olmadığını belirler.  
  
```  
virtual BOOL RestoreAutosavedFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yeniden başlatma Yöneticisi geri yüklemeler otomatik olarak kaydedilmiş dosyaların gösterir; `FALSE` yeniden başlatma Yöneticisi'ni desteklemez gösterir.  
  
##  <a name="run"></a>  CWinApp::Run  
 Varsayılan ileti döngüsü sağlar.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `int` tarafından döndürülen değer `WinMain`.  
  
### <a name="remarks"></a>Açıklamalar  
 **Çalıştırma** edinme ve uygulama alıncaya kadar Windows iletileri gönderir bir **WM_QUIT** ileti. Uygulamanın ileti sırası şu anda hiçbir ileti içeriyorsa **çalıştırmak** çağrıları [ONIDLE](#onidle) boşta kalma süresi işlemini gerçekleştirmek için. Gelen iletileri Git [PreTranslateMessage](#pretranslatemessage) üye işlevi özel işleme ve ardından Windows işlevi için **TranslateMessage** standart klavye çeviri; son olarak,  **DispatchMessage** Windows işlevi çağrılır.  
  
 **Çalıştırma** nadiren geçersiz kılınır, ancak özel davranışı sağlamak üzere geçersiz kılabilirsiniz.  
  
##  <a name="runautomated"></a>  CWinApp::RunAutomated  
 Belirlemek için bu işlevi çağırmak olup olmadığını " **/Automation**"veya" **-Otomasyon**" seçeneği varsa, sunucu uygulaması istemci uygulaması tarafından başlatılan olup olmadığını gösterir.  
  
```  
BOOL RunAutomated();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçenek bulunduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa, komut satırından seçeneği kaldırılır. OLE Otomasyonu hakkında daha fazla bilgi için bkz: [otomasyon sunucuları](../../mfc/automation-servers.md).  
  
##  <a name="runembedded"></a>  CWinApp::RunEmbedded  
 Belirlemek için bu işlevi çağırmak olup olmadığını " **/katıştırma**"veya" **-katıştırma**" seçeneği varsa, sunucu uygulaması istemci uygulaması tarafından başlatılan olup olmadığını gösterir.  
  
```  
BOOL RunEmbedded();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçenek bulunduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa, komut satırından seçeneği kaldırılır. Makaleyi katıştırma daha fazla bilgi için bkz: [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md).  
  
##  <a name="saveallmodified"></a>  CWinApp::SaveAllModified  
 Framework uygulamanın ana çerçeve penceresi kapatıldığında olduğunda tüm belgeleri kaydetme veya aracılığıyla tarafından çağrılan bir `WM_QUERYENDSESSION` ileti.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenli, sonlandırmak sıfır olmayan; 0 güvenli sonlandırmak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi varsayılan uygulamasını çağıran [CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified) sırayla uygulamadaki tüm değiştirilmiş belgeleri için üye işlevi.  
  
##  <a name="selectprinter"></a>  CWinApp::SelectPrinter  
 Belirli bir yazıcı seçmek için bu üye işlevini çağırın ve yazdırma iletişim kutusunda önceden seçilmiş olan yazıcı bırakın.  
  
```  
void SelectPrinter(
    HANDLE hDevNames,  
    HANDLE hDevMode,  
    BOOL bFreeOld = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `hDevNames`  
 İçin bir tanıtıcı bir [DEVNAMES](../../mfc/reference/devnames-structure.md) sürücü, cihaz ve belirli bir yazıcı çıkış bağlantı noktası adlarını tanımlayan yapısı.  
  
 `hDevMode`  
 İçin bir tanıtıcı bir [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) aygıt başlatma ve yazıcı ortamı hakkında bilgi belirten yapısı.  
  
 *bFreeOld*  
 Daha önce seçilen yazıcı boşaltır.  
  
### <a name="remarks"></a>Açıklamalar  
 Her iki `hDevMode` ve `hDevNames` olan **NULL**, `SelectPrinter` geçerli varsayılan yazıcı kullanır.  
  
##  <a name="sethelpmode"></a>  CWinApp::SetHelpMode  
 Uygulamanın Yardım türünü ayarlar.  
  
```  
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```  
  
### <a name="parameters"></a>Parametreler  
 `eHelpType`  
 Kullanılacak Yardım türünü belirtir. Bkz: [CWinApp::m_eHelpType](#m_ehelptype) daha fazla bilgi için.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanın Yardım türünü ayarlar.  
  
 Uygulamanızın Yardım türü HTMLHelp için ayarlanacak çağırabilirsiniz [EnableHTMLHelp](#enablehtmlhelp). Çağırmanız sonra `EnableHTMLHelp`, uygulamanız kendi Yardım uygulaması olarak HTMLHelp kullanmanız gerekir. WinHelp kullanacak şekilde değiştirmek istiyorsanız, çağırabilirsiniz `SetHelpMode` ve `eHelpType` için **afxWinHelp**.  
  
##  <a name="setregistrykey"></a>  CWinApp::SetRegistryKey  
 INİ dosyaları yerine kayıt defterinde depolanan uygulama ayarları neden olur.  
  
```  
void SetRegistryKey(LPCTSTR lpszRegistryKey);  
void SetRegistryKey(UINT nIDRegistryKey);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszRegistryKey*  
 İşaretçi anahtar adını içeren dize.  
  
 *nIDRegistryKey*  
 Kayıt defteri anahtarı adını içeren bir dize kaynak kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev ayarlar *m_pszRegistryKey*, ardından kullanılan tarafından `GetProfileInt`, `GetProfileString`, `WriteProfileInt`, ve `WriteProfileString` üye işlevlerini `CWinApp`. Bu işlev çağrıldığında, en son kullanılan (MRU) dosyaların listesini de kayıt defterinde depolanır. Kayıt defteri anahtarı genellikle bir şirket adıdır. Aşağıdaki biçimde anahtarında depolanır: HKEY_CURRENT_USER\Software\\< şirket adı\>\\< Uygulama adı\>\\< bölüm adı\>\\< değeri ad\>.  
  
##  <a name="supportsapplicationrecovery"></a>  CWinApp::SupportsApplicationRecovery  
 Yeniden başlatma Yöneticisi beklenmedik biçimde çıktı uygulamanın kurtarır olup olmadığını belirler.  
  
```  
virtual BOOL SupportsApplicationRecovery() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yeniden başlatma Yöneticisi kurtarır uygulama gösterir; `FALSE` yeniden başlatma Yöneticisi'ni desteklemez gösterir.  
  
##  <a name="supportsautosaveatinterval"></a>  CWinApp::SupportsAutosaveAtInterval  
 Yeniden başlatma Yöneticisi autosaves düzenli aralıklarla belgeleri Aç olup olmadığını belirler.  
  
```  
virtual BOOL SupportsAutosaveAtInterval() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yeniden başlatma Yöneticisi autosaves belgeleri Aç gösterir; `FALSE` yeniden başlatma Yöneticisi'ni desteklemez gösterir.  
  
##  <a name="supportsautosaveatrestart"></a>  CWinApp::SupportsAutosaveAtRestart  
 Belirler olup olmadığını yeniden başlatma Yöneticisi autosaves tüm açık belgeleri uygulama yeniden başlatıldığında.  
  
```  
virtual BOOL SupportsAutosaveAtRestart() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Uygulama yeniden başlatıldığında yeniden başlatma Yöneticisi autosaves belgeleri Aç gösterir; `FALSE` yeniden başlatma Yöneticisi'ni desteklemez gösterir.  
  
##  <a name="supportsrestartmanager"></a>  CWinApp::SupportsRestartManager  
 Uygulama yeniden başlatma Yöneticisi'ni destekleyip desteklemediğini belirler.  
  
```  
virtual BOOL SupportsRestartManager() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Uygulama yeniden başlatma Yöneticisi'ni desteklediğini gösterir; `FALSE` uygulama desteklemez gösterir.  
  
##  <a name="unregister"></a>  CWinApp::Unregister  
 Uygulama nesnesi tarafından kaydedilen tüm dosyaları kaydını siler.  
  
```  
virtual BOOL Unregister();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `Unregister` İşlevi uygulama nesnesi tarafından gerçekleştirilen kaydı geri alır ve [kaydetmek](#register) işlevi. Normalde, her iki işlevleri MFC tarafından dolaylı olarak adlandırılır ve bu nedenle, kodunuzda görünmez.  
  
 Özel kayıt silme adımları gerçekleştirmek için bu işlevi geçersiz kılar.  
  
##  <a name="unregistershellfiletypes"></a>  CWinApp::UnregisterShellFileTypes  
 Windows Dosya Yöneticisi ile uygulamanızın belge türlerinin tümü kaydını kaldırmak için bu üye işlevini çağırın.  
  
```  
void UnregisterShellFileTypes();
```  
  
##  <a name="winhelp"></a>  CWinApp::WinHelp  
 WinHelp uygulama çağırmak için bu üye işlevini çağırın.  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwData`  
 Ek veri belirtir. Kullanılan değer değerine bağlıdır `nCmd` parametresi.  
  
 `nCmd`  
 İstenen Yardım türünü belirtir. Olası değerler ve nasıl etkilediklerini listesi `dwData` parametresi bkz [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) Windows işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework de WinHelp uygulama çağırmak için bu işlevi çağırır.  
  
 Uygulamanızı sonlandırıldığında framework WinHelp uygulama otomatik olarak kapatılır.  
  
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
 `lpszSection`  
 Noktaları null ile sonlandırılmış dizeye giriş içeren bölüm belirtir. Bölüm mevcut değilse oluşturulur. Bölümün adını bağımsız durumdur; dize, herhangi bir bileşimini büyük ve küçük harfleri olabilir.  
  
 `lpszEntry`  
 Değeri yazılacak girdisi içeren null ile sonlandırılmış bir dize noktalarına. Giriş belirtilen bölümünde mevcut değilse oluşturulur.  
  
 `pData`  
 Yazılacak veri noktalarına.  
  
 `nBytes`  
 Yazılacak bayt sayısını içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 Bu örnekte `CWinApp* pApp = AfxGetApp();` şekilde gösteren CWinApp sınıfta almak için `WriteProfileBinary` ve `GetProfileBinary` bir MFC uygulamasında herhangi bir işlevden kullanılabilir.  
  
 [!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]  
  
 Örneğin başka bir örnek için bkz [CWinApp::GetProfileBinary](#getprofilebinary).  
  
##  <a name="writeprofileint"></a>  CWinApp::WriteProfileInt  
 Belirtilen değer uygulamanın kayıt defteri belirtilen bölüme yazmak için bu üye işlevini çağırın veya. INI dosyası.  
  
```  
BOOL WriteProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszSection`  
 Noktaları null ile sonlandırılmış dizeye giriş içeren bölüm belirtir. Bölüm mevcut değilse oluşturulur. Bölümün adını bağımsız durumdur; dize, herhangi bir bileşimini büyük ve küçük harfleri olabilir.  
  
 `lpszEntry`  
 Değeri yazılacak girdisi içeren null ile sonlandırılmış bir dize noktalarına. Giriş belirtilen bölümünde mevcut değilse oluşturulur.  
  
 `nValue`  
 Yazılacak değer içeriyor.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 Bu örnekte `CWinApp* pApp = AfxGetApp();` şekilde gösteren CWinApp sınıfta almak için `WriteProfileString`, `WriteProfileInt`, `GetProfileString`, ve `GetProfileInt` bir MFC uygulamasında herhangi bir işlevden kullanılabilir.  
  
 [!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Örneğin başka bir örnek için bkz [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="writeprofilestring"></a>  CWinApp::WriteProfileString  
 Belirtilen dize uygulamanın kayıt defteri belirtilen bölüme yazmak için bu üye işlevini çağırın veya. INI dosyası.  
  
```  
BOOL WriteProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszSection`  
 Noktaları null ile sonlandırılmış dizeye giriş içeren bölüm belirtir. Bölüm mevcut değilse oluşturulur. Bölümün adını bağımsız durumdur; dize, herhangi bir bileşimini büyük ve küçük harfleri olabilir.  
  
 `lpszEntry`  
 Değeri yazılacak girdisi içeren null ile sonlandırılmış bir dize noktalarına. Giriş belirtilen bölümünde mevcut değilse oluşturulur. Bu parametre ise `NULL`, belirtilen bölüm `lpszSection` silinir.  
  
 `lpszValue`  
 Yazılacak dizeye noktaları. Bu parametre ise `NULL`, tarafından belirtilen giriş `lpszEntry` parametresi silinir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Örneğin başka bir örnek için bkz [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="setappid"></a>  CWinApp::SetAppID  
 Açıkça uygulama kullanıcısı Model kimliği için uygulama ayarlar. Bu yöntem, herhangi bir kullanıcı arabirimi (en iyi uygulama Oluşturucusu yerdir) kullanıcıya sunulan önce çağrılmalıdır.  
  
```  
void SetAppID(LPCTSTR lpcszAppID);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpcszAppID`  
 Uygulama kullanıcı Model kimliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinThread sınıfı](../../mfc/reference/cwinthread-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme](../../mfc/how-to-add-restart-manager-support.md)



