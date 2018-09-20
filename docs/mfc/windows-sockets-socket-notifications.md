---
title: 'Windows Yuvaları: Yuva bildirimleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90dfddb72ba3362f0e6595ee4f34ea2145bb85ec
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375274"
---
# <a name="windows-sockets-socket-notifications"></a>Windows Yuvaları: Yuva Bildirimleri

Bu makalede, yuva sınıflarından bildirim işlevleri açıklanmaktadır. Bu üye işlevleri framework yuva nesnenizin önemli olayları bildirmek için çağırdığı geri çağırma işlevlerdir. Bildirim işlevler şunlardır:

- [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive): olduğundan veri arabelleği için çağırarak almak için bu yuva bildirir [alma](../mfc/reference/casyncsocket-class.md#receive).

- [OnSend](../mfc/reference/casyncsocket-class.md#onsend): Bu yuva artık veri çağırarak gönderebilmesi gerektiğini bildirir [Gönder](../mfc/reference/casyncsocket-class.md#send).

- [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept): çağırarak bağlantı isteklerini kabul edebilirsiniz dinleme bu yuva bildirir [kabul](../mfc/reference/casyncsocket-class.md#accept).

- [Tetiklediğinde çalıştırılan](../mfc/reference/casyncsocket-class.md#onconnect): kendi bağlantı denemesi tamamlanan bu yuva bağlantı bildirir: belki de başarıyla veya belki de hata.

- [OnClose](../mfc/reference/casyncsocket-class.md#onclose): uygulamanın bağlı olduğu yuva kapatıldı bu yuva bildirir.

    > [!NOTE]
    >  Ek bildirim işlevi [OnOutOfBandData](../mfc/reference/casyncsocket-class.md#onoutofbanddata). Bu bildirim alma yuvası göndermek için "bant-" veri gönderme yuva olduğunu bildirir. Bant dışı verileri, her bağlı Akış yuvaları çifti ile ilişkili mantıksal olarak bağımsızdır bir kanaldır. Bant dışı kanal, genellikle "Acil" veri göndermek için kullanılır. MFC, bant dışı verileri destekler. Sınıfıyla çalışan kullanıcılar Gelişmiş [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md) bant dışı kanal, ancak kullanıcılar sınıfı kullanmanız gerekebilir [CSocket](../mfc/reference/csocket-class.md) kullanmasını önerilmez. Daha kolay yolu, bu tür verileri geçirmek için ikinci bir yuva oluşturmaktır. Bant dışı veriler hakkında daha fazla bilgi için bkz: Windows SDK'da bulunan Windows yuva belirtimi.

Sınıfından türetirseniz `CAsyncSocket`, uygulamanıza olaylarının bu ağ için bildirim işlevleri geçersiz kılmanız gerekir. Sınıfından bir sınıf türetirseniz `CSocket`, ilgilenilen bildirim işlevleri geçersiz kılınıp kılınmayacağını sizin tercihinize bağlıdır. Ayrıca `CSocket` kendisi, bu durumda bildirim işlev varsayılan olarak hiçbir şey yapmadan.

Bu işlevler geçersiz kılınabilir bir geri çağırma işlevlerdir. `CAsyncSocket` ve `CSocket` dönüştürme iletileri bildirimleri, ancak bunları kullanmak istiyorsanız bildirime yanıt nasıl çalıştığını uygulamalıdır. Bildirim işlevlerini, yuva gibi veri okumak için ilgilendiğiniz bir olayı, bildirim zaman çağrılır.

MFC zaman, bildirimde, yuva davranışı özelleştirmenize izin vermek için bildirim işlevleri çağırır. Örneğin, çağırabilirsiniz `Receive` gelen, `OnReceive` bildirim işlevi, diğer bir deyişle, olmaya bildirim veri okumak için çağırması `Receive` okumak için. Bu yaklaşım gerekli değildir, ancak geçerli bir senaryodur. Alternatif olarak, ilerleme durumunu izlemek için bildirim işlevini kullanabilir yazdırma **izleme** iletileri ve benzeri.

Bu bildirim bir yuva türetilmiş sınıftaki bildirim işlevleri geçersiz kılma ve bir uygulama sağlama yararlanabilirsiniz.

Veri gönderme veya alma gibi bir işlem sırasında bir `CSocket` nesne zaman uyumlu olur. Geçerli yuva istediği bildirim için beklerken zaman uyumlu aşamasında, diğer yuva için gereken herhangi bir bildirim kuyruğa alınır. (Örneğin, sırasında bir `Receive` çağrı, yuva okumak için bir bildirim ister.) Yuva, zaman uyumlu işlem tamamlanana ve yeniden zaman uyumsuz duruma sonra diğer Yuvalar sıraya alınan bildirimleri almaya başlayabilirsiniz.

> [!NOTE]
>  İçinde `CSocket`, `OnConnect` bildirim işlevini hiçbir zaman çağrılır. Bağlantılar için çağırmanızı `Connect`, bağlantı (başarıyla veya hata) tamamlandığında döndürülür. Bağlantı bildirimleri nasıl işleneceğini bir MFC Uygulama ayrıntısı olduğunu.

İşlev sınıfı altında her bildirim işlevi hakkında daha fazla ayrıntı için bkz `CAsyncSocket` içinde *MFC başvurusu*. Kaynak kodu ve MFC örnekleri hakkında bilgi için bkz: [MFC örnekleri](../visual-cpp-samples.md).

Daha fazla bilgi için bkz.:

- [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Yuva Sınıflarından Türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)

- [Windows Yuvaları: Bayt Sıralama](../mfc/windows-sockets-byte-ordering.md)

- [Windows Yuvaları: Dizeleri Dönüştürme](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

