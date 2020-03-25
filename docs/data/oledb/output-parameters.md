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
ms.openlocfilehash: ece626eb7fbecae9b90321ccc2569607897cf520
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209865"
---
# <a name="output-parameters"></a>Çıktı Parametreleri

Saklı yordamın çağrılması, SQL komutu çalıştırmaya benzerdir. Temel fark, saklı yordamların çıkış parametrelerini (veya "outparameters") ve dönüş değerlerini kullanmasıdır.

Aşağıdaki saklı yordamda, ilk '? ' dönüş değeri (telefon) ve ikinci '? ', giriş parametresidir (ad):

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }"))
```

Parametre eşlemesinde ın ve out parametrelerini belirtirsiniz:

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter
END_PARAM_MAP()
```

Uygulamanız, saklı yordamlardan döndürülen çıktıyı işlemelidir. Farklı OLE DB sağlayıcıları, sonuç işleme sırasında çıkış parametrelerini ve dönüş değerlerini farklı zamanlarda döndürür. Örneğin, SQL Server (SQLOLEDB) için Microsoft OLE DB sağlayıcısı, saklı yordam tarafından döndürülen sonuç kümelerini aldıktan veya iptal edene kadar çıkış parametreleri ve dönüş kodları sağlamaz. Çıkış, sunucudan son TDS paketinde döndürülür.

## <a name="row-count"></a>Satır sayısı

OutParameters içeren bir saklı yordamı yürütmek için OLE DB tüketici şablonlarını kullanırsanız, satır sayısı, satır kümesini kapatıncaya kadar ayarlanamaz.

Örneğin, bir satır kümesi ve bir outparameter ile saklı yordam düşünün:

```sql
create procedure sp_test
   @_rowcount integer output
as
   select top 50 * from test
   @_rowcount = @@rowcount
return 0
```

`@_rowcount` outparameter, test tablosundan kaç satır döndürüldüğünü bildirir. Ancak, bu saklı yordam satır sayısını 50 olarak sınırlandırır. Örneğin, testte 100 satır varsa, satır sayısı 50 olacaktır (çünkü bu kod yalnızca en üstteki 50 satırları alır). Tabloda yalnızca 30 satır varsa, satır sayısı 30 olur. Değerini döndürmeden önce outparameter 'ı doldurmak için `Close` veya `CloseAll` çağırdığınızdan emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[Saklı Yordamları Kullanma](../../data/oledb/using-stored-procedures.md)
