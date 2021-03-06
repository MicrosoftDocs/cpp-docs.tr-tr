---
description: 'Daha fazla bilgi edinin: güncelleştirilebilir sağlayıcı oluşturma'
title: Güncelleştirilebilir Sağlayıcı Oluşturma
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 948b50f5e49ca8288e5fcf1ada75ae07d4a8b39f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305422"
---
# <a name="creating-an-updatable-provider"></a>Güncelleştirilebilir Sağlayıcı Oluşturma

Visual C++, veri deposunu güncelleştirebilen (yazabilmesi) güncelleştirilebilir sağlayıcıları veya sağlayıcıları destekler. Bu konu, OLE DB şablonları kullanarak güncellenebilir sağlayıcıların nasıl oluşturulacağını açıklamaktadır.

Bu konu başlığı altında, bir çalışılabilir sağlayıcı ile başladığınız varsayılmaktadır. Güncelleştirilebilir bir sağlayıcı oluşturmak için iki adım vardır. İlk olarak sağlayıcının veri deposunda nasıl değişiklik yapacağına karar vermelisiniz; Özellikle, değişikliklerin hemen yapılıp yapılmayacağını veya bir Update komutu verilene kadar ertelenmesini sağlar. "[Sağlayıcıları güncelleştirilebilir hale getirme](#vchowmakingprovidersupdatable)" bölümünde, sağlayıcı kodunda yapmanız gereken değişiklikler ve ayarlar açıklanmaktadır.

Daha sonra, sağlayıcının tüketicinin talep edebildiği her şeyi desteklemek için tüm işlevleri içerdiğinden emin olmanız gerekir. Tüketici veri deposunu güncelleştirmek istiyorsa, sağlayıcının verileri veri deposuna devam eden bir kod içermesi gerekir. Örneğin, veri kaynağınızda bu tür işlemleri gerçekleştirmek için C Run-Time kitaplığını veya MFC 'yi kullanabilirsiniz. "[Veri kaynağına yazma](#vchowwritingtothedatasource)" bölümünde veri kaynağına yazma, null ve varsayılan değerlerle ilgilenme ve sütun bayraklarını ayarlama işlemleri açıklanmaktadır.

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) güncelleştirilebilir sağlayıcıya bir örnektir. UpdatePV, Updatable desteğiyle birlikte MyProv ile aynıdır.

## <a name="making-providers-updatable"></a><a name="vchowmakingprovidersupdatable"></a> Sağlayıcıları güncelleştirilebilir hale getirme

Bir sağlayıcıyı güncelleştirilebilir hale getirmek için gereken anahtar, sağlayıcınızın veri deposunda hangi işlemleri gerçekleştirmesini istediğinizi ve sağlayıcının bu işlemleri nasıl gerçekleştirmesini istediğinizi anlamaktır. Özellikle, önemli sorun, bir Update komutu verilene kadar veri deposundaki güncelleştirmelerin hemen veya ertelenmiş (toplu) olarak yapılıp yapılmayacağını belirtir.

Önce `IRowsetChangeImpl` `IRowsetUpdateImpl` satır kümesi sınıfınızdan mi yoksa bu sınıftan mi devralma gerektiğine karar vermelisiniz. Uygulamak istediğiniz bu seçeneklere bağlı olarak, üç yöntemin işlevselliği etkilenecektir: `SetData` , `InsertRows` ve `DeleteRows` .

- [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)'den devralma yaparsanız, bu üç yöntemi çağırmak veri deposunu hemen değiştirir.

- [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)'den devralma yaparsanız, veya çağrısı yapılıncaya kadar Yöntemler veri deposundaki değişiklikleri erteler `Update` `GetOriginalData` `Undo` . Güncelleştirme birkaç değişiklik içeriyorsa, bunlar Batch modunda gerçekleştirilir (toplu işleme değişikliklerinin önemli miktarda bellek yükü ekleyebileceğini unutmayın).

`IRowsetUpdateImpl`Öğesinden türetildiğine unutmayın `IRowsetChangeImpl` . Bu nedenle, `IRowsetUpdateImpl` özelliği ve toplu iş özelliğini değiştirmenize olanak sağlar.

### <a name="to-support-updatability-in-your-provider"></a>Sağlayıcınızdaki Güncelleştirilebilirliği desteklemek için

1. Satır kümesi sınıfınıza, veya ' den ' i alın `IRowsetChangeImpl` `IRowsetUpdateImpl` . Bu sınıflar veri deposunu değiştirmek için uygun arabirimler sağlar:

   **IRowsetChange ekleme**

   `IRowsetChangeImpl`Bu formu kullanarak devralma zincirinize ekleyin:

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   Ayrıca `COM_INTERFACE_ENTRY(IRowsetChange)` `BEGIN_COM_MAP` satır kümesi sınıfınıza bölümüne de ekleyin.

   **IRowsetUpdate ekleniyor**

   `IRowsetUpdate`Bu formu kullanarak devralma zincirinize ekleyin:

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > `IRowsetChangeImpl`Devralma Zincirinizden satırı kaldırmanız gerekir. Daha önce bahsedilen yönergedeki bu bir özel durum için kodu içermelidir `IRowsetChangeImpl` .

