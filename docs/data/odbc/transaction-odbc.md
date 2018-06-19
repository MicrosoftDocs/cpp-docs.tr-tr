---
title: İşlem (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets [C++], updating
- transactions [C++], MFC ODBC classes
- ODBC [C++], transactions
- recordsets [C++], updating
- databases [C++], transactions
- recordsets [C++], transactions
- ODBC recordsets [C++], transactions
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3acd47746d3a920b679fb5509c34e5978ad43eed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094032"
---
# <a name="transaction-odbc"></a>İşlem (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bir işlem toplu güncelleştirmeler için bir dizi veya gruplandırmak için bir yoldur bir [veri kaynağı](../../data/odbc/data-source-odbc.md) böylece tüm aynı anda kaydedilmiş veya işlemi geri olursa hiçbirinin tamamlanmadığı. Bir işlem kullanmazsanız, veri kaynağına değişiklikler otomatik olarak isteğe bağlı olarak kabul edilmek yerine uygulanır.  
  
> [!NOTE]
>  Tüm ODBC veritabanı sürücüleri işlemlerini destekler. Çağrı `CanTransact` üye işlevini, [CDatabase](../../mfc/reference/cdatabase-class.md) veya [CRecordset](../../mfc/reference/crecordset-class.md) sürücünüzü için verilen bir veritabanı işlemleri destekleyip desteklemediğini belirlemek için nesne. Unutmayın `CanTransact` olup veri kaynağı tam işlem desteği sağlar söylemez. Ayrıca çağırmalısınız `CDatabase::GetCursorCommitBehavior` ve `CDatabase::GetCursorRollbackBehavior` sonra **CommitTrans** ve **geri alma** açık işlem etkisini denetlemek için `CRecordset` nesnesi.  
  
 Çağrılar `AddNew` ve **Düzenle** üye işlevlerinin bir `CRecordset` çağırdığınızda hemen veri kaynağını etkileyen nesne **güncelleştirme**. **Silme** çağrıları da hemen etkili olur. Buna karşılık, birden fazla çağrı oluşan bir işlem kullanabilirsiniz `AddNew`, **Düzenle**, **güncelleştirme**, ve **silmek**, hangi gerçekleştirilen ama kadar kaydedilen değil çağırmanız **CommitTrans** açıkça. Bir işlem oluşturarak, geri alma olanağı korurken tür çağrılar bir dizi yürütebilir. Kritik bir kaynak kullanılamıyor veya başka bir koşul tüm işlemin tamamlanmasını engeller, bunu gerçekleştirmeden yerine işlem geri alabilirsiniz. Bu durumda işleme ait değişikliklerin hiçbiri veri kaynağını etkilemez.  
  
> [!NOTE]
>  Şu anda, sınıf `CRecordset` toplu satır getirme uyguladıysanız veri kaynağı güncelleştirmelerini desteklemez. Bu çağrı yapılamıyor anlamına gelir `AddNew`, **Düzenle**, **silmek**, veya **güncelleştirme**. Ancak, güncelleştirmeleri gerçekleştirmek ve belirli bir işlem içinde bu işlevleri çağırmak için kendi işlevleri yazabilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Kümenizin etkileyen yanı sıra işlemleri ODBC kullandığınız sürece, doğrudan yürütme SQL deyimlerini de etkiler **HDBC** ile ilişkili, `CDatabase` nesnesi veya bir ODBC **HSTMT** göre **HDBC**.  
  
 Aynı anda güncelleştirilmesi gereken birden çok kayıt varsa, işlemleri özellikle yararlı olur. Bu durumda, bir yarı-işlem tamamlandı, gibi son güncelleştirme yapılmadan önce bir özel durum oluştu, gerçekleşebilir önlemek istiyor. Bu güncelleştirmeler bir işlem olarak gruplandırmak değişikliklerden bir kurtarma (rollback) sağlar ve kayıtları işlem öncesi durumuna döndürür. Örneğin, banka hesabı B A hesabından para aktarırsa, hem bir banka hesabından b fon düzgün şekilde başarılı gerekir veya tüm işlem başarısız olmalıdır.  
  
 Veritabanı sınıfları aracılığıyla işlemlerini gerçekleştirmek `CDatabase` nesneleri. A `CDatabase` nesnesi, bir veri kaynağına bağlantıyı temsil eder ve bir veya daha fazla kayıt kümeleri ile ilişkili `CDatabase` nesnesi üzerindeki kayıt kümesi üye işlevleri aracılığıyla veritabanının tablolarda çalışır.  
  
> [!NOTE]
>  Yalnızca bir düzey işlemler desteklenir. Ya da bir işlemde birden çok veritabanı nesnelerini yayılabilir işlemleri iç içe yerleştirilemez.  
  
 Aşağıdaki konular işlemleri nasıl gerçekleştirileceği hakkında daha fazla bilgi sağlar:  
  
-   [İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)  
  
-   [İşlem: İşlemlerin Güncelleştirmeleri Etkilemesi (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)