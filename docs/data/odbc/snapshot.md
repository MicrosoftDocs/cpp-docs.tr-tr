---
title: Anlık Görüntü
ms.date: 11/04/2016
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
ms.openlocfilehash: 62b5952f3052a3248175ce7892b1cf4615f1dd17
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212699"
---
# <a name="snapshot"></a>Anlık Görüntü

Anlık görüntü, anlık görüntünün oluşturulduğu sırada var olan verilerin statik görünümünü yansıtan bir kayıt kümesidir. Anlık görüntüyü açıp tüm kayıtlara taşıdığınızda, içerdiği kayıt kümesi ve değerleri `Requery`çağırarak, anlık görüntüyü yeniden oluşturulana kadar değişmez.

> [!NOTE]
>  Bu konu MFC ODBC sınıfları için geçerlidir. MFC ODBC sınıfları yerine MFC DAO sınıflarını kullanıyorsanız, anlık görüntü türü kayıt kümelerinin bir açıklaması için bkz. [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open) .

Veritabanı sınıflarıyla güncellenebilir veya salt okunabilir anlık görüntüler oluşturabilirsiniz. DYNASET 'in aksine, güncelleştirilebilir bir anlık görüntü, diğer kullanıcılar tarafından yapılan kayıt değerlerinde yapılan değişiklikleri yansıtmaz, ancak programınız tarafından yapılan güncelleştirmeleri ve silmeleri yansıtır. Bir anlık görüntüye eklenen kayıtlar, siz `Requery`çağırana kadar anlık görüntüye görünür olmaz.

> [!TIP]
>  Anlık görüntü, ODBC statik imlece. Statik imleçler gerçekten bu kayda gelene kadar bir veri satırı almaz. Tüm kayıtların hemen alındığından emin olmak için, kayıt kümenizin sonuna kaydırabilir ve sonra görmek istediğiniz ilk kayda kaydırabilirsiniz. Ancak, son kaydırmanın ek yük olduğunu ve performansı düşürebileceğini unutmayın.

Anlık görüntüler, bir rapor oluştururken veya hesaplamalar gerçekleştirirken yaptığınız gibi, işlemleriniz sırasında sabit kalması gereken veriler için en değerlidir. Bu nedenle, veri kaynağı anlık görüntüinizden önemli ölçüde zaman alabilir, böylece zaman zaman bir kez yeniden oluşturmak isteyebilirsiniz.

Anlık görüntü desteği, herhangi bir düzey 1 sürücü için statik imleçler ve konumlandırılmış güncelleştirmeler (updatebeceri için gereklidir) sağlayan ODBC Imleç kitaplığını temel alır. Bu destek için imleç kitaplığı DLL dosyasının belleğe yüklenmesi gerekir. Bir `CDatabase` nesnesi oluşturup `OpenEx` member işlevini çağırdığınızda, *dwOptions* parametresinin `CDatabase::useCursorLib` seçeneğini belirtmeniz gerekir. `Open` member işlevini çağırırsanız, imleç kitaplığı varsayılan olarak yüklenir. Anlık görüntüler yerine dinamik kümeler kullanıyorsanız, imleç kitaplığının yüklenmesine neden olmak istemezsiniz.

Anlık görüntüler yalnızca `CDatabase` nesnesi oluşturulduğunda ODBC Imleç kitaplığı yüklenmişse veya kullandığınız ODBC sürücüsü statik imleçleri destekliyorsa kullanılabilir.

> [!NOTE]
>  Bazı ODBC sürücüleri için anlık görüntüler (statik imleçler) güncelleştirilebilir olmayabilir. Desteklenen imleç türleri ve destekledikleri eşzamanlılık türleri için sürücü belgelerinize bakın. Güncelleştirilebilir anlık görüntüleri güvence altına almak için, `CDatabase` nesne oluştururken imleç kitaplığını belleğe yüklediğinizden emin olun. Daha fazla bilgi için bkz. [ODBC: ODBC Imleç kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).

> [!NOTE]
>  Hem anlık görüntüleri hem de dinamik kümeleri kullanmak istiyorsanız, bunları iki farklı `CDatabase` nesnesine dayandırmalısınız (iki farklı bağlantı).

Tüm kayıt kümeleriyle Özellikler anlık görüntülerini paylaşma hakkında daha fazla bilgi için bkz. [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md). ODBC Imleç kitaplığı da dahil olmak üzere ODBC ve anlık görüntüler hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md).

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
