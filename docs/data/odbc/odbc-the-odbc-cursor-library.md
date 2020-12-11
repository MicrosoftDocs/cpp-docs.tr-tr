---
description: 'Daha fazla bilgi edinin: ODBC: ODBC Imleç kitaplığı'
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
ms.openlocfilehash: 1b7c05529f771b281e623502a4b8c4358e17db71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160993"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC İmleç Kitaplığı

Bu konuda, ODBC Imleç kitaplığı açıklanmakta ve nasıl kullanılacağı açıklanmaktadır. Daha fazla bilgi için bkz:

- [İmleç kitaplığı ve düzey 1 ODBC sürücüleri](#_core_the_cursor_library_and_level_1_odbc_drivers)

- [Konumlandırılmış güncelleştirmeler ve zaman damgası sütunları](#_core_positioned_updates_and_timestamp_columns)

- [Imleç kitaplığını kullanma](#_core_using_the_cursor_library)

ODBC Imleç kitaplığı, ODBC Sürücü Yöneticisi ve sürücü arasında bulunan bir dinamik bağlantı kitaplığı (DLL). ODBC koşullarında, bir sürücü kayıt kümesindeki konumunu izlemek için bir imleç tutar. İmleç, zaten kaydırdığınız kayıt kümesindeki konumu (geçerli kayıt) işaretler.

## <a name="cursor-library-and-level-1-odbc-drivers"></a><a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> İmleç kitaplığı ve düzey 1 ODBC sürücüleri

ODBC Imleç kitaplığı, 1. düzey sürücülere aşağıdaki yeni özellikleri verir:

- İleri ve geri kaydırma. 2. düzey sürücülere, zaten kaydırılabilir olduklarından imleç kitaplığı gerekmez.

- Anlık görüntüler için destek. İmleç kitaplığı, anlık görüntünün kayıtlarını içeren bir arabelleği yönetir. Bu arabellek, programınızın silme işlemlerini ve düzenlemelerini yansıtır, ancak diğer kullanıcıların ekleme, silme veya düzenlemeleriyle kalmaz. Bu nedenle, anlık görüntü yalnızca imleç kitaplığının arabelleği kadar geçerli olur. Arabellek, çağrılana kadar kendi eklemelerinizi de yansıtmaz `Requery` . Dinamik kümeler imleç kitaplığını kullanmaz.

İmleç kitaplığı, normalde sürücünüz tarafından desteklenmese de, anlık görüntüler (statik imleçler) sağlar. Sürücünüz zaten statik imleçler destekliyorsa, anlık görüntü desteğini almak için imleç kitaplığı 'nı yüklemeniz gerekmez. İmleç kitaplığını kullanırsanız, yalnızca anlık görüntüleri ve salt iletme kayıt kümelerini kullanabilirsiniz. Sürücünüz dinamik kümeleri (KEYSET_DRIVEN imleçler) destekliyorsa ve bunları kullanmak istiyorsanız, imleç kitaplığı 'nı kullanmanız gerekir. Hem anlık görüntüleri hem de dinamik kümeleri kullanmak istiyorsanız, `CDatabase` sürücünüz her ikisini de desteklemediği takdirde iki farklı nesneye (iki farklı bağlantı) dayandırmalısınız.

## <a name="positioned-updates-and-timestamp-columns"></a><a name="_core_positioned_updates_and_timestamp_columns"></a> Konumlandırılmış güncelleştirmeler ve zaman damgası sütunları

> [!NOTE]
> ODBC veri kaynaklarına, bu konuda açıklandığı gibi MFC ODBC sınıfları aracılığıyla veya MFC veri erişim nesnesi (DAO) sınıfları aracılığıyla erişilebilir.

> [!NOTE]
> ODBC sürücünüz destekliyorsa `SQLSetPos` , MFC varsa bu konu sizin için geçerlidir.

Çoğu düzey 1 sürücü konumlandırılmış güncelleştirmeleri desteklemez. Bu tür sürücüler, bu şekilde düzey 2 sürücülerin özelliklerine öykünmek için imleç kitaplığı ' nı kullanır. İmleç kitaplığı, değişmeyen alanlarda bir arama güncelleştirmesi gerçekleştirerek konumlandırılmış güncelleştirme desteğine öykünür.

Bazı durumlarda, bir kayıt kümesi değişmeyen alanlardan biri olarak zaman damgası sütunu içerebilir. Zaman damgası sütunları içeren tablolarla MFC kayıt kümeleri kullanılırken iki sorun oluşur.

İlk sorun, zaman damgası sütunları içeren tablolardaki güncelleştirilebilir anlık görüntülerle ilgilidir. Anlık görüntülerinizin bağlandığı tablo bir zaman damgası sütunu içeriyorsa, `Requery` ve öğesini çağırdıktan sonra öğesini çağırmanız gerekir `Edit` `Update` . Aksi takdirde, aynı kaydı tekrar düzenleyemeyebilirsiniz. Öğesini çağırdığınızda `Edit` `Update` , kayıt veri kaynağına yazılır ve zaman damgası sütunu güncellenir. Çağırmazsa `Requery` , anlık görüntüdeki kayıt zaman damgası değeri artık veri kaynağındaki karşılık gelen zaman damgasıyla eşleşmez. Kaydı yeniden güncelleştirmeyi denediğinizde, uyumsuzluk nedeniyle veri kaynağı güncelleştirmeye izin verebilir.

İkinci sorun, [](../../atl-mfc-shared/reference/ctime-class.md) `RFX_Date` bir tabloya veya bir tabloya saat ve tarih bilgilerini aktarmak için işleviyle birlikte kullanıldığında, CTime sınıfının sınırlamalarıyla ilgilidir. Nesnenin işlenmesi, `CTime` veri aktarımı sırasında ek ara işleme biçiminde bazı ek yük getirir. Nesnelerin tarih aralığı `CTime` bazı uygulamalar için de çok fazla sınırlandırma olabilir. İşlevin yeni bir sürümü `RFX_Date` bir nesne yerine BIR ODBC *TIMESTAMP_STRUCT* parametresi alır `CTime` . Daha fazla bilgi için bkz `RFX_Date` . *MFC başvurusu* Içindeki [makrolar ve genel](../../mfc/reference/mfc-macros-and-globals.md) bilgiler.

## <a name="using-the-cursor-library"></a><a name="_core_using_the_cursor_library"></a> Imleç kitaplığını kullanma

Bir veri kaynağına bağlanırken — [CDatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) ' ı çağırarak veri kaynağı için imleç kitaplığının kullanılıp kullanılmayacağını belirtebilirsiniz. Bu veri kaynağında anlık görüntüler oluşturacağınız takdirde, `CDatabase::useCursorLib` parametresi içindeki seçeneğini belirtin `dwOptions` `OpenEx` veya *bUseCursorLib* parametresi için true `Open` değerini belirtin (varsayılan değer true 'dur). ODBC sürücünüz dinamik kümeleri destekliyorsa ve veri kaynağında dinamik kümeleri açmak istiyorsanız, imleç kitaplığını kullanmayın (Bu, dinamik kümeler için gereken bazı sürücü işlevlerine sahiptir). Bu durumda, içinde belirtmeyin `CDatabase::useCursorLib` `OpenEx` veya Içinde *bUseCursorLib* parametresi için false değerini belirtin `Open` .

## <a name="see-also"></a>Ayrıca bkz.

[ODBC temelleri](../../data/odbc/odbc-basics.md)
