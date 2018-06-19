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
ms.openlocfilehash: f172eea3108771e129636e9aa95d721d45c99609
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33168652"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>SQL Server ile Doğrulanabilen Derlemeler Kullanma (C++/CLI)
Dinamik bağlantı kitaplıklarını (DLL'ler) paketlenmiş genişletilmiş saklı yordamlar Visual C++ ile geliştirilmiş işlevler aracılığıyla SQL Server işlevselliği genişletmek için bir yol sağlar. Genişletilmiş saklı yordamlar DLL'ler içinde işlevler olarak uygulanır. İşlevler ek olarak, genişletilmiş saklı yordamlar da tanımlayabilirsiniz [kullanıcı tanımlı türler](../cpp/classes-and-structs-cpp.md) ve [toplama işlevlerinin](http://msdn.microsoft.com/en-us/de255454-f45e-4281-81f9-bc61893ac5da) (örneğin, SUM veya AVG).  
  
 Bir istemci bir genişletilmiş saklı yordamı yürütüldüğünde, DLL için SQL Server aramaları genişletilmiş saklı yordamı ile ilişkili ve DLL'yi yükler. SQL Server istenen genişletilmiş saklı yordamı çağırır ve belirtilen güvenlik bağlamı altında çalışır. Geçişleri sonuç ayarlar ve parametreleri sunucuya geri döndürür genişletilmiş saklı yordamı.  
  
 [!INCLUDE[sqprsqlong](../dotnet/includes/sqprsqlong_md.md)] Transact-SQL (SQL Server'a doğrulanabilen derlemeler yükleme olanak tanımak için T-SQL) uzantıları sağlar. SQL Server izin kümesi güvenlik bağlamı aşağıdaki güvenlik düzeylerini belirtir:  
  
-   Kısıtlanmamış mod: kendi sorumluluğunuzdadır; kodu çalıştırma kod doğrulanabilir şekilde tür kullanımı uyumlu olması gerekmez.  
  
-   Güvenli mod: doğrulanabilir şekilde typesafe kodunu çalıştırın / CLR: safe ile derlenmiş.  
  
 Güvenli mod doğrulanabilir typesafe olması için yürütülen derlemeler gerektirir.  
  
 Oluşturmak ve SQL Server'a doğrulanabilir bir derleme yüklemek için aşağıdaki gibi derleme oluştur ve DROP ASSEMBLY Transact-SQL komutlarını kullanın:  
  
```  
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH   
  PERMISSION_SET <permissions>  
DROP ASSEMBLY <assemblyName>  
```  
  
 Permıssıon_set komutu güvenlik bağlamını belirtir ve KISITLAMASIZ, güvenli veya genişletilmiş değerlere sahip olabilir.  
  
 Ayrıca, bir sınıf yöntemi adlarında bağlamak için CREATE FUNCTION komutunu kullanabilirsiniz:  
  
```  
CREATE FUNCTION <FunctionName>(<FunctionParams>)  
RETURNS returnType  
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki SQL betiğini (örneğin, "MyScript.sql" adındaki) SQL Server'a bir derleme yükler ve bir sınıfın bir yöntem kullanılabilir hale getirir:  
  
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
  
 SQL komut dosyaları SQL Query Analyzer'da veya sqlcmd.exe yardımcı programı ile komut satırında etkileşimli olarak çalıştırılabilir. Aşağıdaki komut satırını için MyServer bağlanır, varsayılan veritabanı kullanan, güvenilen bir bağlantı, MyScript.sql girdileri ve MyResult.txt çıkarır.  
  
```  
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: safe'e geçiş (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)   
 [Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)