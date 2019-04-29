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
ms.openlocfilehash: a151ec5ca2b4bdc19bfa7dc626aebda0740a2c9e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329926"
---
# <a name="transaction-odbc"></a>İşlem (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Bir işlem grubu ya da toplu işlem, güncelleştirmeleri bir dizi için bir yol olan bir [veri kaynağı](../../data/odbc/data-source-odbc.md) tümünü tek seferde kaydedilmiş veya işlem geri alma durumunda taahhüt yok. Bir işlem kullanmıyorsanız, otomatik olarak isteğe bağlı yürütme yerine değişiklikleri veri kaynağına kararlıyız.

> [!NOTE]
>  Veritabanı tüm sürücülerin işlemleri destekler. Çağrı `CanTransact` üye işlevini, [CDatabase](../../mfc/reference/cdatabase-class.md) veya [CRecordset](../../mfc/reference/crecordset-class.md) sürücünüz işlemleri için belirli bir veritabanı destekleyip desteklemediğini belirlemek üzere nesne. Unutmayın `CanTransact` olup veri kaynağı tam işlem desteği sağlar söylemez. Ayrıca çağırmalıdır `CDatabase::GetCursorCommitBehavior` ve `CDatabase::GetCursorRollbackBehavior` sonra `CommitTrans` ve `Rollback` açık işlem etkisini denetlemek için `CRecordset` nesne.

Çağrılar `AddNew` ve `Edit` üye işlevlerinin bir `CRecordset` çağırdığınızda hemen veri kaynağını etkileyen nesne `Update`. `Delete` aramalar da hemen etkili olur. Buna karşılık, birden çok çağrı oluşan bir işlem kullanabilirsiniz `AddNew`, `Edit`, `Update`, ve `Delete`, hangi gerçekleştirildi ancak siz çağrılana kadar tamamlanmayan `CommitTrans` açıkça. Bir işlem oluşturarak, geri alma özelliğini koruyarak bir dizi böyle çağrılar yürütebilir. Kritik bir kaynak kullanılamıyor veya başka bir koşul tüm işlemin tamamlanmasını engeller, işlem kabul etmek yerine geri alabilirsiniz. Bu durumda işleme ait değişikliklerin hiçbiri veri kaynağını etkilemez.

> [!NOTE]
>  Şu anda, sınıf `CRecordset` toplu satır getirme uyguladıysanız güncelleştirmeleri veri kaynağına desteklemez. Bu çağrılar yapılamıyor anlamına gelir `AddNew`, `Edit`, `Delete`, veya `Update`. Ancak, güncelleştirmeler gerçekleştirin ve ardından belirli bir işlem içinde bu işlevleri çağırmak için kendi işlevler yazabilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
>  Kümenizin etkileyen yanı sıra işlemler ODBC kullandığınız sürece, doğrudan yürütme SQL deyimleri etkiler **HDBC** ilişkili, `CDatabase` nesnesi veya bir ODBC **HSTMT** göre **HDBC**.

İşlemler aynı anda güncelleştirilmelidir birden fazla kayıt varsa özellikle yararlıdır. Bu durumda, bir yarı tamamlanmış işlem yapılan son güncelleştirmeden önce bir özel durum oluştu, gibi gerçekleşebilir engellemek istiyorsanız. Bu güncelleştirmeler bir işlem olarak gruplandırmak değişikliklere karşı bir kurtarma (Geri Al) sağlar ve işlem öncesi durumuna kayıtları döndürür. Örneğin, bir banka hesap B bir hesaptan para aktarırsa, hem mevcut Fonu doğru şekilde işlemek için bir ve havale hesabından b başarılı olması gerekir veya tüm işlemin başarısız olması.

Veritabanı sınıfları gerçekleştirdiğiniz işlemleri aracılığıyla `CDatabase` nesneleri. A `CDatabase` nesne veri kaynağı bağlantısı temsil eder ve bir veya daha fazla kayıt kümeleri ile ilişkili `CDatabase` nesne üzerindeki veritabanı kümesi üye işlevleri aracılığıyla tablolarda çalışır.

> [!NOTE]
>  Tek düzey işlemleri desteklenir. İşlemleri iç içe ya da bir işlem birden çok veritabanı nesne kapsayabilir.

Aşağıdaki konular, işlemlerin nasıl gerçekleştirileceği hakkında daha fazla bilgi sağlar:

- [İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [İşlem: İşlemlerin Güncelleştirmeleri Etkileme Biçimi (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)