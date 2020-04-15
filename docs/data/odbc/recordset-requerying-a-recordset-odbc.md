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
ms.openlocfilehash: cdae28f81eebe8427bc829072e0d9a83c6ec1722
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366953"
---
# <a name="recordset-requerying-a-recordset-odbc"></a>Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu, veritabanından kendisini yeniden sorgulamak için bir kayıt kümesi nesnesini nasıl kullanabileceğinizi (diğer bir şekilde yenilemeyi) ve [bunu Requery](../../mfc/reference/crecordset-class.md#requery) üye işleviyle ne zaman yapmak isteyebileceğinizi açıklar.

Bir kayıt kümesini yeniden sorgulamanın başlıca nedenleri şunlardır:

- Sizin veya diğer kullanıcılar tarafından eklenen kayıtlar ve diğer kullanıcılar tarafından silinen kayıtlar (sildiğiniz kayıtlar zaten kayıt kümesine yansıtılır) ile ilgili olarak kayıtları güncel olarak getirin.

- Değişen parametre değerlerini temel alan kayıt kümesini yenileyin.

## <a name="bringing-the-recordset-up-to-date"></a><a name="_core_bringing_the_recordset_up_to_date"></a>Kayıt Kümesini Tarihe Getirme

Sık sık, güncel getirmek için kayıt kümesi nesnenizi yeniden sorgulamak isteyeceksiniz. Çok kullanıcılı bir veritabanı ortamında, diğer kullanıcılar kayıt setinizin ömrü boyunca verilerde değişiklik yapabilir. Kayıt setinizin diğer kullanıcılar tarafından yapılan değişiklikleri ne zaman yansıttığı ve diğer kullanıcıların kayıt kümelerinin değişikliklerinizi ne zaman yansıttığı hakkında daha fazla bilgi için [Kayıt Kümesi: Kayıtları Nasıl Güncelleştiren (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) ve [Dynaset'e](../../data/odbc/dynaset.md)bakın.

## <a name="requerying-based-on-new-parameters"></a><a name="_core_requerying_based_on_new_parameters"></a>Yeni Parametrelere Göre Yeniden Sorgulama

[Requery'nin](../../mfc/reference/crecordset-class.md#requery) sık ve aynı derecede önemli olan bir diğer kullanımı da değişen parametre değerlerine dayalı yeni bir kayıt kümesi seçmektir.

> [!TIP]
> Parametre değerleri değişen `Requery` arama yaptığınızda sorgu hızı büyük `Open` olasılıkla yeniden arama yaptığınızdan çok daha hızlıdır.

## <a name="requerying-dynasets-vs-snapshots"></a><a name="_core_requerying_dynasets_vs.._snapshots"></a>Dynasets ve Anlık Görüntüleri Yeniden Sorgulama

Dynasets dinamik güncel verilerle bir kayıt kümesi sunmak içindir, çünkü diğer kullanıcıların eklemeler yansıtmak istiyorsanız genellikle dinaset yeniden sorgulamak istiyorum. Diğer taraftan anlık görüntüler, raporları hazırlarken, toplamları hesaplarken ve benzerleri sırasında statik içeriklerine güvenle güvenebileceğiniz için yararlıdır. Yine de, bazen anlık görüntüleri de yeniden sorgulamak isteyebilirsiniz. Çok kullanıcılı bir ortamda, diğer kullanıcılar veritabanını değiştirdiğinde anlık görüntü verileri veri kaynağıyla eşitlemeyi kaybedebilir.

#### <a name="to-requery-a-recordset-object"></a>Kayıt kümesi nesnesini yeniden sorgulamak için

1. Nesnenin [Requery](../../mfc/reference/crecordset-class.md#requery) üye işlevini arayın.

Alternatif olarak, orijinal kayıt kümesini kapatıp yeniden açabilirsiniz. Her iki durumda da, yeni kayıt kümesi veri kaynağının geçerli durumunu temsil eder.

Örneğin, [Bkz. Kayıt Görünümleri: İkinci Kayıt Kümesinden Liste Kutusunu Doldurma.](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)

> [!TIP]
> Performansı `Requery` en iyi duruma getirmek için, kayıt setinin [filtresini](../../data/odbc/recordset-filtering-records-odbc.md) veya [sıralamasını](../../data/odbc/recordset-sorting-records-odbc.md)değiştirmekten kaçının. Aramadan `Requery`önce yalnızca parametre değerini değiştirin.

Arama `Requery` başarısız olursa, aramayı yeniden deneyebilirsiniz; aksi takdirde, başvurunuz incelikle sonlandırılmalıdır. Bir çağrı `Requery` `Open` ya da herhangi bir nedenden dolayı başarısız olabilir. Belki bir ağ hatası oluşur; veya arama sırasında, varolan veriler serbest bırakıldıktan sonra ancak yeni veriler elde edilmeden önce, başka bir kullanıcı özel erişim alabilir; veya kayıt setinizin bağlı olduğu tablo silinebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[Kayıt Kümesi: Kayıt Kümeleri Oluşturma ve Kapatma (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)
