---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: bir arşiv ile yuvalar nasıl çalışır?'
title: 'Windows Yuvaları: Yuvaların Arşivlerle Çalışması'
ms.date: 11/19/2018
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
ms.openlocfilehash: 19b24a9942b7405304c9037091266b4535bffbc3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263549"
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows Yuvaları: Yuvaların Arşivlerle Çalışması

Bu makalede bir [CSocket](../mfc/reference/csocket-class.md) nesnesi, bir [CSocketFile](../mfc/reference/csocketfile-class.md) nesnesi ve bir Windows yuvası aracılığıyla veri göndermeyi ve almayı basitleştirmek için bir [CArchive](../mfc/reference/carchive-class.md) nesnesinin nasıl birleştirileceği açıklanır.

[Windows Yuvaları: arşivleri kullanan yuvaların örneği](../mfc/windows-sockets-example-of-sockets-using-archives.md) `PacketSerialize` işlevi sunar. Örnekteki Arşiv nesnesi, bir `PacketSerialize` MFC [serileştirme](../mfc/reference/cobject-class.md#serialize) işlevine iletilen bir arşiv nesnesi gibi çok daha çalışır. Temel fark, yuvaların, bir standart [CFile](../mfc/reference/cfile-class.md) nesnesine (genellikle bir disk dosyasıyla ilişkili) değil, bir nesneye bağlı olması durumunda değil, `CSocketFile` Bir disk dosyasına bağlanmak yerine, `CSocketFile` nesne bir `CSocket` nesneye bağlanır.

Bir `CArchive` nesne bir arabelleği yönetir. Depolama (gönderme) Arşivi arabelleği dolduğunda, ilişkili bir `CFile` nesne arabelleğin içeriğini yazar. Bir yuvaya eklenen bir arşivin arabelleğini Temizleme, ileti gönderme ile eşdeğerdir. Yükleme (alma) Arşivi arabelleği dolduğunda, `CFile` arabellek yeniden kullanılabilir olana kadar nesne okumayı sonlandırır.

Sınıf `CSocketFile` öğesinden türetilir `CFile` , ancak konumlandırma işlevleri ( [](../mfc/reference/cfile-class.md) `Seek` , `GetLength` , `SetLength` , vb.), kilitleme işlevleri ( `LockRange` , `UnlockRange` ) veya `GetPosition` işlev gibi CFile üye işlevlerini desteklemez. Tüm [CSocketFile](../mfc/reference/csocketfile-class.md) nesneleri, ilişkili nesne ile veya arasında bayt yazma veya okuma dizileri olmalıdır `CSocket` . Bir dosya dahil olmadığından, ve gibi işlemler `Seek` `GetPosition` hiçbir fikir vermez. `CSocketFile``CFile`, ' den türetilir, bu nedenle normalde bu üye işlevlerinin tümünü devralınır. Bunu engellemek için, desteklenmeyen `CFile` üye işlevleri ' de `CSocketFile` bir [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)oluşturmak için üzerine yazılır.

`CSocketFile`Nesnesi, `CSocket` veri göndermek veya almak için nesnesinin üye işlevlerini çağırır.

Aşağıdaki şekilde, iletişimin her iki tarafında bu nesneler arasındaki ilişkiler gösterilmektedir.

![CArchive, CSocketFile ve CSocket](../mfc/media/vc38ia1.gif "CArchive, CSocketFile ve CSocket") <br/>
CArchive, CSocketFile ve CSocket

Bu belirgin karmaşıklığın amacı, yuvanın ayrıntılarını kendiniz yönetmek için sizi zorunludur. Yuva, dosya ve arşivi oluşturur, ardından verileri arşive ekleyerek veya arşivden çıkararak veri göndermeye veya almaya başlayabilirsiniz. [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md)ve [CSocket](../mfc/reference/csocket-class.md) , arka planda ayrıntıları yönetir.

Bir `CSocket` nesne aslında iki durumlu bir nesnedir: bazen zaman uyumsuz (olağan durum) ve bazen zaman uyumludur. Zaman uyumsuz durumunda, bir yuva çerçeveden zaman uyumsuz bildirimler alabilir. Ancak, veri alma veya gönderme gibi bir işlem sırasında yuva zaman uyumlu hale gelir. Bu, zaman uyumlu işlem tamamlanana kadar yuvanın daha fazla zaman uyumsuz bildirim almayacağı anlamına gelir. Modları geçtiğinde, örneğin, aşağıdakine benzer bir şey yapabilirsiniz:

[!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]

`CSocket`İki durumlu bir nesne olarak uygulanmadığından, önceki bir bildirimi işlerken aynı olay türü için ek bildirimler almak mümkün olabilir. Örneğin, `OnReceive` işlerken bir bildirim alabilirsiniz `OnReceive` . Yukarıdaki kod parçasında, `str` arşivden ayıklama özyinelemeye yol açabilir. Durumları değiştirerek, `CSocket` Ek bildirimleri engelleyerek özyinelemeyi önler. Genel kurala bildirim içinde bildirim yok.

> [!NOTE]
> Bir `CSocketFile` nesnesi olmayan (sınırlı) dosya olarak da kullanılabilir `CArchive` . Varsayılan olarak, `CSocketFile` oluşturucunun *bArchiveCompatible* parametresi **true**'dur. Bu, dosya nesnesinin bir arşiv ile kullanılmak üzere olduğunu belirtir. Dosya nesnesini arşiv olmadan kullanmak için, *bArchiveCompatible* parametresine **yanlış** geçirin.

"Arşiv uyumlu" modunda bir `CSocketFile` nesne daha iyi performans sağlar ve bir "kilitlenme" düzeyini azaltır. Hem gönderme hem de alma yuvaları birbirini beklerken veya ortak bir kaynak beklenirken bir kilitlenme oluşur. Bu durum, `CArchive` nesne bir nesneyle aynı şekilde çalıştığında meydana gelebilir `CSocketFile` `CFile` . İle `CFile` Arşiv, istenenden daha az bayt alırsa, dosyanın sonuna ulaşıldığını varsayabilir. `CSocketFile`Ancak, veriler ileti tabanlıdır; arabellekte birden çok ileti bulunabilir, bu nedenle istenen bayt sayısından daha az sayıda alma işlemi dosya sonunu göstermez. Uygulama, bu durumda olabileceği gibi engellemez `CFile` ve arabellek boşalıncaya kadar arabellekteki iletileri okumaya devam edebilir. İçindeki [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) işlevi, `CArchive` Bu tür bir durumda arşiv arabelleğinin durumunu izlemek için yararlıdır.

Daha fazla bilgi için bkz [. Windows Yuvaları: Arşivlerle yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CObject:: serileştirme](../mfc/reference/cobject-class.md#serialize)
