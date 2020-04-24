---
title: CAsyncSocket Sınıfı
ms.date: 09/03/2019
f1_keywords:
- CAsyncSocket
- AFXSOCK/CAsyncSocket
- AFXSOCK/CAsyncSocket::CAsyncSocket
- AFXSOCK/CAsyncSocket::Accept
- AFXSOCK/CAsyncSocket::AsyncSelect
- AFXSOCK/CAsyncSocket::Attach
- AFXSOCK/CAsyncSocket::Bind
- AFXSOCK/CAsyncSocket::Close
- AFXSOCK/CAsyncSocket::Connect
- AFXSOCK/CAsyncSocket::Create
- AFXSOCK/CAsyncSocket::Detach
- AFXSOCK/CAsyncSocket::FromHandle
- AFXSOCK/CAsyncSocket::GetLastError
- AFXSOCK/CAsyncSocket::GetPeerName
- AFXSOCK/CAsyncSocket::GetPeerNameEx
- AFXSOCK/CAsyncSocket::GetSockName
- AFXSOCK/CAsyncSocket::GetSockNameEx
- AFXSOCK/CAsyncSocket::GetSockOpt
- AFXSOCK/CAsyncSocket::IOCtl
- AFXSOCK/CAsyncSocket::Listen
- AFXSOCK/CAsyncSocket::Receive
- AFXSOCK/CAsyncSocket::ReceiveFrom
- AFXSOCK/CAsyncSocket::ReceiveFromEx
- AFXSOCK/CAsyncSocket::Send
- AFXSOCK/CAsyncSocket::SendTo
- AFXSOCK/CAsyncSocket::SendToEx
- AFXSOCK/CAsyncSocket::SetSockOpt
- AFXSOCK/CAsyncSocket::ShutDown
- AFXSOCK/CASyncSocket::Socket
- AFXSOCK/CAsyncSocket::OnAccept
- AFXSOCK/CAsyncSocket::OnClose
- AFXSOCK/CAsyncSocket::OnConnect
- AFXSOCK/CAsyncSocket::OnOutOfBandData
- AFXSOCK/CAsyncSocket::OnReceive
- AFXSOCK/CAsyncSocket::OnSend
- AFXSOCK/CAsyncSocket::m_hSocket
helpviewer_keywords:
- CAsyncSocket [MFC], CAsyncSocket
- CAsyncSocket [MFC], Accept
- CAsyncSocket [MFC], AsyncSelect
- CAsyncSocket [MFC], Attach
- CAsyncSocket [MFC], Bind
- CAsyncSocket [MFC], Close
- CAsyncSocket [MFC], Connect
- CAsyncSocket [MFC], Create
- CAsyncSocket [MFC], Detach
- CAsyncSocket [MFC], FromHandle
- CAsyncSocket [MFC], GetLastError
- CAsyncSocket [MFC], GetPeerName
- CAsyncSocket [MFC], GetPeerNameEx
- CAsyncSocket [MFC], GetSockName
- CAsyncSocket [MFC], GetSockNameEx
- CAsyncSocket [MFC], GetSockOpt
- CAsyncSocket [MFC], IOCtl
- CAsyncSocket [MFC], Listen
- CAsyncSocket [MFC], Receive
- CAsyncSocket [MFC], ReceiveFrom
- CAsyncSocket [MFC], ReceiveFromEx
- CAsyncSocket [MFC], Send
- CAsyncSocket [MFC], SendTo
- CAsyncSocket [MFC], SendToEx
- CAsyncSocket [MFC], SetSockOpt
- CAsyncSocket [MFC], ShutDown
- CASyncSocket [MFC], Socket
- CAsyncSocket [MFC], OnAccept
- CAsyncSocket [MFC], OnClose
- CAsyncSocket [MFC], OnConnect
- CAsyncSocket [MFC], OnOutOfBandData
- CAsyncSocket [MFC], OnReceive
- CAsyncSocket [MFC], OnSend
- CAsyncSocket [MFC], m_hSocket
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
ms.openlocfilehash: e384be534bdbb355554c28383e9e214e9084f217
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753024"
---
# <a name="casyncsocket-class"></a>CAsyncSocket Sınıfı

