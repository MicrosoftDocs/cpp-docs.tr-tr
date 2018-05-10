---
title: Veri uygulamaları taşıma | Microsoft Docs
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
ms.openlocfilehash: c148c805cb4ddc5e012e9de5e8e5f7e207f47dc3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="porting-data-applications"></a>Veri uygulamaları bağlantı noktası oluşturma
Yıllar içinde Visual C++ veritabanları ile çalışmak için çeşitli yollar sağlamıştır. 2011 ', SQL Server ürün yerel koddan erişmek için tercih edilen teknoloji olarak ODBC hizalama Microsoft duyurdu. ODBC sektör standardı olan ve bu aracı kullanarak, kodunuzun maksimum taşınabilirlik birden çok platformları ve veri kaynaklarını elde. Çoğu SQL veritabanı ürünleri ve birçok NoSQL ürünleri ODBC desteği. MFC ODBC sarmalayıcı sınıflar ya da üçüncü taraf C++ sarmalayıcı kitaplık kullanabilirsiniz veya alt düzey ODBC API'lerini doğrudan çağırmak ODBC kullanabilirsiniz. 

OLE DB COM belirtimine dayalı olarak bir alt düzey, yüksek performanslı API'dır ve yalnızca Windows üzerinde desteklenir. OLE DB programınızı erişme kullanırsanız [bağlı sunucuları](/sql/relational-databases/linked-servers/linked-servers-database-engine). ATL özel OLE DB sağlayıcıları ve tüketicilerin oluşturmayı kolaylaştırmak OLE DB şablonları sağlar. OLE DB en son sürümünü SQL Native istemcisi 11 geliyordu.  

Eski uygulamanızı SQL Server'a bağlanmak için OLE DB veya üst düzey ADO arabirimini kullanır ve bağlantılı sunucular erişme değil, ODBC yakın gelecekte geçirme düşünmelisiniz. Platformlar arası taşınabilirlik veya en son SQL Server özellikleri gerektirmiyorsa, büyük olasılıkla ODBC (MSDASQL) için Microsoft OLE DB sağlayıcısı kullanabilirsiniz.  MSDASQL OLE DB ve ADO (hangi OLEDB dahili olarak kullanılır) bir ODBC sürücüsü aracılığıyla veri kaynaklarına erişim için oluşturulan uygulamaların sağlar. Tüm çeviri katmanında olduğu gibi MSDASQL veritabanı performansı etkileyebilir. Etkisi, uygulamanız için signifant olup olmadığını belirlemek için test etmeniz gerekir. MSDASQL Windows işletim sistemiyle birlikte gönderilir ve Windows Server 2008 ve Windows Vista SP1 teknolojisi 64-bit sürümünü dahil etmek için ilk Windows sürümlerinde demektir.

ODBC uygulamaları için SQL Native Client bileşeni (SNAC) hangi paketlerin tek bir DLL OLE DB ve ODBC sürücüleri kullanım dışı bırakılmıştır. SNAC (SQLNCLI11 SQL Server 2012 sürümü. Diğer SQL Server bileşenleri bağımlı olduğundan DLL) SQL Server 2016 ile birlikte gelir. Ancak, SQL Server veya Azure SQL veritabanı ODBC aracılığıyla bağlanan yeni C++ uygulamaları kullanması gereken [en son ODBC sürücüsü](https://docs.microsoft.com/en-us/sql/connect/odbc/download-odbc-driver-for-sql-server). Daha fazla bilgi için bkz: [SQL Server yerel istemci programlama](/sql/relational-databases/native-client/sql-server-native-client-programming)

C + kullanırsanız +/ CLI, devam edebilirsiniz ADO.NET olarak her zaman kullanın. Daha fazla bilgi için bkz: [veri erişimi kullanarak ADO.NET (C + +/ CLI)](../dotnet/data-access-using-adonet-cpp-cli.md), ve [Visual Studio'da veri erişimi](/visualstudio/data-tools/accessing-data-in-visual-studio).  
  
-   ODBC sarmalayıcı sınıflar ek olarak, MFC ayrıca veri erişim nesneleri (DAO) sarmalayıcı sınıflar Access veritabanına bağlanmak için sağlar.  Ancak, DAO kullanımdan kalkmıştır. CDaoDatabase veya CDaoRecordset göre herhangi bir kod yükseltilmelidir. 

Veri erişim teknolojileri Microsoft Windows geçmişi hakkında daha fazla bilgi için bkz: [Microsoft Data Access Components (Wikipedia)](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'da Veri Erişimi](../data/data-access-in-cpp.md)  
 [Microsoft açık veritabanı bağlantısı (ODBC)](https://docs.microsoft.com/sql/odbc/microsoft-open-database-connectivity-odbc)  
 [Veri erişim teknolojileri yol haritası](https://msdn.microsoft.com/en-us/library/ms810810.aspx)  