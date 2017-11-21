---
title: "Satır kümesinde çoklu erişimci kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b50604feb05609e15fbc0f241d297c8661efa00b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-multiple-accessors-on-a-rowset"></a>Satır Kümesinde Çoklu Erişimci Kullanma
Birden çok erişimciler kullanmanız gereken üç temel senaryo vardır:  
  
-   **Birden çok okuma/yazma satır kümeleri.** Bu senaryoda, bir birincil anahtara sahip bir tablo sahip. Birincil anahtar dahil satırdaki tüm sütunlar kullanabilmek ister. Ayrıca, (birincil anahtar sütunu yazılamıyor çünkü) birincil anahtar dışındaki tüm sütunları verileri yazmak amacıyla kullanabilmek ister. Bu durumda, iki erişimci ayarlayın:  
  
    -   Erişimci 0 tüm sütunları içerir.  
  
    -   Erişimci 1 birincil anahtar dışındaki tüm sütunları içerir.  
  
-   **Performans.** Bu senaryoda, bir veya daha fazla sütun büyük miktarda veri, örneğin, grafik, ses veya video dosyaları içerir. Bir satıra taşıma her zaman, bunun nedenle uygulamanızın performansını düşürebilecek nedeni büyük olasılıkla sütun büyük veri dosyasıyla almak istediğiniz değil.  
  
     İlk erişimcisi büyük verilerle dışındaki tüm sütunları içeriyor ve veriler bu sütunları otomatik olarak alır ayrı erişimci ayarlayabilirsiniz; Otomatik erişimci budur. Yalnızca büyük veri içeren sütun ikinci erişimcisi alır, ancak bu verileri bu sütunu otomatik olarak almaz. Güncelleştirme veya isteğe bağlı olarak büyük veri getirme diğer yöntemleri olabilir.  
  
    -   Erişimci 0 otomatik erişimci olur; büyük verilerle dışındaki tüm sütunları alır.  
  
    -   Erişimci 1 otomatik erişimci değil; büyük veri sütununun alır.  
  
     Erişimci otomatik erişimci olup olmadığını belirlemek için otomatik bağımsız değişkeni kullanın.  
  
-   **Birden fazla ISequentialStream sütunu.** Bu senaryoda, birden çok sütun içeren sahip `ISequentialStream` veri. Bununla birlikte, her erişimci birine sınırlıdır `ISequentialStream` veri akışı. Bu sorunu çözmek için birkaç erişimci, her birini içeren ayarlayın `ISequentialStream` işaretçi.  
  
 Normalde erişimciler kullanarak oluşturduğunuz [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları. Aynı zamanda [db_accessor](../../windows/db-accessor.md) özniteliği. (Erişimciler daha ayrıntılı açıklanır [kullanıcı kayıtlarını](../../data/oledb/user-records.md).) Makrolar veya öznitelik erişimci otomatik veya otomatik olmayan erişimci olup olmadığını belirtin:  
  
-   Otomatik erişimci yöntemleri gibi taşıma **MoveFirst**, `MoveLast`, `MoveNext`, ve `MovePrev` tüm sütunları otomatik olarak belirtilen için verileri. Erişimci 0 otomatik erişimci olmalıdır.  
  
-   Siz açıkça bir yöntem gibi çağrısı tamamlanana kadar bir otomatik olmayan erişimcisi alma gerçekleşmez **güncelleştirme**, **Ekle**, **Fetch**, veya **Sil**. Yukarıda açıklanan senaryolarda her taşımada tüm sütunlarda almak istemeyebilirsiniz. Bir veya daha fazla sütun ayrı bir erişimci yerleştirin ve, aşağıda gösterildiği gibi bir otomatik olmayan erişimcisi hale getirebilirsiniz.  
  
 Aşağıdaki örnek, okuma ve yazma çoklu erişimci kullanma SQL Server pubs veritabanının işler tablosuna çoklu erişimci kullanır. Çoklu Erişimci en yaygın kullanımı budur; Yukarıdaki "birden çok okuma/yazma satır kümeleri" senaryosuna bakın.  
  
 Kullanıcı kayıt sınıfı aşağıdaki gibidir. İki erişimci ayarlar: erişimci 0 yalnızca birincil anahtar sütunu (ID) ve erişimci 1 diğer sütunları içerir.  
  
```  
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
  
 Ana kod aşağıdaki gibidir. Çağırma `MoveNext` veri erişimci 0 kullanarak birincil anahtar sütunu Kimliğinden otomatik olarak alır. Not nasıl **Ekle** birincil anahtar sütunu yazılmasını engellemek için son kullanan erişimci 1 yakın yöntemi.  
  
```  
int main(int argc, char* argv[])  
{  
    // Initalize COM  
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
            CTable<CAccessor<CJobs> > jobs;  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri kullanma](../../data/oledb/using-accessors.md)   
 [Kullanıcı kayıtları](../../data/oledb/user-records.md)