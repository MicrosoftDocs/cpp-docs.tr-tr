---
description: 'Hakkında daha fazla bilgi edinin: veri kaynağı: program aracılığıyla ODBC veri kaynağında tablo oluşturma'
title: ODBC veri kaynağında program aracılığıyla tablo oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: b195cc4fb81f1caed0b280c5df6a2032f4944ddf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155715"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Veri Kaynağı: Program Aracılığıyla ODBC Veri Kaynağında Tablo Oluşturma

Bu konuda, `ExecuteSQL` sınıfının üye işlevini kullanarak ve `CDatabase` işlevi bir **Create Table** SQL ifadesini içeren bir dize geçirerek veri kaynağınız için bir tablo oluşturma işlemi açıklanmaktadır.

MFC 'deki ODBC veri kaynakları hakkında genel bilgi için bkz. [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md). Konu [veri kaynağı: program aracılığıyla ODBC veri kaynağını yapılandırma](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) veri kaynakları oluşturmayı açıklar.

Veri kaynağı oluşturulduğunda, `ExecuteSQL` üye işlevini ve **Create Table** SQL ifadesini kullanarak tabloları kolayca oluşturabilirsiniz. Örneğin, `CDatabase` adlı bir nesneniz varsa `myDB` , bir tablo oluşturmak IÇIN aşağıdaki MFC kodunu kullanabilirsiniz:

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

Bu kod örneği, tarafından korunan Microsoft Access veri kaynağı bağlantısında "OFISLERI" adlı bir tablo oluşturur `myDB` ; tablo, "OfficeId" ve "OfficeName" olmak üzere iki alan içerir.

> [!NOTE]
> **Create Table** SQL ifadesinde belirtilen alan türleri, kullanmakta olduğunuz ODBC sürücüsüne göre değişiklik gösterebilir. Microsoft sorgu programı (Visual C++ 1,5 ile dağıtılır), bir veri kaynağı için hangi alan türlerinin kullanılabilir olduğunu keşfetmenin bir yoludur. Microsoft Query 'de **Dosya**' ya tıklayın, **Table_Definition**' a tıklayın, veri kaynağından bir tablo seçin ve **tür** Birleşik giriş kutusunda gösterilen türe bakın. Dizinler oluşturmak için SQL sözdizimi de mevcuttur.

## <a name="see-also"></a>Ayrıca bkz.

[Veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)
