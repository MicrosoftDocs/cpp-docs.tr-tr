---
title: Veri uygulamalarını taşıma | Microsoft Docs
ms.custom: ''
ms.date: 05/12/2017
ms.technology:
- devlang-cpp
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 8d10c285-c13f-4e6e-a09e-5ee0f2666b44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc789cb37b51f89022a83d1ba34bb67ae32a206e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391598"
---
# <a name="porting-data-applications"></a>Veri uygulamalarını taşıma
Yıllar içinde Visual C++ veritabanlarıyla çalışmak için birkaç yol sağlamıştır. 2011'de, SQL Server ürün yerel kod içinden erişmek için tercih edilen bir teknoloji olarak ODBC hizalama Microsoft duyurdu. ODBC sektör standardı olan ve bunu kullanarak, kodunuzun en fazla taşınabilirlik birden fazla platform ve veri kaynakları üzerinde elde edin. Çoğu SQL veritabanı ürün ve birçok NoSQL ürünleri ODBC desteği. MFC ODBC sarmalayıcı sınıflar veya bir üçüncü taraf C++ sarmalayıcı kitaplıktır kullanın veya doğrudan alt düzey ODBC API'ları çağırarak ODBC kullanabilirsiniz. 

OLE DB COM belirtimine göre alt düzey, yüksek performanslı bir API ve yalnızca Windows üzerinde desteklenir. OLE DB kullanırsanız, programınızın erişme [bağlı sunucuları](/sql/relational-databases/linked-servers/linked-servers-database-engine). ATL OLE DB Şablonları, özel OLE DB sağlayıcıları ve tüketici oluşturmayı daha kolay hale getirmek sağlar. OLE DB en son sürümü, SQL Yerel İstemcisi 11'de birlikte gelir.  

Eski uygulamanızı SQL Server'a bağlanmak için OLE DB ya da daha üst düzey ADO arabirimini kullanıyorsa ve bağlı sunucular eriştiğiniz değil, ODBC yakın gelecekte geçirmeyi düşünmelisiniz. Platformlar arası taşınabilirlik veya en son SQL Server özelliklerini gerektirmiyorsa, büyük olasılıkla ODBC (MSDASQL) için Microsoft OLE DB sağlayıcısı kullanabilirsiniz.  MSDASQL ODBC sürücüsü aracılığıyla veri kaynaklarına erişim için OLE DB ve ADO (hangi OLEDB dahili olarak kullanılır) üzerinde oluşturulan uygulamalar sağlar. Tüm çeviri katmanı olduğu gibi ile MSDASQL veritabanı performansı etkileyebilir. Etkisi signifant uygulamanız için olup olmadığını belirlemek için test etmeniz gerekir. MSDASQL Windows işletim sistemiyle birlikte gelir ve teknoloji 64-bit sürümünü eklemek için ilk Windows sürümleri, Windows Server 2008 ve Windows Vista SP1 değildir.

ODBC uygulamaları için SQL Native Client bileşeni (SNAC), tek bir DLL'nin OLE DB ve ODBC sürücülerini paketler kullanım dışı bırakılmıştır. SQL Server 2012 sürümünü SNAC (SQLNCLI11. Diğer SQL Server bileşenleri bağımlı olduğundan, DLL) SQL Server 2016 ile birlikte gelir. Ancak, SQL Server veya Azure SQL veritabanına ODBC üzerinden bağlanma yeni C++ uygulamalarını kullanması gereken [en son ODBC sürücüsü](https://docs.microsoft.com/en-us/sql/connect/odbc/download-odbc-driver-for-sql-server). Daha fazla bilgi için [SQL Server yerel istemcisi programlama](/sql/relational-databases/native-client/sql-server-native-client-programming)

C + kullanırsanız +/ CLI, devam edebilirsiniz ADO.NET olarak her zaman kullanın. Daha fazla bilgi için bkz. [veri erişim ADO.NET kullanma (C + +/ CLI)](../dotnet/data-access-using-adonet-cpp-cli.md), ve [Visual Studio'da verilere erişme](/visualstudio/data-tools/accessing-data-in-visual-studio).  
  
- ODBC sarmalayıcı sınıflarının yanı sıra, MFC ayrıca veri erişim nesneleri (DAO) sarmalayıcı sınıflar Access veritabanına bağlanmak için sağlar.  Ancak, DAO kullanımdan kalkmıştır. Herhangi bir kod temelinde `CDaoDatabase` veya `CDaoRecordset` yükseltilmelidir. 

Veri erişim teknolojileri üzerinde Microsoft Windows geçmişi hakkında daha fazla bilgi için bkz. [Microsoft Data Access Components (Wikipedia)](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).  

## <a name="see-also"></a>Ayrıca Bkz.  
 
[Visual C++'da Veri Erişimi](../data/data-access-in-cpp.md)<br/>
[Microsoft açık veritabanı bağlantısı (ODBC)](https://docs.microsoft.com/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
[Veri erişim teknolojileri yol haritası](https://msdn.microsoft.com/library/ms810810.aspx)  