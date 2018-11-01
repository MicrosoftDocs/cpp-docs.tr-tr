---
title: Saklı Yordamları Tanımlama
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
ms.openlocfilehash: 06618d1a468116855ccad149a150c0b621497f2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507958"
---
# <a name="defining-stored-procedures"></a>Saklı Yordamları Tanımlama

Bir saklı yordam çağırmadan önce öncelikle, kullanarak tanımlamalısınız [DEFINE_COMMAND](../../data/oledb/define-command.md) makrosu. Komut tanımladığınızda, soru işareti (?) parametreleriyle parametre işaretçisi olarak gösterin:

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{INSERT {name, phone} INTO shippers (?,?)}"))
```

Kod örnekleri bu konuda kullanılan söz dizimi (kullanımı küme ayraçları, vb.), SQL Server için özeldir. Saklı yordamlar kullandığınız sözdizimi, sağlayıcı göre değişebilir.

Ardından, parametre eşlemesinde komutta gerçekleştikleri sırada parametreleri listeleme komutta kullanılan parametreleri belirtin:

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param
END_PARAM_MAP()
```

Önceki örnekte, olduğu bir saklı yordam tanımlar. Genellikle, için etkili bir biçimde yeniden kod bir veritabanı kümesini adlara sahip önceden tanımlı saklı yordamlar gibi içeren `Sales by Year` veya `dt_adduserobject`. SQL Server Enterprise Manager'ı kullanarak tanımlarını görüntüleyebilirsiniz. Şu şekilde çağırın (yerleşimini *?* parametreleri saklı yordamın arabirimde bağlıdır):

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }"))
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }"))
```

Ardından, komut sınıfı bildirin:

```cpp
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>
```

Son olarak, saklı yordam çağırmak `OpenRowset` gibi:

```cpp
CSession m_session;

HRESULT OpenRowset()
{
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);
}
```

Ayrıca veritabanı özniteliğini kullanarak bir saklı yordam tanımlayabilirsiniz unutmayın [db_command](../../windows/db-command.md) gibi:

```cpp
db_command("{ ? = CALL dbo.dt_adduserobject }")
```

## <a name="see-also"></a>Ayrıca Bkz.

[Saklı Yordamları Kullanma](../../data/oledb/using-stored-procedures.md)