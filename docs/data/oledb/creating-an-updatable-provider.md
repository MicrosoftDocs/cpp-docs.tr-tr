---
title: Güncelleştirilebilir Sağlayıcı Oluşturma
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 720ceba397d17642402de4d44cbb4481852fa153
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365553"
---
# <a name="creating-an-updatable-provider"></a>Güncelleştirilebilir Sağlayıcı Oluşturma

Visual C++ veri deposunu güncelleştirebilen (yazabilen) güncellenebilir sağlayıcıları veya sağlayıcıları destekler. Bu konu, OLE DB şablonlarını kullanarak nasıl güncellenilebilir sağlayıcılar oluşturulacak şekilde açıklanmıştır.

Bu konu, uygulanabilir bir sağlayıcı ile başlıyor varsayar. Güncel bir sağlayıcı oluşturmak için iki adım vardır. Öncelikle sağlayıcının veri deposunda nasıl değişiklik yapacağına karar vermeniz gerekir; özellikle, değişikliklerin hemen yapılıp yapılmayacağı veya bir güncelleştirme komutu verilene kadar ertelenip ertelenmeyeceği. ["Sağlayıcıları Güncelle"](#vchowmakingprovidersupdatable)bölümü, sağlayıcı kodunda yapmanız gereken değişiklikleri ve ayarları açıklar.

Ardından, sağlayıcınızın tüketicinin talep edebileceği her şeyi destekleyecek tüm işlevleri içerdiğinden emin olmalısınız. Tüketici veri deposunu güncelleştirmek istiyorsa, sağlayıcının veri deposunda veri kalıcılığı olan kod içermesi zorundadır. Örneğin, veri kaynağınızda bu tür işlemleri gerçekleştirmek için C Run-Time Kitaplığını veya MFC'yi kullanabilirsiniz. "Veri[Kaynağına Yazma](#vchowwritingtothedatasource)" bölümü, veri kaynağına nasıl yazılalıyapılacağını, NULL ve varsayılan değerlerle nasıl başa çıkılsüreceğini ve sütun bayraklarını nasıl ayarlayabildiğini açıklar.

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) güncelbir sağlayıcı örneğidir. UpdatePV MyProv ile aynıdır ama güncelleyici desteği ile.

## <a name="making-providers-updatable"></a><a name="vchowmakingprovidersupdatable"></a>Sağlayıcıları Güncele getirilebilir hale getirme

Bir sağlayıcıyı güncelletilebilir hale getirmenin anahtarı, sağlayıcınızın veri deposunda hangi işlemleri gerçekleştirmesini istediğinizi ve sağlayıcının bu işlemleri nasıl yürütmesini istediğinizi anlamaktır. Özellikle, en önemli sorun, veri deposundaki güncelleştirmelerin güncelleştirme komutu verilene kadar hemen yapılıp yapılmayacağı veya ertelenip ertelenmeyeceğidir (toplu işlenmedi).

Öncelikle rowset sınıfınızdan `IRowsetChangeImpl` mı `IRowsetUpdateImpl` yoksa sıra kümesi sınıfınızdan mı devraldığınıza karar vermelisiniz. Bunlardan hangisini uygulamayı seçtiğinize bağlı olarak, üç yöntemin `SetData`işlevselliği etkilenir: , , `InsertRows`ve `DeleteRows`.

