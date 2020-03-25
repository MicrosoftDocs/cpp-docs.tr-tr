---
title: Güncelleştirilebilir Sağlayıcı Oluşturma
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 2811cd56bdc87282b9d4395a9a79ba9b333dadee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211399"
---
# <a name="creating-an-updatable-provider"></a>Güncelleştirilebilir Sağlayıcı Oluşturma

Visual C++ , veri deposunu güncelleştirebilen (yazabilmesi) güncelleştirilebilir sağlayıcıları veya sağlayıcıları destekler. Bu konu, OLE DB şablonları kullanarak güncellenebilir sağlayıcıların nasıl oluşturulacağını açıklamaktadır.

Bu konu başlığı altında, bir çalışılabilir sağlayıcı ile başladığınız varsayılmaktadır. Güncelleştirilebilir bir sağlayıcı oluşturmak için iki adım vardır. İlk olarak sağlayıcının veri deposunda nasıl değişiklik yapacağına karar vermelisiniz; Özellikle, değişikliklerin hemen yapılıp yapılmayacağını veya bir Update komutu verilene kadar ertelenmesini sağlar. "[Sağlayıcıları güncelleştirilebilir hale getirme](#vchowmakingprovidersupdatable)" bölümünde, sağlayıcı kodunda yapmanız gereken değişiklikler ve ayarlar açıklanmaktadır.

Daha sonra, sağlayıcının tüketicinin talep edebildiği her şeyi desteklemek için tüm işlevleri içerdiğinden emin olmanız gerekir. Tüketici veri deposunu güncelleştirmek istiyorsa, sağlayıcının verileri veri deposuna devam eden bir kod içermesi gerekir. Örneğin, veri kaynağınızda bu tür işlemleri gerçekleştirmek için C çalışma zamanı kitaplığını veya MFC 'yi kullanabilirsiniz. "[Veri kaynağına yazma](#vchowwritingtothedatasource)" bölümünde veri kaynağına yazma, null ve varsayılan değerlerle ilgilenme ve sütun bayraklarını ayarlama işlemleri açıklanmaktadır.

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) güncelleştirilebilir sağlayıcıya bir örnektir. UpdatePV, Updatable desteğiyle birlikte MyProv ile aynıdır.

##  <a name="making-providers-updatable"></a><a name="vchowmakingprovidersupdatable"></a>Sağlayıcıları güncelleştirilebilir hale getirme

Bir sağlayıcıyı güncelleştirilebilir hale getirmek için gereken anahtar, sağlayıcınızın veri deposunda hangi işlemleri gerçekleştirmesini istediğinizi ve sağlayıcının bu işlemleri nasıl gerçekleştirmesini istediğinizi anlamaktır. Özellikle, önemli sorun, bir Update komutu verilene kadar veri deposundaki güncelleştirmelerin hemen veya ertelenmiş (toplu) olarak yapılıp yapılmayacağını belirtir.

Önce satır kümesi sınıfınıza `IRowsetChangeImpl` veya `IRowsetUpdateImpl` devralma kararı vermelisiniz. Uygulamayı seçtiğiniz bu seçeneklere bağlı olarak, üç yöntemin işlevselliği etkilenecektir: `SetData`, `InsertRows`ve `DeleteRows`.

- [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)'den devralma yaparsanız, bu üç yöntemi çağırmak veri deposunu hemen değiştirir.

- [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)'den devralma yaparsanız, `Update`, `GetOriginalData`veya `Undo`çağırana kadar Yöntemler veri deposuna değişiklikleri erteler. Güncelleştirme birkaç değişiklik içeriyorsa, bunlar Batch modunda gerçekleştirilir (toplu işleme değişikliklerinin önemli miktarda bellek yükü ekleyebileceğini unutmayın).

`IRowsetUpdateImpl` `IRowsetChangeImpl`türediğini unutmayın. Bu nedenle, `IRowsetUpdateImpl` özelliği ve toplu iş özelliğini değiştirmenize olanak sağlar.

### <a name="to-support-updatability-in-your-provider"></a>Sağlayıcınızdaki Güncelleştirilebilirliği desteklemek için

