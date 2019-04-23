---
title: Program aracılığıyla ODBC veri kaynağında tablo oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: 61d3f3e39362db27d1e3abc00fa3cb9ea82b86e2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028405"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Veri kaynağı: Program aracılığıyla ODBC veri kaynağında tablo oluşturma

Bu konu, verileriniz için bir tablo oluşturmak nasıl açıklar kullanarak kaynak `ExecuteSQL` sınıfının üye işlevinde `CDatabase`, işlev içeren bir dize olarak geçirerek bir **CREATE TABLE** SQL deyimi.

MFC ODBC veri kaynakları hakkında genel bilgi için bkz: [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md). Konu [veri kaynağı: Program aracılığıyla ODBC veri kaynağını yapılandırma](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) veri kaynağı oluşturmayı açıklar.

Kurulan veri kaynağına sahip olduğunuzda, kolayca kullanarak tablolar oluşturabilirsiniz `ExecuteSQL` üye işlevi ve **CREATE TABLE** SQL deyimi. Örneğin, tablonuz varsa bir `CDatabase` çağrılan nesne `myDB`, tablo oluşturmak için aşağıdaki MFC kodu kullanabilirsiniz:

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

Bu kod örneği tarafından korunan Microsoft Access veri kaynağı bağlantısı "OFİSLERİ" adlı bir tablo oluşturur `myDB`; iki alan "OfficeID" ve "OfficeName." tablo içerir

> [!NOTE]
>  Belirtilen alan türleri **CREATE TABLE** SQL deyimini kullandığınız ODBC sürücüsü göre farklılık gösterir. (Visual C++ 1.5 ile dağıtılan) Microsoft Query program hangi alan türlerinin bir veri kaynağı için kullanılabilir olduğunu öğrenmek için bir yoludur. Microsoft Query'de tıklayın **dosya**, tıklayın **Table_Definition'a**, bir veri kaynağından bir tablo seçin ve gösterilen türü bakmak **türü** birleşik giriş kutusu. Dizin oluşturmak için SQL söz dizimi de var.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)