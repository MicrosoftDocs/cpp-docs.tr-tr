---
title: CDataRecoveryHandler sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 604ccf9ba0695cf9d17790f149be1f0738266076
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701772"
---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler sınıfı
`CDataRecoveryHandler` Kapanıyorsa belgeler ve uygulama beklenmedik bir şekilde geri yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|Oluşturur bir `CDataRecoveryHandler` nesne.|  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|Her dosya kaydedildi kapanıyorsa `CDataRecoveryHandler` sınıfı.|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|Belirtilen belge kapanıyorsa.|  
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|Bir belge açık belgelerin listesine ekler.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|Tüm geçerli otomatik kaydedilmiş dosyaları siler.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|Belirtilen otomatik kaydedilmiş dosyayı siler.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|Sağlanan belge adıyla ilişkili bir otomatik kaydetme dosyası adını oluşturur.|  
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|Otomatik kaydetme denemeler aralığı döndürür.|  
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|Otomatik kaydedilmiş dosyaların yolunu döndürür.|  
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|Belge adından alır bir `CDocument` nesne.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|Belirtilen belge normal başlığını alır.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Oluşturur ve kurtarılan belgenin başlığını döndürür.|  
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|Uygulama için benzersiz bir yeniden başlatma tanımlayıcısını alır.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|Belirtir olup olmadığını `CDataRecoveryHandler` geçerli boşta döngü üzerinde bir otomatik kaydetme gerçekleştirir.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Yeniden başlatma Yöneticisi uygulamadan çıkmak neden olup olmadığını gösterir.|  
|[CDataRecoveryHandler::Initialize](#initialize)|Başlatır `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|Her belge için bir iletişim kutusu kullanıcı için görüntüler `CDataRecoveryHandler` otomatik kaydedilmiş. İletişim kutusu, kullanıcının otomatik kaydedilmiş belge geri yüklemek isteyip istemediğini belirler.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|Açık belge listesi kayıt defterinden yükler.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|Sağlanan belgesi açık belge listesinden kaldırır.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|Daha önce açık belgeleri açar.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|Kullanıcı girişini temel alarak otomatik kaydedilmiş belgeleri geri yükler.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Windows kayıt defterine geçerli açık belgelerin listesini kaydeder.|  
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|Milisaniye cinsinden otomatik kaydetme döngüleri arasındaki süreyi ayarlar.|  
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|Otomatik kaydedilmiş dosyalarının depolandığı dizine ayarlar.|  
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|Bu örneği için benzersiz bir yeniden başlatma tanımlayıcısını ayarlar `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|Kümeleri olup olmadığını `CDataRecoveryHandler` açık belge bilgileri Windows kayıt defterinde geçerli boşta döngü sırasında kaydeder.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|Uygulamanın önceki çıkış yeniden başlatma Yöneticisi tarafından kaynaklandı olup olmadığını belirler.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|Kullanıcı kaydedilmeden çünkü bir belgenin bilgilerini güncelleştirir.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|m_bRestoringPreviousOpenDocs|Veri kurtarma işleyicisi daha önce açık belgeleri yeniden açana olup olmadığını gösterir.|  
|m_bSaveDocumentInfoOnIdle|Veri kurtarma işleyici kapanıyorsa sonraki boşta döngü üzerinde belgeleri olup olmadığını gösterir.|  
|m_bShutdownByRestartManager|Yeniden başlatma Yöneticisi uygulamadan çıkmak neden olup olmayacağını belirtir.|  
|m_dwRestartManagerSupportFlags|Uygulama için yeniden başlatma Yöneticisi desteği ne belirten bayrakları sağlar.|  
|m_lstAutosavesToDelete|Özgün belge kapatıldığında silinmedi otomatik olarak kaydedilmiş dosyaların listesi. Uygulama, dosyaları silmeyi yeniden başlatma Yöneticisi deneme çıktığında.|  
|m_mapDocNameToAutosaveName|Otomatik kaydedilmiş dosya adları için belge adlarının bir harita.|  
|m_mapDocNameToDocumentPtr|Belge adlarının bir harita [CDocument](../../mfc/reference/cdocument-class.md) işaretçileri.|  
|m_mapDocNameToRestoreBool|Bir harita belge adlarının otomatik kaydedilmiş belge geri gösteren bir Boole parametresi.|  
|m_mapDocumentPtrToDocName|Haritasını `CDocument` belge adlarının işaretçileri.|  
|m_mapDocumentPtrToDocTitle|Haritasını `CDocument` Belge başlıkları işaretçileri. Bu başlık dosyaları kaydetmek için kullanılır.|  
|m_nAutosaveInterval|Kapanıyorsa arasındaki milisaniye cinsinden süre.|  
|m_nTimerID|Otomatik kaydetme zamanlayıcı tanımlayıcısı.|  
|m_strAutosavePath|Otomatik kaydedilmiş belgeleri depolandığı konum.|  
|m_strRestartIdentifier|Yeniden başlatma Yöneticisi için bir GUID dize gösterimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma Yöneticisi'ni kullanan `CDataRecoveryHandler` tutmak sınıfı izlemek bütün açık belgeleri ve otomatik kaydetme için bunları gerektiği şekilde. Otomatik kaydetme etkinleştirmek için [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) yöntemi. Bu yöntem yönlendirir `CDataRecoveryHandler` bir otomatik kaydetme üzerinde sonraki boşta döngü gerçekleştirmek için. Yeniden başlatma Yöneticisi çağrıları `SetSaveDocumentInfoOnIdle` olduğunda `CDataRecoveryHandler` bir otomatik kaydetme gerçekleştirmeniz gerekir.  
  
 Tüm yöntemleri `CDataRecoveryHandler` sanal sınıf. Kendi özel veri kurtarma işleyicisi oluşturmak için bu sınıftaki yöntemleri geçersiz kılın. Kendi veri kurtarma işleyicinizi oluşturma veya yeniden başlatma Yöneticisi sürece bir CDataRecoveryHandler başlatmazsınız. [CWinApp sınıfı](../../mfc/reference/cwinapp-class.md) oluşturur bir `CDataRecoveryHandler` nesne gerekli olduğu gibi.  
  
 Kullanabilmeniz için önce bir `CDataRecoveryHandler` nesne çağırmanız [CDataRecoveryHandler::Initialize](#initialize).  
  
 Çünkü `CDataRecoveryHandler` sınıfı yakından yeniden başlatma Yöneticisi'ne bağlı `CDataRecoveryHandler` genel parametresine bağlı `m_dwRestartManagerSupportFlags`. Bu parametre hangi izinlere sahip bir yeniden başlatma Yöneticisi ve uygulamanızla nasıl etkileşim kurduğunu belirler. Mevcut bir uygulamaya yeniden başlatma Yöneticisi eklemek için atamanız gerekir `m_dwRestartManagerSupportFlags` Oluşturucusu ana uygulamanızı, uygun değeri. Yeniden başlatma Yöneticisi'ni kullanma hakkında daha fazla bilgi için bkz. [nasıl yapılır: yeniden başlatma Yöneticisi desteği ekleme](../../mfc/how-to-add-restart-manager-support.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdatarecovery.h  
  
##  <a name="autosavealldocumentinfo"></a>  CDataRecoveryHandler::AutosaveAllDocumentInfo  
 Her dosya kaydedildi kapanıyorsa `CDataRecoveryHandler` sınıfı.  
  
```  
virtual BOOL AutosaveAllDocumentInfo();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE ise `CDataRecoveryHandler` tüm belgeler için; kaydedildi Varsa FALSE Belge kaydedilmedi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, kaydedilmesi gereken belge varsa TRUE döndürür. Tüm belgeleri almak, kaydetmeden de TRUE döndürür `CWinApp` veya `CDocManager` uygulama bir hata üretir.  
  
 Bu yöntemi kullanmak için AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART ya da AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL ayarlanmalıdır `m_dwRestartManagerSupportFlags`. Bkz: [m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags) daha fazla bilgi için.  
  
##  <a name="autosavedocumentinfo"></a>  CDataRecoveryHandler::AutosaveDocumentInfo  
 Belirtilen belge kapanıyorsa.  
  
```  
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,  
    BOOL bResetModifiedFlag = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*pDocument*|[in] Bir işaretçi `CDocument` kaydetmek için.|  
|*bResetModifiedFlag*|[in] TRUE gösterir `CDataRecoveryHandler` göz önünde bulundurur *pDocument* değiştirilecek; FALSE gösterir framework hesaba katıldığından emin *pDocument* değiştirilmemiş olacak. Bu bayrak etkisi hakkında daha fazla bilgi için Açıklamalar bölümüne bakın.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygun bayrakları ayarlandıysa TRUE ve *pDocument* geçerli bir `CDocument` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Her `CDocument` nenesindeki son kaydetme işleminden sonra değişip değişmediğini gösteren bir bayrak. Kullanım [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) Bu bayrak durumunu belirlemek için. Varsa bir `CDocument` son kaydetmenizden değişmemiştir `AutosaveDocumentInfo` otomatik kaydedilmiş belge dosyaları siler. Son kaydetme işleminden sonra bir belge değiştiyse, kapatma kapatmadan önce belgeyi kaydetmek için kullanıcı ister.  
  
> [!NOTE]
>  Kullanarak *bResetModifiedFlag* değiştirilmemiş için belgenin durumunu değiştirmek için kullanıcı kaydedilmemiş veri kaybına neden olabilir. Framework değiştirilmemiş bir belge olarak değerlendirir, kapatma, kullanıcının kaydetmesine sormaz.  
  
 Bu yöntem ile aykırı [ASSERT](diagnostic-services.md#assert) makrosu, *pDocument* geçerli değil `CDocument` nesne.  
  
 Bu yöntemi kullanmak için AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART ya da AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL ayarlanmalıdır *m_dwRestartManagerSupportFlags*.   
  
##  <a name="cdatarecoveryhandler"></a>  CDataRecoveryHandler::CDataRecoveryHandler  
 Oluşturur bir `CDataRecoveryHandler` nesne.  
  
```  
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,  
    int nAutosaveInterval);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*dwRestartManagerSupportFlags*|[in] Yeniden başlatma Yöneticisi'nin hangi seçeneklerin desteklendiğini gösterir.|  
