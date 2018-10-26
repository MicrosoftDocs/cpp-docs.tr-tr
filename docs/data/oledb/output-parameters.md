---
title: Çıkış parametresi | Microsoft Docs
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: d37cd1cd1facbdba1aeb4c8bc7f655bc3df954c0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073025"
---
# <a name="output-parameters"></a>Çıktı Parametreleri

Bir saklı yordamı çağırma SQL komutunu çalıştırmaya benzer. İkisi arasındaki temel fark, saklı yordamlar çıkış parametreleri (veya "outparameters") kullanın ve dönüş değerleri ' dir.

Aşağıdaki saklı yordamı, ilk '? 'dönüş değeri (phone) ve ikinci is'?' giriş parametresi (ad):

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }"))
```

Parametre haritasında ve out parametreleri belirtin:

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter
END_PARAM_MAP()
```

Uygulamanızı saklı yordamdan döndürülen çıkış işlemesi gerekir. OLE DB sağlayıcıları farklı çıkış parametrelerini ve dönüş sonucu işlenirken farklı zamanlarda dönüş değerleri. Örneğin, SQL Server (SQLOLEDB) için Microsoft OLE DB sağlayıcısı, çıkış parametrelerini değil ve tüketici alınan veya saklı yordam tarafından döndürülen sonuç kümesini iptal sonra kadar kodlarını döndürür. Çıktı, sunucudan son TDS paketinde döndürülür.

## <a name="row-count"></a>Satır sayısı

OLE DB Tüketici Şablonları outparameters sahip bir saklı yordamı yürütmek için kullandığınız satır kümesi kapatana kadar satır sayısı ayarlanmamış.

Örneğin, bir saklı yordam satır ve outparameter göz önünde bulundurun:

```sql
create procedure sp_test
   @_rowcount integer output
as
   select top 50 * from test
   @_rowcount = @@rowcount
return 0
```

`@_rowcount` Outparameter'ı raporları test tablosundan kaç satır döndürülmedi. Ancak, bu saklı yordamı, 50 satır sayısını sınırlar. Örneğin, test 100 satırı varsa, (Bu kod yalnızca ilk 50 satır getireceğinden) satır sayısı 50 olur. Varsa yalnızca 30 Satır tablosunda, satır sayısı 30'dur. Çağırdığınızdan emin olun `Close` veya `CloseAll` değerini yakalamadan önce outparameter'ı doldurmak için.

## <a name="see-also"></a>Ayrıca Bkz.

[Saklı Yordamları Kullanma](../../data/oledb/using-stored-procedures.md)