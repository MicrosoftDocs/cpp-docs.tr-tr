---
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
ms.openlocfilehash: 49fc0e244dd4f63bd7a69d963ff2a9fbc00ddb6c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212608"
---
# <a name="transaction-odbc"></a>İşlem (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir işlem, bir [veri kaynağına](../../data/odbc/data-source-odbc.md) yönelik bir dizi güncelleştirmeyi gruplamak veya toplu olarak bir işlemdir; böylece işlem bir kez yapılır veya işlemi geri alırsanız hiçbiri işlenir. Bir işlem kullanmıyorsanız, veri kaynağında yapılan değişiklikler isteğe bağlı olarak yerine otomatik olarak uygulanır.

> [!NOTE]
>  Tüm ODBC veritabanı sürücüleri işlemleri desteklemez. Sürücünüzün belirli bir veritabanı için işlemleri destekleyip desteklemediğini öğrenmek için, [CDatabase](../../mfc/reference/cdatabase-class.md) veya [CRecordset](../../mfc/reference/crecordset-class.md) nesnenizin `CanTransact` üye işlevini çağırın. `CanTransact`, veri kaynağının tam işlem desteği sunmadığını söylemez. Ayrıca, `CommitTrans` ve `Rollback` sonra, açık `CRecordset` nesnesinde işlemin etkisini denetlemek için `CDatabase::GetCursorCommitBehavior` ve `CDatabase::GetCursorRollbackBehavior` çağırmanız gerekir.

`CRecordset` nesnenin `AddNew` ve `Edit` üye işlevlerine yapılan çağrılar `Update`çağırdığınızda veri kaynağını hemen etkiler. `Delete` çağrılar hemen de etkili olur. Buna karşılık, `AddNew`, `Edit`, `Update`ve `Delete`için birden çok çağrıdan oluşan bir işlem kullanabilirsiniz, ancak bu işlemler, `CommitTrans` açıkça çağrılana kadar gerçekleştirilmeyen ancak yürütülmemiş olur. Bir işlem kurarak, bunları geri alma özelliğini korurken bir dizi bu çağrı gerçekleştirebilirsiniz. Kritik bir kaynak kullanılamıyorsa veya başka bir koşul işlemin tamamının tamamlanmasını engelliyorsa, işlemi yürütmek yerine geri alabilirsiniz. Bu durumda, işleme ait değişikliklerden hiçbiri veri kaynağını etkilemez.

> [!NOTE]
>  Şu anda, sınıf `CRecordset` toplu satır getirme uyguladıysanız veri kaynağına yönelik güncelleştirmeleri desteklemez. Bu, `AddNew`, `Edit`, `Delete`veya `Update`için çağrı yapamayacağı anlamına gelir. Ancak, güncelleştirmeleri gerçekleştirmek için size kendi işlevlerini yazabilir ve ardından bu işlevleri belirli bir işlem içinde çağırabilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
>  Kayıt kümenizin etkilenmesine ek olarak, işlemler, `CDatabase` nesneniz ile ilişkili ODBC **HDBC** veya bu **HDBC**'YI temel alan bir ODBC **hstmt** 'YI kullandığınız sürece doğrudan yürütdiğiniz SQL deyimlerini etkiler.

İşlemler, aynı anda güncellenmesi gereken birden çok kayda sahip olduğunuzda özellikle faydalıdır. Bu durumda, en son güncelleştirme yapılmadan önce bir özel durum oluşursa, gibi yarı tamamlanmış bir işlemden kaçınmak istersiniz. Bu tür güncelleştirmeleri bir işlemde gruplandırmak, değişikliklerden kurtarma (geri alma) sağlar ve kayıtları ön işlem durumuna getirir. Örneğin, bir banka hesabından hesap B 'ye para aktardıysanız, her ikisi de bir ve B 'ye yatıranın doğru şekilde işlenmesi için başarılı olmalıdır veya tüm işlem başarısız olmalıdır.

Veritabanı sınıflarında `CDatabase` nesneleri aracılığıyla işlem gerçekleştirirsiniz. `CDatabase` nesnesi bir veri kaynağıyla bağlantıyı temsil eder ve bu `CDatabase` nesnesiyle ilişkili bir veya daha fazla kayıt kümesi, veritabanı tabloları üzerinde kayıt kümesi üye işlevleri aracılığıyla çalışır.

> [!NOTE]
>  Yalnızca bir düzey işlem desteklenir. İşlemleri iç içe veya bir işlem birden çok veritabanı nesnesine yayamazsınız.

Aşağıdaki konularda, işlemlerin nasıl gerçekleştirildiği hakkında daha fazla bilgi sağlanmaktadır:

- [İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [İşlem: İşlemlerin Güncelleştirmeleri Etkilemesi (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