|*nAutosaveInterval*|[in] Kapanıyorsa arasındaki süre. Bu parametre, milisaniye cinsindendir.|  
  
### <a name="remarks"></a>Açıklamalar  
 MFC çerçevesi otomatik olarak oluşturur bir `CDataRecoveryHandler` kullandığınızda, uygulamanız için nesne **yeni proje** Sihirbazı. Veri kurtarma davranışı veya yeniden başlatma Yöneticisi'ni özelleştirme sürece değil, oluşturmalısınız bir `CDataRecoveryHandler` nesne.  
  
  
##  <a name="createdocumentinfo"></a>  CDataRecoveryHandler::CreateDocumentInfo  
 Bir belge açık belgelerin listesine ekler.  
  
```  
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*pDocument*|[in] Bir işaretçi bir `CDocument`. Bu yöntem, bu belge bilgilerini oluşturur `CDocument`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama, TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem denetler *pDocument* belge eklemeden önce belgeler listesinde zaten olduğunu. Varsa *pDocument* listesinde, bu yöntem otomatik kaydedilmiş dosyası ile ilişkili siler zaten *pDocument*.  
  
 Bu yöntemi kullanmak için AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART ya da AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL ayarlanmalıdır *m_dwRestartManagerSupportFlags*. 
  
##  <a name="deleteallautosavedfiles"></a>  CDataRecoveryHandler::DeleteAllAutosavedFiles  
 Tüm geçerli otomatik kaydedilmiş dosyaları siler.  
  
```  
virtual BOOL DeleteAllAutosavedFiles();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama her zaman TRUE değerini döndürür.  
  
