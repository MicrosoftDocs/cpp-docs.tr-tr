---
description: "Daha fazla bilgi edinin: MFC 'de Windows Yuvaları"
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
ms.openlocfilehash: 9724613fe20abbd53b8f7de6a57723510d37b7f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263432"
---
# <a name="windows-sockets-in-mfc"></a>MFC'de Windows Yuvaları

> [!NOTE]
> MFC Windows Sockets 1 ' i destekler, ancak [Windows Sockets 2](/windows/win32/WinSock/windows-sockets-start-page-2)' i desteklemez. Windows Sockets 2 ilk olarak Windows 98 ile birlikte gelir ve Windows 2000 ' de yer alan sürümdür.

MFC, Windows Yuvaları olan ağ iletişim programlarını yazmak için iki model sağlar ve iki MFC sınıfına sahiptir. Bu makalede, bu modeller ve daha ayrıntılı olarak MFC Yuvaları desteği açıklanmaktadır. "Yuva" bir iletişim uç noktasıdır: uygulamanızın bir ağ üzerindeki diğer Windows Yuvaları uygulamalarıyla iletişim kurduğu nesne.

Yuva kavramının açıklaması da dahil olmak üzere Windows Yuvaları hakkında bilgi için bkz. [Windows Yuvaları: arka plan](../mfc/windows-sockets-background.md).

## <a name="sockets-programming-models"></a><a name="_core_sockets_programming_models"></a> Sockets programlama modelleri

İki MFC Windows Yuvaları programlama modeli aşağıdaki sınıflar tarafından desteklenir:

- `CAsyncSocket`

   Bu sınıf Windows Sockets API 'sini kapsüller. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) , ağ programlamayı bilen ve doğrudan yuvalar API 'sine programlama esnekliği isteyen ve ayrıca ağ olaylarının bildirilmesi için geri çağırma işlevlerinin rahatlığını tercih eden programcılar içindir. C++ ' ta kullanılmak üzere nesne odaklı biçimde paketleme yuvaları dışında, bu sınıfın sağladığı tek ek soyutlama, bazı yuvada ilgili Windows iletilerini geri çağırmaları dönüştürmektir. Daha fazla bilgi için bkz. [Windows Yuvaları: yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md).

- `CSocket`

   Öğesinden türetilen bu sınıf `CAsyncSocket` , BIR MFC [CArchive](../mfc/reference/carchive-class.md) nesnesi aracılığıyla yuva ile çalışmaya yönelik daha yüksek düzey bir soyutlama sağlar. Bir arşiv ile bir yuva kullanılması, MFC 'nin dosya serileştirme protokolünü kullanarak büyük ölçüde benzerdir. Bu, modelden daha kolay kullanılmasını sağlar `CAsyncSocket` . [Csockets](../mfc/reference/csocket-class.md) , `CAsyncSocket` Windows Sockets API 'lerini kapsülleyen birçok üye işlevi devralır; bu işlevlerden bazılarını kullanmanız ve yuva programlamayı genel olarak anlamanız gerekir. Ancak `CSocket` Ham API veya sınıf kullanarak kendiniz yapmanız gereken iletişimin birçok yönünü yönetir `CAsyncSocket` . En önemlisi, `CSocket` zaman uyumlu işlemi için gerekli olan engelleme (Windows iletilerinin arka plan işlemesi ile) sağlar `CArchive` .

Ve nesneleri oluşturma ve kullanma `CSocket` `CAsyncSocket` [Windows Yuvaları: arşivleri ve Windows yuvaları ile yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md) [: sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md).

## <a name="windows-sockets-dlls"></a><a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows Sockets dll 'Leri

Microsoft Windows işletim sistemleri, Windows Sockets dinamik bağlantı kitaplıklarını (DLL) sağlar. Visual C++, uygun üst bilgi dosyalarını ve kitaplıklarını ve Windows Yuvaları belirtimini sağlar.

Windows Yuvaları hakkında daha fazla bilgi için bkz.

- [Windows Yuvaları: akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: veri birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

- [Windows Yuvaları: Arşivlerle yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Işlem dizisi](../mfc/windows-sockets-sequence-of-operations.md)

- [Windows Yuvaları: arşivleri kullanan yuvalara örnek](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows Yuvaları: yuvalar, arşivleri ile nasıl çalışır?](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: yuva sınıflarından türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Yuvaları: yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md)

- [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)

- [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md)

- [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md)

- [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md)

## <a name="see-also"></a>Ayrıca bkz.

[Windows Yuvaları](../mfc/windows-sockets.md)
