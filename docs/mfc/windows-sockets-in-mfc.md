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
ms.openlocfilehash: 44a4838a1cd863bd484701966a156be9f61f8988
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510618"
---
# <a name="windows-sockets-in-mfc"></a>MFC'de Windows Yuvaları

> [!NOTE]
>  MFC Windows Sockets 1 ' i destekler, ancak [Windows Sockets 2](/windows/win32/WinSock/windows-sockets-start-page-2)' i desteklemez. Windows Sockets 2 ilk olarak Windows 98 ile birlikte gelir ve Windows 2000 ' de yer alan sürümdür.

MFC, Windows Yuvaları olan ağ iletişim programlarını yazmak için iki model sağlar ve iki MFC sınıfına sahiptir. Bu makalede, bu modeller ve daha ayrıntılı olarak MFC Yuvaları desteği açıklanmaktadır. "Yuva" bir iletişim uç noktasıdır: uygulamanızın bir ağ üzerindeki diğer Windows Yuvaları uygulamalarıyla iletişim kurduğu nesne.

Yuva kavramının açıklaması da dahil olmak üzere Windows Yuvaları hakkında bilgi için bkz [. Windows Yuvaları: Arka](../mfc/windows-sockets-background.md)plan.

##  <a name="_core_sockets_programming_models"></a>Sockets programlama modelleri

İki MFC Windows Yuvaları programlama modeli aşağıdaki sınıflar tarafından desteklenir:

- `CAsyncSocket`

   Bu sınıf Windows Sockets API 'sini kapsüller. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) , ağ programlamayı bilen ve doğrudan yuvalar API 'sine programlama esnekliği isteyen ve ayrıca ağ olaylarının bildirilmesi için geri çağırma işlevlerinin rahatlığını tercih eden programcılar içindir. ' De C++kullanılmak üzere nesne odaklı biçimde paketleme yuvaları dışında, bu sınıfın sağladığı tek ek soyutlama, bazı yuvada ilgili Windows iletilerini geri çağırmaları dönüştürmektir. Daha fazla bilgi için bkz [. Windows Yuvaları: Yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md).

- `CSocket`

   Öğesinden `CAsyncSocket`türetilen bu sınıf, bir MFC [CArchive](../mfc/reference/carchive-class.md) nesnesi aracılığıyla yuva ile çalışmaya yönelik daha yüksek düzey bir soyutlama sağlar. Bir arşiv ile bir yuva kullanılması, MFC 'nin dosya serileştirme protokolünü kullanarak büyük ölçüde benzerdir. Bu, `CAsyncSocket` modelden daha kolay kullanılmasını sağlar. [Csockets](../mfc/reference/csocket-class.md) , Windows Sockets API 'lerini `CAsyncSocket` kapsülleyen birçok üye işlevi devralır; bu işlevlerden bazılarını kullanmanız ve yuva programlamayı genel olarak anlamanız gerekir. Ancak `CSocket` ham API veya sınıf `CAsyncSocket`kullanarak kendiniz yapmanız gereken iletişimin birçok yönünü yönetir. En önemlisi, `CSocket` zaman uyumlu `CArchive`işlemi için gerekli olan engelleme (Windows iletilerinin arka plan işlemesi ile) sağlar.

Ve [ `CSocket` nesnelerioluşturmavekullanmaWindows`CAsyncSocket` yuvaları 'nda açıklanmaktadır: Arşivleri](../mfc/windows-sockets-using-sockets-with-archives.md) ve[Windows yuvaları ile yuvaları kullanma: Sınıf CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)kullanma.

##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>Windows Sockets dll 'Leri

Microsoft Windows işletim sistemleri, Windows Sockets dinamik bağlantı kitaplıklarını (DLL) sağlar. Görsel C++ , uygun üst bilgi dosyalarını ve kitaplıklarını ve Windows Yuvaları belirtimini sağlar.

Windows Yuvaları hakkında daha fazla bilgi için bkz.

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

- [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: İşlem Dizisi](../mfc/windows-sockets-sequence-of-operations.md)

- [Windows Yuvaları: Arşivler Kullanan Yuvalara Örnek](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: CAsyncSocket Sınıfını Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Yuva Sınıflarından Türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Yuvaları: Yuva Bildirimleri](../mfc/windows-sockets-socket-notifications.md)

- [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)

- [Windows Yuvaları: Bayt Sıralama](../mfc/windows-sockets-byte-ordering.md)

- [Windows Yuvaları: Dizeleri Dönüştürme](../mfc/windows-sockets-converting-strings.md)

- [Windows Yuvaları: Bağlantı Noktaları ve Yuva Adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md)

## <a name="see-also"></a>Ayrıca bkz.

[Windows Yuvaları](../mfc/windows-sockets.md)