##  <a name="deleteautosavedfile"></a>  CDataRecoveryHandler::DeleteAutosavedFile  
 Belirtilen otomatik kaydedilmiş dosyayı siler.  
  
```  
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*strAutosavedFile*|[in] Otomatik kaydedilmiş dosya adını içeren bir dize.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama her zaman TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem otomatik kaydedilmiş dosyası silinemiyor, dosya adını bir listede kaydeder. Yok Edicisi `CDataRecoveryHandler` bu listesinde belirtilen her otomatik kaydedilmiş dosyayı silmek çalışır.  
  
##  <a name="generateautosavefilename"></a>  CDataRecoveryHandler::GenerateAutosaveFileName  
 Sağlanan belge adıyla ilişkili bir otomatik kaydetme dosyası adını oluşturur.  
  
```  
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*strDocumentName*<br/>
[in] Belge adını içeren bir dize. `GenerateAutosaveFileName` Bu belge adı, karşılık gelen bir otomatik kaydetme dosyası adı oluşturmak için kullanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Oluşturulan otomatik kaydetme dosyası adı *strDocumentName*.  
  
### <a name="remarks"></a>Açıklamalar  
 Her bir belge adı bir otomatik kaydetme dosyası adı ile bire bir eşleme var.  
  
##  <a name="getautosaveinterval"></a>  CDataRecoveryHandler::GetAutosaveInterval  
 Otomatik kaydetme denemeler aralığı döndürür.  
  
