---
description: Daha fazla bilgi için bkz. varsayılan kodda yapabileceğiniz değişiklikler (MFC veri erişimi)
title: Varsayılan kodda yapabileceğiniz değişiklikler (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
ms.openlocfilehash: 431144eeaf7ef0a2413e4d9e3931016c2505d338
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181455"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>Varsayılan kodda yapabileceğiniz değişiklikler (MFC veri erişimi)

[MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md) sizin için tek bir tablodaki tüm kayıtları seçen bir kayıt kümesi sınıfı yazar. Genellikle, bu davranışı aşağıdaki yollarla bir veya daha fazla şekilde değiştirmek istersiniz:

- Kayıt kümesi için bir filtre veya sıralama düzeni ayarlayın. Bu işlemi `OnInitialUpdate` , kayıt kümesi nesnesi oluşturulduktan sonra, ancak `Open` üye işlevi çağrılmadan önce yapın. Daha fazla bilgi için bkz. kayıt [kümesi: kayıtları filtreleme (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) ve [kayıt kümesi: KAYıTLARı sıralama (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).

- Kayıt kümesini parametreleştirin. Filtreden sonra gerçek çalışma zamanı parametre değerini belirtin. Daha fazla bilgi için bkz [. kayıt kümesi: bir kayıt kümesini parametrize etme (ODBC)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

- Özelleştirilmiş bir SQL dizesini [Açık](../mfc/reference/crecordset-class.md#open) üye işlevine geçirin. Bu teknikle neler yapabileceğinize ilişkin bir tartışma için bkz. [SQL: kayıt KÜMENIZIN sql deyiminizi özelleştirme (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümü kullanma](../data/using-a-record-view-mfc-data-access.md)
