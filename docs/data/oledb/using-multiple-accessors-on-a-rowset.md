---
title: Satır Kümesinde Çoklu Erişimci Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
ms.openlocfilehash: d1ab314edeebedef4cff14cd5364a7ca16c74769
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033313"
---
# <a name="using-multiple-accessors-on-a-rowset"></a>Satır Kümesinde Çoklu Erişimci Kullanma

Çoklu Erişimci kullanmak gereken üç temel senaryo vardır:

- **Birden çok okuma/yazma satır kümeleri.** Bu senaryoda, bir birincil anahtar içeren bir tablo vardır. Satırın birincil anahtarı dahil olmak üzere tüm sütunları okuyabilmesini istiyorsunuz. Ayrıca, (birincil anahtar sütunu yazamadığınız) birincil anahtar dışındaki tüm sütunları verileri yazmak amacıyla yönetebilmek istiyorsunuz. Bu durumda, iki erişimci ayarlayın:

  - Erişimci 0 tüm sütunları içerir.

  - Erişimci 1 birincil anahtarı dışındaki tüm sütunları içerir.

- **Performans.** Bu senaryoda, çok miktarda veri, örneğin, grafik, ses veya video dosyaları bir veya daha fazla sütun var. Bir satıra taşıma her zaman bunu yapmanız bu nedenle, uygulamanızın performansını düşürebilecek çünkü büyük olasılıkla sütunu ile büyük veri dosyası, almak istediğiniz yok.

  İlk erişimci büyük ölçekli veri dışındaki tüm sütunları içerir ve bu verileri bu sütunları otomatik olarak alır ayrı erişimci ayarlayabilirsiniz. ilk erişimci otomatik erişimcisi ' dir. İkinci erişimcisi yalnızca büyük verileri tutan sütununu alır, ancak otomatik olarak bu sütunun veri almıyorsa. Güncelleştirme veya isteğe bağlı olarak büyük veri getirme diğer yöntemleri olabilir.

  - Erişimci 0 otomatik erişimci olduğu; büyük ölçekli veri dışındaki tüm sütunları alır.

  - Erişimci 1 otomatik erişimci değildir; büyük ölçekli veri sütunu alır.

  Otomatik bağımsız değişken, erişimci otomatik erişimci olup olmadığını belirtmek için kullanın.

- **Birden fazla ISequentialStream sütunu.** Bu senaryoda, seçtiğiniz birden fazla sütun tutan `ISequentialStream` veri. Ancak, her bir erişimci birle sınırlı olur `ISequentialStream` veri akışı. Bu sorunu çözmenin birkaç erişimci, her iki ayarlayın `ISequentialStream` işaretçi.

Normalde erişimciler kullanarak oluşturduğunuz [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları. Ayrıca [db_accessor](../../windows/db-accessor.md) özniteliği. (Erişimci daha ayrıntılı açıklanır [kullanıcı kayıtlarını](../../data/oledb/user-records.md).) Makrolar veya öznitelik erişimci otomatik ya da otomatik olmayan erişimci olup olmadığını belirtin:

- Otomatik erişimci yöntemlerini gibi hareket `MoveFirst`, `MoveLast`, `MoveNext`, ve `MovePrev` tüm sütunları otomatik olarak belirtilen için veri alma. Otomatik erişimci erişimci 0 olmalıdır.

- Siz açıkça bir yöntem çağırmak kadar bir otomatik olmayan erişimcisinde alma oluşmaz `Update`, `Insert`, `Fetch`, veya `Delete`. Yukarıda açıklanan senaryoda her hareket tüm sütunları almak istemeyebilirsiniz. Bir veya daha fazla sütun ayrı bir erişimci yerleştirin ve aşağıda gösterildiği gibi bir otomatik olmayan erişimcisi hale getirebilirsiniz.

Aşağıdaki örnek, okuma ve yazma çoklu erişimci kullanma SQL Server pubs veritabanı işleri tabloya çoklu erişimci kullanır. Bu örnekte, en yaygın çoklu erişimci kullanımıdır; Yukarıdaki "birden çok okuma/yazma satır kümeleri" senaryo bakın.

Kullanıcı kayıt sınıfı aşağıdaki gibidir. İki erişimci ayarlar: erişimci 0 yalnızca birincil anahtar sütunu (kimlik) ve 1 erişimci diğer sütunları içerir.

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

Ana kod aşağıdaki gibidir. Çağırma `MoveNext` otomatik olarak veri erişimci 0'ı kullanarak birincil anahtar sütunu kimliği alır. Not nasıl `Insert` yöntemi için birincil anahtar sütunu yazılmasını engellemek için son kullanan erişimci 1 yakın.

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

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)<br/>
[Kullanıcı Kayıtları](../../data/oledb/user-records.md)
