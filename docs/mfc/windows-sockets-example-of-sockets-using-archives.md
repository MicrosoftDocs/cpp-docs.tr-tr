---
title: 'Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
ms.openlocfilehash: 253a65430ae230fbc4deeb9bd5288f28237310d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371084"
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek

Bu makalede, [csocket](../mfc/reference/csocket-class.md)sınıfı kullanma örneği sunar. Örnek, verileri `CArchive` bir soket aracılığıyla seri hale getirmek için nesneleri kullanır. Bunun bir dosyaya veya dosyadan belge serileştirme olmadığını unutmayın.

Aşağıdaki örnek, nesneler üzerinden `CSocket` veri göndermek ve almak için arşivi nasıl kullandığınızı göstermektedir. Örnek, uygulamanın iki örneğinin (aynı makinede veya ağdaki farklı makinelerde) veri alışverişi sağlayacak şekilde tasarlanmıştır. Bir örnek, diğer örnek alır ve kabul verileri gönderir. Her iki uygulama da bir değişim başlatabilir ve sunucu olarak veya diğer uygulamaya istemci olarak hareket edebilir. Uygulamanın görünüm sınıfında aşağıdaki işlev tanımlanır:

[!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]

Bu örnekle ilgili en önemli şey, yapısının bir `Serialize` MFC işlevine paralel olmasıdır. Üye `PacketSerialize` **işlev, başka** bir yan tümcesi olan **bir if** deyiminden oluşur. İşlev parametreler olarak iki [CArchive](../mfc/reference/carchive-class.md) referansı alır: *arData* ve *arAck*. *arData* arşiv nesnesi depolama (gönderme) için ayarlanmışsa, **if** şubesi yürütür; aksi takdirde, *arData* yükleme (alma) için ayarlanmışsa işlev **başka** bir dalı alır. MFC'de serileştirme hakkında daha fazla bilgi için [Serileştirme'ye](../mfc/how-to-make-a-type-safe-collection.md)bakın.

> [!NOTE]
> *ArAck* arşiv nesnesi *arData*tersi olduğu varsayılır. *arData* göndermek içinise, *arAck* alır ve tersi doğrudur.

Göndermek için, örnek işlev, her seferinde gösteri amacıyla bazı rasgele veriler oluşturarak belirli sayıda döngü oluşturur. Uygulamanız, dosya gibi bazı kaynaklardan gerçek veri elde eder. *arData* arşivinin ekleme işleci (**<<**) ardışık üç veri yığınından oluşan bir akış göndermek için kullanılır:

- Verilerin doğasını (bu durumda, *bValue* değişkeninin değerini ve kaç kopya gönderilecek) belirten bir "üstbilgi".

   Her iki öğe de bu örnek için rasgele oluşturulur.

- Verilerin belirtilen kopya sayısı.

   Döngü **için** iç *bValue* kez belirtilen sayıda gönderir.

- Alıcının kullanıcısına görüntülenebilen *strText* adlı dize.

Almak için, işlev arşivden veri almak için arşivçıkarma işleci**>>**() kullanması dışında, benzer şekilde çalışır. Alıcı uygulama aldığı verileri doğrular, son "Alınan" iletiyi görüntüler ve ardından gönderen uygulamanın görüntülenmesi için "Gönderildi" yazan bir iletiyi geri gönderir.

Bu iletişim modelinde, *strText* değişkeninde gönderilen "Alınan" sözcüğü, iletişimin diğer ucunda görüntülenmek üzeredir, bu nedenle alıcı kullanıcıya belirli sayıda veri alındığını belirtir. Alıcı, özgün gönderenin ekranında görüntülenmek üzere "Gönderildi" yazan benzer bir dizeyle yanıt verir. Her iki dize nin alınması, başarılı iletişimin gerçekleştiğini gösterir.

> [!CAUTION]
> Yerleşik (MFC olmayan) sunucularla iletişim kurmak için bir MFC istemci programı yazıyorsanız, arşiv üzerinden C++ nesneleri göndermeyin. Sunucu göndermek istediğiniz nesne türlerini anlayan bir MFC uygulaması olmadığı sürece, nesnelerinizi alıp deserialize edemez. Makalede [Windows Soketleri: Bayt Sipariş](../mfc/windows-sockets-byte-ordering.md) bu tür bir iletişim gösterir bir örnek.

Daha fazla bilgi için, Windows Soketleri Belirtimi bakınız: **htonl**, **htons**, **ntohl**, **ntohs**. Ayrıca, daha fazla bilgi için bkz:

- [Windows Yuvaları: Yuva Sınıflarından Türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CArchive::IsStoring](../mfc/reference/carchive-class.md#isstoring)<br/>
[CArchive::operatör <<](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive::operatör >>](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive::Flush](../mfc/reference/carchive-class.md#flush)<br/>
[CObject::Serialize](../mfc/reference/cobject-class.md#serialize)
