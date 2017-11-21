---
title: "CDataRecoveryHandler sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveAllDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::CreateDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAllAutosavedFiles
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAutosavedFile
- AFXDATARECOVERY/CDataRecoveryHandler::GenerateAutosaveFileName
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::GetDocumentListName
- AFXDATARECOVERY/CDataRecoveryHandler::GetNormalDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRecoveredDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::GetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::Initialize
- AFXDATARECOVERY/CDataRecoveryHandler::QueryRestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::ReadOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::RemoveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::ReopenPreviousDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::RestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::SaveOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::SetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::SetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::UpdateDocumentInfo
dev_langs: C++
helpviewer_keywords:
- CDataRecoveryHandler [MFC], CDataRecoveryHandler
- CDataRecoveryHandler [MFC], AutosaveAllDocumentInfo
- CDataRecoveryHandler [MFC], AutosaveDocumentInfo
- CDataRecoveryHandler [MFC], CreateDocumentInfo
- CDataRecoveryHandler [MFC], DeleteAllAutosavedFiles
- CDataRecoveryHandler [MFC], DeleteAutosavedFile
- CDataRecoveryHandler [MFC], GenerateAutosaveFileName
- CDataRecoveryHandler [MFC], GetAutosaveInterval
- CDataRecoveryHandler [MFC], GetAutosavePath
- CDataRecoveryHandler [MFC], GetDocumentListName
- CDataRecoveryHandler [MFC], GetNormalDocumentTitle
- CDataRecoveryHandler [MFC], GetRecoveredDocumentTitle
- CDataRecoveryHandler [MFC], GetRestartIdentifier
- CDataRecoveryHandler [MFC], GetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], GetShutdownByRestartManager
- CDataRecoveryHandler [MFC], Initialize
- CDataRecoveryHandler [MFC], QueryRestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], ReadOpenDocumentList
- CDataRecoveryHandler [MFC], RemoveDocumentInfo
- CDataRecoveryHandler [MFC], ReopenPreviousDocuments
- CDataRecoveryHandler [MFC], RestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], SaveOpenDocumentList
- CDataRecoveryHandler [MFC], SetAutosaveInterval
- CDataRecoveryHandler [MFC], SetAutosavePath
- CDataRecoveryHandler [MFC], SetRestartIdentifier
- CDataRecoveryHandler [MFC], SetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], SetShutdownByRestartManager
- CDataRecoveryHandler [MFC], UpdateDocumentInfo
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bf80d43179c0b7e5de52aeb2db46ac17b7df2763
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler sınıfı
`CDataRecoveryHandler` Autosaves belgeler ve bir uygulamanın beklenmedik şekilde bulunup bulunmadığını geri yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|Oluşturan bir `CDataRecoveryHandler` nesnesi.|  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|Her dosya kayıtlı Autosaves `CDataRecoveryHandler` sınıfı.|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|Belirtilen belge Autosaves.|  
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|Bir belgeyi aç belgeler listesine ekler.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|Tüm geçerli otomatik kaydedilmiş dosyaları siler.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|Belirtilen otomatik kaydedilmiş dosyasını siler.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|Sağlanan belge dosya adı ile ilişkili bir otomatik kaydetme dosyasının adı oluşturur.|  
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|Otomatik kaydetme denemeler aralığı döndürür.|  
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|Otomatik kaydedilmiş dosyalarının yolunu döndürür.|  
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|Belge adından alır bir `CDocument` nesnesi.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|Belirtilen belge normal başlığını alır.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Oluşturur ve kurtarılan belgenin başlığını döndürür.|  
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|Uygulama için benzersiz bir yeniden başlatma tanımlayıcı alır.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|Gösterir olup olmadığını `CDataRecoveryHandler` geçerli boşta döngü üzerinde bir otomatik kaydetme gerçekleştirir.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Yeniden başlatma Yöneticisi çıkmak uygulama neden olup olmadığını gösterir.|  
|[CDataRecoveryHandler::Initialize](#initialize)|Başlatır `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|Her belge için bir iletişim kutusu kullanıcı için görüntüler `CDataRecoveryHandler` otomatik kaydedilmiş. İletişim kutusu, kullanıcı otomatik kaydedilmiş belge geri yüklemek isteyip istemediğini belirler.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|Açık belge listesi kayıt defterinden yükler.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|Sağlanan belge açık belge listesinden kaldırır.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|Daha önce açık belgeleri açar.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|Kullanıcı girişini temel alarak otomatik kaydedilmiş belgeleri geri yükler.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Geçerli açık belgelerden listesini Windows kayıt defterine kaydeder.|  
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|Milisaniye cinsinden otomatik kaydetme döngüleri arasındaki süreyi ayarlar.|  
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|Otomatik kaydedilmiş dosyalarının depolandığı dizine ayarlar.|  
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|Bu örneği için benzersiz bir yeniden başlatma tanımlayıcı ayarlar `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|Ayarlar olup olmadığını `CDataRecoveryHandler` açık belge bilgileri Windows kayıt defterine geçerli boşta döngüsü sırasında kaydeder.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|Uygulamanın önceki çıkış yeniden başlatma Yöneticisi tarafından neden olup olmadığını belirler.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|Kullanıcı kaydettiyseniz çünkü bir belgenin bilgilerini güncelleştirir.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|m_bRestoringPreviousOpenDocs|Veri kurtarma işleyicisi daha önce açık belgeleri açana olup olmadığını gösterir.|  
|m_bSaveDocumentInfoOnIdle|Veri kurtarma işleyici autosaves sonraki boşta döngü üzerinde belgeleri olup olmadığını gösterir.|  
|m_bShutdownByRestartManager|Yeniden başlatma Yöneticisi çıkmak uygulama neden olup olmayacağını gösterir.|  
|m_dwRestartManagerSupportFlags|Uygulama için yeniden başlatma Yöneticisi desteği ne belirten bayrakları sağlar.|  
|m_lstAutosavesToDelete|Özgün belgelerin kapatıldığında silinmedi otomatik olarak kaydedilmiş dosyaların listesi. Uygulama, dosyaları silme yeniden başlatma Yöneticisi yeniden deneme çıktığında.|  
|m_mapDocNameToAutosaveName|Otomatik kaydedilmiş dosya adları için belge adlarının haritasını.|  
|m_mapDocNameToDocumentPtr|Belge adlarının haritasını [CDocument](../../mfc/reference/cdocument-class.md) işaretçileri.|  
|m_mapDocNameToRestoreBool|Otomatik kaydedilmiş belge geri kılmayacağını gösteren bir Boole parametresi için belge adlarının haritasını.|  
|m_mapDocumentPtrToDocName|Haritasını `CDocument` belge adlarının işaretçiler.|  
|m_mapDocumentPtrToDocTitle|Haritasını `CDocument` Belge başlıkları işaretçiler. Bu başlık dosyaları kaydetmek için kullanılır.|  
|m_nAutosaveInterval|Autosaves arasındaki milisaniye olarak süre.|  
|m_nTimerID|Otomatik kaydetme zamanlayıcı tanımlayıcısı.|  
|m_strAutosavePath|Otomatik kaydedilmiş belgeleri depolandığı konum.|  
|m_strRestartIdentifier|Yeniden başlatma Yöneticisi için bir GUID dize gösterimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma Yöneticisi'ni kullanan `CDataRecoveryHandler` tutmak için sınıf izleme açık olan tüm belgelerin ve otomatik kaydetme için bunları gerektiği gibi. Otomatik kaydetme etkinleştirmek için [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) yöntemi. Bu yöntem yönlendirir `CDataRecoveryHandler` bir otomatik kaydetme üzerinde sonraki boşta döngü gerçekleştirmek için. Yeniden başlatma Yöneticisi çağrıları `SetSaveDocumentInfoOnIdle` zaman `CDataRecoveryHandler` bir otomatik kaydetme gerçekleştirmeniz gerekir.  
  
 Tüm yöntemlerinden birini `CDataRecoveryHandler` sınıfı sanal. Kendi özel veri kurtarma işleyici oluşturmak için bu sınıftaki yöntemleri geçersiz kılın. Kendi veri kurtarma işleyici oluşturmak veya yeniden başlatma Yöneticisi sürece, bir CDataRecoveryHandler örneği değil. [CWinApp sınıfı](../../mfc/reference/cwinapp-class.md) oluşturur bir `CDataRecoveryHandler` gerekli olduğundan nesne.  
  
 Kullanabilmeniz için önce bir `CDataRecoveryHandler` nesne çağırmanız gerekir [CDataRecoveryHandler::Initialize](#initialize).  
  
 Çünkü `CDataRecoveryHandler` sınıfı yeniden başlatma Yöneticisi yakından bağlı `CDataRecoveryHandler` genel parametresine bağlı `m_dwRestartManagerSupportFlags`. Bu parametre, yeniden başlatma yöneticisi olan izinleri ve uygulamanız ile nasıl etkileşim kurduğu belirler. Var olan bir uygulamayı yeniden başlatma Yöneticisi'ni içerecek şekilde atamanız gerekir `m_dwRestartManagerSupportFlags` ana uygulamanızın Oluşturucusu uygun değeri. Yeniden başlatma Yöneticisi'ni kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: yeniden başlatma Yöneticisi desteği ekleme](../../mfc/how-to-add-restart-manager-support.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdatarecovery.h  
  
##  <a name="autosavealldocumentinfo"></a>CDataRecoveryHandler::AutosaveAllDocumentInfo  
 Her dosya kayıtlı Autosaves `CDataRecoveryHandler` sınıfı.  
  
```  
virtual BOOL AutosaveAllDocumentInfo();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `CDataRecoveryHandler` kaydedilen tüm belgeleri için; `FALSE` herhangi bir belge kaydedilmedi durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem `TRUE` kaydedilmelidir hiçbir belgeler varsa. Ayrıca döndürür `TRUE` alma, herhangi bir belgeniz kaydetmeden `CWinApp` veya `CDocManager` uygulama bir hata üretir.  
  
 Ya da bu yöntemi kullanmak için `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` veya `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL` ayarlanması gerekir `m_dwRestartManagerSupportFlags`. Bkz: [m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags) daha fazla bilgi için.  
  
##  <a name="autosavedocumentinfo"></a>CDataRecoveryHandler::AutosaveDocumentInfo  
 Belirtilen belge Autosaves.  
  
```  
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,  
    BOOL bResetModifiedFlag = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pDocument`|Bir işaretçi `CDocument` kaydetmek için.|  
|[in]`bResetModifiedFlag`|`TRUE`belirten `CDataRecoveryHandler` göz önünde bulundurur `pDocument` değiştirilecek; `FALSE` framework dikkate gösterir `pDocument` değiştirilmemiş olmalıdır. Bu bayrak etkisi hakkında daha fazla bilgi için Açıklamalar bölümüne bakın.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`uygun bayrakları ayarlarsanız ve `pDocument` geçerli bir `CDocument` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Her `CDocument` nesne, son kaydetme itibaren değişip değişmediğini belirten bir bayrak içeriyor. Kullanım [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) Bu bayrak durumunu belirlemek için. Varsa bir `CDocument` son kaydetme bu yana değişmemiştir `AutosaveDocumentInfo` bu belge için otomatik olarak kaydedilmiş dosyaları siler. Bir belgeyi son değiştiyse, kapatma kapatmadan önce belgeyi kaydetmek için kullanıcıya sorar.  
  
> [!NOTE]
>  Kullanarak `bResetModifiedFlag` belgenin durumunu için değiştirilmemiş değiştirmek için kullanıcıya kaydedilmemiş veri kaybına neden olabilir. Framework değiştirilmemiş bir belge olarak değerlendirir, kapatma kaydetmek için kullanıcı sormaz.  
  
 Bu yöntem ile aykırı [ASSERT](diagnostic-services.md#assert) makrosu varsa `pDocument` geçerli değil `CDocument` nesnesi.  
  
 Ya da bu yöntemi kullanmak için `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` veya `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` ayarlanması gerekir `m_dwRestartManagerSupportFlags`.   
  
##  <a name="cdatarecoveryhandler"></a>CDataRecoveryHandler::CDataRecoveryHandler  
 Oluşturan bir `CDataRecoveryHandler` nesnesi.  
  
```  
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,  
    int nAutosaveInterval);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`dwRestartManagerSupportFlags`|Yeniden başlatma Yöneticisi'nin hangi seçeneklerin desteklendiğini gösterir.|  
