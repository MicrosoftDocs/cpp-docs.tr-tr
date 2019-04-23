---
title: (MFC veri erişimi) varsayılan kodda yapabileceğiniz değişiklikler
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
ms.openlocfilehash: fc448ae1e13025a83b33386c2845bdf7bb4d5eec
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038641"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>(MFC veri erişimi) varsayılan kodda yapabileceğiniz değişiklikler

[MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md) içindeki tek bir tablonun tüm kayıtları seçen sizin için bir kayıt kümesi sınıfı yazar. Genellikle, bir veya daha aşağıdaki yollardan biriyle bu davranışı değiştirmek isteyeceksiniz:

- Bir filtre veya sıralama kayıt kümesi için ayarlayın. Bunu yapmak `OnInitialUpdate` kayıt kümesi nesnesi önce oluşturulan sonra kendi `Open` üye işlevi çağrılır. Daha fazla bilgi için [kayıt kümesi: Kayıtları filtreleme (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) ve [kayıt kümesi: Kayıtları sıralama (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).

- Kayıt kümesini parametreleştirme. Fiili çalışma zamanı parametre değeri, sonra filtre belirtin. Daha fazla bilgi için [kayıt kümesi: (ODBC) bir kayıt kümesini parametreleştirme](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

- Özelleştirilmiş bir SQL dizesi geçirmeniz [açık](../mfc/reference/crecordset-class.md#open) üye işlevi. Bu teknik ile gerçekleştirebileceğiniz bir açıklaması için bkz: [SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)