---
description: 'Daha fazla bilgi: kayıt kümesi: kayıt kümeleri oluşturma ve kapatma (ODBC)'
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
ms.openlocfilehash: a8c79afe483ab9fcd03b2102ec93d6574092acf3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186109"
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>Kayıt Kümesi: Kayıt Kümeleri Oluşturma ve Kapatma (ODBC)

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Yine de bir tüketicisi el ile oluşturabilirsiniz.

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir kayıt kümesi kullanmak için bir kayıt kümesi nesnesi oluşturun ve ardından kayıt `Open` kümesi sorgusunu çalıştırmak ve kayıtlar ' ı seçmek için üye işlevini çağırın. Kayıt kümesiyle bitirdiğinizde nesneyi kapatın ve yok edin.

Bu konuda aşağıdakiler açıklanmaktadır:

- [Bir kayıt kümesi nesnesi ne zaman ve nasıl oluşturulur](#_core_creating_recordsets_at_run_time).

- [Ne zaman ve, filtre uygulayan, filtreleyerek, sıralayarak veya kilitleyerek kayıt kümesinin davranışını nasıl niteleyebilirsiniz?](#_core_setting_recordset_options)

- [Bir kayıt kümesi nesnesini ne zaman ve nasıl kapatırsınız](#_core_closing_a_recordset).

## <a name="creating-recordsets-at-run-time"></a><a name="_core_creating_recordsets_at_run_time"></a> Çalışma zamanında kayıt kümeleri oluşturma

Programınızda kayıt kümesi nesneleri oluşturabilmeniz için, genellikle uygulamaya özel kayıt kümesi sınıfları yazarsınız. Bu ön adım hakkında daha fazla bilgi için bkz. [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).

Bir veri kaynağından kayıtlar seçmeniz gerektiğinde bir Dynaset veya anlık görüntü nesnesi açın. Oluşturulacak nesnenin türü, uygulamanızdaki verilerle ne yapmanız gerektiğini ve ODBC sürücünüzün neleri desteklediğine bağlıdır. Daha fazla bilgi için bkz. [Dynaset](../../data/odbc/dynaset.md) ve [anlık görüntü](../../data/odbc/snapshot.md).

#### <a name="to-open-a-recordset"></a>Bir kayıt kümesi açmak için

1. Türetilmiş sınıfınızın bir nesnesini oluşturun `CRecordset` .

   Nesneyi yığında veya bir işlevin yığın çerçevesinde oluşturabilirsiniz.

1. İsteğe bağlı olarak varsayılan kayıt kümesi davranışını değiştirin. Kullanılabilir seçenekler için bkz. [kayıt kümesi seçeneklerini ayarlama](#_core_setting_recordset_options).

1. Nesnenin [Open](../../mfc/reference/crecordset-class.md#open) üye işlevini çağırın.

Oluşturucuda, bir nesneye bir işaretçi geçirin veya bir `CDatabase` veri geçirin ve bu nesnenin, [GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) üye işlevi tarafından döndürülen bağlantı dizesine göre oluşturduğu ve açtığı geçici bir veritabanı nesnesi kullanın. `CDatabase`Nesne zaten bir veri kaynağına bağlanmış olabilir.

`Open`Veri kaynağından kayıtları seçmek IÇIN SQL 'i kullanma çağrısı. Seçilen ilk kayıt (varsa) geçerli kayıttır. Bu kaydın alanlarının değerleri, kayıt kümesi nesnesinin alan veri üyelerinde depolanır. Herhangi bir kayıt seçildiyse, hem hem de `IsBOF` `IsEOF` üye işlevleri 0 döndürür.

[Açık](../../mfc/reference/crecordset-class.md#open) çağrın içinde şunları yapabilirsiniz:

- Kayıt kümesinin bir Dynaset mi yoksa anlık görüntü mi olduğunu belirtin. Kayıt kümeleri varsayılan olarak anlık görüntüler olarak açılır. Ya da, tek seferde bir kayıt olmak üzere yalnızca ileriye doğru kaydırmaya izin veren bir salt iletme kayıt kümesi belirtebilirsiniz.

   Varsayılan olarak, bir kayıt kümesi veri üyesinde depolanan varsayılan türü kullanır `CRecordset` `m_nDefaultType` . Sihirbazlar `m_nDefaultType` , sihirbazda seçtiğiniz kayıt kümesi türüne başlatılacak kodu yazar. Bu varsayılanı kabul etmek yerine, başka bir kayıt kümesi türünü değiştirebilirsiniz.

- Kayıt kümesini oluşturan varsayılan SQL **Select** ifadesini değiştirmek için bir dize belirtin.

- Kayıt kümesinin salt okunurdur mi yoksa salt Ekle mi olduğunu belirtin. Kayıt kümeleri varsayılan olarak tam güncelleştirmeye izin verir, ancak bunu yalnızca yeni kayıtlar eklemeye veya tüm güncelleştirmelere izin vermemeyi sınırlayabilirsiniz.

Aşağıdaki örnek `CStudentSet` , uygulamaya özgü bir sınıf olan sınıfının salt okunurdur anlık görüntü nesnesinin nasıl açılacağını gösterir:

```cpp
// Construct the snapshot object
CStudentSet rsStudent( NULL );
// Set options if desired, then open the recordset
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))
    return FALSE;
// Use the snapshot to operate on its records...
```

Öğesini çağırdıktan sonra `Open` , kayıtlarla çalışmak için nesnenin üye işlevlerini ve veri üyelerini kullanın. Bazı durumlarda, veri kaynağında gerçekleşen değişiklikleri dahil etmek için kayıt kümesini yeniden sorgulamak veya yenilemek isteyebilirsiniz. Daha fazla bilgi için bkz. [kayıt kümesi: bir kayıt kümesini yeniden sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).

> [!TIP]
> Geliştirme sırasında kullandığınız bağlantı dizesi, son kullanıcılarınızın ihtiyacı olan bağlantı dizesi olmayabilir. Uygulamanızı bu şekilde genelleştirerek, bkz. [veri kaynağı: bağlantıları yönetme (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md).

## <a name="setting-recordset-options"></a><a name="_core_setting_recordset_options"></a> Kayıt kümesi seçeneklerini ayarlama

Kayıt kümesi nesnenizi oluşturduktan sonra ancak `Open` kayıtları seçme ' yi çağırmadan önce, kayıt kümesinin davranışını denetlemek için bazı seçenekler ayarlamak isteyebilirsiniz. Tüm kayıt kümelerinde şunları yapabilirsiniz:

- Kayıt seçimini kısıtlamak için bir [filtre](../../data/odbc/recordset-filtering-records-odbc.md) belirtin.

- Kayıtlar için bir [sıralama](../../data/odbc/recordset-sorting-records-odbc.md) düzeni belirtin.

- Çalışma zamanında alınan veya hesaplanan bilgileri kullanarak kayıtları seçebilmeniz için [parametreleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) belirtin.

Koşullar doğru ise aşağıdaki seçeneği de ayarlayabilirsiniz:

- Kayıt kümesi güncelleştirilebilir ise ve kilitleme seçeneklerini destekliyorsa, güncelleştirmeler için kullanılan [kilitleme](../../data/odbc/recordset-locking-records-odbc.md) yöntemini belirtin.

> [!NOTE]
> Kayıt seçimini etkilemek için, üye işlevini çağırmadan önce bu seçenekleri ayarlamanız gerekir `Open` .

## <a name="closing-a-recordset"></a><a name="_core_closing_a_recordset"></a> Kayıt kümesini kapatma

Kayıt kümeniz ile bitirdiğinizde, bunu atmalısınız ve belleğini serbest bırakın.

#### <a name="to-close-a-recordset"></a>Bir kayıt kümesini kapatmak için

1. [Close](../../mfc/reference/crecordset-class.md#close) üye işlevini çağırın.

1. Kayıt kümesi nesnesini yok edin.

   Bir işlevin yığın çerçevesinde bildirdiyseniz, nesne kapsam dışına geçtiğinde nesne otomatik olarak yok edilir. Aksi takdirde işlecini kullanın **`delete`** .

`Close` kayıt kümesinin tanıtıcısını serbest bırakır `HSTMT` . C++ nesnesini yok etmez.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Kaydırma (ODBS)](../../data/odbc/recordset-scrolling-odbc.md)<br/>
[Kayıt kümesi: kayıtları ekleme, güncelleştirme ve silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)