|[in]`nAutosaveInterval`|Autosaves arasındaki süre. Bu parametre milisaniye cinsindendir.|  
  
### <a name="remarks"></a>Açıklamalar  
 MFC çerçevesi otomatik olarak oluşturur bir `CDataRecoveryHandler` kullandığınızda, uygulamanız için nesne **yeni proje** Sihirbazı. Veri kurtarma davranışı veya yeniden başlatma Yöneticisi'ni özelleştirme sürece, değil oluşturmalısınız bir `CDataRecoveryHandler` nesnesi.  
  
  
##  <a name="createdocumentinfo"></a>CDataRecoveryHandler::CreateDocumentInfo  
 Bir belgeyi aç belgeler listesine ekler.  
  
```  
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pDocument`|Bir işaretçi bir `CDocument`. Bu yöntem bu belge bilgilerini oluşturur `CDocument`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama döndürür `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem denetler `pDocument` belge eklemeden önce belgeler listesinde zaten. Varsa `pDocument` listesinde, bu yöntem otomatik kaydedilmiş dosya ilişkili siler zaten `pDocument`.  
  
 Ya da bu yöntemi kullanmak için `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` veya `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` ayarlanması gerekir `m_dwRestartManagerSupportFlags`. 
  
##  <a name="deleteallautosavedfiles"></a>CDataRecoveryHandler::DeleteAllAutosavedFiles  
 Tüm geçerli otomatik kaydedilmiş dosyaları siler.  
  
```  
virtual BOOL DeleteAllAutosavedFiles();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama her zaman döndürür `TRUE`.  
  
