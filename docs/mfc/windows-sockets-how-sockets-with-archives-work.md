---
title: 'Windows Yuvaları: Yuvaların arşivlerle çalışması | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c4f581acb0af27f44c88d59597e52b057991ee4
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954285"
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows Yuvaları: Yuvaların Arşivlerle Çalışması
Bu makalede açıklanır nasıl bir [CSocket](../mfc/reference/csocket-class.md) nesne, bir [CSocketFile](../mfc/reference/csocketfile-class.md) nesnesi ve [CArchive](../mfc/reference/carchive-class.md) nesnesi, bir Windows aracılığıyla veri gönderme ve alma basitleştirmek için birleştirilir Yuva.  
  
 Makaleyi [Windows Yuvaları: örnek, yuva kullanarak arşivler](../mfc/windows-sockets-example-of-sockets-using-archives.md) gösterir `PacketSerialize` işlevi. Arşiv nesnesinde `PacketSerialize` örnek bir MFC geçirilen bir arşiv nesnesi benzer çalışır [serileştirme](../mfc/reference/cobject-class.md#serialize) işlevi. Yuva için standart olmayan arşiv bağlı olduğu temel fark vardır [CFile](../mfc/reference/cfile-class.md) (genellikle bir disk dosyası ile ilişkili) nesne ancak çok bir `CSocketFile` nesnesi. Bir disk dosyasına bağlanmadığı yerine `CSocketFile` nesne bağlandığı bir `CSocket` nesnesi.  
  
 A `CArchive` nesnesi bir arabellek yönetir. Depolama (gönderen) arşiv arabellek dolduğunda, ilişkili bir `CFile` nesnesi arabellek içeriğini yazar. İleti gönderme için düzenleniyor yuvaya bağlı bir arşiv arabellek eşdeğerdir. Arşiv yüklenirken (alma) arabellek dolduğunda, `CFile` nesnesi, arabellek yeniden kullanılabilir hale gelene kadar okuma durdurur.  
  
 Sınıf `CSocketFile` türetilen `CFile`, ancak desteklemediği [CFile](../mfc/reference/cfile-class.md) konumlandırma işlevleri gibi üye işlevleri (`Seek`, `GetLength`, `SetLength`, vb.), işlevleri (kilitleme `LockRange`, `UnlockRange`), veya `GetPosition` işlevi. Tüm [CSocketFile](../mfc/reference/csocketfile-class.md) nesne gerçekleştirmelisiniz yazma veya okuma için veya ilişkili bayt dizisi veya `CSocket` nesnesi. Bir dosya dahil değil çünkü gibi işlemleri `Seek` ve `GetPosition` hiçbir anlamlıdır. `CSocketFile` türetilmiş `CFile`, tüm bu üye işlevleri devralan normalde. Bu, desteklenmeyen önlemek için `CFile` geçersiz kılınan üye işlevleri de `CSocketFile` atmak için bir [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md).  
  
 `CSocketFile` Nesnesi çağırır üye işlevlerini kendi `CSocket` veri göndermek ve almak için nesne.  
  
 Aşağıdaki şekilde iletişimi her iki tarafında bu nesneleri arasındaki ilişkiler gösterilmektedir.  
  
 ![CArchive, CSocketFile ve CSocket](../mfc/media/vc38ia1.gif "vc38ia1")  
CArchive, CSocketFile ve CSocket  
  
 Bu görünen karmaşıklık amacı yuva ayrıntılarını kendiniz yönetme gerekliliğini kalkanı sağlamaktır. Yuva, dosya ve Arşiv oluşturmak ve arşive ekleniyor veya arşivden ayıklanıyor verileri gönderen veya alıcı başlar. [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md), ve [CSocket](../mfc/reference/csocket-class.md) arka planda ayrıntılarını yönetme.  
  
 A `CSocket` nesnesidir gerçekte iki durumlu nesnesi: bazen zaman uyumsuz (normal durum) ve bazen zaman uyumlu. Zaman uyumsuz durumundayken yuva çerçevesinden zaman uyumsuz bildirimleri alabilirsiniz. Ancak, alma veya veri gönderme gibi bir işlem sırasında yuva zaman uyumlu olur. Bu, zaman uyumlu işlem tamamlanana kadar yuva başka zaman uyumsuz bildirimleri alacak anlamına gelir. Modu geçiş olduğundan, örneğin, aşağıdakine benzer bir şey yapabilirsiniz:  
  
 [!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]  
  
 Varsa `CSocket` uygulanmamış iki durumlu nesnesi olarak önceki bir bildirim işleme sırada aynı türde bir olayın için ek bildirim almak mümkün olabilir. Örneğin, alabilirsiniz bir `OnReceive` bildirim işlenirken bir `OnReceive`. Yukarıdaki kod parçasında ayıklanıyor `str` arşivden özyineleme neden olabilir. Durumları, geçiş tarafından `CSocket` ek bildirimleri engelleyerek özyineleme engeller. Genel kural hiçbir bildirimler bildirimleri içinde değil.  
  
> [!NOTE]
>  A `CSocketFile` (sınırlı) dosyası olarak da kullanılabilir bir `CArchive` nesnesi. Varsayılan olarak, `CSocketFile` Oluşturucusu'nın *bArchiveCompatible* parametresi **doğru**. Bu dosya nesnesi bir arşiv ile kullanılmak üzere olduğunu belirtir. Bir arşiv olmadan dosya nesnesi kullanmak için geçirmek **FALSE** içinde *bArchiveCompatible* parametresi.  
  
 Kendi "Arşiv uyumlu" modunda bir `CSocketFile` nesne daha iyi performans sağlar ve bir "kilitlenme." tehlike azaltır Gönderme ve alma yuva birbirlerine bekliyor veya ortak bir kaynak için bekleyen bir kilitlenme oluşur. Bu durum oluşabilir `CArchive` nesne çalıştığınız `CSocketFile` mu ile yolu bir `CFile` nesnesi. İle `CFile`, Arşiv, istenenden daha az sayıda bayt alırsa, dosya sonuna ulaşıldı varsayabilirsiniz. İle `CSocketFile`ancak, veri tabanlı ileti; arabellek birden fazla ileti içerebilir, bu nedenle istenen bayt sayısından az alma değil kapsıyor dosya sonu. Sahip olabileceği gibi bu durumda uygulamayı engellemez `CFile`, ve arabellek boş olana kadar arabellekteki iletileri okumak devam edebilirsiniz. [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) işlevi `CArchive` arşiv 's arabellek böyle bir durumda durumunu izlemek için yararlıdır.  
  
 Daha fazla bilgi için bkz: [Windows Yuvaları: yuvaların arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)   
 [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)

