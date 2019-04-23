---
title: 'Kayıt kümesi: Kayıtları Kilitleme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- locks [C++], recordsets
- optimistic locking
- pessimistic locking in ODBC
- recordsets [C++], locking records
- optimistic locking, ODBC
- ODBC recordsets [C++], locking records
- data [C++], locking
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
ms.openlocfilehash: 1265899e7060527d7e586689eb4c3148eebc4080
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037295"
---
# <a name="recordset-locking-records-odbc"></a>Kayıt kümesi: Kayıtları Kilitleme (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Bu konu şunları açıklar:

- [Kullanılabilir kayıt kilitleme türlerini](#_core_record.2d.locking_modes).

- [Kayıt sırasında güncelleştirmeleri kümenize kilitleme](#_core_locking_records_in_your_recordset).

Veri kaynağındaki bir kaydı güncelleştirmek için bir kayıt kümesi kullandığınızda, başka bir kullanıcı kaydı aynı anda güncelleştirilmesini uygulamanızı kayda kilitleyebilirsiniz. Aynı anda iki kullanıcı tarafından güncelleştirilmiş bir kaydın durumunu, sistem iki kullanıcı bir kaydı aynı anda güncelleştiremiyor garanti sürece tanımsızdır.

> [!NOTE]
>  Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme uyguladıysanız, bazı bilgiler geçerli değildir. Örneğin, çağıramazsınız `Edit` ve `Update` üye işlevleri. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="_core_record.2d.locking_modes"></a> Kayıt kilitleme modu

İki veritabanı sınıfları sağlar [kayıt kilitleme modu](../../mfc/reference/crecordset-class.md#setlockingmode):

- İyimser kilitleme (varsayılan)

- Kötümser kilitleme

Bir kaydı güncelleştirme üç adımda gerçekleştirilir:

1. Çağırarak işlemi başlamadan [Düzenle](../../mfc/reference/crecordset-class.md#edit) üye işlevi.

1. Geçerli kaydın uygun alanları değiştirin.

1. İşlemi sonlandıran — ve normalde güncelleştirme yürütme — çağırarak [güncelleştirme](../../mfc/reference/crecordset-class.md#update) üye işlevi.

Kilit yalnızca veri kaynağında kayıt İyimser kilitleme `Update` çağırın. Çok kullanıcılı bir ortamda İyimser kilitleme kullanırsanız uygulama işlemelidir bir `Update` hata durumu. Kötümser kilitleme kilitler kaydı çağırmanızı hemen sonra `Edit` ve dek çağrı bırakmaz `Update` (hataları aracılığıyla gösterilir `CDBException` tarafından döndürülen FALSE değeri tarafından değil bir mekanizma `Update`). Kötümser kilitleme olan diğer kullanıcılar için olası bir performans cezası aynı kaydı eş zamanlı erişim, uygulamanızın bir işlem tamamlanana kadar beklemeniz gerekebilir çünkü `Update` işlem.

##  <a name="_core_locking_records_in_your_recordset"></a> Kümenizde kayıtları kilitleme

Kayıt kümesi nesnesinin değiştirmek istiyorsanız [kilitleme modu](#_core_record.2d.locking_modes) varsayılandan çağırmadan önce modu değiştirmelisiniz `Edit`.

#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>Kümeniz için geçerli kilitleme modunu değiştirmek için

1. Çağrı [CRecordset::pessimistic](../../mfc/reference/crecordset-class.md#setlockingmode) belirtme, üye işlevi `CRecordset::pessimistic` veya `CRecordset::optimistic`.

Yeni kilitleme modu, siz tekrar değiştirene veya kayıt kapatılana kadar yürürlükte kalır.

> [!NOTE]
>  Nispeten daha az sayıda ODBC sürücüleri şu anda kötümser kilitleme destekler.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Birleşim gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)<br/>
[Kayıt kümesi: Ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)