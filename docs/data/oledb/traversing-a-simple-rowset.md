---
description: 'Daha fazla bilgi edinin: basit bir satır kümesinde geçiş yapma'
title: Basit Bir Satır Kümesinde Geçiş Yapma
ms.date: 10/19/2018
helpviewer_keywords:
- data access [C++], rowsets
- rowsets [C++], accessing
- simple rowsets
- OLE DB consumers [C++], database attributes
- accessors [C++], rowsets
ms.assetid: b45acf16-4029-429d-ab8d-b7fba98b9740
ms.openlocfilehash: f2e0c1f9647e168d8de2a10eaea6425bf9ad5a88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272636"
---
# <a name="traversing-a-simple-rowset"></a>Basit Bir Satır Kümesinde Geçiş Yapma

Aşağıdaki örnek, komutları içermeyen hızlı ve kolay veritabanı erişimini gösterir. Aşağıdaki tüketici kodu, bir ATL projesinde, ODBC için Microsoft OLE DB sağlayıcısı 'nı kullanarak Microsoft Access veritabanında bulunan *sanatçılar* adlı tablodaki kayıtları alır. Kod, Kullanıcı kayıt sınıfına dayalı bir erişimciye sahip bir [CTable](../../data/oledb/ctable-class.md) tablo nesnesi oluşturur `CArtists` . Bir bağlantı açar, bağlantıda bir oturum açar ve tabloyu oturum üzerinde açar.

```cpp
#include <atldbcli.h>
#include <iostream>

using namespace std;

int main()
{
    CDataSource connection;
    CSession session;
    CTable<CAccessor<CArtists>> artists;

    LPCSTR clsid; // Initialize CLSID_MSDASQL here
    LPCTSTR pName = L"NWind";

    // Open the connection, session, and table, specifying authentication
    // using Windows NT integrated security. Hard-coding a password is a major
    // security weakness.
    connection.Open(clsid, pName, NULL, NULL, DBPROP_AUTH_INTEGRATED);

    session.Open(connection);

    artists.Open(session, "Artists");

    // Get data from the rowset
    while (artists.MoveNext() == S_OK)
    {
       cout << artists.m_szFirstName;
       cout << artists.m_szLastName;
    }

    return 0;
}
```

Kullanıcı kaydı, aşağıdaki `CArtists` örneğe benzer şekilde görünür:

```cpp
class CArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_COLUMN_MAP(CArtists)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
   COLUMN_ENTRY(3, m_nAge)
END_COLUMN_MAP()
};
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)
