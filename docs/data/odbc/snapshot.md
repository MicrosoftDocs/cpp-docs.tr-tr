---
title: Anlık görüntü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC cursor library [ODBC], snapshots
- cursors [ODBC], static
- recordsets, snapshots
- snapshots, support in ODBC
- static cursors
- ODBC recordsets, snapshots
- cursor library [ODBC], snapshots
- snapshots
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cb3f2f63d60cd5120479a66eea1fe6bdee91b8ac
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338213"
---
# <a name="snapshot"></a>Anlık Görüntü
Anlık görüntü anlık görüntünün oluşturulduğu anda var olan verilerin statik görünümünü yansıtır, bir kayıt kümesidir. Anlık görüntü açıp tüm kayıtlara taşıma kayıt kümesini içerdiği ve çağırarak anlık görüntü yeniden yapılandırmadan değerlerini değiştirmeyin `Requery`.  
  
> [!NOTE]
>  Bu konu MFC ODBC sınıflarına uygulanır. MFC ODBC sınıfları yerine MFC DAO sınıflarına kullanıyorsanız, bkz [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open) anlık görüntü türü kayıt kümeleri açıklaması.  
  
 Veritabanı sınıfları ile güncelleştirilebilir veya salt okunur anlık görüntülerini oluşturabilirsiniz. Farklı bir dinamik olarak güncelleştirilebilir bir anlık görüntü kayıt değerlerine diğer kullanıcılar tarafından yapılan değişiklikleri yansıtmaz, ancak güncelleştirmeleri ve silme programınız tarafından yapılan yansıtmıyor. Bir anlık görüntüye eklenen kayıtlar değil duruma için anlık görüntü görünür, çağırana kadar `Requery`.  
  
> [!TIP]
>  ODBC statik imleç bir anlık görüntüdür. Statik imleçler kayda kaydırma kadar aslında bir satır veri almıyor. Tüm kayıtları hemen alındığından emin olmak için kayıt sonuna kaydırın ve görmek istediğiniz ilk kayda'e gidin. Ancak, sonuna kaydırma ek yükü gerektirir ve performans düzeyine düşürebilirsiniz olduğunu unutmayın.  
  
 Anlık görüntüleri, verilerin ne zaman, rapor oluştururken veya hesaplamaları olarak işlemlerinizi sırasında sabit mi kalacağını, ihtiyacınız olduğunda en değerli. Bu halde bile veri kaynağının önemli ölçüde zaman zaman yeniden oluşturmak isteyebilirsiniz, anlık görüntüden birleştirmek.  
  
 Anlık görüntü desteği, statik imleçler sağlayan ve güncelleştirmeleri (güncellenebilirlik için gerekli) Düzey 1 sürücüsü için yerleştirilmiş ODBC imleç kitaplığı dayanır. Bu destek için bellekte imleç kitaplığı DLL yüklenmesi gerekir. Oluşturduğunuzda bir `CDatabase` nesne ve çağrı kendi `OpenEx` üye işlevini belirtmelisiniz `CDatabase::useCursorLib` seçeneği *dwOptions* parametresi. Eğer `Open` üye işlevi, imleç kitaplığı, varsayılan olarak yüklenir. Dynaset'ler yerine anlık görüntüleri kullanıyorsanız, imleç kitaplığı yüklenmesine neden istemezsiniz.  
  
 Anlık görüntüler yalnızca ODBC imleç kitaplığı yüklenmişse kullanılabilir `CDatabase` nesnesi oluşturulduğunda veya statik imleçler kullanmakta olduğunuz ODBC sürücüsü destekler.  
  
> [!NOTE]
>  Bazı ODBC sürücüleri için anlık görüntüler (statik imleçler) güncelleştirilebilir olmayabilir. Desteklenen imleç türü için sürücü belgelerinize ve destekledikleri eşzamanlılık türlerini denetleyin. Güncelleştirilebilir anlık görüntüleri garanti için yüklediğiniz imleç kitaplığı belleğe oluşturduğunuzda emin olun bir `CDatabase` nesne. Daha fazla bilgi için [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!NOTE]
>  Anlık görüntüleri hem dynaset'ler kullanmak isterseniz, bunları iki farklı temel gerekir `CDatabase` nesneleri (iki farklı bağlantı).  
  
 Tüm kayıt kümelerini ile özellikleri anlık görüntüleri paylaşımı hakkında daha fazla bilgi için bkz. [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md). ODBC ve ODBC imleç kitaplığı dahil olmak üzere anlık görüntüler hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)