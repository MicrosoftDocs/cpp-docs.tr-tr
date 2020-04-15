---
title: 'İşlem: İşlemlerin Güncelleştirmeleri Etkilemesi (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
ms.openlocfilehash: 8a87176ecb20beaf46583e1190b0ad458d508b31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376430"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>İşlem: İşlemlerin Güncelleştirmeleri Etkilemesi (ODBC)

[Veri kaynağındaki](../../data/odbc/data-source-odbc.md) güncelleştirmeler, bir edit arabelleği (hareketler dışında kullanılan yöntem) aracılığıyla işlemler sırasında yönetilir. Bir kayıt kümesinin alan veri üyeleri, kayıt kümesinin bir `AddNew` veya `Edit`. Bir `Delete` işlem sırasında, geçerli kayıt bir hareket içinde yedeklenmez. Edinme arabelleği ve güncelleştirmelerin geçerli kaydı nasıl depolayıştısı hakkında daha fazla bilgi için Bkz. [Kayıt Kümesi: Kayıtları Nasıl Güncelleştirin (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

> [!NOTE]
> Toplu satır alma uyguladıysanız, `AddNew`, `Edit`veya `Delete`. Bunun yerine veri kaynağına güncelleştirmeleri gerçekleştirmek için kendi işlevlerinizi yazmanız gerekir. Toplu satır alma hakkında daha fazla bilgi için bkz: [Recordset: Toplu Olarak Kayıtları Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Hareketler `AddNew`sırasında, `Edit`ve `Delete` işlemler kaydedilebilir veya geri alınabilir. Efektleri `CommitTrans` ve `Rollback` geçerli kaydın düzenarabelleğe geri yüklenmemesin ekine neden olabilir. Geçerli kaydın düzgün bir şekilde geri yüklenir olduğundan emin `CommitTrans` olmak `Rollback` için, `CDatabase` `CRecordset`güncelleştirme işlevleriile çalışan ve üye işlevlerinin nasıl çalıştığını anlamak önemlidir.

## <a name="how-committrans-affects-updates"></a><a name="_core_how_committrans_affects_updates"></a>CommitTrans Güncelleştirmeleri Nasıl Etkiler?

Aşağıdaki tabloda hareketler `CommitTrans` üzerindeki etkileri açıklanmaktadır.

### <a name="how-committrans-affects-updates"></a>CommitTrans Güncelleştirmeleri Nasıl Etkiler?

|İşlem|Veri kaynağının durumu|
|---------------|---------------------------|
|`AddNew`ve `Update`, ve sonra`CommitTrans`|Veri kaynağına yeni kayıt eklenir.|
|`AddNew`(olmadan `Update`), ve sonra`CommitTrans`|Yeni rekor kayboldu. Kayıt veri kaynağına eklenmez.|
|`Edit`ve `Update`, ve sonra`CommitTrans`|Veri kaynağına adanmış ediner.|
|`Edit`(olmadan `Update`), ve sonra`CommitTrans`|Kayıt takimlari kaybedilir. Kayıt veri kaynağında değişmeden kalır.|
|`Delete`Sonra`CommitTrans`|Veri kaynağından silinen kayıtlar.|

## <a name="how-rollback-affects-transactions"></a><a name="_core_how_rollback_affects_updates"></a>Geri Alma İşlemleri Nasıl Etkiler?

Aşağıdaki tabloda hareketler `Rollback` üzerindeki etkileri açıklanmaktadır.

### <a name="how-rollback-affects-transactions"></a>Geri Alma İşlemleri Nasıl Etkiler?

|İşlem|Geçerli kaydın durumu|Ayrıca,|Veri kaynağının durumu|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew`ve `Update`, sonra`Rollback`|Geçerli kaydın içeriği, yeni kayda yer açmak için geçici olarak depolanır. Yeni kayıt, edit arabelleği girilir. Çağrıldıktan sonra, `Update` geçerli kayıt düzen arabelleği geri yüklenir.||Tarafından `Update` yapılan veri kaynağına ek olarak tersine çevrilir.|
|`AddNew`(olmadan `Update`), o zaman`Rollback`|Geçerli kaydın içeriği, yeni kayda yer açmak için geçici olarak depolanır. Yap arabelleği yeni kayıt içerir.|Düzenle arabelleği boş, yeni bir kayda geri yüklemek için yeniden arayın. `AddNew` Veya `Move`düzen arabelleği için eski değerleri geri yüklemek için (0) arayın.|Çağrılmediği `Update` için veri kaynağında herhangi bir değişiklik yapılmadı.|
|`Edit`ve `Update`, sonra`Rollback`|Geçerli kaydın düzenlenmemiş bir sürümü geçici olarak depolanır. Editler, edit arabelleği içeriğine yapılır. Çağrıldıktan sonra, `Update` kaydın düzenlenmemiş sürümü geçici olarak depolanır.|*Dynaset*: Kaydın düzenlenmemiş sürümünü düzenleme arabellesine geri yüklemek için geçerli kaydı n dışına kaydırın.<br /><br /> *Anlık*Görüntü `Requery` : Kayıt kümesini veri kaynağından yenilemek için arayın.|Veri `Update` kaynağında yapılan değişiklikler tersine çevrilir.|
|`Edit`(olmadan `Update`), o zaman`Rollback`|Geçerli kaydın düzenlenmemiş bir sürümü geçici olarak depolanır. Editler, edit arabelleği içeriğine yapılır.|Kaydın düzenlenmemiş sürümünü düzenleme arabellesine geri yüklemek için yeniden arayın. `Edit`|Çağrılmediği `Update` için veri kaynağında herhangi bir değişiklik yapılmadı.|
|`Delete`Sonra`Rollback`|Geçerli kaydın içeriği silinir.|Geçerli `Requery` kaydın içeriğini veri kaynağından geri yüklemek için arayın.|Veri kaynağından veri silme tersine çevrilir.|

## <a name="see-also"></a>Ayrıca bkz.

[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
