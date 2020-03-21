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
ms.openlocfilehash: e7aa4c0fc2a0acfe7b8df2f50f99bf44eb1ef456
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075914"
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>Kayıt Kümesi: Kayıt Kümeleri Oluşturma ve Kapatma (ODBC)

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Yine de bir tüketicisi el ile oluşturabilirsiniz.

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir kayıt kümesi kullanmak için bir kayıt kümesi nesnesi oluşturun ve ardından kayıt kümesinin sorgusunu çalıştırmak ve kayıtlar ' ı seçmek üzere `Open` üye işlevini çağırın. Kayıt kümesiyle bitirdiğinizde nesneyi kapatın ve yok edin.

Bu konuda aşağıdakiler açıklanmaktadır:

- [Bir kayıt kümesi nesnesi ne zaman ve nasıl oluşturulur](#_core_creating_recordsets_at_run_time).

- [Ne zaman ve, filtre uygulayan, filtreleyerek, sıralayarak veya kilitleyerek kayıt kümesinin davranışını nasıl niteleyebilirsiniz?](#_core_setting_recordset_options)

- [Bir kayıt kümesi nesnesini ne zaman ve nasıl kapatırsınız](#_core_closing_a_recordset).

##  <a name="creating-recordsets-at-run-time"></a><a name="_core_creating_recordsets_at_run_time"></a>Çalışma zamanında kayıt kümeleri oluşturma

Programınızda kayıt kümesi nesneleri oluşturabilmeniz için, genellikle uygulamaya özel kayıt kümesi sınıfları yazarsınız. Bu ön adım hakkında daha fazla bilgi için bkz. [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).

Bir veri kaynağından kayıtlar seçmeniz gerektiğinde bir Dynaset veya anlık görüntü nesnesi açın. Oluşturulacak nesnenin türü, uygulamanızdaki verilerle ne yapmanız gerektiğini ve ODBC sürücünüzün neleri desteklediğine bağlıdır. Daha fazla bilgi için bkz. [Dynaset](../../data/odbc/dynaset.md) ve [anlık görüntü](../../data/odbc/snapshot.md).

#### <a name="to-open-a-recordset"></a>Bir kayıt kümesi açmak için

1. `CRecordset`türetilmiş sınıfınızın bir nesnesini oluşturun.

   Nesneyi yığında veya bir işlevin yığın çerçevesinde oluşturabilirsiniz.

1. İsteğe bağlı olarak varsayılan kayıt kümesi davranışını değiştirin. Kullanılabilir seçenekler için bkz. [kayıt kümesi seçeneklerini ayarlama](#_core_setting_recordset_options).

1. Nesnenin [Open](../../mfc/reference/crecordset-class.md#open) üye işlevini çağırın.

Oluşturucuda, `CDatabase` nesnesine bir işaretçi geçirin veya bir veri geçirin ve bu nesnenin, [GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) üye işlevi tarafından döndürülen bağlantı dizesine göre oluşturduğu ve açtığı geçici bir veritabanı nesnesini kullanın. `CDatabase` nesnesi zaten bir veri kaynağına bağlı olabilir.

`Open` çağrısı, veri kaynağından kayıtları seçmek için SQL 'i kullanır. Seçilen ilk kayıt (varsa) geçerli kayıttır. Bu kaydın alanlarının değerleri, kayıt kümesi nesnesinin alan veri üyelerinde depolanır. Herhangi bir kayıt seçildiyse, hem `IsBOF` hem de `IsEOF` üye işlevleri 0 döndürür.

[Açık](../../mfc/reference/crecordset-class.md#open) çağrın içinde şunları yapabilirsiniz:

- Kayıt kümesinin bir Dynaset mi yoksa anlık görüntü mi olduğunu belirtin. Kayıt kümeleri varsayılan olarak anlık görüntüler olarak açılır. Ya da, tek seferde bir kayıt olmak üzere yalnızca ileriye doğru kaydırmaya izin veren bir salt iletme kayıt kümesi belirtebilirsiniz.

   Varsayılan olarak, bir kayıt kümesi `CRecordset` veri üyesi `m_nDefaultType`depolanan varsayılan türü kullanır. Sihirbazlar, sihirbazda seçtiğiniz kayıt kümesi türüne `m_nDefaultType` başlatmak için kod yazar. Bu varsayılanı kabul etmek yerine, başka bir kayıt kümesi türünü değiştirebilirsiniz.

- Kayıt kümesini oluşturan varsayılan SQL **Select** ifadesini değiştirmek için bir dize belirtin.

- Kayıt kümesinin salt okunurdur mi yoksa salt Ekle mi olduğunu belirtin. Kayıt kümeleri varsayılan olarak tam güncelleştirmeye izin verir, ancak bunu yalnızca yeni kayıtlar eklemeye veya tüm güncelleştirmelere izin vermemeyi sınırlayabilirsiniz.

Aşağıdaki örnek, uygulamaya özgü bir sınıf olan `CStudentSet`sınıfının salt okunurdur bir anlık görüntü nesnesinin nasıl açılacağını gösterir:

```cpp
// Construct the snapshot object
CStudentSet rsStudent( NULL );
// Set options if desired, then open the recordset
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))
    return FALSE;
// Use the snapshot to operate on its records...
```

`Open`çağırdıktan sonra, kayıtlarla çalışmak için nesnenin üye işlevlerini ve veri üyelerini kullanın. Bazı durumlarda, veri kaynağında gerçekleşen değişiklikleri dahil etmek için kayıt kümesini yeniden sorgulamak veya yenilemek isteyebilirsiniz. Daha fazla bilgi için bkz. [kayıt kümesi: bir kayıt kümesini yeniden sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).

> [!TIP]
>  Geliştirme sırasında kullandığınız bağlantı dizesi, son kullanıcılarınızın ihtiyacı olan bağlantı dizesi olmayabilir. Uygulamanızı bu şekilde genelleştirerek, bkz. [veri kaynağı: bağlantıları yönetme (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md).

##  <a name="setting-recordset-options"></a><a name="_core_setting_recordset_options"></a>Kayıt kümesi seçeneklerini ayarlama

Kayıt kümesi nesnenizi oluşturduktan sonra, kayıtları seçmek için `Open` çağırmadan önce, kayıt kümesinin davranışını denetlemek için bazı seçenekler ayarlamak isteyebilirsiniz. Tüm kayıt kümelerinde şunları yapabilirsiniz:

- Kayıt seçimini kısıtlamak için bir [filtre](../../data/odbc/recordset-filtering-records-odbc.md) belirtin.

- Kayıtlar için bir [sıralama](../../data/odbc/recordset-sorting-records-odbc.md) düzeni belirtin.

- Çalışma zamanında alınan veya hesaplanan bilgileri kullanarak kayıtları seçebilmeniz için [parametreleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) belirtin.

Koşullar doğru ise aşağıdaki seçeneği de ayarlayabilirsiniz:

- Kayıt kümesi güncelleştirilebilir ise ve kilitleme seçeneklerini destekliyorsa, güncelleştirmeler için kullanılan [kilitleme](../../data/odbc/recordset-locking-records-odbc.md) yöntemini belirtin.

> [!NOTE]
>  Kayıt seçimini etkilemek için, `Open` üye işlevini çağırmadan önce bu seçenekleri ayarlamanız gerekir.

##  <a name="closing-a-recordset"></a><a name="_core_closing_a_recordset"></a>Kayıt kümesini kapatma

Kayıt kümeniz ile bitirdiğinizde, bunu atmalısınız ve belleğini serbest bırakın.

#### <a name="to-close-a-recordset"></a>Bir kayıt kümesini kapatmak için

1. [Close](../../mfc/reference/crecordset-class.md#close) üye işlevini çağırın.

1. Kayıt kümesi nesnesini yok edin.

   Bir işlevin yığın çerçevesinde bildirdiyseniz, nesne kapsam dışına geçtiğinde nesne otomatik olarak yok edilir. Aksi takdirde, **Delete** işlecini kullanın.

`Close` kayıt kümesinin `HSTMT` tanıtıcısını serbest bırakır. C++ Nesneyi yok etmez.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)