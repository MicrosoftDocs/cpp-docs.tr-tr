---
title: 'Windows Yuvaları: Yuvaların arşivlerle çalışması'
ms.date: 11/19/2018
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
ms.openlocfilehash: 3af94bc881276238f1a8d2dbeeee4dca1f173a4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389451"
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows Yuvaları: Yuvaların arşivlerle çalışması

Bu makalede açıklanır nasıl bir [CSocket](../mfc/reference/csocket-class.md) nesnesi bir [CSocketFile](../mfc/reference/csocketfile-class.md) nesnesi ve bir [CArchive](../mfc/reference/carchive-class.md) nesnesi, bir Windows aracılığıyla veri gönderme ve alma basitleştirmek için birleştirilir Yuva.

Makaleyi [Windows Yuvaları: Yuva kullanarak arşivleri örneği](../mfc/windows-sockets-example-of-sockets-using-archives.md) sunan `PacketSerialize` işlevi. Arşiv nesnesinde `PacketSerialize` örnek bir MFC için geçirilen bir arşiv nesnesi gibi çalışır [serileştirme](../mfc/reference/cobject-class.md#serialize) işlevi. Temel fark yuva için standart olmayan arşiv bağlı [CFile](../mfc/reference/cfile-class.md) (genellikle bir disk dosya ile ilişkilendirilmiş) nesne ancak çok bir `CSocketFile` nesne. Bir disk dosyasına bağlanmak yerine `CSocketFile` nesne bağlandığı bir `CSocket` nesne.

A `CArchive` nesnesi bir arabellek yönetir. Depolama (gönderen) arşiv arabelleğinin dolduğunda, ilişkili bir `CFile` arabellek içeriği nesneyi yazar. Bir yuva için bağlı bir arşiv arabelleğinin düzenleniyor bir ileti göndermeye eşdeğerdir. Bir yükleme (alma) arşiv arabelleğinin dolduğunda `CFile` nesne Okuma arabelleği yeniden kullanılabilir olana kadar durdurur.

Sınıf `CSocketFile` türetildiği `CFile`, ancak desteklemediği [CFile](../mfc/reference/cfile-class.md) konumlama işlevleri gibi üye işlevleri (`Seek`, `GetLength`, `SetLength`, vb.), İşlevler (kilitleme `LockRange`, `UnlockRange`), veya `GetPosition` işlevi. Tüm [CSocketFile](../mfc/reference/csocketfile-class.md) nesne gerçekleştirmelisiniz ilişkili gelen veya bayt dizisi okuma veya yazma `CSocket` nesne. Bir dosya sürecine dahil değildir çünkü gibi işlemler `Seek` ve `GetPosition` hiçbir mantıklı. `CSocketFile` türetilen `CFile`, bunu genellikle tüm bu üye işlevleri devralır. Bu, desteklenmeyen önlemek için `CFile` üye işlevleri kılınır `CSocketFile` atmak için bir [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md).

`CSocketFile` Nesne çağırır üye işlevleri kendi `CSocket` veri göndermek ve almak için nesne.

Aşağıdaki şekilde, iletişimin her iki tarafında bu nesneleri arasındaki ilişkiler gösterilmektedir.

![CArchive CSocketFile ve CSocket](../mfc/media/vc38ia1.gif "CArchive CSocketFile ve CSocket") <br/>
CArchive CSocketFile ve CSocket

Görünen Bu karmaşıklığı amacı, yuva ayrıntıları, kendiniz yönetme ihtiyacını kalkanı sağlamaktır. Yuva, dosya ve arşiv oluşturun ve arşive ekleme veya arşivden ayıklama gönderen veya alıcı veri ardından başlayın. [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md), ve [CSocket](../mfc/reference/csocket-class.md) arka planda ayrıntılarını yönetme.

A `CSocket` nesnedir aslında iki durumlu nesne: bazen zaman uyumsuz (Normal durumu) ve bazen zaman uyumlu. Zaman uyumsuz durumuna bir yuva framework zaman uyumsuz bildirimler alabilir. Ancak, veri gönderme veya alma gibi bir işlem sırasında yuva zaman uyumlu olur. Başka bir deyişle, zaman uyumlu işlem tamamlanıncaya kadar yuva başka zaman uyumsuz bildirimler alırsınız. Modu geçiş için örneğin, aşağıdaki gibi bunu oluşturabilirsiniz:

[!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]

Varsa `CSocket` uygulanmamış iki durumlu nesnesi olarak, önceki bildirim işleme ancak aynı olay türü için ek bildirim almak mümkün olabilir. Örneğin, alabilirsiniz bir `OnReceive` bildirim işlenirken bir `OnReceive`. Yukarıdaki kod parçasında ayıklama `str` arşivden özyineleme neden olabilir. Bir durumdan diğerine geçen tarafından `CSocket` ilave bildirimler engelleyerek özyineleme engeller. Genel bildirim içinde hiç bildirim kuralıdır.

> [!NOTE]
> A `CSocketFile` (sınırlı) dosyası olarak kullanılabilir bir `CArchive` nesne. Varsayılan olarak, `CSocketFile` oluşturucunun *bArchiveCompatible* parametresi **TRUE**. Bu dosya nesnesini bir arşiv ile kullanılmak üzere olduğunu belirtir. Bir arşiv olmadan dosya nesnesini kullanmak için geçirin **FALSE** içinde *bArchiveCompatible* parametresi.

"Arşiv uyumlu" modunda bir `CSocketFile` nesne "kilitlenme." tehlikesi azaltır ve daha iyi performans sağlar Gönderme ve alma yuvalarına birbirleri üzerinde bekliyor veya ortak bir kaynağı bekleyen bir kilitlenme oluşur. Bu durum meydana gelebilir `CArchive` nesne çalıştığınız `CSocketFile` , sahip olduğu gibi bir `CFile` nesne. İle `CFile`, Arşiv, istenenden daha az bayt alırsa, dosya sonuna ulaşıldı varsayabilirsiniz. İle `CSocketFile`ancak, veri tabanlı ileti; arabellek birden fazla ileti içerebilir, bu nedenle, istenen bayt sayısından daha az alan değil yaptığından dosya sonu. Uygulama ile olabileceği gibi bu durumda engellemez `CFile`, arabellek boş olana kadar iletilerini arabellekteki okuma devam edebilir. [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) işlevi `CArchive` arşivin arabellek böyle bir durumda durumunu izlemek için yararlıdır.

Daha fazla bilgi için [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CObject::Serialize](../mfc/reference/cobject-class.md#serialize)
