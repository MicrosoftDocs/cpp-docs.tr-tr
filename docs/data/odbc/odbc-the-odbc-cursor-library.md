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
ms.openlocfilehash: 13640dd2a8593057bef708a45dfc8471ba212563
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367187"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC İmleç Kitaplığı

Bu konu, ODBC İmleç Kitaplığı açıklar ve nasıl kullanılacağını açıklar. Daha fazla bilgi için bkz.

- [İmleç Kitaplığı ve Düzey 1 ODBC Sürücüleri](#_core_the_cursor_library_and_level_1_odbc_drivers)

- [Konumlandırılmış Güncellemeler ve Zaman Damgası Sütunları](#_core_positioned_updates_and_timestamp_columns)

- [İmleç Kitaplığını Kullanma](#_core_using_the_cursor_library)

ODBC İmleç Kitaplığı, ODBC Sürücü Yöneticisi ile sürücü arasında bulunan dinamik bağlantı kitaplığıdır (DLL). ODBC açısından, bir sürücü kayıt kümesindeki konumunu izlemek için bir imleç tutar. İmleç, zaten kaydırdığınız kayıt kümesindeki konumu işaretler - geçerli kayıt.

## <a name="cursor-library-and-level-1-odbc-drivers"></a><a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a>İmleç Kitaplığı ve Düzey 1 ODBC Sürücüleri

ODBC İmleç Kitaplığı Düzey 1 sürücülerine aşağıdaki yeni yetenekleri verir:

- İleri ve geri kaydırma. Düzey 2 sürücüleri zaten kaydırılabilir olduğundan imleç kitaplığı gerekmez.

- Anlık görüntüler için destek. İmleç kitaplığı anlık görüntünün kayıtlarını içeren bir arabellek yönetir. Bu arabellek, programınızın kayıtları olan silme ve yapılan tonları yansıtır, ancak diğer kullanıcıların eklemelerini, silmelerini veya düzenledirmelerini yansıtmaz. Bu nedenle, anlık görüntü yalnızca imleç kitaplığı arabelleği kadar geçerlidir. Arabellek de arama `Requery`kadar kendi eklemeler yansıtmaz. Dinamitler imleç kitaplığını kullanmaz.

İmleç kitaplığı, normalde sürücünüz tarafından desteklenmeseler bile anlık görüntüler (statik imleçler) sağlar. Sürücünüz statik imleçleri zaten destekliyorsa, anlık görüntü desteği almak için imleç kitaplığını yüklemeniz gerekmez. İmleç kitaplığını kullanıyorsanız, yalnızca anlık görüntüler ve yalnızca ileri kayıt kümelerini kullanabilirsiniz. Sürücünüz damasetleri (KEYSET_DRIVEN imleçleri) destekliyorsa ve bunları kullanmak istiyorsanız, imleç kitaplığını kullanmamalısınız. Hem anlık görüntüleri hem de dynaset'i kullanmak istiyorsanız, `CDatabase` sürücünüz her ikisini de desteklemedikçe bunları iki farklı nesneye (iki farklı bağlantı) dayandırmalısınız.

## <a name="positioned-updates-and-timestamp-columns"></a><a name="_core_positioned_updates_and_timestamp_columns"></a>Konumlandırılmış Güncellemeler ve Zaman Damgası Sütunları

> [!NOTE]
> ODBC veri kaynaklarına, bu konuda açıklandığı gibi MFC ODBC sınıfları veya MFC Veri Erişim Nesnesi (DAO) sınıfları aracılığıyla erişilebilir.

> [!NOTE]
> ODBC sürücünüz `SQLSetPos`destekliyorsa , mfc'nin kullandığı şey varsa, bu konu sizin için geçerli değildir.

Çoğu Düzey 1 sürücüsü konumlandırılmış güncelleştirmeleri desteklemez. Bu tür sürücüler, düzey 2 sürücülerinin bu konudaki yeteneklerini taklit etmek için imleç kitaplığına güvenir. İmleç kitaplığı değişmeyen alanlarda aranan bir güncelleştirme yaparak konumlandırılmış güncelleştirme desteğini taklit eder.

Bazı durumlarda, bir kayıt kümesi bu değişmeyen alanlardan biri olarak bir zaman damgası sütunu içerebilir. Zaman damgası sütunları içeren tablolarla MFC kayıt kümelerinin kullanılmasında iki sorun ortaya çıkar.

İlk sorun, zaman damgası sütunlu tablolarda güncelleştirilebilir anlık görüntülerle ilgilidir. Anlık görüntünün bağlı olduğu tabloda bir zaman damgası `Requery` sütunu `Edit` `Update`varsa, aradıktan sonra aramanız gerekir ve . Değilse, aynı kaydı yeniden edinemeyebilirsiniz. Aradiğinizde `Edit` ve `Update`ardından, kayıt veri kaynağına yazılır ve zaman damgası sütunu güncelleştirilir. `Requery`Aramazsanız, anlık görüntünüzdeki kaydın zaman damgası değeri artık veri kaynağındaki ilgili zaman damgası ile eşleşmez. Kaydı yeniden güncelleştirmeyi denediğinizde, veri kaynağı uyumsuzluk nedeniyle güncelleştirmeye izin vermeyebilir.

İkinci sorun, saat ve tarih bilgilerini `RFX_Date` bir tabloya veya tablodan aktarmak için işlevle birlikte kullanıldığında [CTime](../../atl-mfc-shared/reference/ctime-class.md) sınıfının sınırlamalarıyla ilgilidir. Nesnenin `CTime` işlenmesi, veri aktarımı sırasında ekstra ara işleme şeklinde bazı ek yükleri uygular. `CTime` Nesnelerin tarih aralığı da bazı uygulamalar için çok sınırlayıcı olabilir. İşlevin `RFX_Date` yeni bir sürümü, `CTime` nesne yerine ODBC *TIMESTAMP_STRUCT* parametresi alır. Daha fazla bilgi `RFX_Date` için *MFC Başvurusu'ndaki* [Makrolar ve Globaller'e](../../mfc/reference/mfc-macros-and-globals.md) bakın.

## <a name="using-the-cursor-library"></a><a name="_core_using_the_cursor_library"></a>İmleç Kitaplığını Kullanma

Bir veri kaynağına bağlandığınızda - [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [CDatabase::Open-](../../mfc/reference/cdatabase-class.md#open) numaralı telefonu arayarak veri kaynağı için imleç kitaplığını kullanıp kullanmayacağınızı belirtebilirsiniz. Bu veri kaynağında anlık görüntü oluşturuyorsanız, `CDatabase::useCursorLib` parametredeki `dwOptions` seçeneği `OpenEx` *bUseCursorLib* parametresi için `Open` DOĞRU olarak belirtin (varsayılan değer TRUE'dur). ODBC sürücünüz dinamitleri destekliyorsa ve veri kaynağında dinamit açmak istiyorsanız, imleç kitaplığını kullanmayın (dinamitler için gereken bazı sürücü işlevlerini maskeler). Bu durumda, *bUseCursorLib* parametresi için FALSE'yi `Open`belirtmeyin `CDatabase::useCursorLib` `OpenEx` veya belirtmeyin.

## <a name="see-also"></a>Ayrıca bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)
