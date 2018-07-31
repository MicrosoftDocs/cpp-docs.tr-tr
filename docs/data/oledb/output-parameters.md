---
title: Çıkış parametresi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ae742f27f7e2fd13de9acfc3c814b36c85e9e106
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339032"
---
# <a name="output-parameters"></a>Çıktı Parametreleri
Bir SQL komutu çağırmak için bir saklı yordamı çağırma benzerdir. İkisi arasındaki temel fark, saklı yordamlar çıkış parametreleri (veya "outparameters") kullanın ve dönüş değerleri ' dir.  
  
 Aşağıdaki saklı yordamı, ilk '? 'dönüş değeri (phone) ve ikinci is'?' giriş parametresi (ad):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  
  
 Parametre haritasında ve out parametreleri belirtin:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter  
END_PARAM_MAP()  
```  
  
 Uygulamanızı saklı yordamdan döndürülen çıkış işlemesi gerekir. OLE DB sağlayıcıları farklı çıkış parametrelerini ve dönüş sonucu işlenirken farklı zamanlarda dönüş değerleri. Örneğin, SQL Server (SQLOLEDB) için Microsoft OLE DB sağlayıcısı değil çıkış parametrelerini ve tüketici alınan veya saklı yordam tarafından döndürülen sonuç kümesini iptal sonra kadar kodlarını döndürür. Çıktı, sunucudan son TDS paketinde döndürülür.  
  
## <a name="row-count"></a>Satır sayısı  
 Satır kümesi kapatana kadar outparameters sahip bir saklı yordamı yürütmek için OLE DB Tüketici Şablonları kullanıyorsanız, satır sayısı ayarlanmadı.  
  
 Örneğin, bir saklı yordam satır ve outparameter göz önünde bulundurun:  
  
```sql  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 @_rowcount Outparameter'ı raporları kaç satır gerçekten test tablosundan döndürülmedi. Ancak, bu saklı yordam için en fazla 50 satır sayısını sınırlar. Örneğin, test 100 satırı varsa, (Bu kod yalnızca ilk 50 satır getireceğinden) satır sayısı 50 olur. Varsa yalnızca 30 Satır tablosunda, satır sayısı 30'dur. Çağırmalısınız `Close` veya `CloseAll` değerini yakalamadan önce outparameter'ı doldurmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Saklı Yordamları Kullanma](../../data/oledb/using-stored-procedures.md)