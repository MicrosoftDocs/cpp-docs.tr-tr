---
description: 'Hakkında daha fazla bilgi edinin: SQL Server ile Doğrulanabilen Derlemeler Kullanma (C++/CLı)'
title: SQL Server ile Doğrulanabilen Derlemeler Kullanma (C++/CLI)
ms.date: 10/17/2018
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
ms.openlocfilehash: b155fb0360fb373f5931f51de3af557d06858a71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204205"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>SQL Server ile Doğrulanabilen Derlemeler Kullanma (C++/CLI)

Dinamik bağlantı kitaplıkları (dll 'Ler) olarak paketlenmiş genişletilmiş saklı yordamlar, Visual C++ ile geliştirilmiş işlevler aracılığıyla SQL Server işlevselliği genişletmek için bir yol sağlar. Genişletilmiş saklı yordamlar dll 'Ler içinde işlev olarak uygulanır. İşlevlere ek olarak, genişletilmiş saklı yordamlar da [Kullanıcı tanımlı türleri](../cpp/classes-and-structs-cpp.md) ve toplama IŞLEVLERINI (Sum veya AVG gibi) tanımlayabilir.

İstemci genişletilmiş bir saklı yordamı yürüttüğünde, SQL Server Genişletilmiş saklı yordamla ilişkili DLL 'yi arar ve DLL 'yi yükler. SQL Server istenen genişletilmiş saklı yordamı çağırır ve belirtilen bir güvenlik bağlamı altında yürütür. Genişletilmiş saklı yordam sonuç kümelerini geçirir ve parametreleri sunucuya geri döndürür.

SQL Server, Transact-SQL (T-SQL) uzantıları sağlar ve SQL Server doğrulanabilir derlemeler yüklemenize olanak tanır. SQL Server izin kümesi, aşağıdaki güvenlik düzeylerine sahip güvenlik bağlamını belirtir:

- Kısıtlanmamış mod: kodu kendi riskiniz üzerinde çalıştırın; kodun, doğruıya türü güvenli olması gerekmez.

- Güvenli mod: verifili tür kodu çalıştırın; /clr: Safe ile derlendi.

> [!IMPORTANT]
> Visual Studio 2015 kullanım dışı ve Visual Studio 2017, **/clr: Pure** ve **/clr:** doğrulanabilir projelerin güvenli bir şekilde oluşturulmasını desteklemez. Doğrulanabilir koda ihtiyacınız varsa kodunuzu C# ' a çevirmeniz önerilir.

SQL Server bir doğrulanabilen derleme oluşturup yüklemek için Transact-SQL komutlarını derleme oluştur ve DERLEMEYI aşağıdaki gibi kullanın:

```sql
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH
  PERMISSION_SET <permissions>
DROP ASSEMBLY <assemblyName>
```

PERMISSION_SET komutu güvenlik bağlamını belirtir ve değerleri KıSıTLANMAMıŞ, GÜVENLI veya GENIŞLETILMIŞ olabilir.

Ayrıca, bir sınıftaki yöntem adlarına bağlamak için CREATE FUNCTION komutunu kullanabilirsiniz:

```sql
CREATE FUNCTION <FunctionName>(<FunctionParams>)
RETURNS returnType
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]
```

## <a name="example"></a>Örnek

Aşağıdaki SQL betiği (örneğin, "MyScript. SQL" olarak adlandırılır), SQL Server bir derlemeyi yükler ve bir sınıfın bir yöntemini kullanılabilir hale getirir:

```sql
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

SQL betikleri, SQL Sorgu Çözümleyicisi 'nde veya sqlcmd.exe yardımcı programıyla komut satırında etkileşimli olarak yürütülebilir. Aşağıdaki komut satırı sunucum öğesine bağlanır, varsayılan veritabanını kullanır, güvenilir bir bağlantı, MyScript. SQL girişleri ve çıktılar MyResult.txt kullanır.

```cmd
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)
