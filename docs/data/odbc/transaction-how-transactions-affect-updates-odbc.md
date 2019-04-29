---
title: 'İşlem: İşlemler (ODBC) güncelleştirmeleri nasıl etkiler'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
ms.openlocfilehash: 996b8410366661cb91cf82cfff823f17d3aad8b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329913"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>İşlem: İşlemler (ODBC) güncelleştirmeleri nasıl etkiler

Güncelleştirmeleri [veri kaynağı](../../data/odbc/data-source-odbc.md) sırasında işlem düzenleme arabelleği (işlem dışında kullanılan aynı yönteme) kullanılarak yönetilir. Kayıt alan veri üyeleri topluca kayıt sırasında geçici olarak yedekler geçerli kayıt içeren düzenleme arabelleği görevi gören bir `AddNew` veya `Edit`. Sırasında bir `Delete` işlemi, geçerli kayıt yedeklenmez bir işlem içinde. Düzenleme arabelleği ve nasıl kayıt güncelleştirmeleri depolamak hakkında daha fazla bilgi için bkz. [kayıt kümesi: Kümelerinin kayıtları Güncelleştirmesi (ODBC) kayıtları](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

> [!NOTE]
>  Toplu satır getirme uyguladıysanız çağıramazsınız `AddNew`, `Edit`, veya `Delete`. Bunun yerine, veri kaynağı güncelleştirmelerini gerçekleştirmek için kendi işlevleri yazmanız gerekir. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

İşlem sırasında `AddNew`, `Edit`, ve `Delete` işlem kaydedilmiş veya geri alındı. Etkilerini `CommitTrans` ve `Rollback` geçerli kayıt düzenleme ara yüklenmemesine neden olabilir. Geçerli kayıt düzgün bir şekilde geri yüklendiğinden emin olmak için anlamak önemlidir nasıl `CommitTrans` ve `Rollback` üye işlevleri `CDatabase` güncelleştirme işlevlerini ile çalışmak `CRecordset`.

##  <a name="_core_how_committrans_affects_updates"></a> CommitTrans güncelleştirmeleri nasıl etkiler?

Aşağıdaki tablo etkilerini açıklar `CommitTrans` işlemlerle ilgili.

### <a name="how-committrans-affects-updates"></a>CommitTrans güncelleştirmeleri nasıl etkiler?

|Çalışma|Veri kaynağı durumu|
|---------------|---------------------------|
|`AddNew` ve `Update`ve ardından `CommitTrans`|Veri kaynağı için yeni bir kayıt eklenir.|
|`AddNew` (olmadan `Update`) ve ardından `CommitTrans`|Yeni kayıt kaybolur. Kaydı veri kaynağına ekli değil.|
|`Edit` ve `Update`ve ardından `CommitTrans`|Düzenlemeler, veri kaynağına işlendi.|
|`Edit` (olmadan `Update`) ve ardından `CommitTrans`|Kayıt düzenlemeler kaybedilir. Kayıt veri kaynağında değişmeden kalır.|
|`Delete` Ardından `CommitTrans`|Kayıt veri kaynağından silinir.|

##  <a name="_core_how_rollback_affects_updates"></a> Geri alma işlemleri etkileme

Aşağıdaki tablo etkilerini açıklar `Rollback` işlemlerle ilgili.

### <a name="how-rollback-affects-transactions"></a>Geri alma işlemleri etkileme

|Çalışma|Geçerli kayıt durumu|Ayrıca gerekir|Veri kaynağı durumu|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew` ve `Update`, ardından `Rollback`|Geçerli kayıt içeriğini yer açmak için yeni kayıt için geçici olarak depolanır. Yeni kayıt düzenleme arabelleğine girilir. Sonra `Update` çağrıldığında, geçerli kayıt düzenleme ara geri yüklenir.||Veri kaynağı tarafından yapılan bir eklemedir `Update` ters çevrilir.|
|`AddNew` (olmadan `Update`), ardından `Rollback`|Geçerli kayıt içeriğini yer açmak için yeni kayıt için geçici olarak depolanır. Düzen arabellek, yeni bir kayıt içerir.|Çağrı `AddNew` yeniden düzenleme arabellek boş, yeni bir kayıt için geri yüklemek için. Veya çağrı `Move`eski değerleri düzenleme ara geri yüklemek için (0).|Çünkü `Update` çağrılmadı, veri kaynağına yapılan bir değişiklik yoktur.|
|`Edit` ve `Update`, ardından `Rollback`|Geçerli kayıt düzenlenmemiş bir sürümünü geçici olarak depolanır. Düzenlemeler düzenleme arabellek içeriği yapılır. Sonra `Update` çağrıldığında düzenlenmemiş kaydın sürümünü yine de geçici olarak depolanır.|*Dynaset*: Geçerli kayıt düzenlenmemiş sürüm kaydının düzenleme ara geri yüklemek için geri gelin.<br /><br /> *Anlık Görüntü*: Çağrı `Requery` kayıt veri kaynağından yenilenemedi.|Veri kaynağı tarafından yapılan değişiklikleri `Update` alınır.|
|`Edit` (olmadan `Update`), ardından `Rollback`|Geçerli kayıt düzenlenmemiş bir sürümünü geçici olarak depolanır. Düzenlemeler düzenleme arabellek içeriği yapılır.|Çağrı `Edit` yeniden düzenleme ara kaydı düzenlenmemiş sürümünü geri yüklemek için.|Çünkü `Update` çağrılmadı, veri kaynağına yapılan bir değişiklik yoktur.|
|`Delete` Ardından `Rollback`|Geçerli kayıt içeriğini silinir.|Çağrı `Requery` veri kaynağından geçerli kayıt içeriğini geri yüklemek için.|Veri kaynağı silme işlemi ters çevrilir.|

## <a name="see-also"></a>Ayrıca bkz.

[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)