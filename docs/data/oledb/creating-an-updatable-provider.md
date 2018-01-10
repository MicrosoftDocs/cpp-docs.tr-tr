---
title: "Güncelleştirilebilir sağlayıcı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a57a54ac330e191961715440d652b9f084006b29
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-updatable-provider"></a>Güncelleştirilebilir Sağlayıcı Oluşturma
Visual C++ güncelleştirilebilir sağlayıcılar veya güncelleştirebilirsiniz sağlayıcılarını destekler (yazma) veri deposu. Bu konuda, OLE DB Şablonları kullanarak güncelleştirilebilir sağlayıcı oluşturma açıklanmaktadır.  
  
 Bu konu, çalışılabilir sağlayıcı ile başlayarak olduğunu varsayar. Güncelleştirilebilir sağlayıcı oluşturma için iki adımı vardır. Sağlayıcının veri deposuna değişiklikleri nasıl yapacak önce karar vermeniz gerekir; Özellikle, değişiklikleri hemen yapılmasına olup bir güncelleştirme komutu verilene kadar ertelendi. Bölüm "[sağlayıcıları güncelleştirilebilir yapma](#vchowmakingprovidersupdatable)" sağlayıcı kodunda yapmanız gereken ayarları ve değişiklikleri açıklar.  
  
 Ardından, sağlayıcınız tüketici isteyebileceği herhangi bir şey destekleyecek işlevselliği içerir emin olmanız gerekir. Tüketici veri deposunu güncelleştirmek istiyorsa, sağlayıcı veri deposuna veri devam ederse kodu içermesi gerekir. Örneğin, veri kaynağınız gibi işlemleri gerçekleştirmek için MFC ve C çalışma zamanı kitaplığı kullanabilirsiniz. Bölüm "[veri kaynağına yazma](#vchowwritingtothedatasource)" veri kaynağına yazma, uğraşmanız açıklar **NULL** ve varsayılan değerlerin ve sütun bayraklarını ayarlayın.  
  
> [!NOTE]
>  UpdatePV güncelleştirilebilir sağlayıcı örneğidir. UpdatePV MyProv olarak ancak güncelleştirilebilir desteği ile aynıdır.  
  
##  <a name="vchowmakingprovidersupdatable"></a>Sağlayıcıları güncelleştirilebilir hale getirme  
 Bir sağlayıcı güncelleştirilebilir hale getirme anahtarını sağlayıcınız veri deposu ve bu işlemleri gerçekleştirmek için sağlayıcı istediğiniz gerçekleştirmek istediğiniz hangi işlemlerin anlamaktır. Özellikle büyük veri deposu güncelleştirmeleri hemen Bitti veya ertelenmiş olup sorundur (toplu) bir güncelleştirme komutu verilene kadar.  
  
 İlk devralınacak karar vermeniz gerekir `IRowsetChangeImpl` veya `IRowsetUpdateImpl` satır kümesi sınıfınızda. Bunlardan hangilerini uygulamak istediğinize bağlı olarak, üç yöntem işlevselliğini etkilenecek: `SetData`, **InsertRows**, ve `DeleteRows`.  
  
-   Öğesinden devralmalı varsa [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), bu üç yöntem hemen çağırma veri deposu değiştirir.  
  
-   Öğesinden devralmalı varsa [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), çağırmanız kadar veri deposu değişiklikleri yöntemleri erteleneceği **güncelleştirme**, `GetOriginalData`, veya **geri**. Güncelleştirme birkaç değişiklik içeriyorsa, bunlar toplu iş modunda (Not değişiklikleri toplu işleme önemli ölçüde Bellek Yükü ekleyebilirsiniz) gerçekleştirilir.  
  
 Unutmayın `IRowsetUpdateImpl` türetilen `IRowsetChangeImpl`. Bu nedenle, `IRowsetUpdateImpl` değişim yeteneğini artı toplu yeteneği verir.  
  
#### <a name="to-support-updatability-in-your-provider"></a>Sağlayıcınızdaki Güncelleştirilebilirlik desteklemek için  
  
1.  Satır kümesi sınıfınızda devralınmalıdır `IRowsetChangeImpl` veya `IRowsetUpdateImpl`. Bu sınıfları, veri deposu değiştirmek için uygun arabirimleri sağlar:  
  
     **IRowsetChange ekleme**  
  
     Ekleme `IRowsetChangeImpl` bu formu kullanarak, devralma zincirini için:  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     Ayrıca ekleyin `COM_INTERFACE_ENTRY(IRowsetChange)` için `BEGIN_COM_MAP` satır kümesi sınıfınıza bölümünde.  
  
     **IRowsetUpdate ekleme**  
  
     Ekleme `IRowsetUpdate` bu formu kullanarak, devralma zincirini için:  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  Kaldırmanız gerekir `IRowsetChangeImpl` devralma zincirini satırından. Daha önce bahsedilen yönergesi bu bir özel durum kodunu içermelidir `IRowsetChangeImpl`.  
  
