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
ms.openlocfilehash: 309c81e8d370b61ba3a44d9253cda4fa9b84b6cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094770"
---
# <a name="snapshot"></a>Anlık Görüntü
Anlık görüntü oluşturulduğunda var gibi verileri statik görünümünü yansıtan bir kayıt kümesi bir anlık görüntüdür. Anlık görüntüyü açıp tüm kayıtlara taşıdığınızda, kayıt kümesi içerdiği ve çağırarak anlık görüntüyü yeniden yapılandırmadan değerleri değiştirmeyin **Requery**.  
  
> [!NOTE]
>  Bu konu MFC ODBC sınıfları için geçerlidir. MFC ODBC sınıfları yerine MFC DAO sınıflarını kullanıyorsanız bkz [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open) anlık görüntü türü kayıt kümelerinin açıklaması.  
  
 Veritabanı sınıfları ile güncelleştirilebilir veya salt okunur anlık görüntülerini oluşturabilirsiniz. Farklı bir dinamik olarak güncellenebilir bir anlık görüntü kayıt değerlerine diğer kullanıcılar tarafından yapılan değişiklikleri yansıtmaz, ancak güncelleştirmeleri ve silme programınız tarafından yapılan yansıtmamaktadır. Bir anlık görüntüye eklenen kayıtları değil duruma anlık görüntüye görünür, çağrısı tamamlanana kadar **Requery**.  
  
> [!TIP]
>  Bir ODBC statik imleç bir anlık görüntüdür. Kayda kaydırma kadar statik imleçler bir veri satırı gerçekte almıyor. Tüm kayıtları hemen alındığından emin olmak için kayıt sonuna kaydırın ve görmek istediğiniz ilk kaydı kaydırın. Ancak, sonuna kaydırma ek yüke yol açar ve performans düzeyine düşürebilirsiniz olduğunu unutmayın.  
  
 Verilerin ne zaman, bir rapor oluşturulurken veya hesaplamaları olarak, işlemleri sırasında sabit kalır gerektiğinde anlık görüntüleri en değerli. Buna rağmen veri kaynağı önemli ölçüde zaman zaman yeniden oluşturmak isteyebilirsiniz, anlık görüntüden ayırmak.  
  
 Anlık görüntü desteği statik imleçler sağlar ve herhangi bir düzey 1 sürücüsü için (güncellenebilirlik için gerekli) güncelleştirmeler konumlandırıldı ODBC imleç kitaplığı, temel alır. İmleç Kitaplığı DLL'si Bu destek için bellekte yüklenmesi gerekir. Oluşturduğunuzda bir `CDatabase` nesne ve çağrı kendi `OpenEx` üye işlevi belirtmelisiniz **CDatabase::useCursorLib** seçeneği `dwOptions` parametresi. Çağırırsanız **açık** üye işlevi, imleç kitaplığı, varsayılan olarak yüklenir. Anlık görüntü yerine dinamik kümeler kullanıyorsanız, yüklenecek imleç kitaplığı neden etmek istiyor musunuz.  
  
 Anlık görüntü yalnızca ODBC imleç kitaplığı yüklenmişse kullanılabilir `CDatabase` nesnesi oluşturulduğunda veya statik imleçler ODBC sürücüsü kullanıyorsanız destekler.  
  
> [!NOTE]
>  Bazı ODBC sürücüleri için anlık görüntüler (statik imleçler) güncellenebilir olmayabilir. Desteklenen imleç türleri için sürücü belgelerinize ve destekledikleri eşzamanlılık türleri denetleyin. Güncelleştirilebilir anlık görüntüleri güvence altına almak için yük imleç kitaplığı belleğe oluşturduğunuzda emin olun bir `CDatabase` nesnesi. Daha fazla bilgi için bkz: [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!NOTE]
>  Anlık görüntüler ve dinamik kümeler kullanmak istiyorsanız, bunları iki farklı temel gerekir `CDatabase` nesneleri (iki farklı bağlantı).  
  
 Tüm kümeleriyle özellikleri anlık görüntüleri paylaşımı hakkında daha fazla bilgi için bkz: [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md). ODBC ve ODBC imleç kitaplığı ile birlikte anlık görüntüler hakkında daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)