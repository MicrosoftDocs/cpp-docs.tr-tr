---
description: 'Daha fazla bilgi edinin: CDataRecoveryHandler Class'
title: CDataRecoveryHandler sınıfı
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
ms.openlocfilehash: 72189916f4555152ccc8997600d8426e188bb65c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222144"
---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler sınıfı

`CDataRecoveryHandler`Belgeler, bir uygulamanın beklenmedik bir şekilde çıkış durumunda belgeleri kaydeder ve onları geri yükler.

## <a name="syntax"></a>Syntax

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|Bir `CDataRecoveryHandler` nesnesi oluşturur.|

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|-|-|
|[CDataRecoveryHandler:: oto Savealldocumentınfo](#autosavealldocumentinfo)|Sınıfına kayıtlı her dosyayı oto olarak kaydeder `CDataRecoveryHandler` .|
|[CDataRecoveryHandler:: oto Savedocumentınfo](#autosavedocumentinfo)|Belirtilen belgeyi oto kaydeder.|
|[CDataRecoveryHandler:: Createdocumentınfo](#createdocumentinfo)|Açık belgeler listesine bir belge ekler.|
|[CDataRecoveryHandler::D eleteAllAutosavedFiles](#deleteallautosavedfiles)|Tüm geçerli otomatik kaydedilmiş dosyaları siler.|
|[CDataRecoveryHandler::D Eleteoto Kaydedilendosyası](#deleteautosavedfile)|Belirtilen otomatik kaydedilmiş dosyayı siler.|
|[CDataRecoveryHandler:: Generateoto Savefilename](#generateautosavefilename)|Sağlanan belge dosyası adıyla ilişkili bir otomatik kaydetme dosyası için ad üretir.|
|[CDataRecoveryHandler:: Getautosaveınterval](#getautosaveinterval)|Otomatik kaydetme denemeler arasındaki aralığı döndürür.|
|[CDataRecoveryHandler:: GetAutosavePath](#getautosavepath)|Otomatik kaydedilen dosyaların yolunu döndürür.|
|[CDataRecoveryHandler:: Getdocumentıbu](#getdocumentlistname)|Bir nesneden belge adını alır `CDocument` .|
|[CDataRecoveryHandler:: GetNormalDocumentTitle](#getnormaldocumenttitle)|Belirtilen belge için normal başlığı alır.|
|[CDataRecoveryHandler:: GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Kurtarılan belgenin başlığını oluşturur ve döndürür.|
|[CDataRecoveryHandler:: Getrestartıdentifier](#getrestartidentifier)|Uygulamanın benzersiz yeniden başlatma tanımlayıcısını alır.|
|[CDataRecoveryHandler:: Getsavebelgetınonıdle](#getsavedocumentinfoonidle)|`CDataRecoveryHandler`' Nin geçerli boşta döngüsünde bir otomatik kaydetme gerçekleştirip gerçekleştirmediğini belirtir.|
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Yeniden başlatma yöneticisinin uygulamanın çıkmasına neden olup olmadığını gösterir.|
|[CDataRecoveryHandler:: Initialize](#initialize)|Öğesini başlatır `CDataRecoveryHandler` .|
|[CDataRecoveryHandler:: QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|Otomatik kaydedilen her belge için kullanıcıya bir iletişim kutusu görüntüler `CDataRecoveryHandler` . İletişim kutusu, kullanıcının otomatik kaydedilen belgeyi geri yüklemek isteyip istemediğini belirler.|
|[CDataRecoveryHandler:: ReadOpenDocumentList](#readopendocumentlist)|Kayıt defterinden açık belge listesini yükler.|
|[CDataRecoveryHandler:: RemoveDocumentInfo](#removedocumentinfo)|Sağlanan belgeyi açık belge listesinden kaldırır.|
|[CDataRecoveryHandler:: ReopenPreviousDocuments](#reopenpreviousdocuments)|Daha önce açık olan belgeleri açar.|
|[CDataRecoveryHandler:: RestoreAutosavedDocuments](#restoreautosaveddocuments)|Otomatik kaydedilmiş belgeleri Kullanıcı girişine göre geri yükler.|
|[CDataRecoveryHandler:: SaveOpenDocumentList](#saveopendocumentlist)|Açık belgelerin geçerli listesini Windows kayıt defterine kaydeder.|
|[CDataRecoveryHandler:: SetAutosaveInterval](#setautosaveinterval)|Saniye cinsinden otomatik kaydetme döngüleri arasındaki süreyi ayarlar.|
|[CDataRecoveryHandler:: SetAutosavePath](#setautosavepath)|Otomatik kaydedilen dosyaların depolandığı dizini ayarlar.|
|[CDataRecoveryHandler:: Setrestartıdentifier](#setrestartidentifier)|Bu örneği için benzersiz yeniden başlatma tanımlayıcıyı ayarlar `CDataRecoveryHandler` .|
|[CDataRecoveryHandler:: Setsavebelgetınonıdle](#setsavedocumentinfoonidle)|`CDataRecoveryHandler`Açık belge bilgilerini geçerli boşta geçiş sırasında Windows kayıt defterine kaydedip kaydetmediğini ayarlar.|
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|Uygulamanın önceki çıkış sonrasında yeniden başlatma yöneticisinin kaynaklanıp kaynaklanmadığını ayarlar.|
|[CDataRecoveryHandler:: Updatedocumentınfo](#updatedocumentinfo)|Belge, Kullanıcı tarafından kaydedildiği için bilgileri güncelleştirir.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|-|-|
|m_bRestoringPreviousOpenDocs|Veri kurtarma işleyicisinin önceden açık belgelerin yeniden açılıp açılmadığını gösterir.|
|m_bSaveDocumentInfoOnIdle|Veri kurtarma işleyicisinin bir sonraki boşta döngülü belgeleri oto olarak kaydedip kaydetmediğini belirtir.|
|m_bShutdownByRestartManager|Yeniden başlatma yöneticisinin uygulamanın çıkmasına neden olup olmadığını gösterir.|
|m_dwRestartManagerSupportFlags|Yeniden başlatma yöneticisinin uygulama için sağladığı desteği belirten bayraklar.|
|m_lstAutosavesToDelete|Özgün belgeler kapalıyken silinmediği otomatik kaydedilmiş dosyaların listesi. Uygulama çıktığında, yeniden başlatma Yöneticisi dosyaları silmeyi yeniden dener.|
|m_mapDocNameToAutosaveName|Belge adlarının otomatik kaydedilen dosya adlarına bir haritası.|
|m_mapDocNameToDocumentPtr|Belge adlarının [CDocument](../../mfc/reference/cdocument-class.md) işaretçilerine bir haritası.|
|m_mapDocNameToRestoreBool|Belge adlarının, otomatik kaydedilmiş belgenin geri yüklenip yüklenmeyeceğini gösteren bir Boolean parametresine haritası.|
|m_mapDocumentPtrToDocName|`CDocument`Belge adlarına işaretçilerin haritası.|
|m_mapDocumentPtrToDocTitle|`CDocument`Belge başlıklarına yönelik işaretçilerin haritası. Bu başlıklar dosyaları kaydetmek için kullanılır.|
|m_nAutosaveInterval|Tekrar kaydetmeler arasındaki milisaniye cinsinden süre.|
|m_nTimerID|Otomatik kaydetme zamanlayıcının tanımlayıcısı.|
|m_strAutosavePath|Otomatik kaydedilen belgelerin depolandığı konum.|
|m_strRestartIdentifier|Yeniden başlatma Yöneticisi için bir GUID 'nin dize temsili.|

## <a name="remarks"></a>Açıklamalar

Yeniden başlatma Yöneticisi, `CDataRecoveryHandler` tüm açık belgeleri izlemek ve gerektiğinde bunları otomatik olarak kaydetmek için sınıfını kullanır. Otomatik kaydetmeyi etkinleştirmek için [CDataRecoveryHandler:: Setsavebelgetınfoonıdle](#setsavedocumentinfoonidle) metodunu kullanın. Bu yöntem, `CDataRecoveryHandler` bir sonraki boşta döngüsünde bir otomatik kaydetme işlemi gerçekleştirmeye yönlendirir. Yeniden başlatma Yöneticisi `SetSaveDocumentInfoOnIdle` , ' nin `CDataRecoveryHandler` bir otomatik kaydetme gerçekleştirmesi durumunda çağırır.

Sınıfının tüm yöntemleri `CDataRecoveryHandler` sanal. Kendi özel veri kurtarma işleyicinizi oluşturmak için bu sınıftaki yöntemleri geçersiz kılın. Kendi veri kurtarma işleyicinizi veya yeniden başlatma yöneticisini oluşturmadığınız takdirde, bir CDataRecoveryHandler örneğini oluşturmayın. [CWinApp sınıfı](../../mfc/reference/cwinapp-class.md) , gerekli olduğu `CDataRecoveryHandler` gibi bir nesne oluşturur.

Bir nesneyi kullanabilmeniz için önce `CDataRecoveryHandler` [CDataRecoveryHandler:: Initialize](#initialize)öğesini çağırmanız gerekir.

`CDataRecoveryHandler`Sınıfı yeniden başlatma yöneticisine yakından bağlandığından, `CDataRecoveryHandler` genel parametreye bağımlıdır `m_dwRestartManagerSupportFlags` . Bu parametre, yeniden başlatma yöneticisinin hangi izinlere sahip olduğunu ve uygulamanızla nasıl etkileşime gireceğini belirler. Yeniden başlatma yöneticisini mevcut bir uygulamaya eklemek için, `m_dwRestartManagerSupportFlags` ana uygulamanızın oluşturucusuna uygun değeri atamanız gerekir. Yeniden başlatma Yöneticisi 'nin nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [nasıl yapılır: yeniden başlatma Yöneticisi desteği ekleme](../../mfc/how-to-add-restart-manager-support.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdatarecovery. h

## <a name="cdatarecoveryhandlerautosavealldocumentinfo"></a><a name="autosavealldocumentinfo"></a> CDataRecoveryHandler:: oto Savealldocumentınfo

Sınıfına kayıtlı her dosyayı oto olarak kaydeder `CDataRecoveryHandler` .

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>Dönüş Değeri

`CDataRecoveryHandler`Tüm belgeler KAYDEDILMIŞSE doğru; Herhangi bir belge kaydedilmamışsa FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kaydedilmesi gereken belge yoksa TRUE değerini döndürür. Ayrıca, `CWinApp` `CDocManager` uygulama bir hata oluşturursa, herhangi bir BELGEYI kaydetmeden true değerini döndürür.

Bu yöntemi kullanmak için, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART veya AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL içinde ayarlanması gerekir `m_dwRestartManagerSupportFlags` . Daha fazla bilgi için bkz. [nasıl yapılır: yeniden başlatma Yöneticisi desteği ekleme](../../mfc/how-to-add-restart-manager-support.md).

## <a name="cdatarecoveryhandlerautosavedocumentinfo"></a><a name="autosavedocumentinfo"></a> CDataRecoveryHandler:: oto Savedocumentınfo

Belirtilen belgeyi oto kaydeder.

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>Parametreler

*pDocument*\
'ndaki Kaydedilecek bir işaretçisi `CDocument` .

*bResetModifiedFlag*\
'ndaki TRUE, `CDataRecoveryHandler` *pDocument* 'in değiştirilmesini kabul eder; FALSE, Framework 'ün *pDocument* 'in değiştirilmemiş olduğunu düşünür. Bu bayrağın etkisi hakkında daha fazla bilgi için açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Uygun bayraklar ayarlandıysa ve *pDocument* geçerli bir `CDocument` nesneyse doğru.

### <a name="remarks"></a>Açıklamalar

Her `CDocument` nesne, son kaydetme işleminden sonra değişip değişmediğini gösteren bir bayrak içerir. Bu bayrağın durumunu öğrenmek için [CDocument:: IsModified](../../mfc/reference/cdocument-class.md#ismodified) kullanın. `CDocument`Son kaydetme işleminden sonra bir değişmediyseniz, `AutosaveDocumentInfo` Bu belge için otomatik kaydedilmiş dosyaları siler. Son kaydetmeden bu yana bir belge değiştiyse, kapatmadan önce kullanıcıdan belgeyi kaydetmesi istenir.

> [!NOTE]
> Belgenin durumunu değiştirilmemiş olarak değiştirmek için *Bresetmodifiedflag* kullanılması, kullanıcının kaydedilmemiş verileri kaybetmesine neden olabilir. Çerçeve bir belgeyi değiştirilmemiş olarak düşünür, kapatmak kullanıcıdan kaydetmesini istemez.

Bu yöntem, *pDocument* geçerli bir nesne değilse [onaylama](diagnostic-services.md#assert) makrosu ile bir özel durum oluşturur `CDocument` .

Bu yöntemi kullanmak için, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART veya AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL *m_dwRestartManagerSupportFlags* ayarlanmalıdır.

## <a name="cdatarecoveryhandlercdatarecoveryhandler"></a><a name="cdatarecoveryhandler"></a> CDataRecoveryHandler::CDataRecoveryHandler

Bir `CDataRecoveryHandler` nesnesi oluşturur.

```
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,
    int nAutosaveInterval);
```

### <a name="parameters"></a>Parametreler

*dwRestartManagerSupportFlags*\
'ndaki Yeniden başlatma Yöneticisi 'nin hangi seçeneklerinin desteklendiğini gösterir.

*Nautosaveınterval*\
'ndaki Oto kaydetme arasındaki süre. Bu parametre milisaniyedir.

### <a name="remarks"></a>Açıklamalar

`CDataRecoveryHandler` **Yeni proje** SIHIRBAZı 'nı kullandığınızda MFC çerçevesi otomatik olarak uygulamanız için bir nesne oluşturur. Veri kurtarma davranışını veya yeniden başlatma yöneticisini özelleştirmediğiniz takdirde bir nesne oluşturmamalıdır `CDataRecoveryHandler` .

## <a name="cdatarecoveryhandlercreatedocumentinfo"></a><a name="createdocumentinfo"></a> CDataRecoveryHandler:: Createdocumentınfo

Açık belgeler listesine bir belge ekler.

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Parametreler

*pDocument*\
'ndaki Bir işaretçisi `CDocument` . Bu yöntem, belge bilgilerini oluşturur `CDocument` .

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belgeyi eklemeden önce *pDocument* 'ın zaten belge listesinde olup olmadığını denetler. *PDocument* zaten listede ise, bu yöntem *pDocument* ile ilişkili otomatik kaydedilmiş dosyayı siler.

Bu yöntemi kullanmak için, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART veya AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL *m_dwRestartManagerSupportFlags* ayarlanmalıdır.

## <a name="cdatarecoveryhandlerdeleteallautosavedfiles"></a><a name="deleteallautosavedfiles"></a> CDataRecoveryHandler::D eleteAllAutosavedFiles

Tüm geçerli otomatik kaydedilmiş dosyaları siler.

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama her zaman TRUE değerini döndürür.

## <a name="cdatarecoveryhandlerdeleteautosavedfile"></a><a name="deleteautosavedfile"></a> CDataRecoveryHandler::D Eleteoto Kaydedilendosyası

Belirtilen otomatik kaydedilmiş dosyayı siler.

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>Parametreler

*strAutosavedFile*\
'ndaki Otomatik kaydedilmiş dosya adını içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem otomatik kaydedilmiş dosyayı silemezde, dosyanın adını bir listede kaydeder. İçin yıkıcısı, `CDataRecoveryHandler` Bu listede belirtilen her bir otomatik kaydedilmiş dosyayı silmeye çalışır.

## <a name="cdatarecoveryhandlergenerateautosavefilename"></a><a name="generateautosavefilename"></a> CDataRecoveryHandler:: Generateoto Savefilename

Sağlanan belge dosyası adıyla ilişkili bir otomatik kaydetme dosyası için ad üretir.

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>Parametreler

*strDocumentName*<br/>
'ndaki Belge adını içeren bir dize. `GenerateAutosaveFileName` karşılık gelen bir otomatik kaydetme dosya adı oluşturmak için bu belge adını kullanır.

### <a name="return-value"></a>Dönüş Değeri

*StrDocumentName* öğesinden oluşturulan otomatik kaydetme dosyası adı.

### <a name="remarks"></a>Açıklamalar

Her belge adının bir otomatik kaydetme dosya adı ile bire bir eşlemesi vardır.

## <a name="cdatarecoveryhandlergetautosaveinterval"></a><a name="getautosaveinterval"></a> CDataRecoveryHandler:: Getautosaveınterval

Otomatik kaydetme denemeler arasındaki aralığı döndürür.

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik kaydetme denemeler arasındaki milisaniye sayısı.

## <a name="cdatarecoveryhandlergetautosavepath"></a><a name="getautosavepath"></a> CDataRecoveryHandler:: GetAutosavePath

Otomatik kaydedilen dosyaların yolunu döndürür.

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik kaydedilen belgelerin depolandığı konum.

## <a name="cdatarecoveryhandlergetdocumentlistname"></a><a name="getdocumentlistname"></a> CDataRecoveryHandler:: Getdocumentıbu

Bir nesneden belge adını alır `CDocument` .

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>Parametreler

*pDocument*\
'ndaki Bir işaretçisi `CDocument` . `GetDocumentListName` belge adını bu dosyadan alır `CDocument` .

### <a name="return-value"></a>Dönüş Değeri

*PDocument*'daki belge adı.

### <a name="remarks"></a>Açıklamalar

, `CDataRecoveryHandler` *M_mapDocNameToAutosaveName*, *m_mapDocNameToDocumentPtr* ve *m_mapDocNameToRestoreBool*' deki anahtar olarak belge adını kullanır. Bu parametre `CDataRecoveryHandler` `CDocument` nesneleri, otomatik kaydetme dosya adını ve otomatik kaydetme ayarlarını izlemek için etkinleştirir.

## <a name="cdatarecoveryhandlergetnormaldocumenttitle"></a><a name="getnormaldocumenttitle"></a> CDataRecoveryHandler:: GetNormalDocumentTitle

Belirtilen belge için normal başlığı alır.

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>Parametreler

*pDocument*\
'ndaki Bir işaretçisi `CDocument` .

### <a name="return-value"></a>Dönüş Değeri

Belirtilen belge için normal başlık.

### <a name="remarks"></a>Açıklamalar

Belgenin normal başlığı genellikle yolun yolu olmadan dosya adıdır. Bu, **farklı kaydet** Iletişim kutusunun **dosya adı** alanındaki başlıktır.

## <a name="cdatarecoveryhandlergetrecovereddocumenttitle"></a><a name="getrecovereddocumenttitle"></a> CDataRecoveryHandler:: GetRecoveredDocumentTitle

Kurtarılan belgenin başlığını oluşturur ve döndürür.

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>Parametreler

*strDocumentTitle*<br/>
'ndaki Belge için normal başlık.

### <a name="return-value"></a>Dönüş Değeri

Kurtarılan belge başlığı.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir belgenin kurtarılan başlığı, **[kurtarılan]** öğesine eklenen normal başlıktır. Kurtarılan başlık, kullanıcıyı `CDataRecoveryHandler` Otomatik kaydedilmiş belgeleri geri yüklemeyi sorguladığında kullanıcıya gösterilir.

## <a name="cdatarecoveryhandlergetrestartidentifier"></a><a name="getrestartidentifier"></a> CDataRecoveryHandler:: Getrestartıdentifier

Uygulamanın benzersiz yeniden başlatma tanımlayıcısını alır.

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>Dönüş Değeri

Benzersiz yeniden başlatma tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma tanımlayıcısı, uygulamanın her yürütmesi için benzersizdir.

`CDataRecoveryHandler`Bilgileri, şu anda açık olan belgelerle ilgili kayıt defterine depolar. Yeniden başlatma Yöneticisi bir uygulamadan çıkıp yeniden başlattığında, için yeniden başlatma tanımlayıcısı sağlar `CDataRecoveryHandler` . , `CDataRecoveryHandler` Önceden açık belgelerin listesini almak için yeniden başlatma tanımlayıcısını kullanır. Bu, `CDataRecoveryHandler` Otomatik kaydedilmiş dosyaları bulmayı ve geri yüklemeyi denemeye olanak sağlar.

## <a name="cdatarecoveryhandlergetsavedocumentinfoonidle"></a><a name="getsavedocumentinfoonidle"></a> CDataRecoveryHandler:: Getsavebelgetınonıdle

`CDataRecoveryHandler`' Nin geçerli boşta döngüsünde bir otomatik kaydetme gerçekleştirip gerçekleştirmediğini belirtir.

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, `CDataRecoveryHandler` geçerli boşta döngüsünde, tekrar kaydettiğini belirtir; FALSE, olmadığını gösterir.

## <a name="cdatarecoveryhandlergetshutdownbyrestartmanager"></a><a name="getshutdownbyrestartmanager"></a> CDataRecoveryHandler::GetShutdownByRestartManager

Yeniden başlatma yöneticisinin uygulamanın çıkmasına neden olup olmadığını gösterir.

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, yeniden başlatma yöneticisinin uygulamanın çıkmasına neden olduğunu belirtir; FALSE, olmadığını gösterir.

## <a name="cdatarecoveryhandlerinitialize"></a><a name="initialize"></a> CDataRecoveryHandler:: Initialize

Öğesini başlatır `CDataRecoveryHandler` .

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Başlatma işlemi, otomatik kaydetme dosyalarını kayıt defterinden depolamak için yolu yükler. `Initialize`Yöntem bu dizini bulamazsa veya yol null ise, `Initialize` başarısız olur ve döndürür `FALSE` .

Uygulamanızı başlattıktan sonra otomatik kaydetme yolunu değiştirmek için [CDataRecoveryHandler:: SetAutosavePath](#setautosavepath) kullanın `CDataRecoveryHandler` .

`Initialize`Yöntemi, sonraki otomatik kaydetme işleminin ne zaman gerçekleşeceğini izlemek için de bir süreölçer başlatır. Uygulamanızı başlattıktan sonra otomatik kaydetme aralığını değiştirmek için [CDataRecoveryHandler:: SetAutosaveInterval](#setautosaveinterval) kullanın `CDataRecoveryHandler` .

## <a name="cdatarecoveryhandlerqueryrestoreautosaveddocuments"></a><a name="queryrestoreautosaveddocuments"></a> CDataRecoveryHandler:: QueryRestoreAutosavedDocuments

Otomatik kaydedilen her belge için kullanıcıya bir iletişim kutusu görüntüler `CDataRecoveryHandler` . İletişim kutusu, kullanıcının otomatik kaydedilen belgeyi geri yüklemek isteyip istemediğini belirler.

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>Açıklamalar

Uygulamanız Unicode ise, bu yöntem kullanıcıya bir [CTaskDialog Iletişim kutusu](../../mfc/reference/ctaskdialog-class.md) görüntüler. Aksi halde, çerçeve kullanıcıyı sorgulamak için [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) kullanır.

`QueryRestoreAutosavedDocuments`Kullanıcının tüm yanıtlarını topladıktan sonra, bilgileri *m_mapDocNameToRestoreBool* üye değişkeninde depolar. Bu yöntem, otomatik kaydedilmiş belgeleri geri yüklemez.

## <a name="cdatarecoveryhandlerreadopendocumentlist"></a><a name="readopendocumentlist"></a> CDataRecoveryHandler:: ReadOpenDocumentList

Kayıt defterinden açık belge listesini yükler.

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>Dönüş Değeri

TRUE `ReadOpenDocumentList` , kayıt defterinden en az bir belge için bilgileri yüklediğini belirtir; FALSE, hiçbir belge bilgisinin yüklenmediğini gösterir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, kayıt defterinden açık belge bilgilerini yükler ve *m_mapDocNameToAutosaveName* üye değişkeninde depolar.

`ReadOpenDocumentList`Tüm verileri yükledikten sonra, belge bilgilerini kayıt defterinden siler.

## <a name="cdatarecoveryhandlerremovedocumentinfo"></a><a name="removedocumentinfo"></a> CDataRecoveryHandler:: RemoveDocumentInfo

Sağlanan belgeyi açık belge listesinden kaldırır.

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Parametreler

*pDocument*\
'ndaki Kaldırılacak belgeye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*PDocument* LISTEDEN kaldırılmışsa true; Bir hata oluştuysa FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir belgeyi kapattığında, çerçeve bu yöntemi açık belgeler listesinden kaldırmak için kullanır.

`RemoveDocumentInfo`Açık Belgeler listesinde *pDocument* bulunamıyor, hiçbir şey yapmaz ve true değerini döndürür.

Bu yöntemi kullanmak için, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES *m_dwRestartManagerSupportFlags* ayarlanması gerekir.

## <a name="cdatarecoveryhandlerreopenpreviousdocuments"></a><a name="reopenpreviousdocuments"></a> CDataRecoveryHandler:: ReopenPreviousDocuments

Daha önce açık olan belgeleri açar.

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>Dönüş Değeri

En az bir belge açıldıysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, önceden açık belgelerin en son kaydedilmesini açar. Bir belge kaydedilmedi veya otomatik kaydedilmişken, `ReopenPreviousDocuments` Bu dosya türü için şablonu temel alan boş bir belge açar.

Bu yöntemi kullanmak için, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES *m_dwRestartManagerSupportFlags* ayarlanması gerekir. Bu parametre ayarlanmamışsa, `ReopenPreviousDocuments` hiçbir şey yapmaz ve false döndürür.

Daha önce açık belgeler listesinde depolanan belge yoksa, `ReopenPreviousDocuments` hiçbir şey yapmaz ve false döndürür.

## <a name="cdatarecoveryhandlerrestoreautosaveddocuments"></a><a name="restoreautosaveddocuments"></a> CDataRecoveryHandler:: RestoreAutosavedDocuments

Otomatik kaydedilmiş belgeleri Kullanıcı girişine göre geri yükler.

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem belgeleri başarıyla geri yüklerse TRUE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcının hangi belgeleri geri yüklemek istediğini belirleyen [CDataRecoveryHandler:: QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) öğesini çağırır. Bir kullanıcı otomatik kaydedilmiş bir belgeyi geri yüklemeyi deneriyorsa, `RestoreAutosavedDocuments` otomatik kaydetme dosyasını siler. Aksi takdirde, `RestoreAutosavedDocuments` Açık belgeyi otomatik kaydedilmiş sürümle değiştirir.

Bu yöntemi kullanmak için, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES veya AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES içinde ayarlanması gerekir `m_dwRestartManagerSupportFlags` .

## <a name="cdatarecoveryhandlersaveopendocumentlist"></a><a name="saveopendocumentlist"></a> CDataRecoveryHandler:: SaveOpenDocumentList

Açık belgelerin geçerli listesini Windows kayıt defterine kaydeder.

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>Dönüş Değeri

Kaydedilecek açık belge yoksa veya başarıyla kaydedildiyse TRUE. Kayıt defterine kaydedilecek belgeler varsa, ancak bir hata oluştuğundan kaydedilmediği için FALSE.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma Yöneticisi, `SaveOpenDocumentList` uygulama beklenmedik bir şekilde çıktığında veya bir yükseltme için çıktığında çağırır. Uygulama yeniden başlatıldığında, açık belgelerin listesini almak için [CDataRecoveryHandler:: ReadOpenDocumentList](#readopendocumentlist) öğesini kullanır.

Bu yöntem yalnızca açık belgelerin listesini kaydeder. [CDataRecoveryHandler:: oto Savedocumentınfo](#autosavedocumentinfo) yöntemi, belgelerin kendilerini kaydetmekten sorumludur.

## <a name="cdatarecoveryhandlersetautosaveinterval"></a><a name="setautosaveinterval"></a> CDataRecoveryHandler:: SetAutosaveInterval

Saniye cinsinden otomatik kaydetme döngüleri arasındaki süreyi ayarlar.

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>Parametreler

*Nautosaveınterval*<br/>
'ndaki Milisaniye cinsinden yeni otomatik kaydetme aralığı.

## <a name="cdatarecoveryhandlersetautosavepath"></a><a name="setautosavepath"></a> CDataRecoveryHandler:: SetAutosavePath

Otomatik kaydedilen dosyaların depolandığı dizini ayarlar.

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>Parametreler

*strAutosavePath*\
'ndaki Otomatik kaydetme dosyalarının depolandığı yol.

### <a name="remarks"></a>Açıklamalar

Otomatik kaydetme dizininin değiştirilmesi, şu anda otomatik kaydedilmiş dosyaları taşımaz.

## <a name="cdatarecoveryhandlersetrestartidentifier"></a><a name="setrestartidentifier"></a> CDataRecoveryHandler:: Setrestartıdentifier

Bu örneği için benzersiz yeniden başlatma tanımlayıcıyı ayarlar `CDataRecoveryHandler` .

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>Parametreler

*strRestartIdentifier*\
'ndaki Yeniden başlatma Yöneticisi için benzersiz tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Yeniden başlatma Yöneticisi, kayıt defterindeki açık belgelerle ilgili bilgileri kaydeder. Bu bilgiler, anahtar olarak benzersiz yeniden başlatma tanımlayıcısı ile birlikte depolanır. Yeniden başlatma tanımlayıcısı bir uygulamanın her örneği için benzersiz olduğundan, bir uygulamanın birden çok örneği beklenmedik bir şekilde sonlandırılabilir ve yeniden başlatma Yöneticisi bunların her birini kurtarabilir.

## <a name="cdatarecoveryhandlersetsavedocumentinfoonidle"></a><a name="setsavedocumentinfoonidle"></a> CDataRecoveryHandler:: Setsavebelgetınonıdle

`CDataRecoveryHandler`Açık belge bilgilerini geçerli boşta geçiş sırasında Windows kayıt defterine kaydedip kaydetmediğini ayarlar.

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>Parametreler

*Bsaveonıdle*\
'ndaki Geçerli boşta geçiş sırasında belge bilgilerini kaydetmek için TRUE; Kaydetme işlemi gerçekleştirmediğinden FALSE.

## <a name="cdatarecoveryhandlersetshutdownbyrestartmanager"></a><a name="setshutdownbyrestartmanager"></a> CDataRecoveryHandler::SetShutdownByRestartManager

Uygulamanın önceki çıkış sonrasında yeniden başlatma yöneticisinin kaynaklanıp kaynaklanmadığını ayarlar.

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>Parametreler

*bShutdownByRestartManager*\
'ndaki Yeniden başlatma yöneticisinin uygulamanın çıkmasına neden olduğunu belirtmek için TRUE; Uygulamanın başka bir nedenden dolayı çıkış olduğunu göstermek için FALSE.

### <a name="remarks"></a>Açıklamalar

Çerçeve, önceki çıkış beklenip yeniden başlatma Yöneticisi tarafından başlatılıp başlatılmayacağını temel alınarak farklı şekilde davranır.

## <a name="cdatarecoveryhandlerupdatedocumentinfo"></a><a name="updatedocumentinfo"></a> CDataRecoveryHandler:: Updatedocumentınfo

Belge, Kullanıcı tarafından kaydedildiği için bilgileri güncelleştirir.

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Parametreler

*pDocument*\
'ndaki Kaydedilen belgeye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem otomatik kaydedilmiş belgeyi sildiyseniz ve belge bilgilerini güncelleştirdiyse doğru; Bir hata oluştuysa FALSE.

### <a name="remarks"></a>Açıklamalar

Bir Kullanıcı bir belgeyi kaydettiğinde, artık gerekli olmadığından, uygulama otomatik kaydedilmiş dosyayı kaldırır. `UpdateDocumentInfo`[CDataRecoveryHandler:: RemoveDocumentInfo](#removedocumentinfo)çağırarak otomatik kaydedilmiş dosyayı siler. `UpdateDocumentInfo` daha sonra bu bilgileri sildiği, ancak kaydedilen belge hala açık olduğundan, *pDocument* bilgilerini şu anda açık olan belgeler listesine ekler `RemoveDocumentInfo` .

Bu yöntemi kullanmak için, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES *m_dwRestartManagerSupportFlags* ayarlanması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Nasıl yapılır: yeniden başlatma Yöneticisi desteği ekleme](../../mfc/how-to-add-restart-manager-support.md)
