---
title: 'ODBC: ODBC imleç kitaplığı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e57251263738d534b7e7e22ff287607fbc5159a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092600"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC İmleç Kitaplığı
Bu konuda ODBC imleç kitaplığı açıklar ve nasıl kullanılacağını açıklar. Daha fazla bilgi için bkz.:  
  
-   [İmleç Kitaplığı ve düzey 1 ODBC sürücüleri](#_core_the_cursor_library_and_level_1_odbc_drivers)  
  
-   [Konumlandırılmış güncelleştirmeler ve zaman damgası sütunları](#_core_positioned_updates_and_timestamp_columns)  
  
-   [İmleç kitaplığını kullanma](#_core_using_the_cursor_library)  
  
 ODBC imleç kitaplığı ODBC Sürücü Yöneticisi ve sürücü arasında bulunan bir dinamik bağlantı kitaplığı (DLL) ' dir. ODBC bağlamında, bir sürücü kayıt kümesi içindeki konumunu izlemek için bir işaretçi tutar. İmleç konumu için zaten kaydırılan kümesinde işaretler — geçerli kayıt.  
  
##  <a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> İmleç Kitaplığı ve düzey 1 ODBC sürücüleri  
 ODBC imleç kitaplığı düzey 1 sürücüleri aşağıdaki yeni özellikleri sağlar:  
  
-   İleri ve geri kaydırma. Zaten kaydırılabilir olduklarından Düzey 2 sürücüleri imleç kitaplığı gerekmez.  
  
-   Anlık görüntüler için destek. İmleç Kitaplığı anlık görüntünün kayıtlarını içeren bir arabelleği yönetir. Bu arabelleğin programınızın silme işlemleri ve kayıtları ancak ekleme, silme veya diğer kullanıcıların düzenlemeleri düzenlemeleri yansıtır. Bu nedenle, anlık görüntü yalnızca imleç kitaplığının arabelleği kadar geçerlidir. Çağırmanız kadar arabellek kendi eklemeler de yansıtmaz **Requery**. Dinamik kümeler imleç kitaplığı kullanmayın.  
  
 Normalde, sürücüsü tarafından desteklenmez olsa bile imleç kitaplığı, anlık görüntüler (statik imleçler) sağlar. Sürücünüzün statik imleçleri destekliyorsa, anlık görüntü desteği almak için imleç kitaplığını yükleme gerekmez. İmleç kitaplığı kullanıyorsanız, yalnızca anlık görüntüler ve salt iletme kayıt kümeleri kullanabilirsiniz. Dinamik kümeler (KEYSET_DRIVEN imleçler) sürücünüzü destekliyorsa ve bunları kullanmak istediğiniz, imleç kitaplığı kullanmaması gerekir. Anlık görüntüler ve dinamik kümeler kullanmak istiyorsanız, bunları iki farklı temel gerekir `CDatabase` sürücünüzü her ikisini desteklemedikçe nesnelerini (iki farklı bağlantı).  
  
##  <a name="_core_positioned_updates_and_timestamp_columns"></a> Konumlandırılmış güncelleştirmeler ve zaman damgası sütunları  
  
> [!NOTE]
>  ODBC veri kaynakları, MFC veri erişim nesnesi (DAO) sınıfları veya bu konu başlığı altında açıklandığı gibi MFC ODBC sınıfları üzerinden erişilebilir.  
  
> [!NOTE]
>  ODBC sürücüsü destekliyorsa **SQLSetPos**, hangi MFC kullanan varsa, bu konu için geçerli değildir.  
  
 Düzey 1 sürücülerin çoğu konumlandırılmış güncelleştirmeler desteklemez. Bu tür sürücüler Düzey 2 sürücüleri özelliklerini bu bağlamda benzetmek için imleç kitaplığını kullanır. İmleç Kitaplığı değişmeyen alanlarda aranan bir güncelleştirme yaparak konumlandırılmış güncelleştirme desteğine öykünür.  
  
 Bazı durumlarda, bir kayıt kümesi değişmeyen bu alanlardan biri olarak bir zaman damgası sütunu içerebilir. MFC kayıt kümelerini zaman damgası sütunları içeren tablolar ile kullanırken iki sorunları ortaya çıkar.  
  
 İlk sorunu, zaman damgası sütunları tablolarla güncellenebilir anlık ilgilidir. Anlık görüntünüz bağlı tabloda bir zaman damgası sütunu içeriyorsa, çağırmalıdır **Requery** çağırdıktan sonra **Düzenle** ve **güncelleştirme**. Aksi durumda, aynı kayıt yeniden düzenlemeniz mümkün olmayabilir. Çağırdığınızda **Düzenle** ve ardından **güncelleştirme**, kayıt veri kaynağına yazılır ve zaman damgası sütunu güncelleştirilir. Değil çağırırsanız **Requery**, anlık görüntünüz kaydında zaman damgası değeri karşılık gelen zaman damgası veri kaynağı artık eşleşmiyor. Veri kaynağı kaydı tekrar güncelleştirmeye çalıştığınızda, güncelleştirme uyumsuzluğu nedeniyle izin vermeyebilir.  
  
 İkinci sorun sınıfının sınırlamaları işlemiyle ilgili [CTime](../../atl-mfc-shared/reference/ctime-class.md) ile kullanıldığında `RFX_Date` veya bir tablodan saat ve tarih bilgi aktarmak için işlevi. İşleme `CTime` nesne bazı ek veri aktarımı sırasında fazladan orta düzeyde işleme biçiminde uygular. Tarih aralığını `CTime` nesneleri ayrıca çok sınırlama bazı uygulamalar için. Yeni bir sürümü `RFX_Date` işlev alır ODBC **TIMESTAMP_STRUCT** parametresi yerine bir `CTime` nesnesi. Daha fazla bilgi için bkz: `RFX_Date` içinde [makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md) içinde *MFC başvurusu*.  

  
##  <a name="_core_using_the_cursor_library"></a> İmleç kitaplığını kullanma  
 Bir veri kaynağına bağlandığınızda — çağırarak [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) — imleç kitaplığı veri kaynağı için kullanılıp kullanılmayacağını belirtebilirsiniz. Bu veri kaynağında anlık görüntüleri oluşturacaksanız belirtin **CDatabase::useCursorLib** seçeneğini `dwOptions` parametresi `OpenEx` veya belirtmek **TRUE** için  **bUseCursorLib** parametresi **açık** (varsayılan değer **TRUE**). Dinamik kümeler ODBC sürücüsü destekliyorsa ve veri kaynağı üzerinde dinamik kümeler açmak istediğiniz, imleç kitaplığı (dinamik kümeler için gereken bazı sürücü işlevleri maskeleri) kullanmayın. Bu durumda, belirtmeyin **CDatabase::useCursorLib** içinde `OpenEx` veya belirtmek **FALSE** için **bUseCursorLib** parametresinde **açın**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC Temelleri](../../data/odbc/odbc-basics.md)