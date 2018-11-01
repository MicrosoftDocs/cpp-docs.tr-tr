---
title: Güncelleştirilebilir Sağlayıcı Oluşturma
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 39e0fffa10af560537a932d503946ec2469bef5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570592"
---
# <a name="creating-an-updatable-provider"></a>Güncelleştirilebilir Sağlayıcı Oluşturma

Visual C++ güncelleştirilebilir sağlayıcılar veya güncelleştirebilirsiniz sağlayıcılarını destekler (yazma) veri deposu. Bu konu, OLE DB Şablonları kullanarak güncelleştirilebilir sağlayıcı oluşturma işlemini açıklar.

Bu konuda, uyumlu bir sağlayıcı ile başlayan varsayılır. Güncelleştirilebilir sağlayıcı oluşturma için iki adımı vardır. Sağlayıcı veri deposuna değişiklikleri nasıl yapacak önce karar vermeniz gerekir; Özellikle, değişiklikleri hemen yapılmasına olup bir güncelleştirme komut verilene kadar ertelendi. Bölüm "[sağlayıcıları güncelleştirilebilir yapmadan](#vchowmakingprovidersupdatable)" sağlayıcı kodunda yapmak için ihtiyacınız olan ayarları ve değişiklikleri açıklar.

Ardından, sağlayıcınız tüketici isteyebileceği desteklemek için tüm işlevselliklerini içerir emin olmanız gerekir. Tüketici veri deposunu güncelleştirin isterse, sağlayıcı veri deposunda veri devam kodu içermesi gerekir. Örneğin, veri kaynağı gibi işlemleri gerçekleştirmek için MFC ve C çalışma zamanı kitaplığı kullanabilirsiniz. Bölüm "[veri kaynağına yazma](#vchowwritingtothedatasource)" veri kaynağına yazmak için NULL ve varsayılan değerlerle Dağıt ve sütun bayraklarını ayarlayın açıklar.

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) güncelleştirilebilir sağlayıcı örneğidir. UpdatePV MyProv ancak güncelleştirilebilir destekle aynıdır.

##  <a name="vchowmakingprovidersupdatable"></a> Güncelleştirilebilir sağlayıcılar hale getirme

Anahtarı bir sağlayıcı güncelleştirilebilir yapmak istediğiniz veri deposuna ve bu işlemleri gerçekleştirmek için sağlayıcı istediğiniz gerçekleştirmek için sağlayıcınıza hangi işlemleri anlamaktır. Özellikle, veri deposuna güncelleştirmeleri hemen Bitti veya ertelenmiş olup önemli bir sorun olduğunu (toplanmış) güncelleştirme komut verilene kadar.

İlk devralınacak karar vermeniz gerekir `IRowsetChangeImpl` veya `IRowsetUpdateImpl` satır kümesi sınıfınızdaki. Bu uygulama seçiminize bağlı olarak, üç yöntem işlevselliği etkilenir: `SetData`, `InsertRows`, ve `DeleteRows`.

- Gelen devralıyorsanız [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), hemen bu üç yöntem çağırma veri deposu değiştirir.

- Gelen devralıyorsanız [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), çağırana kadar yöntemleri veri deposuna değişiklikler erteleme `Update`, `GetOriginalData`, veya `Undo`. Güncelleştirme birkaç değişikliği içeriyorsa, bunlar toplu iş modunda (değişiklikleri toplu işleme önemli ölçüde Bellek Yükü ekleyebilirsiniz. Not) gerçekleştirilir.

Unutmayın `IRowsetUpdateImpl` türetildiği `IRowsetChangeImpl`. Bu nedenle, `IRowsetUpdateImpl` değiştirme yeteneği yanı sıra batch yeteneği verir.

### <a name="to-support-updatability-in-your-provider"></a>Sağlayıcınızdaki Güncelleştirilebilirlik desteklemek için

