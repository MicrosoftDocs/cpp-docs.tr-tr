---
title: 'Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
ms.openlocfilehash: 285053c79b13ebea23aedc7dae52eabe85f55a12
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436276"
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek

Bu makalede sınıfı kullanmanın bir örnek sunulmaktadır [CSocket](../mfc/reference/csocket-class.md). Örnek kullanan `CArchive` nesnelerin bir yuva aracılığıyla verileri seri hale getirme. Bu belge serileştirme için veya bir dosyadan olmadığını unutmayın.

Aşağıdaki örnekte, arşiv aracılığıyla veri göndermek ve almak için nasıl kullanacağınız gösterilmektedir. `CSocket` nesneleri. Örneğin, iki örnek uygulamanın (aynı makinede veya farklı makinelerde ağ üzerinde) veri değişimi şekilde tasarlanmıştır. Bir örneği, diğer örneği alır ve edilemeyeceğini verileri gönderir. Bir exchange ya da uygulama başlatabilir ve ya da başka bir uygulama için istemci veya sunucu olarak görev yapabilir. Aşağıdaki işlev uygulamanın görünümü sınıfında tanımlanır:

[!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]

Bu örnekle ilgili en önemli şey yapısı, bir MFC parallels olan `Serialize` işlevi. `PacketSerialize` Üye işlevi oluşur bir **varsa** deyimiyle bir **başka** yan tümcesi. İşlev iki alan [CArchive](../mfc/reference/carchive-class.md) parametre olarak başvuruları: *arData* ve *arAck*. Varsa *arData* arşiv nesne (gönderen) depolamak için ayarlanmış **varsa** dal yürütür; Aksi takdirde *arData* ayarlanır işlevi alır(alma)yüklemekiçin**başka** dal. MFC'de seri hale getirme hakkında daha fazla bilgi için bkz: [serileştirme](../mfc/how-to-make-a-type-safe-collection.md).

> [!NOTE]
>  *ArAck* arşiv nesne olduğu varsayılır tersini *arData*. Varsa *arData* göndermek *arAck* alabileceği ve listesiyse true.

Gönderme belirtilen birkaç kez, Tanıtım amaçlı bazı rastgele bir veri üreterek her zaman için örnek işlevi döngüde kalır. Uygulamanızın gerçek veri dosyası gibi bir kaynaktan elde edebilirsiniz. *ArData* arşivin ekleme operatörü (**<<**) üç ardışık öbekler halinde veri akışı göndermek için kullanılır:

- "header" veri yapısını belirtir (Bu durumda, değerini *bDeğer* değişkeni ve kopya gönderilir).

   Her iki öğe, bu örnek için rastgele oluşturulur.

- Verilerin kopyaları belirtilen sayısı.

   İç **için** döngü gönderir *bDeğer* belirtilen sayısı.

- Bir dize olarak adlandırılan *strText* , alıcı, kullanıcıya görüntüler.

Arşivin ayıklama işleci kullanması hariç, alan için işlev benzer şekilde, çalışır (**>>**) arşivden veri almak için. Alıcı uygulamasına gönderen uygulamayı görüntülemek için verileri alır, son "Alınan" iletisi görüntüler ve ardından "Gönderilen" ifadesini içeren bir ileti gönderir doğrular.

Bu iletişimler modelde "Alınan" sözcüğü gönderilen ileti *strText* değişken olduğundan iletişim diğer uçtaki görüntülemek için belirli bir sayıda veri paketlerini yapıldığını alıcı kullanıcıya belirtir aldı. Alıcı, özgün gönderenin ekranda diyor "gönderilen", görüntü için benzer bir dize ile yanıtlar. İki dizenin giriş başarılı iletişim oluştuğunu gösterir.

> [!CAUTION]
>  C++ nesnelerinin arşiv aracılığıyla kurulan (MFC olmayan) sunucularıyla iletişim kurmak için bir MFC istemci programı yazıyorsanız göndermeyin. Göndermek istediğiniz nesne türlerini anlayan bir MFC uygulaması sunucu olmadığı sürece, alma ve nesnelerinizin seri durumdan mümkün olmayacaktır. Bu makaledeki örnek [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md) bu tür bir iletişim gösterir.

Daha fazla bilgi için Windows Sockets belirtime bakın: **htonl**, **htons**, **ntohl**, **ntohs**. Ayrıca, daha fazla bilgi için bkz:

- [Windows Yuvaları: Yuva Sınıflarından Türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CArchive::IsStoring](../mfc/reference/carchive-class.md#isstoring)<br/>
[CArchive::operator <<](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive::operator >>](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive::Flush](../mfc/reference/carchive-class.md#flush)<br/>
[CObject::Serialize](../mfc/reference/cobject-class.md#serialize)

