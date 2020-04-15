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
ms.openlocfilehash: abd5f817ad321241df2d8565bd6bf346c0792088
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366957"
---
# <a name="recordset-locking-records-odbc"></a>Kayıt Kümesi: Kayıtları Kilitleme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu açıklar:

- [Kullanılabilir kayıt kilitleme türleri.](#_core_record.2d.locking_modes)

- [Güncelleştirmeler sırasında kayıt setinizdeki kayıtları kilitleme.](#_core_locking_records_in_your_recordset)

Veri kaynağındaki bir kaydı güncelleştirmek için bir kayıt kümesi kullandığınızda, uygulamanız kaydı kilitleyebilir, böylece başka hiçbir kullanıcı kaydı aynı anda güncelleştiremez. Sistem, iki kullanıcının aynı anda bir kaydı güncelleştiremeyeceğini garanti edemediği sürece, aynı anda iki kullanıcı tarafından güncelleştirilen bir kaydın durumu tanımsızdır.

> [!NOTE]
> Bu konu, toplu satır `CRecordset` alma nın uygulanmadığı türetilen nesneler için geçerlidir. Toplu satır alma uyguladıysanız, bazı bilgiler geçerli değildir. Örneğin, `Edit` ve `Update` üye işlevleri arayamamazsınız. Toplu satır alma hakkında daha fazla bilgi için bkz: [Recordset: Toplu Olarak Kayıtları Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="record-locking-modes"></a><a name="_core_record.2d.locking_modes"></a>Kayıt Kilitleme Modları

Veritabanı sınıfları iki [kayıt kilitleme modu](../../mfc/reference/crecordset-class.md#setlockingmode)sağlar:

- İyimser kilitleme (varsayılan)

- Kötümser kilitleme

Bir kaydı niçin güncelleştirme, üç adımda gerçekleşir:

1. [İşleme Edit](../../mfc/reference/crecordset-class.md#edit) üye işlevini çağırarak başlarsınız.

1. Geçerli kaydın uygun alanlarını değiştirirsiniz.

1. [Güncelleştirme](../../mfc/reference/crecordset-class.md#update) üyesi işlevini arayarak işlemi sonlandırın ve normalde güncelleştirmeyi yaparsınız.

İyimser kilitleme, yalnızca `Update` arama sırasında veri kaynağındaki kaydı kilitler. Çok kullanıcılı bir ortamda iyimser kilitleme kullanıyorsanız, `Update` uygulama bir hata koşulu işlemek gerekir. Kötümser kilitleme en kısa sürede arama `Edit` ve aramakadar `Update` serbest bırakmaz (hatalar `CDBException` mekanizma üzerinden değil, FALSE bir `Update`değer tarafından döndürülen gösterilir) Kötümser kilitleme, aynı kayda eşzamanlı erişim uygulamanızın `Update` işleminin tamamlanmasına kadar beklemek zorunda kalabilir, çünkü kötümser kilitleme diğer kullanıcılar için potansiyel bir performans cezası vardır.

## <a name="locking-records-in-your-recordset"></a><a name="_core_locking_records_in_your_recordset"></a>Kayıt Setinizdeki Kayıtları Kilitleme

Varsayılan dan bir kayıt kümesi nesnenin [kilitleme modunu](#_core_record.2d.locking_modes) değiştirmek istiyorsanız, aramadan `Edit`önce modu değiştirmeniz gerekir.

#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>Kayıt setinizin geçerli kilitleme modunu değiştirmek için

1. [SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode) üye işlevini, ya `CRecordset::pessimistic` da `CRecordset::optimistic`.

Yeni kilitleme modu, siz yeniden değiştirene veya kayıt kümesi kapanana kadar etkin kalır.

> [!NOTE]
> Nispeten az Sayıda ODBC sürücüleri şu anda kötümser kilitleme desteği.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)
