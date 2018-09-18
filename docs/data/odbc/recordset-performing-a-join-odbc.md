---
title: 'Kayıt kümesi: bir birleşim gerçekleştirme (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e033a300a023b3460fb27ced7cd4bae99ebd0b92
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097918"
---
# <a name="recordset-performing-a-join-odbc"></a>Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.  
  
## <a name="what-a-join-is"></a>Ne bir birleşim  

Birleştirme işlemi, genel bir veri erişim görev tek bir kayıt kümesi nesnesi kullanarak birden fazla tabloyu verilerle çalışmanıza olanak tanır. İki veya daha fazla tabloları birleştirme, her bir tablodaki sütunları içerebilir ancak uygulamanız için tek bir tablo olarak görünen bir kayıt kümesi üretir. Bazen birleştirme tüm sütunlardan tüm tabloları, ancak bazen SQL kullanan **seçin** JOIN yan tümcesinde her tablodaki sütunların yalnızca bir bölümünü kullanır. Veritabanı sınıfları salt okunur birleştirmeler güncellenebilir birleştirmeler destekler.  
  
Birleştirilmiş bir tablodan sütun içeren kayıtları seçmek için aşağıdaki öğeler gerekir:  
  
- Birleştirilen tüm tabloların adlarını içeren bir tablo listesi.  
  
- Tüm katılımcı sütunlarının adlarını içeren bir sütun listesi. Aynı adı taşıyan ancak farklı tablolardan gelen sütunlar tablo adı tarafından yetkili olan.  
  
- Bir filtre (SQL **burada** yan tümcesi) tabloları birleştirilir sütunları belirtir. Bu filtreyi alır "Table1.KeyCol Table2.KeyCol =" ve gerçekten birleşim gerçekleştirir.  
  
İkiden fazla tabloları eşitleyerek birden çok çiftlerini sütunları, SQL anahtar sözcüğüyle birleştirilmiş her bir çifti tarafından aynı şekilde birleştirebilirsiniz **ve**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[Kayıt Kümesi: Tablo için Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)