##  <a name="deleteautosavedfile"></a>CDataRecoveryHandler::DeleteAutosavedFile  
 Belirtilen otomatik kaydedilmiş dosyasını siler.  
  
```  
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`strAutosavedFile`|Otomatik kaydedilmiş dosya adı içeren bir dize.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama her zaman dönüş `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem otomatik kaydedilmiş dosya silemiyorsanız, listede dosyanın adını kaydeder. Yıkıcı için `CDataRecoveryHandler` bu listesinde belirtilen her otomatik kaydedilmiş dosyayı silmek çalışır.  
  
##  <a name="generateautosavefilename"></a>CDataRecoveryHandler::GenerateAutosaveFileName  
 Sağlanan belge dosya adı ile ilişkili bir otomatik kaydetme dosyasının adı oluşturur.  
  
```  
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`strDocumentName`  
 Belge adını içeren dize. `GenerateAutosaveFileName`karşılık gelen bir otomatik kaydetme dosya adı oluşturmak için bu belge adını kullanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üretilen otomatik kaydetme dosya adı `strDocumentName`.  
  
### <a name="remarks"></a>Açıklamalar  
 Her bir belge adı otomatik kaydetme dosya adı ile bire bir eşleme sahiptir.  
  
##  <a name="getautosaveinterval"></a>CDataRecoveryHandler::GetAutosaveInterval  
 Otomatik kaydetme denemeler aralığı döndürür.  
  
```  
virtual int GetAutosaveInterval() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Otomatik kaydetme arasındaki milisaniye olarak çalışır.  
  
