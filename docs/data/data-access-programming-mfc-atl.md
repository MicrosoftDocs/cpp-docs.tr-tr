---
title: "Veri erişim programlama (MFC-ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6a7d07941e15fad7d1b58560fb6efeb7d41c90d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="data-access-programming-mfcatl"></a>Veri erişimi (MFC/ATL) programlama
Yıllar içinde Visual C++ veritabanları ile çalışmak için çeşitli yollar sağlamıştır. 2011 ', SQL Server ürün yerel koddan erişmek için tercih edilen teknoloji olarak ODBC hizalama Microsoft duyurdu. ODBC sektör standardı olan ve bu aracı kullanarak, kodunuzun maksimum taşınabilirlik birden çok platformları ve veri kaynaklarını elde. Çoğu SQL veritabanı ürünleri ve birçok NoSQL ürünleri ODBC desteği. MFC ODBC sarmalayıcı sınıflar ya da üçüncü taraf C++ sarmalayıcı kitaplık kullanabilirsiniz veya alt düzey ODBC API'lerini doğrudan çağırmak ODBC kullanabilirsiniz. 

OLE DB COM belirtimine dayalı olarak bir alt düzey, yüksek performanslı API'dır ve yalnızca Windows üzerinde desteklenir. OLE DB programınızı erişme kullanırsanız [bağlı sunucuları](https://msdn.microsoft.com/library/ms188279.aspx). ATL özel OLE DB sağlayıcıları ve tüketicilerin oluşturmayı kolaylaştırmak OLE DB şablonları sağlar. OLE DB en son sürümünü SQL Native istemcisi 11 geliyordu.  

Eski uygulamanızı SQL Server'a bağlanmak için OLE DB veya üst düzey ADO arabirimini kullanır ve bağlantılı sunucular erişme değil, ODBC yakın gelecekte geçirme düşünmelisiniz. Platformlar arası taşınabilirlik veya en son SQL Server özellikleri gerektirmiyorsa, büyük olasılıkla ODBC (MSDASQL) için Microsoft OLE DB sağlayıcısı kullanabilirsiniz.  MSDASQL OLE DB ve ADO (hangi OLEDB dahili olarak kullanılır) bir ODBC sürücüsü aracılığıyla veri kaynaklarına erişim için oluşturulan uygulamaların sağlar. Tüm çeviri katmanında olduğu gibi MSDASQL veritabanı performansı etkileyebilir. Etkisi, uygulamanız için signifant olup olmadığını belirlemek için test etmeniz gerekir. MSDASQL Windows işletim sistemiyle birlikte gönderilir ve Windows Server 2008 ve Windows Vista SP1 teknolojisi 64-bit sürümünü dahil etmek için ilk Windows sürümlerinde demektir.

ODBC uygulamaları için SQL Native Client bileşeni (SNAC) hangi paketlerin tek bir DLL OLE DB ve ODBC sürücüleri kullanım dışı bırakılmıştır. SNAC (SQLNCLI11 SQL Server 2012 sürümü. Diğer SQL Server bileşenleri bağımlı olduğundan DLL) SQL Server 2016 ile birlikte gelir. Ancak, SQL Server veya Azure SQL veritabanı ODBC aracılığıyla bağlanan yeni C++ uygulamaları kullanması gereken [en son ODBC sürücüsü](https://docs.microsoft.com/en-us/sql/connect/odbc/download-odbc-driver-for-sql-server). Daha fazla bilgi için bkz: [SQL Server yerel istemci programlama](https://msdn.microsoft.com/en-us/library/ms130892.aspx)

C + kullanırsanız +/ CLI, devam edebilirsiniz ADO.NET olarak her zaman kullanın. Daha fazla bilgi için bkz: [veri erişimi kullanarak ADO.NET (C + +/ CLI)](../dotnet/data-access-using-adonet-cpp-cli.md), ve [Visual Studio'da veri erişimi](/visualstudio/data-tools/accessing-data-in-visual-studio).  
  
-   ODBC sarmalayıcı sınıflar ek olarak, MFC ayrıca veri erişim nesneleri (DAO) sarmalayıcı sınıflar Access veritabanına bağlanmak için sağlar.  Ancak, DAO kullanımdan kalkmıştır. CDaoDatabase veya CDaoRecordset göre herhangi bir kod yükseltilmelidir. 

Veri erişim teknolojileri Microsoft Windows geçmişi hakkında daha fazla bilgi için bkz: [Microsoft Data Access Components (Wikipedia)](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri erişimi](data-access-in-cpp.md) [Microsoft açık veritabanı bağlantısı (ODBC)](https://docs.microsoft.com/sql/odbc/microsoft-open-database-connectivity-odbc) [veri erişim teknolojileri yol haritası](https://msdn.microsoft.com/en-us/library/ms810810.aspx)