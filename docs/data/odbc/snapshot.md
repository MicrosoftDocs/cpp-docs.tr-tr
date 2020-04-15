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
ms.openlocfilehash: e487b5abcc5eee4e3f4b1941100980eac4a040c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366915"
---
# <a name="snapshot"></a>Anlık Görüntü

Anlık görüntü, anlık görüntü oluşturulduğu anda var olan verilerin statik görünümünü yansıtan bir kayıt kümesidir. Anlık görüntünün açılımını açtığınızda ve tüm kayıtlara geçtikçe, içerdiği kayıt kümesi ve `Requery`anlık görüntü'ü arayarak yeniden yapılandırana kadar değerleri değişmez.

> [!NOTE]
> Bu konu MFC ODBC sınıfları için geçerlidir. MFC ODBC sınıfları yerine MFC DAO sınıflarını kullanıyorsanız, [bkz.](../../mfc/reference/cdaorecordset-class.md#open)

Veritabanı sınıflarıyla güncelleştirilebilir veya salt okunur anlık görüntüler oluşturabilirsiniz. Dynaset'in aksine, güncelleştirilebilir anlık görüntü diğer kullanıcılar tarafından yapılan kayıt değerlerindeki değişiklikleri yansıtmaz, ancak programınız tarafından yapılan güncelleştirmeleri ve silmeleri yansıtır. Anlık görüntüye eklenen kayıtlar, siz arayana `Requery`kadar anlık görüntüde görünür hale gelmez.

> [!TIP]
> Anlık görüntü, ODBC statik imlecidir. Statik imleçler, siz bu kayda kaydırana kadar bir veri satırı almaz. Tüm kayıtların hemen alınmasını sağlamak için kayıt setinizin sonuna kadar ilerleyebilir ve ardından görmek istediğiniz ilk kayda geçebilirsiniz. Ancak, sonuna kaydırma ekstra ek yükü gerektirir ve performansı düşürebilir unutmayın.

Anlık görüntüler, işlemleriniz sırasında verilerin sabit kalması gerektiğinde, rapor oluştururken veya hesaplamalar gerçekleştirirken olduğu gibi en değerli sidir. Yine de, veri kaynağı anlık görüntünüzden önemli ölçüde farklıolabilir, bu nedenle zaman zaman yeniden oluşturmak isteyebilirsiniz.

Anlık görüntü desteği, herhangi bir Düzey 1 sürücüsü için statik imleçler ve konumlandırılmış güncelleştirmeler (güncellenebilirlik için gerekli) sağlayan ODBC Imleç Kitaplığı'nı temel alır. İmleç kitaplığı DLL bu destek için bellekte yüklenmesi gerekir. Bir `CDatabase` nesne oluşturup `OpenEx` üye işlevini çağırdığınızda, `CDatabase::useCursorLib` *dwOptions* parametresinin seçeneğini belirtmeniz gerekir. `Open` Üye işlevi çağırırsanız, imleç kitaplığı varsayılan olarak yüklenir. Anlık görüntüler yerine dinamit kullanıyorsanız, imleç kitaplığı yüklenmesiiçin neden olmak istemiyorum.

Anlık görüntüler yalnızca `CDatabase` nesne oluşturulduğunda ODBC İmleci Kitaplığı yüklendiğinde veya kullandığınız ODBC sürücüsü statik imleçleri destekliyorsa kullanılabilir.

> [!NOTE]
> Bazı ODBC sürücüleri için anlık görüntüler (statik imleçler) güncelleştirilemeyebilir. Desteklenen imleç türleri ve destekledikleri eşzamanlılık türleri için sürücü belgelerinizi denetleyin. Güncelleştirilebilir anlık görüntüleri garanti etmek için, bir `CDatabase` nesne oluştururken imleç kitaplığını belleğe yüklediğinizden emin olun. Daha fazla bilgi için [Bkz. ODBC: ODBC İmleç Kitaplığı.](../../data/odbc/odbc-the-odbc-cursor-library.md)

> [!NOTE]
> Hem anlık görüntüleri hem de dynaset'i kullanmak istiyorsanız, `CDatabase` bunları iki farklı nesneye (iki farklı bağlantı) dayandırmalısınız.

Anlık görüntünün tüm kayıt kümeleriyle paylaştığı özellikler hakkında daha fazla bilgi için [Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)'ye bakın. ODBC ve Anlık Görüntüler hakkında daha fazla bilgi için, ODBC İmleç Kitaplığı da dahil olmak üzere, Bkz. [ODBC.](../../data/odbc/odbc-basics.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