##  <a name="getautosavepath"></a>CDataRecoveryHandler::GetAutosavePath  
 Otomatik kaydedilmiş dosyalarının yolunu döndürür.  
  
```  
virtual CString GetAutosavePath() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Otomatik kaydedilmiş belgeleri depolandığı konum.  
  
##  <a name="getdocumentlistname"></a>CDataRecoveryHandler::GetDocumentListName  
 Belge adından alır bir `CDocument` nesnesi.  
  
```  
virtual CString GetDocumentListName(CDocument* pDocument) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pDocument`|Bir işaretçi bir `CDocument`. `GetDocumentListName`Bu belge adını alır `CDocument`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belge adından `pDocument`.  
  
### <a name="remarks"></a>Açıklamalar  
 `CDataRecoveryHandler` Belge adı anahtar olarak kullanır `m_mapDocNameToAutosaveName`, `m_mapDocNameToDocumentPtr`, ve `m_mapDocNameToRestoreBool`. Bu parametreyi etkinleştirin `CDataRecoveryHandler` izlemek için `CDocument` nesneleri, otomatik kaydetme dosya adı ve otomatik kaydetme ayarları.  
  
##  <a name="getnormaldocumenttitle"></a>CDataRecoveryHandler::GetNormalDocumentTitle  
 Belirtilen belge normal başlığını alır.  
  
```  
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pDocument`|Bir işaretçi bir `CDocument`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen belge normal başlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir belge normal başlığı genellikle belgesinin yolu olmadan dosya adıdır. Başlık budur **dosya adı** alanını **Kaydet** iletişim kutusu.  
  
##  <a name="getrecovereddocumenttitle"></a>CDataRecoveryHandler::GetRecoveredDocumentTitle  
 Oluşturur ve kurtarılan belgenin başlığını döndürür.  
  
```  
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`strDocumentTitle`  
 Belge için normal başlığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kurtarılan belge başlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, kurtarılan bir belge normal başlıkla başlığıdır **[kurtarıldı]** eklenmiş. Kurtarılan başlık kullanıcıya görüntülenen zaman `CDataRecoveryHandler` otomatik kaydedilmiş belgeleri geri yüklemek için kullanıcı sorgular.  
  
