---
title: MFC'de Windows Yuvaları
ms.date: 11/04/2016
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
ms.openlocfilehash: 8e5562b028d3d9b7cba4b47716b63fd1392c514f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371091"
---
# <a name="windows-sockets-in-mfc"></a>MFC'de Windows Yuvaları

> [!NOTE]
> MFC, Windows Soketleri 1'i destekler, ancak [Windows Soketleri 2'yi](/windows/win32/WinSock/windows-sockets-start-page-2)desteklemez. Windows Sockets 2 ilk Windows 98 ile sevk ve Windows 2000 ile birlikte sürümüdür.

MFC, iki MFC sınıfında somutlaşan Windows Soketleri ile ağ iletişim programları yazmak için iki model sağlar. Bu makalede, bu modeller ve daha fazla ayrıntı MFC soketleri desteği açıklanmaktadır. "Soket" iletişimin bir bitiş noktasıdır: uygulamanızın ağdaki diğer Windows Soketleri uygulamalarıyla iletişim kurduğu bir nesne.

Soket kavramının bir açıklaması da dahil olmak üzere Windows Soketleri hakkında bilgi için [Bkz. Windows Soketleri: Arka Plan.](../mfc/windows-sockets-background.md)

## <a name="sockets-programming-models"></a><a name="_core_sockets_programming_models"></a>Soketprogramlama Modelleri

İki MFC Windows Soketleri programlama modeli aşağıdaki sınıflar tarafından desteklenir:

- `CAsyncSocket`

   Bu sınıf, Windows Soketleri API'sini kapsüller. [CAsyncSocket,](../mfc/reference/casyncsocket-class.md) ağ programlamayı bilen ve programlama esnekliğini doğrudan soketapi'ne isteyen ancak ağ olaylarının bildirimi için geri arama işlevlerinin kolaylığını isteyen programcılar içindir. C++'da kullanılmak üzere nesne yönelimli biçimde paketleme soketleri dışında, bu sınıf ala¤layan tek ek soyutlama, soketle ilgili windows iletilerini geri arama lara dönüştürmektir. Daha fazla bilgi için [Bkz. Windows Soketleri: Soket Bildirimleri.](../mfc/windows-sockets-socket-notifications.md)

- `CSocket`

   Türetilen bu `CAsyncSocket`sınıf, bir MFC [CArchive](../mfc/reference/carchive-class.md) nesnesi aracılığıyla soketlerle çalışmak için daha yüksek bir düzey soyutlama sağlar. Arşivli bir soket kullanmak, MFC'nin dosya serileştirme protokolünü kullanmaya büyük ölçüde benzer. Bu, `CAsyncSocket` modelden daha kolay kullanılmasını sağlar. [CSocket,](../mfc/reference/csocket-class.md) Windows Sockets `CAsyncSocket` API'lerini kapsülleyen birçok üye işlevi devralır; bu işlevlerin bazılarını kullanmak ve genel olarak soket programlama anlamak zorunda kalacaktır. Ama `CSocket` kendinizi ham API veya sınıf `CAsyncSocket`kullanarak yapmak zorunda olacağını iletişimbirçok yönlerini yönetir. En önemlisi, `CSocket` senkron çalışması için gerekli olan engelleme (Windows iletilerinin arka `CArchive`plan işleme ile) sağlar.

Oluşturma ve `CSocket` `CAsyncSocket` kullanma ve nesneleri Windows Soketleri açıklanmıştır: Arşiv ve Windows Soketleri [ile Soketler kullanma:](../mfc/windows-sockets-using-sockets-with-archives.md) [Sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md).

## <a name="windows-sockets-dlls"></a><a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>Windows Soketleri DLls

Microsoft Windows işletim sistemleri, Windows Sockets dinamik bağlantı kitaplıklarını (DLL) sağlar. Visual C++ uygun üstbilgi dosyalarını ve kitaplıklarını ve Windows Soketleri belirtimini sağlar.

Windows Soketleri hakkında daha fazla bilgi için bkz:

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

- [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: İşlem Dizisi](../mfc/windows-sockets-sequence-of-operations.md)

- [Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Yuva Sınıflarından Türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Yuvaları: Yuva Bildirimleri](../mfc/windows-sockets-socket-notifications.md)

- [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)

- [Windows Yuvaları: Bayt Sıralama](../mfc/windows-sockets-byte-ordering.md)

- [Windows Yuvaları: Dizeleri Dönüştürme](../mfc/windows-sockets-converting-strings.md)

- [Windows Yuvaları: Bağlantı Noktaları ve Yuva Adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md)

## <a name="see-also"></a>Ayrıca bkz.

[Windows Soketleri](../mfc/windows-sockets.md)
