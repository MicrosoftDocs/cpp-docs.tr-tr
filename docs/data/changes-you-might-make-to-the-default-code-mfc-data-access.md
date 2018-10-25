---
title: Varsayılan kodda (MFC veri erişimi) yaptığınız değişiklikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cee9316e2bd526465b6eed735df0bb0c6d5d6593
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072999"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>(MFC veri erişimi) varsayılan kodda yapabileceğiniz değişiklikler

[MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md) içindeki tek bir tablonun tüm kayıtları seçen sizin için bir kayıt kümesi sınıfı yazar. Genellikle, bir veya daha aşağıdaki yollardan biriyle bu davranışı değiştirmek isteyeceksiniz:

- Bir filtre veya sıralama kayıt kümesi için ayarlayın. Bunu yapmak `OnInitialUpdate` kayıt kümesi nesnesi önce oluşturulan sonra kendi `Open` üye işlevi çağrılır. Daha fazla bilgi için [kayıt kümesi: kayıtları filtreleme (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) ve [kayıt kümesi: Kayıtları sıralama (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).

- Kayıt kümesini parametreleştirme. Fiili çalışma zamanı parametre değeri, sonra filtre belirtin. Daha fazla bilgi için [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

- Özelleştirilmiş bir SQL dizesi geçirmeniz [açık](../mfc/reference/crecordset-class.md#open) üye işlevi. Bu teknik ile gerçekleştirebileceğiniz bir açıklaması için bkz. [SQL: özelleştirme Kümenizin SQL deyimini (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)