---
title: Saklı yordamları tanımlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1e03a5ae2e7c75d905216a6be92630376484d047
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="defining-stored-procedures"></a>Saklı Yordamları Tanımlama
Saklı yordam çağırmadan önce önce kullanarak tanımlamalısınız [DEFINE_COMMAND](../../data/oledb/define-command.md) makrosu. Komutu tanımladığınızda, soru işareti (?) parametrelerle parametre işaretçisi olarak gösterin:  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 Bu konuda kod örneklerinde kullanılan sözdizimi (kullanımı köşeli parantez vb.) SQL Server'a özgü olduğuna dikkat edin. Saklı yordamlar kullandığınız sözdizimi, kullandığınız sağlayıcıya göre değişebilir.  
  
 Ardından, parametre eşlemesinde komutta oluşma sırasına parametreleri listeleme komutta kullanılan parametreleri belirtin:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 Gidiyor olarak önceki örnek bir saklı yordam tanımlar. Genellikle, kod verimli kullanılmasını için bir dizi önceden tanımlanmış saklı yordamlar "Satış tarafından yıl" veya "dt_adduserobject." gibi adlara sahip bir veritabanı içerir. SQL Server Enterprise Manager kullanarak tanımlarını görüntüleyebilirsiniz. Aşağıdaki gibi çağrı (yerleşimini '?' parametreleri saklı yordamın arabirimde bağlıdır):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 Ardından, komut sınıfını bildirin:  
  
```  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>  
```  
  
 Son olarak, saklı yordam çağrısı `OpenRowset` gibi:  
  
```  
CSession m_session;  

HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);  
}  
```  
  
 Ayrıca veritabanı özniteliğini kullanarak bir saklı yordam tanımlayabilirsiniz unutmayın [db_command](../../windows/db-command.md) gibi:  
  
```  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Saklı Yordamları Kullanma](../../data/oledb/using-stored-procedures.md)