Ağ iletişiminin bitiş noktası olan Bir Windows Soketini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CAsyncSocket : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|Bir `CAsyncSocket` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAsyncSocket::Kabul](#accept)|Soketteki bağlantıyı kabul eder.|
|[CAsyncSocket::AsyncSelect](#asyncselect)|Soket için olay bildirimi ister.|
|[CAsyncSocket::Ekle](#attach)|Bir `CAsyncSocket` nesneye soket tutamacı bağlar.|
|[CAsyncSocket::Bağlama](#bind)|Yerel bir adresi soketle ilişkilendirer.|
|[CAsyncSocket::Kapat](#close)|Soketi kapatır.|
|[CAsyncSocket::Bağlan](#connect)|Eş soketine bağlantı kurar.|
|[CAsyncSocket::Oluştur](#create)|Bir soket oluşturur.|
|[CAsyncSocket::Detach](#detach)|Bir soket tutamacını `CAsyncSocket` bir nesneden ayırır.|
|[CAsyncSocket::FromHandle](#fromhandle)|Soket tutamacı `CAsyncSocket` verilen bir işaretçiyi nesneye döndürür.|
|[CAsyncSocket::GetLastError](#getlasterror)|Başarısız olan son işlemin hata durumunu alır.|
|[CAsyncSocket::GetPeerName](#getpeername)|Soketin bağlı olduğu eş soketin adresini alır.|
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Soketin bağlı olduğu eş soketin adresini alır (IPv6 adreslerini işler).|
|[CAsyncSocket::GetSockName](#getsockname)|Bir soketiçin yerel adı alır.|
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Bir soketin yerel adını alır (IPv6 adreslerini işler).|
|[CAsyncSocket::GetSockOpt](#getsockopt)|Bir soket seçeneği alır.|
|[CAsyncSocket::IOCtl](#ioctl)|Soketin modunu kontrol eder.|
|[CAsyncSocket::Dinle](#listen)|Gelen bağlantı isteklerini dinlemek için bir soket kurar.|
|[CAsyncSocket::Receive](#receive)|Soketten veri alır.|
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Bir datagram alır ve kaynak adresi depolar.|
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Bir datagram alır ve kaynak adresi depolar (IPv6 adreslerini işler).|
|[CAsyncSocket::Gönder](#send)|Bağlı bir sokete veri gönderir.|
|[CAsyncSocket::SendTo](#sendto)|Belirli bir hedefe veri gönderir.|
|[CAsyncSocket::SendToEx](#sendtoex)|Belirli bir hedefe veri gönderir (IPv6 adreslerini işler).|
|[CAsyncSocket::SetSockOpt](#setsockopt)|Bir soket seçeneği ayarlar.|
|[CAsyncSocket::Kapatma](#shutdown)|Soketi `Send` devre dışı `Receive` bırakıp/veya aramaları.|
|[CASyncSocket::Soket](#socket)|Soket tutamacı ayırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAsyncSocket::OnAccept](#onaccept)|Bir dinleme soketini arayarak `Accept`bekleyen bağlantı isteklerini kabul edebileceğine dair bilgi vermez.|
|[CAsyncSocket::OnClose](#onclose)|Bir sokete bağlı soketin kapalı olduğunu belirtir.|
|[CAsyncSocket::OnConnect](#onconnect)|Bağlantı soketi, başarılı veya hatalı olsun, bağlantı denemesinin tamamlandığına dair bir hata dır.|
|[CAsyncSocket::OnoutofBandData](#onoutofbanddata)|Alıcı bir sokete, genellikle acil bir ileti olan sokette okunacak bant dışı veriler olduğunu belirtir.|
|[CAsyncSocket::OnReceive](#onreceive)|Bir dinleme soketini arayarak `Receive`alınacak veri olduğunu belirtir.|
|[CAsyncSocket::OnSend](#onsend)|Bir soketi arayarak `Send`veri gönderebileceğini belirtir.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAsyncSocket::operator =](#operator_eq)|Nesneye yeni bir `CAsyncSocket` değer atar.|
|[CAsyncSocket::operatör SOKETI](#operator_socket)|Nesnenin SOCKET tutamacını `CAsyncSocket` almak için bu işleci kullanın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAsyncSocket::m_hSocket](#m_hsocket)|Bu `CAsyncSocket` nesneye bağlı SOCKET tutamacını gösterir.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CAsyncSocket` Windows Soketleri MFC ile birlikte kullanmak isteyen programcılar için nesne yönelimli bir soyutlama sağlayarak Windows Soketi İşlevleri API'sini kapsüller.

Bu sınıf, ağ iletişimini anladığınız varsayımına dayanır. Unicode ve multibayt karakter kümesi (MBCS) dizeleri arasındaki engelleme, bayt sırası farkları ve dönüşümleri işlemeksizin sorumlusunuz. Bu sorunları sizin için yöneten daha kullanışlı bir arabirim istiyorsanız, [bkz.](../../mfc/reference/csocket-class.md)

Bir `CAsyncSocket` nesneyi kullanmak için, oluşturucusu çağırın ve kabul edilen `SOCKET`soketler dışında temel soket tutamacını (tür) oluşturmak için [Oluştur](#create) işlevini arayın. Bir sunucu soketi için [Dinle](#listen) üye işlevini arayın ve istemci soketi için [Connect](#connect) üye işlevini arayın. Sunucu soketi, bir bağlantı isteği aldıktan sonra [Kabul](#accept) işlevini aramalıdır. Soketler `CAsyncSocket` arasındaki iletişimi gerçekleştirmek için kalan işlevleri kullanın. Tamamlandıktan sonra, `CAsyncSocket` yığın üzerinde oluşturulduysa nesneyi yok edin; yıkıcı otomatik olarak [Kapat](#close) işlevini çağırır. SOCKET veri türü makalede [Windows Soketleri açıklanmıştır: Arka plan.](../../mfc/windows-sockets-background.md)

> [!NOTE]
> Statik olarak bağlı bir MFC uygulamasında ikincil iş parçacıklarında MFC `AfxSocketInit` soketleri kullanırken, soket kitaplıklarını başlatmak için soket kullanan her iş parçacığı çağırmanız gerekir. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığı denir.

Daha fazla bilgi için [Bkz. Windows Soketleri: CAsyncSocket sınıfı](../../mfc/windows-sockets-using-class-casyncsocket.md) ve ilgili makaleleri kullanma., windows [soketleri 2 API'sini.](/windows/win32/WinSock/windows-sockets-start-page-2)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsock.h

## <a name="casyncsocketaccept"></a><a name="accept"></a>CAsyncSocket::Kabul

Soketüzerindeki bağlantıyı kabul etmek için bu üye işlevini arayın.

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>Parametreler

*rConnectedSocket*<br/>
Bağlantı için kullanılabilen yeni bir soketi tanımlayan bir başvuru.

*lpSockAddr*<br/>
Ağda bilindiği gibi bağlantı soketi adresini alan bir [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısına işaretçi. *lpSockAddr* bağımsız değişkeninin tam biçimi, soket oluşturulduğunda kurulan adres ailesi tarafından belirlenir. *lpSockAddr* ve/veya *lpSockAddrLen* NULL'a eşitse, kabul edilen soketin uzak adresi hakkında hiçbir bilgi döndürülmez.

*lpSockAddrLen*<br/>
*Baytlarda lpSockAddr* adresinin uzunluğuna bir işaretçi. *LpSockAddrLen* bir değer-sonuç parametresi: başlangıçta *lpSockAddr*tarafından işaret alan miktarını içermelidir; dönüşte, iade edilen adresin gerçek uzunluğunu (baytlarda) içerecektir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEFAULT *LPSockAddrLen* bağımsız değişkeni çok küçüktür [(SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısının boyutundan daha az).

- WSAEINPROGRESS Bir engelleme Windows Soketleri arama devam ediyor.

- WSAEINVAL `Listen` kabul edilmeden önce çağrılmadı.

- WSAEMFILE Sıra kabul etmek için girişte boş ve kullanılabilir tanımlayıcısı yok.

- WSAENOBUFS Tampon alanı yok.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAEOPNOTSUPP Başvurulan soket, bağlantı yönelimli hizmeti destekleyen bir tür değildir.

- WSAEWOULDBLOCK Soket engellenmez olarak işaretlenir ve kabul edilecek bağlantı yoktur.

### <a name="remarks"></a>Açıklamalar

Bu yordam bekleyen bağlantılar kuyruğundaki ilk bağlantıyı ayıklar, bu soketle aynı özelliklere sahip yeni bir soket oluşturur ve *rConnectedSocket'e*bağlar. Sırada bekleyen bağlantı yoksa, `Accept` sıfır döndürür `GetLastError` ve bir hata döndürür. Kabul edilen soket *(rConnectedSocket)* daha fazla bağlantı kabul etmek için kullanılamaz. Orijinal soket açık ve dinleme kalır.

Bağımsız değişken *lpSockAddr,* iletişim katmanında bilindiği gibi bağlantı soketi adresiyle doldurulan bir sonuç parametresitir. `Accept`SOCK_STREAM gibi bağlantı tabanlı soket tipleri ile kullanılır.

## <a name="casyncsocketasyncselect"></a><a name="asyncselect"></a>CAsyncSocket::AsyncSelect

Bir soket için olay bildirimi istemek için bu üye işlevini arayın.

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parametreler

*Levent*<br/>
Uygulamanın ilgilendiği ağ olaylarının bir birleşimini belirten bir bitmaskesi.

- FD_READ Okumaya hazır olduğu bildirimini almak istiyorum.

- FD_WRITE Veriler okunabilmek için kullanılabilir olduğunda bildirim almak istiyorum.

- FD_OOB Bant dışı verilerin gelişi hakkında bildirim almak istiyorum.

- FD_ACCEPT Gelen bağlantıların bildirimini almak istiyorum.

- FD_CONNECT Bağlantı sonuçları bildirimi almak istiyorum.

- FD_CLOSE Bir yuva bir eş tarafından kapatıldığında bildirim almak istiyorum.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEINVAL Belirtilen parametrelerden birinin geçersiz olduğunu gösterir.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, soket için hangi MFC geri arama bildirim işlevlerinin çağrılacağını belirtmek için kullanılır. `AsyncSelect`bu soketi otomatik olarak engellememe moduna ayarlar. Daha fazla bilgi için [Windows Soketleri: Soket Bildirimleri](../../mfc/windows-sockets-socket-notifications.md)makalesine bakın.

## <a name="casyncsocketattach"></a><a name="attach"></a>CAsyncSocket::Ekle

*HSocket* tutamacını bir `CAsyncSocket` nesneye takmak için bu üye işlevi çağırın.

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parametreler

*hSoket*<br/>
Bir soketiçin bir tutamaç içerir.

*Levent*<br/>
Uygulamanın ilgilendiği ağ olaylarının bir birleşimini belirten bir bitmaskesi.

- FD_READ Okumaya hazır olduğu bildirimini almak istiyorum.

- FD_WRITE Veriler okunabilmek için kullanılabilir olduğunda bildirim almak istiyorum.

- FD_OOB Bant dışı verilerin gelişi hakkında bildirim almak istiyorum.

- FD_ACCEPT Gelen bağlantıların bildirimini almak istiyorum.

- FD_CONNECT Bağlantı sonuçları bildirimi almak istiyorum.

- FD_CLOSE Bir yuva bir eş tarafından kapatıldığında bildirim almak istiyorum.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfıra inme.

### <a name="remarks"></a>Açıklamalar

SOCKET tutamacı nesnenin [m_hSocket](#m_hsocket) veri üyesinde depolanır.

## <a name="casyncsocketbind"></a><a name="bind"></a>CAsyncSocket::Bağlama

Yerel bir adresi soketle ilişkilendirmek için bu üye işlevini arayın.

```
BOOL Bind(
    UINT nSocketPort,
    LPCTSTR lpszSocketAddress = NULL);

BOOL Bind (
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>Parametreler

*nSocketPort*<br/>
Soket uygulamasını tanımlayan bağlantı noktası.

*lpszSocketAddress*<br/>
Ağ adresi, "128.56.22.8" gibi noktalı bir sayı. Bu parametre için NULL dizesi geçmek, örneğin tüm ağ arabirimlerinde istemci etkinliğini dinlemesi `CAsyncSocket` gerektiğini gösterir.

*lpSockAddr*<br/>
Bu sokete atayacak adresi içeren bir [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısına işaretçi.

*nSockAddrLen*<br/>
*LpSockAddr'daki* adresin baytlarla uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki liste, döndürülebilecek hatalardan birkaçını kapsar. Tam liste için [Windows Soketleri Hata Kodları'na](/windows/win32/winsock/windows-sockets-error-codes-2)bakın.

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEADDRINUSE Belirtilen adres zaten kullanımda. [(SetSockOpt](#setsockopt)altında SO_REUSEADDR soket seçeneğine bakın.)

- WSAEFAULT *nSockAddrLen* bağımsız değişkeni çok küçüktür [(SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısının boyutundan daha az).

- WSAEINPROGRESS Bir engelleme Windows Soketleri arama devam ediyor.

- WSAEAFNOSUPPORT Belirtilen adres ailesi bu bağlantı noktası tarafından desteklenmez.

- WSAEINVAL Soket zaten bir adrese bağlı.

- WSAENOBUFS Yeterli arabellek, çok fazla bağlantı yok.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

### <a name="remarks"></a>Açıklamalar

Bu yordam, sonraki `Connect` veya aramadan önce bağlantısız `Listen` bir veri gramı veya akış soketi üzerinde kullanılır. Bağlantı isteklerini kabul etmeden önce, bir dinleme sunucusu soketi bir bağlantı noktası `Bind`numarası seçmeli ve arayarak Windows Soketleri'ni duyurmalıdır. `Bind`adı açıklanmayan bir sokete yerel bir ad atayarak soketin yerel ilişkilendirmesini (ana bilgisayar adresi/bağlantı noktası numarası) kurar.

## <a name="casyncsocketcasyncsocket"></a><a name="casyncsocket"></a>CAsyncSocket::CAsyncSocket

Boş bir soket nesnesi oluşturuyor.

```
CAsyncSocket();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi oluşturduktan sonra, SOCKET `Create` veri yapısını oluşturmak ve adresini bağlamak için üye işlevini aramanız gerekir. (Windows Soketleri iletişiminin sunucu tarafında, dinleme soketi `Accept` aramada kullanılacak bir soket `Create` oluşturduğunda, bu soketi aramazsınız.)

## <a name="casyncsocketclose"></a><a name="close"></a>CAsyncSocket::Kapat

Soketi kapatır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev soket tanımlayıcısını serbest bırakır, böylece wsaenotsock hatasıyla daha fazla başvuru başarısız olur. Bu, temel yuvaya yapılan son başvuruysa, ilişkili adlandırma bilgileri ve sıralanan veriler atılır. Soket nesnesinin yıkıcısı sizi `Close` çağırıyor.

Için `CAsyncSocket`, ama `CSocket`için değil , `Close` semantiği soket seçenekleri SO_LINGER etkilenir ve SO_DONTLINGER. Daha fazla bilgi için `GetSockOpt`üye işlevine bakın.

## <a name="casyncsocketconnect"></a><a name="connect"></a>CAsyncSocket::Bağlan

Bağlanmamış bir akışa veya datagram yuvasına bağlantı kurmak için bu üye işlevi arayın.

```
BOOL Connect(
    LPCTSTR lpszHostAddress,
    UINT nHostPort);

BOOL Connect(
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>Parametreler

*lpszHostAddress*<br/>
Bu nesnenin bağlı olduğu soketin ağ adresi: "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi noktalı bir sayı.

*nHostPort*<br/>
Soket uygulamasını tanımlayan bağlantı noktası.

*lpSockAddr*<br/>
Bağlı soketin adresini içeren bir [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısına işaretçi.

*nSockAddrLen*<br/>
*LpSockAddr'daki* adresin baytlarla uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Bu WSAEWOULDBLOCK bir hata kodu gösterir ve uygulamanız geçersiz geri aramaları kullanıyorsa, `OnConnect` bağlantı işlemi tamamlandığında uygulamanız bir ileti alır. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEADDRINUSE Belirtilen adres zaten kullanımda.

- WSAEINPROGRESS Bir engelleme Windows Soketleri arama devam ediyor.

- WSAEADDRNOTAVAIL Belirtilen adres yerel makineden kullanılamaz.

- WSAEAFNOSUPPORT Belirtilen ailedeki adresler bu soketle kullanılamaz.

- WSAECONNREFUSED Bağlanma girişimi reddedildi.

- WSAEDESTADDRREQ Bir hedef adresi gereklidir.

- WSAEFAULT *nSockAddrLen* bağımsız değişkeni yanlıştır.

- WSAEINVAL Geçersiz ana bilgisayar adresi.

- WSAEISCONN Soket zaten bağlı.

- WSAEMFILE Başka dosya tanımlayıcısı yok.

- WSAENETUNREACH Şu anda bu ana bilgisayardan ağa ulaşılamaz.

- WSAENOBUFS Tampon alanı yok. Soket bağlanamaz.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAETIMEDOUT Bağlantı kurmadan zaman lanmış bağlanmagirişimi.

- WSAEWOULDBLOCK Soket engellenmez olarak işaretlenir ve bağlantı hemen tamamlanamaz.

### <a name="remarks"></a>Açıklamalar

Soket bağlanmamışsa, sistem tarafından yerel ilişkilendirme için benzersiz değerler atanır ve soket bağlı olarak işaretlenir. Ad yapısının adres alanı sıfırların tümüyse, `Connect` sıfırı döndüreceğini unutmayın. Genişletilmiş hata bilgilerini almak için `GetLastError` üye işlevi arayın.

Akış soketleri (tip SOCK_STREAM) için, yabancı ana bilgisayara etkin bir bağlantı başlatılır. Soket araması başarıyla tamamlandığında, soket veri göndermeye/almaya hazırdır.

Bir datagram soketi (tür SOCK_DGRAM) için, sonraki `Send` ve `Receive` aramalarda kullanılacak varsayılan bir hedef ayarlanır.

## <a name="casyncsocketcreate"></a><a name="create"></a>CAsyncSocket::Oluştur

Windows `Create` soketi oluşturmak ve takmak için bir soket nesnesi oluşturduktan sonra üye işlevi arayın.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Parametreler

*nSocketPort*<br/>
Yuvayla birlikte kullanılmak üzere iyi bilinen bir bağlantı noktası veya Windows Soketlerinin bir bağlantı noktası seçmesini istiyorsanız 0.

*nSocketType*<br/>
SOCK_STREAM ya da SOCK_DGRAM.

*Levent*<br/>
Uygulamanın ilgilendiği ağ olaylarının bir birleşimini belirten bir bitmaskesi.

- FD_READ Okumaya hazır olduğu bildirimini almak istiyorum.

- FD_WRITE Yazmaya hazır olduğu bildirimini almak istiyorum.

- FD_OOB Bant dışı verilerin gelişi hakkında bildirim almak istiyorum.

- FD_ACCEPT Gelen bağlantıların bildirimini almak istiyorum.

- FD_CONNECT Tamamlanan bağlantıbildirimialmak istiyorum.

- FD_CLOSE Soket kapatma bildirimi almak istiyorum.

*lpszSockAdres*<br/>
Bağlı soketin ağ adresini içeren bir dize işaretçisi, "128.56.22.8" gibi noktalı bir sayı. Bu parametre için NULL dizesi geçmek, örneğin tüm ağ arabirimlerinde istemci etkinliğini dinlemesi `CAsyncSocket` gerektiğini gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEAFNOSUPPORT Belirtilen adres ailesi desteklenmez.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAEMFILE Başka dosya tanımlayıcısı yok.

- WSAENOBUFS Tampon alanı yok. Soket oluşturulamıyor.

- WSAEPROTONOSUPPORT Belirtilen bağlantı noktası desteklenmez.

- WSAEPROTOTYPE Belirtilen bağlantı noktası bu soket için yanlış türüdür.

- WSAESOCKTNOSUPPORT Belirtilen soket türü bu adres ailesinde desteklenmez.

### <a name="remarks"></a>Açıklamalar

`Create`[Soket'i](#socket) çağırır ve başarılı olursa, yuvayı belirtilen adrese bağlaması için [Bind'i](#bind) çağırır. Aşağıdaki soket türleri desteklenir:

- SOCK_STREAM Sıralı, güvenilir, tam çift yönlü, bağlantı tabanlı bayt akışları sağlar. Internet adresi ailesi için İletim Denetim Protokolü'nü (TCP) kullanır.

- SOCK_DGRAM Sabit (genellikle küçük) maksimum uzunlukta ki bağlantısız, güvenilmez paketleri destekleyen verigramlarını destekler. Internet adresi ailesi için Kullanıcı VeriGram Protokolü'nü (UDP) kullanır.

    > [!NOTE]
    >  `Accept` Üye işlev, parametresi olarak `CSocket` yeni, boş bir nesneye başvuru alır. Bu nesneyi aramadan `Accept`önce oluşturmanız gerekir. Bu soket nesnesi kapsam dışına çıkarsa, bağlantının kapandığını unutmayın. Bu yeni `Create` soket nesnesi için aramayın.

> [!IMPORTANT]
> `Create`iş parçacığı güvenli **değildir.**  Farklı iş parçacıkları tarafından aynı anda çağrılabileceği çok iş parçacığı ortamında çağırıyorsanız, her aramayı bir mutex veya başka bir eşitleme kilidiyle koruduğunuzdan emin olun.

Akış ve veri gram soketleri hakkında daha fazla bilgi için [Windows Soketleri: Arka Plan](../../mfc/windows-sockets-background.md) ve Windows [Soketleri: Bağlantı Noktaları ve Soket Adresleri](../../mfc/windows-sockets-ports-and-socket-addresses.md) ve Windows [Soketleri 2 API'ye](/windows/win32/WinSock/windows-sockets-start-page-2)bakın.

## <a name="casyncsocketdetach"></a><a name="detach"></a>CAsyncSocket::Detach

*m_hSocket* veri üyesindeki SOCKET tutamacını `CAsyncSocket` nesneden ayırmak ve *m_hSocket* NULL olarak ayarlamak için bu üye işlevini çağırın.

```
SOCKET Detach();
```

## <a name="casyncsocketfromhandle"></a><a name="fromhandle"></a>CAsyncSocket::FromHandle

Bir işaretçiyi `CAsyncSocket` nesneye döndürür.

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Parametreler

*hSoket*<br/>
Bir soketiçin bir tutamaç içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir `CAsyncSocket` nesneye işaretçi veya `CAsyncSocket` *hSocket'e*bağlı bir nesne yoksa NULL .

### <a name="remarks"></a>Açıklamalar

Bir SOCKET tutamacı verildiğinde, bir `CAsyncSocket` nesne tutamak için bağlı değilse, üye işlev NULL döndürür.

## <a name="casyncsocketgetlasterror"></a><a name="getlasterror"></a>CAsyncSocket::GetLastError

Başarısız olan son işlem için hata durumunu almak için bu üye işlevi arayın.

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>Dönüş Değeri

İade değeri, bu iş parçacığı tarafından gerçekleştirilen son Windows Soketleri API yordamı için hata kodunu gösterir.

### <a name="remarks"></a>Açıklamalar

Belirli bir üye işlev bir hata oluştuğunu `GetLastError` gösterdiğinde, uygun hata kodunu almak için çağrılmalıdır. Geçerli hata kodları listesi için tek tek üye işlev açıklamalarına bakın.

Hata kodları hakkında daha fazla bilgi için [Windows Soketleri 2 API'ye](/windows/win32/WinSock/windows-sockets-start-page-2)bakın.

## <a name="casyncsocketgetpeername"></a><a name="getpeername"></a>CAsyncSocket::GetPeerName

Bu soketin bağlı olduğu eş soketin adresini almak için bu üye işlevini arayın.

```
BOOL GetPeerName(
    CString& rPeerAddress,
    UINT& rPeerPort);

BOOL GetPeerName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>Parametreler

*rPeerAddress*<br/>
Noktalı `CString` bir numara IP adresi alan bir nesneye başvuru.

*rPeerPort*<br/>
Bağlantı noktası depolayan bir UINT'ye başvuru.

*lpSockAddr*<br/>
Eş soketinin adını alan [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısına işaretçi.

*lpSockAddrLen*<br/>
*Baytlarda lpSockAddr* adresinin uzunluğuna bir işaretçi. Dönüşte, *lpSockAddrLen* bağımsız *değişkeni lpSockAddr* bayt döndürülen gerçek boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEFAULT *LPSockAddrLen* bağımsız değişkeni yeterince büyük değildir.

- WSAEINPROGRESS Bir engelleme Windows Soketleri arama devam ediyor.

- WSAENOTCONN Soket bağlı değil.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

### <a name="remarks"></a>Açıklamalar

IPv6 adreslerini işlemek için [CAsyncSocket::GetPeerNameEx](#getpeernameex)adresini kullanın.

## <a name="casyncsocketgetpeernameex"></a><a name="getpeernameex"></a>CAsyncSocket::GetPeerNameEx

Bu soketin bağlı olduğu eş soketin adresini almak için bu üye işlevini arayın (IPv6 adreslerini işler).

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>Parametreler

*rPeerAddress*<br/>
Noktalı `CString` bir numara IP adresi alan bir nesneye başvuru.

*rPeerPort*<br/>
Bağlantı noktası depolayan bir UINT'ye başvuru.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEFAULT *LPSockAddrLen* bağımsız değişkeni yeterince büyük değildir.

- WSAEINPROGRESS Bir engelleme Windows Soketleri arama devam ediyor.

- WSAENOTCONN Soket bağlı değil.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

### <a name="remarks"></a>Açıklamalar

Bu işlev [CAsyncSocket ile aynıdır:GetPeerName,](#getpeername) iPv6 adreslerinin yanı sıra eski protokolleri de işlemesi dışında.

## <a name="casyncsocketgetsockname"></a><a name="getsockname"></a>CAsyncSocket::GetSockName

Bir soketin yerel adını almak için bu üye işlevini arayın.

```
BOOL GetSockName(
    CString& rSocketAddress,
    UINT& rSocketPort);

BOOL GetSockName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>Parametreler

*rSocketAddress*<br/>
Noktalı `CString` bir numara IP adresi alan bir nesneye başvuru.

*rSocketPort*<br/>
Bağlantı noktası depolayan bir UINT'ye başvuru.

*lpSockAddr*<br/>
Soketin adresini alan bir [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısına işaretçi.

*lpSockAddrLen*<br/>
*Baytlarda lpSockAddr* adresinin uzunluğuna bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEFAULT *LPSockAddrLen* bağımsız değişkeni yeterince büyük değildir.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAEINVAL Soketi ile `Bind`bir adrese bağlı olmamıştır.

### <a name="remarks"></a>Açıklamalar

Bu çağrı özellikle bir `Connect` `Bind` ilk yapmadan bir arama yapıldığında yararlıdır; bu çağrı, sistem tarafından ayarlanan yerel ilişkilendirmeyi belirleyebileceğiniz tek yolu sağlar.

IPv6 adreslerini işlemek için [CAsyncSocket kullanın::GetSockNameEx](#getsocknameex)

## <a name="casyncsocketgetsocknameex"></a><a name="getsocknameex"></a>CAsyncSocket::GetSockNameEx

Bir soketin yerel adını almak için bu üye işlevini arayın (IPv6 adreslerini işler).

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>Parametreler

*rSocketAddress*<br/>
Noktalı `CString` bir numara IP adresi alan bir nesneye başvuru.

*rSocketPort*<br/>
Bağlantı noktası depolayan bir UINT'ye başvuru.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEFAULT *LPSockAddrLen* bağımsız değişkeni yeterince büyük değildir.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAEINVAL Soketi ile `Bind`bir adrese bağlı olmamıştır.

### <a name="remarks"></a>Açıklamalar

Bu çağrı [CAsyncSocket ile aynıdır::GetSockName,](#getsockname) IPv6 adreslerinin yanı sıra eski protokolleri de işlemesi dışında.

Bu çağrı özellikle bir `Connect` `Bind` ilk yapmadan bir arama yapıldığında yararlıdır; bu çağrı, sistem tarafından ayarlanan yerel ilişkilendirmeyi belirleyebileceğiniz tek yolu sağlar.

## <a name="casyncsocketgetsockopt"></a><a name="getsockopt"></a>CAsyncSocket::GetSockOpt

Bir soket seçeneği almak için bu üye işlevi arayın.

```
BOOL GetSockOpt(
    int nOptionName,
    void* lpOptionValue,
    int* lpOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Parametreler

*nOptionName*<br/>
Değerin alınabilmek için soket seçeneği.

*lpOptionValue*<br/>
İstenen seçeneğin değerinin döndürülene ne olacak arabellek için bir işaretçi. Seçili seçenekle ilişkili değer *arabellek lpOptionValue*döndürülür. *lpOptionLen* tarafından işaret edilen tamsayı aslında baytlarda bu arabellek boyutunu içermelidir; ve iade de döndürülen değerin boyutuna ayarlanır. SO_LINGER için, bu bir `LINGER` yapının boyutu olacak; tüm diğer seçenekler için bir BOOL veya **int**boyutu olacak , seçeneğine bağlı olarak. Seçenekler in listesine ve boyutlarına açıklamalar bölümünde bakın.

*lpOptionLen*<br/>
*Baytlarda lpOptionValue* arabelleğinin boyutuna işaretçi.

*nSeviye*<br/>
Seçeneğin tanımlandığı düzey; desteklenen tek düzey SOL_SOCKET ve IPPROTO_TCP.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Bir seçenek hiçbir zaman `SetSockOpt`ayarlıdeğilse, seçenek için varsayılan değeri `GetSockOpt` döndürür. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEFAULT *LPOptionLen* bağımsız değişkeni geçersizdi.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAENOPROTOOPT Seçeneği bilinmiyor veya desteklenmis. Özellikle, SO_BROADCAST tip SOCK_STREAM soketlerinde desteklenmezken, SOCK_DGRAM SOCK_DGRAM soketlerinde SO_ACCEPTCONN, SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER ve SO_OOBINLINE desteklenmez.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

### <a name="remarks"></a>Açıklamalar

`GetSockOpt`herhangi bir durumda, herhangi bir türde bir soket ile ilişkili bir soket seçeneği için geçerli değeri alır ve *lpOptionValue*sonucu depolar. Seçenekler, paketlerin yönlendirmesi, bant dışı veri aktarımı gibi soket işlemlerini etkiler.

Aşağıdaki seçenekler `GetSockOpt`için desteklenir. Tür, *lpOptionValue*tarafından adreslenen veri türünü tanımlar. TCP_NODELAY seçeneği düzey IPPROTO_TCP kullanır; diğer tüm seçenekler SOL_SOCKET düzeyi kullanır.

|Değer|Tür|Anlamı|
|-----------|----------|-------------|
|SO_ACCEPTCONN|Bool|Soket dinliyor.|
|SO_BROADCAST|Bool|Soket, yayın iletilerinin iletimi için yapılandırılmıştır.|
|SO_DEBUG|Bool|Hata ayıklama etkinleştirildi.|
|SO_DONTLINGER|Bool|Doğruysa, SO_LINGER seçeneği devre dışı bırakılır.|
|SO_DONTROUTE|Bool|Yönlendirme devre dışı bırakılır.|
|SO_ERROR|**int**|Hata durumunu alın ve temizleyin.|
|SO_KEEPALIVE|Bool|Keep-alives gönderiliyor.|
|SO_LINGER|`struct LINGER`|Geçerli oyalanma seçeneklerini verir.|
|SO_OOBINLINE|Bool|Bant dışı veriler normal veri akışında alınıyor.|
|SO_RCVBUF|int|Alır için arabellek boyutu.|
|SO_REUSEADDR|Bool|Soket zaten kullanılmakta olan bir adrese bağlanabilir.|
|SO_SNDBUF|**int**|Göndermeler için tampon boyutu.|
|SO_TYPE|**int**|Soketin türü (örneğin, SOCK_STREAM).|
|TCP_NODELAY|Bool|Birleştirme göndermek için Nagle algoritmasını devre dışı kılabilir.|

Berkeley Yazılım Dağıtımı (BSD) seçenekleri `GetSockOpt` için desteklenmeyen şunlardır:

|Değer|Tür|Anlamı|
|-----------|----------|-------------|
|SO_RCVLOWAT|**int**|Düşük su işareti alın.|
|SO_RCVTIMEO|**int**|Zaman alanın.|
|SO_SNDLOWAT|**int**|Düşük su işareti gönderin.|
|SO_SNDTIMEO|**int**|Zaman aralarını gönderin.|
|IP_OPTIONS||IP üstbilgisinde seçenekler alın.|
|TCP_MAXSEG|**int**|TCP maksimum segment boyutunu alın.|

Desteklenmeyen bir seçenekle arama yapmak, `GetSockOpt` WSAENOPROTOOPT'in `GetLastError`hata kodunun .'den döndürülmesi ile sonuçlanır.

## <a name="casyncsocketioctl"></a><a name="ioctl"></a>CAsyncSocket::IOCtl

Bir soketin modunu denetlemek için bu üye işlevi arayın.

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>Parametreler

*lKomut*<br/>
Soket üzerinde gerçekleştirmek için komut.

*lpArgument*<br/>
*lCommand*için bir parametre için bir işaretçi .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEINVAL *lCommand* geçerli bir komut değildir veya *lpArgument* *lCommand*için kabul edilebilir bir parametre değildir veya komut verilen soket türü için geçerli değildir.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

### <a name="remarks"></a>Açıklamalar

Bu yordam herhangi bir durumda herhangi bir soket üzerinde kullanılabilir. Protokol ve iletişim alt sisteminden bağımsız olarak soketle ilişkili çalışma parametrelerini almak veya almak için kullanılır. Aşağıdaki komutlar desteklenir:

- FIONBIO Soketüzerindeki engellemesiz modu etkinleştirin veya devre dışı kaldırın. Engelleme modu etkinolacaksa `DWORD`sıfır olmayan bir , *bir lpArgument* parametresi puanve devre dışı bırakılacaksa sıfır. Bir `AsyncSelect` soket üzerinde verilmişse, soketi engelleme moduna geri ayarlamak için kullanılan `IOCtl` herhangi bir girişim WSAEINVAL ile başarısız olur. Soketi engelleme moduna geri ayarlamak ve WSAEINVAL hatasını önlemek `AsyncSelect` için, `AsyncSelect` bir uygulamanın önce 0'a `IOCtl`eşit *lEvent* parametresi ile arayarak devre dışı bırakması gerekir, sonra .

- FIONREAD Bu soketten gelen bir `Receive` çağrıyla okunabilecek maksimum bayt sayısını belirleyin. *LPArgument* parametresi sonucu `DWORD` depolayan `IOCtl` bir noktayı işaret ediyor. Bu soket SOCK_STREAM türündeyse, FIONREAD tek `Receive`bir işlemde okunabilen toplam veri miktarını döndürür; bu normalde yuvada sıralanmış toplam veri miktarıyla aynıdır. Bu soket tip SOCK_DGRAM ise, FIONREAD soketüzerinde sıralanmış ilk veri gramının boyutunu döndürür.

- SIOCATMARK Tüm bant dışı verilerin okunup okunmadığını belirleyin. Bu, yalnızca bant dışı verilerin (SO_OOBINLINE) satır içi alımı için yapılandırılan tip SOCK_STREAM bir soket için geçerlidir. Bant dışı veri okunmayı beklemiyorsa, işlem sıfırsız döndürür. Aksi takdirde 0 döndürür ve yuvada bir sonraki `Receive` veya `ReceiveFrom` gerçekleştirilen "işareti" öncesinde ki verilerin bir kısmını veya tamamını alır; uygulama, herhangi bir verinin kalıp kalmadığı konusunda SIOCATMARK işlemini kullanmalıdır. "Acil" (bant dışı) verilerden önce normal bir veri varsa, sırayla alınır. (Bir `Receive` veya `ReceiveFrom` asla bant dışı ve normal verileri aynı çağrıda karıştırmayacağına dikkat edin.) *LPArgument* parametresi sonucu `DWORD` depolayan `IOCtl` bir noktayı işaret ediyor.

Bu işlev, Berkeley `ioctl()` soketlerinde kullanılan bir alt kümesidir. Özellikle, FIOASYNC'e eşdeğer bir komut yoktur, ancak SIOCATMARK desteklenen tek soket seviyesi komutudur.

## <a name="casyncsocketlisten"></a><a name="listen"></a>CAsyncSocket::Dinle

Gelen bağlantı isteklerini dinlemek için bu üye işlevini arayın.

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>Parametreler

*nConnectionBacklog*<br/>
Bekleyen bağlantı sırasının büyüyebileceği maksimum uzunluk. Geçerli aralık 1 ile 5 arasındadır.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEADDRINUSE Kullanımdaki bir adresi dinlemeye çalışılmıştır.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAEINVAL Soket ile `Bind` bağlı değil veya zaten bağlı.

- WSAEISCONN Soket zaten bağlı.

- WSAEMFILE Başka dosya tanımlayıcısı yok.

- WSAENOBUFS Tampon alanı yok.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAEOPNOTSUPP Başvurulan `Listen` soket, işlemi destekleyen bir tür değildir.

### <a name="remarks"></a>Açıklamalar

Bağlantıları kabul etmek için, soket `Create`ilk olarak , gelen bağlantılar için `Listen`bir biriktirme listesi ile oluşturulur `Accept`, ve daha sonra bağlantıları ile kabul edilir . `Listen`yalnızca bağlantıları destekleyen soketler, yani tip SOCK_STREAM için geçerlidir. Bu soket, gelen bağlantıların kabul edildiği ve işlem tarafından kabul edilinceye kadar sıraya alındığı "pasif" moduna alınır.

Bu işlev genellikle sunucular (veya bağlantıları kabul etmek isteyen herhangi bir uygulama) tarafından kullanılır ve aynı anda birden fazla bağlantı isteği olabilir: bir bağlantı isteği sıra dolu ysa, istemci WSAECONNREFUSED bir göstergesi ile bir hata alır.

`Listen`kullanılabilir bağlantı noktaları (tanımlayıcılar) olmadığında rasyonel olarak çalışmaya devam etmeye çalışır. Sıra boşalana kadar bağlantıları kabul eder. Bağlantı noktaları kullanılabilir hale gelirse, `Listen` sırayı daha sonra geçerli veya en son "biriktirme listesine" çağırır veya `Accept` yeniden doldurabilir ve gelen bağlantıları dinlemeye devam eder.

## <a name="casyncsocketm_hsocket"></a><a name="m_hsocket"></a>CAsyncSocket::m_hSocket

Bu `CAsyncSocket` nesne tarafından kapsüllenmiş soket için SOKET tutamacını içerir.

```
SOCKET m_hSocket;
```

## <a name="casyncsocketonaccept"></a><a name="onaccept"></a>CAsyncSocket::OnAccept

Bir dinleme soketi nin üye [işlevini kabul](#accept) ederek bekleyen bağlantı isteklerini kabul edebileceğini bildirmek için çerçeve tarafından çağrılır.

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir soketteki en son hata. Aşağıdaki hata kodları `OnAccept` üye işlev için geçerlidir:

- **0** İşlev başarıyla yürütülür.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. Windows Soketleri: Soket Bildirimleri.](../../mfc/windows-sockets-socket-notifications.md)

## <a name="casyncsocketonclose"></a><a name="onclose"></a>CAsyncSocket::OnClose

Bağlı soketin işlemi tarafından kapatılarak kapatılır bu sokete bildirmek için çerçeve tarafından çağrılır.

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir soketteki en son hata. `OnClose` Aşağıdaki hata kodları üye işlevi için geçerlidir:

- **0** İşlev başarıyla yürütülür.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAECONNRESET Bağlantı uzak tarafta sıfırlandı.

- WSAECONNABORTED Zaman arızası veya başka bir arıza nedeniyle bağlantı iptal edildi.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. Windows Soketleri: Soket Bildirimleri.](../../mfc/windows-sockets-socket-notifications.md)

## <a name="casyncsocketonconnect"></a><a name="onconnect"></a>CAsyncSocket::OnConnect

Bu bağlantı soketi nin başarılı veya hatalı olsun, bağlantı denemesinin tamamlandığını bildirmek için çerçeve tarafından çağrılır.

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir soketteki en son hata. `OnConnect` Aşağıdaki hata kodları üye işlevi için geçerlidir:

- **0** İşlev başarıyla yürütülür.

- WSAEADDRINUSE Belirtilen adres zaten kullanımda.

- WSAEADDRNOTAVAIL Belirtilen adres yerel makineden kullanılamaz.

- WSAEAFNOSUPPORT Belirtilen ailedeki adresler bu soketle kullanılamaz.

- WSAECONNREDDEDBAĞLANMA GIRIŞIMI zorla reddedildi.

- WSAEDESTADDRREQ Bir hedef adresi gereklidir.

- WSAEFAULT *LPSockAddrLen* bağımsız değişkeni yanlıştır.

- WSAEINVAL Soket zaten bir adrese bağlı.

- WSAEISCONN Soket zaten bağlı.

- WSAEMFILE Başka dosya tanımlayıcısı yok.

- WSAENETUNREACH Şu anda bu ana bilgisayardan ağa ulaşılamaz.

- WSAENOBUFS Tampon alanı yok. Soket bağlanamaz.

- WSAENOTCONN Soket bağlı değil.

- WSAENOTSOCK Tanımlayıcı bir dosyadır, soket değil.

- WSAETIMEDOUT Bağlantı kurmadan zaman lanmış bağlanma girişimi.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> [CSocket'de](../../mfc/reference/csocket-class.md) `OnConnect` bildirim işlevi hiçbir zaman çağrılmaz. Bağlantılar için, bağlantı `Connect`tamamlandığında (başarılı veya hatalı) döndürülecek olan , yalnızca aramanız yeterlidir. Bağlantı bildirimlerinin nasıl işlenir, Bir MFC uygulama ayrıntısI.

Daha fazla bilgi için [Bkz. Windows Soketleri: Soket Bildirimleri.](../../mfc/windows-sockets-socket-notifications.md)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

## <a name="casyncsocketonoutofbanddata"></a><a name="onoutofbanddata"></a>CAsyncSocket::OnoutofBandData

Gönderen soketin gönderilecek bant dışı verisi olduğunu bildiren çerçeve tarafından çağrılır.

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir soketteki en son hata. `OnOutOfBandData` Aşağıdaki hata kodları üye işlevi için geçerlidir:

- **0** İşlev başarıyla yürütülür.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

### <a name="remarks"></a>Açıklamalar

Bant dışı veriler, SOCK_STREAM türübağlı soketlerin her çiftiyle ilişkili mantıksal olarak bağımsız bir kanaldır. Kanal genellikle acil veri göndermek için kullanılır.

MFC bant dışı verileri destekler, ancak `CAsyncSocket` sınıf kullanıcılarının verileri kullanmaları önerilmez. Daha kolay yolu, bu tür verileri aktarmak için ikinci bir soket oluşturmaktır. Bant dışı veriler hakkında daha fazla bilgi için [Windows Soketleri: Soket Bildirimleri](../../mfc/windows-sockets-socket-notifications.md)bölümüne bakın.

## <a name="casyncsocketonreceive"></a><a name="onreceive"></a>CAsyncSocket::OnReceive

`Receive` Bu sokete üye işlevi çağırArak alınabilecek arabellekte veri olduğunu bildirmek için çerçeve tarafından çağrılır.

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir soketteki en son hata. `OnReceive` Aşağıdaki hata kodları üye işlevi için geçerlidir:

- **0** İşlev başarıyla yürütülür.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. Windows Soketleri: Soket Bildirimleri.](../../mfc/windows-sockets-socket-notifications.md)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

## <a name="casyncsocketonsend"></a><a name="onsend"></a>CAsyncSocket::OnSend

`Send` Artık üye işlevi arayarak veri gönderebileceğini sokete bildirmek için çerçeve tarafından çağrılır.

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir soketteki en son hata. `OnSend` Aşağıdaki hata kodları üye işlevi için geçerlidir:

- **0** İşlev başarıyla yürütülür.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. Windows Soketleri: Soket Bildirimleri.](../../mfc/windows-sockets-socket-notifications.md)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

## <a name="casyncsocketoperator-"></a><a name="operator_eq"></a>CAsyncSocket::operator =

Nesneye yeni bir `CAsyncSocket` değer atar.

```cpp
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Varolan `CAsyncSocket` bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Varolan `CAsyncSocket` bir nesneyi başka `CAsyncSocket` bir nesneye kopyalamak için bu işlevi çağırın.

## <a name="casyncsocketoperator-socket"></a><a name="operator_socket"></a>CAsyncSocket::operatör SOKETI

Nesnenin SOCKET tutamacını `CAsyncSocket` almak için bu işleci kullanın.

```
operator SOCKET() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, SOCKET nesnesinin tutamacı; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Windows API'lerini doğrudan aramak için tutamacı kullanabilirsiniz.

## <a name="casyncsocketreceive"></a><a name="receive"></a>CAsyncSocket::Receive

Bir soketten veri almak için bu üye işlevini arayın.

```
virtual int Receive(
    void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Gelen veriler için bir arabellek.

*nBufLen*<br/>
*Baytlarda lpBuf* uzunluğu.

*Nflags*<br/>
Aramanın nasıl yapıldığını belirtir. Bu işlevin anlamtileri soket seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, aşağıdaki değerlerden herhangi birinin C++ **VEYA** işleci ile birleştirilmesiyle oluşturulur:

- gelen verilere MSG_PEEK. Veriler arabelleğe kopyalanır, ancak giriş kuyruğundan kaldırılmaz.

- MSG_OOB İşlem bant dışı verileri.

### <a name="return-value"></a>Dönüş Değeri

Hata oluşmazsa, `Receive` alınan bayt sayısını döndürür. Bağlantı kapatıldıysa, 0 döndürür. Aksi takdirde, SOCKET_ERROR değeri döndürülür ve belirli bir hata kodu [GetLastError](#getlasterror)çağırArak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAENOTCONN Soket bağlı değil.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAEOPNOTSUPP MSG_OOB belirtilmiş, ancak soket tip SOCK_STREAM değildir.

- WSAESHUTDOWN Soket kapatıldı; *nHow* 0 veya `Receive` 2 olarak `ShutDown` ayarlandıktan sonra bir soketi aramak mümkün değildir.

- WSAEWOULDBLOCK Soket nonblocking olarak `Receive` işaretlenir ve işlem engellenir.

- WSAEMSGSIZE Veri gramı belirtilen arabelleğe sığmayacak kadar büyüktü ve kesildi.

- WSAEINVAL Soketi ile `Bind`bağlı olmamıştır.

- WSAECONNABORTED Sanal devre zaman aşımı veya diğer arıza nedeniyle iptal edildi.

- WSAECONNRESET Sanal devre uzak tarafta sıfırlandı.

### <a name="remarks"></a>Açıklamalar

Bu işlev bağlı akış veya datagram soketleri için kullanılır ve gelen verileri okumak için kullanılır.

Tip SOCK_STREAM soketleri için, şu anda sağlanan arabellek boyutuna kadar kullanılabilir kadar çok bilgi döndürülür. Soket, bant dışı verilerin (soket seçeneği SO_OOBINLINE) satır içi alımı için yapılandırıldıysa ve bant dışı veriler okunmamışsa, yalnızca bant dışı veriler döndürülür. Uygulama, bant `IOCtlSIOCATMARK` dışı verilerin okunmaya kalıp kalmadığı konusunda seçenek veya [OnOutOfBandData](#onoutofbanddata) kullanabilir.

Datagram soketleri için, veriler ilk sıralı veri gramından sağlanan arabellek boyutuna kadar ayıklanır. Veri gramı sağlanan arabellekten daha büyükse, arabellek veri gramının ilk bölümüyle doldurulur, `Receive` fazla veri kaybolur ve hata kodu WSAEMSGSIZE'a ayarlanmış SOCKET_ERROR değerini döndürür. Sokette gelen veri yoksa, wsaewouldblock için ayarlanan hata koduyla SOCKET_ERROR değeri döndürülür. [OnReceive](#onreceive) geri çağırma işlevi, daha fazla verinin ne zaman varabileceğini belirlemek için kullanılabilir.

Soket tip SOCK_STREAM ve uzak tarafı bağlantıyı zarif bir şekilde `Receive` kapatmışsa, alınan 0 bayt ile bir anda tamamlanır. Bağlantı sıfırlandıysa, WSAECONNRESET `Receive` hatası yla başarısız olur.

`Receive`[casyncSocket her](#onreceive) zaman için sadece bir kez çağrılmalıdır::OnReceive denir.

### <a name="example"></a>Örnek

  [CAsyncSocket örneğine bakın::OnReceive](#onreceive).

## <a name="casyncsocketreceivefrom"></a><a name="receivefrom"></a>CAsyncSocket::ReceiveFrom

Bir datagram almak ve kaynak adresi [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısında veya *rSocketAddress'te*depolamak için bu üye işlevini arayın.

```
int ReceiveFrom(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);

int ReceiveFrom(
    void* lpBuf,
    int nBufLen,
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Gelen veriler için bir arabellek.

*nBufLen*<br/>
*Baytlarda lpBuf* uzunluğu.

*rSocketAddress*<br/>
Noktalı `CString` bir numara IP adresi alan bir nesneye başvuru.

*rSocketPort*<br/>
Bağlantı noktası depolayan bir UINT'ye başvuru.

*lpSockAddr*<br/>
Döndükten sonra kaynak adresi tutan bir [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısına işaretçi.

*lpSockAddrLen*<br/>
*LpSockAddr* bytes kaynak adresinin uzunluğu için bir işaretçi.

*Nflags*<br/>
Aramanın nasıl yapıldığını belirtir. Bu işlevin anlamtileri soket seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, aşağıdaki değerlerden herhangi birinin C++ **VEYA** işleci ile birleştirilmesiyle oluşturulur:

- gelen verilere MSG_PEEK. Veriler arabelleğe kopyalanır, ancak giriş kuyruğundan kaldırılmaz.

- MSG_OOB İşlem bant dışı verileri.

### <a name="return-value"></a>Dönüş Değeri

Hata oluşmazsa, `ReceiveFrom` alınan bayt sayısını döndürür. Bağlantı kapatıldıysa, 0 döndürür. Aksi takdirde, SOCKET_ERROR değeri döndürülür ve belirli bir hata `GetLastError`kodu arayarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEFAULT *LPSockAddrLen* bağımsız değişkengeçersiz oldu: *lpSockAddr* tampon akran adresi karşılamak için çok küçüktü.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAEINVAL Soketi ile `Bind`bağlı olmamıştır.

- WSAENOTCONN Soket bağlı değildir (yalnızca SOCK_STREAM).

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAEOPNOTSUPP MSG_OOB belirtilmiş, ancak soket tip SOCK_STREAM değildir.

- WSAESHUTDOWN Soket kapatıldı; *nHow* 0 veya `ReceiveFrom` 2 olarak `ShutDown` ayarlandıktan sonra bir soketi aramak mümkün değildir.

- WSAEWOULDBLOCK Soket nonblocking olarak `ReceiveFrom` işaretlenir ve işlem engellenir.

- WSAEMSGSIZE Veri gramı belirtilen arabelleğe sığmayacak kadar büyüktü ve kesildi.

- WSAECONNABORTED Sanal devre zaman aşımı veya diğer arıza nedeniyle iptal edildi.

- WSAECONNRESET Sanal devre uzak tarafta sıfırlandı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, gelen verileri (büyük olasılıkla bağlı) bir soketüzerinde okumak ve verilerin gönderildiği adresi yakalamak için kullanılır.

IPv6 adreslerini işlemek için [CAsyncSocket:ReceiveFromEx'i](#receivefromex)kullanın.

Tip SOCK_STREAM soketleri için, şu anda sağlanan arabellek boyutuna kadar kullanılabilir kadar çok bilgi döndürülür. Soket, bant dışı verilerin (soket seçeneği SO_OOBINLINE) satır içi alımı için yapılandırıldıysa ve bant dışı veriler okunmamışsa, yalnızca bant dışı veriler döndürülür. Uygulama `IOCtlSIOCATMARK` seçeneği kullanabilir veya `OnOutOfBandData` daha fazla bant dışı verinin okunup okunmadığını belirleyebilir. *lpSockAddr* ve *lpSockAddrLen* parametreleri SOCK_STREAM soketleri için göz ardı edilir.

Datagram soketleri için, veriler ilk sıralı veri gramından sağlanan arabellek boyutuna kadar ayıklanır. Verigramı sağlanan arabellekten daha büyükse, arabellek iletinin ilk bölümüyle doldurulur, fazla `ReceiveFrom` veri kaybolur ve hata kodu WSAEMSGSIZE'a ayarlanmış SOCKET_ERROR değerini döndürür.

*lpSockAddr* sıfırsız sayılsa ve soket tip SOCK_DGRAM ise, verileri gönderen soketin ağ adresi ilgili [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısına kopyalanır. *lpSockAddrLen* tarafından işaret edilen değer bu yapının boyutuna başharflenir ve burada depolanan adresin gerçek boyutunu belirtmek üzere iade üzerine değiştirilir. Sokette gelen veri yoksa, soket engellenmedikçe `ReceiveFrom` arama veri gelmesini bekler. Bu durumda, SOCKET_ERROR değeri WSAEWOULDBLOCK için ayarlanan hata kodu ile döndürülür. Geri `OnReceive` arama, daha fazla verinin ne zaman varabileceğini belirlemek için kullanılabilir.

Soket tip SOCK_STREAM ve uzak tarafı bağlantıyı zarif bir şekilde `ReceiveFrom` kapatmışsa, alınan 0 bayt ile bir anda tamamlanır.

## <a name="casyncsocketreceivefromex"></a><a name="receivefromex"></a>CAsyncSocket::ReceiveFromEx

Bir datagram almak ve kaynak adresi [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısında veya *rSocketAddress'te* (IPv6 adreslerini işler) depolamak için bu üye işlevini arayın.

```
int ReceiveFromEx(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Gelen veriler için bir arabellek.

*nBufLen*<br/>
*Baytlarda lpBuf* uzunluğu.

*rSocketAddress*<br/>
Noktalı `CString` bir numara IP adresi alan bir nesneye başvuru.

*rSocketPort*<br/>
Bağlantı noktası depolayan bir UINT'ye başvuru.

*Nflags*<br/>
Aramanın nasıl yapıldığını belirtir. Bu işlevin anlamtileri soket seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, aşağıdaki değerlerden herhangi birinin C++ **VEYA** işleci ile birleştirilmesiyle oluşturulur:

- gelen verilere MSG_PEEK. Veriler arabelleğe kopyalanır, ancak giriş kuyruğundan kaldırılmaz.

- MSG_OOB İşlem bant dışı verileri.

### <a name="return-value"></a>Dönüş Değeri

Hata oluşmazsa, `ReceiveFromEx` alınan bayt sayısını döndürür. Bağlantı kapatıldıysa, 0 döndürür. Aksi takdirde, SOCKET_ERROR değeri döndürülür ve belirli bir hata `GetLastError`kodu arayarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEFAULT *LPSockAddrLen* bağımsız değişkengeçersiz oldu: *lpSockAddr* tampon akran adresi karşılamak için çok küçüktü.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAEINVAL Soketi ile `Bind`bağlı olmamıştır.

- WSAENOTCONN Soket bağlı değildir (yalnızca SOCK_STREAM).

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAEOPNOTSUPP MSG_OOB belirtilmiş, ancak soket tip SOCK_STREAM değildir.

- WSAESHUTDOWN Soket kapatıldı; *nHow* 0 veya `ReceiveFromEx` 2 olarak `ShutDown` ayarlandıktan sonra bir soketi aramak mümkün değildir.

- WSAEWOULDBLOCK Soket nonblocking olarak `ReceiveFromEx` işaretlenir ve işlem engellenir.

- WSAEMSGSIZE Veri gramı belirtilen arabelleğe sığmayacak kadar büyüktü ve kesildi.

- WSAECONNABORTED Sanal devre zaman aşımı veya diğer arıza nedeniyle iptal edildi.

- WSAECONNRESET Sanal devre uzak tarafta sıfırlandı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, gelen verileri (büyük olasılıkla bağlı) bir soketüzerinde okumak ve verilerin gönderildiği adresi yakalamak için kullanılır.

Bu işlev [CAsyncSocket ile aynıdır::ReceiveFrom,](#receivefrom) IPv6 adreslerinin yanı sıra eski protokolleri de işlettiği dışında.

Tip SOCK_STREAM soketleri için, şu anda sağlanan arabellek boyutuna kadar kullanılabilir kadar çok bilgi döndürülür. Soket, bant dışı verilerin (soket seçeneği SO_OOBINLINE) satır içi alımı için yapılandırıldıysa ve bant dışı veriler okunmamışsa, yalnızca bant dışı veriler döndürülür. Uygulama `IOCtlSIOCATMARK` seçeneği kullanabilir veya `OnOutOfBandData` daha fazla bant dışı verinin okunup okunmadığını belirleyebilir. *lpSockAddr* ve *lpSockAddrLen* parametreleri SOCK_STREAM soketleri için göz ardı edilir.

Datagram soketleri için, veriler ilk sıralı veri gramından sağlanan arabellek boyutuna kadar ayıklanır. Verigramı sağlanan arabellekten daha büyükse, arabellek iletinin ilk bölümüyle doldurulur, fazla `ReceiveFromEx` veri kaybolur ve hata kodu WSAEMSGSIZE'a ayarlanmış SOCKET_ERROR değerini döndürür.

*lpSockAddr* sıfırsız sayılsa ve soket tip SOCK_DGRAM ise, verileri gönderen soketin ağ adresi ilgili [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısına kopyalanır. *lpSockAddrLen* tarafından işaret edilen değer bu yapının boyutuna başharflenir ve burada depolanan adresin gerçek boyutunu belirtmek üzere iade üzerine değiştirilir. Sokette gelen veri yoksa, soket engellenmedikçe `ReceiveFromEx` arama veri gelmesini bekler. Bu durumda, SOCKET_ERROR değeri WSAEWOULDBLOCK için ayarlanan hata kodu ile döndürülür. Geri `OnReceive` arama, daha fazla verinin ne zaman varabileceğini belirlemek için kullanılabilir.

Soket tip SOCK_STREAM ve uzak tarafı bağlantıyı zarif bir şekilde `ReceiveFromEx` kapatmışsa, alınan 0 bayt ile bir anda tamamlanır.

## <a name="casyncsocketsend"></a><a name="send"></a>CAsyncSocket::Gönder

Bağlı bir sokete veri göndermek için bu üye işlevini arayın.

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Aktabiri verilecek verileri içeren bir arabellek.

*nBufLen*<br/>
*LpBuf'taki* verilerin baytlarda uzunluğu.

*Nflags*<br/>
Aramanın nasıl yapıldığını belirtir. Bu işlevin anlamtileri soket seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, aşağıdaki değerlerden herhangi birinin C++ **VEYA** işleci ile birleştirilmesiyle oluşturulur:

- MSG_DONTROUTE Verilerin yönlendirmeye tabi olmaması gerektiğini belirtir. Bir Windows Soketleri tedarikçisi bu bayrağı yoksaymayı seçebilir.

- MSG_OOB Bant dışı veri gönderin (yalnızca SOCK_STREAM).

### <a name="return-value"></a>Dönüş Değeri

Hata oluşmazsa, `Send` gönderilen toplam karakter sayısını döndürür. (Bu *nBufLen*tarafından belirtilen sayıdan daha az olabilir unutmayın.) Aksi takdirde, SOCKET_ERROR değeri döndürülür ve belirli bir hata kodu [GetLastError](#getlasterror)çağırArak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEACCES İstenen adres bir yayın adresidir, ancak uygun bayrak ayarlanmadı.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAEFAULT *LPBuf* bağımsız değişkeni kullanıcı adres alanının geçerli bir bölümünde değildir.

- WSAENETRESET Windows Soketleri uygulaması bıraktığından bağlantı sıfırlanmalıdır.

- WSAENOBUFS Windows Soketleri uygulaması bir arabellek kilitlemi bildirir.

- WSAENOTCONN Soket bağlı değil.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAEOPNOTSUPP MSG_OOB belirtilmiş, ancak soket tip SOCK_STREAM değildir.

- WSAESHUTDOWN Soket kapatıldı; *nHow* 1 veya `Send` 2 olarak `ShutDown` ayarlandıktan sonra bir soketi aramak mümkün değildir.

- WSAEWOULDBLOCK Soket engellenmez olarak işaretlenir ve istenen işlem engellenir.

- WSAEMSGSIZE Soket tip SOCK_DGRAM ve veri gramı Windows Soketleri uygulaması tarafından desteklenen maksimumdan daha büyüktür.

- WSAEINVAL Soketi ile `Bind`bağlı olmamıştır.

- WSAECONNABORTED Sanal devre zaman aşımı veya diğer arıza nedeniyle iptal edildi.

- WSAECONNRESET Sanal devre uzak tarafta sıfırlandı.

### <a name="remarks"></a>Açıklamalar

`Send`giden verileri bağlı akış veya datagram soketlerine yazmak için kullanılır. Datagram soketleri için, [WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) yapısındaki `iMaxUdpDg` eleman tarafından verilen temel alt ağların maksimum IP paket boyutunu `AfxSocketInit`aşmamaya özen gösterilmelidir. Veriler temel protokolden atomik olarak geçemeyecek kadar uzunsa, WSAEMSGSIZE hatası üzerinden `GetLastError`döndürülür ve veri aktarılmez.

Bir veri gram soketi için `Send` bir a'nın başarılı bir şekilde tamamlanmasının verilerin başarıyla teslim edildiğini göstermediğini unutmayın.

Tür `CAsyncSocket` SOCK_STREAM nesneleri üzerinde, yazılan bayt sayısı, hem yerel hem de yabancı ana bilgisayarlarda arabellek kullanılabilirliğine bağlı olarak 1 ile istenen uzunluk arasında olabilir.

### <a name="example"></a>Örnek

  [CAsyncSocket örneğine bakın::OnSend](#onsend).

## <a name="casyncsocketsendto"></a><a name="sendto"></a>CAsyncSocket::SendTo

Belirli bir hedefe veri göndermek için bu üye işlevini arayın.

```
int SendTo(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);

int SendTo(
    const void* lpBuf,
    int nBufLen,
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Aktabiri verilecek verileri içeren bir arabellek.

*nBufLen*<br/>
*LpBuf'taki* verilerin baytlarda uzunluğu.

*nHostPort*<br/>
Soket uygulamasını tanımlayan bağlantı noktası.

*lpszHostAddress*<br/>
Bu nesnenin bağlı olduğu soketin ağ adresi: "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi noktalı bir sayı.

*Nflags*<br/>
Aramanın nasıl yapıldığını belirtir. Bu işlevin anlamtileri soket seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, aşağıdaki değerlerden herhangi birinin C++ **VEYA** işleci ile birleştirilmesiyle oluşturulur:

- MSG_DONTROUTE Verilerin yönlendirmeye tabi olmaması gerektiğini belirtir. Bir Windows Soketleri tedarikçisi bu bayrağı yoksaymayı seçebilir.

- MSG_OOB Bant dışı veri gönderin (yalnızca SOCK_STREAM).

*lpSockAddr*<br/>
Hedef soketin adresini içeren bir [SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısına işaretçi.

*nSockAddrLen*<br/>
*LpSockAddr'daki* adresin baytlarla uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Hata oluşmazsa, `SendTo` gönderilen toplam karakter sayısını döndürür. (Bu *nBufLen*tarafından belirtilen sayıdan daha az olabilir unutmayın.) Aksi takdirde, SOCKET_ERROR değeri döndürülür ve belirli bir hata kodu [GetLastError](#getlasterror)çağırArak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEACCES İstenen adres bir yayın adresidir, ancak uygun bayrak ayarlanmadı.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAEFAULT *LPBuf* veya *lpSockAddr* parametreleri kullanıcı adres alanının bir parçası değildir veya *lpSockAddr* bağımsız değişkeni çok küçüktür [(SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısının boyutundan daha az).

- WSAEINVAL Ana bilgisayar adı geçersizdir.

- WSAENETRESET Windows Soketleri uygulaması bıraktığından bağlantı sıfırlanmalıdır.

- WSAENOBUFS Windows Soketleri uygulaması bir arabellek kilitlemi bildirir.

- WSAENOTCONN Soket bağlı değildir (yalnızca SOCK_STREAM).

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAEOPNOTSUPP MSG_OOB belirtilmiş, ancak soket tip SOCK_STREAM değildir.

- WSAESHUTDOWN Soket kapatıldı; *nHow* 1 veya `SendTo` 2 olarak `ShutDown` ayarlandıktan sonra bir soketi aramak mümkün değildir.

- WSAEWOULDBLOCK Soket engellenmez olarak işaretlenir ve istenen işlem engellenir.

- WSAEMSGSIZE Soket tip SOCK_DGRAM ve veri gramı Windows Soketleri uygulaması tarafından desteklenen maksimumdan daha büyüktür.

- WSAECONNABORTED Sanal devre zaman aşımı veya diğer arıza nedeniyle iptal edildi.

- WSAECONNRESET Sanal devre uzak tarafta sıfırlandı.

- WSAEADDRNOTAVAIL Belirtilen adres yerel makineden kullanılamaz.

- WSAEAFNOSUPPORT Belirtilen ailedeki adresler bu soketle kullanılamaz.

- WSAEDESTADDRREQ Bir hedef adresi gereklidir.

- WSAENETUNREACH Şu anda bu ana bilgisayardan ağa ulaşılamaz.

### <a name="remarks"></a>Açıklamalar

`SendTo`datagram veya akış soketlerinde kullanılır ve giden verileri bir sokete yazmak için kullanılır. Datagram soketleri için, `iMaxUdpDg` [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)tarafından doldurulan [WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) yapısındaki eleman tarafından verilen alt ağların maksimum IP paket boyutunu aşmamaya özen gösterilmelidir. Veriler temel protokolden atomik olarak geçemeyecek kadar uzunsa, WSAEMSGSIZE hatası döndürülür ve veri aktarılmez.

A'nın `SendTo` başarıyla tamamlanmasının verilerin başarıyla teslim edildiğini göstermediğini unutmayın.

`SendTo`*yalnızca lpSockAddr* parametresi tarafından tanımlanan belirli bir sokete veri gramı göndermek için SOCK_DGRAM bir soketüzerinde kullanılır.

Bir yayın göndermek için (yalnızca SOCK_DGRAM, *lpSockAddr* parametresi üzerindeki adres INADDR_BROADCAST özel IP adresi kullanılarak oluşturulmalıdır (Windows Soketleri üstbilgi dosyası WINSOCK'ta tanımlanır. H) amaçlanan bağlantı noktası numarası ile birlikte. Veya *lpszHostAddress* parametresi NULL ise, soket yayın için yapılandırılır. Bir yayın vericesinin parçalanmanın oluşabileceği boyutu aşması genellikle tavsiye edilmez, bu da veri gramının veri bölümünün (üstbilgiler hariç) 512 baytı aşmaması gerektiği anlamına gelir.

IPv6 adreslerini işlemek için [CAsyncSocket::SendToEx](#sendtoex)adresini kullanın.

## <a name="casyncsocketsendtoex"></a><a name="sendtoex"></a>CAsyncSocket::SendToEx

Belirli bir hedefe veri göndermek için bu üye işlevini arayın (IPv6 adreslerini işler).

```
int SendToEx(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Aktabiri verilecek verileri içeren bir arabellek.

*nBufLen*<br/>
*LpBuf'taki* verilerin baytlarda uzunluğu.

*nHostPort*<br/>
Soket uygulamasını tanımlayan bağlantı noktası.

*lpszHostAddress*<br/>
Bu nesnenin bağlı olduğu soketin ağ adresi: "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi noktalı bir sayı.

*Nflags*<br/>
Aramanın nasıl yapıldığını belirtir. Bu işlevin anlamtileri soket seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, aşağıdaki değerlerden herhangi birinin C++ **VEYA** işleci ile birleştirilmesiyle oluşturulur:

- MSG_DONTROUTE Verilerin yönlendirmeye tabi olmaması gerektiğini belirtir. Bir Windows Soketleri tedarikçisi bu bayrağı yoksaymayı seçebilir.

- MSG_OOB Bant dışı veri gönderin (yalnızca SOCK_STREAM).

### <a name="return-value"></a>Dönüş Değeri

Hata oluşmazsa, `SendToEx` gönderilen toplam karakter sayısını döndürür. (Bu *nBufLen*tarafından belirtilen sayıdan daha az olabilir unutmayın.) Aksi takdirde, SOCKET_ERROR değeri döndürülür ve belirli bir hata kodu [GetLastError](#getlasterror)çağırArak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEACCES İstenen adres bir yayın adresidir, ancak uygun bayrak ayarlanmadı.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAEFAULT *LPBuf* veya *lpSockAddr* parametreleri kullanıcı adres alanının bir parçası değildir veya *lpSockAddr* bağımsız değişkeni çok küçüktür [(SOCKADDR](/windows/win32/winsock/sockaddr-2) yapısının boyutundan daha az).

- WSAEINVAL Ana bilgisayar adı geçersizdir.

- WSAENETRESET Windows Soketleri uygulaması bıraktığından bağlantı sıfırlanmalıdır.

- WSAENOBUFS Windows Soketleri uygulaması bir arabellek kilitlemi bildirir.

- WSAENOTCONN Soket bağlı değildir (yalnızca SOCK_STREAM).

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

- WSAEOPNOTSUPP MSG_OOB belirtilmiş, ancak soket tip SOCK_STREAM değildir.

- WSAESHUTDOWN Soket kapatıldı; *nHow* 1 veya `SendToEx` 2 olarak `ShutDown` ayarlandıktan sonra bir soketi aramak mümkün değildir.

- WSAEWOULDBLOCK Soket engellenmez olarak işaretlenir ve istenen işlem engellenir.

- WSAEMSGSIZE Soket tip SOCK_DGRAM ve veri gramı Windows Soketleri uygulaması tarafından desteklenen maksimumdan daha büyüktür.

- WSAECONNABORTED Sanal devre zaman aşımı veya diğer arıza nedeniyle iptal edildi.

- WSAECONNRESET Sanal devre uzak tarafta sıfırlandı.

- WSAEADDRNOTAVAIL Belirtilen adres yerel makineden kullanılamaz.

- WSAEAFNOSUPPORT Belirtilen ailedeki adresler bu soketle kullanılamaz.

- WSAEDESTADDRREQ Bir hedef adresi gereklidir.

- WSAENETUNREACH Şu anda bu ana bilgisayardan ağa ulaşılamaz.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CAsyncSocket ile aynıdır::SendTo,](#sendto) iPv6 adreslerinin yanı sıra eski protokolleri de işlemesi dışında.

`SendToEx`datagram veya akış soketlerinde kullanılır ve giden verileri bir sokete yazmak için kullanılır. Datagram soketleri için, `iMaxUdpDg` [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)tarafından doldurulan [WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) yapısındaki eleman tarafından verilen alt ağların maksimum IP paket boyutunu aşmamaya özen gösterilmelidir. Veriler temel protokolden atomik olarak geçemeyecek kadar uzunsa, WSAEMSGSIZE hatası döndürülür ve veri aktarılmez.

A'nın `SendToEx` başarıyla tamamlanmasının verilerin başarıyla teslim edildiğini göstermediğini unutmayın.

`SendToEx`*yalnızca lpSockAddr* parametresi tarafından tanımlanan belirli bir sokete veri gramı göndermek için SOCK_DGRAM bir soketüzerinde kullanılır.

Bir yayın göndermek için (yalnızca SOCK_DGRAM, *lpSockAddr* parametresi üzerindeki adres INADDR_BROADCAST özel IP adresi kullanılarak oluşturulmalıdır (Windows Soketleri üstbilgi dosyası WINSOCK'ta tanımlanır. H) amaçlanan bağlantı noktası numarası ile birlikte. Veya *lpszHostAddress* parametresi NULL ise, soket yayın için yapılandırılır. Bir yayın vericesinin parçalanmanın oluşabileceği boyutu aşması genellikle tavsiye edilmez, bu da veri gramının veri bölümünün (üstbilgiler hariç) 512 baytı aşmaması gerektiği anlamına gelir.

## <a name="casyncsocketsetsockopt"></a><a name="setsockopt"></a>CAsyncSocket::SetSockOpt

Bir soket seçeneği ayarlamak için bu üye işlevini arayın.

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Parametreler

*nOptionName*<br/>
Değerin ayarlanabilmek için soket seçeneği.

*lpOptionValue*<br/>
İstenen seçeneğin değerinin sağlandığı arabellek için bir işaretçi.

*nOptionLen*<br/>
Baytlarda *lpOptionValue* arabelleğinin boyutu.

*nSeviye*<br/>
Seçeneğin tanımlandığı düzey; desteklenen tek düzey SOL_SOCKET ve IPPROTO_TCP.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEFAULT *lpOptionValue* işlem adresi alanının geçerli bir bölümünde değildir.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAEINVAL *nLevel* geçerli değildir veya *lpOptionValue'daki* bilgiler geçerli değildir.

- WSAENETRESET Bağlantısı, SO_KEEPALIVE ayarlandığında zaman doldu.

- WSAENOPROTOOPT Seçeneği bilinmiyor veya desteklenmis. Özellikle, SO_BROADCAST tip SOCK_STREAM soketlerinde desteklenmezken, SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER ve SO_OOBINLINE tip SOCK_DGRAM soketlerinde desteklenmez.

- SO_KEEPALIVE ayarlandığında WSAENOTCONN Bağlantısı sıfırlanmıştır.

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

### <a name="remarks"></a>Açıklamalar

`SetSockOpt`herhangi bir durumda, herhangi bir türde bir soket ile ilişkili bir soket seçeneği için geçerli değeri ayarlar. Seçenekler birden çok protokol düzeyinde var olabilir, ancak bu belirtim yalnızca en üstteki "soket" düzeyinde bulunan seçenekleri tanımlar. Seçenekler, hızlandırılmış verilerin normal veri akışında alınıp alınmadığı, yayın iletilerinin sokete gönderip gönderilemeyeceği gibi soket işlemlerini etkiler.

İki tür soket seçeneği vardır: Bir özelliği veya davranışı etkinleştiren veya devre dışı bırakan Boolean seçenekleri ve tamsayı değeri veya yapısı gerektiren seçenekler. Boolean seçeneğini etkinleştirmek için *lpOptionValue* sıfır olmayan bir tamsayıya işaret edin. *LpOptionValue* seçeneğini devre dışı düşürmek için sıfıra eşit bir bir karşıcıya işaret edin. *nOptionLen* Boolean `sizeof(BOOL)` seçenekleri için eşit olmalıdır. Diğer seçenekler için *lpOptionValue,* seçenek için istenen değeri içeren veya yapıyı veya sondayı işaret ediyor ve *nOptionLen,* tümseğin veya yapının uzunluğudur.

SO_LINGER, gönderilmemiş veriler bir soketüzerinde sıraya girdiğinde `Close` ve işlek soketi kapatmak için çağrıldığında gerçekleştirilen eylemi denetler.

Varsayılan olarak, bir soket zaten kullanılmakta olan yerel bir adrese bağlanamaz [(bkz. Bind).](#bind) Ancak, zaman zaman bir adresi bu şekilde "yeniden kullanmak" istenebilebilir. Her bağlantı, yerel ve uzak adreslerin birleşimi ile benzersiz olarak tanımlandığından, uzak adresler farklı olduğu sürece aynı yerel adrese bağlı iki yuvaya sahip olmakla ilgili bir sorun yoktur.

İstenilen adres zaten `Bind` başka bir soket tarafından kullanılıyor olduğundan, Windows Soketleri uygulamasına `Bind` bir soket üzerindeki çağrıya izin verilmemesi gerektiğini bildirmek için, uygulama aramayı vermeden önce soket için SO_REUSEADDR soketi seçeneğini ayarlamalıdır. Seçeneğin yalnızca `Bind` arama sırasında yorumlandığını unutmayın: bu nedenle seçeneği varolan bir adrese bağlı olmayan bir soket üzerinde ayarlamak ve `Bind` aramayı ayarlamaktan veya sıfırlamaktan sonra seçeneği ayarlamak veya sıfırlamak bu veya başka bir soket üzerinde hiçbir etkisi yoktur.

Bir uygulama, Windows Soketleri uygulamasının SO_KEEPALIVE soketi seçeneğini açarak Iletim Denetim Protokolü (TCP) bağlantılarında "canlı tutma" paketlerinin kullanılmasını sağlamasını isteyebilir. Windows Soketleri uygulamasının keep-alives kullanımını desteklemesi gerekmez: eğer varsa, kesin semantik uygulamaya özgüdir ancak RFC 1122'nin 4.2.3.6 bölümüne uygun olmalıdır: "Internet Ana Bilgisayarları için Gereksinimler — İletişim Katmanları." "Keep-alives" sonucunda bir bağlantı bırakılırsa, WSAENETRESET hata kodu soketüzerinde devam eden çağrılara döndürülür ve sonraki aramalar WSAENOTCONN ile başarısız olur.

TCP_NODELAY seçeneği Nagle algoritmasını devre dışı bırakmaz. Nagle algoritması, tam boyutlu bir paket gönderilene kadar onaylanmamış gönder verilerini arabelleğe alarak bir ana bilgisayar tarafından gönderilen küçük paketlerin sayısını azaltmak için kullanılır. Ancak, bazı uygulamalar için bu algoritma performansı engelleyebilir ve TCP_NODELAY kapatmak için kullanılabilir. Uygulama yazarları, TCP_NODELAY ayarlamanın ağ performansı üzerinde önemli bir olumsuz etkisi olabileceğinden, bunu yapmanın etkisi iyi anlaşılıp istenmediği sürece TCP_NODELAY belirlememelidir. TCP_NODELAY, seviye IPPROTO_TCP kullanan tek desteklenen soket seçeneğidir; diğer tüm seçenekler SOL_SOCKET düzeyi kullanır.

Windows Soketleri'nin bazı uygulamaları, SO_DEBUG seçeneği bir uygulama tarafından ayarlanmışsa çıktı hata ayıklama bilgileri sağlar.

Aşağıdaki seçenekler `SetSockOpt`için desteklenir. Tür, *lpOptionValue*tarafından adreslenen veri türünü tanımlar.

|Değer|Tür|Anlamı|
|-----------|----------|-------------|
|SO_BROADCAST|Bool|Yayın iletilerinin sokete iletilmesine izin verin.|
|SO_DEBUG|Bool|Hata ayıklama bilgilerini kaydedin.|
|SO_DONTLINGER|Bool|Gönderilmemiş verilerin `Close` gönderilmesini beklemeyi engellemeyin. Bu seçeneği ayarlamak, `l_onoff` sıfıra ayarlanmış SO_LINGER ayarlamaya eşdeğerdir.|
|SO_DONTROUTE|Bool|Rota yapmayın: doğrudan arayüze gönderin.|
|SO_KEEPALIVE|Bool|Keep-alives gönder.|
|SO_LINGER|`struct LINGER`|Gönderilmemiş `Close` veriler varsa oyala.|
|SO_OOBINLINE|Bool|Normal veri akışında bant dışı veri alın.|
|SO_RCVBUF|**int**|Alıcılar için arabellek boyutunu belirtin.|
|SO_REUSEADDR|Bool|Soketin zaten kullanılmakta olan bir adrese bağlanmasına izin verin. (Bkz. [Bind](#bind).)|
|SO_SNDBUF|**int**|Göndermeler için arabellek boyutunu belirtin.|
|TCP_NODELAY|Bool|Birleştirme göndermek için Nagle algoritmasını devre dışı kılabilir.|

Berkeley Yazılım Dağıtımı (BSD) seçenekleri `SetSockOpt` için desteklenmeyen şunlardır:

|Değer|Tür|Anlamı|
|-----------|----------|-------------|
|SO_ACCEPTCONN|Bool|Soket dinliyor|
|SO_ERROR|**int**|Hata durumunu alın ve temizleyin.|
|SO_RCVLOWAT|**int**|Düşük su işareti alın.|
|SO_RCVTIMEO|**int**|Zaman aralarını alma|
|SO_SNDLOWAT|**int**|Düşük su işareti gönderin.|
|SO_SNDTIMEO|**int**|Zaman aralarını gönderin.|
|SO_TYPE|**int**|Soket türü.|
|IP_OPTIONS||IP üstbilgisinde seçenekler alanını ayarlayın.|

## <a name="casyncsocketshutdown"></a><a name="shutdown"></a>CAsyncSocket::Kapatma

Soketüzerinde gönderir, alır veya her ikisini de devre dışı kılabilir.

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>Parametreler

*Nhow*<br/>
Aşağıdaki numaralandırılmış değerleri kullanarak artık hangi işlem türlerine izin verilmeyeceğini açıklayan bir bayrak:

- **alır = 0**

- **gönderir = 1**

- **her ikisi de = 2**

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata kodu [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki hatalar bu üye işlev için geçerlidir:

- WSANOTINITIALISED Başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce oluşmalıdır.

- WSAENETDOWN Windows Soketleri uygulaması ağ alt sisteminin başarısız olduğunu algılamıştır.

- WSAEINVAL *nHow* geçerli değildir.

- WSAEINPROGRESS Bir engelleme Windows Soketleri işlemi devam etmektedir.

- WSAENOTCONN Soket bağlı değildir (yalnızca SOCK_STREAM).

- WSAENOTSOCK Tanımlayıcı bir soket değildir.

### <a name="remarks"></a>Açıklamalar

`ShutDown`alımı, iletimi veya her ikisini de devre dışı kılabilir. *nHow* 0 ise, soketüzerinde sonraki alır izin verilmez. Bunun alt protokol katmanları üzerinde hiçbir etkisi yoktur.

İletim Denetim Protokolü (TCP) için TCP penceresi değiştirilmez ve gelen veriler pencere tükenene kadar kabul edilir (ancak onaylanmaz). Kullanıcı Datagram Protokolü (UDP) için gelen datagramlar kabul edilir ve sıraya alınır. Hiçbir durumda bir ICMP hata paketi oluşturulur. *nHow* 1 ise, sonraki göndermeler izin verilmez. TCP soketleri için bir FIN gönderilir. *NHow* to 2'yi yukarıda açıklandığı gibi hem gönderir hem de alır devre dışı kılabilir.

Soketi `ShutDown` kapatmadığını ve sokete bağlı kaynakların çağrılana `Close` kadar serbest bırakılmayacağını unutmayın. Bir uygulama kapatıldıktan sonra bir soketi yeniden kullanabilmeye güvenmemelidir. Özellikle, böyle bir `Connect` soketüzerinde kullanımını desteklemek için bir Windows Soketleri uygulaması gerekli değildir.

### <a name="example"></a>Örnek

  [CAsyncSocket örneğine bakın::OnReceive](#onreceive).

## <a name="casyncsocketsocket"></a><a name="socket"></a>CASyncSocket::Soket

Soket tutamacı ayırır.

```
BOOL Socket(
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    int nProtocolType = 0,
    int nAddressFormat = PF_INET);
```

### <a name="parameters"></a>Parametreler

*nSocketType*<br/>
Belirtir `SOCK_STREAM` veya `SOCK_DGRAM`.

*Levent*<br/>
Uygulamanın ilgilendiği ağ olaylarının bir birleşimini belirten bir bitmaskesi.

- `FD_READ`: Okumaya hazır olduğu bildirimini almak istiyorum.

- `FD_WRITE`: Yazmaya hazır olduğu bildirimini almak istiyorum.

- `FD_OOB`: Bant dışı verilerin gelişine İlişkin bildirim almak istiyorum.

- `FD_ACCEPT`: Gelen bağlantıların bildirimini almak istiyorum.

- `FD_CONNECT`: Tamamlanan bağlantının bildirimini almak istiyorum.

- `FD_CLOSE`: Soket kapatma bildirimi almak istiyorum.

*nProtocolType*<br/>
Belirtilen adres ailesine özgü soketle kullanılacak protokol.

*nAddressFormat*<br/>
Adres aile belirtimi.

### <a name="return-value"></a>Dönüş Değeri

Başarıya, `TRUE` `FALSE` başarısızlıkta geri döner.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir soket tutamacı ayırır. Soketi belirli bir adrese bağlamak için [CAsyncSocket::Bind](#bind) aramaz, `Bind` bu nedenle soketi belirtilen adrese bağlamak için daha sonra aramanız gerekir. [CAsyncSocket::SetSockOpt'i](#setsockopt) kullanarak soket seçeneğini bağlanmadan önce ayarlayabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSocket Sınıfı](../../mfc/reference/csocket-class.md)<br/>
[Csocketfile Sınıfı](../../mfc/reference/csocketfile-class.md)