```  
virtual int GetAutosaveInterval() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Otomatik kaydetme arasındaki milisaniye sayısını çalışır.  
  
##  <a name="getautosavepath"></a>  CDataRecoveryHandler::GetAutosavePath  
 Otomatik kaydedilmiş dosyaların yolunu döndürür.  
  
```  
virtual CString GetAutosavePath() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Otomatik kaydedilmiş belgeleri depolandığı konum.  
  
##  <a name="getdocumentlistname"></a>  CDataRecoveryHandler::GetDocumentListName  
 Belge adından alır bir `CDocument` nesne.  
  
```  
virtual CString GetDocumentListName(CDocument* pDocument) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*pDocument*|[in] Bir işaretçi bir `CDocument`. `GetDocumentListName` Bu belge adını alır `CDocument`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belge adından *pDocument*.  
  
### <a name="remarks"></a>Açıklamalar  
 `CDataRecoveryHandler` Belge adı, anahtar olarak kullanır *m_mapDocNameToAutosaveName*, *m_mapDocNameToDocumentPtr*, ve *m_mapDocNameToRestoreBool*. Bu parametre etkinleştirme `CDataRecoveryHandler` izlemek için `CDocument` nesneleri, otomatik kaydetme dosyası adı ve Otomatik Kaydet ayarları.  
  
##  <a name="getnormaldocumenttitle"></a>  CDataRecoveryHandler::GetNormalDocumentTitle  
 Belirtilen belge normal başlığını alır.  
  
```  
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*pDocument*|[in] Bir işaretçi bir `CDocument`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen belge için normal başlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Normal bir belge başlığının genellikle yol olmadan belgenin dosya adıdır. Bu başlık, **dosya adı** alanını **Kaydet** iletişim kutusu.  
  
##  <a name="getrecovereddocumenttitle"></a>  CDataRecoveryHandler::GetRecoveredDocumentTitle  
 Oluşturur ve kurtarılan belgenin başlığını döndürür.  
  
