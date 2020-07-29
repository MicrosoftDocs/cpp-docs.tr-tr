---
title: 'Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
ms.openlocfilehash: 275a6c274648225fedcec9d42c280f77af68158e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226782"
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek

Bu makalede, [CSocket](../mfc/reference/csocket-class.md)sınıfının kullanımına ilişkin bir örnek sunulmaktadır. Örnek, `CArchive` verileri bir yuva aracılığıyla seri hale getirmek için nesneleri kullanır. Bu, bir dosyadan veya bir dosyaya belge serileştirmesi olmadığına unutmayın.

Aşağıdaki örnek, nesneleri aracılığıyla veri göndermek ve almak için Arşivi nasıl kullanacağınızı gösterir `CSocket` . Örnek, uygulamanın iki örneğinin (aynı makinede veya ağ üzerindeki farklı makinelerde) veri alışverişi yapmak üzere tasarlanmıştır. Bir örnek, diğer örneğin aldığı ve aldığını bildiren verileri gönderir. Uygulama bir Exchange başlatabilir ve sunucu ya da başka bir uygulamaya istemci olarak hareket edebilir. Aşağıdaki işlev, uygulamanın görünüm sınıfında tanımlanmıştır:

[!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]

Bu örnekle ilgili en önemli şey, yapısı bir MFC işlevinin bu şekilde paraleldir `Serialize` . `PacketSerialize`Üye işlevi **`if`** yan tümce içeren bir deyimden oluşur **`else`** . İşlev, iki [CArchive](../mfc/reference/carchive-class.md) başvuruyu parametre olarak alır: *Ardata* ve *arack*. *Ardata* Arşiv nesnesi depolama (gönderme) için ayarlandıysa, **`if`** dal yürütülür; Aksi takdirde, *ardata* yükleme için ayarlandıysa (alma) işlev **`else`** dalı alır. MFC 'de serileştirme hakkında daha fazla bilgi için bkz. [serileştirme](../mfc/how-to-make-a-type-safe-collection.md).

> [!NOTE]
> *Arack* Arşivi nesnesinin, *ardata*'ın tersi olduğu varsayılır. *Ardata* gönderme için ise, *Aracı* alır ve listesiyse doğru olur.

Göndermek için örnek işlevi, her zaman Gösterim amacıyla bazı rastgele veriler oluşturan belirli bir sayıda döngü döngüsü. Uygulamanız bir dosya gibi bazı kaynaklardan gerçek verileri elde eder. *Ardata* Arşivi ekleme operatörü (), **<<** art arda üç veri öbekinin akışını göndermek için kullanılır:

- Verilerin yapısını belirten bir "üst bilgi" (Bu durumda, *bValue* değişkeninin değeri ve kaç kopya gönderileceğini).

   Bu örnek için her iki öğe de rastgele oluşturulur.

- Verilerin belirtilen sayıda kopyası.

   İç **`for`** döngü, *bValue değerini* belirtilen sayıda gönderir.

- Alıcının kullanıcısına gösterdiği *strText* adlı bir dize.

Alma işlemi için işlev benzer şekilde çalışır, ancak **>>** arşivden verileri almak için Arşiv 'in ayıklama işlecini () kullanması gerekir. Alıcı uygulama aldığı verileri doğrular, son "alındı" iletisini görüntüler ve ardından gönderen uygulamanın görüntülemesi için "gönderildi" iletisini bildiren bir ileti gönderir.

Bu iletişim modelinde, *strText* değişkeninde gönderilen ileti olan "alındı" sözcüğü iletişimin diğer ucunda görüntülenmek içindir. bu nedenle, alıcı kullanıcıya belirli sayıda veri paketi alındığını belirtir. Alıcı, özgün gönderenin ekranında görüntülenmek üzere "gönderildi" yazan benzer bir dize ile yanıt verir. Her iki dizenin de alınması, başarılı iletişimin oluştuğunu gösterir.

> [!CAUTION]
> Oluşturulan (MFC olmayan) sunucularla iletişim kurmak için bir MFC istemci programı yazıyorsanız, arşiv aracılığıyla C++ nesneleri göndermeyin. Sunucu, göndermek istediğiniz nesne türlerini anlayan bir MFC uygulaması değilse, nesnelerinizi alamaz ve seri durumdan çıkarmayabilir. [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md) makalesindeki bir örnek, bu türden bir iletişim gösterir.

Daha fazla bilgi için bkz. Windows Yuvaları belirtimi: **htonl**, **hton**, **ntohl**, **ntohs**. Ayrıca, daha fazla bilgi için bkz.

- [Windows Yuvaları: yuva sınıflarından türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Yuvaları: yuvalar, arşivleri ile nasıl çalışır?](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CArchive:: ısdepo](../mfc/reference/carchive-class.md#isstoring)<br/>
[CArchive:: operator <<](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive:: operator >>](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive:: Flush](../mfc/reference/carchive-class.md#flush)<br/>
[CObject:: serileştirme](../mfc/reference/cobject-class.md#serialize)
