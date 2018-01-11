---
title: "Kayıt kümesi: Oluşturma ve kayıt kümeleri (ODBC) kapatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC recordsets, creating
- recordsets, creating
- recordsets, opening
- recordsets, closing
- ODBC recordsets, closing
- ODBC recordsets, opening
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9ec09c08aa4730c11960d675aef68c8a1007c900
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>Kayıt Kümesi: Kayıt Kümeleri Oluşturma ve Kapatma (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bir kayıt kümesi kullanmak için bir kayıt kümesi nesnesi oluşturun ve ardından çağıran kendi **açık** kümesinin sorgusunu çalıştırmak ve kayıtları seçmek için üye işlevi. Kayıt kümesi ile işiniz bittiğinde, kapatın ve nesne yok.  
  
 Bu konuda açıklanmaktadır:  
  
-   [Bir kayıt kümesi nesnesi oluşturmak nasıl ve ne zaman](#_core_creating_recordsets_at_run_time).  
  
-   [Ne zaman ve nasıl kayıt kümesinin davranış kümesini parametreleştirme, filtreleme, sıralama veya kilitleyerek tarafından nitelemek](#_core_setting_recordset_options).  
  
-   [Ne zaman ve nasıl kayıt kümesi nesnesi kapatma](#_core_closing_a_recordset).  
  
##  <a name="_core_creating_recordsets_at_run_time"></a>Çalışma zamanında kayıt kümeleri oluşturma  
 Kayıt kümesi nesneleri programınıza oluşturmadan önce uygulamaya özgü kayıt kümesi sınıfları genellikle yazma. Bu ön adım hakkında daha fazla bilgi için bkz: [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Bir veri kaynağından kayıtları seçmek gerektiğinde bir dynaset veya anlık görüntü nesnesi açın. Gerçekleştirmeniz gereken üzerinde oluşturulacak nesne türüne bağlıdır verilerle uygulamanız ve ODBC sürücünüzün neyi destekler. Daha fazla bilgi için bkz: [Dynaset](../../data/odbc/dynaset.md) ve [anlık görüntü](../../data/odbc/snapshot.md).  
  
#### <a name="to-open-a-recordset"></a>Bir kayıt kümesi açmak için  
  
1.  Bir nesne oluşturun, `CRecordset`-türetilmiş sınıf.  
  
     Nesneyi yığında veya işlevin yığın çerçevesinde oluşturabilirsiniz.  
  
2.  İsteğe bağlı olarak varsayılan kayıt kümesi davranışını değiştirin. Kullanılabilir seçenekler için bkz [kayıt kümesi seçeneklerini ayarlama](#_core_setting_recordset_options).  
  
3.  Nesnenin çağrı [açık](../../mfc/reference/crecordset-class.md#open) üye işlevi.  
  
 Oluşturucuda geçirmek için bir işaretçi bir `CDatabase` nesne veya geçirmek **NULL** geçici bir kullanılacak framework oluşturur ve açılır veritabanı nesnesi tarafından döndürülen bağlantı dizesini dayalı [GetDefaultConnect ](../../mfc/reference/crecordset-class.md#getdefaultconnect) üye işlevi. `CDatabase` Nesnesi zaten bir veri kaynağına bağlı.  
  
 Çağrı **açık** SQL veri kaynağından kayıtları seçmek için kullanır. (Varsa) seçilen ilk kayıt geçerli kayıttır. Bu kaydın alanların değerlerini kayıt kümesi nesnesinin alan veri üyeleri depolanır. Herhangi bir kayıt seçildiyse, hem `IsBOF` ve `IsEOF` üye işlevleri 0 döndürür.  
  
 İçinde [açık](../../mfc/reference/crecordset-class.md#open) çağrısı, şunları yapabilirsiniz:  
  
-   Kayıt kümesi dynaset veya anlık görüntü olup olmadığını belirtin. Kayıt kümeleri anlık görüntüleri olarak varsayılan olarak açar. Veya yalnızca ileri kaydırma, aynı anda tek bir kayıtta sağlayan bir salt iletme kayıt belirtebilirsiniz.  
  
     Varsayılan olarak, bir kayıt kümesi depolanan varsayılan türünü kullanan `CRecordset` veri üyesi **m_nDefaultType**. Sihirbazlar başlatmak için kod yazma **m_nDefaultType** sihirbazda seçtiğiniz kayıt kümesi türü. Bu varsayılanı kabul etmek yerine başka bir kayıt kümesi türü yerine kullanabilirsiniz.  
  
-   Varsayılan SQL değiştirmek için bir dize belirtin **seçin** deyimi kayıt kümesi oluşturur.  
  
-   Kayıt kümesi salt okunur veya salt sonuna olup olmadığını belirtin. Kayıt kümeleri varsayılan olarak, güncelleştirme tam izin ancak, yeni kayıtları eklemeye yalnızca sınırlandırabilir veya tüm güncelleştirmeler engelleyebilirsiniz.  
  
 Aşağıdaki örnek, sınıfın bir salt okunur anlık görüntü nesnesi açmak gösterilmiştir `CStudentSet`, uygulamaya özgü sınıfı:  
  
```  
// Construct the snapshot object  
CStudentSet rsStudent( NULL );  
// Set options if desired, then open the recordset  
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))  
    return FALSE;  
// Use the snapshot to operate on its records...  
```  
  
 Çağırdıktan sonra **açık**, nesne üye işlevleri ve veri üyeleri kayıtlarıyla çalışmak için kullanın. Bazı durumlarda, requery veya veri kaynağı üzerinde gerçekleşen değişiklikleri dahil etmek için kayıt yenileme isteyebilirsiniz. Daha fazla bilgi için bkz: [kayıt kümesi: bir kayıt kümesi (ODBC) yeniden sorgulama](../../data/odbc/recordset-requerying-a-recordset-odbc.md).  
  
> [!TIP]
>  Geliştirme sırasında kullandığınız bağlantı dizesini son kullanıcılarınıza aynı bağlantı dizesini olmayabilir. Uygulamanız bu bağlamda genelleştirme hakkında daha fazla fikir için bkz: [veri kaynağı: bağlantıları yönetme (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md).  
  
##  <a name="_core_setting_recordset_options"></a>Kayıt kümesi seçeneklerini ayarlama  
 Kayıt kümesi nesnenizi oluşturduktan sonra ancak çağırmadan önce **açık** kayıtları seçmek için kayıt kümesinin davranışını denetlemek için bazı seçenekleri ayarlamak isteyebilirsiniz. Tüm kayıt kümeleri için şunları yapabilirsiniz:  
  
-   Belirtin bir [filtre](../../data/odbc/recordset-filtering-records-odbc.md) kayıt seçimi sınırlamak için.  
  
-   Belirtin bir [sıralama](../../data/odbc/recordset-sorting-records-odbc.md) kayıtlar için düzeni.  
  
-   Belirtin [parametreleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) çalışma zamanında hesaplanan veya alınan bilgileri kullanarak kayıtları seçebilmek için.  
  
 Koşullar doğru olduğunda aşağıdaki iki seçenek de ayarlayabilirsiniz:  
  
-   Kayıt kümesi güncelleştirilebilir ve kilitleme seçeneklerini destekliyorsa, belirtin [kilitleme](../../data/odbc/recordset-locking-records-odbc.md) güncelleştirmeler için kullanılan yöntem.  
  
> [!NOTE]
>  Arama yapmadan önce kayıt seçimini etkilemek için bu seçenekleri ayarlamalısınız **açık** üye işlevi.  
  
##  <a name="_core_closing_a_recordset"></a>Bir kayıt kümesini kapatma  
 Kümenizin ile işiniz bittiğinde, bunu dispose ve kendi bellek ayırması gerekir.  
  
#### <a name="to-close-a-recordset"></a>Kayıt kümesi kapatmak için  
  
1.  Çağrı kendi [Kapat](../../mfc/reference/crecordset-class.md#close) üye işlevi.  
  
2.  Kayıt kümesi nesnesi yok.  
  
     Bir işlev yığın çerçevesi üzerinde bildirilen, nesne kapsam dışına çıktığında nesnesi otomatik olarak yok. Aksi takdirde kullanın **silmek** işleci.  
  
 **Kapat** kümesinin boşaltır **HSTMT** işler. C++ nesne yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)   
 [Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)