- [IRowsetChangeImpl'den](../../data/oledb/irowsetchangeimpl-class.md)miras alırsanız, bu üç yöntemi çağırmak hemen veri deposunu değiştirir.

- [IRowsetUpdateImpl'den](../../data/oledb/irowsetupdateimpl-class.md)devralırsanız, yöntemler veri deposundaki değişiklikleri `Update`, `GetOriginalData`veya `Undo`. Güncelleştirme birkaç değişiklik içeriyorsa, toplu iş modunda gerçekleştirilir (toplu iş değiştirmelerin önemli miktarda bellek yükü ekleyebileceğini unutmayın).

`IRowsetUpdateImpl` Bu türetilmiştir `IRowsetChangeImpl`unutmayın. Böylece, `IRowsetUpdateImpl` yeteneği artı toplu iş yeteneği değiştirmek verir.

### <a name="to-support-updatability-in-your-provider"></a>Sağlayıcınızda yükseltilebilirliği desteklemek için

1. Rowset sınıfınızda, `IRowsetChangeImpl` devralan `IRowsetUpdateImpl`veya . Bu sınıflar, veri deposunu değiştirmek için uygun arabirimler sağlar:

   **IRowsetChange ekleme**

   Bu `IRowsetChangeImpl` formu kullanarak devralma zincirinize ekleyin:

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   Ayrıca `COM_INTERFACE_ENTRY(IRowsetChange)` rowset `BEGIN_COM_MAP` sınıfındabölüme ekleyin.

   **IRowsetUpdate ekleme**

   Bu `IRowsetUpdate` formu kullanarak devralma zincirinize ekleyin:

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > `IRowsetChangeImpl` Çizgiyi kalıtım zincirinden çıkarmalısın. Daha önce bahsedilen yönergeye bu bir istisna `IRowsetChangeImpl`için kod içermelidir.

1. COM haritanıza aşağıdakileri`BEGIN_COM_MAP ... END_COM_MAP`ekleyin ( ):

   |  Eğer uygularsanız   |           COM haritasına ekle             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | Eğer uygularsanız | Özellik kümesi haritasına ekle |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. Komutunuzda, özellik kümesi haritanıza aşağıdakileri`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`ekleyin ( ):

   |  Eğer uygularsanız   |                                             Özellik kümesi haritasına ekle                                              |
   |---------------------|------------------------------------------------------------------------------------------------------------------|
   | `IRowsetChangeImpl` |                            `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`                             |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. Özellik kümesi haritanızda, aşağıdaki ayarların tümlerini aşağıda göründükleri gibi eklemeniz gerekir:

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

   Bu makro aramalarında kullanılan değerleri özellik disleri ve değerleri için Atldb.h'ye bakarak bulabilirsiniz (Atldb.h çevrimiçi belgelerden farklıysa, Atldb.h belgelerin yerini alabiliyor).

   > [!NOTE]
   > Ayarların `VARIANT_FALSE` `VARIANT_TRUE` çoğu OLE DB şablonları tarafından gereklidir; OLE DB belirtimi, okunabilir/yazılabilir, ancak OLE DB şablonları yalnızca bir değeri destekleyebilir diyor.

   **IRowsetChangeImpl uygularsanız**

   Uygularsanız, `IRowsetChangeImpl`sağlayıcınızda aşağıdaki özellikleri ayarlamanız gerekir. Bu özellikler öncelikle üzerinden arabirimleri `ICommandProperties::SetProperties`istemek için kullanılır.

   - `DBPROP_IRowsetChange`: Bu otomatik `DBPROP_IRowsetChange`olarak ayarlar .

   - `DBPROP_UPDATABILITY`: Desteklenen yöntemleri belirten bir bitmask `SetData` `DeleteRows` `IRowsetChange`: `InsertRow`, , veya .

   - `DBPROP_CHANGEINSERTEDROWS`: Tüketici `IRowsetChange::DeleteRows` arayabilir `SetData` veya yeni eklenen satırlar için.

   - `DBPROP_IMMOBILEROWS`: Rowset, eklenen veya güncelleştirilmiş satırları yeniden sıralamaz.

   **IRowsetUpdateImpl uygularsanız**

   Uygularsanız, `IRowsetUpdateImpl` `IRowsetChangeImpl` daha önce listelenen tüm özellikleri ayarlamaya ek olarak sağlayıcınızda aşağıdaki özellikleri ayarlamanız gerekir:

   - `DBPROP_IRowsetUpdate`.

   - `DBPROP_OWNINSERT`: READ_ONLY VE VARIANT_TRUE olmalıdır.

   - `DBPROP_OWNUPDATEDELETE`: READ_ONLY VE VARIANT_TRUE olmalıdır.

   - `DBPROP_OTHERINSERT`: READ_ONLY VE VARIANT_TRUE olmalıdır.

   - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY VE VARIANT_TRUE olmalıdır.

   - `DBPROP_REMOVEDELETED`: READ_ONLY VE VARIANT_TRUE olmalıdır.

   - `DBPROP_MAXPENDINGROWS`.

   > [!NOTE]
   > Bildirimleri destekliyorsanız, başka özellikleriniz de olabilir; bu listeiçin `IRowsetNotifyCP` bölüme bakın.

## <a name="writing-to-the-data-source"></a><a name="vchowwritingtothedatasource"></a>Veri Kaynağına Yazma

Veri kaynağından okumak için `Execute` işlevi arayın. Veri kaynağına yazmak için `FlushData` işlevi arayın. (Genel anlamda floş, bir tabloda yaptığınız değişiklikleri veya dizinle diske kaydetmek anlamına gelir.)

```cpp
FlushData(HROW, HACCESSOR);
```

Satır tutamacı (HROW) ve erişimci tanıtıcı (HACCESSOR) bağımsız değişkenleri, yazacak bölgeyi belirtmenize olanak sağlar. Genellikle, aynı anda tek bir veri alanı yazarsınız.

Yöntem, `FlushData` verileri ilk depolandığı biçimde yazar. Bu işlevi geçersiz kılmazsanız, sağlayıcınız doğru çalışır, ancak değişiklikler veri deposuna atılamaz.

### <a name="when-to-flush"></a>Flush ne zaman

Sağlayıcı şablonları, verilerin veri deposuna yazılması gerektiğinde FlushData'yı arar; bu genellikle (ancak her zaman değil) aşağıdaki işlevlere yapılan çağrıların bir sonucu olarak ortaya çıkar:

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows`(satıra eklenecek yeni veriler varsa)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>Nasıl Çalışır?

Tüketici floş gerektiren bir arama yapar (Güncelleştirme gibi) ve bu çağrı her zaman aşağıdakileri yapar sağlayıcıya iletilir:

- Durum `SetDBStatus` değeriniz bağlı olduğunda aramalar.

- Sütun bayraklarını denetler.

- Aramalar `IsUpdateAllowed`.

Bu üç adım güvenliği sağlamaya yardımcı olur. Sonra sağlayıcı `FlushData`çağırır.

### <a name="how-to-implement-flushdata"></a>FlushData Nasıl Uygulanır?

Uygulamak `FlushData`için, dikkate çeşitli sorunları almak gerekir:

Veri deposunun değişiklikleri işleyediğinden emin olun.

NULL değerlerini işleme.

### <a name="handling-default-values"></a>Varsayılan değerleri işleme.

Kendi `FlushData` yönteminizi uygulamak için şunları yapmanız gerekir:

- Rowset sınıfına git.

- Rowset sınıfında aşağıdakileri bildirgeyi koydu:

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- Bir uygulama `FlushData`sağlayın.

`FlushData` Yalnızca güncelleştirilen satır ve sütunları saklar. Optimizasyon için depolanan geçerli satır ve sütunu belirlemek için HROW ve HACCESSOR parametrelerini kullanabilirsiniz.

Genellikle, en büyük sorun kendi yerel veri deposu ile çalışmaktır. Mümkünse şunları deneyin:

- Veri deponuza yazma yöntemini olabildiğince basit tutun.

- NULL değerlerini işleme (isteğe bağlı ancak tavsiye edilir).

- Varsayılan değerleri işleme (isteğe bağlı ancak tavsiye edilir).

Yapmanız gereken en iyi şey, NULL ve varsayılan değerler için veri deposunuzda gerçek belirtilen değerlere sahip olmaktır. Bu verileri tahmin edebilirsiniz en iyisidir. Değilse, NULL ve varsayılan değerlere izin vermemeniz önerilir.

Aşağıdaki örnek, `FlushData` örnekteki `RUpdateRowset` sınıfta nasıl uygulandığını `UpdatePV` gösterir (örnek koddaki Rowset.h'ye bakın):

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

### <a name="handling-changes"></a>Değişiklikleri Işleme

Sağlayıcınızın değişiklikleri işlemesi için öncelikle veri deponuzun (metin dosyası veya video dosyası gibi) üzerinde değişiklik yapmanızı sağlayan olanaklara sahip olduğundan emin olmanız gerekir. Yoksa, bu kodu sağlayıcı projeden ayrı olarak oluşturmanız gerekir.

### <a name="handling-null-data"></a>NULL Verilerini Işleme

Bir son kullanıcının NULL verisi göndermesi mümkündür. Veri kaynağındaki alanlara NULL değerleri yazdığınızda, olası sorunlar olabilir. Şehir ve posta kodu değerlerini kabul eden bir sipariş alma uygulaması düşünün; ya da her iki değeri de kabul edebilir, ama ikisi de kabul etmez, çünkü bu durumda teslim imkansız olacaktır. Bu nedenle, uygulamanız için anlamlı olan alanlardaki null değerlerinin belirli birleşimlerini kısıtlamanız gerekir.

Sağlayıcı geliştiricisi olarak, bu verileri nasıl depoladığınızı, veri deposundan bu verileri nasıl okuyacağınızı ve bunu kullanıcıya nasıl belirttiğinizi göz önünde bulundurmanız gerekir. Özellikle, veri kaynağındaki satır kümesi verilerinin veri durumunu nasıl değiştireceğiniz göz önünde bulundurulmalıdır (örneğin, DataStatus = NULL). Bir tüketici NULL değeri içeren bir alana eriştığında hangi değeri döndüreceğine siz karar verirsiniz.

UpdatePV örneğindeki koda bakın; sağlayıcının NULL verilerini nasıl işleyeceğini gösterir. UpdatePV'de sağlayıcı, veri deposuna "NULL" dizesini yazarak NULL verilerini depolar. Veri deposundan NULL verilerini okuduğunda, bu dizeyi görür ve arabelleği boşalarak null dizesini oluşturur. Ayrıca, veri değeri `IRowsetImpl::GetDBStatus` boşsa DBSTATUS_S_ISNULL döndürdeğinin geçersiz kılındığı da bir geçersiz kılma vardır.

### <a name="marking-nullable-columns"></a>Nullable Sütunları İşaretleme

Şema satır kümelerini de uygularsanız (bakınız), `IDBSchemaRowsetImpl`uygulamanız DBSCHEMA_COLUMNS rowset'te (genellikle Sağlayıcınızda CxxxSchemaColSchemaRowset tarafından işaretlenir) sütunun geçersiz olduğunu belirtmelidir.

Ayrıca, tüm boşatılabilir sütunların DBCOLUMNFLAGS_ISNULLABLE değerini içerdiğini belirtmeniz `GetColumnInfo`gerekir.

OLE DB şablonları uygulamasında, sütunları nullable olarak işaretlemezseniz, sağlayıcı bunların bir değer içermesi gerektiğini varsayar ve tüketicinin bu değerleri null değerleri göndermesine izin vermez.

Aşağıdaki örnek, güncelleştirmepv'de işlevin CUpdateCommand'da nasıl uygulandığını `CommonGetColInfo` gösterir (bkz. UpProvRS.cpp). Sütunların bu DBCOLUMNFLAGS_ISNULLABLE boşsütunlar için nasıl olduğunu unutmayın.

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

### <a name="default-values"></a>Varsayılan Değerler

NULL verilerinde olduğu gibi, değişen varsayılan değerlerle başa çıkma sorumluluğunuz da sizdedir.

Varsayılan `FlushData` ve `Execute` S_OK dönmektir. Bu nedenle, bu işlevi geçersiz kılmazsanız, değişiklikler başarılı görünür (S_OK döndürülür), ancak bunlar veri deposuna aktarılacak.

Örnekte `UpdatePV` (Rowset.h'de), `SetDBStatus` yöntem varsayılan değerleri aşağıdaki gibi işler:

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

### <a name="column-flags"></a>Sütun Bayrakları

Sütunlarınızda varsayılan değerleri destekliyorsanız, sağlayıcı sınıfı SchemaRowset\>sınıfındaki \<meta verileri kullanarak ayarlamanız gerekir. Ayarlayın. `m_bColumnHasDefault = VARIANT_TRUE`

Ayrıca, DBCOLUMNFLAGS numaralandırılmış türü kullanılarak belirtilen sütun bayraklarını ayarlama sorumluluğunuz da vardır. Sütun bayrakları sütun özelliklerini açıklar.

Örneğin, (Session.h'deki `CUpdateSessionColSchemaRowset` `UpdatePV` sınıfta) ilk sütun şu şekilde ayarlanır:

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

Bu kod, diğer şeylerin yanı sıra, sütunun varsayılan değeri 0'ı desteklediğini, yazılabilir olmasını ve sütundaki tüm verilerin aynı uzunluğa sahip olduğunu belirtir. Bir sütundaki verilerin değişken uzunluğa sahip olmasını istiyorsanız, bu bayrağı ayarlamazsınız.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcısı Oluşturma](creating-an-ole-db-provider.md)
