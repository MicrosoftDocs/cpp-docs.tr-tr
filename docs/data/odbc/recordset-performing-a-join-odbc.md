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
ms.openlocfilehash: 7e8d42f2b96911cd57aca7c132b53ed7c10162be
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212803"
---
# <a name="recordset-performing-a-join-odbc"></a>Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

## <a name="what-a-join-is"></a>JOIN ne olur?

Ortak bir veri erişim görevi olan JOIN işlemi, tek bir kayıt kümesi nesnesi kullanarak birden fazla tablodan verilerle çalışmanıza olanak sağlar. İki veya daha fazla tablonun katılması, her tablodan sütun içerebilen, ancak uygulamanızda tek bir tablo olarak görünen bir kayıt kümesi oluşturur. Bazen JOIN tüm tablolardaki tüm sütunları kullanır, ancak bazen bir birleşimdeki SQL **Select** yan tümcesi her tablodaki sütunlardan yalnızca bazılarını kullanır. Veritabanı sınıfları Salt-okunabilir birleştirmeleri destekler ancak güncelleştirilemez birleştirmeleri destekler.

Birleştirilmiş tablolardan sütun içeren kayıtları seçmek için aşağıdaki öğeler gereklidir:

- Katılmakta olan tüm tabloların adlarını içeren bir tablo listesi.

- Tüm katılan sütunların adlarını içeren bir sütun listesi. Farklı tablolardan aynı ada sahip sütunlar, tablo adı tarafından nitelenir.

- Tabloların katıldığı sütunları belirten bir filtre (SQL **WHERE** yan tümcesi). Bu filtre, "Table1. KeyCol = Table2. KeyCol" formunu alır ve katılmayı gerçekten gerçekleştirir.

Birden çok sütun çifti elde ederek, her bir çiftin SQL anahtar sözcüğüne **ve ve '** a katılmış şekilde, ikiden fazla tablonun aynı şekilde katılmasını sağlayabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[Kayıt Kümesi: Tablo için Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)
