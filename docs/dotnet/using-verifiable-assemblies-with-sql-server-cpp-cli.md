---
title: SQL Server ile doğrulanabilen derlemeler kullanma (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dfe64e627fd3ca37ab1e1d2d820cafaf3a6a4258
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43199971"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>SQL Server ile Doğrulanabilen Derlemeler Kullanma (C++/CLI)
Genişletilmiş saklı yordamlar, dinamik bağlantı kitaplıkları (DLL'ler), paketlenmiş işlevleri Visual C++ ile geliştirilmiş aracılığıyla SQL Server işlevselliği genişletmek için bir yol sağlar. Genişletilmiş saklı yordamlar, DLL'leri iç işlev olarak uygulanır. Ek İşlevler, genişletilmiş saklı yordamlar da tanımlayabilirsiniz [kullanıcı tanımlı türler](../cpp/classes-and-structs-cpp.md) ve [toplama işlevleri](https://msdn.microsoft.com/de255454-f45e-4281-81f9-bc61893ac5da) (örneğin, SUM veya AVG).  
  
 Bir istemci bir genişletilmiş saklı yordamı yürütüldüğünde, SQL Server aramaları DLL için genişletilmiş saklı yordamı ile ilişkili ve DLL'yi yükler. SQL Server, istenen genişletilmiş saklı yordam çağrıları ve belirtilen güvenlik bağlamı altında çalışır. Geçişleri sonucu ayarlar ve parametreler sunucuya geri döndürür genişletilmiş saklı yordamı.  
  
 SQL Server Transact-SQL (SQL Server ile doğrulanabilen derlemeler yüklemek, izin vermek için T-SQL) uzantıları sağlar. SQL Server izin kümesi, aşağıdaki güvenlik düzeyleri ile güvenlik bağlamını belirtir:  
  
-   Kısıtlanmamış modu: kendi sorumluluğunuzdadır; kod çalıştırma kod doğrulanabilir şekilde tür kullanımı uyumlu olması gerekmez.  
  
-   Güvenli mod: doğrulanabilir şekilde typesafe kodunu çalıştırın / CLR: safe ile derlenmiş.  
  
 Güvenli mod yürütülen derlemeler doğrulanabilir şekilde uyumlu olmasını gerektirir.  
  
 Oluşturma ve doğrulanabilir bir derleme SQL Server'a yükleme hakkında bilgi için CREATE ASSEMBLY ve DROP ASSEMBLY Transact-SQL komutlarını şu şekilde kullanın:  
  
```  
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH   
  PERMISSION_SET <permissions>  
DROP ASSEMBLY <assemblyName>  
```  
  
 Permıssıon_set komut güvenlik bağlamını belirtir ve SINIRSIZ, güvenli ve genişletilmiş değerlere sahip olabilir.  
  
 Ayrıca, bir sınıf, yöntem adları bağlamak için CREATE FUNCTION komutunu kullanabilirsiniz:  
  
```  
CREATE FUNCTION <FunctionName>(<FunctionParams>)  
RETURNS returnType  
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki SQL betiğini (örneğin, adlandırılmış "MyScript.sql"), SQL Server içinde bir derlemeyi yükler ve bir sınıfın bir yöntem kullanılabilir hale getirir:  
  
```  
-- Create assembly without external access  
drop assembly stockNoEA  
go  
create assembly stockNoEA  
from   
'c:\stockNoEA.dll'  
with permission_set safe  
  
-- Create function on assembly with no external access  
drop function GetQuoteNoEA  
go  
create function GetQuoteNoEA(@sym nvarchar(10))  
returns real  
external name stockNoEA:StockQuotes::GetQuote  
go  
  
-- To call the function  
select dbo.GetQuoteNoEA('MSFT')  
go  
```  
  
 SQL betikleri SQL Query Analyzer veya sqlcmd.exe yardımcı programını komut satırından etkileşimli olarak çalıştırılabilir. Aşağıdaki komut satırı için MyServer bağlanır, varsayılan veritabanı kullanır, güvenilir bir bağlantı kullanır, MyScript.sql girdileri ve MyResult.txt çıkarır.  
  
```  
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: safe'e geçiş (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)   
 [Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)