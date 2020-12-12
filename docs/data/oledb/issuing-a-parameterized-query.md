---
description: 'Daha fazla bilgi edinin: Parametreli sorgu verme'
title: Parametreleştirilmiş Sorgu Verme
ms.date: 10/19/2018
helpviewer_keywords:
- parameter queries, running using CCommand class
ms.assetid: aedb0fce-52a4-4c97-a5c9-b2114be6c3b0
ms.openlocfilehash: 2d3f03a359fe3ce079239fdcb9603b2d30299c33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317239"
---
# <a name="issuing-a-parameterized-query"></a>Parametreleştirilmiş Sorgu Verme

Aşağıdaki örnek, bir Microsoft Access veritabanındaki bir tablodan yaş alanı (30 ' dan büyük olan) kayıtları alan basit parametreli bir sorgu yayınlar. Parametresini desteklemek için, Kullanıcı kaydının ek bir eşlemesi olmalıdır. Aşağıdaki kod, bir ATL projesinde, `CCommand` `CTable` Önceki örnekte kullanılan sınıf yerine sınıfı kullanır ve [basit bir satır kümesine geçiş](../../data/oledb/traversing-a-simple-rowset.md)yapın.

```cpp
#include <atldbcli.h>
#include <iostream>

using namespace std;

int main()
{
    CDataSource connection;
    CSession session;
    CCommand<CAccessor<CArtists>> artists;
    LPCSTR clsid; // Initialize CLSID_MSDASQL here
    LPCTSTR pName = L"NWind";

    // Open the connection, session, and table, specifying authentication
    // using Windows NT integrated security. Hard-coding a password is a major
    // security weakness.
    connection.Open(clsid, pName, NULL, NULL, DBPROP_AUTH_INTEGRATED);

    session.Open(connection);

    // Set the parameter for the query
    artists.m_nAge = 30;
    artists.Open(session, "select * from artists where age > ?");

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

// Parameter binding map
BEGIN_PARAM_MAP(CArtists)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(1, m_nAge)
END_PARAM_MAP()
};
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)
