---
title: Satır Kümesinde Çoklu Erişimci Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
ms.openlocfilehash: 48772539b4dda9262a244506a36932d1e752949e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509404"
---
# <a name="using-multiple-accessors-on-a-rowset"></a>Satır Kümesinde Çoklu Erişimci Kullanma

Birden çok erişimci kullanmanız gereken üç temel senaryo vardır:

- **Birden çok okuma/yazma satır kümesi.** Bu senaryoda, birincil anahtarı olan bir tablonuz vardır. Birincil anahtar dahil olmak üzere satırdaki tüm sütunları okuyabilmek istiyorsunuz. Birincil anahtar (birincil anahtar sütununa yazamadığı için) dışındaki tüm sütunlara veri yazabiliyor olmanız da gerekir. Bu durumda, iki erişimci ayarlarsınız:

  - Erişimci 0 tüm sütunları içerir.

  - Erişimci 1, birincil anahtar dışındaki tüm sütunları içerir.

- **Mının.** Bu senaryoda, bir veya daha fazla sütunda büyük miktarda veri (örneğin, grafikler, ses veya video dosyaları) vardır. Bir satıra her geçtiğinizde, büyük olasılıkla sütunu büyük veri dosyası ile almak istemezsiniz, çünkü bunu yapmanız uygulamanızın performansını yavaşlatır.

  İlk erişimcinin, büyük veri içeren bir sütun hariç tüm sütunları içerdiği ve bu sütunlardan verileri otomatik olarak alan ayrı erişimciler ayarlayabilirsiniz; ilk erişimci otomatik erişimcidir. İkinci erişimci yalnızca büyük verileri tutan sütunu alır, ancak bu sütundan verileri otomatik olarak almaz. Diğer yöntemlerin büyük verileri isteğe bağlı olarak güncelleştirmesine veya uygulamasına getirebilirsiniz.

  - Erişimci 0 bir otomatik erişimdir; büyük verilerle bir hariç tüm sütunları alır.

  - Erişimci 1 otomatik erişimci değil; sütunu, büyük verilerle alır.

  Erişimcinin otomatik erişimci olup olmadığını belirtmek için Auto bağımsız değişkenini kullanın.

- **Birden çok ISequentialStream sütunu.** Bu senaryoda, verileri tutan birden fazla sütununuz vardır `ISequentialStream` . Ancak, her erişimci bir `ISequentialStream` veri akışıyla sınırlandırılmıştır. Bu sorunu çözmek için, her biri tek bir işaretçiye sahip birkaç erişimci ayarlayın `ISequentialStream` .