```  
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*strDocumentTitle*<br/>
[in] Belge için normal başlığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kurtarılan belgenin başlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, kurtarılan bir belge normal başlığıyla başlığıdır **[kurtarıldı]** eklenmiş. Kurtarılan başlığı kullanıcıya görüntülenen zaman `CDataRecoveryHandler` otomatik kaydedilmiş belgeleri geri yüklemek için kullanıcı sorgular.  
  
##  <a name="getrestartidentifier"></a>  CDataRecoveryHandler::GetRestartIdentifier  
 Uygulama için benzersiz bir yeniden başlatma tanımlayıcısını alır.  
  
```  
virtual CString GetRestartIdentifier() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Benzersiz tanımlayıcı yeniden başlatın.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma olarak her uygulamanın yürütülmesi için benzersiz tanımlayıcısıdır.  
  
 `CDataRecoveryHandler` Kayıt defteri şu anda açık belgeler hakkında bilgi depolar. Yeniden başlatma Yöneticisi bir uygulamadan çıkar ve yeniden başlatır, yeniden başlatma tanımlayıcısına sağlar. `CDataRecoveryHandler`. `CDataRecoveryHandler` Daha önce açık belgelerin listesini almak için yeniden başlatma tanımlayıcısını kullanır. Böylece `CDataRecoveryHandler` otomatik olarak kaydedilmiş dosyaların geri denemek için.  
  
##  <a name="getsavedocumentinfoonidle"></a>  CDataRecoveryHandler::GetSaveDocumentInfoOnIdle  
 Belirtir olup olmadığını `CDataRecoveryHandler` geçerli boşta döngü üzerinde bir otomatik kaydetme gerçekleştirir.  
  
```  
virtual BOOL GetSaveDocumentInfoOnIdle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 DOĞRU gösterir `CDataRecoveryHandler` kapanıyorsa geçerli boşta döngü;'üzerinde FALSE yok gösterir.  
  
##  <a name="getshutdownbyrestartmanager"></a>  CDataRecoveryHandler::GetShutdownByRestartManager  
 Yeniden başlatma Yöneticisi uygulamadan çıkmak neden olup olmadığını gösterir.  
  
```  
virtual BOOL GetShutdownByRestartManager() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE, yeniden başlatma Yöneticisi uygulamadan çıkmak neden gösterir; FALSE, belirtmiyor gösterir.  
  
##  <a name="initialize"></a>  CDataRecoveryHandler::Initialize  
 Başlatır `CDataRecoveryHandler`.  
  
```  
virtual BOOL Initialize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılı ise TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatma işlemi, kayıt defterinden otomatik kaydetme dosyalarını depolamak için bir yol yükler. Varsa `Initialize` yöntemi, bu dizin bulunamıyor veya yol NULL olup olmadığını `Initialize` döndürür ve başarısız `FALSE`.  
  
 Kullanım [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) uygulamanızı başlatır sonra otomatik kaydetme yolu değiştirmek için `CDataRecoveryHandler`.  
  
 `Initialize` Yöntemi ayrıca sonraki otomatik kaydetme oluştuğunda izlemek için bir zamanlayıcı başlatır. Kullanım [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) uygulamanızı başlatır sonra otomatik kaydetme aralığını değiştirmek için `CDataRecoveryHandler`.  
  
##  <a name="queryrestoreautosaveddocuments"></a>  CDataRecoveryHandler::QueryRestoreAutosavedDocuments  
 Her belge için bir iletişim kutusu kullanıcı için görüntüler `CDataRecoveryHandler` otomatik kaydedilmiş. İletişim kutusu, kullanıcının otomatik kaydedilmiş belge geri yüklemek isteyip istemediğini belirler.  
  
```  
virtual void QueryRestoreAutosavedDocuments();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanız Unicode ise, bu yöntem görüntüler bir [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) kullanıcı. Aksi takdirde, framework kullanan [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) kullanıcı sorgulanamıyor.  
  
 Sonra `QueryRestoreAutosavedDocuments` tüm yanıtları toplayan kullanıcıdan bilgi üye değişkeni depolar *m_mapDocNameToRestoreBool*. Bu yöntem otomatik kaydedilmiş belgeleri geri yüklemez.  
  
##  <a name="readopendocumentlist"></a>  CDataRecoveryHandler::ReadOpenDocumentList  
 Açık belge listesi kayıt defterinden yükler.  
  
