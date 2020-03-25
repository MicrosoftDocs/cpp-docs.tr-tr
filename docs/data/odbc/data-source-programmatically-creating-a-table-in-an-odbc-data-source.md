---
title: ODBC veri kaynağında program aracılığıyla tablo oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: 25c975560d6a73ce67294d97830b2f5bec9cd635
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213284"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Veri Kaynağı: Program Aracılığıyla ODBC Veri Kaynağında Tablo Oluşturma

Bu konuda, `CDatabase`sınıfının `ExecuteSQL` üye işlevini kullanarak, işlevi bir **Create Table** SQL ifadesini içeren bir dize geçirerek veri kaynağınız için bir tablo oluşturma işlemi açıklanmaktadır.

MFC 'deki ODBC veri kaynakları hakkında genel bilgi için bkz. [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md). Konu [veri kaynağı: program aracılığıyla ODBC veri kaynağını yapılandırma](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) veri kaynakları oluşturmayı açıklar.

Veri kaynağı oluşturulduğunda, `ExecuteSQL` üye işlevini ve **Create Table** SQL ifadesini kullanarak kolayca tablo oluşturabilirsiniz. Örneğin, `myDB`adlı bir `CDatabase` nesneniz varsa, bir tablo oluşturmak için aşağıdaki MFC kodunu kullanabilirsiniz:

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

Bu kod örneği, `myDB`tarafından tutulan Microsoft Access veri kaynağı bağlantısında "OFISLERI" adlı bir tablo oluşturur; tablo, "OfficeId" ve "OfficeName" iki alanını içerir.

> [!NOTE]
>  **Create Table** SQL ifadesinde belirtilen alan türleri, kullanmakta olduğunuz ODBC sürücüsüne göre değişiklik gösterebilir. Microsoft Query programı (Visual C++ 1,5 ile dağıtılır), bir veri kaynağı için hangi alan türlerinin kullanılabilir olduğunu keşfetmenin bir yoludur. Microsoft Query 'de **Dosya**' ya tıklayın, **Table_Definition**' a tıklayın, veri kaynağından bir tablo seçin ve **tür** Birleşik giriş kutusunda gösterilen türe bakın. Dizinler oluşturmak için SQL sözdizimi de mevcuttur.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)
