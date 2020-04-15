---
title: ODBC Veri Kaynağında Programlı Bir Tablo Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: 6cf26cad7fe39f374daf371902525087b446658c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358834"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Veri Kaynağı: Program Aracılığıyla ODBC Veri Kaynağında Tablo Oluşturma

Bu konu, sınıfın `ExecuteSQL` `CDatabase`üye işlevini kullanarak, create **TABLE** SQL deyimi içeren bir dize geçirerek, veri kaynağınız için nasıl bir tablo oluşturulutamamgerektiğini açıklar.

MFC'deki ODBC veri kaynakları hakkında genel bilgi için [bkz.](../../data/odbc/data-source-odbc.md) Konu [Veri Kaynağı: Bir ODBC Veri Kaynağının Programlı olarak yapılandırılarak](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) yapılandırılması, veri kaynakları oluşturmayı açıklar.

Veri kaynağını oluşturduğunuzda, üye işlevve CREATE `ExecuteSQL` **TABLE** SQL deyimini kullanarak kolayca tablo oluşturabilirsiniz. Örneğin, adında `CDatabase` `myDB`bir nesneniz varsa, tablo oluşturmak için aşağıdaki MFC kodunu kullanabilirsiniz:

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

Bu kod örneği, `myDB`Microsoft Access veri kaynağı bağlantısında "OFFICE" adlı bir tablo oluşturur; tabloda "OfficeID" ve "OfficeName" olmak için iki alan bulunmaktadır.

> [!NOTE]
> **CREATE TABLE** SQL deyiminde belirtilen alan türleri, kullanmakta olduğunuz ODBC sürücüsüne göre değişiklik gösterebilir. Microsoft Sorgu programı (Visual C++ 1.5 ile dağıtılır) bir veri kaynağı için hangi alan türlerinin kullanılabilerini keşfetmenin bir yoludur. Microsoft Sorgusu'nda **Dosya'yı**tıklatın, **Table_Definition**tıklatın, veri kaynağından bir tablo seçin ve **Tür** açılan kutusunda gösterilen türe bakın. Dizinoluşturmak için SQL sözdizimi de vardır.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)
