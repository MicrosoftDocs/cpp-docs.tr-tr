---
title: 'Kayıt Kümesi: Kayıtları Kilitleme (ODBC)'
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
ms.openlocfilehash: d4e80816a131c997e9f5bfaa34f025394b05a358
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212868"
---
# <a name="recordset-locking-records-odbc"></a>Kayıt Kümesi: Kayıtları Kilitleme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konuda aşağıdakiler açıklanmaktadır:

- [Kullanılabilir kayıt kilitleme türleri](#_core_record.2d.locking_modes).

- [Güncelleştirmeler sırasında kayıt kümenizde kayıtları kilitleme](#_core_locking_records_in_your_recordset).

Veri kaynağındaki bir kaydı güncellemek için bir kayıt kümesi kullandığınızda, uygulamanız kaydı kilitleyerek başka bir kullanıcının kaydı aynı anda güncelleştiremez. Aynı anda iki kullanıcı tarafından güncelleştirilmiş bir kaydın durumu, sistem iki kullanıcının bir kaydı aynı anda güncelleştiremediği garanti edemediği durumlar için tanımsızdır.

> [!NOTE]
>  Bu konu, toplu satır yakalamanın uygulanmadığı `CRecordset` türetilen nesneler için geçerlidir. Toplu satır getirme uyguladıysanız bazı bilgiler uygulanmaz. Örneğin, `Edit` ve `Update` üye işlevleri çağrılamaz. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="record-locking-modes"></a><a name="_core_record.2d.locking_modes"></a>Kayıt kilitleme modları

Veritabanı sınıfları iki [kayıt kilitleme modu](../../mfc/reference/crecordset-class.md#setlockingmode)sağlar:

- İyimser kilitleme (varsayılan)

- Kötümser kilitleme

Bir kaydın güncelleştirilmesi üç adımda gerçekleşir:

1. Üyeyi [Düzenle](../../mfc/reference/crecordset-class.md#edit) işlevini çağırarak işlemi başlatabilirsiniz.

1. Geçerli kaydın uygun alanlarını değiştirirsiniz.

1. İşlemi sonlandırın — ve [güncelleştirme üyesi işlevini çağırarak genellikle güncelleştirmeyi yürütün](../../mfc/reference/crecordset-class.md#update) .

İyimser kilitleme, veri kaynağındaki kaydı yalnızca `Update` çağrısı sırasında kilitler. Çok kullanıcılı bir ortamda iyimser kilitleme kullanırsanız, uygulamanın bir `Update` hata koşulunu işlemesi gerekir. Kötümser kilitleme, `Edit` çağırana kadar kaydı kilitler ve siz `Update` çağırana kadar serbest bırakmaz (`Update`tarafından döndürülen yanlış bir değer tarafından değil, `CDBException` mekanizmasıyla belirtilir). Aynı kayda eşzamanlı erişim, uygulamanızın `Update` işleminin tamamlanmasını beklemek zorunda olabileceğinden, Kötümser kilitleme diğer kullanıcılar için olası bir performans cezası içerir.

##  <a name="locking-records-in-your-recordset"></a><a name="_core_locking_records_in_your_recordset"></a>Kayıt kümenizde kayıt kilitleme

Bir kayıt kümesi nesnesinin [kilitleme modunu](#_core_record.2d.locking_modes) varsayılana değiştirmek istiyorsanız, `Edit`çağrısı yapmadan önce modu değiştirmeniz gerekir.

#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>Kayıt kümenizin geçerli kilitleme modunu değiştirmek için

1. `CRecordset::pessimistic` ya da `CRecordset::optimistic`belirterek [SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode) üye işlevini çağırın.

Yeni kilitleme modu, siz değiştirene veya kayıt kümesi kapatıldıktan kadar yürürlükte kalır.

> [!NOTE]
>  Nispeten kilitlemeyi destekleyen nispeten daha az sayıda ODBC sürücüsü şu anda çalışıyor.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)