##  <a name="getrestartidentifier"></a>CDataRecoveryHandler::GetRestartIdentifier  
 Uygulama için benzersiz bir yeniden başlatma tanımlayıcı alır.  
  
```  
virtual CString GetRestartIdentifier() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Benzersiz tanımlayıcı yeniden başlatın.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma olarak her uygulama yürütme için benzersiz tanımlayıcısıdır.  
  
 `CDataRecoveryHandler` Kayıt defteri geçerli açık belgelerden hakkında bilgi depolar. Yeniden başlatma Yöneticisi'ni bir uygulama çıktıktan ve onu yeniden başlatıldığında, yeniden başlatma tanımlayıcı sağlayan `CDataRecoveryHandler`. `CDataRecoveryHandler` Önceden açık belgeler listesini almak için yeniden başlatma tanımlayıcısını kullanır. Böylece `CDataRecoveryHandler` bulmak ve otomatik olarak kaydedilmiş dosyalarını geri yüklemeye çalıştığınızda.  
  
##  <a name="getsavedocumentinfoonidle"></a>CDataRecoveryHandler::GetSaveDocumentInfoOnIdle  
 Gösterir olup olmadığını `CDataRecoveryHandler` geçerli boşta döngü üzerinde bir otomatik kaydetme gerçekleştirir.  
  
```  
virtual BOOL GetSaveDocumentInfoOnIdle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`gösterir `CDataRecoveryHandler` autosaves geçerli boşta döngüde; `FALSE` yok gösterir.  
  
##  <a name="getshutdownbyrestartmanager"></a>CDataRecoveryHandler::GetShutdownByRestartManager  
 Yeniden başlatma Yöneticisi çıkmak uygulama neden olup olmadığını gösterir.  
  
```  
virtual BOOL GetShutdownByRestartManager() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yeniden başlatma Yöneticisi çıkmak uygulamanın neden oldu gösterir; `FALSE` onu belirtmiyor gösterir.  
  
##  <a name="initialize"></a>CDataRecoveryHandler::Initialize  
 Başlatır `CDataRecoveryHandler`.  
  
```  
virtual BOOL Initialize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başlatma başarılıysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatma işlemi kayıt defterinden otomatik kaydetme dosyaları depolamak için yol yükler. Varsa `Initialize` yöntemi, bu dizin bulunamıyor veya yolu olup olmadığını `NULL`, `Initialize` başarısız olur ve döndürür `FALSE`.  
  
 Kullanım [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) uygulamanızı başlatır sonra otomatik kaydetme yolu değiştirmek için `CDataRecoveryHandler`.  
  
 `Initialize` Yöntemi de sonraki otomatik kaydetme oluştuğunda izlemek için bir süreölçer başlatır. Kullanım [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) uygulamanızı başlatır sonra otomatik kaydetme aralığını değiştirmek için `CDataRecoveryHandler`.  
  
##  <a name="queryrestoreautosaveddocuments"></a>CDataRecoveryHandler::QueryRestoreAutosavedDocuments  
 Her belge için bir iletişim kutusu kullanıcı için görüntüler `CDataRecoveryHandler` otomatik kaydedilmiş. İletişim kutusu, kullanıcı otomatik kaydedilmiş belge geri yüklemek isteyip istemediğini belirler.  
  
```  
virtual void QueryRestoreAutosavedDocuments();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı Unicode ise, bu yöntem görüntüler bir [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) kullanıcı. Aksi takdirde, çerçeve kullanır [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) kullanıcı sorgulanamıyor.  
  
 Sonra `QueryRestoreAutosavedDocuments` tüm yanıtları toplar kullanıcıdan bilgi üye değişkeninde depolar `m_mapDocNameToRestoreBool`. Bu yöntem, otomatik kaydedilmiş belgeleri geri yüklemeyin.  
  
