---
title: SQL Server ile Doğrulanabilen Derlemeler Kullanma (C++/CLI)
ms.date: 10/17/2018
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
ms.openlocfilehash: 27dec67cc0932a784cdd041ba346bb8c635b280d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747702"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>SQL Server ile Doğrulanabilen Derlemeler Kullanma (C++/CLI)

Genişletilmiş saklı yordamlar, dinamik bağlantı kitaplıkları (DLL'ler), paketlenmiş işlevleri Visual C++ ile geliştirilmiş aracılığıyla SQL Server işlevselliği genişletmek için bir yol sağlar. Genişletilmiş saklı yordamlar, DLL'leri iç işlev olarak uygulanır. Ek İşlevler, genişletilmiş saklı yordamlar da tanımlayabilirsiniz [kullanıcı tanımlı türler](../cpp/classes-and-structs-cpp.md) ve toplama işlevleri (örneğin, SUM veya AVG).

Bir istemci bir genişletilmiş saklı yordamı yürütüldüğünde, SQL Server aramaları DLL için genişletilmiş saklı yordamı ile ilişkili ve DLL'yi yükler. SQL Server, istenen genişletilmiş saklı yordam çağrıları ve belirtilen güvenlik bağlamı altında çalışır. Geçişleri sonucu ayarlar ve parametreler sunucuya geri döndürür genişletilmiş saklı yordamı.

SQL Server Transact-SQL (SQL Server ile doğrulanabilen derlemeler yüklemek, izin vermek için T-SQL) uzantıları sağlar. SQL Server izin kümesi, aşağıdaki güvenlik düzeyleri ile güvenlik bağlamını belirtir:

- Kısıtlanmamış modu: Kod, kendi risk altında çalıştırın; kod doğrulanabilir şekilde tür kullanımı uyumlu olması gerekmez.

- Güvenli mod: Uyumlu kod doğrulanabilir şekilde çalıştırın / CLR: safe ile derlenmiş.

> [!IMPORTANT]
> Visual Studio 2015 kullanım dışı ve Visual Studio 2017'yi desteklemez **/CLR: pure** ve **/CLR: safe** doğrulanabilir projeleri oluşturma. Doğrulanabilen kod gerekiyorsa, C# kodunuzda Çevir öneririz.

Oluşturma ve doğrulanabilir bir derleme SQL Server'a yükleme hakkında bilgi için CREATE ASSEMBLY ve DROP ASSEMBLY Transact-SQL komutlarını şu şekilde kullanın:

```sql
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH
  PERMISSION_SET <permissions>
DROP ASSEMBLY <assemblyName>
```

Permıssıon_set komut güvenlik bağlamını belirtir ve SINIRSIZ, güvenli ve genişletilmiş değerlere sahip olabilir.

Ayrıca, bir sınıf, yöntem adları bağlamak için CREATE FUNCTION komutunu kullanabilirsiniz:

```sql
CREATE FUNCTION <FunctionName>(<FunctionParams>)
RETURNS returnType
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]
```

## <a name="example"></a>Örnek

Aşağıdaki SQL betiğini (örneğin, adlandırılmış "MyScript.sql"), SQL Server içinde bir derlemeyi yükler ve bir sınıfın bir yöntem kullanılabilir hale getirir:

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

SQL betikleri SQL Query Analyzer veya sqlcmd.exe yardımcı programını komut satırından etkileşimli olarak çalıştırılabilir. Aşağıdaki komut satırı için MyServer bağlanır, varsayılan veritabanı kullanır, güvenilir bir bağlantı kullanır, MyScript.sql girdileri ve MyResult.txt çıkarır.

```cmd
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)
