---
title: "Kayıt kümesi: kayıt kümesi (ODBC) yeniden sorgulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1445273d29fc521b24fbf04ffc5abec1fadd4e59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-requerying-a-recordset-odbc"></a>Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konu yeniden sorgulamak için bir kayıt kümesi nesnesi nasıl kullanabileceğinizi açıklar (diğer bir deyişle, yenileme) kendisi veritabanından ve bunun isteyebileceğiniz [Requery](../../mfc/reference/crecordset-class.md#requery) üye işlevi.  
  
 Bir kayıt kümesinde yeniden sorgulama için asıl nedeni vardır:  
  
-   Kayıt kümesi sizin tarafınızdan veya diğer kullanıcılar tarafından eklenen kayıtlar ve (Bu sildiğiniz zaten kayıt kümesinde yansıtılır) diğer kullanıcılar tarafından silinen kayıtlar göre güncel duruma getirin.  
  
-   Parametre değerleri değişen göre kayıt kümesi yenileyin.  
  
##  <a name="_core_bringing_the_recordset_up_to_date"></a>Kayıt kümesi güncelleme  
 Sıklıkla, duruma getirmek için kayıt kümesi nesnesi requery güncel istersiniz. Çok kullanıcılı veritabanı ortamında, diğer kullanıcılar için veri kümenizin ömrü sırasında değişiklik yapabilirsiniz. Ne zaman kümenizin diğer kullanıcılar tarafından yapılan değişiklikleri yansıtır ve ne zaman diğer kullanıcıların kayıt kümeleri yaptığınız değişiklikleri yansıtacak hakkında daha fazla bilgi için bkz: [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) ve [Dynaset](../../data/odbc/dynaset.md).  
  
##  <a name="_core_requerying_based_on_new_parameters"></a>Yeni parametrelere göre yeniden sorgulama  
 Sık başka — ve eşit oranda önemli — kullanımı [Requery](../../mfc/reference/crecordset-class.md#requery) yeni bir parametre değerlerini değişen göre kayıt kümesi seçmektir.  
  
> [!TIP]
>  Sorgu hızıdır çağırırsanız büyük olasılıkla önemli ölçüde daha hızlı **Requery** çağrısı yaparsanız daha parametre değerlerini değiştirme ile **açık** yeniden.  
  
##  <a name="_core_requerying_dynasets_vs.._snapshots"></a>Dinamik kümeler vs yeniden sorgulama. Anlık görüntüler  
 Dinamik kümeler güncel dinamik veri ile bir kayıt kümesi sunmak için anlamına geldiğinden, genellikle diğer kullanıcıların eklemeleri yansıtacak şekilde istiyorsanız dinamik kümeler requery istiyor. Anlık görüntüler, diğer yandan, raporlar hazırlamak, toplamları hesaplamak ve böyle devam ederken statik içeriklerini güvenli bir şekilde güvenebilirsiniz olduğundan kullanışlıdır. Yine de, bazen de bir anlık görüntü requery isteyebilirsiniz. Diğer kullanıcılar veritabanını değiştirdikçe çok kullanıcılı bir ortamda anlık görüntü verileri eşitleme veri kaynağı ile kaybedebilirsiniz.  
  
#### <a name="to-requery-a-recordset-object"></a>Kayıt kümesi nesnesi yeniden sorgulamak için  
  
1.  Çağrı [Requery](../../mfc/reference/crecordset-class.md#requery) nesnenin üye işlevi.  
  
 Alternatif olarak, kapatın ve özgün kayıt kümesi açın. Her iki durumda da, yeni kayıt veri kaynağı geçerli durumunu temsil eder.  
  
 Bir örnek için bkz: [kayıt görünümleri: ikinci kayıt kümesinden liste kutusunu doldurma](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).  
  
> [!TIP]
>  En iyi duruma getirme **Requery** performans, kayıt kümesinin değiştirmekten kaçının [filtre](../../data/odbc/recordset-filtering-records-odbc.md) veya [sıralama](../../data/odbc/recordset-sorting-records-odbc.md). Yalnızca bir parametre çağırmadan önce değiştirme **Requery**.  
  
 Varsa **Requery** çağrısı başarısız oldu, çağrıyı yeniden deneyin; Aksi halde, uygulamanızın düzgün biçimde sonlanmalıdır. Çağrı **Requery** veya **açık** herhangi bir birkaç nedenden dolayı başarısız olabilir. Belki de bir ağ hatası oluşur; veya, arama sırasında var olan verileri yayımlandıktan sonra ancak yeni verileri elde önce başka bir kullanıcı özel erişim sağlanmaya; veya kümenizin bağımlı olduğu tablo silinemiyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Veri sütunlarını (ODBC) dinamik olarak bağlama](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [Kayıt Kümesi: Kayıt Kümeleri Oluşturma ve Kapatma (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)