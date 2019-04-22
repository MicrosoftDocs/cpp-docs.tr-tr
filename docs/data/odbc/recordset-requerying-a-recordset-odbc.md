---
title: 'Kayıt kümesi: (ODBC) bir kayıt kümesinde yeniden sorgulama'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
ms.openlocfilehash: 7edc1c04da617f96165b25a47ce169b266ae0003
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024601"
---
# <a name="recordset-requerying-a-recordset-odbc"></a>Kayıt kümesi: (ODBC) bir kayıt kümesinde yeniden sorgulama

Bu konu MFC ODBC sınıflarına uygulanır.

Bu konu, yeniden sorgulamak için bir kayıt kümesi nesnesi nasıl kullanabileceğinizi açıklar (diğer bir deyişle, Yenile) kendisi veritabanından ve bunun isteyebileceğiniz [Requery](../../mfc/reference/crecordset-class.md#requery) üye işlevi.

Bir kayıt kümesinde yeniden sorgulama için asıl nedeni vardır:

- Kayıt kümesi, veya diğer kullanıcılar tarafından eklenen kayıtlar ve (Bu silmeniz zaten kümenize yansıtılır) diğer kullanıcılar tarafından silinen kayıtlar ile ilgili güncel duruma getirin.

- Parametre değerlerini değişen dayalı kayıt kümesini yenileyin.

##  <a name="_core_bringing_the_recordset_up_to_date"></a> Kayıt güncelleme

Genelde, bunu getirmek için kayıt kümesi nesnesi requery güncel isteyebilirsiniz. Çok kullanıcılı veritabanı ortamında, diğer kullanıcılar için veri kümenizin ömrü sırasında değişiklik yapabilirsiniz. Ne zaman kümenizin diğer kullanıcılar tarafından yapılan değişiklikleri yansıtır ve ne zaman diğer kullanıcıların kayıt kümeleri yaptığınız değişiklikleri yansıtacak hakkında daha fazla bilgi için bkz. [kayıt kümesi: Kümelerinin kayıtları Güncelleştirmesi (ODBC) kayıtları](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) ve [Dynaset](../../data/odbc/dynaset.md).

##  <a name="_core_requerying_based_on_new_parameters"></a> Yeni parametrelere göre kümesinde yeniden sorgulama

Sık yapmanız gereken başka — ve eşit oranda önemli — kullanım [Requery](../../mfc/reference/crecordset-class.md#requery) yeni bir parametre değerlerini değişen dayalı kayıt kümesi seçeneğini belirlemektir.

> [!TIP]
>  Sorgu hızı çağırırsanız büyük olasılıkla önemli ölçüde daha hızlı `Requery` parametre değerleriyle çağırın, değişen `Open` yeniden.

##  <a name="_core_requerying_dynasets_vs.._snapshots"></a> Dynaset'ler vs kümesinde yeniden sorgulama. Anlık görüntüleri

Dynaset'ler dinamik güncel verilerle bir kayıt kümesi sunmak için nedeni, genellikle diğer kullanıcıların eklemeleri yansıtacak şekilde istiyorsanız dynaset'ler requery istiyorsunuz. Anlık görüntüler, diğer taraftan, raporlar hazırlama toplamları hesaplamak ve benzeri statik içerikleri güvenli bir şekilde güvenebilirsiniz olduğundan kullanışlıdır. Yine de, bazen de bir anlık görüntü requery isteyebilirsiniz. Diğer kullanıcıların veritabanını değiştirdikçe çok kullanıcılı bir ortamda veri kaynağı ile eşitleme anlık görüntü veriler kaybedilebilir.

#### <a name="to-requery-a-recordset-object"></a>Kayıt kümesi nesnesi yeniden sorgulamak için

1. Çağrı [Requery](../../mfc/reference/crecordset-class.md#requery) nesnesinin üye işlevi.

Alternatif olarak, kapatın ve özgün kayıt yeniden açın. Her iki durumda da, yeni kayıt veri kaynağı geçerli durumunu temsil eder.

Bir örnek için bkz [kayıt görünümleri: İkinci kayıt kümesinden liste kutusunu doldurma](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).

> [!TIP]
>  En iyi duruma getirme `Requery` performans, kayıt kümesinin değiştirmekten kaçının [filtre](../../data/odbc/recordset-filtering-records-odbc.md) veya [sıralama](../../data/odbc/recordset-sorting-records-odbc.md). Parametre değeri yalnızca çağırmadan önce değiştirme `Requery`.

Varsa `Requery` çağrısı başarısız olur, çağrıyı yeniden deneyin; Aksi takdirde, uygulamanızın düzgün bir şekilde sonlandırması gerekir. Bir çağrı `Requery` veya `Open` herhangi bir dizi nedenden biri için başarısız olabilir. Belki de bir ağ hatası oluşur; veya, arama sırasında var olan verileri yayımlandıktan sonra ancak yeni veriler elde edilen önce başka bir kullanıcı özel erişim alabilirsiniz; veya bağımlı olduğu kayıt tablosu silinemedi.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: (ODBC) veri sütunlarını dinamik olarak bağlama](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[Kayıt kümesi: Oluşturma ve kapatma (ODBC) kayıt kümeleri](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)