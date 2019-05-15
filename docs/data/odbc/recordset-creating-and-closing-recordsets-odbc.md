---
title: 'Kayıt kümesi: Oluşturma ve kapatma (ODBC) kayıt kümeleri'
ms.date: 05/09/2019
helpviewer_keywords:
- ODBC recordsets, creating
- recordsets, creating
- recordsets, opening
- recordsets, closing
- ODBC recordsets, closing
- ODBC recordsets, opening
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
ms.openlocfilehash: b4896dff711d87db05334afc0345c15da2fa23e6
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707993"
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>Kayıt kümesi: Oluşturma ve kapatma (ODBC) kayıt kümeleri

> [!NOTE] 
> MFC ODBC Tüketici Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil. Bir tüketici yine de el ile oluşturabilirsiniz.

Bu konu MFC ODBC sınıflarına uygulanır.

Bir kayıt kümesini kullanmak için bir kayıt kümesi nesnesi oluşturun ve sonra çağrı kendi `Open` kümesinin sorgusunu çalıştırın ve kayıtları seçmek için üye işlevi. Kayıt kümesi ile işiniz bittiğinde kapatın ve nesne yok.

Bu konu şunları açıklar:

- [Bir kayıt kümesi nesnesi oluşturmak nasıl ve ne zaman](#_core_creating_recordsets_at_run_time).

- [Ne zaman ve nasıl kayıt kümesinin davranışını kümesini parametreleştirme, filtreleme, sıralama veya kilitleyerek belirtebilme](#_core_setting_recordset_options).

- [Ne zaman ve nasıl kayıt kümesi nesnesi kapatma](#_core_closing_a_recordset).

##  <a name="_core_creating_recordsets_at_run_time"></a> Çalışma zamanında kayıt kümeleri oluşturma

Programınızda kayıt nesneleri oluşturmadan önce genellikle uygulamaya özgü kayıt kümesi sınıfları yazın. Bu ilk adım hakkında daha fazla bilgi için bkz: [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).

Bir veri kaynağındaki kayıtları seçmek gerektiğinde dinamik veya anlık görüntü bir nesneyi açın. Oluşturulacak nesne türü için yapmanız gerekenler üzerinde bağlıdır verilerle uygulamanız ve hangi ODBC sürücüsünün destekler. Daha fazla bilgi için [Dynaset](../../data/odbc/dynaset.md) ve [anlık görüntü](../../data/odbc/snapshot.md).

#### <a name="to-open-a-recordset"></a>Bir kayıt kümesi açmak için

1. Bir nesne oluşturun, `CRecordset`-türetilmiş sınıf.

   Yığın veya yığın çerçevesi bir işlev nesnesi oluşturabilirsiniz.

1. İsteğe bağlı olarak varsayılan kayıt davranışını değiştirin. Kullanılabilir seçenekleri için bkz. [ayarı kayıt seçenekleri](#_core_setting_recordset_options).

1. Nesnenin [açık](../../mfc/reference/crecordset-class.md#open) üye işlevi.

Oluşturucusunun içinde bir işaretçi geçirin bir `CDatabase` nesne veya framework oluşturan bir geçici veritabanı nesnesini kullanmak için NULL ve açılır tarafından döndürülen bağlantı dizesini geçirin [GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) üye işlevi. `CDatabase` Nesnesi zaten bağlı bir veri kaynağına.

Çağrı `Open` SQL veri kaynağından kayıtları seçmek için kullanır. (Varsa) seçilen ilk kayıt geçerli bir kayıttır. Kayıt kümesi nesnenin alan veri üyeleri bu kaydın alanlarının değerlerini depolanır. Herhangi bir kayıt seçildiyse, hem `IsBOF` ve `IsEOF` üye işlevleri, 0 döndürür.

İçinde [açık](../../mfc/reference/crecordset-class.md#open) çağrı, şunları yapabilirsiniz:

- Kayıt kümesi bir dinamik anlık görüntü olup olmadığını belirtin. Kayıt kümeleri varsayılan olarak anlık görüntü olarak açın. Veya yalnızca ileri kaydırma, aynı anda tek bir kayıtta sağlayan bir salt iletme kayıt belirtebilirsiniz.

   Varsayılan olarak, bir kayıt kümesi içinde depolanan varsayılan türü kullanır. `CRecordset` veri üyesi `m_nDefaultType`. Sihirbazları başlatmak için kod yazma `m_nDefaultType` sihirbazda seçtiğiniz kayıt kümesi türü. Bu varsayılanı kabul etmek yerine başka bir kayıt kümesi türü yerine kullanabilirsiniz.

- Varsayılan SQL değiştirmek için bir dize belirtin **seçin** kayıt kümesini oluşturan bir ifade.

- Kayıt kümesi salt okunur veya salt olup olmadığını belirtin. Kayıt kümeleri varsayılan olarak, güncelleştirme tam izin ver, ancak, yeni kayıtları eklemeye yalnızca sınırlayabilirsiniz veya tüm güncelleştirmeleri engelleyebilirsiniz.

Aşağıdaki örnek, sınıfın bir salt okunur anlık görüntü nesnesi açmak gösterilmektedir `CStudentSet`, uygulamaya özgü sınıfı:

```cpp
// Construct the snapshot object
CStudentSet rsStudent( NULL );
// Set options if desired, then open the recordset
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))
    return FALSE;
// Use the snapshot to operate on its records...
```

Çağırdıktan sonra `Open`, nesnenin üye işlevleri ve veri üyelerine kayıtlarıyla çalışmak üzere kullanın. Bazı durumlarda, requery veya veri kaynağı üzerinde oluşan değişikliklerin eklenmesi için kayıt kümesini yenilemek isteyebilirsiniz. Daha fazla bilgi için [kayıt kümesi: (ODBC) bir kayıt kümesinde yeniden sorgulama](../../data/odbc/recordset-requerying-a-recordset-odbc.md).

> [!TIP]
>  Geliştirme sırasında kullandığınız bağlantı dizesi, son kullanıcılarınızın gereken aynı bağlantı dizesini olmayabilir. Bu konuda, uygulamanızın genelleştiriliyor hakkında daha fazla fikir için bkz [veri kaynağı: Bağlantıları yönetme (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md).

##  <a name="_core_setting_recordset_options"></a> Kayıt kümesi seçeneklerini ayarlama

Kayıt kümesi nesnenizi oluşturduktan sonra ancak çağırmadan önce `Open` kayıtları seçmek için kayıt kümesinin davranışını denetlemek için bazı seçenekleri ayarlamak isteyebilirsiniz. Tüm kayıt kümelerini için şunları yapabilirsiniz:

- Belirtin bir [filtre](../../data/odbc/recordset-filtering-records-odbc.md) kayıt seçimi sınırlamak için.

- Belirtin bir [sıralama](../../data/odbc/recordset-sorting-records-odbc.md) kayıtlar için düzeni.

- Belirtin [parametreleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) alınan veya çalışma zamanında hesaplanan bilgileri kullanarak kayıtları seçebilmeniz için.

Koşullar doğru olduğunda, aşağıdaki seçeneği ayarlayabilirsiniz:

- Kayıt kümesi güncelleştirilemez ve kilitleme seçenekleri destekler, belirtin [kilitleme](../../data/odbc/recordset-locking-records-odbc.md) güncelleştirmeleri için kullanılan yöntem.

> [!NOTE]
>  Çağırmadan önce kayıt seçimini etkilemek için bu seçenekleri ayarlamalısınız `Open` üye işlevi.

##  <a name="_core_closing_a_recordset"></a> Bir kayıt kümesi kapatma

Kümenizin ile işiniz bittiğinde, atabilirsiniz ve kendi bellek ayırması gerekir.

#### <a name="to-close-a-recordset"></a>Bir kayıt kümesi kapatmak için

1. Çağrı, [Kapat](../../mfc/reference/crecordset-class.md#close) üye işlevi.

1. Kayıt kümesi nesnesi yok.

   Yığın çerçevesinin işlev üzerinde bildirilen, nesne kapsam dışına çıktığında, nesne otomatik olarak yok edilir. Aksi takdirde kullanın **Sil** işleci.

`Close` kayıt kümesi boşaltır `HSTMT` tanıtıcı. C++ nesne yok.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Kaydırma (ODBS)](../../data/odbc/recordset-scrolling-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)