Genellikle [BEGIN_ACCESSOR](./macros-and-global-functions-for-ole-db-consumer-templates.md#begin_accessor) ve [end_accessor](./macros-and-global-functions-for-ole-db-consumer-templates.md#end_accessor) makrolarını kullanarak erişimciler oluşturursunuz. [Db_accessor](../../windows/attributes/db-accessor.md) özniteliğini de kullanabilirsiniz. (Erişimciler [Kullanıcı kayıtlarında](../../data/oledb/user-records.md)daha ayrıntılı olarak açıklanmıştır.) Makrolar veya öznitelik, bir erişimcinin otomatik mi yoksa otomatik olmayan bir erişimci mi olduğunu belirtir:

- Otomatik bir erişimcisinde,,, ve gibi `MoveFirst` yöntemleri `MoveLast` , `MoveNext` `MovePrev` belirtilen tüm sütunlara otomatik olarak alır. Erişimci 0 otomatik erişimci olmalıdır.

- Otomatik olmayan bir erişimcisinde,,, veya gibi bir yöntemi açıkça çağırana kadar alma gerçekleşmez `Update` `Insert` `Fetch` `Delete` . Yukarıda açıklanan senaryolarda, her bir taşımanın tüm sütunlarını almak istemeyebilirsiniz. Bir veya daha fazla sütunu ayrı bir erişimciye yerleştirebilir ve aşağıda gösterildiği gibi otomatik olmayan bir erişimci yapabilirsiniz.

Aşağıdaki örnek, birden çok erişimci kullanarak SQL Server pubs veritabanının işler tablosunu okumak ve yazmak için birden çok erişimci kullanır. Bu örnek, birden çok erişimciyi en yaygın kullanımı örneğidir; Yukarıdaki "çoklu okuma/yazma satır kümeleri" senaryosuna bakın.

Kullanıcı kayıt sınıfı aşağıdaki gibidir. İki erişimci ayarlar: erişimci 0 yalnızca birincil anahtar sütunu içerir (KIMLIK) ve erişimci 1 diğer sütunları içerir.

```cpp
class CJobs
{
public:
    enum {
        sizeOfDescription = 51
    };

    short nID;
    char szDescription[ sizeOfDescription ];
    short nMinLvl;
    short nMaxLvl;

    DWORD dwID;
    DWORD dwDescription;
    DWORD dwMinLvl;
    DWORD dwMaxLvl;

BEGIN_ACCESSOR_MAP(CJobs, 2)
    // Accessor 0 is the automatic accessor
    BEGIN_ACCESSOR(0, true)
        COLUMN_ENTRY_STATUS(1, nID, dwID)
    END_ACCESSOR()
    // Accessor 1 is the non-automatic accessor
    BEGIN_ACCESSOR(1, true)
        COLUMN_ENTRY_STATUS(2, szDescription, dwDescription)
        COLUMN_ENTRY_STATUS(3, nMinLvl, dwMinLvl)
        COLUMN_ENTRY_STATUS(4, nMaxLvl, dwMaxLvl)
    END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

Ana kod aşağıdaki gibidir. Çağırma `MoveNext` , erişimci 0 kullanarak birincil anahtar sütun kimliğinden verileri otomatik olarak alır. `Insert`Son görüntülenen yöntemin, birincil anahtar sütununa yazmayı önlemek için erişimci 1 ' i nasıl kullandığını aklınızda tutun.

```cpp
int main(int argc, char* argv[])
{
    // Initialize COM
    ::CoInitialize(NULL);

    // Create instances of the data source and session
    CDataSource source;
    CSession session;
    HRESULT hr = S_OK;

    // Set initialization properties
    CDBPropSet dbinit(DBPROPSET_DBINIT);
    dbinit.AddProperty(DBPROP_AUTH_USERID, OLESTR("my_user_id"));
    dbinit.AddProperty(DBPROP_INIT_CATALOG, OLESTR("pubs"));
    dbinit.AddProperty(DBPROP_INIT_DATASOURCE, OLESTR("(local)"));

    hr = source.Open("SQLOLEDB.1", &dbinit);
    if (hr == S_OK)
    {
        hr = session.Open(source);
        if (hr == S_OK)
        {
            // Ready to fetch/access data
            CTable<CAccessor<CJobs>> jobs;

            // Set properties for making the rowset a read/write cursor
            CDBPropSet dbRowset(DBPROPSET_ROWSET);
            dbRowset.AddProperty(DBPROP_CANFETCHBACKWARDS, true);
            dbRowset.AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
            dbRowset.AddProperty(DBPROP_IRowsetChange, true);
            dbRowset.AddProperty(DBPROP_UPDATABILITY,
                DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE |
                DBPROPVAL_UP_DELETE);

            hr = jobs.Open(session, "jobs", &dbRowset);
            if (hr == S_OK)
            {
                // Calling MoveNext automatically retrieves ID
                // (using accessor 0)
                while(jobs.MoveNext() == S_OK)
                   printf_s("Description = %s\n", jobs.szDescription);

                hr = jobs.MoveFirst();
                if (hr == S_OK)
                {
                    jobs.nID = 25;
                    strcpy_s(&jobs.szDescription[0],
                             jobs.sizeOfDescription,
                             "Developer");
                    jobs.nMinLvl = 10;
                    jobs.nMaxLvl = 20;

                    jobs.dwDescription = DBSTATUS_S_OK;
                    jobs.dwID = DBSTATUS_S_OK;
                    jobs.dwMaxLvl = DBSTATUS_S_OK;
                    jobs.dwMinLvl = DBSTATUS_S_OK;

                    // Insert method uses accessor 1
                    // (to avoid writing to the primary key column)
                    hr = jobs.Insert(1);
                }
                jobs.Close();
            }
            session.Close();
        }
        source.Close();
    }

    // Uninitialize COM
    ::CoUninitialize();
    return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)<br/>
[Kullanıcı kayıtları](../../data/oledb/user-records.md)
