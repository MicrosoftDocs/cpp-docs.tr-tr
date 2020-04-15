---
title: 'Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirmesi (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
ms.openlocfilehash: 03fb696c1fadd834962d37c8e75b5f8910af819e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366974"
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirmesi (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Kayıt kümeleri, bir veri kaynağından kayıtları seçebilme yeteneklerinin yanı sıra, seçili kayıtları güncelleyebilir veya silebilir veya yeni kayıtlar ekleyebilir. Üç faktör bir kayıt kümesinin güncellenebilirliğini belirler: bağlı veri kaynağının güncellenebilir olup olmadığı, bir kayıt kümesi nesnesi oluştururken belirttiğiniz seçenekler ve oluşturulan SQL.

> [!NOTE]
> Nesnenizin `CRecordset` dayandığı SQL kayıt setinizin güncellenebilirliğini etkileyebilir. Örneğin, SQL'iniz bir birleştirme veya **GROUP BY** yan tümcesi içeriyorsa, MFC güncellenebilirliği FALSE olarak ayarlar.

> [!NOTE]
> Bu konu, toplu satır `CRecordset` alma nın uygulanmadığı türetilen nesneler için geçerlidir. Toplu satır alma kullanıyorsanız, [bkz.](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

Bu konu açıklar:

- [Kayıt kurulumu ndaki rolünüz ve](#_core_your_role_in_recordset_updating) çerçevenin sizin için ne yaptığı.

- [Bir edit arabelleği olarak kayıt kümesi](#_core_the_edit_buffer) ve [dinamitler ve anlık görüntüler arasındaki farklar.](#_core_dynasets_and_snapshots)

[Recordset: AddNew, Düzenle ve İşi Sil (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) bu işlevlerin eylemlerini kayıt kümesi açısından nasıl açıklar.

[Recordset: Daha Fazla Güncelleştirme hakkında (ODBC),](../../data/odbc/recordset-more-about-updates-odbc.md) işlemlerin güncelleştirmeleri nasıl etkilediğini, kayıt kümesini veya kaydırmanın devam eden güncelleştirmeleri nasıl etkilediğini ve güncelleştirmelerinizin diğer kullanıcıların güncelleştirmeleriyle nasıl etkileşimde olduğunu açıklayarak kayıt kümesi güncelleştirme hikayesini tamamlar.

## <a name="your-role-in-recordset-updating"></a><a name="_core_your_role_in_recordset_updating"></a>Kayıt Kurulumundaki Rolünüz Güncel

Aşağıdaki tablo, çerçevenin sizin için yaptığı yla birlikte kayıtları eklemek, kaydetmek veya silmek için kayıt kümelerini kullanmadaki rolünüzü gösterir.

### <a name="recordset-updating-you-and-the-framework"></a>Recordset Güncelleme: Siz ve Çerçeve

|Bunun için,|Çerçeve|
|---------|-------------------|
|Veri kaynağının güncelleştirilebilir (veya eklenebilir) olup olmadığını belirleyin.|Veri kaynağının güncellenebilirliğini veya eklenebilirliğini sınamak için [CDatabase](../../mfc/reference/cdatabase-class.md) üye işlevleri sağlar.|
|Güncel bir kayıt kümesi (herhangi bir türde) açın.||
|Kayıt kümesinin güncelleştirilebilir olup `CRecordset` olmadığını, güncelleştirme `CanUpdate` `CanAppend`işlevlerini çağırarak belirleyin veya .||
|Kayıtları eklemek, düzenlemek ve silmek için kayıt kümesi üye işlevlerini arayın.|Kayıt kümesi nesneniz ile veri kaynağınız arasında veri alışverişi mekaniğini yönetir.|
|İsteğe bağlı olarak, güncelleştirme işlemini denetlemek için hareketleri kullanın.|Hareketleri `CDatabase` desteklemek için üye işlevleri sağlar.|

İşlemler hakkında daha fazla bilgi için [Bkz. Hareket (ODBC)](../../data/odbc/transaction-odbc.md).

## <a name="the-edit-buffer"></a><a name="_core_the_edit_buffer"></a>Arabellek'i Edin

Toplu olarak ele alındığında, bir kayıt kümesinin alan veri üyeleri tek bir kayıt - geçerli kayıt içeren bir edit arabelleği olarak hizmet vermektedir. Güncelleştirme işlemleri geçerli kayıt üzerinde çalışmak için bu arabelleği kullanın.

- Bir kayıt eklediğinizde, edit arabelleği yeni bir kayıt oluşturmak için kullanılır. Kaydı eklemeyi bitirdiğinizde, daha önce geçerli olan kayıt yeniden geçerli olur.

- Bir kaydı güncellediğinizde (güncellediğinizde), kayıt kümesinin alan veri üyelerini yeni değerlere ayarlamak için durum arabelleği kullanılır. Güncelleştirmeyi bitirdiğinizde, güncelleştirilmiş kayıt hala geçerlidir.

[AddNew](../../mfc/reference/crecordset-class.md#addnew) veya [Edit'i](../../mfc/reference/crecordset-class.md#edit)aradiğinizde, geçerli kayıt gerektiğinde daha sonra geri yüklenebilmek için depolanır. [Sil'i](../../mfc/reference/crecordset-class.md#delete)aradiğinizde, geçerli kayıt depolanmaz, silinmiş olarak işaretlenir ve başka bir kayda kaydırmanız gerekir.

> [!NOTE]
> Edinme arabelleği kayıt silmede hiçbir rol oynamaz. Geçerli kaydı sildiğinizde, kayıt silinmiş olarak işaretlenir ve farklı bir kayda geçene kadar kayıt kümesi "kayıtta değil" olarak işaretlenir.

## <a name="dynasets-and-snapshots"></a><a name="_core_dynasets_and_snapshots"></a>Dynasets ve Snapshots

[Dynasets, kayda](../../data/odbc/dynaset.md) geçerken kaydın içeriğini yeniler. [Anlık görüntüler](../../data/odbc/snapshot.md) kayıtların statik gösterimleridir, bu nedenle [Requery'yi](../../mfc/reference/crecordset-class.md#requery)aramadığınız sürece kaydın içeriği yenilenmez. Dynasets'in tüm işlevselliğini kullanmak için, doğru ODBC API desteği düzeyine uygun bir ODBC sürücüsüyle çalışıyor olmalısınız. Daha fazla bilgi için [ODBC](../../data/odbc/odbc-basics.md) ve [Dynaset'e](../../data/odbc/dynaset.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: AddNew, Düzenleme ve Silmenin Çalışması (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)
