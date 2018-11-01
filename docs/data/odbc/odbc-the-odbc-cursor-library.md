---
title: 'ODBC: ODBC İmleç Kitaplığı'
ms.date: 11/04/2016
helpviewer_keywords:
- cursor library [ODBC]
- snapshots, support in ODBC
- timestamps, ODBC timestamp columns
- ODBC cursor library [ODBC]
- static cursors
- ODBC drivers, Level 1
- ODBC drivers, cursor support
- positioned updates
- cursors, ODBC cursor library
- Level 1 ODBC drivers
- cursor library [ODBC], snapshots
- ODBC, timestamp
- positioning cursors
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
ms.openlocfilehash: e175a9b27cb19b0c2a67a08751b7a7717226ac55
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435145"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC İmleç Kitaplığı

Bu konuda ODBC imleç kitaplığını ve nasıl kullanılacağını açıklar. Daha fazla bilgi için bkz.:

- [İmleç Kitaplığı ve düzey 1 ODBC sürücüleri](#_core_the_cursor_library_and_level_1_odbc_drivers)

- [Konumlandırılmış güncelleştirmeler ve zaman damgası sütunları](#_core_positioned_updates_and_timestamp_columns)

- [İmleç kitaplığını kullanma](#_core_using_the_cursor_library)

ODBC imleç kitaplığı ODBC Sürücü Yöneticisi ve sürücü arasında bulunan bir dinamik bağlantı kitaplığı (DLL) ' dir. ODBC bağlamında, bir sürücü konumunu kümesinde izlemek için bir işaretçi tutar. İmleç konumu olduğu, zaten kaydırılan kümesinde işaretler — geçerli kayıt.

##  <a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> İmleç Kitaplığı ve düzey 1 ODBC sürücüleri

ODBC imleç kitaplığı düzey 1 sürücüleri aşağıdaki yeni özellikleri sağlar:

- İleri ve geri gezinme. Düzey 2 sürücüler, zaten kaydırılabilir oldukları için imleç kitaplığı gerekmez.

- Anlık görüntüleri için destek. İmleç Kitaplığı anlık görüntünün kayıtlarını içeren bir arabelleği yönetir. Bu tampon, programınızın silme işlemleri ve kayıtları ancak ekleme, silme veya diğer kullanıcıların düzenlemeler düzenlemeler yansıtır. Bu nedenle anlık görüntü yalnızca imleç kitaplığının arabellek olarak geçerli olarak gereklidir. Çağırana kadar arabellek kendi eklemeleri ayrıca yansıtmaz `Requery`. Dynaset'ler imleç kitaplığı kullanmayın.

Normalde, sürücü tarafından desteklenmiyor olsa bile imleç kitaplığı, anlık görüntüler (statik imleçler) sunar. Sürücünüzün statik imleçler destekliyorsa, anlık görüntü desteği almak için imleç kitaplığı yüklemek gerekmez. İmleç kitaplığı kullanıyorsanız, yalnızca anlık görüntüler ve salt iletme kayıt kümeleri kullanabilirsiniz. Dynaset'ler (KEYSET_DRIVEN imleçler) sürücünüzü destekliyorsa ve bunları kullanmak istediğiniz, imleç kitaplığı kullanmamalıdır. Anlık görüntüleri hem dynaset'ler kullanmak isterseniz, bunları iki farklı temel gerekir `CDatabase` nesneleri (iki farklı bağlantı) sürece sürücünüzü her ikisini de destekler.

##  <a name="_core_positioned_updates_and_timestamp_columns"></a> Konumlandırılmış güncelleştirmeler ve zaman damgası sütunları

> [!NOTE]
>  ODBC veri kaynakları, veri erişim nesnesi (DAO) MFC sınıfları veya bu konuda açıklandığı gibi MFC ODBC sınıfları aracılığıyla erişilebilir.

> [!NOTE]
>  ODBC sürücünüz destekliyorsa `SQLSetPos`, varsa hangi MFC kullanır, bu konu için geçerli değildir.

Konumlandırılmış güncelleştirmeler çoğu düzey 1 sürücüleri desteklemez. Bu tür sürücüler Düzey 2 sürücüleri yeteneklerini bu bağlamda benzetmek için imleç kitaplığını kullanır. İmleç Kitaplığı, değişmeyen alanları aranan bir güncelleştirme yaparak konumlandırılmış güncelleştirme desteğini öykünür.

Bazı durumlarda, bir kayıt kümesi değişmeyen bu alanlardan biri olarak bir zaman damgası sütunu bulunabilir. Zaman damgası sütunları içeren tablolar ile MFC kayıt kümeleri kullanarak iki sorun ortaya çıkar.

İlk sorun, zaman damgası sütunları içeren tablolar güncellenebilir anlık ilgilidir. Anlık ilişkili tabloda bir zaman damgası sütunu içeriyorsa, çağırmalıdır `Requery` çağırdıktan sonra `Edit` ve `Update`. Aksi durumda, aynı kayıt yeniden düzenlemeniz mümkün olmayabilir. Çağırdığınızda `Edit` ardından `Update`, kaydı veri kaynağına yazılır ve zaman damgası sütununu güncelleştirilir. Değil çağırırsanız `Requery`, zaman damgası değeri, anlık görüntü kayıt için veri kaynağına karşılık gelen zaman damgasını artık eşleşmiyor. Kaydı yeniden güncelleştirmeye çalıştığınızda, veri kaynağı uyumsuzluğu nedeniyle güncelleştirme izin vermeyebilir.

İkinci sorun sınıfı sınırlamaları ilgiliyse [CTime](../../atl-mfc-shared/reference/ctime-class.md) ile kullanıldığında `RFX_Date` saat ve tarih bilgilerinin ya da bir tablodan aktarmak için işlevi. İşleme `CTime` nesnesi biçiminde fazladan Ara işleme veri aktarımı sırasında bazı ek yükler getirir. Tarih aralığını `CTime` nesneleri ayrıca çok sınırlama bazı uygulamalar için. Yeni bir sürümü `RFX_Date` işlevi alır bir ODBC *TIMESTAMP_STRUCT* yerine parametre bir `CTime` nesne. Daha fazla bilgi için `RFX_Date` içinde [makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md) içinde *MFC başvurusu*.

##  <a name="_core_using_the_cursor_library"></a> İmleç kitaplığını kullanma

Bir veri kaynağına bağlandığınızda — çağırarak [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) — veri kaynağı için imleç kitaplığı kullanıp kullanmayacağınızı belirtin. Bu veri kaynağında anlık görüntüleri oluşturacaksanız belirtin `CDatabase::useCursorLib` seçeneğini `dwOptions` parametresi `OpenEx` veya belirtmek için TRUE *bUseCursorLib* parametresi `Open` (varsayılan değer: DOĞRU). ODBC sürücünüz dynaset'ler destekliyorsa ve dinamik kümeler veri kaynağında açmak istediğiniz, imleç kitaplığı (dynasets için gereken bazı sürücü işlevleri maskeleri) kullanmayın. Bu durumda, belirtmeyin `CDatabase::useCursorLib` içinde `OpenEx` veya için FALSE belirtin *bUseCursorLib* parametresinde `Open`.

## <a name="see-also"></a>Ayrıca Bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)