##  <a name="readopendocumentlist"></a>CDataRecoveryHandler::ReadOpenDocumentList  
 Açık belge listesi kayıt defterinden yükler.  
  
```  
virtual BOOL ReadOpenDocumentList();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`belirten `ReadOpenDocumentList` en az bir belgenin bilgilerini kayıt defterinden; yüklendi `FALSE` hiçbir belge bilgilerini yüklenen gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev açık belge bilgileri kayıt defterinden yükler ve üye değişkeninde depolar `m_mapDocNameToAutosaveName`.  
  
 Sonra `ReadOpenDocumentList` verileri yükler belge bilgilerini kayıt defterinden siler.  
  
##  <a name="removedocumentinfo"></a>CDataRecoveryHandler::RemoveDocumentInfo  
 Sağlanan belge açık belge listesinden kaldırır.  
  
```  
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pDocument`|Belgenin kaldırmak için bir işaretçi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `pDocument` listeden; kaldırıldı `FALSE` durumunda bir hata oluştu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir belge kapandığında çerçevesi açık belgeler listesinden kaldırmak için bu yöntemi kullanır.  
  
 Varsa `RemoveDocumentInfo` bulunamıyor `pDocument` açık belgeler listesinde hiçbir şey yapmaz ve döndürür `TRUE`.  
  
 Bu yöntemi kullanmak için `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` ayarlanması gerekir `m_dwRestartManagerSupportFlags`.   
  
##  <a name="reopenpreviousdocuments"></a>CDataRecoveryHandler::ReopenPreviousDocuments  
 Daha önce açık belgeleri açar.  
  
```  
virtual BOOL ReopenPreviousDocuments();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`en az bir belge açılmışsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem daha önce açık belgelerin en son kaydetme açar. Bir belge kaydedilmedi varsa veya otomatik olarak kaydedilmiş, `ReopenPreviousDocuments` o dosya türü için şablonunu temel alan boş bir belge açar.  
  
 Bu yöntemi kullanmak için `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` ayarlanması gerekir `m_dwRestartManagerSupportFlags`. Bu parametre ayarlanmamışsa `ReopenPreviousDocuments` hiçbir şey yapmaz ve döndürür `FALSE`.  
  
 Daha önce açık belgeler listesinde depolanan hiçbir belgeler varsa `ReopenPreviousDocuments` hiçbir şey yapmaz ve döndürür `FALSE`.  
  
##  <a name="restoreautosaveddocuments"></a>CDataRecoveryHandler::RestoreAutosavedDocuments  
 Kullanıcı girişini temel alarak otomatik kaydedilmiş belgeleri geri yükler.  
  
```  
virtual BOOL RestoreAutosavedDocuments();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem, belgelerin başarıyla geri yükler  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) geri yüklemek, hangi kullanıcı belgeleri belirlemek için istemektedir. Bir kullanıcı bir otomatik kaydedilmiş belge geri yüklemeyin karar verirse `RestoreAutosavedDocuments` otomatik kaydetme dosyasını siler. Aksi takdirde, `RestoreAutosavedDocuments` açık belgeyi otomatik kaydedilmiş sürümüyle değiştirir.  
  
 Ya da bu yöntemi kullanmak için `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` veya `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES` ayarlanması gerekir `m_dwRestartManagerSupportFlags`.   
  
##  <a name="saveopendocumentlist"></a>CDataRecoveryHandler::SaveOpenDocumentList  
 Geçerli açık belgelerden listesini Windows kayıt defterine kaydeder.  
  
```  
virtual BOOL SaveOpenDocumentList();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`kaydetmek için hiçbir açık belgeler varsa veya başarıyla kaydedildi. `FALSE`kayıt defterine kaydetmek için belgeler vardır, ancak bir hata oluştuğundan bunlar kaydedilmedi  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma Yöneticisi çağrıları `SaveOpenDocumentList` uygulama beklenmedik şekilde çıktığında veya yükseltme için çıktığında. Uygulama yeniden başlatıldıktan sonra kullanan [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) açık belgeler listesi alınamadı.  
  
 Bu yöntem yalnızca açık belgeler listesi kaydeder. Yöntem [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) belgeleri kaydetmek için sorumludur.  
  
##  <a name="setautosaveinterval"></a>CDataRecoveryHandler::SetAutosaveInterval  
 Milisaniye cinsinden otomatik kaydetme döngüleri arasındaki süreyi ayarlar.  
  
```  
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nAutosaveInterval`  
 Yeni otomatik kaydetme aralığını milisaniye cinsinden.  
  
##  <a name="setautosavepath"></a>CDataRecoveryHandler::SetAutosavePath  
 Otomatik kaydedilmiş dosyalarının depolandığı dizine ayarlar.  
  
```  
virtual void SetAutosavePath(const CString& strAutosavePath);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`strAutosavePath`|Otomatik kaydetme dosyalarının depolandığı yolu.|  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik kaydetme dizinini değiştirme otomatik kaydedilmiş dosyaları şu anda taşımaz.  
  
