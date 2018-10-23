---
title: Parametreleştirilmiş sorgu verme | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- parameter queries, running using CCommand class
ms.assetid: aedb0fce-52a4-4c97-a5c9-b2114be6c3b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e410b0e849d71e8955229eca8a44bf4d3d3dbb91
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807958"
---
# <a name="issuing-a-parameterized-query"></a>Parametreleştirilmiş Sorgu Verme

Aşağıdaki örnek, bir Microsoft Access veritabanındaki bir tablodan (30'dan büyük olan) bir geçerlilik süresi alan kayıtlarla alır basit, parametreli bir sorgu verir. Parametre desteklemek için kullanıcı kaydı, ek bir harita olmalıdır. Aşağıdaki kod, kullanan bir ATL projesinde `CCommand` sınıfı yerine `CTable` önceki örnekte kullanılan sınıf [basit bir satır kümesinde geçiş yapma](../../data/oledb/traversing-a-simple-rowset.md).  
  
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
  
Kullanıcı kaydı, `CArtists`, bu örnek gibi görünür:  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)