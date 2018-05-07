---
title: Program aracılığıyla ODBC veri kaynağında tablo oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5ea8ddc8e683c0e5f0681bdf98cbddca180e4023
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Veri Kaynağı: Program Aracılığıyla ODBC Veri Kaynağında Tablo Oluşturma
Bu konu, verileriniz için bir tablo oluşturmak nasıl açıklar kullanarak kaynak `ExecuteSQL` sınıfının üye işlevini `CDatabase`, işlev içeren bir dize geçirme bir **CREATE TABLE** SQL deyimi.  
  
 MFC içinde ODBC veri kaynakları hakkında genel bilgi için bkz: [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md). Konu [veri kaynağı: program aracılığıyla ODBC veri kaynağını yapılandırma](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) veri kaynağı oluşturmayı açıklar.  
  
 Oluşturulan veri kaynağına sahip olduğunuzda, tablolar kullanarak kolayca oluşturabilirsiniz `ExecuteSQL` üye işlevini ve **CREATE TABLE** SQL deyimi. Örneğin, sahip olduğunuz bir `CDatabase` adlı nesne `myDB`, bir tablo oluşturmak için aşağıdaki MFC kodu kullanabilirsiniz:  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 Bu kod örneği tarafından korunan Microsoft Access veri kaynağı bağlantısı içinde "OFİSLERİ" adlı bir tablo oluşturur `myDB`; iki alan "OfficeID" ve "OfficeName." tablo içerir  
  
> [!NOTE]
>  Belirtilen alan türleri **CREATE TABLE** SQL deyimi, kullanmakta olduğunuz ODBC sürücüsü göre farklılık. (Visual C++ 1.5 ile dağıtılan) Microsoft Query program hangi alan türlerinin bir veri kaynağı için kullanılabilir olduğunu öğrenmek için bir yoludur. Microsoft Query'de tıklatın **dosya**, tıklatın **Table_Definition'a**, bir veri kaynağından bir tablo seçin ve gösterilen türü bakmak **türü** birleşik giriş kutusu. SQL söz dizimi dizin oluşturmak için de bulunmaktadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)