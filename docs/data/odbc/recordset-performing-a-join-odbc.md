---
title: 'Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
ms.openlocfilehash: 135992e7eebd56c985c24228370695f10ac6da3a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523945"
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