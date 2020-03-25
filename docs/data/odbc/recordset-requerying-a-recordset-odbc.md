---
title: 'Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
ms.openlocfilehash: b7cf40ca3b0c8e415368772063aee61008a52764
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212790"
---
# <a name="recordset-requerying-a-recordset-odbc"></a>Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu, bir kayıt kümesi nesnesini veritabanından veritabanını yeniden sorgulamak (yani yenilemek) için nasıl kullanabileceğinizi ve bunu [YenidenSorgula](../../mfc/reference/crecordset-class.md#requery) üye işleviyle ne zaman yapmak isteyebileceğiniz açıklanmaktadır.

Bir kayıt kümesini yeniden sorgulama için asıl nedenler şunlardır:

- Kayıt kümesini siz veya diğer kullanıcılar tarafından silinen kayıtlar veya diğer kullanıcılar tarafından silinen kayıtlar (kayıt kümesine zaten yansıtılmıştır) göre güncel hale getirin.

- Kayıt kümesini değişen parametre değerlerine göre yenileyin.

##  <a name="bringing-the-recordset-up-to-date"></a><a name="_core_bringing_the_recordset_up_to_date"></a>Kayıt kümesini güncel hale getirme

Genellikle, kayıt kümesini güncel hale getirmek için kayıt kümesi nesnesini yeniden sorgulamak isteyeceksiniz. Çok kullanıcılı bir veritabanı ortamında, diğer kullanıcılar kayıt kümenizin ömrü boyunca verilerde değişiklik yapabilirler. Kayıt kümenizin diğer kullanıcılar tarafından yapılan değişiklikleri yansıtmaları ve diğer kullanıcıların kayıt kümelerinin değişikliklerinizi yansıtması hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıt kümeleri kayıtları güncelleştirme (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) ve [Dynaset](../../data/odbc/dynaset.md).

##  <a name="requerying-based-on-new-parameters"></a><a name="_core_requerying_based_on_new_parameters"></a>Yeni parametrelere göre yeniden sorgulama

Başka bir sık kullanılan ve eşit ölçüde önemli — yeniden [sorgulama](../../mfc/reference/crecordset-class.md#requery) kullanımı, değişen parametre değerlerini temel alan yeni bir kayıt kümesi seçmedir.

> [!TIP]
>  `Open` yeniden çağırdıysanız değişen parametre değerleriyle `Requery` çağırırsanız sorgu hızı büyük olasılıkla daha hızlı bir şekilde daha hızlıdır.

##  <a name="requerying-dynasets-vs-snapshots"></a><a name="_core_requerying_dynasets_vs.._snapshots"></a>Dinamik kümeleri ve anlık görüntüleri yeniden sorgulama

Dinamik kümeler dinamik güncel verilerle bir kayıt kümesi sunabileceğinden, diğer kullanıcıların eklemelerini yansıtmak istiyorsanız dinamik kümeleri yeniden sorgulamak istersiniz. Diğer yandan anlık görüntüler kullanışlıdır, çünkü raporları hazırlarken, toplamları hesaplarken ve benzeri bir statik içeriğine güvenle güvenebilirsiniz. Hala, bazen bir anlık görüntüyü de yeniden sorgulamak isteyebilirsiniz. Çok kullanıcılı bir ortamda, diğer kullanıcılar veritabanını değiştirirken anlık görüntü verileri veri kaynağıyla eşitlemeyi kaybedebilir.

#### <a name="to-requery-a-recordset-object"></a>Bir kayıt kümesi nesnesini yeniden sorgulamak için

1. Nesnenin [Requery](../../mfc/reference/crecordset-class.md#requery) üye işlevini çağırın.

Alternatif olarak, özgün kayıt kümesini kapatabilir ve yeniden açabilirsiniz. Her iki durumda da, yeni kayıt kümesi veri kaynağının geçerli durumunu temsil eder.

Bir örnek için bkz. [Kayıt görünümleri: ikinci bir kayıt kümesinden liste kutusu doldurma](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).

> [!TIP]
>  `Requery` performansını iyileştirmek için, kayıt kümesinin [filtre](../../data/odbc/recordset-filtering-records-odbc.md) veya [sıralamasını](../../data/odbc/recordset-sorting-records-odbc.md)değiştirmekten kaçının. `Requery`çağrılmadan önce yalnızca parametre değerini değiştirin.

`Requery` çağrısı başarısız olursa, çağrıyı yeniden deneyebilirsiniz; Aksi takdirde, uygulamanız düzgün bir şekilde sonlandırılmalıdır. `Requery` veya `Open` çağrısı, herhangi bir sayıda nedenden dolayı başarısız olabilir. Belki de bir ağ hatası oluşuyor; ya da çağrı sırasında, mevcut veriler yayımlandıktan sonra, yeni veriler alınmadan önce, başka bir kullanıcı özel erişim alabilir; ya da kayıt kümenizin bağımlı olduğu tablo silinebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[Kayıt Kümesi: Kayıt Kümeleri Oluşturma ve Kapatma (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)
