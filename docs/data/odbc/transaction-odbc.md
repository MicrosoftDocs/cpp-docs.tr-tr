---
description: 'Daha fazla bilgi edinin: Işlem (ODBC)'
title: İşlem (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets [C++], updating
- transactions [C++], MFC ODBC classes
- ODBC [C++], transactions
- recordsets [C++], updating
- databases [C++], transactions
- recordsets [C++], transactions
- ODBC recordsets [C++], transactions
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
ms.openlocfilehash: a7b769c37b58b34433939a18cb0dccf5fb4a798d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333866"
---
# <a name="transaction-odbc"></a>İşlem (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir işlem, bir [veri kaynağına](../../data/odbc/data-source-odbc.md) yönelik bir dizi güncelleştirmeyi gruplamak veya toplu olarak bir işlemdir; böylece işlem bir kez yapılır veya işlemi geri alırsanız hiçbiri işlenir. Bir işlem kullanmıyorsanız, veri kaynağında yapılan değişiklikler isteğe bağlı olarak yerine otomatik olarak uygulanır.

> [!NOTE]
> Tüm ODBC veritabanı sürücüleri işlemleri desteklemez. `CanTransact`Sürücünüzün belirli bir veritabanı için işlemleri destekleyip desteklemediğini öğrenmek için, [CDatabase](../../mfc/reference/cdatabase-class.md) veya [CRecordset](../../mfc/reference/crecordset-class.md) nesnenizin üye işlevini çağırın. `CanTransact`Veri kaynağının tam işlem desteği verip sunmadığını söylemez. Ayrıca, `CDatabase::GetCursorCommitBehavior` `CDatabase::GetCursorRollbackBehavior` `CommitTrans` `Rollback` Açık nesnedeki işlemin etkisini denetlemek için ve sonra ve ' i çağırmanız gerekir `CRecordset` .

`AddNew`Bir nesnenin ve üye işlevlerine yapılan çağrılar, ' i `Edit` `CRecordset` çağırdığınızda veri kaynağını hemen etkiler `Update` . `Delete` çağrılar de hemen etkili olur. Bunun aksine,,, ve için birden çok çağrıdan oluşan, `AddNew` `Edit` `Update` `Delete` ancak açıkça çağrılana kadar Yürütülmeyen bir işlem kullanabilirsiniz `CommitTrans` . Bir işlem kurarak, bunları geri alma özelliğini korurken bir dizi bu çağrı gerçekleştirebilirsiniz. Kritik bir kaynak kullanılamıyorsa veya başka bir koşul işlemin tamamının tamamlanmasını engelliyorsa, işlemi yürütmek yerine geri alabilirsiniz. Bu durumda, işleme ait değişikliklerden hiçbiri veri kaynağını etkilemez.

> [!NOTE]
> Şu anda, `CRecordset` toplu satır getirme uyguladıysanız sınıf veri kaynağına yönelik güncelleştirmeleri desteklemez. Bu,,, veya için çağrı yapamayacağı anlamına gelir `AddNew` `Edit` `Delete` `Update` . Ancak, güncelleştirmeleri gerçekleştirmek için size kendi işlevlerini yazabilir ve ardından bu işlevleri belirli bir işlem içinde çağırabilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
> Kayıt kümenizin etkilenmesine ek olarak işlemler, nesneniz ile ilişkili ODBC **HDBC** 'yi `CDatabase` ya da bu **HDBC** tabanlı bir ODBC **hstmt** 'yi kullandığınız sürece doğrudan yürütdiğiniz SQL deyimlerini etkiler.

İşlemler, aynı anda güncellenmesi gereken birden çok kayda sahip olduğunuzda özellikle faydalıdır. Bu durumda, en son güncelleştirme yapılmadan önce bir özel durum oluşursa, gibi yarı tamamlanmış bir işlemden kaçınmak istersiniz. Bu tür güncelleştirmeleri bir işlemde gruplandırmak, değişikliklerden kurtarma (geri alma) sağlar ve kayıtları ön işlem durumuna getirir. Örneğin, bir banka hesabından hesap B 'ye para aktardıysanız, her ikisi de bir ve B 'ye yatıranın doğru şekilde işlenmesi için başarılı olmalıdır veya tüm işlem başarısız olmalıdır.

Veritabanı sınıflarında, nesneler aracılığıyla işlem gerçekleştirirsiniz `CDatabase` . Bir `CDatabase` nesne bir veri kaynağıyla bağlantıyı temsil eder ve bu nesneyle ilişkili bir veya daha fazla kayıt `CDatabase` kümesi, veritabanı tabloları üzerinde kayıt kümesi üye işlevleri aracılığıyla çalışır.

> [!NOTE]
> Yalnızca bir düzey işlem desteklenir. İşlemleri iç içe veya bir işlem birden çok veritabanı nesnesine yayamazsınız.

Aşağıdaki konularda, işlemlerin nasıl gerçekleştirildiği hakkında daha fazla bilgi sağlanmaktadır:

- [İşlem: kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [İşlem: Işlemlerin güncelleştirmeleri etkilemesi (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
