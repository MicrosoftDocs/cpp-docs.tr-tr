---
title: Varsayılan kodda yapabileceğiniz değişiklikler (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
ms.openlocfilehash: 7ea616caf176cd1e9e2f26bee1339640067b4e3e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213473"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>Varsayılan kodda yapabileceğiniz değişiklikler (MFC veri erişimi)

[MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md) sizin için tek bir tablodaki tüm kayıtları seçen bir kayıt kümesi sınıfı yazar. Genellikle, bu davranışı aşağıdaki yollarla bir veya daha fazla şekilde değiştirmek istersiniz:

- Kayıt kümesi için bir filtre veya sıralama düzeni ayarlayın. Bunu, kayıt kümesi nesnesi oluşturulduktan sonra, `Open` üye işlevi çağrılmadan önce `OnInitialUpdate`. Daha fazla bilgi için bkz. kayıt [kümesi: kayıtları filtreleme (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) ve [kayıt kümesi: KAYıTLARı sıralama (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).

- Kayıt kümesini parametreleştirin. Filtreden sonra gerçek çalışma zamanı parametre değerini belirtin. Daha fazla bilgi için bkz [. kayıt kümesi: bir kayıt kümesini parametrize etme (ODBC)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

- Özelleştirilmiş bir SQL dizesini [Açık](../mfc/reference/crecordset-class.md#open) üye işlevine geçirin. Bu teknikle neler yapabileceğinize ilişkin bir tartışma için bkz. [SQL: kayıt KÜMENIZIN sql deyiminizi özelleştirme (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümü kullanma](../data/using-a-record-view-mfc-data-access.md)