```  
virtual BOOL ReadOpenDocumentList();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE gösterir `ReadOpenDocumentList` en az bir belgenin bilgilerini kayıt defterinden; yüklendi FALSE, belge bilgi yüklendi gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev açık belge bilgileri kayıt defterinden yükler ve üye değişkeni depolar *m_mapDocNameToAutosaveName*.  
  
 Sonra `ReadOpenDocumentList` verileri yükler belge bilgileri kayıt defterinden siler.  
  
##  <a name="removedocumentinfo"></a>  CDataRecoveryHandler::RemoveDocumentInfo  
 Sağlanan belgesi açık belge listesinden kaldırır.  
  
```  
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*pDocument*|[in] Belgenin kaldırmak için bir işaretçi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE ise *pDocument* listeden kaldırıldı Bir hata oluştuğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir belge kapatıldığında, çerçeve açık belge listesinden kaldırmak için bu yöntemi kullanır.  
  
 Varsa `RemoveDocumentInfo` bulunamıyor *pDocument* açık belge listesinde, hiçbir şey yapmaz ve TRUE döndürür.  
  
 Bu yöntemi kullanmak için AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES ayarlanmalıdır *m_dwRestartManagerSupportFlags*.   
  
##  <a name="reopenpreviousdocuments"></a>  CDataRecoveryHandler::ReopenPreviousDocuments  
 Daha önce açık belgeleri açar.  
  
```  
virtual BOOL ReopenPreviousDocuments();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En az bir belge açarsa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, daha önce açık belgelerin en son kaydetme açılır. Belge kaydedilmedi varsa veya otomatik kaydedilmiş, `ReopenPreviousDocuments` dosya türü için şablona dayalı bir boş belge açılır.  
  
 Bu yöntemi kullanmak için AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES ayarlanmalıdır *m_dwRestartManagerSupportFlags*. Bu parametre ayarlanmazsa `ReopenPreviousDocuments` hiçbir şey yapmaz ve false değerini döndürür.  
  
 Daha önce açık belge listesinde depolanan hiçbir belge varsa `ReopenPreviousDocuments` hiçbir şey yapmaz ve false değerini döndürür.  
  
##  <a name="restoreautosaveddocuments"></a>  CDataRecoveryHandler::RestoreAutosavedDocuments  
 Kullanıcı girişini temel alarak otomatik kaydedilmiş belgeleri geri yükler.  
  
```  
virtual BOOL RestoreAutosavedDocuments();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eğer bu yöntem, belgelerin başarıyla geri yükler.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin çağırdığı [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) geri yüklemek, hangi kullanıcı belgeleri belirlemek için istemektedir. Bir kullanıcı bir otomatik kaydedilmiş belge geri karar verirse `RestoreAutosavedDocuments` otomatik kaydetme dosyayı siler. Aksi takdirde, `RestoreAutosavedDocuments` açık belge otomatik olarak kaydedilmiş sürüm ile değiştirir.  
  
 Bu yöntemi kullanmak için AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES ya da AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES ayarlanmalıdır `m_dwRestartManagerSupportFlags`.   
  
##  <a name="saveopendocumentlist"></a>  CDataRecoveryHandler::SaveOpenDocumentList  
 Windows kayıt defterine geçerli açık belgelerin listesini kaydeder.  
  
```  
virtual BOOL SaveOpenDocumentList();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydetmek için hiçbir açık belgeler olduğunda veya başarılı bir şekilde kaydedilmiş ise TRUE. Kayıt defterine kaydetmek için belgeleri vardır, ancak bir hata oluştuğundan, kaydedilmedi FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma Yöneticisi çağrıları `SaveOpenDocumentList` uygulama beklenmedik bir şekilde çıktığında veya yükseltme çıktığında. Uygulama yeniden başlatıldığında, kullandığı [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) açık belgeler listesi alınamıyor.  
  
 Bu yöntem yalnızca açık belgelerin listesini kaydeder. Yöntem [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) belgeleri kaydetmek için sorumludur.  
  
##  <a name="setautosaveinterval"></a>  CDataRecoveryHandler::SetAutosaveInterval  
 Milisaniye cinsinden otomatik kaydetme döngüleri arasındaki süreyi ayarlar.  
  
```  
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```  
  
### <a name="parameters"></a>Parametreler  
*nAutosaveInterval*<br/>
[in] Yeni otomatik kaydetme aralığını milisaniye cinsinden.  
  
##  <a name="setautosavepath"></a>  CDataRecoveryHandler::SetAutosavePath  
 Otomatik kaydedilmiş dosyalarının depolandığı dizine ayarlar.  
  
```  
virtual void SetAutosavePath(const CString& strAutosavePath);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*strAutosavePath*|[in] Otomatik kaydetme dosyalarının depolandığı yolu.|  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik kaydetme dizini değiştirmek şu anda otomatik kaydedilmiş dosyaları taşımaz.  
  
