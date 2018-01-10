---
title: "Parametreleştirilmiş sorgu verme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: parameter queries, running using CCommand class
ms.assetid: aedb0fce-52a4-4c97-a5c9-b2114be6c3b0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e016b6bb8c37fe24d9f1929f19904f17592e6f3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="issuing-a-parameterized-query"></a>Parametreleştirilmiş Sorgu Verme
Aşağıdaki örnek, bir Microsoft Access veritabanı tablosunda (30'dan büyük olan) bir geçerlilik süresi alan kayıtlarıyla alır basit bir Parametreli sorgu verir. Parametre desteklemek için kullanıcı kaydının ek bir eşlemesinin olması gerekir. Aşağıdaki kod bir ATL projesinde kullanır `CCommand` sınıfına `CTable` önceki örnekte kullanılan sınıf [basit bir satır kümesinde geçiş yapma](../../data/oledb/traversing-a-simple-rowset.md).  
  
```  
#include <atldbcli.h>  
  
CDataSource connection;  
CSession session;  
CCommand<CAccessor<CArtists> > artists;  
  
// Open the connection, session, and table, specifying authentication   
// using Windows NT integrated security. Hard-coding a password is a major   
// security weakness.  
connection.Open(CLSID_MSDASQL, "NWind", NULL, NULL,   
DBPROP_AUTH_INTEGRATED);  
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
```  
  
 Kullanıcı kaydı, `CArtists`, şöyle görünür:  
  
```  
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