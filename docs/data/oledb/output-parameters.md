---
title: Çıktı Parametreleri
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
ms.openlocfilehash: 196c50ea62c3e3188b61a3b35a9e2752740c4ad5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283980"
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

## <a name="see-also"></a>Ayrıca bkz.

[Saklı Yordamları Kullanma](../../data/oledb/using-stored-procedures.md)