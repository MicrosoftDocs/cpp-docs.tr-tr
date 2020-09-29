---
title: Saklı Yordamları Tanımlama
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
ms.openlocfilehash: 47f68bcf5c62aa54cc5ee60de166e1085f5a3fc5
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500926"
---
# <a name="defining-stored-procedures"></a>Saklı Yordamları Tanımlama

Saklı yordam çağrılmadan önce, [DEFINE_COMMAND](./macros-and-global-functions-for-ole-db-consumer-templates.md#define_command) makrosunu kullanarak, önce onu tanımlamanız gerekir. Komutu tanımlarken parametre işaretçisi olarak bir soru işareti (?) ile parametreleri belirtin:

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{INSERT {name, phone} INTO shippers (?,?)}"))
```

Bu konudaki kod örneklerinde kullanılan sözdizimi (küme ayraçlarının kullanımı vb.) SQL Server özeldir. Saklı yordamlarınızda kullandığınız sözdizimi, kullandığınız sağlayıcıya göre değişiklik gösterebilir.

Ardından, parametre eşlemesinde, komutta kullanılan parametreleri belirtin ve parametreleri komutta gerçekleşdikleri sırada listeleme:

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param
END_PARAM_MAP()
```

Önceki örnekte olduğu gibi bir saklı yordam tanımlanmaktadır. Genellikle kodun verimli bir şekilde yeniden kullanılması için bir veritabanı, veya gibi adlara sahip önceden tanımlanmış bir saklı yordamlar kümesi `Sales by Year` içerir `dt_adduserobject` . Tanımlarını SQL Server Enterprise Manager kullanarak görüntüleyebilirsiniz. Bunları şu şekilde çağırabilirsiniz (öğesinin yerleşimi *?* Parametreler, saklı yordamın arabirimine bağlıdır):

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }"))
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }"))
```

Ardından komut sınıfını bildirin:

```cpp
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>
```

Son olarak, saklı yordamı `OpenRowset` aşağıdaki gibi çağırın:

```cpp
CSession m_session;

HRESULT OpenRowset()
{
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);
}
```

Ayrıca, veritabanı özniteliğini kullanarak [db_command](../../windows/attributes/db-command.md) aşağıdaki gibi bir saklı yordam tanımlayabileceğinizi unutmayın:

```cpp
db_command("{ ? = CALL dbo.dt_adduserobject }")
```

## <a name="see-also"></a>Ayrıca bkz.

[Saklı yordamları kullanma](../../data/oledb/using-stored-procedures.md)
