---
description: 'Daha fazla bilgi: kayıt kümesi: bir kayıt kümesini yeniden sorgulama (ODBC)'
title: 'Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
ms.openlocfilehash: 3efcaac1273e6b5cc786e983bfd59f73c870cbea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204478"
---
# <a name="recordset-requerying-a-recordset-odbc"></a>Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu, bir kayıt kümesi nesnesini veritabanından veritabanını yeniden sorgulamak (yani yenilemek) için nasıl kullanabileceğinizi ve bunu [YenidenSorgula](../../mfc/reference/crecordset-class.md#requery) üye işleviyle ne zaman yapmak isteyebileceğiniz açıklanmaktadır.

Bir kayıt kümesini yeniden sorgulama için asıl nedenler şunlardır:

- Kayıt kümesini siz veya diğer kullanıcılar tarafından silinen kayıtlar veya diğer kullanıcılar tarafından silinen kayıtlar (kayıt kümesine zaten yansıtılmıştır) göre güncel hale getirin.

- Kayıt kümesini değişen parametre değerlerine göre yenileyin.

## <a name="bringing-the-recordset-up-to-date"></a><a name="_core_bringing_the_recordset_up_to_date"></a> Kayıt kümesini güncel hale getirme

Genellikle, kayıt kümesini güncel hale getirmek için kayıt kümesi nesnesini yeniden sorgulamak isteyeceksiniz. Çok kullanıcılı bir veritabanı ortamında, diğer kullanıcılar kayıt kümenizin ömrü boyunca verilerde değişiklik yapabilirler. Kayıt kümenizin diğer kullanıcılar tarafından yapılan değişiklikleri yansıtmaları ve diğer kullanıcıların kayıt kümelerinin değişikliklerinizi yansıtması hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıt kümeleri kayıtları güncelleştirme (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) ve [Dynaset](../../data/odbc/dynaset.md).

## <a name="requerying-based-on-new-parameters"></a><a name="_core_requerying_based_on_new_parameters"></a> Yeni parametrelere göre yeniden sorgulama

Başka bir sık kullanılan ve eşit ölçüde önemli — yeniden [sorgulama](../../mfc/reference/crecordset-class.md#requery) kullanımı, değişen parametre değerlerini temel alan yeni bir kayıt kümesi seçmedir.

> [!TIP]
> Sorgu hızı, `Requery` değişen parametre değerleriyle yeniden çağrı yaparsanız daha fazla önemli ölçüde daha hızlıdır `Open` .

## <a name="requerying-dynasets-vs-snapshots"></a><a name="_core_requerying_dynasets_vs.._snapshots"></a> Dinamik kümeleri ve anlık görüntüleri yeniden sorgulama

Dinamik kümeler dinamik güncel verilerle bir kayıt kümesi sunabileceğinden, diğer kullanıcıların eklemelerini yansıtmak istiyorsanız dinamik kümeleri yeniden sorgulamak istersiniz. Diğer yandan anlık görüntüler kullanışlıdır, çünkü raporları hazırlarken, toplamları hesaplarken ve benzeri bir statik içeriğine güvenle güvenebilirsiniz. Hala, bazen bir anlık görüntüyü de yeniden sorgulamak isteyebilirsiniz. Çok kullanıcılı bir ortamda, diğer kullanıcılar veritabanını değiştirirken anlık görüntü verileri veri kaynağıyla eşitlemeyi kaybedebilir.

#### <a name="to-requery-a-recordset-object"></a>Bir kayıt kümesi nesnesini yeniden sorgulamak için

1. Nesnenin [Requery](../../mfc/reference/crecordset-class.md#requery) üye işlevini çağırın.

Alternatif olarak, özgün kayıt kümesini kapatabilir ve yeniden açabilirsiniz. Her iki durumda da, yeni kayıt kümesi veri kaynağının geçerli durumunu temsil eder.

Bir örnek için bkz. [Kayıt görünümleri: ikinci bir kayıt kümesinden liste kutusu doldurma](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).

> [!TIP]
> Performansı iyileştirmek için `Requery` , kayıt kümesinin [filtre](../../data/odbc/recordset-filtering-records-odbc.md) veya [sıralamasını](../../data/odbc/recordset-sorting-records-odbc.md)değiştirmekten kaçının. Çağrılmadan önce yalnızca parametre değerini değiştirin `Requery` .

`Requery`Çağrı başarısız olursa, çağrıyı yeniden deneyebilirsiniz; Aksi takdirde uygulamanızın düzgün bir şekilde sonlandırılması gerekir. Veya için yapılan bir çağrı, `Requery` `Open` birkaç nedenden dolayı başarısız olabilir. Belki de bir ağ hatası oluşuyor; ya da çağrı sırasında, mevcut veriler yayımlandıktan sonra, yeni veriler alınmadan önce, başka bir kullanıcı özel erişim alabilir; ya da kayıt kümenizin bağımlı olduğu tablo silinebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: veri sütunlarını dinamik olarak bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[Kayıt kümesi: kayıt kümeleri oluşturma ve kapatma (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)