1. Satır kümesi sınıfınızda devralınacak `IRowsetChangeImpl` veya `IRowsetUpdateImpl`. Bu sınıflar, veri depolama alanı değiştirmek için uygun arabirimleri sağlar:

     **IRowsetChange ekleme**

   Ekleme `IRowsetChangeImpl` bu formu kullanarak, devralma zincirini için:

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   Ayrıca `COM_INTERFACE_ENTRY(IRowsetChange)` için `BEGIN_COM_MAP` satır kümesi sınıfınıza bölümünde.

     **IRowsetUpdate ekleme**

   Ekleme `IRowsetUpdate` bu formu kullanarak, devralma zincirini için:

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

    > [!NOTE]
    > Kaldırmalısınız `IRowsetChangeImpl` , devralma zincirini satırından. Bu daha önce bahsedilen yönergesi bir durum kodunu içermelidir `IRowsetChangeImpl`.

1. COM haritanıza aşağıdakileri ekleyin (`BEGIN_COM_MAP ... END_COM_MAP`):

    |Uygularsanız|COM Eşlemesi Ekle|
    |----------------------|--------------------|
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|

1. Özellik kümesi haritanıza komutunuza ekleyin (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`):

    |Uygularsanız|Özellik kümesi haritasına Ekle|
    |----------------------|-----------------------------|
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|

1. Bunlar aşağıda görüldüğü gibi özellik kümesi eşlemesi, ayrıca tüm aşağıdaki ayarlardan birini içermelidir:

    ```cpp
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

   Özellik kimlikleri ve değerleri için Atldb.h bakarak bu makro çağrılarında kullanılan değerleri bulabilirsiniz (Atldb.h çevrimiçi belgelerinden farklıysa, Atldb.h belgeleri yerini alır).

    > [!NOTE]
    > Çoğu `VARIANT_FALSE` ve `VARIANT_TRUE` ayarları, OLE DB Şablonları tarafından gereklidir; OLE DB belirtimi okuma/yazma olabilirler, ancak OLE DB Şablonları, yalnızca bir değer destekleyebilir söyler.

     **IRowsetChangeImpl uygularsanız**

   Uygularsanız `IRowsetChangeImpl`, sağlayıcınız üzerinde aşağıdaki özellikleri ayarlayın. Bu özellikler öncelikle arabirimleri aracılığıyla istemek için kullanılan `ICommandProperties::SetProperties`.

    - `DBPROP_IRowsetChange`: Bu otomatik olarak kümelerini ayarlama `DBPROP_IRowsetChange`.

    - `DBPROP_UPDATABILITY`: Desteklenen yöntemlerden belirtme bir bit maskesi `IRowsetChange`: `SetData`, `DeleteRows`, veya `InsertRow`.

    - `DBPROP_CHANGEINSERTEDROWS`: Tüketici çağırabilir `IRowsetChange::DeleteRows` veya `SetData` yeni eklenen satırlar için.

    - `DBPROP_IMMOBILEROWS`: Satır kümesi, eklenen veya güncelleştirilen satır düzenlemez.

     **IRowsetUpdateImpl uygularsanız**

   Uygularsanız `IRowsetUpdateImpl`, aşağıdaki özellikleri sağlayıcınız üzerinde ayrıca tüm özelliklerini ayarlamak ayarlamanız gerekir `IRowsetChangeImpl` daha önce listelenen:

    - `DBPROP_IRowsetUpdate`.

    - `DBPROP_OWNINSERT`: READ_ONLY ve VARIANT_TRUE olması gerekir.

    - `DBPROP_OWNUPDATEDELETE`: READ_ONLY ve VARIANT_TRUE olması gerekir.

    - `DBPROP_OTHERINSERT`: READ_ONLY ve VARIANT_TRUE olması gerekir.

    - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY ve VARIANT_TRUE olması gerekir.

    - `DBPROP_REMOVEDELETED`: READ_ONLY ve VARIANT_TRUE olması gerekir.

    - `DBPROP_MAXPENDINGROWS`.

        > [!NOTE]
        > Bildirimleri destekliyorsa, bazı diğer özellikleri de da olabilir; bölümüne `IRowsetNotifyCP` bu listesi.

##  <a name="vchowwritingtothedatasource"></a> Veri kaynağına yazma

Veri kaynağından okumak için çağrı `Execute` işlevi. Veri kaynağına yazmak için çağrı `FlushData` işlevi. (Genel olarak, bir tablo veya dizini diske yaptığınız değişiklikleri kaydetmek için yol temizler.)

```cpp
FlushData(HROW, HACCESSOR);
```

Erişimci tanıtıcısı (HACCESSOR) bağımsız değişkenleri ve satır tanıtıcısı (HROW) yazmak için belirtmesine olanak sağlar. Genellikle, bir kerede tek bir veri alanının yazın.

`FlushData` Yöntemi içinde başlangıçta depolandığı biçiminde veri yazar. Bu işlev geçersiz kılmayacak sağlayıcınızın düzgün biçimde çalışmayacağıdır ancak değişiklikleri veri deposuna kullanılmaz.

### <a name="when-to-flush"></a>Ne zaman temizleme

Verileri veri deposuna yazılması her sağlayıcı şablonları FlushData çağırın. Bu genellikle (ama her zaman kullanılmaz) aşağıdaki işlevlere çağrı sonucunda oluşur:

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows` (satır eklemek için yeni veri yoksa)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>Nasıl çalışır?

Tüketici temizleme (örneğin, güncelleştirme) gerektiren bir çağrıda bulunur ve bu çağrı, her zaman şunları yapar sağlayıcıya geçirilir:

- Çağrıları `SetDBStatus` bağlı bir durum değerine sahip olduğunuzda.

- Sütun bayrakları denetler.

- Çağrıları `IsUpdateAllowed`.

Bu üç adımı güvenliğini sağlamak. Ardından sağlayıcısı çağrıları `FlushData`.

### <a name="how-to-implement-flushdata"></a>FlushData gerçekleştirme

Uygulamak için `FlushData`, çeşitli sorunlar dikkate almanız gerekir:

Veri deposu değişiklikleri işleyebildiğinden emin olun.

NULL değerleri işleme.

### <a name="handling-default-values"></a>Varsayılan değerleri işleme.

Kendi uygulamak için `FlushData` yöntemi gerekir:

- Satır kümesi sınıfı gidin.

- Satır kümesinde, sınıf bildirimi yerleştirin:

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- Bir uygulamasını sağlamak `FlushData`.

İyi bir uygulaması `FlushData` yalnızca satır ve gerçekten güncelleştirilir sütunları depolar. Geçerli satır ve sütunları için iyileştirme depolanmakta olan belirlemek için HROW ve HACCESSOR parametreleri kullanabilirsiniz.

Genellikle, en büyük güçlük, kendi yerel veri deposu ile çalışmaktadır. Mümkünse, deneyin:

- Veri deponuz olarak basit yazma yöntemi tutun.

- (İsteğe bağlı, ancak tavsiye edilir) NULL değerleri işleyin.

- (İsteğe bağlı, ancak tavsiye edilir) varsayılan değerlerini işler.

Yapılacak en iyi şey data Store NULL ve varsayılan değerleri için gerçek belirtilen değerlere sahip olmaktır. Bu veriler tahmin edebilmek en iyisidir. Aksi durumda, boş ve varsayılan değerlere izin vermeyecek şekilde önerilir.

Aşağıdaki örnekte gösterildiği nasıl `FlushData` uygulanan `RUpdateRowset` sınıfını `UpdatePV` örnek (satır örnek koda bakın):

```cpp
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

Sağlayıcınız değişiklikleri işlemek önce data store (örneğin, bir metin dosyası veya video dosyası) üzerinde değişiklik yapmanızı sağlayan olanaklara sahip olduğundan emin olmak gerekir. Kullanmıyorsa, kod sağlayıcısı projeden ayrı olarak oluşturmalısınız.

### <a name="handling-null-data"></a>BOŞ verileri işleme

Son kullanıcı NULL veri göndermesi mümkündür. Veri kaynağı alanları için NULL değerler yazma, olası sorunları olabilir. Şehir ve posta kodu için değerleri kabul eden bir sipariş alma uygulama düşünün; Bu durumda, teslim imkansız olur çünkü her ikisi de değerler, ancak değil ne kabul edemedi. Bu nedenle, belirli bir uygulama için anlamlı alanlarındaki NULL değerleri birleşimlerini sınırlamak zorunda.

Sağlayıcı geliştiricisi olarak, bu verileri nasıl depolar, nasıl bu verileri veri deposundan okur ve nasıl kullanıcıya belirlersiniz düşünmeniz gerekir. Satır kümesi veri veri kaynağındaki verileri durumunu değiştirmek nasıl özellikle dikkate almanız gereken (örneğin, DataStatus = NULL). Bir NULL değer içeren bir alanda bir tüketici eriştiğinde, dönüş değeri karar verin.

Kod oluşturma bakın; Bu, NULL veri sağlayıcı nasıl işleyebileceğini gösterir. UpdatePV öğesinde sağlayıcı NULL veri dizesi "NULL" yazarak veri deposunda saklar. NULL veri veri deposundan okur, o dizeyi görür ve ardından boş bir dize oluşturma arabellek boşaltır. Ayrıca, bir geçersiz kılma sahip `IRowsetImpl::GetDBStatus` , veri değeri boşsa, BT DBSTATUS_S_ISNULL döndürür.

### <a name="marking-nullable-columns"></a>Boş değer atanabilir sütun işaretleme

Şema satır kümeleri uygularsanız (bkz `IDBSchemaRowsetImpl`), uygulamanızın (genellikle sağlayıcınız tarafından CxxxSchemaColSchemaRowset işaretlenmiştir) DBSCHEMA_COLUMNS satır kümesindeki sütunu boş değer atanabilir belirtmeniz gerekir.

Tüm null yapılabilir sütunlar sürümünüz DBCOLUMNFLAGS_ISNULLABLE değeri içerdiğini belirtmeniz gerekir `GetColumnInfo`.

Sütun null yapılabilir, olarak işaretlemek başarısız olursa OLE DB Şablonları uygulamasında, bir değer içermelidir ve tüketici null değerler göndermesine izin vermez sağlayıcı varsayar.

Aşağıdaki örnekte gösterildiği nasıl `CommonGetColInfo` işlevi CUpdateCommand gerçekleştirilir (bkz. öğesinde) UpdatePV. Sütun null yapılabilir sütunlar için bu DBCOLUMNFLAGS_ISNULLABLE şeklinize unutmayın.

```cpp
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

BOŞ verilerle gibi varsayılan değerleri değiştirme ile ilgili sorumluluğu sahip.

Varsayılan değer olan `FlushData` ve `Execute` S_OK getirmektir. Bu işlev geçersiz ise, bu nedenle, değişiklikleri başarılı olması için görünür (S_OK döndürülür), ancak veri deposuna iletilmez.

İçinde `UpdatePV` (satır) içindeki örnek `SetDBStatus` yöntemi varsayılan değerleri şu şekilde işler:

```cpp
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

Varsayılan değerleri sütunlar üzerinde destekliyorsa, meta verileri kullanarak ayarlamanız gerekir \<sağlayıcı sınıfı\>SchemaRowset sınıfı. Ayarlama `m_bColumnHasDefault = VARIANT_TRUE`.

Ayrıca DBCOLUMNFLAGS kullanarak listelenmiş türü belirtilen sütun bayrakları ayarlamanızı sorumluluğu vardır. Sütun bayrakları sütun özelliklerini açıklar.

Örneğin, `CUpdateSessionColSchemaRowset` sınıfını `UpdatePV` (Session.h'deki), ilk sütun bu şekilde ayarlanır:

```cpp
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

Bu kod, diğerlerinin yanı sıra sütunu yazılabilir, 0, varsayılan değeri destekler ve sütundaki tüm verilerin aynı uzunluğa sahip olduğunu belirtir. Değişken uzunluğa sahip bir sütun verileri istiyorsanız, bu bayrağı ayarlamazsınız.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcısı Oluşturma](creating-an-ole-db-provider.md)