2.  COM eşlemenizi aşağıdakileri ekleyin (**BEGIN_COM_MAP... END_COM_MAP**):  
  
    |Öğesini uygularsanız|COM Eşlemesi Ekle|  
    |----------------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  Aşağıdaki özellik kümesi eşlemenizi komutunuza ekleyin (**BEGIN_PROPSET_MAP... END_PROPSET_MAP**):  
  
    |Öğesini uygularsanız|Özellik kümesi eşlemesi Ekle|  
    |----------------------|-----------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  Aşağıda göründükleri gibi özellik kümesi eşlemesini, ayrıca tüm aşağıdaki ayarlardan birini içermelidir:  
  
    ```  
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |   
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)  
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)  
  
    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)  
    ```  
  
     Özellik kimlikleri ve değerler için Atldb.h içine bakarak bu makro çağrılarında kullanılan değerleri bulabilirsiniz (Atldb.h çevrimiçi belgelerinden farklıysa Atldb.h belgeleri yerini alır).  
  
    > [!NOTE]
    >  Çoğu **VARIANT_FALSE** ve `VARIANT_TRUE` ayarları, OLE DB Şablonları tarafından gereklidir; OLE DB belirtimine okuma/yazma olabilir, ancak OLE DB şablonları yalnızca bir değer destekleyebilir söyler.  
  
     **IRowsetChangeImpl uygularsanız**  
  
     Öğesini uygularsanız `IRowsetChangeImpl`, sağlayıcınız üzerinde aşağıdaki özellikleri ayarlamanız gerekir. Bu özellikler öncelikle arabirimleri aracılığıyla istemek için kullanılan **ICommandProperties::SetProperties**.  
  
    -   `DBPROP_IRowsetChange`: Bu otomatik olarak ayarlar ayarlama **DBPROP_IRowsetChange**.  
  
    -   `DBPROP_UPDATABILITY`: Desteklenen yöntemlerden belirtme bir bit maskesi `IRowsetChange`: `SetData`, `DeleteRows`, veya `InsertRow`.  
  
    -   `DBPROP_CHANGEINSERTEDROWS`: Tüketici çağırabilir **IRowsetChange::DeleteRows** veya `SetData` yeni eklenen satırların.  
  
    -   `DBPROP_IMMOBILEROWS`: Satır kümesi eklenen veya güncelleştirilen satır yeniden değil.  
  
     **IRowsetUpdateImpl uygularsanız**  
  
     Öğesini uygularsanız `IRowsetUpdateImpl`, aşağıdaki özellikleri sağlayıcınız üzerinde ayrıca tüm özelliklerini ayarını ayarlamalısınız `IRowsetChangeImpl` daha önce listelenen:  
  
    -   `DBPROP_IRowsetUpdate`.  
  
    -   `DBPROP_OWNINSERT`: READ_ONLY ve VARIANT_TRUE olmalıdır.  
  
    -   `DBPROP_OWNUPDATEDELETE`: READ_ONLY ve VARIANT_TRUE olmalıdır.  
  
    -   `DBPROP_OTHERINSERT`: READ_ONLY ve VARIANT_TRUE olmalıdır.  
  
    -   `DBPROP_OTHERUPDATEDELETE`: READ_ONLY ve VARIANT_TRUE olmalıdır.  
  
    -   `DBPROP_REMOVEDELETED`: READ_ONLY ve VARIANT_TRUE olmalıdır.  
  
    -   `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  Bildirimleri destekliyorsa, bazı diğer özellikleri de sahip olabilir; bölümüne bakarak `IRowsetNotifyCP` bu liste için.  
  
     Örneğin özellikleri nasıl ayarlanır özellik eşlemesi bkz **CUpdateCommand** (içinde satır) içinde [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f).  
  
##  <a name="vchowwritingtothedatasource"></a>Veri kaynağına yazma  
 Veri kaynağından okumak için çağırın **yürütme** işlevi. Veri kaynağına yazmak için arama `FlushData` işlevi. (Genel olarak, bir tablo veya dizini diske yaptığınız değişiklikleri kaydetmek için yollar temizlenir.)  
  
```  
FlushData(HROW, HACCESSOR);  
```  
  
 Satır tanıtıcısı (*HROW*) ve erişimci tanıtıcısı (*HACCESSOR*) bağımsız değişkenleri yazılacak bölgeyi belirtmenize olanak tanır. Genellikle, bir kerede tek bir veri alanının yazma.  
  
 `FlushData` Yöntemi içinde başlangıçta depolandığı biçiminde veri yazar. Bu işlev geçersiz kılmaz sağlayıcınız düzgün biçimde çalışmayacağıdır ancak değişiklikleri veri deposuna Temizlenen değil.  
  
### <a name="when-to-flush"></a>Zaman temizlemek için  
 Sağlayıcı şablonları çağrısı `FlushData` her veri gereken veri deposuna yazılacak; bu genellikle (ancak her zaman) aşağıdaki işlevlere çağrıları sonucunda oluşur:  
  
-   **IRowsetChange::DeleteRows**  
  
-   **IRowsetChange::SetData**  
  
-   **IRowsetChange::InsertRows** (olup olmadığını satır eklemek için yeni veriler)  
  
-   **IRowsetUpdate::Update**  
  
### <a name="how-it-works"></a>Nasıl çalışır?  
 Tüketici temizleme gerektiren bir çağrı yapar (gibi **güncelleştirme**) ve bu çağrıyı her zaman aşağıdakileri yapar sağlayıcıya geçirilir:  
  
-   Çağrıları `SetDBStatus` bağlı bir durum değerine sahip olduğunda (bkz *OLE DB Programcı Başvurusu*, Bölüm 6 *veri bölümleri: durum*).  
  
-   Sütun bayrakları denetler.  
  
-   Çağrıları `IsUpdateAllowed`.  
  
 Bu üç adımı güvenliğini sağlamak. Ardından sağlayıcı çağrıları `FlushData`.  
  
### <a name="how-to-implement-flushdata"></a>FlushData gerçekleştirme  
 Uygulanacak `FlushData`, çeşitli sorunları dikkate almanız gerekir:  
  
-   Veri deposunun değişiklikleri işleyebildiğinden emin olma.  
  
-   İşleme **NULL** değerleri.  
  
-   İşleme varsayılan değerleri.  
  
 Kendi uygulamak için `FlushData` yöntemi, gerekir:  
  
-   Satır kümesi sınıfınıza gidin.  
  
-   Satır kümesinde sınıf bildirimi koyun:  
  
```  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    // Insert your implementation here and return an HRESULT.  
}  
```  
  
-   Bir belirtin `FlushData`.  
  
 İyi bir uyarlamasını `FlushData` yalnızca satır ve gerçekte güncelleştirilir sütunları depolar. Kullanabileceğiniz *HROW* ve *HACCESSOR* geçerli satır ve sütun için en iyi duruma getirme depolanmakta belirlemek için parametreler.  
  
 Genellikle, en büyük zorluk kendi yerel veri deposu ile çalışmaktadır. Mümkünse, deneyin:  
  
-   Veri deponuza kadar basit yazma yöntemi tutun.  
  
-   İşleme **NULL** değerleri (isteğe bağlı, ancak tavsiye edilir).  
  
-   Varsayılan değerleri (isteğe bağlı, ancak tavsiye edilir) işler.  
  
 Yapmak için en iyi veri deponuzda gerçek belirtilen değerlere sahip şeydir **NULL** ve varsayılan değerleri. Bu verileri tahmin en iyisidir. Değilse, izin verme önerilir, **NULL** ve varsayılan değerleri.  
  
 Aşağıdaki örnekte gösterildiği nasıl `FlushData` uygulanan `RUpdateRowset` sınıfını [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) örneği (örnek kodda satır bakın):  
  
```  
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
...  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    ATLTRACE2(atlTraceDBProvider, 0, "RUpdateRowset::FlushData\n");  
  
    USES_CONVERSION;  
    enum {  
        sizeOfString = 256,  
        sizeOfFileName = MAX_PATH  
    };  
    FILE*    pFile = NULL;  
    TCHAR    szString[sizeOfString];  
    TCHAR    szFile[sizeOfFileName];  
    errcode  err = 0;  
  
    ObjectLock lock(this);  
  
    // From a filename, passed in as a command text,   
    // scan the file placing data in the data array.  
    if (m_strCommandText == (BSTR)NULL)  
    {  
        ATLTRACE( "RRowsetUpdate::FlushData -- "  
                  "No filename specified\n");  
        return E_FAIL;  
    }  
  
    // Open the file  
    _tcscpy_s(szFile, sizeOfFileName, OLE2T(m_strCommandText));  
    if ((szFile[0] == _T('\0')) ||   
        ((err = _tfopen_s(&pFile, &szFile[0], _T("w"))) != 0))  
    {  
        ATLTRACE("RUpdateRowset::FlushData -- Could not open file\n");  
        return DB_E_NOTABLE;  
    }  
  
    // Iterate through the row data and store it.  
    for (long l=0; l<m_rgRowData.GetSize(); l++)  
    {  
        CAgentMan am = m_rgRowData[l];  
  
        _putw((int)am.dwFixed, pFile);  
  
        if (_tcscmp(&am.szCommand[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szText[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szText);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szCommand2[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand2);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szText2[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szText2);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
    }  
  
    if (fflush(pFile) == EOF || fclose(pFile) == EOF)  
    {  
        ATLTRACE("RRowsetUpdate::FlushData -- "  
                 "Couldn't flush or close file\n");  
    }  
  
    return S_OK;  
}  
```  
  
### <a name="handling-changes"></a>Değişiklikleri işleme  
 Sağlayıcınız değişiklikleri yürütmek için ilk data store (örneğin, bir metin dosyası veya video dosyası) üzerinde değişiklik yapmanızı sağlamak olanaklara sahip olduğundan emin olmanız gerekir. Yoksa, bu kodu sağlayıcı projesinden ayrı oluşturmalısınız.  
  
### <a name="handling-null-data"></a>NULL veri işleme  
 Bir son kullanıcı göndereceğiniz mümkündür **NULL** veri. Yazdığınız zaman **NULL** değerleri veri kaynağındaki alanlarına olabilir olası sorunları. Şehir ve posta kodu değerlerini kabul eden bir sipariş alma uygulama düşünün; Bu durumda teslim imkansız olan olduğundan birini veya her ikisini değerleri, ancak değil hiçbiri kabul edemedi. Bu nedenle belirli birleşimlerini kısıtlamak sahip **NULL** uygulamanız için anlamlı alanlarında değer.  
  
 Sağlayıcı geliştiricisi olarak, bu verileri nasıl depolar, veri deposundan verileri nasıl okuma yapacak ve nasıl, kullanıcıya belirttiğiniz dikkate almanız gerekir. Satır kümesi veri veri kaynağındaki veri durumunu değiştirmek nasıl özellikle dikkate almanız gereken (örneğin, DataStatus = **NULL**). Ne alan içeren bir tüketici eriştiğinde, döndürülecek değer karar bir **NULL** değeri.  
  
 Kodda bakabilir [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) örnek; gösterilmektedir sağlayıcı nasıl işleyebilir **NULL** veri. Sağlayıcı UpdatePV öğesinde depolar **NULL** veri deposunda dizesi "NULL" yazarak veri. Ne zaman okur **NULL** verisini veri deposuna, bu dizeyi görür ve arabellek boşaltır oluşturma bir **NULL** dize. Ayrıca, bir geçersiz kılma sahip `IRowsetImpl::GetDBStatus` hangi döndürür, **DBSTATUS_S_ISNULL** , veri değeri boş ise.  
  
### <a name="marking-nullable-columns"></a>Boş değer atanabilir sütunları işaretleme  
 Şema satır kümeleri de uygularsanız (bkz `IDBSchemaRowsetImpl`), uygulamanızı belirtmeniz gerekir **DBSCHEMA_COLUMNS** satır kümesi (genellikle sağlayıcınız tarafından olarak işaretlenmiş **C***xxx* **SchemaColSchemaRowset**) sütunu null olabilir.  
  
 Ayrıca tüm boş değer atanabilir sütun içermesi belirtmek zorunda **DBCOLUMNFLAGS_ISNULLABLE** sürümünüz değerinde `GetColumnInfo`.  
  
 Sütun null yapılabilir, olarak işaretlemek başarısız olursa OLE DB Şablonları uygulamasında sağlayıcı bir değer içermelidir ve tüketici null değerler göndermesine izin vermez olduğunu varsayar.  
  
 Aşağıdaki örnekte gösterildiği nasıl **CommonGetColInfo** işlevi uygulandığına **CUpdateCommand** (öğesinde bakın) UpdatePV. Sütunları bu şeklinize Not **DBCOLUMNFLAGS_ISNULLABLE** boş değer atanabilir sütunlar için.  
  
```  
/////////////////////////////////////////////////////////////////////////////  
// CUpdateCommand (in UpProvRS.cpp)  
  
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols, bool bBookmark)  
{  
    static ATLCOLUMNINFO _rgColumns[6];  
    ULONG ulCols = 0;  
  
    if (bBookmark)  
    {  
        ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,  
                            sizeof(DWORD), DBTYPE_BYTES,  
                            0, 0, GUID_NULL, CAgentMan, dwBookmark,  
                            DBCOLUMNFLAGS_ISBOOKMARK)  
        ulCols++;  
    }  
  
    // Next set the other columns up.  
    // Add a fixed length entry for OLE DB conformance testing purposes  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Fixed"), 1, 4, DBTYPE_UI4,  
                        10, 255, GUID_NULL, CAgentMan, dwFixed,   
                        DBCOLUMNFLAGS_WRITE |   
                        DBCOLUMNFLAGS_ISFIXEDLENGTH)  
    ulCols++;  
  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command"), 2, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szCommand,  
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text"), 3, 16, DBTYPE_STR,   
                        255, 255, GUID_NULL, CAgentMan, szText,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command2"), 4, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szCommand2,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text2"), 5, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szText2,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
  
    if (pcCols != NULL)  
    {  
        *pcCols = ulCols;  
    }  
  
    return _rgColumns;  
}  
```  
  
### <a name="default-values"></a>Varsayılan değerler  
 İle **NULL** verilerine varsayılan değerlerini değiştirme ile mücadele etmek için sorumluluk sahiptir.  
  
 Varsayılan değer olan `FlushData` ve **yürütme** döndürülmesini `S_OK`. Bu işlev geçersiz kılmaz, bu nedenle, değişiklikler başarılı görünür (`S_OK` döndürülür), ancak veri deposuna aktarılmaz.  
  
 İçinde [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) (Rowset.h), örnek `SetDBStatus` yöntemi varsayılan değerleri aşağıdaki gibi işler:  
  
```  
virtual HRESULT SetDBStatus(DBSTATUS* pdbStatus, CSimpleRow* pRow,  
                            ATLCOLUMNINFO* pColInfo)  
{  
    ATLASSERT(pRow != NULL && pColInfo != NULL && pdbStatus != NULL);  
  
    void* pData = NULL;  
    char* pDefaultData = NULL;  
    DWORD* pFixedData = NULL;  
  
    switch (*pdbStatus)  
    {  
        case DBSTATUS_S_DEFAULT:  
            pData = (void*)&m_rgRowData[pRow->m_iRowset];  
            if (pColInfo->wType == DBTYPE_STR)  
            {  
                pDefaultData = (char*)pData + pColInfo->cbOffset;  
                strcpy_s(pDefaultData, "Default");  
            }  
            else  
            {  
                pFixedData = (DWORD*)((BYTE*)pData +   
                                          pColInfo->cbOffset);  
                *pFixedData = 0;  
                return S_OK;  
            }  
            break;  
        case DBSTATUS_S_ISNULL:  
        default:  
            break;  
    }  
    return S_OK;  
}  
```  
  
### <a name="column-flags"></a>Sütun bayrakları  
 Varsayılan değerler sütunlar üzerinde destekliyorsa, meta verileri kullanarak ayarlamanız gerekir  **\<**  *sağlayıcı sınıfı***> SchemaRowset** sınıfı. Ayarlama *m_bColumnHasDefault* = `VARIANT_TRUE`.  
  
 Kullanılarak belirtilen sütun bayraklarını ayarlayın sorumluluğu de **DBCOLUMNFLAGS** numaralandırılmış türü. Sütun bayrakları sütun özelliklerini açıklar.  
  
 Örneğin, `CUpdateSessionColSchemaRowset` sınıfını [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) (Session.h'deki), ilk sütun bu şekilde ayarlanır:  
  
```  
// Set up column 1  
trData[0].m_ulOrdinalPosition = 1;  
trData[0].m_bIsNullable = VARIANT_FALSE;  
trData[0].m_bColumnHasDefault = VARIANT_TRUE;  
trData[0].m_nDataType = DBTYPE_UI4;  
trData[0].m_nNumericPrecision = 10;  
trData[0].m_ulColumnFlags = DBCOLUMNFLAGS_WRITE |  
                            DBCOLUMNFLAGS_ISFIXEDLENGTH;  
lstrcpyW(trData[0].m_szColumnDefault, OLESTR("0"));  
m_rgRowData.Add(trData[0]);  
```  
  
 Bu kod, diğerlerinin yanında, sütun yazılabilir, 0, varsayılan değeri destekler ve sütundaki tüm verilerin aynı uzunlukta olduğunu belirtir. Değişken uzunlukta olmasını bir sütundaki verileri istiyorsanız, bu bayrağı ayarlamazsınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)