---
title: "Çıktı parametreleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 061766f73b554895f8d7ad8952dc6172fd381169
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="output-parameters"></a>Çıktı Parametreleri
Saklı yordam çağırma SQL komutunu çağırmaya benzerdir. Ana saklı yordamlar çıktı parametreleri (veya "outparameters") kullanın ve dönüş değerleri farktır.  
  
 Aşağıdaki saklı yordamı, ilk '? 'dönüş değeri (telefon) ve ikinci Is'?' giriş parametresi (ad):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  
  
 Parametre eşlemesinde ve out parametreleri belirtin:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter  
END_PARAM_MAP()  
```  
  
 Uygulamanızı saklı yordamdan döndürülen çıkış işlemelidir. Farklı OLE DB sağlayıcıları çıktı parametrelerini ve dönüş sonucu işleme sırasında farklı zamanlarda dönüş değerleri. Örneğin, SQL Server (SQLOLEDB) için Microsoft OLE DB sağlayıcısı değil çıktı parametrelerini ve dönüş kodları kadar tüketici alınan veya saklı yordam tarafından döndürülen sonuç kümesini iptal sonra. Çıktı sunucudan son TDS paketinde döndürülür.  
  
## <a name="row-count"></a>Satır sayısı  
 OLE DB Tüketici Şablonları outparameters'ı olan bir saklı yordamı yürütmek için kullanırsanız, satır kapatana kadar satır sayısı ayarlanmadı.  
  
 Örneğin, bir satır kümesi ve outparameter olan bir saklı yordam göz önünde bulundurun:  
  
```  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 @_rowcount Outparameter'ı raporları satır sayısını gerçekte test tablosundan döndürülmedi. Ancak, bu saklı yordam en fazla 50 satır sayısını sınırlar. Örneğin, testte 100 satır olsaydı (Bu kod yalnızca ilk 50 satırları getireceğinden) satır sayısı 50 olur. Yalnızca 30 satır olsaydı tabloda, rowcount 30 olacaktı. Çağırmalısınız **Kapat** veya **CloseAll** değerini yakalamadan önce outparameter'ı doldurmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Saklı Yordamları Kullanma](../../data/oledb/using-stored-procedures.md)