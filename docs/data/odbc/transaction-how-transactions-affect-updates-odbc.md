---
description: 'Daha fazla bilgi edinin: Işlem: Işlemlerin güncelleştirmeleri etkilemesi (ODBC)'
title: 'İşlem: İşlemlerin Güncelleştirmeleri Etkilemesi (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
ms.openlocfilehash: 56435d477ab11fe057ec20610a35e75d84cf7340
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333902"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>İşlem: İşlemlerin Güncelleştirmeleri Etkilemesi (ODBC)

[Veri kaynağı](../../data/odbc/data-source-odbc.md) güncelleştirmeleri, bir düzenleme arabelleği kullanılarak işlemler sırasında yönetilir (işlemler dışında kullanılan yöntem). Bir kayıt kümesinin alan veri üyeleri topluca, kayıt kümesinin bir veya sırasında geçici olarak yedeklediği geçerli kaydı içeren bir düzenleme arabelleği olarak hizmet verir `AddNew` `Edit` . İşlem sırasında `Delete` geçerli kayıt bir işlem içinde yedeklenmez. Düzenleme arabelleği ve güncelleştirmelerin geçerli kaydı nasıl depolayabileceği hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıt kümeleri kayıtları güncelleştirme (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

> [!NOTE]
> Toplu satır getirme uyguladıysanız, veya ' i çağrılamaz `AddNew` `Edit` `Delete` . Bunun yerine, veri kaynağına yönelik güncelleştirmeleri gerçekleştirmek için kendi işlevlerinizi yazmanız gerekir. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

İşlemler, `AddNew` ,, ve işlemler sırasında,,, `Edit` ve işlemleri gerçekleştirilebilir `Delete` veya geri alınabilir. `CommitTrans`Ve etkileri `Rollback` geçerli kaydın düzenleme arabelleğine geri yüklenmemesine neden olabilir. Geçerli kaydın düzgün şekilde geri yüklendiğinden emin olmak için, `CommitTrans` ve `Rollback` üye işlevlerinin `CDatabase` güncelleştirme işlevleriyle nasıl çalıştığını anlamak önemlidir `CRecordset` .

## <a name="how-committrans-affects-updates"></a><a name="_core_how_committrans_affects_updates"></a> CommitTrans güncelleştirmeleri nasıl etkiler

Aşağıdaki tabloda işlemlerin etkileri açıklanmaktadır `CommitTrans` .

### <a name="how-committrans-affects-updates"></a>CommitTrans güncelleştirmeleri nasıl etkiler

|İşlem|Veri kaynağının durumu|
|---------------|---------------------------|
|`AddNew` ve `Update` sonra `CommitTrans`|Yeni kayıt veri kaynağına eklenir.|
|`AddNew` (olmadan `Update` ) ve ardından `CommitTrans`|Yeni kayıt kaybolur. Kayıt veri kaynağına eklenmedi.|
|`Edit` ve `Update` sonra `CommitTrans`|Veri kaynağına işlenmiş düzenlemeler.|
|`Edit` (olmadan `Update` ) ve ardından `CommitTrans`|Kayıttaki düzenlemeler kaybedilir. Kayıt, veri kaynağında değişmeden kalır.|
|`Delete` ni `CommitTrans`|Kayıtlar veri kaynağından silindi.|

## <a name="how-rollback-affects-transactions"></a><a name="_core_how_rollback_affects_updates"></a> Geri almanın Işlemleri nasıl etkilediği

Aşağıdaki tabloda işlemlerin etkileri açıklanmaktadır `Rollback` .

### <a name="how-rollback-affects-transactions"></a>Geri almanın Işlemleri nasıl etkilediği

|İşlem|Geçerli kaydın durumu|Ayrıca şunları da yapmanız gerekir|Veri kaynağının durumu|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew` ve `Update` sonra `Rollback`|Geçerli kaydın içeriği, yeni kayda yer açmak için geçici olarak depolanır. Düzenleme arabelleğine yeni kayıt girilir. Çağrıldıktan sonra `Update` , geçerli kayıt düzenleme arabelleğine geri yüklenir.||Tarafından yapılan veri kaynağına ekleme `Update` işlemi tersine çevrilir.|
|`AddNew` (olmadan `Update` ), ardından `Rollback`|Geçerli kaydın içeriği, yeni kayda yer açmak için geçici olarak depolanır. Düzenleme arabelleği yeni kayıt içerir.|`AddNew`Düzenleme arabelleğini boş, yeni bir kayda geri yüklemek için yeniden çağırın. Ya da `Move` eski değerleri düzenleme arabelleğine geri yüklemek için (0) çağrısı yapın.|`Update`Çağrılmadı, veri kaynağında hiçbir değişiklik yapılmadı.|
|`Edit` ve `Update` sonra `Rollback`|Geçerli kaydın düzenlenmemiş sürümü geçici olarak depolanır. Düzenleme arabelleğinin içeriğinde düzenlemeler yapılır. Çağrıldıktan sonra `Update` , kaydın düzenlenmemiş sürümü hala geçici olarak depolanır.|*Dynaset*: kaydın düzenlenmemiş sürümünü düzenleme arabelleğine geri yüklemek için geçerli kaydı kapatın ve geri dönün.<br /><br /> *Snapshot*: `Requery` veri kaynağından kayıt kümesini yenilemek için çağırın.|Tarafından yapılan veri kaynağına yapılan değişiklikler `Update` tersine çevrilir.|
|`Edit` (olmadan `Update` ), ardından `Rollback`|Geçerli kaydın düzenlenmemiş sürümü geçici olarak depolanır. Düzenleme arabelleğinin içeriğinde düzenlemeler yapılır.|`Edit`Kaydın düzenlenmemiş sürümünü düzenleme arabelleğine geri yüklemek için yeniden çağırın.|`Update`Çağrılmadı, veri kaynağında hiçbir değişiklik yapılmadı.|
|`Delete` ni `Rollback`|Geçerli kaydın içeriği silindi.|`Requery`Geçerli kaydın içeriğini veri kaynağından geri yüklemek için çağırın.|Veri kaynağından veri silme işlemi tersine çevrilir.|

## <a name="see-also"></a>Ayrıca bkz.

[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[İşlem: kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)
