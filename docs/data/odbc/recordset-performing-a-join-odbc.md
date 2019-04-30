---
title: 'Kayıt kümesi: Birleşim gerçekleştirme (ODBC)'
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
ms.openlocfilehash: 9e589f00ec0512794d14accc6bb33c0e7adbd378
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397737"
---
# <a name="recordset-performing-a-join-odbc"></a>Kayıt kümesi: Birleşim gerçekleştirme (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

## <a name="what-a-join-is"></a>Ne bir birleşim

Birleştirme işlemi, genel bir veri erişim görev tek bir kayıt kümesi nesnesi kullanarak birden fazla tabloyu verilerle çalışmanıza olanak tanır. İki veya daha fazla tabloları birleştirme, her bir tablodaki sütunları içerebilir ancak uygulamanız için tek bir tablo olarak görünen bir kayıt kümesi üretir. Bazen birleştirme tüm sütunlardan tüm tabloları, ancak bazen SQL kullanan **seçin** JOIN yan tümcesinde her tablodaki sütunların yalnızca bir bölümünü kullanır. Veritabanı sınıfları salt okunur birleştirmeler güncellenebilir birleştirmeler destekler.

Birleştirilmiş bir tablodan sütun içeren kayıtları seçmek için aşağıdaki öğeler gerekir:

- Birleştirilen tüm tabloların adlarını içeren bir tablo listesi.

- Tüm katılımcı sütunlarının adlarını içeren bir sütun listesi. Aynı adı taşıyan ancak farklı tablolardan gelen sütunlar tablo adı tarafından yetkili olan.

- Bir filtre (SQL **burada** yan tümcesi) tabloları birleştirilir sütunları belirtir. Bu filtreyi alır "Table1.KeyCol Table2.KeyCol =" ve gerçekten birleşim gerçekleştirir.

İkiden fazla tabloları eşitleyerek birden çok çiftlerini sütunları, SQL anahtar sözcüğüyle birleştirilmiş her bir çifti tarafından aynı şekilde birleştirebilirsiniz **ve**.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Önceden Tanımlanmış Sorgu için Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[Kayıt kümesi: Tablo için Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Kayıt kümesi: Kayıt Kümesini Yeniden Sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)