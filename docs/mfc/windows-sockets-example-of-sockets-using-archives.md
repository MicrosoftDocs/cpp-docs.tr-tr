---
title: 'Windows Yuvaları: Arşivlerle kullanılan yuvalara örnek | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02cd74a20f0ccc54a366c1a62d913ee30e72471a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek
Bu makalede sınıfını kullanarak bir örnek sunar [CSocket](../mfc/reference/csocket-class.md). Örnek kullanan `CArchive` yuva verilerine serileştirmek için nesneleri. Bu belge serileştirmesi için veya bir dosyadan olmadığını unutmayın.  
  
 Aşağıdaki örnekte, arşiv aracılığıyla veri göndermek ve almak için nasıl kullanacağınız gösterilmiştir `CSocket` nesneleri. Örneğin, uygulamanın (aynı makine üzerindeki veya ağ üzerindeki farklı makinelerde) iki örnek veri değişimi şekilde tasarlanmıştır. Bir örnek, diğer örneğe alan ve kabul ettikten verileri gönderir. Bir exchange ya da uygulama başlatabilir ve sunucu veya istemci diğer uygulama olarak davranamaz. Aşağıdaki işlevi uygulamanın görünümü sınıfında tanımlanır:  
  
 [!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]  
  
 Bu örnek hakkında en önemli şey yapısı, bir MFC paraleldir `Serialize` işlevi. **PacketSerialize** üye işlevi oluşur bir **varsa** deyimiyle bir **başka** yan tümcesi. İşlev iki alan [CArchive](../mfc/reference/carchive-class.md) parametre olarak başvuruları: `arData` ve `arAck`. Varsa `arData` arşiv nesne (gönderen) depolamak için ayarlanmış **varsa** dal yürütür; Aksi halde, eğer `arData` ayarlanmış işlev alır (alma) yüklemek için **başka** dal. MFC'de seri hale getirme hakkında daha fazla bilgi için bkz: [seri hale getirme](../mfc/how-to-make-a-type-safe-collection.md).  
  
> [!NOTE]
>  `arAck` Arşiv nesne olduğu varsayılır karşıtı `arData`. Varsa `arData` göndermek için olan `arAck` alır, ve ters geçerlidir.  
  
 Göndermek için belirtilen kaç kez, her zaman tanıtım amacıyla rastgele bazı verileri oluşturmak için örnek işlevi döngüsü. Uygulamanızı gerçek veri dosyası gibi bazı kaynağından elde edebilirsiniz. `arData` Arşiv'ın ekleme işleci (**<<**) üç ardışık öbekleri veri akışı göndermek için kullanılır:  
  
-   "Üstbilgisi" veri yapısını belirtir (Bu durumda, değeri `bValue` değişkeni ve kaç kopya gönderilir).  
  
     Her iki öğe, bu örnek için rastgele üretilir.  
  
-   Belirtilen sayıda kopyasını verileri.  
  
     İç **için** döngü gönderir `bValue` belirtilen sayısı.  
  
-   Bir dize olarak adlandırılan `strText` , kendi kullanıcı için alıcı görüntüler.  
  
 Arşiv 's ayıklama işleci kullanır ancak bu alma için işlev benzer şekilde çalışır (**>>**) arşivden veri almak için. Alma işlemini yapan uygulamanın alır, son "Alınan" iletisi görüntülenir ve ardından "Gönderilen" belirten bir ileti gönderir veri gönderen uygulama görüntülemek doğrular.  
  
 Bu iletişimler modelde, word "Alınan" iletisi gönderilen `strText` değişken olduğundan iletişim diğer uçtaki görüntülemek için belirli bir sayıda veri paketlerini alınmış olan alıcı kullanıcıya belirtir. Özgün gönderenin ekranda diyor "gönderilen", görüntü için benzer bir dizeyle alıcı yanıtlar. Her iki dize alınmasını başarılı iletişimi oluştuğunu gösterir.  
  
> [!CAUTION]
>  Kurulan (MFC olmayan) sunucularıyla iletişim kurmak için bir MFC istemci programı yazıyorsanız, arşiv C++ nesnelerde göndermeyin. Sunucu göndermek istediğiniz nesne türlerini özelliğini algılayan bir MFC uygulaması olmadığı sürece almak ve nesnelerinizin seri durumdan mümkün olmayacaktır. Makalede örnek [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md) bu tür bir iletişimi gösterir.  
  
 Windows Yuvaları belirtimi daha fazla bilgi için bkz: **htonl**, **htons**, **ntohl**, **ntohs**. Ayrıca, daha fazla bilgi için bkz:  
  
-   [Windows Yuvaları: Yuva Sınıflarından Türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)   
 [CArchive::IsStoring](../mfc/reference/carchive-class.md#isstoring)   
 [CArchive::operator <<](../mfc/reference/carchive-class.md#operator_lt_lt)   
 [CArchive::operator >>](../mfc/reference/carchive-class.md#operator_lt_lt)   
 [CArchive::Flush](../mfc/reference/carchive-class.md#flush)   
 [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)

