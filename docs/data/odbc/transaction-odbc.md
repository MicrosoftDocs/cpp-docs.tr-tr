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
ms.openlocfilehash: 56629f8c5ff74aff4e0df589cda1e7b988fb5fd3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376408"
---
# <a name="transaction-odbc"></a>İşlem (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Hareket, bir [veri kaynağına](../../data/odbc/data-source-odbc.md) yapılan bir dizi güncelleştirmeyi gruplandırmanın veya toplu iş yapmanın bir yoludur, böylece hareketi geri alırsanız, tümü aynı anda veya hiç işlenmez. Bir hareket kullanmazsanız, veri kaynağındaki değişiklikler isteğe bağlı olarak taahhüt edilmek yerine otomatik olarak işlenir.

> [!NOTE]
> Tüm ODBC veritabanı sürücüleri hareketleri desteklemez. Sürücünüzün `CanTransact` belirli bir veritabanı için hareketleri destekleyip desteklemediğini belirlemek için [CDatabase](../../mfc/reference/cdatabase-class.md) veya [CRecordset](../../mfc/reference/crecordset-class.md) nesnenizin üye işlevini arayın. Veri `CanTransact` kaynağının tam işlem desteği sağlayıp sağlamadığını size söylemeyenleri unutmayın. Ayrıca aramanız `CDatabase::GetCursorCommitBehavior` `CDatabase::GetCursorRollbackBehavior` ve `CommitTrans` `Rollback` sonra ve hareketin açık `CRecordset` nesne üzerindeki etkisini kontrol etmelisiniz.

Bir `AddNew` `CRecordset` nesnenin `Edit` ve üye işlevlerine yapılan çağrılar, `Update`'yi çağırdığınızda veri kaynağını hemen etkiler. `Delete`aramalar da hemen yürürlüğe girer. Buna karşılık, birden çok çağrıdan `AddNew` `Edit` `Update` `Delete`oluşan ve açıkça çağırana `CommitTrans` kadar gerçekleştirilmeyen ancak taahhüt edilmeyecek bir işlem kullanabilirsiniz. Bir işlem oluşturarak, bu tür çağrıları geri alma yeteneğini korurken bir dizi çağrıyı gerçekleştirebilirsiniz. Kritik bir kaynak kullanılamıyorsa veya başka bir koşul tüm işlemin tamamlanmasını engelliyorsa, hareketi işlemek yerine geri alabilirsiniz. Bu durumda, harekete ait değişikliklerin hiçbiri veri kaynağını etkilemez.

> [!NOTE]
> Şu anda, toplu satır alma uyguladıysanız sınıf `CRecordset` veri kaynağıgüncelleştirmelerini desteklemez. Bu, , `AddNew`, `Edit` `Delete`, veya `Update`. Ancak, güncelleştirmeleri gerçekleştirmek için kendi işlevlerini yazabilir ve ardından belirli bir işlem deki bu işlevleri arayabilirsiniz. Toplu satır alma hakkında daha fazla bilgi için bkz: [Recordset: Toplu Olarak Kayıtları Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
> Kayıt setinizi etkilemenin yanı sıra, `CDatabase` hareketler nesnenizle ilişkili ODBC **HDBC'yi** veya bu **HDBC'ye**dayalı bir ODBC **HSTMT'yi** kullandığınız sürece doğrudan yürüttüğünüz SQL ekstrelerini etkiler.

Aynı anda güncelleştirilmesi gereken birden çok kaydınız olduğunda hareketler özellikle yararlıdır. Bu durumda, son güncelleştirme yapılmadan önce bir özel durum atılırsa gerçekleşebileceği gibi, yarı tamamlanmış bir işlemden kaçınmak istiyorsunuz. Bu tür güncelleştirmeleri bir işlem de gruplandırmak, değişikliklerden kurtarma (geri alma) sağlar ve kayıtları ön işlem durumuna döndürür. Örneğin, bir banka A hesabından B hesabına para aktarırsa, hem A'dan para çekme hem de B'ye para yatırma işleminin başarılı olması gerekir veya tüm işlem başarısız olmalıdır.

Veritabanı sınıflarında, nesneler üzerinden `CDatabase` hareketleri gerçekleştirirsiniz. Bir `CDatabase` nesne bir veri kaynağına olan bağlantıyı temsil eder `CDatabase` ve bu nesneyle ilişkili bir veya daha fazla kayıt kümesi, kayıt kümesi üye işlevleri aracılığıyla veritabanıtablolarında çalışır.

> [!NOTE]
> Yalnızca bir işlem düzeyi desteklenir. Hareketleri iç içe geçemez siniz veya bir hareket birden çok veritabanı nesnelerine yayılamaz.

Aşağıdaki konular, işlemlerin nasıl gerçekleştirildiği hakkında daha fazla bilgi sağlar:

- [İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [İşlem: İşlemlerin Güncelleştirmeleri Etkilemesi (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
