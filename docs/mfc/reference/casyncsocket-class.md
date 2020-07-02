---
title: CAsyncSocket sınıfı
ms.date: 06/25/2020
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
ms.openlocfilehash: 9a3a04046d75a4cfdbb50347259820eb727eeb38
ms.sourcegitcommit: 83ea5df40917885e261089b103d5de3660314104
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85813595"
---
# <a name="casyncsocket-class"></a>CAsyncSocket sınıfı

Bir Windows yuvasını temsil eder: bir ağ iletişimi uç noktası.

## <a name="syntax"></a>Sözdizimi

```
class CAsyncSocket : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CAsyncSocket:: CAsyncSocket](#casyncsocket)|Bir `CAsyncSocket` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CAsyncSocket:: Accept](#accept)|Yuvada bir bağlantıyı kabul eder.|
|[CAsyncSocket:: AsyncSelect](#asyncselect)|Yuva için olay bildirimi ister.|
|[CAsyncSocket:: Attach](#attach)|Bir nesneye bir yuva tutamacı iliştirir `CAsyncSocket` .|
|[CAsyncSocket:: bind](#bind)|Yerel bir adresi yuva ile ilişkilendirir.|
|[CAsyncSocket:: Close](#close)|Yuvayı kapatır.|
|[CAsyncSocket:: Connect](#connect)|Eş yuvasına bağlantı kurar.|
|[CAsyncSocket:: Create](#create)|Yuva oluşturur.|
|[CAsyncSocket:: CreateEx](#createex)|Gelişmiş seçeneklerle bir yuva oluşturur.|
|[CAsyncSocket::D etach](#detach)|Bir nesneden bir yuva tanıtıcısını ayırır `CAsyncSocket` .|
|[CAsyncSocket:: FromHandle](#fromhandle)|Bir `CAsyncSocket` yuva tutamacı verilen bir nesneye bir işaretçi döndürür.|
|[CAsyncSocket:: GetLastError](#getlasterror)|Başarısız olan son işlem için hata durumunu alır.|
|[CAsyncSocket:: GetPeerName](#getpeername)|Yuvanın bağlandığı eş yuvasının adresini alır.|
|[CAsyncSocket:: GetPeerNameEx](#getpeernameex)|Yuvanın bağlı olduğu eş yuvasının adresini alır (IPv6 adreslerini işler).|
|[CAsyncSocket:: GetSockName](#getsockname)|Bir yuvanın yerel adını alır.|
|[CAsyncSocket:: GetSockNameEx](#getsocknameex)|Bir yuva için yerel adı alır (IPv6 adreslerini işler).|
|[CAsyncSocket:: GetSockOpt](#getsockopt)|Bir yuva seçeneği alır.|
|[CAsyncSocket:: IOCTL](#ioctl)|Yuva modunu denetler.|
|[CAsyncSocket:: Listen](#listen)|Gelen bağlantı isteklerini dinlemek için bir yuva oluşturur.|
|[CAsyncSocket:: Receive](#receive)|Yuvadan veri alır.|
|[CAsyncSocket:: ReceiveFrom](#receivefrom)|Bir veri birimi alır ve kaynak adresi depolar.|
|[CAsyncSocket:: ReceiveFromEx](#receivefromex)|Bir veri birimi alır ve kaynak adresini depolar (IPv6 adreslerini işler).|
|[CAsyncSocket:: Send](#send)|Bağlı bir yuvaya veri gönderir.|
|[CAsyncSocket:: SendTo](#sendto)|Verileri belirli bir hedefe gönderir.|
|[CAsyncSocket:: SendToEx](#sendtoex)|Verileri belirli bir hedefe gönderir (IPv6 adreslerini işler).|
|[CAsyncSocket:: SetSockOpt](#setsockopt)|Bir yuva seçeneği belirler.|
|[CAsyncSocket:: kapanıyor](#shutdown)|Soketi devre dışı bırakır `Send` ve/veya `Receive` çağırır.|
|[CASyncSocket:: soketi](#socket)|Bir yuva tutamacı ayırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CAsyncSocket:: OnAccept](#onaccept)|Bir dinleme yuvasına, çağırarak bekleyen bağlantı isteklerini kabul edemediğini bildirir `Accept` .|
|[CAsyncSocket:: OnClose](#onclose)|Kendisine bağlı olan yuvanın kapatıldığını bir yuvaya bildirir.|
|[CAsyncSocket:: OnConnect](#onconnect)|Başarılı veya hatalı olsun, bağlantı girişiminin tamamlandığını bağlama yuvasına bildirir.|
|[CAsyncSocket:: OnOutOfBandData](#onoutofbanddata)|Genellikle acil bir ileti olan yuvada okunan bant dışı veriler olduğunu bildiren bir yuvaya bildirir.|
|[CAsyncSocket:: OnReceive](#onreceive)|Çağırarak bir dinleme yuvasına alınacak verilerin olduğunu bildirir `Receive` .|
|[CAsyncSocket:: OnSend](#onsend)|Çağırarak, verileri gönderebileceği bir yuvaya bildirir `Send` .|

### <a name="public-operators"></a>Ortak İşleçler

|Name|Açıklama|
|----------|-----------------|
|[CAsyncSocket:: operator =](#operator_eq)|Nesnesine yeni bir değer atar `CAsyncSocket` .|
|[CAsyncSocket:: operator yuvası](#operator_socket)|Nesnenin yuva tanıtıcısını almak için bu işleci kullanın `CAsyncSocket` .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Name|Açıklama|
|----------|-----------------|
|[CAsyncSocket:: m_hSocket](#m_hsocket)|Bu nesneye eklenen yuva tanıtıcısını gösterir `CAsyncSocket` .|

## <a name="remarks"></a>Açıklamalar

Sınıfı, `CAsyncSocket` MFC ile birlikte Windows Yuvaları kullanmak isteyen programcılar için nesne odaklı bir soyutlama sağlayan Windows yuva IŞLEVLERI API 'sini kapsüller.

Bu sınıf, ağ iletişimlerini anladığınızı varsayımına göre belirlenir. Engelleme, bayt sırası farklılıkları ve Unicode ve çok baytlı karakter kümesi (MBCS) dizeleri arasındaki dönüştürmelerin işlenmesinden sorumlusunuz. Sizin için bu sorunları yöneten daha uygun bir arabirim isterseniz, bkz. sınıf [Csoketi](../../mfc/reference/csocket-class.md).

Bir nesne kullanmak için `CAsyncSocket` yapıcısını çağırın, ardından, kabul edilen yuvalar dışında temel yuva tanıtıcısını (türü) oluşturmak Için [Create](#create) işlevini çağırın `SOCKET` . Sunucu yuvası için [dinleme](#listen) üyesi işlevini çağırın ve bir istemci yuvası Için, [Connect](#connect) member işlevini çağırın. Sunucu yuvası bir bağlantı isteği aldıktan sonra [Accept](#accept) işlevini çağırmalıdır. `CAsyncSocket`Yuvalar arasındaki iletişimleri yürütmek için kalan işlevleri kullanın. Tamamlandıktan sonra, `CAsyncSocket` yığın üzerinde oluşturulduysa nesneyi yok edin; yıkıcı otomatik olarak [Close](#close) işlevini çağırır. YUVA veri türü, [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md)makalesinde açıklanmaktadır.

> [!NOTE]
> Statik olarak bağlı bir MFC uygulamasında ikincil iş parçacıklarında MFC Yuvaları kullanırken, `AfxSocketInit` yuva kitaplıklarını başlatmak için yuva kullanan her bir iş parçacığında çağrı yapmanız gerekir. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığında çağırılır.

Daha fazla bilgi için bkz. [Windows Yuvaları: sınıf CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) ve ilgili makalelerin yanı sıra [WINDOWS Sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsock. h

## <a name="casyncsocketaccept"></a><a name="accept"></a>CAsyncSocket:: Accept

Bir yuvada bir bağlantıyı kabul etmek için bu üye işlevi çağırın.

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>Parametreler

*Rconnectedsoketi*<br/>
Bağlantı için kullanılabilen yeni bir yuvayı tanımlayan bir başvuru.

*lpSockAddr*<br/>
Ağ üzerinde bilinen, bağlantı yuvasının adresini alan bir [sockaddr](/windows/win32/winsock/sockaddr-2) yapısına yönelik bir işaretçi. *LpSockAddr* bağımsız değişkeninin tam biçimi, yuva oluşturulduğunda oluşturulan adres ailesine göre belirlenir. *LpSockAddr* ve/veya *lpSockAddrLen* , null değerine eşitse, kabul edilen yuvanın uzak adresiyle ilgili hiçbir bilgi döndürülmez.

*lpSockAddrLen*<br/>
Bayt cinsinden *lpSockAddr* içindeki adresin uzunluğuna yönelik bir işaretçi. *LpSockAddrLen* bir değer-sonuç parametresidir: başlangıçta *lpSockAddr*tarafından işaret edilen boşluk miktarını içermelidir; Sonuç olarak, döndürülen adresin gerçek uzunluğunu (bayt olarak) içerir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni çok küçük ( [sockaddr](/windows/win32/winsock/sockaddr-2) yapısının boyutundan daha az).

- WSAEINPROGRESS bir engelleme Windows Yuvaları çağrısı devam ediyor.

- WSAEINVAL `Listen` , kabul etmeden önce çağrılmadı.

- WSAEMFILE, kabul edilecek giriş sonrasında sıra boştur ve kullanılabilir tanımlayıcı yoktur.

- WSAENOBUFS kullanılabilir arabellek alanı yok.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- WSAEOPNOTSUPP başvurulan yuva bağlantı yönelimli hizmeti destekleyen bir tür değil.

- WSAEWOULDBLOCK yuva engellemeyen olarak işaretlendi ve kabul edilecek bir bağlantı yok.

### <a name="remarks"></a>Açıklamalar

Bu yordam, bekleyen bağlantıların sırasındaki ilk bağlantıyı ayıklar, bu soket ile aynı özelliklere sahip yeni bir yuva oluşturur ve bunu *rConnectedSocket*'e ekler. Kuyrukta bekleyen bir bağlantı yoksa, `Accept` sıfır döndürür ve `GetLastError` bir hata döndürür. Kabul edilen yuva ( *rConnectedSocket)* , daha fazla bağlantı kabul etmek için kullanılamaz. Özgün yuva açık ve dinliyor durumda kalır.

*LpSockAddr* bağımsız değişkeni, iletişim katmanında bilinen, bağlantı yuvasının adresiyle doldurulmuş bir sonuç parametresidir. `Accept`SOCK_STREAM gibi bağlantı tabanlı yuva türleriyle kullanılır.

## <a name="casyncsocketasyncselect"></a><a name="asyncselect"></a>CAsyncSocket:: AsyncSelect

Bir yuva için olay bildirimi istemek üzere bu üye işlevini çağırın.

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parametreler

*Elvent*<br/>
Uygulamanın ilgilendiği ağ olaylarının birleşimini belirten bir bit maskesi.

- FD_READ okuma için hazır olma bildirimini almak Istiyor.

- Veriler okunmanız için kullanılabilir olduğunda bildirim almak Istiyor FD_WRITE.

- FD_OOB bant dışı verilerin gelişini almak Istiyor.

- FD_ACCEPT gelen bağlantılar hakkında bildirim almak Istiyor.

- FD_CONNECT bağlantı sonuçları bildirimini almak Istiyor.

- Bir yuva bir eş tarafından kapatıldığında bildirim almak Istiyor FD_CLOSE.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEINVAL belirtilen parametrelerden birinin geçersiz olduğunu gösterir.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

### <a name="remarks"></a>Açıklamalar

Bu işlev, yuva için hangi MFC geri çağırma bildirimi işlevlerinin çağrılacaktır belirtmek için kullanılır. `AsyncSelect`Bu yuvayı otomatik olarak engellenmeyen moda ayarlar. Daha fazla bilgi için [Windows Yuvaları: yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md)makalesine bakın.

## <a name="casyncsocketattach"></a><a name="attach"></a>CAsyncSocket:: Attach

*HSocket* tanıtıcısını bir nesneye iliştirmek için bu üye işlevini çağırın `CAsyncSocket` .

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parametreler

*hSocket*<br/>
Yuva için bir tanıtıcı içerir.

*Elvent*<br/>
Uygulamanın ilgilendiği ağ olaylarının birleşimini belirten bir bit maskesi.

- FD_READ okuma için hazır olma bildirimini almak Istiyor.

- Veriler okunmanız için kullanılabilir olduğunda bildirim almak Istiyor FD_WRITE.

- FD_OOB bant dışı verilerin gelişini almak Istiyor.

- FD_ACCEPT gelen bağlantılar hakkında bildirim almak Istiyor.

- FD_CONNECT bağlantı sonuçları bildirimini almak Istiyor.

- Bir yuva bir eş tarafından kapatıldığında bildirim almak Istiyor FD_CLOSE.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı.

### <a name="remarks"></a>Açıklamalar

YUVA tutamacı nesnenin [m_hSocket](#m_hsocket) veri üyesinde depolanır.

## <a name="casyncsocketbind"></a><a name="bind"></a>CAsyncSocket:: bind

Yerel bir adresi yuva ile ilişkilendirmek için bu üye işlevini çağırın.

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
Yuva uygulamasını tanımlayan bağlantı noktası.

*lpszSocketAddress*<br/>
Ağ adresi, "128.56.22.8" gibi noktalı bir sayıdır. Bu parametre için NULL dizenin geçirilmesi, `CAsyncSocket` Örneğin tüm ağ arabirimlerinde istemci etkinliğini dinlemesi gerektiğini gösterir.

*lpSockAddr*<br/>
Bu yuvaya atanacak adresi içeren bir [sockaddr](/windows/win32/winsock/sockaddr-2) yapısına yönelik işaretçi.

*nSockAddrLen*<br/>
Bayt cinsinden *lpSockAddr* içindeki adresin uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Aşağıdaki listede, döndürülebilecek hatalardan bazıları yer almaktadır. Tüm liste için bkz. [Windows Sockets hata kodları](/windows/win32/winsock/windows-sockets-error-codes-2).

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEADDRINUSE belirtilen adres zaten kullanımda. ( [Setsockopt](#setsockopt)altındaki SO_REUSEADDR yuva seçeneğine bakın.)

- WSAEFAULT *nSockAddrLen* bağımsız değişkeni çok küçük ( [sockaddr](/windows/win32/winsock/sockaddr-2) yapısının boyutundan daha az).

- WSAEINPROGRESS bir engelleme Windows Yuvaları çağrısı devam ediyor.

- WSAEAFNOSUPPORT belirtilen adres ailesi bu bağlantı noktası tarafından desteklenmiyor.

- WSAEINVAL yuva zaten bir adrese bağlıydı.

- WSAENOBUFS yeterli arabellek yok, çok fazla bağlantı var.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

### <a name="remarks"></a>Açıklamalar

Bu yordam, bağlı olmayan bir veri birimi veya akış yuvasında, sonraki `Connect` veya `Listen` çağrılardan önce kullanılır. Bağlantı isteklerini kabul etmeden önce, bir dinleme sunucusu yuvası bir bağlantı noktası numarası seçip çağırarak Windows Yuvaları tarafından bilinmelidir `Bind` . `Bind`adlandırılmamış bir yuvaya yerel bir ad atayarak, yuvanın yerel ilişkilendirmesini (ana bilgisayar adresi/bağlantı noktası numarası) belirler.

## <a name="casyncsocketcasyncsocket"></a><a name="casyncsocket"></a>CAsyncSocket:: CAsyncSocket

Boş bir yuva nesnesi oluşturur.

```
CAsyncSocket();
```

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra, `Create` yuva veri yapısını oluşturmak ve adresini bağlamak için üye işlevini çağırmanız gerekir. (Bir Windows Sockets iletişiminin sunucu tarafında, dinleme yuvası çağrıda kullanılacak bir yuva oluşturduğunda `Accept` , `Create` Bu yuva için çağrı yapmayın.)

## <a name="casyncsocketclose"></a><a name="close"></a>CAsyncSocket:: Close

Yuvayı kapatır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, daha fazla başvuru WSAENOTSOCK hatasıyla başarısız olacak şekilde yuva tanımlayıcısını serbest bırakır. Bu, temeldeki yuvanın son başvurusu ise, ilişkili adlandırma bilgileri ve sıraya alınan veriler atılır. Yuva nesnesinin yıkıcısı `Close` sizin için çağırır.

İçin `CAsyncSocket` değil, için, `CSocket` semantiğinin `Close` SO_LINGER ve SO_DONTLINGER yuva seçeneklerinden etkilendi. Daha fazla bilgi için bkz. üye işlevi `GetSockOpt` .

## <a name="casyncsocketconnect"></a><a name="connect"></a>CAsyncSocket:: Connect

Bağlanmayan bir akışa veya veri birimi yuvasına bağlantı kurmak için bu üye işlevi çağırın.

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
Bu nesnenin bağlı olduğu yuvanın ağ adresi: "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi noktalı bir sayı.

*nHostPort*<br/>
Yuva uygulamasını tanımlayan bağlantı noktası.

*lpSockAddr*<br/>
Bağlı yuvanın adresini içeren bir [sockaddr](/windows/win32/winsock/sockaddr-2) yapısına yönelik işaretçi.

*nSockAddrLen*<br/>
Bayt cinsinden *lpSockAddr* içindeki adresin uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu, WSAEWOULDBLOCK hata kodunu gösteriyorsa ve uygulamanız geçersiz kılınabilir geri çağırmaları kullanıyorsa, `OnConnect` bağlanma işlemi tamamlandığında uygulamanız bir ileti alır. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEADDRINUSE belirtilen adres zaten kullanımda.

- WSAEINPROGRESS bir engelleme Windows Yuvaları çağrısı devam ediyor.

- WSAEADDRNOTAVAIL belirtilen adres yerel makineden kullanılamıyor.

- Belirtilen ailedeki WSAEAFNOSUPPORT adresleri bu yuvada kullanılamaz.

- WSAECONNREFUSED bağlanma girişimi reddedildi.

- WSAEDESTADDRREQ hedef adresi gerekiyor.

- WSAEFAULT *nSockAddrLen* bağımsız değişkeni yanlış.

- WSAEINVAL geçersiz ana bilgisayar adresi.

- WSAEISCONN yuva zaten bağlı.

- WSAEMFILE daha fazla dosya tanımlayıcısı yok.

- Bu konaktan, bu ana bilgisayardan, ağa ulaşmayı Şu anda ulaşılamıyor.

- WSAENOBUFS kullanılabilir arabellek alanı yok. Yuva bağlanamıyor.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- Bir bağlantı oluşturmadan WSAETIMEıNOUT bağlanma denemesi zaman aşımına uğradı.

- WSAEWOULDBLOCK yuva nonengellemeyen olarak işaretlendi ve bağlantı hemen tamamlanamaz.

### <a name="remarks"></a>Açıklamalar

Yuva ilişkisiz ise, benzersiz değerler sistem tarafından yerel ilişkiye atanır ve yuva bağlı olarak işaretlenir. Ad yapısının adres alanı tümüyle sıfırlardan bulunursa, `Connect` sıfır döndürür. Genişletilmiş hata bilgilerini almak için `GetLastError` üye işlevini çağırın.

Akış yuvaları (tür SOCK_STREAM) için, yabancı ana bilgisayara etkin bir bağlantı başlatılır. Yuva çağrısı başarıyla tamamlandığında, yuva veri göndermeye/almaya hazırdır.

Bir veri birimi yuvası (tür SOCK_DGRAM) için, sonraki ve çağrılarında kullanılacak varsayılan bir hedef ayarlanır `Send` `Receive` .

## <a name="casyncsocketcreate"></a><a name="create"></a>CAsyncSocket:: Create

`Create`Windows yuvasını oluşturmak ve eklemek için bir yuva nesnesi oluşturduktan sonra üye işlevini çağırın.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Parametreler

*nSocketPort*<br/>
Yuva ile kullanılacak iyi bilinen bir bağlantı noktası veya Windows Sockets 'in bir bağlantı noktasını seçmesini istiyorsanız 0.

*nSocketType*<br/>
SOCK_STREAM veya SOCK_DGRAM.

*Elvent*<br/>
Uygulamanın ilgilendiği ağ olaylarının birleşimini belirten bir bit maskesi.

- FD_READ okuma için hazır olma bildirimini almak Istiyor.

- FD_WRITE yazma hazırlığı hakkında bildirim almak Istiyor.

- FD_OOB bant dışı verilerin gelişini almak Istiyor.

- FD_ACCEPT gelen bağlantılar hakkında bildirim almak Istiyor.

- FD_CONNECT tamamlanmış bağlantı bildirimini almak Istiyor.

- FD_CLOSE yuva kapanışının bildirimini almak Istiyor.

*lpszSockAddress*<br/>
Bağlı yuvanın ağ adresini içeren bir dize işaretçisi, "128.56.22.8" gibi noktalı bir sayıdır. Bu parametre için NULL dizenin geçirilmesi, `CAsyncSocket` Örneğin tüm ağ arabirimlerinde istemci etkinliğini dinlemesi gerektiğini gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEAFNOSUPPORT belirtilen adres ailesi desteklenmiyor.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAEMFILE daha fazla dosya tanımlayıcısı yok.

- WSAENOBUFS kullanılabilir arabellek alanı yok. Yuva oluşturulamıyor.

- WSAEPROTONOSUPPORT belirtilen bağlantı noktası desteklenmiyor.

- WSAEPROTOTYPE belirtilen bağlantı noktası bu yuva için yanlış türde.

- WSAESOCKTNOSUPPORT belirtilen yuva türü bu adres ailesinde desteklenmiyor.

### <a name="remarks"></a>Açıklamalar

`Create`[soketi](#socket) çağırır ve başarılı olursa, yuvayı belirtilen adrese bağlamak için [bağlama](#bind) çağırır. Aşağıdaki yuva türleri desteklenir:

- SOCK_STREAM sıralı, güvenilir, tam çift yönlü, bağlantı tabanlı bayt akışları sağlar. Internet adresi ailesi için Iletim Denetim Protokolü 'Nü (TCP) kullanır.

- SOCK_DGRAM, bağlantısız, güvenilir olmayan (genellikle küçük) en fazla uzunlukta paketler olan datagramları destekler. Internet adresi ailesi için Kullanıcı Datagram protokolünü (UDP) kullanır.

    > [!NOTE]
    >  `Accept`Üye işlevi, parametresi olarak yeni, boş bir nesneye başvuru alır `CSocket` . Bu nesneyi, çağrısından önce oluşturmanız gerekir `Accept` . Bu yuva nesnesi kapsam dışına geçtiğinde bağlantının kapandığını aklınızda bulundurun. `Create`Bu yeni yuva nesnesi için çağrı kullanmayın.

> [!IMPORTANT]
> `Create`, iş parçacığı açısından güvenli **değildir** .  Farklı iş parçacıkları tarafından aynı anda çağrılabileceği çok iş parçacıklı bir ortamda çağırıyorsanız, her çağrıyı bir mutex veya diğer eşitleme kilidiyle koruduğunuzdan emin olun.

Stream ve datagram yuvaları hakkında daha fazla bilgi için bkz. [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md) ve [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../../mfc/windows-sockets-ports-and-socket-addresses.md) ve [Windows Yuvaları 2 API](/windows/win32/WinSock/windows-sockets-start-page-2).

## <a name="casyncsocketcreateex"></a><a name="createex"></a>CAsyncSocket:: CreateEx

`CreateEx`Windows yuvasını oluşturmak ve eklemek için bir yuva nesnesi oluşturduktan sonra üye işlevini çağırın.

Yuva türü gibi gelişmiş seçenekler sağlamanız gerektiğinde bu işlevi kullanın.

```
BOOL CreateEx(
    ADDRINFOT* pAI,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parametreler

*PAI*<br/>
Aile ve yuva türü gibi yuva bilgilerini tutmak için bir [ADDRINFOT](https://docs.microsoft.com/windows/win32/api/ws2def/ns-ws2def-addrinfoa) işaretçisi.

*Elvent*<br/>
Uygulamanın ilgilendiği ağ olaylarının birleşimini belirten bir bit maskesi.

- FD_READ okuma için hazır olma bildirimini almak Istiyor.

- FD_WRITE yazma hazırlığı hakkında bildirim almak Istiyor.

- FD_OOB bant dışı verilerin gelişini almak Istiyor.

- FD_ACCEPT gelen bağlantılar hakkında bildirim almak Istiyor.

- FD_CONNECT tamamlanmış bağlantı bildirimini almak Istiyor.

- FD_CLOSE yuva kapanışının bildirimini almak Istiyor.

### <a name="return-value"></a>Dönüş Değeri

[Create ()](#return-value-5)için dönüş değerine bakın.

### <a name="remarks"></a>Açıklamalar

[Create ()](#remarks-8)hakkındaki açıklamalara bakın.

## <a name="casyncsocketdetach"></a><a name="detach"></a>CAsyncSocket::D etach

*M_hSocket* VERI üyesinde yuva tanıtıcısını `CAsyncSocket` nesneden AYıRMAK ve *m_hSocket* null olarak ayarlamak için bu üye işlevi çağırın.

```
SOCKET Detach();
```

## <a name="casyncsocketfromhandle"></a><a name="fromhandle"></a>CAsyncSocket:: FromHandle

Nesnesine bir işaretçi döndürür `CAsyncSocket` .

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Parametreler

*hSocket*<br/>
Yuva için bir tanıtıcı içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir nesne işaretçisi `CAsyncSocket` veya `CAsyncSocket` *hSocket*'e iliştirilmiş nesne yoksa null.

### <a name="remarks"></a>Açıklamalar

Bir yuva tutamacı verildiğinde, bir `CAsyncSocket` nesne tutamaya iliştirilmişse, üye IşLEVI null değerini döndürür.

## <a name="casyncsocketgetlasterror"></a><a name="getlasterror"></a>CAsyncSocket:: GetLastError

Başarısız olan son işlem için hata durumunu almak üzere bu üye işlevi çağırın.

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri, bu iş parçacığı tarafından gerçekleştirilen son Windows Yuvaları API yordamının hata kodunu gösterir.

### <a name="remarks"></a>Açıklamalar

Belirli bir üye işlevi bir hatanın oluştuğunu gösteriyorsa, `GetLastError` uygun hata kodunu almak için çağrılmalıdır. Geçerli hata kodlarının bir listesi için bkz. bağımsız üye işlev açıklamaları.

Hata kodları hakkında daha fazla bilgi için bkz. [Windows Sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2).

## <a name="casyncsocketgetpeername"></a><a name="getpeername"></a>CAsyncSocket:: GetPeerName

Bu yuvanın bağlandığı eş yuvasının adresini almak için bu üye işlevini çağırın.

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
`CString`Noktalı sayı IP adresi alan bir nesneye başvuru.

*rPeerPort*<br/>
Bir bağlantı noktası depolayan bir UINT öğesine başvuru.

*lpSockAddr*<br/>
Eş yuvasının adını alan [sockaddr](/windows/win32/winsock/sockaddr-2) yapısına yönelik bir işaretçi.

*lpSockAddrLen*<br/>
Bayt cinsinden *lpSockAddr* içindeki adresin uzunluğuna yönelik bir işaretçi. Sonuç olarak, *lpSockAddrLen* bağımsız değişkeni bayt olarak döndürülen *lpSockAddr* gerçek boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni yeterince büyük değil.

- WSAEINPROGRESS bir engelleme Windows Yuvaları çağrısı devam ediyor.

- WSAENOTCONN yuva bağlı değil.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

### <a name="remarks"></a>Açıklamalar

IPv6 adreslerini işlemek için [CAsyncSocket:: GetPeerNameEx](#getpeernameex)kullanın.

## <a name="casyncsocketgetpeernameex"></a><a name="getpeernameex"></a>CAsyncSocket:: GetPeerNameEx

Bu yuvanın bağlı olduğu eş yuvasının adresini almak için bu üye işlevini çağırın (IPv6 adreslerini işler).

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>Parametreler

*rPeerAddress*<br/>
`CString`Noktalı sayı IP adresi alan bir nesneye başvuru.

*rPeerPort*<br/>
Bir bağlantı noktası depolayan bir UINT öğesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni yeterince büyük değil.

- WSAEINPROGRESS bir engelleme Windows Yuvaları çağrısı devam ediyor.

- WSAENOTCONN yuva bağlı değil.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

### <a name="remarks"></a>Açıklamalar

Bu işlev, [CAsyncSocket:: GetPeerName](#getpeername) ile aynıdır, ancak IPv6 adreslerini ve eski protokolleri de işler.

## <a name="casyncsocketgetsockname"></a><a name="getsockname"></a>CAsyncSocket:: GetSockName

Bir yuvanın yerel adını almak için bu üye işlevi çağırın.

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
`CString`Noktalı sayı IP adresi alan bir nesneye başvuru.

*rSocketPort*<br/>
Bir bağlantı noktası depolayan bir UINT öğesine başvuru.

*lpSockAddr*<br/>
Yuva adresini alan [sockaddr](/windows/win32/winsock/sockaddr-2) yapısına yönelik bir işaretçi.

*lpSockAddrLen*<br/>
Bayt cinsinden *lpSockAddr* içindeki adresin uzunluğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni yeterince büyük değil.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- WSAEINVAL yuva ile bir adrese bağlanmadı `Bind` .

### <a name="remarks"></a>Açıklamalar

Bu çağrı, özellikle `Connect` bir çağrı yapılmadan bir çağrı yapıldığında yararlıdır `Bind` ; Bu çağrı, sistem tarafından ayarlanan yerel ilişkilendirmeyi belirleyebilmeniz için tek bir yol sağlar.

IPv6 adreslerini işlemek için [CAsyncSocket:: GetSockNameEx](#getsocknameex) kullanın

## <a name="casyncsocketgetsocknameex"></a><a name="getsocknameex"></a>CAsyncSocket:: GetSockNameEx

Bir yuvanın yerel adını almak için bu üye işlevi çağırın (IPv6 adreslerini işler).

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>Parametreler

*rSocketAddress*<br/>
`CString`Noktalı sayı IP adresi alan bir nesneye başvuru.

*rSocketPort*<br/>
Bir bağlantı noktası depolayan bir UINT öğesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni yeterince büyük değil.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- WSAEINVAL yuva ile bir adrese bağlanmadı `Bind` .

### <a name="remarks"></a>Açıklamalar

Bu çağrı, IPv6 adreslerini ve eski protokolleri de işleyeceğinden, [CAsyncSocket:: GetSockName](#getsockname) ile aynıdır.

Bu çağrı, özellikle `Connect` bir çağrı yapılmadan bir çağrı yapıldığında yararlıdır `Bind` ; Bu çağrı, sistem tarafından ayarlanan yerel ilişkilendirmeyi belirleyebilmeniz için tek bir yol sağlar.

## <a name="casyncsocketgetsockopt"></a><a name="getsockopt"></a>CAsyncSocket:: GetSockOpt

Bir yuva seçeneği almak için bu üye işlevini çağırın.

```
BOOL GetSockOpt(
    int nOptionName,
    void* lpOptionValue,
    int* lpOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Parametreler

*nOptionName*<br/>
Değerin alınacağı yuva seçeneği.

*lpOptionValue*<br/>
İstenen seçeneğin değerinin döndürüleceği arabelleğin bir işaretçisi. Seçili seçenekle ilişkili değer buffer *lpOptionValue*içinde döndürülür. *LpOptionLen* tarafından işaret edilen tamsayı, başlangıçta bu arabelleğin boyutunu bayt cinsinden içermelidir; dönüş sırasında döndürülen değerin boyutuna ayarlanır. SO_LINGER için bu, bir yapının boyutu olacaktır `LINGER` ; diğer tüm seçenekler için, seçeneğe bağlı olarak bool veya **int**boyut olacaktır. Açıklamalar bölümünde Seçenekler listesini ve boyutlarını görün.

*lpOptionLen*<br/>
*LpOptionValue* arabelleğinin bayt cinsinden boyutu için bir işaretçi.

*nLevel*<br/>
Seçeneğin tanımlandığı düzey; desteklenen tek düzeyler SOL_SOCKET ve IPPROTO_TCP.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bir seçenek hiçbir şekilde ayarlanmamışsa `SetSockOpt` , `GetSockOpt` seçeneğinin varsayılan değerini döndürür. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEFAULT *lpOptionLen* bağımsız değişkeni geçersizdi.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAENOPROTOOPT seçeneği bilinmiyor veya desteklenmiyor. Özellikle, SOCK_STREAM türündeki yuvalarda SO_BROADCAST desteklenmez; SO_ACCEPTCONN, SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER ve SO_OOBINLINE sock_dgram tür yuvalarda desteklenmez.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

### <a name="remarks"></a>Açıklamalar

`GetSockOpt`herhangi bir durumda, herhangi bir türde bir yuva ile ilişkili bir yuva seçeneğinin geçerli değerini alır ve sonucu *lpOptionValue*olarak depolar. Seçenekler, paketlerin yönlendirilmesi, bant dışı veri aktarımı vb. gibi yuva işlemlerini etkiler.

Aşağıdaki seçenekler için desteklenir `GetSockOpt` . Türü, *lpOptionValue*tarafından belirtilen veri türünü tanımlar. TCP_NODELAY seçeneği düzey IPPROTO_TCP kullanır; diğer tüm seçenekler düzey SOL_SOCKET kullanır.

|Değer|Tür|Anlamı|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Yuva dinliyor.|
|SO_BROADCAST|BOOL|Yuva, yayın iletilerinin iletilmesi için yapılandırılır.|
|SO_DEBUG|BOOL|Hata ayıklama etkinleştirildi.|
|SO_DONTLINGER|BOOL|True ise SO_LINGER seçeneği devre dışıdır.|
|SO_DONTROUTE|BOOL|Yönlendirme devre dışı.|
|SO_ERROR|**int**|Hata durumunu alın ve temizleyin.|
|SO_KEEPALIVE|BOOL|Etkin tutma gönderme gönderiliyor.|
|SO_LINGER|`struct LINGER`|Geçerli lger seçeneklerini döndürür.|
|SO_OOBINLINE|BOOL|Normal veri akışında bant dışı veriler alınır.|
|SO_RCVBUF|int|Alma için arabellek boyutu.|
|SO_REUSEADDR|BOOL|Yuva zaten kullanımda olan bir adrese bağlanabilir.|
|SO_SNDBUF|**int**|Gönderimler için arabellek boyutu.|
|SO_TYPE|**int**|Yuva türü (örneğin, SOCK_STREAM).|
|TCP_NODELAY|BOOL|Birleştirme gönderme için Nagle algoritmasını devre dışı bırakır.|

İçin desteklenmeyen Berkeley yazılım dağıtımı (BSD) seçenekleri `GetSockOpt` şunlardır:

|Değer|Tür|Anlamı|
|-----------|----------|-------------|
|SO_RCVLOWAT|**int**|Düşük su işareti al.|
|SO_RCVTIMEO|**int**|Alma zaman aşımı.|
|SO_SNDLOWAT|**int**|Düşük su işareti gönderin.|
|SO_SNDTIMEO|**int**|Gönderme zaman aşımı.|
|IP_OPTIONS||IP üstbilgisindeki seçenekleri alın.|
|TCP_MAXSEG|**int**|En fazla TCP segment boyutunu alın.|

`GetSockOpt`Desteklenmeyen bir seçenekle çağırmak, öğesinden BIR WSAENOPROTOOPT hata kodu oluşmasına neden olur `GetLastError` .

## <a name="casyncsocketioctl"></a><a name="ioctl"></a>CAsyncSocket:: IOCTL

Bir yuvanın modunu denetlemek için bu üye işlevi çağırın.

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>Parametreler

*lCommand*<br/>
Yuvada gerçekleştirilecek komut.

*lpArgument*<br/>
*LCommand*parametresi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEINVAL *lCommand* geçerli bir komut değil veya *lpArgument* , *lCommand*için kabul edilebilir bir parametre değil veya komut sağlanan yuva türü için geçerli değil.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

### <a name="remarks"></a>Açıklamalar

Bu yordam herhangi bir durumda herhangi bir yuvada kullanılabilir. Protokol ve iletişim alt sisteminden bağımsız olarak, soket ile ilişkili işletim parametrelerini almak veya almak için kullanılır. Aşağıdaki komutlar desteklenir:

- FIONBIO yuva üzerinde engelleyici olmayan modu etkinleştirir veya devre dışı bırakır. *LpArgument* parametresi `DWORD` , blok olmayan mod etkinleştirilse sıfır olmayan bir değer ve devre dışı bırakılabileceği sıfır olduğunda işaret eder. `AsyncSelect`Bir yuvada verildiyse, `IOCtl` yeniden engelleme moduna geçmek için herhangi BIR deneme WSAEINVAL ile başarısız olur. Yuvayı engelleme moduna geri ayarlamak ve WSAEINVAL hatasını engellemek için, bir uygulamanın ilk önce devre dışı bırakılması gerekir ve sonra bir uygulama, `AsyncSelect` `AsyncSelect` 0 ' a eşit *ve* ardından çağırır `IOCtl` .

- FIONREAD, bu yuvadan bir çağrıyla okunabilecek en fazla bayt sayısını tespit edebilir `Receive` . *LpArgument* parametresi, `DWORD` sonucu depolayan bir içinde işaret eder `IOCtl` . Bu yuva SOCK_STREAM türünde ise, FIONREAD tek tek içinde okunabilecek toplam veri miktarını döndürür `Receive` ; Bu, normalde yuvada sıraya alınan toplam veri miktarıyla aynıdır. Bu yuva SOCK_DGRAM türünde ise FIONREAD, yuvada sıraya alınan ilk veri biriminin boyutunu döndürür.

- SıOCATMARK, tüm bant dışı verilerin okunup okunmadığını belirleme. Bu, yalnızca bant dışı verilerin (SO_OOBINLINE) satır içi alımı için yapılandırılmış SOCK_STREAM bir yuva için geçerlidir. Bant dışı veriler okunmayı bekliyorsa, işlem sıfır dışında bir değer döndürür. Aksi takdirde, 0 döndürür ve `Receive` yuva üzerinde yapılan bir sonraki ya da tüm verilerin bir `ReceiveFrom` kısmını ya da tümünü "işaretle" dan önce alır; uygulamanın, herhangi bir verinin kalıp kalmadığını anlamak için SIOCATMARK işlemini kullanması gerekir. "Acil" (bant dışı) verilerden önce gelen normal veriler varsa, bu, sırasıyla alınır. (Bir `Receive` veya `ReceiveFrom` , bant dışı ve normal verilerin aynı çağrıda hiçbir şekilde karıştırılacağını unutmayın.) *LpArgument* parametresi, `DWORD` sonucu depolayan bir içinde işaret eder `IOCtl` .

Bu işlev, `ioctl()` Berkeley Sockets ' de kullanılan bir alt kümesidir. Özellikle, fiocatmark 'un desteklediği tek yuva düzeyi komutu olduğu için, FIOASYNC ile eşdeğer bir komut yoktur.

## <a name="casyncsocketlisten"></a><a name="listen"></a>CAsyncSocket:: Listen

Gelen bağlantı isteklerini dinlemek için bu üye işlevi çağırın.

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>Parametreler

*nConnectionBacklog*<br/>
Bekleyen bağlantıların sırasının büyüyebileceği maksimum uzunluk. Geçerli Aralık 1 ile 5 arasındadır.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEADDRINUSE kullanımdaki bir adresi dinlemek için bir girişimde bulunuldu.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAEINVAL yuva ile bağlanmamış `Bind` veya zaten bağlı.

- WSAEISCONN yuva zaten bağlı.

- WSAEMFILE daha fazla dosya tanımlayıcısı yok.

- WSAENOBUFS kullanılabilir arabellek alanı yok.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- WSAEOPNOTSUPP başvurulan yuva işlemi destekleyen bir türde değil `Listen` .

### <a name="remarks"></a>Açıklamalar

Bağlantıları kabul etmek için yuva ilk olarak oluşturulur `Create` , ile gelen bağlantılar için bir kapsam belirtilir `Listen` ve sonra bağlantılar kabul edilir `Accept` . `Listen`yalnızca bağlantıları destekleyen yuvalar için geçerlidir, diğer bir deyişle SOCK_STREAM türü. Bu yuva, gelen bağlantıların alındığı ve işlem tarafından bekleyen kabul edildiği "pasif" moda konur.

Bu işlev genellikle sunucular (veya bağlantıları kabul etmek isteyen uygulamalar) tarafından aynı anda birden fazla bağlantı isteğine sahip olabilecek bir şekilde kullanılır: bir bağlantı isteği tümüyle sıraya alınırsa, istemci, WSAECONNREFUSED göstergesi ile bir hata alır.

`Listen`kullanılabilir bağlantı noktası (tanımlayıcı) olmadığında, en çok işlevine devam etmeyi dener. Sıra boşaltılana kadar bağlantıları kabul edecektir. Bağlantı noktaları kullanılabilir hale gelirse, daha sonra `Listen` `Accept` kuyruğu geçerli veya en son "biriktirme listesi" olarak yeniden kuyruğa alarak gelen bağlantıları dinlemeyi sürdürür.

## <a name="casyncsocketm_hsocket"></a><a name="m_hsocket"></a>CAsyncSocket:: m_hSocket

Bu nesne tarafından kapsüllenmiş yuva için yuva tanıtıcısını içerir `CAsyncSocket` .

```
SOCKET m_hSocket;
```

## <a name="casyncsocketonaccept"></a><a name="onaccept"></a>CAsyncSocket:: OnAccept

Kendisini [kabul et](#accept) işlevini çağırarak, bekleyen bağlantı isteklerini kabul edebilecek bir dinleme yuvasına bildirmek için Framework tarafından çağırılır.

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuvada en son hata. Aşağıdaki hata kodları üye işlevi için geçerlidir `OnAccept` :

- **0** işlev başarıyla yürütüldü.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Windows Yuvaları: yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

## <a name="casyncsocketonclose"></a><a name="onclose"></a>CAsyncSocket:: OnClose

Bu yuvaya bağlı yuvanın işlemi tarafından kapandığını bildirmek için Framework tarafından çağırılır.

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuvada en son hata. Aşağıdaki hata kodları üye işlevi için geçerlidir `OnClose` :

- **0** işlev başarıyla yürütüldü.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAECONNRESET bağlantı uzak taraf tarafından sıfırlandı.

- WSAECONNABORTED bağlantı zaman aşımı veya başka bir hata nedeniyle sonlandırıldı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Windows Yuvaları: yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

## <a name="casyncsocketonconnect"></a><a name="onconnect"></a>CAsyncSocket:: OnConnect

Bu bağlantı yuvasını, başarılı veya hatalı olup olmadığını bu bağlama yuvasına bildirmek için Framework tarafından çağırılır.

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuvada en son hata. Aşağıdaki hata kodları üye işlevi için geçerlidir `OnConnect` :

- **0** işlev başarıyla yürütüldü.

- WSAEADDRINUSE belirtilen adres zaten kullanımda.

- WSAEADDRNOTAVAIL belirtilen adres yerel makineden kullanılamıyor.

- Belirtilen ailedeki WSAEAFNOSUPPORT adresleri bu yuvada kullanılamaz.

- WSAECONNREFUSED bağlanma girişimi zorla reddedildi.

- WSAEDESTADDRREQ hedef adresi gerekiyor.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni yanlış.

- WSAEINVAL yuva zaten bir adrese bağlıydı.

- WSAEISCONN yuva zaten bağlı.

- WSAEMFILE daha fazla dosya tanımlayıcısı yok.

- Bu konaktan, bu ana bilgisayardan, ağa ulaşmayı Şu anda ulaşılamıyor.

- WSAENOBUFS kullanılabilir arabellek alanı yok. Yuva bağlanamıyor.

- WSAENOTCONN yuva bağlı değil.

- WSAENOTSOCK tanımlayıcı, yuva değil bir dosyadır.

- WSAE-bağlantı kurma girişimi bağlantı kurulmadan zaman aşımına uğradı.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> [CSocket](../../mfc/reference/csocket-class.md)'de `OnConnect` bildirim işlevi hiçbir şekilde çağrılmaz. Bağlantılar için, `Connect` Bağlantı tamamlandığında (başarılı veya hatalı) geri döndürülecek bir çağrı yapmanız yeterlidir. Bağlantı bildirimlerinin nasıl işlendiği, MFC Uygulama ayrıntısıyla belirlenir.

Daha fazla bilgi için bkz. [Windows Yuvaları: yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

## <a name="casyncsocketonoutofbanddata"></a><a name="onoutofbanddata"></a>CAsyncSocket:: OnOutOfBandData

Alıcı yuvasına gönderme yuvasının göndermek için bant dışı veri olduğunu bildirmek üzere Framework tarafından çağırılır.

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuvada en son hata. Aşağıdaki hata kodları üye işlevi için geçerlidir `OnOutOfBandData` :

- **0** işlev başarıyla yürütüldü.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

### <a name="remarks"></a>Açıklamalar

Bant dışı veriler, SOCK_STREAM türünde her bağlantılı yuva çifti ile ilişkili mantıksal olarak bağımsız bir kanaldır. Kanal genellikle acil veri göndermek için kullanılır.

MFC bant dışı verileri destekler, ancak sınıfının kullanıcılarının `CAsyncSocket` kullanılması önerilmez. Daha kolay yol, bu tür verileri geçirmek için ikinci bir yuva oluşturmaktır. Bant dışı veriler hakkında daha fazla bilgi için bkz. [Windows Yuvaları: yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

## <a name="casyncsocketonreceive"></a><a name="onreceive"></a>CAsyncSocket:: OnReceive

Bu yuvaya, üye işlevi çağırarak alınabilecek arabellekte veri olduğunu bildirmek için Framework tarafından çağırılır `Receive` .

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuvada en son hata. Aşağıdaki hata kodları üye işlevi için geçerlidir `OnReceive` :

- **0** işlev başarıyla yürütüldü.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Windows Yuvaları: yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

## <a name="casyncsocketonsend"></a><a name="onsend"></a>CAsyncSocket:: OnSend

Şimdi üye işlevini çağırarak veri gönderebilecek yuvaya bildirimde bulunmak için Framework tarafından çağırılır `Send` .

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuvada en son hata. Aşağıdaki hata kodları üye işlevi için geçerlidir `OnSend` :

- **0** işlev başarıyla yürütüldü.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Windows Yuvaları: yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

## <a name="casyncsocketoperator-"></a><a name="operator_eq"></a>CAsyncSocket:: operator =

Nesnesine yeni bir değer atar `CAsyncSocket` .

```cpp
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Varolan bir `CAsyncSocket` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Varolan bir `CAsyncSocket` nesneyi başka bir nesneye kopyalamak için bu işlevi çağırın `CAsyncSocket` .

## <a name="casyncsocketoperator-socket"></a><a name="operator_socket"></a>CAsyncSocket:: operator yuvası

Nesnenin yuva tanıtıcısını almak için bu işleci kullanın `CAsyncSocket` .

```
operator SOCKET() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, yuva nesnesinin tanıtıcısı; Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

İşleyiciyi doğrudan Windows API 'Leri çağırmak için kullanabilirsiniz.

## <a name="casyncsocketreceive"></a><a name="receive"></a>CAsyncSocket:: Receive

Bir yuvadan veri almak için bu üye işlevini çağırın.

```
virtual int Receive(
    void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Gelen veriler için bir arabellek.

*nBufLen*<br/>
Bayt cinsinden *Lparabelleğe* uzunluğu.

*nFlags*<br/>
Çağrının yapılma yöntemini belirtir. Bu işlevin semantiği, yuva seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, C++ **veya** işleçle aşağıdaki değerlerden herhangi birini birleştirerek oluşturulur:

- Gelen verilere göz atın MSG_PEEK. Veriler arabelleğe kopyalanır ancak Giriş sırasından kaldırılmaz.

- Bant dışı verileri Işlemek MSG_OOB.

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir hata oluşursa, `Receive` alınan bayt sayısını döndürür. Bağlantı kapalıysa 0 döndürür. Aksi takdirde, SOCKET_ERROR değeri döndürülür ve [GetLastError](#getlasterror)çağırarak belirli bir hata kodu elde edilebilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAENOTCONN yuva bağlı değil.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi, ancak yuva SOCK_STREAM türünde değil.

- WSAESHUTDOWN yuva kapatıldı; `Receive` `ShutDown` *NNasıl* 0 veya 2 ' ye ayarlı olduktan sonra bir yuvada çağrılamaz.

- WSAEWOULDBLOCK yuva engellemeyen şekilde işaretlendi ve `Receive` işlem engellenir.

- WSAEMSGSIZE veri birimi, belirtilen arabelleğe sığamayacak kadar büyüktü ve kesildi.

- WSAEINVAL yuva ile bağlanmadı `Bind` .

- WSAECONNABORTED sanal devre, zaman aşımı veya başka bir hata nedeniyle sonlandırıldı.

- WSAECONNRESET sanal bağlantı hattı uzak taraf tarafından sıfırlandı.

### <a name="remarks"></a>Açıklamalar

Bu işlev bağlı akış veya veri birimi yuvaları için kullanılır ve gelen verileri okumak için kullanılır.

SOCK_STREAM türündeki yuvalar için, şu anda sağlanan arabellek boyutuna kadar çok bilgi döndürülür. Yuva bant dışı verilerin çevrimiçi alımı (yuva seçeneği SO_OOBINLINE) ve bant dışı verilerin okunmamışsa, yalnızca bant dışı veriler geri döndürülür. Uygulama, `IOCtlSIOCATMARK` bir veya daha fazla bant dışı veri okunana kadar devam edilip edilmeyeceğini anlamak için, seçeneğini veya [OnOutOfBandData verilerini](#onoutofbanddata) kullanabilir.

Veri birimi yuvaları için veriler, sağlanan arabelleğin boyutuna kadar ilk sıraya alınmış veri kaynağından ayıklanır. Veri birimi sağlanan arabellekten daha büyükse, arabellek veri biriminin ilk bölümüyle doldurulur, fazlalık veriler kaybolur ve `Receive` hata kodu, WSAEMSGSIZE olarak ayarlanan socket_error bir değeri döndürür. Yuvada hiçbir gelen veri yoksa, bir SOCKET_ERROR değeri, WSAEWOULDBLOCK olarak ayarlanan hata kodu ile döndürülür. [OnReceive](#onreceive) geri çağırma işlevi, ne zaman daha fazla verinin ulaştığında anlamak için kullanılabilir.

Yuva SOCK_STREAM türündedir ve uzak taraf bağlantıyı düzgün şekilde kapatmışsa, `Receive` 0 bayt alınan bir bütün olarak tamamlanır. Bağlantı sıfırlandığında, `Receive` WSAECONNRESET hatasıyla başarısız olur.

`Receive`Her [CAsyncSocket:: OnReceive](#onreceive) çağrıldığında yalnızca bir kez çağrılmalıdır.

### <a name="example"></a>Örnek

  [CAsyncSocket:: OnReceive](#onreceive)örneğine bakın.

## <a name="casyncsocketreceivefrom"></a><a name="receivefrom"></a>CAsyncSocket:: ReceiveFrom

Bir veri birimi almak için bu üye işlevi çağırın ve kaynak adresini [sockaddr](/windows/win32/winsock/sockaddr-2) yapısında veya *rSocketAddress*içinde depolayın.

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

*Lparabelleğe*<br/>
Gelen veriler için bir arabellek.

*nBufLen*<br/>
Bayt cinsinden *Lparabelleğe* uzunluğu.

*rSocketAddress*<br/>
`CString`Noktalı sayı IP adresi alan bir nesneye başvuru.

*rSocketPort*<br/>
Bir bağlantı noktası depolayan bir UINT öğesine başvuru.

*lpSockAddr*<br/>
Dönüş sırasında kaynak adresini tutan bir [sockaddr](/windows/win32/winsock/sockaddr-2) yapısına yönelik işaretçi.

*lpSockAddrLen*<br/>
Bayt cinsinden *lpSockAddr* içindeki kaynak adresinin uzunluğuna yönelik bir işaretçi.

*nFlags*<br/>
Çağrının yapılma yöntemini belirtir. Bu işlevin semantiği, yuva seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, C++ **veya** işleçle aşağıdaki değerlerden herhangi birini birleştirerek oluşturulur:

- Gelen verilere göz atın MSG_PEEK. Veriler arabelleğe kopyalanır ancak Giriş sırasından kaldırılmaz.

- Bant dışı verileri Işlemek MSG_OOB.

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir hata oluşursa, `ReceiveFrom` alınan bayt sayısını döndürür. Bağlantı kapalıysa 0 döndürür. Aksi takdirde, SOCKET_ERROR değeri döndürülür ve çağırarak belirli bir hata kodu elde edilebilir `GetLastError` . Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni geçersizdi: *lpSockAddr* buffer, eş adresini barındırmak için çok küçüktü.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAEINVAL yuva ile bağlanmadı `Bind` .

- WSAENOTCONN yuva bağlı değil (yalnızca SOCK_STREAM).

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi, ancak yuva SOCK_STREAM türünde değil.

- WSAESHUTDOWN yuva kapatıldı; `ReceiveFrom` `ShutDown` *NNasıl* 0 veya 2 ' ye ayarlı olduktan sonra bir yuvada çağrılamaz.

- WSAEWOULDBLOCK yuva engellemeyen şekilde işaretlendi ve `ReceiveFrom` işlem engellenir.

- WSAEMSGSIZE veri birimi, belirtilen arabelleğe sığamayacak kadar büyüktü ve kesildi.

- WSAECONNABORTED sanal devre, zaman aşımı veya başka bir hata nedeniyle sonlandırıldı.

- WSAECONNRESET sanal bağlantı hattı uzak taraf tarafından sıfırlandı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, (muhtemelen bağlı) bir yuvada gelen verileri okumak ve verilerin gönderildiği adresi yakalamak için kullanılır.

IPv6 adreslerini işlemek için [CAsyncSocket:: ReceiveFromEx](#receivefromex)kullanın.

SOCK_STREAM türündeki yuvalar için, şu anda sağlanan arabellek boyutuna kadar çok bilgi döndürülür. Yuva bant dışı verilerin çevrimiçi alımı (yuva seçeneği SO_OOBINLINE) ve bant dışı verilerin okunmamışsa, yalnızca bant dışı veriler geri döndürülür. Uygulama, `IOCtlSIOCATMARK` seçeneğini kullanabilir veya `OnOutOfBandData` daha fazla bant dışı veri okunana kadar devam edilip edilmeyeceğini tespit edebilir. *LpSockAddr* ve *lpSockAddrLen* parametreleri sock_stream yuvaları için yok sayılır.

Veri birimi yuvaları için veriler, sağlanan arabelleğin boyutuna kadar ilk sıraya alınmış veri kaynağından ayıklanır. Veri birimi sağlanan arabellekten daha büyükse, arabellek iletinin ilk kısmıyla doldurulur, fazlalık veriler kaybolur ve `ReceiveFrom` hata kodu, WSAEMSGSIZE olarak ayarlanan socket_error bir değeri döndürür.

*LpSockAddr* sıfır değilse ve yuva sock_dgram türünde ise, verileri gönderen yuvanın ağ adresi karşılık gelen [sockaddr](/windows/win32/winsock/sockaddr-2) yapısına kopyalanır. *LpSockAddrLen* tarafından işaret edilen değer bu yapının boyutuna başlatılır ve burada depolanan adresin gerçek boyutunu belirtmek için dönüşte değiştirilir. Yuvada hiçbir gelen veri yoksa, `ReceiveFrom` yuva engellenmediği takdirde arama verilerin gelmesini bekler. Bu durumda, bir SOCKET_ERROR değeri, WSAEWOULDBLOCK olarak ayarlanan hata kodu ile döndürülür. `OnReceive`Geri çağırma, ne zaman daha fazla veri ulaştığında anlamak için kullanılabilir.

Yuva SOCK_STREAM türündedir ve uzak taraf bağlantıyı düzgün şekilde kapatmışsa, `ReceiveFrom` 0 bayt alınan bir bütün olarak tamamlanır.

## <a name="casyncsocketreceivefromex"></a><a name="receivefromex"></a>CAsyncSocket:: ReceiveFromEx

Bir veri birimi almak için bu üye işlevi çağırın ve kaynak adresini [sockaddr](/windows/win32/winsock/sockaddr-2) yapısında veya *rSocketAddress* 'da (, IPv6 adreslerini işler) depolayın.

```
int ReceiveFromEx(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Gelen veriler için bir arabellek.

*nBufLen*<br/>
Bayt cinsinden *Lparabelleğe* uzunluğu.

*rSocketAddress*<br/>
`CString`Noktalı sayı IP adresi alan bir nesneye başvuru.

*rSocketPort*<br/>
Bir bağlantı noktası depolayan bir UINT öğesine başvuru.

*nFlags*<br/>
Çağrının yapılma yöntemini belirtir. Bu işlevin semantiği, yuva seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, C++ **veya** işleçle aşağıdaki değerlerden herhangi birini birleştirerek oluşturulur:

- Gelen verilere göz atın MSG_PEEK. Veriler arabelleğe kopyalanır ancak Giriş sırasından kaldırılmaz.

- Bant dışı verileri Işlemek MSG_OOB.

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir hata oluşursa, `ReceiveFromEx` alınan bayt sayısını döndürür. Bağlantı kapalıysa 0 döndürür. Aksi takdirde, SOCKET_ERROR değeri döndürülür ve çağırarak belirli bir hata kodu elde edilebilir `GetLastError` . Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni geçersizdi: *lpSockAddr* buffer, eş adresini barındırmak için çok küçüktü.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAEINVAL yuva ile bağlanmadı `Bind` .

- WSAENOTCONN yuva bağlı değil (yalnızca SOCK_STREAM).

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi, ancak yuva SOCK_STREAM türünde değil.

- WSAESHUTDOWN yuva kapatıldı; `ReceiveFromEx` `ShutDown` *NNasıl* 0 veya 2 ' ye ayarlı olduktan sonra bir yuvada çağrılamaz.

- WSAEWOULDBLOCK yuva engellemeyen şekilde işaretlendi ve `ReceiveFromEx` işlem engellenir.

- WSAEMSGSIZE veri birimi, belirtilen arabelleğe sığamayacak kadar büyüktü ve kesildi.

- WSAECONNABORTED sanal devre, zaman aşımı veya başka bir hata nedeniyle sonlandırıldı.

- WSAECONNRESET sanal bağlantı hattı uzak taraf tarafından sıfırlandı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, (muhtemelen bağlı) bir yuvada gelen verileri okumak ve verilerin gönderildiği adresi yakalamak için kullanılır.

Bu işlev, IPv6 adreslerini ve eski protokolleri de işleyeceğinden, [CAsyncSocket:: ReceiveFrom](#receivefrom) ile aynıdır.

SOCK_STREAM türündeki yuvalar için, şu anda sağlanan arabellek boyutuna kadar çok bilgi döndürülür. Yuva bant dışı verilerin çevrimiçi alımı (yuva seçeneği SO_OOBINLINE) ve bant dışı verilerin okunmamışsa, yalnızca bant dışı veriler geri döndürülür. Uygulama, `IOCtlSIOCATMARK` seçeneğini kullanabilir veya `OnOutOfBandData` daha fazla bant dışı veri okunana kadar devam edilip edilmeyeceğini tespit edebilir. *LpSockAddr* ve *lpSockAddrLen* parametreleri sock_stream yuvaları için yok sayılır.

Veri birimi yuvaları için veriler, sağlanan arabelleğin boyutuna kadar ilk sıraya alınmış veri kaynağından ayıklanır. Veri birimi sağlanan arabellekten daha büyükse, arabellek iletinin ilk kısmıyla doldurulur, fazlalık veriler kaybolur ve `ReceiveFromEx` hata kodu, WSAEMSGSIZE olarak ayarlanan socket_error bir değeri döndürür.

*LpSockAddr* sıfır değilse ve yuva sock_dgram türünde ise, verileri gönderen yuvanın ağ adresi karşılık gelen [sockaddr](/windows/win32/winsock/sockaddr-2) yapısına kopyalanır. *LpSockAddrLen* tarafından işaret edilen değer bu yapının boyutuna başlatılır ve burada depolanan adresin gerçek boyutunu belirtmek için dönüşte değiştirilir. Yuvada hiçbir gelen veri yoksa, `ReceiveFromEx` yuva engellenmediği takdirde arama verilerin gelmesini bekler. Bu durumda, bir SOCKET_ERROR değeri, WSAEWOULDBLOCK olarak ayarlanan hata kodu ile döndürülür. `OnReceive`Geri çağırma, ne zaman daha fazla veri ulaştığında anlamak için kullanılabilir.

Yuva SOCK_STREAM türündedir ve uzak taraf bağlantıyı düzgün şekilde kapatmışsa, `ReceiveFromEx` 0 bayt alınan bir bütün olarak tamamlanır.

## <a name="casyncsocketsend"></a><a name="send"></a>CAsyncSocket:: Send

Bağlı bir yuvada veri göndermek için bu üye işlevini çağırın.

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Aktarılacak verileri içeren bir arabellek.

*nBufLen*<br/>
Bayt cinsinden verilerin *lpbytes* cinsinden uzunluğu.

*nFlags*<br/>
Çağrının yapılma yöntemini belirtir. Bu işlevin semantiği, yuva seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, C++ **veya** işleçle aşağıdaki değerlerden herhangi birini birleştirerek oluşturulur:

- MSG_DONTROUTE, verilerin yönlendirmeye tabi olmaması gerektiğini belirtir. Bir Windows Sockets tedarikçisine bu bayrağı yok saymayı tercih edebilirsiniz.

- MSG_OOB bant dışı verileri (yalnızca SOCK_STREAM) gönderin.

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir hata oluşursa, `Send` gönderilen toplam karakter sayısını döndürür. (Bu, *nBufLen*tarafından belirtilen sayıdan daha az olabileceğini unutmayın.) Aksi takdirde, SOCKET_ERROR değeri döndürülür ve [GetLastError](#getlasterror)çağırarak belirli bir hata kodu elde edilebilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEACCES istenen adres bir yayın adresidir, ancak uygun bayrak ayarlanmadı.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAEFAULT, *Lparabelleğe* bağımsız değişkeni Kullanıcı adres alanının geçerli bir bölümünde değil.

- WSAENETRESET Windows Yuvaları uygulamasının bu uygulamayı bıraktığı için bağlantı sıfırlanmalıdır.

- WSAENOBUFS Windows Yuvaları uygulamasında bir arabellek kilitlenmesi bildiriliyor.

- WSAENOTCONN yuva bağlı değil.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi, ancak yuva SOCK_STREAM türünde değil.

- WSAESHUTDOWN yuva kapatıldı; `Send` `ShutDown` *NNasıl* 1 veya 2 ' ye ayarlı olduktan sonra bir yuvada çağrılamaz.

- WSAEWOULDBLOCK yuva engellemeyen şekilde işaretlendi ve istenen işlem engellenir.

- WSAEMSGSIZE yuva SOCK_DGRAM türündedir ve veri birimi Windows Yuvaları uygulamasının desteklediği en yüksek sayıdan daha büyük.

- WSAEINVAL yuva ile bağlanmadı `Bind` .

- WSAECONNABORTED sanal devre, zaman aşımı veya başka bir hata nedeniyle sonlandırıldı.

- WSAECONNRESET sanal bağlantı hattı uzak taraf tarafından sıfırlandı.

### <a name="remarks"></a>Açıklamalar

`Send`bağlı akış veya veri birimi yuvaları üzerine giden verileri yazmak için kullanılır. Veri birimi yuvaları için, bu, `iMaxUdpDg` tarafından döndürülen [wsaveri](/windows/win32/api/winsock2/ns-winsock2-wsadata) yapısındaki öğe tarafından verilen temel alt ağların maksimum IP paket boyutunu aşmamak zorunda değildir `AfxSocketInit` . Verilerin temel alınan protokol aracılığıyla otomatik olarak geçemeyeceği kadar uzunsa, WSAEMSGSIZE hatası ile döndürülür `GetLastError` ve hiçbir veri aktarılmaz.

Bir veri birimi yuvasının başarılı bir şekilde tamamlandığını, `Send` verilerin başarıyla teslim edildiğini belirtmediğini unutmayın.

`CAsyncSocket`Sock_stream türündeki nesnelerde, hem yerel hem de yabancı konaklarda arabellek kullanılabilirliğine bağlı olarak, yazılan bayt sayısı 1 ile istenen uzunluk arasında olabilir.

### <a name="example"></a>Örnek

  [CAsyncSocket:: OnSend](#onsend)örneğine bakın.

## <a name="casyncsocketsendto"></a><a name="sendto"></a>CAsyncSocket:: SendTo

Belirli bir hedefe veri göndermek için bu üye işlevi çağırın.

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

*Lparabelleğe*<br/>
Aktarılacak verileri içeren bir arabellek.

*nBufLen*<br/>
Bayt cinsinden verilerin *lpbytes* cinsinden uzunluğu.

*nHostPort*<br/>
Yuva uygulamasını tanımlayan bağlantı noktası.

*lpszHostAddress*<br/>
Bu nesnenin bağlandığı yuvanın ağ adresi: "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi noktalı bir sayı.

*nFlags*<br/>
Çağrının yapılma yöntemini belirtir. Bu işlevin semantiği, yuva seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, C++ **veya** işleçle aşağıdaki değerlerden herhangi birini birleştirerek oluşturulur:

- MSG_DONTROUTE, verilerin yönlendirmeye tabi olmaması gerektiğini belirtir. Bir Windows Sockets tedarikçisine bu bayrağı yok saymayı tercih edebilirsiniz.

- MSG_OOB bant dışı verileri (yalnızca SOCK_STREAM) gönderin.

*lpSockAddr*<br/>
Hedef yuvanın adresini içeren bir [sockaddr](/windows/win32/winsock/sockaddr-2) yapısına yönelik işaretçi.

*nSockAddrLen*<br/>
Bayt cinsinden *lpSockAddr* içindeki adresin uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir hata oluşursa, `SendTo` gönderilen toplam karakter sayısını döndürür. (Bu, *nBufLen*tarafından belirtilen sayıdan daha az olabileceğini unutmayın.) Aksi takdirde, SOCKET_ERROR değeri döndürülür ve [GetLastError](#getlasterror)çağırarak belirli bir hata kodu elde edilebilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEACCES istenen adres bir yayın adresidir, ancak uygun bayrak ayarlanmadı.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAEFAULT, *Lparabelleğe* veya *lpSockAddr* parametreleri Kullanıcı adres alanının bir parçası değil veya *lpSockAddr* bağımsız değişkeni çok küçük ( [sockaddr](/windows/win32/winsock/sockaddr-2) yapısının boyutundan daha az).

- WSAEINVAL ana bilgisayar adı geçersiz.

- WSAENETRESET Windows Yuvaları uygulamasının bu uygulamayı bıraktığı için bağlantı sıfırlanmalıdır.

- WSAENOBUFS Windows Yuvaları uygulamasında bir arabellek kilitlenmesi bildiriliyor.

- WSAENOTCONN yuva bağlı değil (yalnızca SOCK_STREAM).

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi, ancak yuva SOCK_STREAM türünde değil.

- WSAESHUTDOWN yuva kapatıldı; `SendTo` `ShutDown` *NNasıl* 1 veya 2 ' ye ayarlı olduktan sonra bir yuvada çağrılamaz.

- WSAEWOULDBLOCK yuva engellemeyen şekilde işaretlendi ve istenen işlem engellenir.

- WSAEMSGSIZE yuva SOCK_DGRAM türündedir ve veri birimi Windows Yuvaları uygulamasının desteklediği en yüksek sayıdan daha büyük.

- WSAECONNABORTED sanal devre, zaman aşımı veya başka bir hata nedeniyle sonlandırıldı.

- WSAECONNRESET sanal bağlantı hattı uzak taraf tarafından sıfırlandı.

- WSAEADDRNOTAVAIL belirtilen adres yerel makineden kullanılamıyor.

- Belirtilen ailedeki WSAEAFNOSUPPORT adresleri bu yuvada kullanılamaz.

- WSAEDESTADDRREQ hedef adresi gerekiyor.

- Bu konaktan, bu ana bilgisayardan, ağa ulaşmayı Şu anda ulaşılamıyor.

### <a name="remarks"></a>Açıklamalar

`SendTo`, veri birimi veya akış yuvaları üzerinde kullanılır ve bir yuvada giden verileri yazmak için kullanılır. Veri birimi yuvaları için, ilgili alt ağların maksimum IP paket boyutunu aşmamak için, bu, `iMaxUdpDg` [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)tarafından doldurulan [wsaveri](/windows/win32/api/winsock2/ns-winsock2-wsadata) yapısındaki öğe tarafından verilir. Verilerin temel alınan protokol aracılığıyla otomatik olarak geçemeyeceği kadar uzunsa, WSAEMSGSIZE hatası döndürülür ve hiçbir veri aktarılmaz.

Başarılı bir `SendTo` şekilde tamamlanmasının, verilerin başarıyla teslim edildiğini belirtdiğine unutmayın.

`SendTo`yalnızca bir SOCK_DGRAM yuvasında, *lpSockAddr* parametresi tarafından tanımlanan belirli bir yuvaya veri birimi göndermek için kullanılır.

Bir yayın göndermek için (yalnızca bir SOCK_DGRAM), *lpSockAddr* parametresindeki adresin, INADDR_BROADCAST özel IP adresi kullanılarak oluşturulması gerekir (Windows Yuvaları başlık dosyasında, WINSOCK olarak tanımlanmıştır. H) istenen bağlantı noktası numarasıyla birlikte. Ya da *lpszHostAddress* parametresi null ise, yuva yayın için yapılandırılır. Genellikle bir yayın veri biriminin parçalanma gerçekleşebileceği boyutu aşmasının (üstbilgiler hariç) 512 baytı aşmamalıdır.

IPv6 adreslerini işlemek için [CAsyncSocket:: SendToEx](#sendtoex)kullanın.

## <a name="casyncsocketsendtoex"></a><a name="sendtoex"></a>CAsyncSocket:: SendToEx

Belirli bir hedefe veri göndermek için bu üye işlevi çağırın (IPv6 adreslerini işler).

```
int SendToEx(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Aktarılacak verileri içeren bir arabellek.

*nBufLen*<br/>
Bayt cinsinden verilerin *lpbytes* cinsinden uzunluğu.

*nHostPort*<br/>
Yuva uygulamasını tanımlayan bağlantı noktası.

*lpszHostAddress*<br/>
Bu nesnenin bağlandığı yuvanın ağ adresi: "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi noktalı bir sayı.

*nFlags*<br/>
Çağrının yapılma yöntemini belirtir. Bu işlevin semantiği, yuva seçenekleri ve *nFlags* parametresi tarafından belirlenir. İkincisi, C++ **veya** işleçle aşağıdaki değerlerden herhangi birini birleştirerek oluşturulur:

- MSG_DONTROUTE, verilerin yönlendirmeye tabi olmaması gerektiğini belirtir. Bir Windows Sockets tedarikçisine bu bayrağı yok saymayı tercih edebilirsiniz.

- MSG_OOB bant dışı verileri (yalnızca SOCK_STREAM) gönderin.

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir hata oluşursa, `SendToEx` gönderilen toplam karakter sayısını döndürür. (Bu, *nBufLen*tarafından belirtilen sayıdan daha az olabileceğini unutmayın.) Aksi takdirde, SOCKET_ERROR değeri döndürülür ve [GetLastError](#getlasterror)çağırarak belirli bir hata kodu elde edilebilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEACCES istenen adres bir yayın adresidir, ancak uygun bayrak ayarlanmadı.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAEFAULT, *Lparabelleğe* veya *lpSockAddr* parametreleri Kullanıcı adres alanının bir parçası değil veya *lpSockAddr* bağımsız değişkeni çok küçük ( [sockaddr](/windows/win32/winsock/sockaddr-2) yapısının boyutundan daha az).

- WSAEINVAL ana bilgisayar adı geçersiz.

- WSAENETRESET Windows Yuvaları uygulamasının bu uygulamayı bıraktığı için bağlantı sıfırlanmalıdır.

- WSAENOBUFS Windows Yuvaları uygulamasında bir arabellek kilitlenmesi bildiriliyor.

- WSAENOTCONN yuva bağlı değil (yalnızca SOCK_STREAM).

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi, ancak yuva SOCK_STREAM türünde değil.

- WSAESHUTDOWN yuva kapatıldı; `SendToEx` `ShutDown` *NNasıl* 1 veya 2 ' ye ayarlı olduktan sonra bir yuvada çağrılamaz.

- WSAEWOULDBLOCK yuva engellemeyen şekilde işaretlendi ve istenen işlem engellenir.

- WSAEMSGSIZE yuva SOCK_DGRAM türündedir ve veri birimi Windows Yuvaları uygulamasının desteklediği en yüksek sayıdan daha büyük.

- WSAECONNABORTED sanal devre, zaman aşımı veya başka bir hata nedeniyle sonlandırıldı.

- WSAECONNRESET sanal bağlantı hattı uzak taraf tarafından sıfırlandı.

- WSAEADDRNOTAVAIL belirtilen adres yerel makineden kullanılamıyor.

- Belirtilen ailedeki WSAEAFNOSUPPORT adresleri bu yuvada kullanılamaz.

- WSAEDESTADDRREQ hedef adresi gerekiyor.

- Bu konaktan, bu ana bilgisayardan, ağa ulaşmayı Şu anda ulaşılamıyor.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, IPv6 adreslerini ve eski protokolleri işleyeceği için [CAsyncSocket:: SendTo](#sendto) ile aynıdır.

`SendToEx`, veri birimi veya akış yuvaları üzerinde kullanılır ve bir yuvada giden verileri yazmak için kullanılır. Veri birimi yuvaları için, ilgili alt ağların maksimum IP paket boyutunu aşmamak için, bu, `iMaxUdpDg` [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)tarafından doldurulan [wsaveri](/windows/win32/api/winsock2/ns-winsock2-wsadata) yapısındaki öğe tarafından verilir. Verilerin temel alınan protokol aracılığıyla otomatik olarak geçemeyeceği kadar uzunsa, WSAEMSGSIZE hatası döndürülür ve hiçbir veri aktarılmaz.

Başarılı bir `SendToEx` şekilde tamamlanmasının, verilerin başarıyla teslim edildiğini belirtdiğine unutmayın.

`SendToEx`yalnızca bir SOCK_DGRAM yuvasında, *lpSockAddr* parametresi tarafından tanımlanan belirli bir yuvaya veri birimi göndermek için kullanılır.

Bir yayın göndermek için (yalnızca bir SOCK_DGRAM), *lpSockAddr* parametresindeki adresin, INADDR_BROADCAST özel IP adresi kullanılarak oluşturulması gerekir (Windows Yuvaları başlık dosyasında, WINSOCK olarak tanımlanmıştır. H) istenen bağlantı noktası numarasıyla birlikte. Ya da *lpszHostAddress* parametresi null ise, yuva yayın için yapılandırılır. Genellikle bir yayın veri biriminin parçalanma gerçekleşebileceği boyutu aşmasının (üstbilgiler hariç) 512 baytı aşmamalıdır.

## <a name="casyncsocketsetsockopt"></a><a name="setsockopt"></a>CAsyncSocket:: SetSockOpt

Bir yuva seçeneği ayarlamak için bu üye işlevini çağırın.

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Parametreler

*nOptionName*<br/>
Değeri ayarlanacak yuva seçeneği.

*lpOptionValue*<br/>
İstenen seçeneğin değerinin sağlandığı arabelleğin bir işaretçisi.

*nOptionLen*<br/>
*LpOptionValue* arabelleğinin bayt cinsinden boyutu.

*nLevel*<br/>
Seçeneğin tanımlandığı düzey; desteklenen tek düzeyler SOL_SOCKET ve IPPROTO_TCP.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEFAULT *lpOptionValue* , işlem adres alanının geçerli bir bölümünde değil.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAEINVAL *nLevel* geçerli değil veya *lpOptionValue* 'daki bilgiler geçerli değil.

- SO_KEEPALIVE ayarlandığında, WSAENETRESET bağlantısı zaman aşımına uğradı.

- WSAENOPROTOOPT seçeneği bilinmiyor veya desteklenmiyor. Özellikle, SO_BROADCAST SOCK_STREAM türündeki yuvalarda desteklenmez SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER ve SO_OOBINLINE sock_dgram tür yuvalarda desteklenmez.

- SO_KEEPALIVE ayarlandığında, WSAENOTCONN bağlantısı sıfırlandı.

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

### <a name="remarks"></a>Açıklamalar

`SetSockOpt`herhangi bir durumda herhangi bir türde bir yuva ile ilişkili bir yuva seçeneği için geçerli değeri ayarlar. Seçenekler birden fazla protokol düzeyinde bulunabilir, ancak bu belirtim yalnızca en üst "yuva" düzeyinde bulunan seçenekleri tanımlar. Seçenekler, normal veri akışında çabuk veri alınıp alınmayacağı, yuvadan yayın iletilerinin gönderilip gönderilemediği gibi yuva işlemlerini etkiler.

İki tür yuva seçeneği vardır: bir özelliği veya davranışı etkinleştiren veya devre dışı bırakan Boole seçenekleri ve tamsayı değer veya yapı gerektiren seçenekler. Bir Boole seçeneğini etkinleştirmek için *lpOptionValue* sıfır dışında bir tamsayıya işaret eder. *LpOptionValue* seçeneğini sıfıra eşit bir tamsayı olarak devre dışı bırakmak için. *nOptionLen* , `sizeof(BOOL)` Boole seçeneklerine eşit olmalıdır. Diğer seçenekler için, *lpOptionValue* , seçenek için istenen değeri içeren tamsayı veya yapıya işaret eder ve *nOptionLen* tamsayı veya yapının uzunluğudur.

SO_LINGER, gönderilmemiş veriler bir yuva üzerinde sıraya alınmışsa ve bu `Close` işlev yuvayı kapatmak için çağrıldığında gerçekleştirilecek eylemi denetler.

Varsayılan olarak, bir yuva zaten kullanımda olan bir yerel adrese bağlanamaz (bkz. [bağlama](#bind)). Ancak, bazen bu şekilde bir adresin "yeniden kullanılması" istenebilir. Her bağlantı yerel ve uzak adreslerin birleşimi tarafından benzersiz bir şekilde tanımlandığı için, uzak adresler farklı olduğu sürece, aynı yerel adrese bağlı iki yuva olan bir sorun yoktur.

`Bind`İstenen adres başka bir yuva tarafından zaten kullanımda olduğundan, Windows Sockets uygulamasına bir yuvanın çağrısına izin verilmediğini bildirmek için, uygulamanın çağrıyı vermeden önce yuva için SO_REUSEADDR yuva seçeneğini ayarlaması gerekir `Bind` . Seçeneğinin yalnızca çağrının sırasında yorumlandığını unutmayın `Bind` : Bu nedenle, var olan bir adrese bağlanmayacak bir yuva üzerinde seçeneğini ayarlamak ve `Bind` çağrının bu ya da başka bir yuva üzerinde hiçbir etkisi olmadığında bu seçeneğin ayarlanması veya sıfırlanması gerekmez.

Uygulama, Windows Yuvaları uygulamasının, SO_KEEPALIVE yuva seçeneğini açarak Iletim Denetimi Protokolü (TCP) bağlantılarında "canlı tut" paketlerinin kullanımını etkinleştirmesine izin verebilir. Bir Windows Sockets uygulamasının etkin tutma kullanımını desteklememesi gerekir: Eğer ise, kesin anlambilim uygulamaya özgüdür, ancak RFC 1122: "Internet ana bilgisayarları için gereksinimler" Iletişim katmanları için 4.2.3.6 bölümüne uymalıdır. "Etkin tut" sonucu olarak bir bağlantı bırakıldığında, WSAENETRESET hata kodu yuva üzerinde devam eden çağrılara döndürülür ve sonraki çağrılar WSAENOTCONN ile başarısız olur.

TCP_NODELAY seçeneği, Nagle algoritmasını devre dışı bırakır. Nagle algoritması, bir ana bilgisayar tarafından gönderilen küçük paketlerin sayısını azaltmak için kullanılır ve tam boyutlu bir paket gönderileene kadar bildirilmemiş gönderme verilerini arabelleğe alabilir. Ancak bazı uygulamalarda bu algoritma performansı belirleyebilir ve TCP_NODELAY devre dışı bırakmak için kullanılabilir. Uygulama yazarları TCP_NODELAY ayarlamamalıdır, TCP_NODELAY çünkü bunun etkisi, ağ performansı üzerinde önemli ölçüde olumsuz bir etkiye sahip olabilir. TCP_NODELAY, düzeyi IPPROTO_TCP kullanan tek desteklenen yuva seçeneğidir; diğer tüm seçenekler düzey SOL_SOCKET kullanır.

Bazı Windows Yuvaları uygulamaları, SO_DEBUG seçeneği bir uygulama tarafından ayarlandıysa çıkış hata ayıklama bilgilerini sağlar.

Aşağıdaki seçenekler için desteklenir `SetSockOpt` . Türü, *lpOptionValue*tarafından belirtilen veri türünü tanımlar.

|Değer|Tür|Anlamı|
|-----------|----------|-------------|
|SO_BROADCAST|BOOL|Yuva üzerinde yayın iletilerinin aktarımına izin verin.|
|SO_DEBUG|BOOL|Hata ayıklama bilgilerini kaydedin.|
|SO_DONTLINGER|BOOL|`Close`Gönderilmemiş verilerin gönderilmesini beklemeyi engellemez. Bu seçeneğin ayarlanması, sıfıra ayarlanmış SO_LINGER ayarlama ile eşdeğerdir `l_onoff` .|
|SO_DONTROUTE|BOOL|Yönlendirmeyin: doğrudan arabirime gönderin.|
|SO_KEEPALIVE|BOOL|Canlı tutmayı gönder.|
|SO_LINGER|`struct LINGER`|`Close`Gönderilmemiş veriler varsa açık.|
|SO_OOBINLINE|BOOL|Normal veri akışında bant dışı veri alın.|
|SO_RCVBUF|**int**|Alma için arabellek boyutunu belirtin.|
|SO_REUSEADDR|BOOL|Yuvanın zaten kullanımda olan bir adrese bağlanmasına izin verin. (Bkz. [bind](#bind).)|
|SO_SNDBUF|**int**|Gönderme için arabellek boyutunu belirtin.|
|TCP_NODELAY|BOOL|Birleştirme gönderme için Nagle algoritmasını devre dışı bırakır.|

İçin desteklenmeyen Berkeley yazılım dağıtımı (BSD) seçenekleri `SetSockOpt` şunlardır:

|Değer|Tür|Anlamı|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Yuva dinliyor|
|SO_ERROR|**int**|Hata durumunu alın ve temizleyin.|
|SO_RCVLOWAT|**int**|Düşük su işareti al.|
|SO_RCVTIMEO|**int**|Alma zaman aşımı|
|SO_SNDLOWAT|**int**|Düşük su işareti gönderin.|
|SO_SNDTIMEO|**int**|Gönderme zaman aşımı.|
|SO_TYPE|**int**|Yuva türü.|
|IP_OPTIONS||IP üstbilgisindeki seçenek alanını ayarla.|

## <a name="casyncsocketshutdown"></a><a name="shutdown"></a>CAsyncSocket:: kapanıyor

Yuva üzerinde gönderme, alma veya her ikisini devre dışı bırakmak için bu üye işlevini çağırın.

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>Parametreler

*NNasıl yapılır?*<br/>
Aşağıdaki numaralandırılmış değerleri kullanarak, hangi tür işlemleri artık izin verileceğini açıklayan bir bayrak:

- **Alır = 0**

- **gönderme = 1**

- **Her iki = 2**

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu, [GetLastError](#getlasterror)çağırarak alınabilir. Bu üye işlevi için aşağıdaki hatalar geçerlidir:

- WSANOTıNITIAL, bu API kullanılmadan önce başarılı bir [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) gerçekleşmelidir.

- Windows Yuvaları uygulamasının wsa, ağ alt sisteminin başarısız olduğunu algıladı.

- WSAEINVAL *NNasıl* geçerli değildir.

- WSAEINPROGRESS bir Windows Yuvaları engelleme işlemi devam ediyor.

- WSAENOTCONN yuva bağlı değil (yalnızca SOCK_STREAM).

- WSAENOTSOCK, tanımlayıcı bir yuva değil.

### <a name="remarks"></a>Açıklamalar

`ShutDown`, alma, iletim veya her ikisini devre dışı bırakmak için tüm yuva türlerinde kullanılır. *NNasıl* 0 olursa, yuvada sonraki alma izni engellenir. Bu, alt protokol katmanları üzerinde hiçbir etkiye sahip değildir.

Iletim Denetim Protokolü (TCP) için, TCP penceresi değiştirilmez ve gelen veriler pencere tükenene kadar kabul edilir (ancak onaylanmaz). Kullanıcı Datagram Protokolü (UDP) için, gelen veri birimleri kabul edilir ve kuyruğa alınır. Hiçbir durumda, bir ıCMP hata paketi oluşturulur. *NNasıl* 1 olursa, sonraki gönderime izin verilmez. TCP yuvaları için bir FIN gönderilir. *NNasıl yapılır* 2 ayarı, yukarıda açıklandığı gibi hem gönderme hem de alma özelliğini devre dışı bırakır

`ShutDown`Yuvayı kapatmadığını ve yuvaya eklenen kaynakların, çağrılana kadar serbest olamayacağını unutmayın `Close` . Bir uygulamanın kapatıldıktan sonra bir yuvayı yeniden kullanabilme güvenmemelidir. Özellikle, `Connect` Bu tür bir yuvada kullanımını desteklemek Için Windows Yuvaları uygulamasının kullanılması gerekmez.

### <a name="example"></a>Örnek

  [CAsyncSocket:: OnReceive](#onreceive)örneğine bakın.

## <a name="casyncsocketsocket"></a><a name="socket"></a>CASyncSocket:: soketi

Bir yuva tutamacı ayırır.

```
BOOL Socket(
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    int nProtocolType = 0,
    int nAddressFormat = PF_INET);
```

### <a name="parameters"></a>Parametreler

*nSocketType*<br/>
`SOCK_STREAM`Veya belirtir `SOCK_DGRAM` .

*Elvent*<br/>
Uygulamanın ilgilendiği ağ olaylarının birleşimini belirten bir bit maskesi.

- `FD_READ`: Okuma için hazır olma bildirimini almak ister.

- `FD_WRITE`: Yazma hazırlığı için bildirim almak istiyorsanız.

- `FD_OOB`: Bant dışı verilerin gelişmesi hakkında bildirim almak ister.

- `FD_ACCEPT`: Gelen bağlantılar için bildirim almak istiyorsanız.

- `FD_CONNECT`: Tamamlanmış bağlantı bildirimini almak istiyor.

- `FD_CLOSE`: Yuva kapanışının bildirimini almak ister.

*nProtocolType*<br/>
Belirtilen adres ailesine özgü yuvada kullanılacak protokol.

*nAddressFormat*<br/>
Adres ailesi belirtimi.

### <a name="return-value"></a>Dönüş Değeri

`TRUE`Hatada başarılı ' i döndürür `FALSE` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir yuva tanıtıcısı ayırır. Yuvayı belirtilen bir adrese bağlamak için [CAsyncSocket:: bind](#bind) çağrısını yapmaz, bu yüzden `Bind` yuvayı belirtilen bir adrese bağlamak için daha sonra çağrı yapmanız gerekir. [CAsyncSocket:: setsockopt](#setsockopt) ' i, bağlanmadan önce yuva seçeneğini ayarlamak için kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSocket Sınıfı](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile sınıfı](../../mfc/reference/csocketfile-class.md)
