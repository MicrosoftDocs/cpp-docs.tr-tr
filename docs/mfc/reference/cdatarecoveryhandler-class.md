---
title: CDataRecoveryHandler Sınıfı
ms.date: 03/27/2019
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
ms.openlocfilehash: bdfcbea6c345235358384691388afcdbbd2d0a42
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321940"
---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler Sınıfı

Bir `CDataRecoveryHandler` uygulama beklenmedik bir şekilde çıkarsa belgeleri otomatik olarak kaydeder ve geri yüklenir.

## <a name="syntax"></a>Sözdizimi

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|Bir `CDataRecoveryHandler` nesne inşa eder.|

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|Sınıfa kayıtlı her dosyayı `CDataRecoveryHandler` otomatik olarak kaydeder.|
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|Belirtilen belgeyi otomatik olarak kaydeder.|
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|Açık belgeler listesine bir belge ekler.|
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|Geçerli otomatik kaydedilmiş tüm dosyaları siler.|
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|Belirtilen otomatik kaydedilmiş dosyayı siler.|
|[CDataRecoveryHandler::Otomatik kaydetmeDosyaName oluşturma](#generateautosavefilename)|Sağlanan belge dosya adı ile ilişkili bir otomatik kaydetme dosyasının adını oluşturur.|
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|Otomatik kaydetme denemeleri arasındaki aralığı döndürür.|
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|Otomatik kaydedilen dosyaların yolunu döndürür.|
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|Belge adını bir `CDocument` nesneden alır.|
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|Belirtilen belgenin normal başlığını alır.|
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Kurtarılan belgenin başlığını oluşturur ve döndürür.|
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|Uygulama için benzersiz yeniden başlatma tanımlayıcısını alır.|
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|Geçerli boşta döngü üzerinde otomatik kaydetme `CDataRecoveryHandler` yapıp gerçekleştirmediğini gösterir.|
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Yeniden başlatma yöneticisinin uygulamanın çıkışına neden olup olmadığını gösterir.|
|[CDataRecoveryHandler::Initialize](#initialize)|Initializes `CDataRecoveryHandler`.|
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|`CDataRecoveryHandler` Otomatik olarak kaydedilen her belge için kullanıcıya bir iletişim kutusu görüntüler. İletişim kutusu, kullanıcının otomatik kaydedilen belgeyi geri yüklemek isteyip istemediğini belirler.|
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|Açık belge listesini kayıt defterinden yükler.|
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|Sağlanan belgeyi açık belge listesinden kaldırır.|
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|Daha önce açık olan belgeleri açar.|
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|Kullanıcı girişine dayalı otomatik kaydedilen belgeleri geri yükler.|
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Geçerli açık belgelerin listesini Windows kayıt defterine kaydeder.|
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|Otomatik kaydetme döngüleri arasındaki süreyi milisaniye cinsinden ayarlar.|
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|Otomatik kaydedilen dosyaların depolandığı dizini ayarlar.|
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|Bu örnek için benzersiz yeniden başlatma tanımlayıcısını `CDataRecoveryHandler`ayarlar.|
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|Geçerli boşta döngü sırasında açık belge bilgilerini Windows kayıt defterine `CDataRecoveryHandler` kaydedip kaydetmediğini ayarlar.|
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|Uygulamanın önceki çıkışının yeniden başlatma yöneticisitarafından neden olup olmadığını ayarlar.|
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|Kullanıcı kaydettiği için belgenin bilgilerini güncelleştirir.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|m_bRestoringPreviousOpenDocs|Veri kurtarma işleyicisinin daha önce açık belgeleri yeniden açıp açmadığını gösterir.|
|m_bSaveDocumentInfoOnIdle|Veri kurtarma işleyicisinin belgeleri bir sonraki boşalma döngüsünde otomatik olarak kaydedip kaydetmediğini gösterir.|
|m_bShutdownByRestartManager|Yeniden başlatma yöneticisinin uygulamanın çıkmasına neden olup olmadığını gösterir.|
|m_dwRestartManagerSupportFlags|Yeniden başlatma yöneticisinin uygulama için hangi desteği sağladığını gösteren bayraklar.|
|m_lstAutosavesToDelete|Özgün belgeler kapatıldığında silinmeyen otomatik olarak kaydedilen dosyaların listesi. Uygulama çıktığında, yeniden başlat yöneticisi dosyaları silmeye çalışır.|
|m_mapDocNameToAutosaveName|Otomatik kaydedilmiş dosya adlarına belge adlarının haritası.|
|m_mapDocNameToDocumentPtr|[CDocument](../../mfc/reference/cdocument-class.md) işaretçileri için belge adlarının bir haritası.|
|m_mapDocNameToRestoreBool|Belge adlarının, otomatik olarak kaydedilen belgeyi geri yükleyip geri yüklemeyeceğini belirten boolean parametresinin haritası.|
|m_mapDocumentPtrToDocName|Belge adlarının `CDocument` işaretçilerin haritası.|
|m_mapDocumentPtrToDocTitle|Belge başlıklarıiçin `CDocument` işaretçilerin haritası. Bu başlıklar dosyaları kaydetmek için kullanılır.|
|m_nAutosaveInterval|Otomatik kaydetmeler arasında milisaniye cinsinden zaman.|
|m_nTimerID|Otomatik kaydetme zamanlayıcısı için tanımlayıcı.|
|m_strAutosavePath|Otomatik kaydedilen belgelerin depolandığı konum.|
|m_strRestartIdentifier|Yeniden başlatma yöneticisi için GUID dize gösterimi.|

## <a name="remarks"></a>Açıklamalar

Yeniden başlatma `CDataRecoveryHandler` yöneticisi, tüm açık belgeleri izlemek ve gerektiğinde otomatik olarak kaydetmek için sınıfı kullanır. Otomatik kaydetmeyi etkinleştirmek için [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) yöntemini kullanın. Bu yöntem, `CDataRecoveryHandler` bir sonraki boşalma döngüsünde otomatik kaydetme gerçekleştirmeyi yönlendirir. Yeniden başlatma yöneticisi, `CDataRecoveryHandler` otomatik kaydetme yapılması gerektiğinde çağırır. `SetSaveDocumentInfoOnIdle`

`CDataRecoveryHandler` Sınıfın tüm yöntemleri sanaldır. Kendi özel veri kurtarma işleyicinizi oluşturmak için bu sınıftaki yöntemleri geçersiz kılın. Kendi veri kurtarma işleyicinizi oluşturmadığınız veya yöneticiyi yeniden başlatmadığınız sürece, bir CDataRecoveryHandler'ı anında oluşturmayın. [CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md) gerektiği `CDataRecoveryHandler` gibi bir nesne oluşturur.

Bir `CDataRecoveryHandler` nesneyi kullanamadan önce [CDataRecoveryHandler'ı aramanız gerekir::Initialize](#initialize).

`CDataRecoveryHandler` Sınıf yeniden başlatma yöneticisine yakından bağlı `CDataRecoveryHandler` olduğundan, genel parametreye `m_dwRestartManagerSupportFlags`bağlıdır. Bu parametre, yeniden başlatma yöneticisinin hangi izinlere sahip olduğunu ve uygulamanızla nasıl etkileşimde olduğunu belirler. Yeniden başlatma yöneticisini varolan bir uygulamaya dahil etmek `m_dwRestartManagerSupportFlags` için, ana uygulamanızın oluşturucusuna uygun değeri atamanız gerekir. Yeniden başlatma yöneticisinin nasıl kullanılacağı hakkında daha fazla bilgi için [bkz.](../../mfc/how-to-add-restart-manager-support.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdatarecovery.h

## <a name="cdatarecoveryhandlerautosavealldocumentinfo"></a><a name="autosavealldocumentinfo"></a>CDataRecoveryHandler::AutosaveAllDocumentInfo

Sınıfa kayıtlı her dosyayı `CDataRecoveryHandler` otomatik olarak kaydeder.

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>Dönüş Değeri

DOĞRU tüm `CDataRecoveryHandler` belgeleri kaydedilmiş ise; Herhangi bir belge kaydedilmediyse YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Kaydedilmesi gereken belge yoksa, bu yöntem TRUE döndürür. Uygulama nın alınması `CWinApp` veya `CDocManager` uygulama için bir hata oluşturuyorsa, herhangi bir belge kaydetmeden TRUE'yu döndürür.

Bu yöntemi kullanmak için, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART veya `m_dwRestartManagerSupportFlags`AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL olarak ayarlanmalıdır. Daha fazla bilgi için [bkz: Yeniden Başlat Yöneticisi Desteği ekle.](../../mfc/how-to-add-restart-manager-support.md)

## <a name="cdatarecoveryhandlerautosavedocumentinfo"></a><a name="autosavedocumentinfo"></a>CDataRecoveryHandler::AutosaveDocumentInfo

Belirtilen belgeyi otomatik olarak kaydeder.

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pBelge*|[içinde] Kaydetmek için `CDocument` bir işaretçi.|
|*bResetModifibayrak*|[içinde] TRUE, `CDataRecoveryHandler` *pDocument'ın* değiştirilmesi gerektiğini gösterir; FALSE, çerçevenin *pDocument'ı* değiştirilmemiş olarak gördüğünü gösterir. Bu bayrağın etkisi hakkında daha fazla bilgi için Açıklamalar bölümüne bakın.|

### <a name="return-value"></a>Dönüş Değeri

Uygun bayraklar ayarlanmışsa ve *pDocument* geçerli `CDocument` bir nesneyse DOĞRU.

### <a name="remarks"></a>Açıklamalar

Her `CDocument` nesnenin son kaydedilmeden sonra değişip değişmediğini gösteren bir bayrağı vardır. Bu bayrağın durumunu belirlemek için [CDocument::Ismodified](../../mfc/reference/cdocument-class.md#ismodified) kullanın. Son `CDocument` kaydedilmeden bu `AutosaveDocumentInfo` yana a değişmediyse, bu belge için otomatik olarak kaydedilen dosyaları siler. Bir belge son kaydedilmeden sonra değiştiyse, belgenin kapatılması, kullanıcıdan kapatmadan önce belgeyi kaydetmesini ister.

> [!NOTE]
> Belgenin durumunu değiştirilmemiş olarak değiştirmek için *bResetModifiedFlag'in* kullanılması, kullanıcının kaydedilmemiş verileri kaybetmesine neden olabilir. Çerçeve, bir belgenin değiştirilmediğini düşünüyorsa, kapatma, kullanıcıdan kaydolmasını gerektirmez.

*PDocument* geçerli `CDocument` bir nesne değilse, bu yöntem [ASSERT](diagnostic-services.md#assert) makrosu yla bir özel durum oluşturur.

Bu yöntemi kullanmak için, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART veya AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL *m_dwRestartManagerSupportFlags*olarak ayarlanmalıdır.

## <a name="cdatarecoveryhandlercdatarecoveryhandler"></a><a name="cdatarecoveryhandler"></a>CDataRecoveryHandler::CDataRecoveryHandler

Bir `CDataRecoveryHandler` nesne inşa eder.

```
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,
    int nAutosaveInterval);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*dwRestartManagerSupportFlags*|[içinde] Yeniden başlatma yöneticisinin hangi seçeneklerinin desteklendiğibelirtilir.|
|*nAutosaveInterval*|[içinde] Otomatik kaydetmeler arasındaki zaman. Bu parametre milisaniye cinsindendir.|

### <a name="remarks"></a>Açıklamalar

**Yeni Proje** sihirbazını kullandığınızda `CDataRecoveryHandler` MFC çerçevesi uygulamanız için otomatik olarak bir nesne oluşturur. Veri kurtarma davranışını veya yeniden başlatma yöneticisini özelleştirmediğiniz sürece, bir `CDataRecoveryHandler` nesne oluşturmamalısınız.

## <a name="cdatarecoveryhandlercreatedocumentinfo"></a><a name="createdocumentinfo"></a>CDataRecoveryHandler::CreateDocumentInfo

Açık belgeler listesine bir belge ekler.

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pBelge*|[içinde] Bir işaretçi `CDocument`. Bu yöntem, bunun `CDocument`için belge bilgilerini oluşturur.|

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belgeyi ekleyenden önce *pDocument'ın* zaten belge listesinde olup olmadığını denetler. *pDocument* zaten listedeyse, bu yöntem *pDocument*ile ilişkili otomatik kaydedilmiş dosyayı siler.

Bu yöntemi kullanmak için, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART veya AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL *m_dwRestartManagerSupportFlags*olarak ayarlanmalıdır.

## <a name="cdatarecoveryhandlerdeleteallautosavedfiles"></a><a name="deleteallautosavedfiles"></a>CDataRecoveryHandler::DeleteAllAutosavedFiles

Geçerli otomatik kaydedilmiş tüm dosyaları siler.

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama her zaman TRUE döndürür.

## <a name="cdatarecoveryhandlerdeleteautosavedfile"></a><a name="deleteautosavedfile"></a>CDataRecoveryHandler::DeleteAutosavedFile

Belirtilen otomatik kaydedilmiş dosyayı siler.

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*strAutosavedDosya*|[içinde] Otomatik kaydedilmiş dosya adını içeren bir dize.|

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama her zaman TRUE döndürün.

### <a name="remarks"></a>Açıklamalar

Bu yöntem otomatik olarak kaydedilen dosyayı silemezse, dosyanın adını bir listeye kaydeder. Bu listede belirtilen otomatik `CDataRecoveryHandler` kaydedilmiş her dosyayı silmeye çalışan yıkıcı.

## <a name="cdatarecoveryhandlergenerateautosavefilename"></a><a name="generateautosavefilename"></a>CDataRecoveryHandler::Otomatik kaydetmeDosyaName oluşturma

Sağlanan belge dosya adı ile ilişkili bir otomatik kaydetme dosyasının adını oluşturur.

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>Parametreler

*strDocumentName*<br/>
[içinde] Belge adını içeren bir dize. `GenerateAutosaveFileName`karşılık gelen otomatik kaydetme dosya adını oluşturmak için bu belge adını kullanır.

### <a name="return-value"></a>Dönüş Değeri

*strDocumentName'den*oluşturulan otomatik kaydetme dosya adı.

### <a name="remarks"></a>Açıklamalar

Her belge adının otomatik kaydetme dosya adı içeren bire bir eşlemevardır.

## <a name="cdatarecoveryhandlergetautosaveinterval"></a><a name="getautosaveinterval"></a>CDataRecoveryHandler::GetAutosaveInterval

Otomatik kaydetme denemeleri arasındaki aralığı döndürür.

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik kaydetme denemeleri arasındaki milisaniye sayısı.

## <a name="cdatarecoveryhandlergetautosavepath"></a><a name="getautosavepath"></a>CDataRecoveryHandler::GetAutosavePath

Otomatik kaydedilen dosyaların yolunu döndürür.

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik kaydedilen belgelerin depolandığı konum.

## <a name="cdatarecoveryhandlergetdocumentlistname"></a><a name="getdocumentlistname"></a>CDataRecoveryHandler::GetDocumentListName

Belge adını bir `CDocument` nesneden alır.

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pBelge*|[içinde] Bir işaretçi `CDocument`. `GetDocumentListName`belge adını buradan `CDocument`alır.|

### <a name="return-value"></a>Dönüş Değeri

*pDocument*belge adı .

### <a name="remarks"></a>Açıklamalar

Belge `CDataRecoveryHandler` *adı, m_mapDocNameToAutosaveName,* *m_mapDocNameToDocumentPtr*ve *m_mapDocNameToRestoreBool*anahtar olarak kullanır. Bu parametre `CDataRecoveryHandler` nesneleri, `CDocument` otomatik kaydetme dosya adını ve otomatik kaydetme ayarlarını izlemesini sağlar.

## <a name="cdatarecoveryhandlergetnormaldocumenttitle"></a><a name="getnormaldocumenttitle"></a>CDataRecoveryHandler::GetNormalDocumentTitle

Belirtilen belgenin normal başlığını alır.

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pBelge*|[içinde] Bir işaretçi `CDocument`.|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen belgenin normal başlığı.

### <a name="remarks"></a>Açıklamalar

Belgenin normal başlığı genellikle yol olmadan belgenin dosya adıdır. Bu, **Farklı Kaydet** iletişim kutusunun **Dosya adı** alanındaki başlıktır.

## <a name="cdatarecoveryhandlergetrecovereddocumenttitle"></a><a name="getrecovereddocumenttitle"></a>CDataRecoveryHandler::GetRecoveredDocumentTitle

Kurtarılan belgenin başlığını oluşturur ve döndürür.

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>Parametreler

*strDocumentTitle*<br/>
[içinde] Belgenin normal başlığı.

### <a name="return-value"></a>Dönüş Değeri

Kurtarılan belge başlığı.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir belgenin kurtarılan başlığı, belgeye eklenen **[kurtarıldı]** normal başlıktır. Otomatik olarak kaydedilen belgeleri geri yüklemek `CDataRecoveryHandler` için kullanıcı sorguladığında kurtarılan başlık kullanıcıya görüntülenir.

## <a name="cdatarecoveryhandlergetrestartidentifier"></a><a name="getrestartidentifier"></a>CDataRecoveryHandler::GetRestartIdentifier

Uygulama için benzersiz yeniden başlatma tanımlayıcısını alır.

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>Dönüş Değeri

Benzersiz yeniden başlatma tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma tanımlayıcısı, uygulamanın her yürütülmesi için benzersizdir.

Şu `CDataRecoveryHandler` anda açık olan belgelerle ilgili bilgileri kayıt defterinde saklar. Yeniden başlatma yöneticisi bir uygulamadan çıkıp yeniden başlattığında, yeniden başlat tanımlayıcısını `CDataRecoveryHandler`. Daha `CDataRecoveryHandler` önce açılmış belgelerin listesini almak için yeniden başlat tanımlayıcısı kullanır. Bu, `CDataRecoveryHandler` otomatik olarak kaydedilen dosyaları bulmayı ve geri yüklemeyi denemenizi sağlar.

## <a name="cdatarecoveryhandlergetsavedocumentinfoonidle"></a><a name="getsavedocumentinfoonidle"></a>CDataRecoveryHandler::GetSaveDocumentInfoOnIdle

Geçerli boşta döngü üzerinde otomatik kaydetme `CDataRecoveryHandler` yapıp gerçekleştirmediğini gösterir.

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, `CDataRecoveryHandler` geçerli boşalma döngüsündeki otomatik kaydetmeleri gösterir; FALSE olmadığını gösterir.

## <a name="cdatarecoveryhandlergetshutdownbyrestartmanager"></a><a name="getshutdownbyrestartmanager"></a>CDataRecoveryHandler::GetShutdownByRestartManager

Yeniden başlatma yöneticisinin uygulamanın çıkışına neden olup olmadığını gösterir.

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma yöneticisinin uygulamanın çıkmasına neden olduğunu gösterir; YANLIŞ olmadığını gösterir.

## <a name="cdatarecoveryhandlerinitialize"></a><a name="initialize"></a>CDataRecoveryHandler::Initialize

Initializes `CDataRecoveryHandler`.

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Başlatma işlemi, otomatik kaydetme dosyalarını kayıt defterinden depolama yolunu yükler. `Initialize` Yöntem bu dizini bulamıyorsa veya yol `Initialize` NULL ise `FALSE`başarısız olur ve döndürür.

[CDataRecoveryHandler kullanın::SetAutosavePath](#setautosavepath) uygulamanız baş harflerini aldıktan sonra `CDataRecoveryHandler`otomatik kaydetme yolunu değiştirmek için .

Yöntem, `Initialize` bir sonraki otomatik kaydetme gerçekleştiğinde izlemek için bir zamanlayıcı da başlatır. [CDataRecoveryHandler kullanın::SetAutosaveInterval](#setautosaveinterval) uygulamanız baş harfe geldikten `CDataRecoveryHandler`sonra otomatik kaydetme aralığını değiştirmek için .

## <a name="cdatarecoveryhandlerqueryrestoreautosaveddocuments"></a><a name="queryrestoreautosaveddocuments"></a>CDataRecoveryHandler::QueryRestoreAutosavedDocuments

`CDataRecoveryHandler` Otomatik olarak kaydedilen her belge için kullanıcıya bir iletişim kutusu görüntüler. İletişim kutusu, kullanıcının otomatik kaydedilen belgeyi geri yüklemek isteyip istemediğini belirler.

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>Açıklamalar

Uygulamanız Unicode ise, bu yöntem kullanıcıya bir [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) görüntüler. Aksi takdirde, çerçeve kullanıcıyı sorgulamak için [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) kullanır.

Kullanıcıdan gelen tüm yanıtları topladıktan sonra, `QueryRestoreAutosavedDocuments` m_mapDocNameToRestoreBool üye değişkeninde bilgileri depolar. *m_mapDocNameToRestoreBool* Bu yöntem otomatik olarak kaydedilen belgeleri geri yüklemez.

## <a name="cdatarecoveryhandlerreadopendocumentlist"></a><a name="readopendocumentlist"></a>CDataRecoveryHandler::ReadOpenDocumentList

Açık belge listesini kayıt defterinden yükler.

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, `ReadOpenDocumentList` kayıt defterinden en az bir belgeiçin bilgi yüklendiğini gösterir; FALSE, belge bilgisinin yüklenmemediğini gösterir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, açık belge bilgilerini kayıt defterinden yükler ve üye değişken *m_mapDocNameToAutosaveName*depolar.

Tüm `ReadOpenDocumentList` verileri yüklendikten sonra, kayıt defterinden belge bilgilerini siler.

## <a name="cdatarecoveryhandlerremovedocumentinfo"></a><a name="removedocumentinfo"></a>CDataRecoveryHandler::RemoveDocumentInfo

Sağlanan belgeyi açık belge listesinden kaldırır.

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pBelge*|[içinde] Kaldırılacak belgenin işaretçisi.|

### <a name="return-value"></a>Dönüş Değeri

*pDocument* listeden kaldırıldıysa DOĞRU; Bir hata oluştuysa FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir belgeyi kapattığında, çerçeve belgeyi açık belgeler listesinden kaldırmak için bu yöntemi kullanır.

Açık `RemoveDocumentInfo` belgeler listesinde *pDocument* bulamazsa, hiçbir şey yapmaz ve TRUE döndürür.

Bu yöntemi kullanmak için AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES *m_dwRestartManagerSupportFlags*olarak ayarlanmalıdır.

## <a name="cdatarecoveryhandlerreopenpreviousdocuments"></a><a name="reopenpreviousdocuments"></a>CDataRecoveryHandler::ReopenPreviousDocuments

Daha önce açık olan belgeleri açar.

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>Dönüş Değeri

En az bir belge açılmışsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, daha önce açık olan belgelerin en son kaydini açar. Belge kaydedilmediyse veya otomatik `ReopenPreviousDocuments` olarak kaydedilmediyse, bu dosya türü için şablonu temel alan boş bir belge açılır.

Bu yöntemi kullanmak için AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES *m_dwRestartManagerSupportFlags*olarak ayarlanmalıdır. Bu parametre ayarlanmazsa, `ReopenPreviousDocuments` hiçbir şey yapmaz ve FALSE döndürür.

Daha önce açılmış belgeler listesinde depolanan hiçbir belge `ReopenPreviousDocuments` yoksa, hiçbir şey yapmaz ve FALSE döndürür.

## <a name="cdatarecoveryhandlerrestoreautosaveddocuments"></a><a name="restoreautosaveddocuments"></a>CDataRecoveryHandler::RestoreAutosavedDocuments

Kullanıcı girişine dayalı otomatik kaydedilen belgeleri geri yükler.

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem belgeleri başarıyla geri yüklerse DOĞRU.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcının geri yüklemek istediği belgeleri belirlemek için [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) çağırır. Bir kullanıcı otomatik kaydedilmiş bir belgeyi `RestoreAutosavedDocuments` geri yüklememeye karar verirse, otomatik kaydetme dosyasını siler. Aksi `RestoreAutosavedDocuments` takdirde, açık belgeyi otomatik kaydedilmiş sürümle değiştirir.

Bu yöntemi kullanmak için AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES veya AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES `m_dwRestartManagerSupportFlags`olarak ayarlanmalıdır.

## <a name="cdatarecoveryhandlersaveopendocumentlist"></a><a name="saveopendocumentlist"></a>CDataRecoveryHandler::SaveOpenDocumentList

Geçerli açık belgelerin listesini Windows kayıt defterine kaydeder.

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>Dönüş Değeri

Kaydedilen açık belge yoksa veya başarıyla kaydedildiyse DOĞRU. Kayıt defterine kaydedilmesi gereken belgeler varsa, ancak bir hata oluştuğu için kaydedilmediler.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma yöneticisi, uygulama beklenmedik bir şekilde çıktığında veya yükseltme için çıktığında çağırır. `SaveOpenDocumentList` Uygulama yeniden başlatıldığında, açık belgelerin listesini almak için [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) kullanır.

Bu yöntem yalnızca açık belgelerin listesini kaydeder. Yöntem [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) belgeleri kendilerini kaydetmekten sorumludur.

## <a name="cdatarecoveryhandlersetautosaveinterval"></a><a name="setautosaveinterval"></a>CDataRecoveryHandler::SetAutosaveInterval

Otomatik kaydetme döngüleri arasındaki süreyi milisaniye cinsinden ayarlar.

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>Parametreler

*nAutosaveInterval*<br/>
[içinde] Milisaniye cinsinden yeni otomatik kaydetme aralığı.

## <a name="cdatarecoveryhandlersetautosavepath"></a><a name="setautosavepath"></a>CDataRecoveryHandler::SetAutosavePath

Otomatik kaydedilen dosyaların depolandığı dizini ayarlar.

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*strAutosavePath*|[içinde] Otomatik kaydetme dosyalarının depolandığı yol.|

### <a name="remarks"></a>Açıklamalar

Otomatik kaydetme dizinini değiştirmek, şu anda otomatik olarak kaydedilen dosyaları hareket ettirmiyor.

## <a name="cdatarecoveryhandlersetrestartidentifier"></a><a name="setrestartidentifier"></a>CDataRecoveryHandler::SetRestartIdentifier

Bu örnek için benzersiz yeniden başlatma tanımlayıcısını `CDataRecoveryHandler`ayarlar.

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*strRestartIdentifier*|[içinde] Yeniden başlatma yöneticisi için benzersiz tanımlayıcı.|

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma yöneticisi, kayıt defterindeki açık belgelerle ilgili bilgileri kaydeder. Bu bilgiler, anahtar olarak benzersiz yeniden başlatma tanımlayıcısı ile depolanır. Yeniden başlatma tanımlayıcısı bir uygulamanın her örneği için benzersiz olduğundan, bir uygulamanın birden çok örneği beklenmeyen bir şekilde çıkabilir ve yeniden başlatma yöneticisi bunların her birini kurtarabilir.

## <a name="cdatarecoveryhandlersetsavedocumentinfoonidle"></a><a name="setsavedocumentinfoonidle"></a>CDataRecoveryHandler::SetSaveDocumentInfoOnIdle

Geçerli boşta döngü sırasında açık belge bilgilerini Windows kayıt defterine `CDataRecoveryHandler` kaydedip kaydetmediğini ayarlar.

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*bSaveOnIdle*|[içinde] Geçerli boşta döngü sırasında belge bilgilerini kaydetmek için TRUE; Kaydet yapmamak için YANLIŞ.|

## <a name="cdatarecoveryhandlersetshutdownbyrestartmanager"></a><a name="setshutdownbyrestartmanager"></a>CDataRecoveryHandler::SetShutdownByRestartManager

Uygulamanın önceki çıkışının yeniden başlatma yöneticisitarafından neden olup olmadığını ayarlar.

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*bShutdownByRestartManager*|[içinde] Uygulamanın çıkmasına yeniden başlatma yöneticisinin neden olduğunu belirtmek için TRUE; UYGULAMANIN başka bir nedenle çıktığını belirtmek için YANLIŞ.|

### <a name="remarks"></a>Açıklamalar

Çerçeve, önceki çıkışın beklenmeyen olup olmadığına veya yeniden başlatma yöneticisi tarafından başlatılıp başlatılmadığına bağlı olarak farklı şekilde çalışır.

## <a name="cdatarecoveryhandlerupdatedocumentinfo"></a><a name="updatedocumentinfo"></a>CDataRecoveryHandler::UpdateDocumentInfo

Kullanıcı kaydettiği için belgenin bilgilerini güncelleştirir.

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pBelge*|[içinde] Kaydedilen belgeiçin bir işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem otomatik olarak kaydedilen belgeyi sildiyse ve belge bilgilerini güncellediyse DOĞRU; Bir hata oluştuysa FALSE.

### <a name="remarks"></a>Açıklamalar

Bir kullanıcı bir belge yi kaydettiğinde, uygulama artık gerekmediği için otomatik olarak kaydedilen dosyayı kaldırır. `UpdateDocumentInfo`[CDataRecoveryHandler](#removedocumentinfo)arayarak otomatik olarak kaydedilen dosyayı siler::RemoveDocumentInfo . `UpdateDocumentInfo`daha sonra *pDocument'daki* bilgileri şu anda `RemoveDocumentInfo` açık olan belgeler listesine ekler, çünkü bu bilgileri siler, ancak kaydedilen belge hala açıktır.

Bu yöntemi kullanmak için AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES *m_dwRestartManagerSupportFlags*olarak ayarlanmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme](../../mfc/how-to-add-restart-manager-support.md)