1. Aşağıdakileri COM haritanızda ( `BEGIN_COM_MAP ... END_COM_MAP` ) ekleyin:

   |  Uygularsanız   |           COM haritasına Ekle             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | Uygularsanız | Özellik kümesi eşlemesine Ekle |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. Komutunuz için, özellik kümesi haritanızda () aşağıdakini ekleyin `BEGIN_PROPSET_MAP ... END_PROPSET_MAP` :

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
   > `VARIANT_FALSE`OLE DB şablonları için çoğu ve `VARIANT_TRUE` ayarı gereklidir; OLE DB belirtimi, bunların okunabilir/yazılabilir olduğunu söyler, ancak OLE DB şablonları yalnızca bir değeri destekleyebilir.

   **IRowsetChangeImpl uygularsanız**

   Uygulamasını uygularsanız `IRowsetChangeImpl` , sağlayıcınızda aşağıdaki özellikleri ayarlamanız gerekir. Bu özellikler öncelikle aracılığıyla arabirim istemek için kullanılır `ICommandProperties::SetProperties` .

   - `DBPROP_IRowsetChange`: Bu otomatik olarak ayarlanır `DBPROP_IRowsetChange` .

   - `DBPROP_UPDATABILITY`: Üzerinde desteklenen yöntemleri belirten bir bit maskesi `IRowsetChange` : `SetData` , `DeleteRows` , veya `InsertRow` .

   - `DBPROP_CHANGEINSERTEDROWS`: Tüketici `IRowsetChange::DeleteRows` `SetData` Yeni ekli satırları çağırabilir veya kullanabilir.

   - `DBPROP_IMMOBILEROWS`: Satır kümesi, ekli veya güncelleştirilmiş satırları yeniden sıramayacak.

   **IRowsetUpdateImpl uygularsanız**

   Uygulamasını uygularsanız, `IRowsetUpdateImpl` daha önce listelenen tüm özellikleri ayarlamaya ek olarak, aşağıdaki özellikleri sağlayıcınızda ayarlamanız gerekir `IRowsetChangeImpl` :

   - `DBPROP_IRowsetUpdate`.

   - `DBPROP_OWNINSERT`: READ_ONLY ve VARIANT_TRUE olmalıdır.

   - `DBPROP_OWNUPDATEDELETE`: READ_ONLY ve VARIANT_TRUE olmalıdır.

   - `DBPROP_OTHERINSERT`: READ_ONLY ve VARIANT_TRUE olmalıdır.

   - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY ve VARIANT_TRUE olmalıdır.

   - `DBPROP_REMOVEDELETED`: READ_ONLY ve VARIANT_TRUE olmalıdır.

   - `DBPROP_MAXPENDINGROWS`.

   > [!NOTE]
   > Bildirimleri destekederseniz Ayrıca bazı diğer özelliklere de sahip olabilirsiniz; `IRowsetNotifyCP` Bu liste için bölümüne bakın.

## <a name="writing-to-the-data-source"></a><a name="vchowwritingtothedatasource"></a> Veri kaynağına yazma

Veri kaynağından okumak için, `Execute` işlevini çağırın. Veri kaynağına yazmak için `FlushData` işlevini çağırın. (Genel anlamda, Temizleme, bir tabloda veya dizinde disk dizinine yaptığınız değişiklikleri kaydetme anlamına gelir.)

```cpp
FlushData(HROW, HACCESSOR);
```

Satır tanıtıcısı (HROW) ve erişimci tanıtıcısı (HACCESSOR) bağımsız değişkenleri yazılacak bölgeyi belirtmenizi sağlar. Genellikle, her seferinde tek bir veri alanı yazarsınız.

`FlushData`Yöntemi, verileri özgün olarak saklandığı biçimde yazar. Bu işlevi geçersiz kılamazsınız, sağlayıcınız doğru şekilde çalışır, ancak değişiklikler veri deposuna silinir.

### <a name="when-to-flush"></a>Ne zaman boşaltım