##  <a name="setrestartidentifier"></a>CDataRecoveryHandler::SetRestartIdentifier  
 Bu örneği için benzersiz bir yeniden başlatma tanımlayıcı ayarlar `CDataRecoveryHandler`.  
  
```  
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`strRestartIdentifier`|Yeniden başlatma Yöneticisi için benzersiz tanımlayıcı.|  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma Yöneticisi kayıt defterinde açık belgeleri ilgili bilgileri kaydeder. Bu bilgiler benzersiz yeniden tanımlayıcısına sahip anahtar olarak depolanır. Yeniden başlatma tanımlayıcı bir uygulama her örneği için benzersiz olduğundan, bir uygulama birden çok örneğini beklenmedik şekilde çıkabilir ve yeniden başlatma Yöneticisi her birine kurtarabilirsiniz.  
  
##  <a name="setsavedocumentinfoonidle"></a>CDataRecoveryHandler::SetSaveDocumentInfoOnIdle  
 Ayarlar olup olmadığını `CDataRecoveryHandler` açık belge bilgileri Windows kayıt defterine geçerli boşta döngüsü sırasında kaydeder.  
  
```  
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`bSaveOnIdle`|`TRUE`Geçerli boşta döngü sırasında belge bilgilerini kaydetmek için; `FALSE to not perform a save`.|  
  
##  <a name="setshutdownbyrestartmanager"></a>CDataRecoveryHandler::SetShutdownByRestartManager  
 Uygulamanın önceki çıkış yeniden başlatma Yöneticisi tarafından neden olup olmadığını belirler.  
  
```  
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`bShutdownByRestartManager`|`TRUE`yeniden başlatma Yöneticisi çıkmak uygulama neden belirtmek için; `FALSE` uygulama başka bir nedenle çıktı belirtmek için.|  
  
### <a name="remarks"></a>Açıklamalar  
 Framework farklı önceki çıkış beklenmeyen olup olup yeniden başlatma Yöneticisi tarafından başlatılan göre davranır.  
  
##  <a name="updatedocumentinfo"></a>CDataRecoveryHandler::UpdateDocumentInfo  
 Kullanıcı kaydettiyseniz çünkü bir belgenin bilgilerini güncelleştirir.  
  
```  
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pDocument`|Kaydedilen belge için bir işaretçi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem otomatik kaydedilmiş belge silindi ve güncelleştirilmiş belge bilgileri `FALSE` durumunda bir hata oluştu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı bir belge kaydettiğinde, artık gerekli olmadığından uygulamayı otomatik olarak kaydedilmiş dosya kaldırır. `UpdateDocumentInfo`otomatik kaydedilmiş dosyasını çağırarak siler [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo). `UpdateDocumentInfo`bilgileri ekler `pDocument` listesine şu anda açık belgeler çünkü `RemoveDocumentInfo` bu bilgileri ancak kaydedilen siler belgedir hala açık.  
  
 Bu yöntemi kullanmak için `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` ayarlanması gerekir `m_dwRestartManagerSupportFlags`.   
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Nasıl yapılır: yeniden başlatma Yöneticisi desteği ekleme](../../mfc/how-to-add-restart-manager-support.md)

