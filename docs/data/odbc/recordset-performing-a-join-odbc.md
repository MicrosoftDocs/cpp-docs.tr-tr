---
description: 'Daha fazla bilgi edinin: kayıt kümesi: JOIN gerçekleştirme (ODBC)'
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
ms.openlocfilehash: 1c7aa7bfb6925d9f7e916ddb6cd60061667d7859
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204517"
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
[Kayıt kümesi: önceden tanımlanmış sorgu için bir sınıf bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[Kayıt kümesi: tablo için sınıf bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Kayıt kümesi: bir kayıt kümesini yeniden sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)