1. Satır kümesi sınıfınıza `IRowsetChangeImpl` veya `IRowsetUpdateImpl`öğesinden devralma. Bu sınıflar veri deposunu değiştirmek için uygun arabirimler sağlar:

   **IRowsetChange ekleme**

   Bu formu kullanarak devralma zincirinize `IRowsetChangeImpl` ekleyin:

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   Ayrıca, satır kümesi sınıfınıza `BEGIN_COM_MAP` bölümüne `COM_INTERFACE_ENTRY(IRowsetChange)` ekleyin.

   **IRowsetUpdate ekleniyor**

   Bu formu kullanarak devralma zincirinize `IRowsetUpdate` ekleyin:

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > `IRowsetChangeImpl` satırını devralma Zincirinizden kaldırmanız gerekir. Daha önce bahsedilen yönergedeki bu tek istisna, `IRowsetChangeImpl`için kod içermelidir.

1. COM haritanızda aşağıdakini ekleyin (`BEGIN_COM_MAP ... END_COM_MAP`):

   |  Uygularsanız   |           COM haritasına Ekle             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | Uygularsanız | Özellik kümesi eşlemesine Ekle |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. Komutunuz için, özellik kümesi haritanızda aşağıdakini ekleyin (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`):

   |  Uygularsanız   |                                             Özellik kümesi eşlemesine Ekle                                              |
   |---------------------|------------------------------------------------------------------------------------------------------------------|
   | `IRowsetChangeImpl` |                            `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`                             |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. Özellik kümesi haritalarınız içinde, aşağıdaki ayarların tümünü aşağıda göründükleri gibi de dahil etmelisiniz:

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

   Özellik kimlikleri ve değerleri için Atldb. h ' ye bakarak bu makro çağrılarında kullanılan değerleri bulabilirsiniz (atldb. h çevrimiçi belgelerden farklıysa, Atldb. h belgelerinin yerini alır).

   > [!NOTE]
   > `VARIANT_FALSE` ve `VARIANT_TRUE` ayarlarının çoğu OLE DB şablonları için gereklidir; OLE DB belirtimi, bunların okunabilir/yazılabilir olduğunu, ancak OLE DB şablonlarının yalnızca bir değeri destekleyebilecekleri bir değer belirtir.

   **IRowsetChangeImpl uygularsanız**

   `IRowsetChangeImpl`uygularsanız, sağlayıcınızda aşağıdaki özellikleri ayarlamanız gerekir. Bu özellikler öncelikle `ICommandProperties::SetProperties`aracılığıyla arabirimler istemek için kullanılır.

   - `DBPROP_IRowsetChange`: Bu, `DBPROP_IRowsetChange`otomatik olarak ayarlar.

   - `DBPROP_UPDATABILITY`: `IRowsetChange`üzerinde desteklenen yöntemleri belirten bir bit maskesi: `SetData`, `DeleteRows`veya `InsertRow`.

   - `DBPROP_CHANGEINSERTEDROWS`: Tüketici, yeni ekli satırlar için `IRowsetChange::DeleteRows` veya `SetData` çağırabilir.

   - `DBPROP_IMMOBILEROWS`: satır kümesi, ekli veya güncelleştirilmiş satırları yeniden sıramayacak.

   **IRowsetUpdateImpl uygularsanız**

   `IRowsetUpdateImpl`uygularsanız, daha önce listelenen `IRowsetChangeImpl` tüm özellikleri ayarlamaya ek olarak, aşağıdaki özellikleri sağlayıcınızda ayarlamanız gerekir:

   - `DBPROP_IRowsetUpdate`.

   - `DBPROP_OWNINSERT`: READ_ONLY ve VARIANT_TRUE olmalıdır.

   - `DBPROP_OWNUPDATEDELETE`: READ_ONLY ve VARIANT_TRUE olmalıdır.

   - `DBPROP_OTHERINSERT`: READ_ONLY ve VARIANT_TRUE olmalıdır.

   - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY ve VARIANT_TRUE olmalıdır.

   - `DBPROP_REMOVEDELETED`: READ_ONLY ve VARIANT_TRUE olmalıdır.

   - `DBPROP_MAXPENDINGROWS`.

   > [!NOTE]
   > Bildirimleri destekederseniz Ayrıca bazı diğer özelliklere de sahip olabilirsiniz; Bu liste için `IRowsetNotifyCP` bölümüne bakın.

##  <a name="writing-to-the-data-source"></a><a name="vchowwritingtothedatasource"></a>Veri kaynağına yazma

Veri kaynağından okumak için `Execute` işlevini çağırın. Veri kaynağına yazmak için `FlushData` işlevini çağırın. (Genel anlamda, Temizleme, bir tabloda veya dizinde disk dizinine yaptığınız değişiklikleri kaydetme anlamına gelir.)

```cpp
FlushData(HROW, HACCESSOR);
```

Satır tanıtıcısı (HROW) ve erişimci tanıtıcısı (HACCESSOR) bağımsız değişkenleri yazılacak bölgeyi belirtmenizi sağlar. Genellikle, her seferinde tek bir veri alanı yazarsınız.

`FlushData` yöntemi, verileri özgün olarak saklandığı biçimde yazar. Bu işlevi geçersiz kılamazsınız, sağlayıcınız doğru şekilde çalışır, ancak değişiklikler veri deposuna silinir.

### <a name="when-to-flush"></a>Ne zaman boşaltım

Sağlayıcı şablonları, verilerin veri deposuna yazılması gerektiğinde, Flushverilerini çağırır; Bu genellikle aşağıdaki işlevlere yapılan çağrıların sonucu olarak (her zaman değil) oluşur:

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows` (satıra eklenecek yeni veriler varsa)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>Nasıl çalıştığı

Tüketici, temizleme işlemi gerektiren bir çağrı yapar (örneğin, güncelleştirme) ve bu çağrı sağlayıcıya geçirilir ve her zaman aşağıdakileri yapar:

- Bir durum değeri her bağlandığında `SetDBStatus` çağırır.

- Sütun bayraklarını denetler.

- `IsUpdateAllowed`çağırır.

Bu üç adım güvenlik sağlamaya yardımcı olur. Ardından sağlayıcı `FlushData`çağırır.

### <a name="how-to-implement-flushdata"></a>FlushData nasıl uygulanır?

`FlushData`uygulamak için birkaç sorunu dikkate almanız gerekir:

Veri deposunun değişiklikleri işleyebileceği doğrulanıyor.

NULL değerleri işleme.

### <a name="handling-default-values"></a>Varsayılan değerler işleniyor.

Kendi `FlushData` yönteminizi uygulamak için şunları yapmanız gerekir:

- Satır kümesi Sınıfınıza gidin.

- Satır kümesi sınıfında şu bildirimi koyun:

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- `FlushData`bir uygulama sağlayın.

`FlushData` iyi bir uygulama yalnızca gerçekten güncellenen satırları ve sütunları depolar. En iyi duruma getirme için depolanmakta olan geçerli satırı ve sütunu öğrenmek için HROW ve HACCESSOR parametrelerini kullanabilirsiniz.

Genellikle en büyük zorluk kendi yerel veri deponuzla çalışmaktadır. Mümkünse şunları deneyin:

- Veri deponuza yazma yöntemini mümkün olduğunca basit tutun.

- NULL değerleri işleyin (isteğe bağlı ancak önerilir).

- Varsayılan değerleri işleyin (isteğe bağlı ancak önerilir).

En iyi şey, veri deponuzda NULL ve varsayılan değerler için belirtilen gerçek değerleri içermelidir. Bu verileri tahmin etmek için en iyi seçenektir. Aksi takdirde, NULL ve varsayılan değerlere izin vermeniz önerilir.

Aşağıdaki örnek, `FlushData` `UpdatePV` örneğindeki `RUpdateRowset` sınıfında nasıl uygulandığını gösterir (örnek kodda bkz. rowset. h):

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

Sağlayıcınızın değişiklikleri işlemesi için, önce veri deponuzda (örneğin, bir metin dosyası veya video dosyası) üzerinde değişiklik yapmanıza olanak sağlayan tesislere sahip olduğundan emin olmanız gerekir. Değilse, bu kodu sağlayıcı projesinden ayrı olarak oluşturmanız gerekir.

### <a name="handling-null-data"></a>NULL verileri işleme

Son kullanıcının NULL verileri gönderebilmesi mümkündür. Veri kaynağındaki alanlara NULL değerler yazdığınızda olası sorunlar olabilir. Şehir ve posta kodu değerlerini kabul eden bir sıra alma uygulaması düşünün; Her iki değeri de kabul edebilir, ancak bu durum teslimatı mümkün olmadığı için hiçbirini içermez. Bu nedenle, uygulamanız için anlamlı olan alanlarda bazı NULL değer birleşimlerini kısıtlamanız gerekir.

Sağlayıcı geliştiricisi olarak, bu verileri nasıl depolayacağınızı, veri deposundaki verileri nasıl okuyacağınızı ve Kullanıcı için nasıl belirtduğunuzu göz önünde bulundurmanız gerekir. Özellikle, veri kaynağındaki satır kümesi verilerinin veri durumunun nasıl değiştirileceğini düşünmeniz gerekir (örneğin, DataStatus = NULL). Bir Tüketici NULL değer içeren bir alana eriştiğinde döndürülecek değere karar verirsiniz.

UpdatePV örneğindeki koda bakın; bir sağlayıcının NULL verileri nasıl işleyebileceğini gösterir. UpdatePV öğesinde sağlayıcı, veri deposunda "NULL" dizesini yazarak NULL verileri depolar. Veri deposundan NULL verileri okuduğunda, bu dizeyi görür ve sonra bir NULL dize oluşturarak arabelleği boşaltır. Ayrıca, bu veri değeri boş ise DBSTATUS_S_ISNULL döndürdüğü `IRowsetImpl::GetDBStatus` geçersiz kılar.

### <a name="marking-nullable-columns"></a>Null yapılabilir sütunları işaretleme

Ayrıca, şema satır kümeleri (bkz. `IDBSchemaRowsetImpl`) uygularsanız, uygulamanız DBSCHEMA_COLUMNS satır kümesinde (genellikle CxxxSchemaColSchemaRowset tarafından olarak işaretlenir) sütunun null değer atanabilir olduğunu belirtmelidir.

Ayrıca, null olabilen tüm sütunların `GetColumnInfo`sürümünüzde DBCOLUMNFLAGS_ISNULLABLE değeri içerdiğini belirtmeniz gerekir.

OLE DB şablonları uygulamasında, sütunları null yapılabilir olarak işaretlemediğinizi, sağlayıcı bir değer içermesi gerektiğini varsayar ve tüketicinin bu değeri, null değerler göndermesini sağlar.

Aşağıdaki örnek, `CommonGetColInfo` işlevinin, UpdatePV içindeki CUpdateCommand (bkz. UpProvRS. cpp) içinde nasıl uygulandığını gösterir. Sütunlarda null yapılabilir sütunlar için bu DBCOLUMNFLAGS_ISNULLABLE nasıl sahip olduğunu aklınızda edin.

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

NULL verilerde olduğu gibi, değişen varsayılan değerlerle ilgilenme sorumluluğu vardır.

`FlushData` ve `Execute` varsayılan değer S_OK döndürmemelidir. Bu nedenle, bu işlevi geçersiz kılamazsınız, değişiklikler başarılı olarak görünür (S_OK döndürülür), ancak bunlar veri deposuna aktarılmaz.

`UpdatePV` örneğinde (rowset. h), `SetDBStatus` yöntemi varsayılan değerleri aşağıdaki şekilde işler:

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

Sütunlarınızın varsayılan değerlerini destekederseniz, \<sağlayıcı sınıfı\>SchemaRowset sınıfında meta verileri kullanarak ayarlamanız gerekir. `m_bColumnHasDefault = VARIANT_TRUE`ayarlayın.

Ayrıca, DBCOLUMNFLAGS numaralandırılmış türü kullanılarak belirtilen sütun bayraklarını ayarlama sorumluluğuna de sahipsiniz. Sütun bayrakları sütun özelliklerini tanımlıyor.

Örneğin, `UpdatePV` `CUpdateSessionColSchemaRowset` sınıfında (Session. h), ilk sütun bu şekilde ayarlanır:

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

Bu kod, diğer şeyler arasında, sütunun varsayılan değeri olan 0 ' ı desteklediğini, yazılabilir olduğunu ve sütundaki tüm verilerin aynı uzunluğa sahip olduğunu belirtir. Sütundaki verilerin değişken uzunlukta olmasını istiyorsanız bu bayrağı ayarlayamazsınız.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcısı Oluşturma](creating-an-ole-db-provider.md)