Sağlayıcı şablonları, verilerin veri deposuna yazılması gerektiğinde, Flushverilerini çağırır; Bu genellikle aşağıdaki işlevlere yapılan çağrıların sonucu olarak (her zaman değil) oluşur:

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows` (satıra eklenecek yeni veriler varsa)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>Nasıl çalıştığı

Tüketici, temizleme işlemi gerektiren bir çağrı yapar (örneğin, güncelleştirme) ve bu çağrı sağlayıcıya geçirilir ve her zaman aşağıdakileri yapar:

- `SetDBStatus`Bir durum değeri bağladınız her seferinde çağırır.

- Sütun bayraklarını denetler.

- Çağırır `IsUpdateAllowed` .

Bu üç adım güvenlik sağlamaya yardımcı olur. Ardından sağlayıcı çağırır `FlushData` .

### <a name="how-to-implement-flushdata"></a>FlushData nasıl uygulanır?

Uygulamak için `FlushData` birkaç sorunu dikkate almanız gerekir:

Veri deposunun değişiklikleri işleyebileceği doğrulanıyor.

NULL değerleri işleme.

### <a name="handling-default-values"></a>Varsayılan değerler işleniyor.

Kendi yönteminizi uygulamak için şunları yapmanız `FlushData` gerekir:

- Satır kümesi Sınıfınıza gidin.

- Satır kümesi sınıfında şu bildirimi koyun:

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- Uygulamasının bir uygulamasını sağlayın `FlushData` .

İyi bir uygulama `FlushData` , yalnızca gerçekten güncellenen satırları ve sütunları depolar. En iyi duruma getirme için depolanmakta olan geçerli satırı ve sütunu öğrenmek için HROW ve HACCESSOR parametrelerini kullanabilirsiniz.

Genellikle en büyük zorluk kendi yerel veri deponuzla çalışmaktadır. Mümkünse şunları deneyin:

- Veri deponuza yazma yöntemini mümkün olduğunca basit tutun.

- NULL değerleri işleyin (isteğe bağlı ancak önerilir).

- Varsayılan değerleri işleyin (isteğe bağlı ancak önerilir).

En iyi şey, veri deponuzda NULL ve varsayılan değerler için belirtilen gerçek değerleri içermelidir. Bu verileri tahmin etmek için en iyi seçenektir. Aksi takdirde, NULL ve varsayılan değerlere izin vermeniz önerilir.

Aşağıdaki örnek örnekteki sınıfında nasıl `FlushData` uygulandığını gösterir `RUpdateRowset` `UpdatePV` (örnek kodda rowset. h öğesine bakın):

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

UpdatePV örneğindeki koda bakın; bir sağlayıcının NULL verileri nasıl işleyebileceğini gösterir. UpdatePV öğesinde sağlayıcı, veri deposunda "NULL" dizesini yazarak NULL verileri depolar. Veri deposundan NULL verileri okuduğunda, bu dizeyi görür ve sonra bir NULL dize oluşturarak arabelleği boşaltır. Ayrıca, `IRowsetImpl::GetDBStatus` Bu veri değeri boş ise DBSTATUS_S_ISNULL döndürdüğü bir geçersiz kılma içerir.

### <a name="marking-nullable-columns"></a>Null yapılabilir sütunları işaretleme

Ayrıca, şema satır kümeleri (bkz. `IDBSchemaRowsetImpl` ) uygularsanız, uygulamanız DBSCHEMA_COLUMNS satır kümesinde (genellikle CxxxSchemaColSchemaRowset tarafından olarak işaretlenir) sütunun null değer atanabilir olduğunu belirtmelidir.

Ayrıca, tüm null yapılabilir sütunların, sürümünüze DBCOLUMNFLAGS_ISNULLABLE değerini içermesini de belirtmeniz gerekir `GetColumnInfo` .

OLE DB şablonları uygulamasında, sütunları null yapılabilir olarak işaretlemediğinizi, sağlayıcı bir değer içermesi gerektiğini varsayar ve tüketicinin bu değeri, null değerler göndermesini sağlar.

Aşağıdaki örnek, bir işlevin, `CommonGetColInfo` UpdatePV Içindeki CUpdateCommand (bkz. UpProvRS. cpp) içinde nasıl uygulandığını gösterir. Sütunlarda null yapılabilir sütunlar için bu DBCOLUMNFLAGS_ISNULLABLE nasıl sahip olduğunu aklınızda edin.

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

`FlushData`Ve ' nin varsayılan ' i `Execute` S_OK döndürmemelidir. Bu nedenle, bu işlevi geçersiz kılamazsınız, değişiklikler başarılı olarak görünür (S_OK döndürülür), ancak bunlar veri deposuna aktarılmaz.

`UpdatePV`Örnekte (rowset. h), `SetDBStatus` yöntemi varsayılan değerleri aşağıdaki şekilde işler:

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

Sütunlarınızın varsayılan değerlerini destekederseniz, bunu SchemaRowset sınıfında meta verileri kullanarak ayarlamanız gerekir \<provider class\> . Ayarlayın `m_bColumnHasDefault = VARIANT_TRUE` .

Ayrıca, DBCOLUMNFLAGS numaralandırılmış türü kullanılarak belirtilen sütun bayraklarını ayarlama sorumluluğuna de sahipsiniz. Sütun bayrakları sütun özelliklerini tanımlıyor.

Örneğin, `CUpdateSessionColSchemaRowset` içindeki sınıfında `UpdatePV` (Session. h), ilk sütun bu şekilde ayarlanır:

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

[OLE DB sağlayıcısı oluşturma](creating-an-ole-db-provider.md)