##  <a name="setrestartidentifier"></a>  CDataRecoveryHandler::SetRestartIdentifier  
 Bu örneği için benzersiz bir yeniden başlatma tanımlayıcısını ayarlar `CDataRecoveryHandler`.  
  
```  
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*strRestartIdentifier*|[in] Yeniden başlatma Yöneticisi için benzersiz tanımlayıcı.|  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden başlatma Yöneticisi, kayıt defterinde açık belgeleri ilgili bilgileri kaydeder. Bu bilgileri yeniden benzersiz tanımlayıcısına sahip anahtar olarak depolanır. Yeniden başlatma tanımlayıcısı uygulamanın her örneği için benzersiz olduğundan, bir uygulamanın birden çok örneği beklenmedik bir şekilde sonlandırılabilir ve yeniden başlatma Yöneticisi her birine kurtarabilirsiniz.  
  
##  <a name="setsavedocumentinfoonidle"></a>  CDataRecoveryHandler::SetSaveDocumentInfoOnIdle  
 Kümeleri olup olmadığını `CDataRecoveryHandler` açık belge bilgileri Windows kayıt defterinde geçerli boşta döngü sırasında kaydeder.  
  
```  
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*bSaveOnIdle*|[in] Geçerli boşta döngü sırasında belge bilgileri kaydetmek için TRUE; Kaydetme işlemi yapmayacak şekilde FALSE.|  
  
##  <a name="setshutdownbyrestartmanager"></a>  CDataRecoveryHandler::SetShutdownByRestartManager  
 Uygulamanın önceki çıkış yeniden başlatma Yöneticisi tarafından kaynaklandı olup olmadığını belirler.  
  
```  
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*bShutdownByRestartManager*|[in] Yeniden başlatma Yöneticisi uygulamadan çıkmak neden belirtmek için TRUE; Uygulama başka bir nedenle çıkıldı belirtmek için FALSE.|  
  
### <a name="remarks"></a>Açıklamalar  
 Framework, önceki çıkış olup olmadığını beklenmiyordu veya olup yeniden başlatma Yöneticisi tarafından başlatılan farklı göre davranır.  
  
##  <a name="updatedocumentinfo"></a>  CDataRecoveryHandler::UpdateDocumentInfo  
 Kullanıcı kaydedilmeden çünkü bir belgenin bilgilerini güncelleştirir.  
  
```  
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*pDocument*|[in] Kaydedilen belge işaretçisi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem otomatik kaydedilmiş belge silindi ve güncelleştirilmiş belge bilgileri gerekiyorsa TRUE; Bir hata oluştuğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı bir belgeyi kaydederken, artık gerekli olmadığından uygulamayı otomatik olarak kaydedilmiş dosyanın kaldırır. `UpdateDocumentInfo` otomatik kaydedilmiş dosyasını çağırarak siler [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo). `UpdateDocumentInfo` ardından gelen bilgileri ekler *pDocument* listesine şu anda açık belgeler çünkü `RemoveDocumentInfo` bu bilgileri, ancak kaydedilen siler belge hala açık.  
  
 Bu yöntemi kullanmak için AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES ayarlanmalıdır *m_dwRestartManagerSupportFlags*.   
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme](../../mfc/how-to-add-restart-manager-support.md)

