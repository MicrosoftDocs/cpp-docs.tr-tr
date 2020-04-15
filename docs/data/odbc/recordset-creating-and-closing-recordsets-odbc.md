---
title: 'Kayıt Kümesi: Kayıt Kümeleri Oluşturma ve Kapatma (ODBC)'
ms.date: 05/09/2019
helpviewer_keywords:
- ODBC recordsets, creating
- recordsets, creating
- recordsets, opening
- recordsets, closing
- ODBC recordsets, closing
- ODBC recordsets, opening
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
ms.openlocfilehash: 41b1c11e2c820b6e5777e1af426c5e1253ed5468
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367083"
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>Kayıt Kümesi: Kayıt Kümeleri Oluşturma ve Kapatma (ODBC)

> [!NOTE]
> MFC ODBC Tüketici sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz. Yine de bir tüketiciyi el ile oluşturabilirsiniz.

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir kayıt kümesi ni kullanmak için, bir `Open` kayıt kümesi nesnesi oluşturun ve ardından kayıt kümesinin sorgusunu çalıştırmak ve kayıtları seçmek için üye işlevini çağırın. Kayıt kümesini bitirdiğinizde nesneyi kapatın ve yok edin.

Bu konu açıklar:

- [Ne zaman ve nasıl bir kayıt kümesi nesnesi oluşturmak için](#_core_creating_recordsets_at_run_time).

- [Kayıt kümesinin davranışını parametreleştirerek, filtreleyerek, sıralayarak veya kilitleyerek ne zaman ve nasıl nitelendirebilirsiniz.](#_core_setting_recordset_options)

- [Kayıt kümesi nesnesi ne zaman ve nasıl kapatılınca.](#_core_closing_a_recordset)

## <a name="creating-recordsets-at-run-time"></a><a name="_core_creating_recordsets_at_run_time"></a>Çalışma Zamanında Kayıt Kümeleri Oluşturma

Programınızda kayıt kümesi nesneleri oluşturmadan önce genellikle uygulamaya özgü kayıt kümesi sınıfları yazarsınız. Bu ön adım hakkında daha fazla bilgi için [bkz.](../../mfc/reference/adding-an-mfc-odbc-consumer.md)

Bir veri kaynağından kayıtları seçmeniz gerektiğinde bir dinaset veya anlık görüntü nesnesi açın. Oluşturulacak nesnenin türü, uygulamanızdaki verilerle ne yapmanız gerektiğine ve ODBC sürücünüzün neyi desteklediğine bağlıdır. Daha fazla bilgi için [Dynaset](../../data/odbc/dynaset.md) ve [Snapshot'a](../../data/odbc/snapshot.md)bakın.

#### <a name="to-open-a-recordset"></a>Kayıt kümesini açmak için

1. Türetilmiş sınıfınızın `CRecordset`bir nesnesini oluştur.

   Nesneyi yığında veya bir işlevin yığın çerçevesi üzerinde oluşturabilirsiniz.

1. İsteğe bağlı olarak varsayılan kayıt kümesi davranışını değiştirin. Kullanılabilir seçenekler için Kayıt [Kümesi Ni Ayarlama Seçenekleri'ne](#_core_setting_recordset_options)bakın.

1. Nesnenin [Açık](../../mfc/reference/crecordset-class.md#open) üye işlevini arayın.

Oluşturucuda, çerçevenin `CDatabase` [GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) üye işlevi tarafından döndürülen bağlantı dizesini temel alarak oluşturduğu ve açtığı geçici bir veritabanı nesnesini kullanmak için bir nesneye işaretçi geçirin veya NULL'u geçirin. Nesne `CDatabase` zaten bir veri kaynağına bağlı olabilir.

Arama, `Open` veri kaynağından kayıtları seçmek için SQL kullanır. Seçilen ilk kayıt (varsa) geçerli kayıttır. Bu kaydın alanlarının değerleri, kaydedici nesnenin alan veri üyelerinde depolanır. Herhangi bir kayıt seçiliyse, hem üye `IsBOF` `IsEOF` işlevler 0 döndürer.

[Açık](../../mfc/reference/crecordset-class.md#open) aramanızda şunları yapabilirsiniz:

- Kayıt kümesinin bir dinamit mi yoksa anlık görüntü mü olduğunu belirtin. Kayıt kümeleri varsayılan olarak anlık görüntü olarak açılır. Veya, yalnızca ileri kaydırmaya, aynı anda bir kayıt sağlayan bir ileri kayıt kümesi belirtebilirsiniz.

   Varsayılan olarak, bir kayıt kümesi `CRecordset` veri üyesinde `m_nDefaultType`depolanan varsayılan türü kullanır. Sihirbazlar sihirbazseçtiğiniz recordset türüne para yla baş harflerini `m_nDefaultType` yazmak için kod yazar. Bu varsayılanı kabul etmek yerine, başka bir kayıt kümesi türünü değiştirebilirsiniz.

- Kayıt kümesinin yaptığı varsayılan SQL **SELECT** deyimini değiştirmek için bir dize belirtin.

- Kayıt kümesinin salt okunur mu yoksa yalnızca ek mi olduğunu belirtin. Kayıt kümeleri varsayılan olarak tam güncelleştirmeye izin verir, ancak bunu yalnızca yeni kayıtlar eklemekle sınırlandırabilirsiniz veya tüm güncelleştirmelere izin verebilirsiniz.

Aşağıdaki örnek, uygulamaya özgü bir sınıf olan `CStudentSet`sınıfın salt okunur anlık görüntü nesnesinin nasıl açılacağını gösterir:

```cpp
// Construct the snapshot object
CStudentSet rsStudent( NULL );
// Set options if desired, then open the recordset
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))
    return FALSE;
// Use the snapshot to operate on its records...
```

Aradıktan `Open`sonra, kayıtlarla çalışmak için nesnenin üye işlevlerini ve veri üyelerini kullanın. Bazı durumlarda, veri kaynağında meydana gelen değişiklikleri içerecek şekilde kayıt kümesini yeniden sorgulamak veya yenilemek isteyebilirsiniz. Daha fazla bilgi için [bkz: Recordset: Requerying a Recordset (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).

> [!TIP]
> Geliştirme sırasında kullandığınız bağlantı dizesi, nihai kullanıcılarınızın gereksinim duyduğu bağlantı dizesinin aynısı olmayabilir. Bu konuda uygulamanızı genelleme hakkında fikirler için bkz: [Veri Kaynağı: Bağlantıları Yönetme (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md).

## <a name="setting-recordset-options"></a><a name="_core_setting_recordset_options"></a>Recordset Seçeneklerini Ayarlama

Kayıt kümesi nesnenizi oluştursanız, `Open` ancak kayıtları seçmek için aramadan önce, kayıt kümesinin davranışını denetlemek için bazı seçenekler ayarlamak isteyebilirsiniz. Tüm kayıt kümeleri için şunları yapabilirsiniz:

- Kayıt seçimini kısıtlamak için bir [filtre](../../data/odbc/recordset-filtering-records-odbc.md) belirtin.

- Kayıtlar için bir [sıralama](../../data/odbc/recordset-sorting-records-odbc.md) sırası belirtin.

- Çalışma zamanında elde edilen veya hesaplanan bilgileri kullanarak kayıtları seçebilmeniz için [parametreleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) belirtin.

Koşullar uygunsa aşağıdaki seçeneği de ayarlayabilirsiniz:

- Kayıt kümesi güncelleştirilebilirse ve kilitleme seçeneklerini destekliyorsa, güncelleştirmeler için kullanılan [kilitleme](../../data/odbc/recordset-locking-records-odbc.md) yöntemini belirtin.

> [!NOTE]
> Kayıt seçimini etkilemek için, üye işlevi çağırmadan `Open` önce bu seçenekleri ayarlamanız gerekir.

## <a name="closing-a-recordset"></a><a name="_core_closing_a_recordset"></a>Kayıt Kümesini Kapatma

Kayıt setinizle bitirdiğinizde, onu elden çıkarmalı ve hafızasını ayarlamanız gerekir.

#### <a name="to-close-a-recordset"></a>Kayıt kümesini kapatmak için

1. [Yakın](../../mfc/reference/crecordset-class.md#close) üye işlevini arayın.

1. Kayıt kümesi nesnesini yok edin.

   Bir işlevin yığın çerçevesi üzerinde beyan ettiyseniz, nesne kapsam dışına çıktığında nesne otomatik olarak yok edilir. Aksi takdirde, **silme** işleci kullanın.

`Close`kayıt kümesinin `HSTMT` tutamacını serbest bırakarak serbest kalır. C++ nesnesini yok etmez.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)
