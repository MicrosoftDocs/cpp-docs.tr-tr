---
title: CAsyncSocket sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: ef486e653eaf78914ea25663e0c1ab744ab30cd4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260016"
---
# <a name="casyncsocket-class"></a>CAsyncSocket sınıfı

Bir Windows yuvasını temsil eder; ağ iletişimi bir uç nokta.

## <a name="syntax"></a>Sözdizimi

```
class CAsyncSocket : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|Oluşturur bir `CAsyncSocket` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAsyncSocket::Accept](#accept)|Bir yuva bağlantısı kabul eder.|
|[CAsyncSocket::AsyncSelect](#asyncselect)|Yuva için istekleri olay bildirimi.|
|[CAsyncSocket::Attach](#attach)|Ekler için yuva tanıtıcı bir `CAsyncSocket` nesne.|
|[CAsyncSocket::Bind](#bind)|Yerel Adres yuvası ile ilişkilendirir.|
|[CAsyncSocket::Close](#close)|Yuva kapatır.|
|[CAsyncSocket::Connect](#connect)|Bir eş yuva bağlantı kurar.|
|[CAsyncSocket::Create](#create)|Bir yuva oluşturur.|
|[CAsyncSocket::Detach](#detach)|Bir yuva tanıtıcıdan ayırır bir `CAsyncSocket` nesne.|
|[CAsyncSocket::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CAsyncSocket` bir yuva belirli nesne.|
|[CAsyncSocket::GetLastError](#getlasterror)|Hata durumu için son işlemi başarısız oldu alır.|
|[CAsyncSocket::GetPeerName](#getpeername)|Yuvanın bağlanacağı eş yuva adresini alır.|
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Yuva bağlı (IPv6 adresleri tutamaçlar) olduğu eş yuva adresini alır.|
|[CAsyncSocket::GetSockName](#getsockname)|Bir yuva yerel adı alır.|
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Bir yuva (IPv6 adresleri tutamaçlar) yerel adı alır.|
|[CAsyncSocket::GetSockOpt](#getsockopt)|Bir yuva seçeneği alır.|
|[CAsyncSocket::IOCtl](#ioctl)|Yuva modunu denetler.|
|[CAsyncSocket::Listen](#listen)|Gelen bağlantı isteklerini dinlemek için bir yuva oluşturur.|
|[CAsyncSocket::Receive](#receive)|Veri yuvadan alır.|
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Bir veri birimi alır ve kaynak adresi depolar.|
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Bir veri birimi alır ve kaynak adresi (IPv6 adresleri tutamaçlar) depolar.|
|[CAsyncSocket::Send](#send)|Bağlanmış bir yuva için verileri gönderir.|
|[CAsyncSocket::SendTo](#sendto)|Verileri belirli bir hedefe gönderir.|
|[CAsyncSocket::SendToEx](#sendtoex)|Verileri belirli bir hedefe (IPv6 adresleri tutamaçlar) gönderir.|
|[CAsyncSocket::SetSockOpt](#setsockopt)|Bir yuva seçeneği ayarlar.|
|[CAsyncSocket::ShutDown](#shutdown)|Devre dışı bırakır `Send` ve/veya `Receive` yuva çağırır.|
|[CASyncSocket::Socket](#socket)|Socket tanıtıcısı ayırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAsyncSocket::OnAccept](#onaccept)|Çağırarak bağlantı isteklerini kabul edebilirsiniz dinleme bir yuva bildirir `Accept`.|
|[CAsyncSocket::OnClose](#onclose)|Yuva kendisine bağlı bir yuva kapatıldı bildirir.|
|[CAsyncSocket::OnConnect](#onconnect)|Bağlantı bir yuva bağlantı denemesi olup başarıyla veya hatayla, tamamlandığını bildirir.|
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|Bir alıcı yuva yuva, genellikle acil bir ileti okumak için bant dışı veri olduğunu bildirir.|
|[CAsyncSocket::OnReceive](#onreceive)|Dinleme yuva çağırarak alınacak veri olduğunu bildirir `Receive`.|
|[CAsyncSocket::OnSend](#onsend)|Bu çağrı yaparak veri gönderebilir yuva bildirir `Send`.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAsyncSocket::operator =](#operator_eq)|Yeni bir değer atar bir `CAsyncSocket` nesne.|
|[CAsyncSocket::operator YUVA](#operator_socket)|YUVA tanıtıcısını almak için bu işleci kullanın `CAsyncSocket` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAsyncSocket::m_hSocket](#m_hsocket)|Şuna bağlı SOCKET tanıtıcısı gösterir `CAsyncSocket` nesne.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CAsyncSocket` Windows yuva işlevleri programcılara Windows Sockets MFC ile birlikte kullanmak istediğiniz bir nesne odaklı Özet sağlayan API kapsüller.

Bu sınıf, ağ iletişimi anladığınızı varsayımına dayanır. Engelleme, bayt sırası farklar işlenmesinden sorumludur ve Unicode ve çok baytlı karakter arasında dönüştürmeler (MBCS) dizeleri ayarlayın. Bu sorunları sizin yerinize yönetir daha kullanışlı bir arabirim istiyorsanız bkz [CSocket](../../mfc/reference/csocket-class.md).

Kullanılacak bir `CAsyncSocket` nesne, kendi oluşturucusunu'ı çağırın [Oluştur](#create) temel alınan yuva işleyicisini oluşturmak için işlevi (türü `SOCKET`), kabul edilen yuvalarda hariç. Bir sunucu yuva çağrısı için [dinleme](#listen) üye işlevini ve bir istemci yuvası çağrısı için [Bağlan](#connect) üye işlevi. Sunucu yuvası çağırmalıdır [kabul](#accept) işlevi bağlantı isteği alır almaz. Kalan kullanın `CAsyncSocket` yuva arasındaki iletişimleri gerçekleştirmek için işlevleri. Tamamlandıktan sonra yok `CAsyncSocket` yığında oluşturduysanız nesne; yıkıcı otomatik olarak çağırır [Kapat](#close) işlevi. YUVA veri türü makalesinde açıklanan [Windows Yuvaları: Arka plan](../../mfc/windows-sockets-background.md).

> [!NOTE]
>  Statik olarak bağlı bir MFC uygulamasında İkincil iş parçacıklarındaki MFC Yuvaları kullanılırken çağırmalısınız `AfxSocketInit` yuva kitaplıklarını başlatma yuva kullanan her bir iş parçacığı. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığında çağrılır.

Daha fazla bilgi için [Windows Yuvaları: Sınıf Casyncsocket'ini kullanma](../../mfc/windows-sockets-using-class-casyncsocket.md) ve ilgili makaleler. yanı [Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxsock.h

##  <a name="accept"></a>  CAsyncSocket::Accept

Bir yuva bağlantı kabul etmek için bu üye işlevini çağırın.

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>Parametreler

*rConnectedSocket*<br/>
Bağlantı için kullanılabilir olan yeni bir yuva tanımlayan bir başvuru.

*lpSockAddr*<br/>
Bir işaretçi bir [SOCKADDR](/windows/desktop/winsock/sockaddr-2) bağlanma adresi alan yapısı yuva ağda bilinen. Tam biçimi *lpSockAddr* bağımsız değişkeni, yuva oluşturulduğunda oluşturulan Adres ailesi tarafından belirlenir. Varsa *lpSockAddr* ve/veya *lpSockAddrLen* NULL olarak kabul edilen yuva bir uzak adres hakkında bilgi verilir eşitse.

*lpSockAddrLen*<br/>
Uzunluğu adresini bir işaretçiye *lpSockAddr* bayt. *LpSockAddrLen* değeri sonuç parametresi: başlangıçta tarafından işaret edilen alan miktarı içermelidir *lpSockAddr*; sonrasında gerçek uzunluğunu (bayt cinsinden) döndürülen adresini içerecektir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni çok küçük (boyutundan daha küçük bir [SOCKADDR](/windows/desktop/winsock/sockaddr-2) yapısı).

- WSAEINPROGRESS engelleme Windows Sockets çağırmak bir işlemi devam ediyor.

- WSAEINVAL `Listen` kabul etmek için çağrılan önceki değildi.

- WSAEMFILE sıranın kabul etmek için giriş boş olduğundan ve hiçbir tanımlayıcıları vardır.

- WSAENOBUFS Hayır arabellek alanı kullanılabilir.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- WSAEOPNOTSUPP başvurulan yuva bağlantı dayalı hizmet destekleyen bir türü değil.

- Yuva işaretlenmiş WSAEWOULDBLOCK olarak sayıda ve kabul edilmesi için hiçbir bağlantı yok.

### <a name="remarks"></a>Açıklamalar

Bu yordam bağlantıları bekleyen sırasındaki ilk bağlantı ayıklar, bu Yuva aynı özelliklere sahip yeni bir yuva oluşturur ve ekler *rConnectedSocket*. Hiçbir bekleyen bağlantılar sırada, mevcut olması durumunda `Accept` sıfır döndürür ve `GetLastError` bir hata döndürür. Kabul edilen yuva ( *rConnectedSocket)* daha fazla bağlantı kabul etmek için kullanılamaz. Özgün yuva açık ve dinleme kalır.

Bağımsız değişken *lpSockAddr* yuva bağlantı adresi ile doldurulan bir sonuç iletişimleri katmanına bilinen parametredir. `Accept` Yuva bağlantı tabanlı türleri SOCK_STREAM gibi kullanılır.

##  <a name="asyncselect"></a>  CAsyncSocket::AsyncSelect

Bir yuva için olay bildirimini istemek için bu üye işlevini çağırın.

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parametreler

*lEvent*<br/>
Ağ olayları, uygulama, ilgileniyor birleşimi belirten bir bit maskesi.

- FD_READ okumak için hazır olma durumu bildirim almak istiyorsanız.

- FD_WRITE veri okumak kullanılabilir olduğunda bildirim almak istiyor.

- Bant dışı veri bildirim almak için FD_OOB istersiniz.

- FD_ACCEPT gelen bağlantıları bildirim almak istiyor.

- FD_CONNECT bağlantı sonuçları bildirim almak istiyorsanız.

- FD_CLOSE bir eş tarafından bir yuva kapatıldığında bildirim almak istiyor.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEINVAL gösterir, belirtilen parametrelerinden biri geçersiz.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

### <a name="remarks"></a>Açıklamalar

Bu işlev için yuva MFC geri çağırma bildirimi işlev çağrılacak belirtmek için kullanılır. `AsyncSelect` otomatik olarak bu yuva için sayıda modunu ayarlar. Daha fazla bilgi için bkz [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="attach"></a>  CAsyncSocket::Attach

Eklemek için bu üye işlevi çağrısı *hSocket* işlemek için bir `CAsyncSocket` nesne.

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parametreler

*hSocket*<br/>
Bir yuva için bir tanıtıcı içerir.

*lEvent*<br/>
Ağ olayları, uygulama, ilgileniyor birleşimi belirten bir bit maskesi.

- FD_READ okumak için hazır olma durumu bildirim almak istiyorsanız.

- FD_WRITE veri okumak kullanılabilir olduğunda bildirim almak istiyor.

- Bant dışı veri bildirim almak için FD_OOB istersiniz.

- FD_ACCEPT gelen bağlantıları bildirim almak istiyor.

- FD_CONNECT bağlantı sonuçları bildirim almak istiyorsanız.

- FD_CLOSE bir eş tarafından bir yuva kapatıldığında bildirim almak istiyor.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır.

### <a name="remarks"></a>Açıklamalar

SOCKET tanıtıcısı nesnenin içinde depolanan [m_hSocket](#m_hsocket) veri üyesi.

##  <a name="bind"></a>  CAsyncSocket::Bind

Yerel Adres yuvası ile ilişkilendirmek için bu üye işlevini çağırın.

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
Ağ adresi "128.56.22.8" gibi noktalı bir sayı olabilir. Bu parametresi için dize NULL geçirme `CAsyncSocket` örneği istemci etkinliği tüm ağ arabirimleri üzerinde dinler.

*lpSockAddr*<br/>
Bir işaretçi bir [SOCKADDR](/windows/desktop/winsock/sockaddr-2) bu yuva için atanacak adresini içeren yapısı.

*nSockAddrLen*<br/>
Adres uzunluğunu *lpSockAddr* bayt.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEADDRINUSE belirtilen adresi zaten kullanılıyor. (SO_REUSEADDR yuva seçeneği altında görmek [SetSockOpt](#setsockopt).)

- WSAEFAULT *nSockAddrLen* bağımsız değişkeni çok küçük (boyutundan daha küçük bir [SOCKADDR](/windows/desktop/winsock/sockaddr-2) yapısı).

- WSAEINPROGRESS engelleme Windows Sockets çağırmak bir işlemi devam ediyor.

- Belirtilen adres ailesi WSAEAFNOSUPPORT Bu bağlantı noktası tarafından desteklenmiyor.

- WSAEINVAL yuva için bir adres zaten bağlı.

- WSAENOBUFS değil yeterince arabelleği kullanılabilir bağlantı sayısı çok fazla.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

### <a name="remarks"></a>Açıklamalar

Bu yordam bir bağlantısız veri birimi veya akış yuva önce kullanılan sonraki `Connect` veya `Listen` çağırır. Bağlantı isteklerini kabul etmeden önce bir dinleme sunucu yuvası bir bağlantı noktası numarası seçin ve onu Windows yuvalarına çağırarak bilinen olmanız gerekir `Bind`. `Bind` adlandırılmamış bir yuva için bir yerel ad atayarak yuva yerel ilişkisini (ana bilgisayar adresi/bağlantı noktası numarası) oluşturur.

##  <a name="casyncsocket"></a>  CAsyncSocket::CAsyncSocket

Boş yuva bir nesne oluşturur.

```
CAsyncSocket();
```

### <a name="remarks"></a>Açıklamalar

Nesne oluşturduktan sonra çağırmanız gerekir, `Create` YUVA veri yapısını oluşturmanız ve adresini bağlamak için üye işlevi. (Sunucu tarafında dinleme yuva kullanmak için bir yuva oluşturduğunda Windows Sockets iletişim `Accept` çağrısı, arama `Create` bu yuva için.)

##  <a name="close"></a>  CAsyncSocket::Close

Yuva kapatır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla başvuruları WSAENOTSOCK hatasıyla başarısız olur, bu işlev yuva tanımlayıcısı serbest bırakır. Bu temel alınan yuva son başvuruysa ise, kuyruğa alınmış verilere ve ilişkili adlandırma bilgileri atılır. Yuva nesnenin yıkıcı çağrıları `Close` sizin için.

İçin `CAsyncSocket`, ancak `CSocket`, semantiği `Close` yuva seçenekleri SO_LINGER ve SO_DONTLINGER etkilenir. Daha fazla bilgi için bkz: üye işlev `GetSockOpt`.

##  <a name="connect"></a>  CAsyncSocket::Connect

Bir bağlantısız akış veya veri birimi yuva bağlantı kurmak için bu üye işlevini çağırın.

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
Bu nesne bağlı yuva ağ adresi: "ftp.microsoft.com" veya "128.56.22.8" gibi noktalı bir sayı gibi bir makine adı.

*nHostPort*<br/>
Yuva uygulamasını tanımlayan bağlantı noktası.

*lpSockAddr*<br/>
Bir işaretçi bir [SOCKADDR](/windows/desktop/winsock/sockaddr-2) bağlı bir yuva adresini içeren yapısı.

*nSockAddrLen*<br/>
Adres uzunluğunu *lpSockAddr* bayt.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Bu hata kodu WSAEWOULDBLOCK gösterir ve uygulamanızı geçersiz kılınabilir geri aramaları kullanıyorsa, uygulamanızı alacak bir `OnConnect` bağlanma işlemi tamamlandığında, ileti. Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEADDRINUSE belirtilen adresi zaten kullanılıyor.

- WSAEINPROGRESS engelleme Windows Sockets çağırmak bir işlemi devam ediyor.

- Yerel makineden WSAEADDRNOTAVAIL belirtilen adresi kullanılamaz.

- Bu yuva ile belirtilen ailesindeki WSAEAFNOSUPPORT adresleri kullanılamaz.

- WSAECONNREFUSED bağlanma girişimi reddedildi.

- WSAEDESTADDRREQ bir hedef adresi gereklidir.

- WSAEFAULT *nSockAddrLen* bağımsız değişkeni yanlış.

- Ana bilgisayar adresi WSAEINVAL geçersiz.

- Yuva WSAEISCONN zaten bağlı.

- WSAEMFILE Hayır, daha fazla dosya tanımlayıcısı kullanılabilir.

- WSAENETUNREACH ağ şu anda bu konaktan erişilemiyor.

- WSAENOBUFS Hayır arabellek alanı kullanılabilir. Yuva bağlanamaz.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- WSAETIMEDOUT bağlanma girişimleri bağlantı kurmadan zaman aşımına uğradı.

- Yuva işaretlenmiş WSAEWOULDBLOCK olarak sayıda ve bağlantı hemen tamamlanamıyor.

### <a name="remarks"></a>Açıklamalar

Yuva ilişkisiz ise, benzersiz değerler yerel bir ilişkilendirme için sistem tarafından atanır ve yuva olarak işaretlenmiş bağlı. Unutmayın tümüyle sıfıra adres alanıdır adı yapısı `Connect` sıfır döndürür. Genişletilmiş hata bilgilerini almak için arama `GetLastError` üye işlevi.

Akış yuvaları (SOCK_STREAM türü) için etkin bir bağlantısı yabancı bir konağa başlatılır. Yuva çağrısı başarıyla tamamlandığında, yuva veri gönderme ve alma hazırdır.

Bir veri birimi yuva (SOCK_DGRAM türü) için varsayılan hedef, sonraki üzerinde kullanılacak ayarlandıktan `Send` ve `Receive` çağırır.

##  <a name="create"></a>  CAsyncSocket::Create

Çağrı `Create` sonra Windows yuva oluşturma ve bunu eklemek için bir yuva nesnesi oluşturulurken, üye işlevi.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Parametreler

*nSocketPort*<br/>
Bir bağlantı noktası seçmek için Windows yuva istiyorsanız socket veya 0 ile kullanılmak üzere bir bilinen bağlantı noktası.

*nSocketType*<br/>
SOCK_STREAM veya SOCK_DGRAM.

*lEvent*<br/>
Ağ olayları, uygulama, ilgileniyor birleşimi belirten bir bit maskesi.

- FD_READ okumak için hazır olma durumu bildirim almak istiyorsanız.

- Yazma için hazırlık bildirim almak için FD_WRITE istersiniz.

- Bant dışı veri bildirim almak için FD_OOB istersiniz.

- FD_ACCEPT gelen bağlantıları bildirim almak istiyor.

- FD_CONNECT tamamlanmış bağlantı bildirim almak istiyor.

- FD_CLOSE yuva kapatma bildirim almak istiyor.

*lpszSockAddress*<br/>
Bağlı bir yuva, noktalı bir sayı "128.56.22.8" gibi ağ adresini içeren bir dize işaretçisi. Bu parametresi için dize NULL geçirme `CAsyncSocket` örneği istemci etkinliği tüm ağ arabirimleri üzerinde dinler.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- Belirtilen adres ailesi WSAEAFNOSUPPORT desteklenmiyor.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- WSAEMFILE Hayır, daha fazla dosya tanımlayıcısı kullanılabilir.

- WSAENOBUFS Hayır arabellek alanı kullanılabilir. Yuva oluşturulamadı.

- Belirtilen bağlantı noktası WSAEPROTONOSUPPORT desteklenmiyor.

- Belirtilen bağlantı noktası WSAEPROTOTYPE yanlış bu yuva için türüdür.

- Bu adres ailesinde WSAESOCKTNOSUPPORT belirtilen yuva türü desteklenmiyor.

### <a name="remarks"></a>Açıklamalar

`Create` çağrıları [yuva](#socket) ve başarılı olursa çağrı [bağlama](#bind) belirtilen adresine yuvası bağlama. Aşağıdaki yuva türleri desteklenir:

- SOCK_STREAM sıralı, güvenilir, tam çift yönlü, bağlantı tabanlı bayt akışları sağlar. İletim Denetimi Protokolü (TCP), Internet adresi ailesinde için kullanır.

- Sabit (genellikle küçük) maksimum uzunluktaki bağlantısız, güvenilir olmayan paketlerin SOCK_DGRAM destekleyen veri birimi. Kullanıcı Veri Birimi Protokolü (UDP), Internet adresi ailesinde için kullanır.

    > [!NOTE]
    >  `Accept` Üye işlev yeni, boş bir başvuru alır `CSocket` parametre olarak nesne. Çağırmadan önce bu nesne oluşturmalıdır `Accept`. Aklınızda bu yuva nesnesi kapsamını, bağlantıyı kapatır aşması durumunda. Çağırmayın `Create` bu yeni bir yuva nesnesi.

> [!IMPORTANT]
> `Create` olan **değil** iş parçacığı açısından güvenli.  Burada, aynı anda farklı iş parçacıkları tarafından çağırılabilir, çok iş parçacıklı bir ortamda arıyorsanız, her çağrı bir mutex veya diğer eşitleme kilit ile korunacak emin olun.

Stream ve veri birimi yuvaları hakkında daha fazla bilgi için makalelere bakın [Windows Yuvaları: Arka plan](../../mfc/windows-sockets-background.md) ve [Windows Yuvaları: Bağlantı noktaları ve yuva adresleri](../../mfc/windows-sockets-ports-and-socket-addresses.md) ve [Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2).

##  <a name="detach"></a>  CAsyncSocket::Detach

SOCKET tanıtıcısı ayırmak için bu üye işlevini çağırın *m_hSocket* veri üyesinden `CAsyncSocket` ayarlayın ve nesne *m_hSocket* null.

```
SOCKET Detach();
```

##  <a name="fromhandle"></a>  CAsyncSocket::FromHandle

Bir işaretçi döndüren bir `CAsyncSocket` nesne.

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Parametreler

*hSocket*<br/>
Bir yuva için bir tanıtıcı içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CAsyncSocket` nesne veya yoksa NULL hiçbir `CAsyncSocket` nesne iliştirilmiş *hSocket*.

### <a name="remarks"></a>Açıklamalar

Bir YUVA işleyicisini varsa verildiğinde bir `CAsyncSocket` nesne tanıtıcısını bağlı değil, üye işlev NULL döndürür.

##  <a name="getlasterror"></a>  CAsyncSocket::GetLastError

İçin son işlemi başarısız oldu hata durumu almak için bu üye işlevini çağırın.

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri, bu iş parçacığı tarafından gerçekleştirilen son Windows Sockets API'SİNİN yordamı hata kodunu gösterir.

### <a name="remarks"></a>Açıklamalar

Özel üye işlevi bir hata oluştuğunu gösteriyorsa `GetLastError` uygun hata kodunu almak için çağrılmalıdır. İlgili hata kodlarının bir listesi için tek tek üye işlevi açıklamaları bakın.

Hata kodları hakkında daha fazla bilgi için bkz. [Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2).

##  <a name="getpeername"></a>  CAsyncSocket::GetPeerName

Bu yuva bağlandığı eş yuva adresini almak için bu üye işlevini çağırın.

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
Başvuru bir `CString` noktalı bir sayı IP adresi alan nesnesi.

*rPeerPort*<br/>
Bir bağlantı noktası depolayan bir UINT başvuru.

*lpSockAddr*<br/>
Bir işaretçi [SOCKADDR](/windows/desktop/winsock/sockaddr-2) yapısı eş yuva adını alır.

*lpSockAddrLen*<br/>
Uzunluğu adresini bir işaretçiye *lpSockAddr* bayt. Sonrasında, *lpSockAddrLen* bağımsız değişken içeren gerçek boyutuna *lpSockAddr* bayt döndürdü.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni, yeteri kadar büyük değil.

- WSAEINPROGRESS engelleme Windows Sockets çağırmak bir işlemi devam ediyor.

- Yuva WSAENOTCONN bağlı değil.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

### <a name="remarks"></a>Açıklamalar

IPv6 adresleri işlemek için kullanmak [CAsyncSocket::GetPeerNameEx](#getpeernameex).

##  <a name="getpeernameex"></a>  CAsyncSocket::GetPeerNameEx

Bu yuva bağlı (IPv6 adresleri tutamaçlar) olduğu eş yuva adresini almak için bu üye işlevini çağırın.

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>Parametreler

*rPeerAddress*<br/>
Başvuru bir `CString` noktalı bir sayı IP adresi alan nesnesi.

*rPeerPort*<br/>
Bir bağlantı noktası depolayan bir UINT başvuru.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni, yeteri kadar büyük değil.

- WSAEINPROGRESS engelleme Windows Sockets çağırmak bir işlemi devam ediyor.

- Yuva WSAENOTCONN bağlı değil.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

### <a name="remarks"></a>Açıklamalar

Bu işlev aynı şekilde, [CAsyncSocket::GetPeerName](#getpeername) IPv6 işleme dışında de olarak eski protokolleri yöneliktir.

##  <a name="getsockname"></a>  CAsyncSocket::GetSockName

Bir yuva yerel adı almak için bu üye işlevini çağırın.

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
Başvuru bir `CString` noktalı bir sayı IP adresi alan nesnesi.

*rSocketPort*<br/>
Bir bağlantı noktası depolayan bir UINT başvuru.

*lpSockAddr*<br/>
Bir işaretçi bir [SOCKADDR](/windows/desktop/winsock/sockaddr-2) yuva adresini alan yapısı.

*lpSockAddrLen*<br/>
Uzunluğu adresini bir işaretçiye *lpSockAddr* bayt.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni, yeteri kadar büyük değil.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- Yuva bağlı sahip bir adresi WSAEINVAL `Bind`.

### <a name="remarks"></a>Açıklamalar

Bu çağrı durumlarda özellikle yararlı olur bir `Connect` çağrı yapmak olmadan yapılan bir `Bind` ilk; bu çağrı tarafından belirleyebilirsiniz sistemi tarafından ayarlanan yerel bir ilişkilendirme yalnızca sağlar.

IPv6 adresleri işlemek için kullanmak [CAsyncSocket::GetSockNameEx](#getsocknameex)

##  <a name="getsocknameex"></a>  CAsyncSocket::GetSockNameEx

Bir yuva (IPv6 adresleri tutamaçlar) yerel adı almak için bu üye işlevini çağırın.

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>Parametreler

*rSocketAddress*<br/>
Başvuru bir `CString` noktalı bir sayı IP adresi alan nesnesi.

*rSocketPort*<br/>
Bir bağlantı noktası depolayan bir UINT başvuru.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni, yeteri kadar büyük değil.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- Yuva bağlı sahip bir adresi WSAEINVAL `Bind`.

### <a name="remarks"></a>Açıklamalar

Bu çağrı aynıdır [CAsyncSocket::GetSockName](#getsockname) IPv6 işleme dışında de olarak eski protokolleri yöneliktir.

Bu çağrı durumlarda özellikle yararlı olur bir `Connect` çağrı yapmak olmadan yapılan bir `Bind` ilk; bu çağrı tarafından belirleyebilirsiniz sistemi tarafından ayarlanan yerel bir ilişkilendirme yalnızca sağlar.

##  <a name="getsockopt"></a>  CAsyncSocket::GetSockOpt

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
Değeri alınacak olduğu yuva seçeneği.

*lpOptionValue*<br/>
İstenen seçeneğinin değeri döndürülecek arabellek için işaretçi. Arabellekte döndürülen seçeneği ile ilişkili değer *lpOptionValue*. Tamsayı tarafından işaret edilen *lpOptionLen* ilk bayt; bu arabellek boyutu içermelidir ve, geri döndürülen değer boyutuna ayarlanır. SO_LINGER için bu boyutu olacak bir `LINGER` yapısı; diğer tüm seçenekler için bir BOOL boyutunu olacaktır ya da bir **int**seçeneğine bağlı olarak. Seçenekler ve Açıklamalar bölümü içindeki boyutlarının listesini görürsünüz.

*lpOptionLen*<br/>
Bir işaretçinin boyutuna *lpOptionValue* arabelleğinin bayt cinsinden.

*nLevel*<br/>
Seçeneğin tanımlandığı düzeyi; yalnızca desteklenen düzeyler SOL_SOCKET ve IPPROTO_TCP verilmiştir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Bir seçenek ile hiçbir zaman ayarlandıysa `SetSockOpt`, ardından `GetSockOpt` seçeneğinin varsayılan değerini döndürür. Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEFAULT *lpOptionLen* bağımsız değişkeni geçersiz.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- Bilinmeyen veya desteklenmeyen WSAENOPROTOOPT seçeneği. Özellikle, SO_BROADCAST yuva SO_ACCEPTCONN, SO_DONTLINGER SO_KEEPALIVE SO_LINGER ve SO_OOBINLINE çalışırken, SOCK_STREAM türü SOCK_DGRAM yuvalarda desteklenmez türü desteklenmiyor.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

### <a name="remarks"></a>Açıklamalar

`GetSockOpt` bir yuva herhangi bir durum içinde herhangi bir tür ile ilişkili bir yuva seçeneği için geçerli değer alır ve sonuçta depolar *lpOptionValue*. Seçenekler, paketler, bant dışı veri aktarımı ve benzeri yönlendirme gibi yuva işlemlerini etkiler.

Aşağıdaki seçenekler için desteklenen `GetSockOpt`. Tarafından ele alınan verilerin türünü tanımlayan *lpOptionValue*. Düzey IPPROTO_TCP TCP_NODELAY seçeneğini kullanır. diğer tüm seçenekler düzeyi SOL_SOCKET kullanın.

|Değer|Tür|Açıklama|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Yuva dinliyor.|
|SO_BROADCAST|BOOL|Yuva yayın ileti aktarım için yapılandırılır.|
|SO_DEBUG|BOOL|Hata ayıklama etkin.|
|SO_DONTLINGER|BOOL|TRUE ise SO_LINGER seçeneği devre dışı bırakıldı.|
|SO_DONTROUTE|BOOL|Yönlendirme devre dışı bırakıldı.|
|SO_ERROR|**int**|Hata durumu almak ve temizleyin.|
|SO_KEEPALIVE|BOOL|Gönderilen etkin tutma.|
|SO_LINGER|`struct LINGER`|Geçerli lınger seçeneklerini döndürür.|
|SO_OOBINLINE|BOOL|Bant dışı verileri normal veri akışında alınır.|
|SO_RCVBUF|int|Arabellek boyutunu alır.|
|SO_REUSEADDR|BOOL|Yuva zaten kullanımda olan bir adresle bağlı olabilir.|
|SO_SNDBUF|**int**|Arabellek boyutu için gönderir.|
|SO_TYPE|**int**|' % S'yuva (örneğin, SOCK_STREAM) türü.|
|TCP_NODELAY|BOOL|Gönderme birleşim Nagle algoritmasını devre dışı bırakır.|

Berkeley yazılım dağıtım (BSD) seçenekleri için desteklenmeyen `GetSockOpt` şunlardır:

|Değer|Tür|Açıklama|
|-----------|----------|-------------|
|SO_RCVLOWAT|**int**|Düşük su işareti alırsınız.|
|SO_RCVTIMEO|**int**|Zaman aşımı alırsınız.|
|SO_SNDLOWAT|**int**|Düşük su işareti gönderin.|
|SO_SNDTIMEO|**int**|Zaman aşımı gönderin.|
|IP_OPTIONS||Seçenekler IP üstbilgisinde alın.|
|TCP_MAXSEG|**int**|TCP en büyük kesim boyutu alın.|

Çağırma `GetSockOpt` WSAENOPROTOOPT öğesinden döndürülen hata kodu ile bir desteklenmeyen seçenek sonuçlanır `GetLastError`.

##  <a name="ioctl"></a>  CAsyncSocket::IOCtl

Bir yuva modunu denetlemek için bu üye işlevini çağırın.

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>Parametreler

*lCommand*<br/>
Yuva gerçekleştirmek için komutu.

*lpArgument*<br/>
Bir parametre için bir işaretçiye *lCommand*.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEINVAL *lCommand* geçerli bir komut değil veya *lpArgument* için kabul edilebilir bir parametre değil *lCommand*, ya da komut sağlanan yuva türü için geçerli değil .

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

### <a name="remarks"></a>Açıklamalar

Bu yordam herhangi bir yuvada kullanılabilir. Elde etmek veya yuvasıyla protokolü ve iletişim alt sistemi bağımsız ilişkili parametrelerini almak için kullanılır. Aşağıdaki komutlar desteklenir:

- FIONBIO etkinleştirmek veya devre dışı sayıda modu yuvadaki. *LpArgument* parametresi işaret adresindeki bir `DWORD`sayıda modu etkinleştirilmesini ise sıfır dışında olan ve sıfır olduğu devre dışı bırakılacak. Varsa `AsyncSelect` herhangi kullanma girişimi sonra bir yuvada verildi `IOCtl` yuva ayarlamak için engelleme modu geri WSAEINVAL ile başarısız olur. Yuva engelleme moduna ayarlayın ve WSAEINVAL hatayı önlemek için bir uygulama önce devre dışı bırakmalısınız `AsyncSelect` çağırarak `AsyncSelect` ile *lEvent* parametresi 0'a eşit'ı çağırın `IOCtl`.

- FIONREAD belirlemek biriyle okunan bayt sayısı `Receive` bu yuvadan çağırın. *LpArgument* parametresi işaret konumunda bir `DWORD` hangi `IOCtl` sonucu depolar. Bu yuva türü SOCK_STREAM ise FIONREAD okunabilir verilerin toplam miktarı tek bir döndürür. `Receive`; yuvada toplam veri miktarı kuyruğa Bu normalde aynı olur. Bu yuva SOCK_DGRAM türü ise, ilk veri birimi boyutunu yuva kuyruğa FIONREAD döndürür.

- SIOCATMARK belirlemek olup tüm bant dışı verileri okuyun. Bu yalnızca bir yuva türü herhangi bir bant dışı veri (SO_OOBINLINE) satır içi alma için yapılandırılan SOCK_STREAM geçerlidir. Bant dışı veri okumak için bekleyen, işlem sıfır döndürür. Aksi durumda 0 ve sonraki döndürür `Receive` veya `ReceiveFrom` gerçekleştirilen yuva bazılarını veya tümünü "işareti" önceki veri alır; herhangi bir veri kalıp kalmayacağını belirlemek için uygulama SIOCATMARK işlemi kullanmanız gerekir. "Acil" (bant-) verilerin önceki herhangi bir normal veri varsa, sırayla alınır. (Unutmayın bir `Receive` veya `ReceiveFrom` hiçbir zaman aynı çağrı bant dışı ve normal verileri karıştırın.) *LpArgument* parametresi işaret konumunda bir `DWORD` hangi `IOCtl` sonucu depolar.

Bu işlev, bir alt kümesini `ioctl()` Berkeley yuva kullanılır. Özellikle, SIOCATMARK desteklenmeyen yalnızca yuva düzeyinde komutu olsa da FIOASYNC için eşdeğer olan bir komut yoktur.

##  <a name="listen"></a>  CAsyncSocket::Listen

Gelen bağlantı isteklerini dinlemek için bu üye işlevini çağırın.

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>Parametreler

*nConnectionBacklog*<br/>
Sıranın bağlantıları bekleyen büyüyebileceği maksimum uzunluğu. Geçerli aralık 1'den 5 ' dir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- Adresin kullanılmakta dinleyecek şekilde WSAEADDRINUSE girişiminde bulunuldu.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- Yuva bağlı ile WSAEINVAL `Bind` veya zaten bağlı.

- Yuva WSAEISCONN zaten bağlı.

- WSAEMFILE Hayır, daha fazla dosya tanımlayıcısı kullanılabilir.

- WSAENOBUFS Hayır arabellek alanı kullanılabilir.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- Başvurulan yuva destekleyen bir tür değil WSAEOPNOTSUPP `Listen` işlemi.

### <a name="remarks"></a>Açıklamalar

Bağlantıları kabul etmek için yuva ilk ile oluşturulan `Create`, gelen bağlantıları için bir biriktirme listesi ile belirtilen `Listen`, ve ardından ile bağlantıları kabul `Accept`. `Listen` bağlantılar, destekleyen yuva için diğer bir deyişle, bu tür SOCK_STREAM geçerlidir. Bu yuva, gelen bağlantıları burada onaylanır ve onay bir işlem tarafından sıraya "pasif" moduna yerleştirin.

Bu işlevin genellikle sunucuları (veya bağlantıları kabul etmek isteyen herhangi bir uygulama) tarafından kullanılan aynı anda birden fazla bağlantı isteğine sahip: bir bağlantı isteği kuyruğu dolu alınırsa, istemci bir göstergesi ile ilgili bir hata alır WSAECONNREFUSED.

`Listen` kullanılabilir bağlantı noktası (tanımlayıcıları) olduğunda rationally çalışmaya devam etmek çalışır. Sıranın boşaltılıp boşaltılmaması kadar bağlantılarını kabul eder. Bağlantı noktaları yayımlanırsa sonraki çağrı `Listen` veya `Accept` geçerli ya da en son "biriktirme listesi," kuyruğa mümkünse yenileme ve gelen bağlantıları dinlemeyi Sürdür.

##  <a name="m_hsocket"></a>  CAsyncSocket::m_hSocket

Bu kapsüllenmiş yuva için SOCKET tanıtıcısı içeren `CAsyncSocket` nesne.

```
SOCKET m_hSocket;
```

##  <a name="onaccept"></a>  CAsyncSocket::OnAccept

Çağırarak bağlantı isteklerini kabul edebilirsiniz dinleme bir yuva bildirmek için framework tarafından çağırılır [kabul](#accept) üye işlevi.

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuva en son hata oluştu. Aşağıdaki hata kodları uygulandığı `OnAccept` üye işlevi:

- **0** işlevi başarıyla yürütüldü.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onclose"></a>  CAsyncSocket::OnClose

Bu yuva bağlı bir yuva işlemleri tarafından kapalı olduğunu bildirmek için framework tarafından çağırılır.

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuva en son hata oluştu. Aşağıdaki hata kodları uygulamak `OnClose` üye işlevi:

- **0** işlevi başarıyla yürütüldü.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- Uzak yan yana WSAECONNRESET bağlantı sıfırlandı.

- WSAECONNABORTED bağlantı zaman aşımı veya diğer hata nedeniyle durduruldu.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onconnect"></a>  CAsyncSocket::OnConnect

Bu yuva bağlantı, bağlantı denemesi, başarıyla veya hatayla tamamlandığını bildirmek için framework tarafından çağırılır.

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuva en son hata oluştu. Aşağıdaki hata kodları uygulamak `OnConnect` üye işlevi:

- **0** işlevi başarıyla yürütüldü.

- WSAEADDRINUSE belirtilen adresi zaten kullanılıyor.

- Yerel makineden WSAEADDRNOTAVAIL belirtilen adresi kullanılamaz.

- Bu yuva ile belirtilen ailesindeki WSAEAFNOSUPPORT adresleri kullanılamaz.

- WSAECONNREFUSED bağlanma girişimi zorla reddedildi.

- WSAEDESTADDRREQ bir hedef adresi gereklidir.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni yanlış.

- WSAEINVAL yuva için bir adres zaten bağlı.

- Yuva WSAEISCONN zaten bağlı.

- WSAEMFILE Hayır, daha fazla dosya tanımlayıcısı kullanılabilir.

- WSAENETUNREACH ağ şu anda bu konaktan erişilemiyor.

- WSAENOBUFS Hayır arabellek alanı kullanılabilir. Yuva bağlanamaz.

- Yuva WSAENOTCONN bağlı değil.

- WSAENOTSOCK tanımlayıcı, bir yuva dosyadır.

- WSAETIMEDOUT bağlanma girişimi bağlantı kurmadan zaman aşımına uğradı.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  İçinde [CSocket](../../mfc/reference/csocket-class.md), `OnConnect` bildirim işlevini hiçbir zaman çağrılır. Yalnızca bağlantıları için çağırmanız `Connect`, bağlantı (başarıyla veya hata) tamamlandığında döndürülür. Bağlantı bildirimleri nasıl işleneceğini bir MFC Uygulama ayrıntısı olduğunu.

Daha fazla bilgi için [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

##  <a name="onoutofbanddata"></a>  CAsyncSocket::OnOutOfBandData

Bildirim göndermek için bant dışı veri gönderen yuva olan alan yuva için framework tarafından çağırılır.

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuva en son hata oluştu. Aşağıdaki hata kodları uygulamak `OnOutOfBandData` üye işlevi:

- **0** işlevi başarıyla yürütüldü.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

### <a name="remarks"></a>Açıklamalar

Bant dışı veri türü SOCK_STREAM bağlı yuva her bir çifti ile ilişkili olan mantıksal olarak bağımsızdır bir kanaldır. Kanal, genellikle Acil veri göndermek için kullanılır.

MFC destekler ama sınıfın kullanıcılar bant dışı veri `CAsyncSocket` kullanmasını önerilmez. Daha kolay yolu, bu tür verileri geçirmek için ikinci bir yuva oluşturmaktır. Bant dışı veriler hakkında daha fazla bilgi için bkz. [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onreceive"></a>  CAsyncSocket::OnReceive

Bu yuva olduğundan veri çağrılarak alınabilir arabellek bildirmek için framework tarafından çağırılır `Receive` üye işlevi.

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuva en son hata oluştu. Aşağıdaki hata kodları uygulamak `OnReceive` üye işlevi:

- **0** işlevi başarıyla yürütüldü.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

##  <a name="onsend"></a>  CAsyncSocket::OnSend

Şimdi veri çağırarak gönderebilmesi gerektiğini yuva bildirmek için framework tarafından çağırılır `Send` üye işlevi.

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>Parametreler

*nErrorCode*<br/>
Bir yuva en son hata oluştu. Aşağıdaki hata kodları uygulamak `OnSend` üye işlevi:

- **0** işlevi başarıyla yürütüldü.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

##  <a name="operator_eq"></a>  CAsyncSocket::operator =

Yeni bir değer atar bir `CAsyncSocket` nesne.

```
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Var olan bir başvuru `CAsyncSocket` nesne.

### <a name="remarks"></a>Açıklamalar

Mevcut bir kopyalamak için bu işlevi çağırın `CAsyncSocket` başka bir nesneye `CAsyncSocket` nesne.

##  <a name="operator_socket"></a>  CAsyncSocket::operator YUVA

YUVA tanıtıcısını almak için bu işleci kullanın `CAsyncSocket` nesne.

```
operator SOCKET() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, YUVA nesnesi; tanıtıcısı Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı, doğrudan Windows API çağırmak için kullanabilirsiniz.

##  <a name="receive"></a>  CAsyncSocket::Receive

Bir yuvadan verileri almak için bu üye işlevini çağırın.

```
virtual int Receive(
    void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Gelen veriler için arabellek.

*nBufLen*<br/>
Uzunluğunu *lpBuf* bayt.

*nFlags*<br/>
Çağrının yapıldığı yolu belirtir. Bu işlev semantiği yuva seçeneklere göre belirlenir ve *nFlags* parametresi. İkincisi aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulur **veya** işleci:

- MSG_PEEK Özet gelen veri. Veriler belleğe kopyalanır, ancak giriş sıradan kaldırılmadı.

- Bant dışı verilerini MSG_OOB işleme.

### <a name="return-value"></a>Dönüş Değeri

Eğer hiç Hata oluşmazsa `Receive` alınan bayt sayısını döndürür. Bağlantıyı kapattıysanız, 0 değerini döndürür. Aksi takdirde SOCKET_ERROR değeri döndürülür ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- Yuva WSAENOTCONN bağlı değil.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi ancak yuva SOCK_STREAM türü değil.

- WSAESHUTDOWN yuva kapatıldı; Çağrı mümkün değil `Receive` sonra bir yuvada `ShutDown` ile çağrılan *nHow* 0 veya 2 olarak ayarlayın.

- Yuva işaretlenmiş WSAEWOULDBLOCK olarak sayıda ve `Receive` işlem engellendi.

- WSAEMSGSIZE veri birimi belirtilen arabelleğe sığamayacak kadar büyük ve kesildi.

- Yuva bağlı ile WSAEINVAL `Bind`.

- Sanal bağlantı hattını WSAECONNABORTED zaman aşımı veya diğer hata nedeniyle durduruldu.

- Sanal bağlantı hattını WSAECONNRESET uzak yan yana sıfırlandı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bağlı stream veya veri birimi yuvaları kullanılır ve gelen veri okumak için kullanılır.

İçin yuva türü SOCK_STREAM sağlanan arabellek boyutu en fazla şu anda kullanılabilir olduğu kadar çok bilgi döndürülür. Bant dışı verileri (Yuva seçeneği SO_OOBINLINE) satır içi alımını yuva yapılandırıldı ve bant dışı veri okunmamış ise, yalnızca bant dışı verileri döndürülür. Uygulamanın kullanabileceği `IOCtlSIOCATMARK` seçeneği veya [OnOutOfBandData](#onoutofbanddata) daha-bant verileri okumak için kalıp kalmayacağını belirlemek için.

Veri birimi yuvaları için sağlanan arabellek boyutu en fazla ilk sıraya alınan veri birimi gelen veri ayıklanır. Veri birimi sağlanan arabellekten daha büyük ise, arabelleği veri birimi ilk kısmı ile doldurulur, fazlalık veriler kaybolur ve `Receive` SOCKET_ERROR değerini hata kodu ile ayarlamak için WSAEMSGSIZE döndürür. Gelen veri yok yuva kullanılabilir haldeyse, SOCKET_ERROR değeri için WSAEWOULDBLOCK ayarlayın hata kodu ile döndürülür. [OnReceive](#onreceive) geri çağırma işlevi, daha fazla veri geldiğinde belirlemek için kullanılabilir.

Yuva SOCK_STREAM türüdür ve uzak tarafı düzgün bir şekilde, bağlantıyı kapattı bir `Receive` 0 alınan bayt sayısı ile hemen tamamlanır. Bağlantı sıfırlarsanız bir `Receive` WSAECONNRESET hata ile başarısız olur.

`Receive` her defasında yalnızca bir kez çağrılmalıdır [CAsyncSocket::OnReceive](#onreceive) çağrılır.

### <a name="example"></a>Örnek

  Örneğin bakın [CAsyncSocket::OnReceive](#onreceive).

##  <a name="receivefrom"></a>  CAsyncSocket::ReceiveFrom

Bir veri birimi almak ve kaynak adresi depolamak için bu üye işlevi çağrısı [SOCKADDR](/windows/desktop/winsock/sockaddr-2) yapısı veya *rSocketAddress*.

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
Gelen veriler için arabellek.

*nBufLen*<br/>
Uzunluğunu *lpBuf* bayt.

*rSocketAddress*<br/>
Başvuru bir `CString` noktalı bir sayı IP adresi alan nesnesi.

*rSocketPort*<br/>
Bir bağlantı noktası depolayan bir UINT başvuru.

*lpSockAddr*<br/>
Bir işaretçi bir [SOCKADDR](/windows/desktop/winsock/sockaddr-2) iade sırasında kaynak adresi tutan yapı.

*lpSockAddrLen*<br/>
Kaynak adresi uzunluğunu işaretçisi *lpSockAddr* bayt.

*nFlags*<br/>
Çağrının yapıldığı yolu belirtir. Bu işlev semantiği yuva seçeneklere göre belirlenir ve *nFlags* parametresi. İkincisi aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulur **veya** işleci:

- MSG_PEEK Özet gelen veri. Veriler belleğe kopyalanır, ancak giriş sıradan kaldırılmadı.

- Bant dışı verilerini MSG_OOB işleme.

### <a name="return-value"></a>Dönüş Değeri

Eğer hiç Hata oluşmazsa `ReceiveFrom` alınan bayt sayısını döndürür. Bağlantıyı kapattıysanız, 0 değerini döndürür. Aksi takdirde SOCKET_ERROR değeri döndürülür ve belirli bir kodu çağrılarak alınabilir `GetLastError`. Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni geçersiz: *lpSockAddr* arabellek eş adresi uyum sağlamak için çok küçük.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- Yuva bağlı ile WSAEINVAL `Bind`.

- Yuva değil WSAENOTCONN (yalnızca SOCK_STREAM) bağlı.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi ancak yuva SOCK_STREAM türü değil.

- WSAESHUTDOWN yuva kapatıldı; Çağrı mümkün değil `ReceiveFrom` sonra bir yuvada `ShutDown` ile çağrılan *nHow* 0 veya 2 olarak ayarlayın.

- Yuva işaretlenmiş WSAEWOULDBLOCK olarak sayıda ve `ReceiveFrom` işlem engellendi.

- WSAEMSGSIZE veri birimi belirtilen arabelleğe sığamayacak kadar büyük ve kesildi.

- Sanal bağlantı hattını WSAECONNABORTED zaman aşımı veya diğer hata nedeniyle durduruldu.

- Sanal bağlantı hattını WSAECONNRESET uzak yan yana sıfırlandı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, (büyük olasılıkla bağlı) bir yuva gelen verileri okuma ve verilerin gönderildiği adresi yakalamak için kullanılır.

IPv6 adresleri işlemek için kullanmak [CAsyncSocket::ReceiveFromEx](#receivefromex).

İçin yuva türü SOCK_STREAM sağlanan arabellek boyutu en fazla şu anda kullanılabilir olduğu kadar çok bilgi döndürülür. Bant dışı verileri (Yuva seçeneği SO_OOBINLINE) satır içi alımını yuva yapılandırıldı ve bant dışı veri okunmamış ise, yalnızca bant dışı verileri döndürülür. Uygulamanın kullanabileceği `IOCtlSIOCATMARK` seçeneği veya `OnOutOfBandData` daha-bant verileri okumak için kalıp kalmayacağını belirlemek için. *LpSockAddr* ve *lpSockAddrLen* SOCK_STREAM yuva için parametreleri yok sayılır.

Veri birimi yuvaları için sağlanan arabellek boyutu en fazla ilk sıraya alınan veri birimi gelen veri ayıklanır. Veri birimi sağlanan arabellekten daha büyük ise, arabellek ileti ilk kısmı ile doldurulur, fazlalık veriler kaybolur ve `ReceiveFrom` SOCKET_ERROR değerini hata kodu ile ayarlamak için WSAEMSGSIZE döndürür.

Varsa *lpSockAddr* sıfır ve yuva SOCK_DGRAM türüdür, karşılık gelen ağ adresi gönderilen veri yuva kopyalanır [SOCKADDR](/windows/desktop/winsock/sockaddr-2) yapısı. Değeri tarafından işaret edilen *lpSockAddrLen* bu yapının boyutuna başlatılır ve depolanan adresi gerçek boyutunu belirtmek getirisini değiştirilir. Gelen veri yuva kullanılabilir durumdaysa `ReceiveFrom` çağrı bekler yuva olmadığı sürece gelmesi için veri sayıda. Bu durumda, WSAEWOULDBLOCK için ayarlayın hata kodu ile SOCKET_ERROR değeri döndürülür. `OnReceive` Geri çağırma daha fazla veri geldiğinde belirlemek için kullanılabilir.

Yuva SOCK_STREAM türüdür ve uzak tarafı düzgün bir şekilde, bağlantıyı kapattı bir `ReceiveFrom` 0 alınan bayt sayısı ile hemen tamamlanır.

##  <a name="receivefromex"></a>  CAsyncSocket::ReceiveFromEx

Bir veri birimi almak ve kaynak adresi depolamak için bu üye işlevi çağrısı [SOCKADDR](/windows/desktop/winsock/sockaddr-2) yapısı veya *rSocketAddress* (IPv6 adresleri işler).

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
Gelen veriler için arabellek.

*nBufLen*<br/>
Uzunluğunu *lpBuf* bayt.

*rSocketAddress*<br/>
Başvuru bir `CString` noktalı bir sayı IP adresi alan nesnesi.

*rSocketPort*<br/>
Bir bağlantı noktası depolayan bir UINT başvuru.

*nFlags*<br/>
Çağrının yapıldığı yolu belirtir. Bu işlev semantiği yuva seçeneklere göre belirlenir ve *nFlags* parametresi. İkincisi aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulur **veya** işleci:

- MSG_PEEK Özet gelen veri. Veriler belleğe kopyalanır, ancak giriş sıradan kaldırılmadı.

- Bant dışı verilerini MSG_OOB işleme.

### <a name="return-value"></a>Dönüş Değeri

Eğer hiç Hata oluşmazsa `ReceiveFromEx` alınan bayt sayısını döndürür. Bağlantıyı kapattıysanız, 0 değerini döndürür. Aksi takdirde SOCKET_ERROR değeri döndürülür ve belirli bir kodu çağrılarak alınabilir `GetLastError`. Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEFAULT *lpSockAddrLen* bağımsız değişkeni geçersiz: *lpSockAddr* arabellek eş adresi uyum sağlamak için çok küçük.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- Yuva bağlı ile WSAEINVAL `Bind`.

- Yuva değil WSAENOTCONN (yalnızca SOCK_STREAM) bağlı.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi ancak yuva SOCK_STREAM türü değil.

- WSAESHUTDOWN yuva kapatıldı; Çağrı mümkün değil `ReceiveFromEx` sonra bir yuvada `ShutDown` ile çağrılan *nHow* 0 veya 2 olarak ayarlayın.

- Yuva işaretlenmiş WSAEWOULDBLOCK olarak sayıda ve `ReceiveFromEx` işlem engellendi.

- WSAEMSGSIZE veri birimi belirtilen arabelleğe sığamayacak kadar büyük ve kesildi.

- Sanal bağlantı hattını WSAECONNABORTED zaman aşımı veya diğer hata nedeniyle durduruldu.

- Sanal bağlantı hattını WSAECONNRESET uzak yan yana sıfırlandı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, (büyük olasılıkla bağlı) bir yuva gelen verileri okuma ve verilerin gönderildiği adresi yakalamak için kullanılır.

Bu işlev aynı şekilde, [CAsyncSocket::ReceiveFrom](#receivefrom) IPv6 işleme dışında de olarak eski protokolleri yöneliktir.

İçin yuva türü SOCK_STREAM sağlanan arabellek boyutu en fazla şu anda kullanılabilir olduğu kadar çok bilgi döndürülür. Bant dışı verileri (Yuva seçeneği SO_OOBINLINE) satır içi alımını yuva yapılandırıldı ve bant dışı veri okunmamış ise, yalnızca bant dışı verileri döndürülür. Uygulamanın kullanabileceği `IOCtlSIOCATMARK` seçeneği veya `OnOutOfBandData` daha-bant verileri okumak için kalıp kalmayacağını belirlemek için. *LpSockAddr* ve *lpSockAddrLen* SOCK_STREAM yuva için parametreleri yok sayılır.

Veri birimi yuvaları için sağlanan arabellek boyutu en fazla ilk sıraya alınan veri birimi gelen veri ayıklanır. Veri birimi sağlanan arabellekten daha büyük ise, arabellek ileti ilk kısmı ile doldurulur, fazlalık veriler kaybolur ve `ReceiveFromEx` SOCKET_ERROR değerini hata kodu ile ayarlamak için WSAEMSGSIZE döndürür.

Varsa *lpSockAddr* sıfır ve yuva SOCK_DGRAM türüdür, karşılık gelen ağ adresi gönderilen veri yuva kopyalanır [SOCKADDR](/windows/desktop/winsock/sockaddr-2) yapısı. Değeri tarafından işaret edilen *lpSockAddrLen* bu yapının boyutuna başlatılır ve depolanan adresi gerçek boyutunu belirtmek getirisini değiştirilir. Gelen veri yuva kullanılabilir durumdaysa `ReceiveFromEx` çağrı bekler yuva olmadığı sürece gelmesi için veri sayıda. Bu durumda, WSAEWOULDBLOCK için ayarlayın hata kodu ile SOCKET_ERROR değeri döndürülür. `OnReceive` Geri çağırma daha fazla veri geldiğinde belirlemek için kullanılabilir.

Yuva SOCK_STREAM türüdür ve uzak tarafı düzgün bir şekilde, bağlantıyı kapattı bir `ReceiveFromEx` 0 alınan bayt sayısı ile hemen tamamlanır.

##  <a name="send"></a>  CAsyncSocket::Send

Bağlanmış bir yuva üzerinden verileri göndermek için bu üye işlevini çağırın.

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
İletilecek verileri içeren arabellek.

*nBufLen*<br/>
Veri uzunluğu *lpBuf* bayt.

*nFlags*<br/>
Çağrının yapıldığı yolu belirtir. Bu işlev semantiği yuva seçeneklere göre belirlenir ve *nFlags* parametresi. İkincisi aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulur **veya** işleci:

- Yönlendirme tabi verileri olmamalıdır MSG_DONTROUTE belirtir. Windows Yuvaları tedarikçi bu bayrağı yoksayın seçebilirsiniz.

- Bant dışı veri (yalnızca SOCK_STREAM) MSG_OOB Gönder.

### <a name="return-value"></a>Dönüş Değeri

Eğer hiç Hata oluşmazsa `Send` karakter gönderilen toplam sayısını döndürür. (Bu tarafından belirtilen sayıdan daha az olabileceğini unutmayın *nBufLen*.) Aksi takdirde SOCKET_ERROR değeri döndürülür ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- İstenen adreslerin WSAEACCES, bir yayın adresi olmakla birlikte uygun bayrağı ayarlı değil.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- WSAEFAULT *lpBuf* bağımsız değişkeni geçerli bir kullanıcı adres alanının parçası değil.

- Windows Sockets uygulaması, bırakılan çünkü WSAENETRESET bağlantı sıfırlamanız gerekir.

- WSAENOBUFS Windows Sockets uygulaması arabellek kilitlenme raporları.

- Yuva WSAENOTCONN bağlı değil.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi ancak yuva SOCK_STREAM türü değil.

- WSAESHUTDOWN yuva kapatıldı; Çağrı mümkün değil `Send` sonra bir yuvada `ShutDown` ile çağrılan *nHow* 1 veya 2 olarak ayarlayın.

- Yuva işaretlenmiş WSAEWOULDBLOCK olarak sayıda ve istenen işlem engellendi.

- Yuva WSAEMSGSIZE SOCK_DGRAM türüdür ve veri birimi Windows Sockets uygulaması tarafından desteklenen en yüksek değerinden daha büyük.

- Yuva bağlı ile WSAEINVAL `Bind`.

- Sanal bağlantı hattını WSAECONNABORTED zaman aşımı veya diğer hata nedeniyle durduruldu.

- Sanal bağlantı hattını WSAECONNRESET uzak yan yana sıfırlandı.

### <a name="remarks"></a>Açıklamalar

`Send` bağlı akışı veya veri birimi yuvaları üzerinde giden veri yazmak için kullanılır. Veri birimi yuvaları için temel alınan alt ağlar, maksimum IP paket boyutu tarafından belirtilmiş olan aşmayacak şekilde dikkatli olunması gerekir `iMaxUdpDg` öğesinde [WSADATA](/windows/desktop/api/winsock2/ns-winsock2-wsadata) yapısı tarafından döndürülen `AfxSocketInit`. Verileri temel alınan protokolüyle atomik olarak geçirilecek uzunsa WSAEMSGSIZE aracılığıyla döndürülen hata `GetLastError`, ve veri aktarılır.

Bir veri birimi için başarıyla tamamlanması, yuva unutmayın bir `Send` verileri başarıyla teslim edildi göstermez.

Üzerinde `CAsyncSocket` SOCK_STREAM türündeki nesneler, yazılan bayt sayısı, yerel ve yabancı konakları arabellek kullanılabilirliğine bağlı olarak istenen uzunluğu 1 ila olabilir.

### <a name="example"></a>Örnek

  Örneğin bakın [CAsyncSocket::OnSend](#onsend).

##  <a name="sendto"></a>  CAsyncSocket::SendTo

Belirli bir hedefe veri göndermek için bu üye işlevini çağırın.

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
İletilecek verileri içeren arabellek.

*nBufLen*<br/>
Veri uzunluğu *lpBuf* bayt.

*nHostPort*<br/>
Yuva uygulamasını tanımlayan bağlantı noktası.

*lpszHostAddress*<br/>
Bu nesne bağlı yuva ağ adresi: "ftp.microsoft.com" veya "128.56.22.8" gibi noktalı bir sayı gibi bir makine adı.

*nFlags*<br/>
Çağrının yapıldığı yolu belirtir. Bu işlev semantiği yuva seçeneklere göre belirlenir ve *nFlags* parametresi. İkincisi aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulur **veya** işleci:

- Yönlendirme tabi verileri olmamalıdır MSG_DONTROUTE belirtir. Windows Yuvaları tedarikçi bu bayrağı yoksayın seçebilirsiniz.

- Bant dışı veri (yalnızca SOCK_STREAM) MSG_OOB Gönder.

*lpSockAddr*<br/>
Bir işaretçi bir [SOCKADDR](/windows/desktop/winsock/sockaddr-2) yapısı, hedef yuva adresini içerir.

*nSockAddrLen*<br/>
Adres uzunluğunu *lpSockAddr* bayt.

### <a name="return-value"></a>Dönüş Değeri

Eğer hiç Hata oluşmazsa `SendTo` karakter gönderilen toplam sayısını döndürür. (Bu tarafından belirtilen sayıdan daha az olabileceğini unutmayın *nBufLen*.) Aksi takdirde SOCKET_ERROR değeri döndürülür ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- İstenen adreslerin WSAEACCES, bir yayın adresi olmakla birlikte uygun bayrağı ayarlı değil.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- WSAEFAULT *lpBuf* veya *lpSockAddr* parametreleri kullanıcı adres alanının parçası değil veya *lpSockAddr* bağımsız değişkeni çok küçük (bir boyutuküçüktür[SOCKADDR](/windows/desktop/winsock/sockaddr-2) yapısı).

- WSAEINVAL ana bilgisayar adı geçersiz.

- Windows Sockets uygulaması, bırakılan çünkü WSAENETRESET bağlantı sıfırlamanız gerekir.

- WSAENOBUFS Windows Sockets uygulaması arabellek kilitlenme raporları.

- Yuva değil WSAENOTCONN (yalnızca SOCK_STREAM) bağlı.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi ancak yuva SOCK_STREAM türü değil.

- WSAESHUTDOWN yuva kapatıldı; Çağrı mümkün değil `SendTo` sonra bir yuvada `ShutDown` ile çağrılan *nHow* 1 veya 2 olarak ayarlayın.

- Yuva işaretlenmiş WSAEWOULDBLOCK olarak sayıda ve istenen işlem engellendi.

- Yuva WSAEMSGSIZE SOCK_DGRAM türüdür ve veri birimi Windows Sockets uygulaması tarafından desteklenen en yüksek değerinden daha büyük.

- Sanal bağlantı hattını WSAECONNABORTED zaman aşımı veya diğer hata nedeniyle durduruldu.

- Sanal bağlantı hattını WSAECONNRESET uzak yan yana sıfırlandı.

- Yerel makineden WSAEADDRNOTAVAIL belirtilen adresi kullanılamaz.

- Bu yuva ile belirtilen ailesindeki WSAEAFNOSUPPORT adresleri kullanılamaz.

- WSAEDESTADDRREQ bir hedef adresi gereklidir.

- WSAENETUNREACH ağ şu anda bu konaktan erişilemiyor.

### <a name="remarks"></a>Açıklamalar

`SendTo` veri birimi veya akıştan yuvalarda kullanılır ve bir yuvada giden veri yazmak için kullanılır. Veri birimi yuvaları için temel alınan alt ağlar, maksimum IP paket boyutu tarafından belirtilmiş olan aşmayacak şekilde dikkatli olunması gerekir `iMaxUdpDg` öğesinde [WSADATA](/windows/desktop/api/winsock2/ns-winsock2-wsadata) tarafından yapısı dolu [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Verileri temel alınan protokolüyle atomik olarak geçirilecek uzunsa WSAEMSGSIZE döndürülen hata ve veri iletilir.

Unutmayın başarılı olarak tamamlanmasına bir `SendTo` verileri başarıyla teslim edildi göstermez.

`SendTo` yalnızca bir SOCK_DGRAM yuvada bir veri birimi ile tanımlanan belirli bir yuva göndermek için kullanılan *lpSockAddr* parametresi.

(Bir SOCK_DGRAM üzerinde yalnızca), yayın gönderilecek adres *lpSockAddr* parametre oluşturulmasını özel IP adresiyle INADDR_BROADCAST (WINSOCK Windows Sockets üstbilgi dosyasında tanımlanır. H) ile birlikte istenen bağlantı noktası numarası. Veya *lpszHostAddress* parametre NULL ise, yuva yayın için yapılandırılmış. Başlangıçtan parçalanma gerçekleşebilir, boyut değerini aşmasına yayın bir veri birimi için genelde önerilmez (üst bilgiler hariç) veri birimi veri bölümünü 512 bayt aşmamalıdır anlamına gelir.

IPv6 adresleri işlemek için kullanmak [CAsyncSocket::SendToEx](#sendtoex).

##  <a name="sendtoex"></a>  CAsyncSocket::SendToEx

Belirli bir hedefe (IPv6 adresleri tutamaçlar) veri göndermek için bu üye işlevini çağırın.

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
İletilecek verileri içeren arabellek.

*nBufLen*<br/>
Veri uzunluğu *lpBuf* bayt.

*nHostPort*<br/>
Yuva uygulamasını tanımlayan bağlantı noktası.

*lpszHostAddress*<br/>
Bu nesne bağlı yuva ağ adresi: "ftp.microsoft.com" veya "128.56.22.8" gibi noktalı bir sayı gibi bir makine adı.

*nFlags*<br/>
Çağrının yapıldığı yolu belirtir. Bu işlev semantiği yuva seçeneklere göre belirlenir ve *nFlags* parametresi. İkincisi aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulur **veya** işleci:

- Yönlendirme tabi verileri olmamalıdır MSG_DONTROUTE belirtir. Windows Yuvaları tedarikçi bu bayrağı yoksayın seçebilirsiniz.

- Bant dışı veri (yalnızca SOCK_STREAM) MSG_OOB Gönder.

### <a name="return-value"></a>Dönüş Değeri

Eğer hiç Hata oluşmazsa `SendToEx` karakter gönderilen toplam sayısını döndürür. (Bu tarafından belirtilen sayıdan daha az olabileceğini unutmayın *nBufLen*.) Aksi takdirde SOCKET_ERROR değeri döndürülür ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- İstenen adreslerin WSAEACCES, bir yayın adresi olmakla birlikte uygun bayrağı ayarlı değil.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- WSAEFAULT *lpBuf* veya *lpSockAddr* parametreleri kullanıcı adres alanının parçası değil veya *lpSockAddr* bağımsız değişkeni çok küçük (bir boyutuküçüktür[SOCKADDR](/windows/desktop/winsock/sockaddr-2) yapısı).

- WSAEINVAL ana bilgisayar adı geçersiz.

- Windows Sockets uygulaması, bırakılan çünkü WSAENETRESET bağlantı sıfırlamanız gerekir.

- WSAENOBUFS Windows Sockets uygulaması arabellek kilitlenme raporları.

- Yuva değil WSAENOTCONN (yalnızca SOCK_STREAM) bağlı.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

- WSAEOPNOTSUPP MSG_OOB belirtildi ancak yuva SOCK_STREAM türü değil.

- WSAESHUTDOWN yuva kapatıldı; Çağrı mümkün değil `SendToEx` sonra bir yuvada `ShutDown` ile çağrılan *nHow* 1 veya 2 olarak ayarlayın.

- Yuva işaretlenmiş WSAEWOULDBLOCK olarak sayıda ve istenen işlem engellendi.

- Yuva WSAEMSGSIZE SOCK_DGRAM türüdür ve veri birimi Windows Sockets uygulaması tarafından desteklenen en yüksek değerinden daha büyük.

- Sanal bağlantı hattını WSAECONNABORTED zaman aşımı veya diğer hata nedeniyle durduruldu.

- Sanal bağlantı hattını WSAECONNRESET uzak yan yana sıfırlandı.

- Yerel makineden WSAEADDRNOTAVAIL belirtilen adresi kullanılamaz.

- Bu yuva ile belirtilen ailesindeki WSAEAFNOSUPPORT adresleri kullanılamaz.

- WSAEDESTADDRREQ bir hedef adresi gereklidir.

- WSAENETUNREACH ağ şu anda bu konaktan erişilemiyor.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ile aynıdır [CAsyncSocket::SendTo](#sendto) IPv6 işleme dışında de olarak eski protokolleri yöneliktir.

`SendToEx` veri birimi veya akıştan yuvalarda kullanılır ve bir yuvada giden veri yazmak için kullanılır. Veri birimi yuvaları için temel alınan alt ağlar, maksimum IP paket boyutu tarafından belirtilmiş olan aşmayacak şekilde dikkatli olunması gerekir `iMaxUdpDg` öğesinde [WSADATA](/windows/desktop/api/winsock2/ns-winsock2-wsadata) tarafından yapısı dolu [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Verileri temel alınan protokolüyle atomik olarak geçirilecek uzunsa WSAEMSGSIZE döndürülen hata ve veri iletilir.

Unutmayın başarılı olarak tamamlanmasına bir `SendToEx` verileri başarıyla teslim edildi göstermez.

`SendToEx` yalnızca bir SOCK_DGRAM yuvada bir veri birimi ile tanımlanan belirli bir yuva göndermek için kullanılan *lpSockAddr* parametresi.

(Bir SOCK_DGRAM üzerinde yalnızca), yayın gönderilecek adres *lpSockAddr* parametre oluşturulmasını özel IP adresiyle INADDR_BROADCAST (WINSOCK Windows Sockets üstbilgi dosyasında tanımlanır. H) ile birlikte istenen bağlantı noktası numarası. Veya *lpszHostAddress* parametre NULL ise, yuva yayın için yapılandırılmış. Başlangıçtan parçalanma gerçekleşebilir, boyut değerini aşmasına yayın bir veri birimi için genelde önerilmez (üst bilgiler hariç) veri birimi veri bölümünü 512 bayt aşmamalıdır anlamına gelir.

##  <a name="setsockopt"></a>  CAsyncSocket::SetSockOpt

Bir yuva seçeneğini ayarlamak için bu üye işlevini çağırın.

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Parametreler

*nOptionName*<br/>
Değeri ayarlanacak olduğu yuva seçeneği.

*lpOptionValue*<br/>
İstenen seçeneğine ilişkin değer sağlandığı arabellek için işaretçi.

*nOptionLen*<br/>
Boyutu *lpOptionValue* arabelleğinin bayt cinsinden.

*nLevel*<br/>
Seçeneğin tanımlandığı düzeyi; yalnızca desteklenen düzeyler SOL_SOCKET ve IPPROTO_TCP verilmiştir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEFAULT *lpOptionValue* geçerli bir işlemin adres alanının parçası değil.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- WSAEINVAL *nLevel* geçerli değil veya bilgileri *lpOptionValue* geçerli değil.

- SO_KEEPALIVE ayarlandığında WSAENETRESET bağlantı zaman aşımına uğradı.

- Bilinmeyen veya desteklenmeyen WSAENOPROTOOPT seçeneği. Özellikle, SO_BROADCAST yuva SO_DONTLINGER, SO_KEEPALIVE SO_LINGER ve SO_OOBINLINE çalışırken, SOCK_STREAM türü SOCK_DGRAM yuvalarda desteklenmez türü desteklenmiyor.

- SO_KEEPALIVE ayarlandığında WSAENOTCONN bağlantı sıfırlandı.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

### <a name="remarks"></a>Açıklamalar

`SetSockOpt` bir yuva herhangi bir durumda herhangi bir tür ile ilişkili bir yuva seçeneği için geçerli değerini ayarlar. Birden çok protokol düzeylerinde seçenekler bulunabilir ancak bu belirtimi yalnızca üst "yuva" düzeyinde mevcut olan seçenekler tanımlar. Seçenekler, yayın iletilerini yuva gönderilir ve benzeri olup olmadığını normal veri akışında alınan hızlandırılmış veri olup olmadığı gibi yuva işlemlerini etkiler.

İki tür yuva seçeneği vardır: Etkinleştirmek veya bir özelliği ya da davranışı devre dışı bırakan Boole seçenekleri ve bir tamsayı değeri veya yapı gerektiren seçenekleri. Bir Boolean seçeneği etkinleştirmek için *lpOptionValue* işaret sıfır olmayan bir tamsayı. Seçeneğini devre dışı bırakmak için *lpOptionValue* sıfıra eşit bir tamsayı işaret eder. *nOptionLen* eşit olmalıdır `sizeof(BOOL)` Boole seçenekleri. Diğer seçenekler için *lpOptionValue* işaret eden bir tamsayı ya da seçeneğinin istenen değeri içeren yapısı ve *nOptionLen* tamsayı veya yapının uzunluğudur.

SO_LINGER gönderilmemiş verileri bir yuvada sıraya konursa gerçekleştirilecek eylemi denetler ve `Close` işlevi yuva kapatmak için çağrılır.

Varsayılan olarak, bir yuva bağlanamaz (bkz [bağlama](#bind)) zaten kullanımda olan bir yerel adres için. Bazen, ancak bunu "Bu şekilde bir adresi yeniden kullanmak için" istenebilir. Her bağlantı yerel ve uzak adres birleşimiyle benzersiz şekilde tanımlanır olduğundan, iki yuva uzak adresleri farklı olduğu sürece aynı yerel adresine bağlı olan hiçbir sorun yoktur.

Windows Yuvaları uygulama bildirmek için bir `Bind` yuva çağrıda değil izin verilmeyen istenen adresi zaten başka bir yuva tarafından kullanımda olduğundan, uygulama vermeden önce SO_REUSEADDR yönelik olarak yuva seçeneği yuva ayarlamanız gerekir `Bind` çağırın. Seçeneği yalnızca zamanında yorumlanır unutmayın `Bind` çağrı:, bu nedenle, var olan bir adresine bağlı olmayan bir yuvada seçeneğini ayarlamak için (ancak zararsız) gerekli değildir ve ayarlama veya seçeneğinden sonra sıfırlama `Bind` çağrısı vardır Bu veya başka bir yuva üzerinde hiçbir etkisi yok.

Bir uygulama, Windows Sockets uygulaması SO_KEEPALIVE yuva seçeneğini etkinleştirerek İletim Denetimi Protokolü (TCP) bağlantılarda "etkin tutma" paketlerin kullanımını etkinleştirmek isteyebilirsiniz. Bir Windows Sockets uygulaması tutma kullanımını desteklemiyor: kesin semantiği aşması durumunda, uygulamaya özgü ancak RFC 1122 4.2.3.6 bölümüne uymalıdır: "Internet ana bilgisayarları için gereksinimleri — iletişim katmanları." Sonuç olarak bir bağlantı kesilirse "etkin tutma" hata kodu WSAENETRESET sürüyor çağrılardan hiçbirine yuva döndürülür ve WSAENOTCONN ile sonraki çağrılar başarısız olur.

TCP_NODELAY seçeneği Nagle algoritmayı devre dışı bırakır. Nagle algoritması, bir ana bilgisayar tarafından tam boyutlu bir paket gönderilebilir kadar bildirilmemiş gönderme veri arabelleğe alma tarafından gönderilen küçük paketlerinin sayısını azaltmak için kullanılır. Ancak, bazı uygulamalar için performansı bu algoritma engel ve TCP_NODELAY devre dışı bırakmak için kullanılabilir. TCP_NODELAY ayarı ağ performansını önemli olumsuz bir etkisi olabileceği için etkisi Bunun yapılması, bu nedenle anlaşılır ve istenen, olmadığı sürece, uygulama yazarları TCP_NODELAY ayarlanmamalıdır. TCP_NODELAY olan tek düzey IPPROTO_TCP; kullanan yuva seçeneği desteklenmiyor diğer tüm seçenekler düzeyi SOL_SOCKET kullanın.

Bir uygulama tarafından SO_DEBUG seçenek ayarlanırsa Windows Sockets tedarik bazı uygulamalarında hata ayıklama bilgileri çıktı.

Aşağıdaki seçenekler için desteklenen `SetSockOpt`. Tarafından ele alınan verilerin türünü tanımlayan *lpOptionValue*.

|Değer|Tür|Açıklama|
|-----------|----------|-------------|
|SO_BROADCAST|BOOL|Yayın ileti yuvada izin verir.|
|SO_DEBUG|BOOL|Hata ayıklama bilgileri kayıt.|
|SO_DONTLINGER|BOOL|Engelleme `Close` gönderilecek gönderilmemiş verileri bekleniyor. Bu ayar ile SO_LINGER ayarını eşdeğer `l_onoff` sıfır olarak ayarlayın.|
|SO_DONTROUTE|BOOL|Yol yok: doğrudan arabirimi Gönder.|
|SO_KEEPALIVE|BOOL|Canlı tutma gönderir.|
|SO_LINGER|`struct LINGER`|Lınger `Close` , veri gönderilmedi.|
|SO_OOBINLINE|BOOL|Bant dışı verileri normal veri akışında alırsınız.|
|SO_RCVBUF|**int**|Arabellek boyutu için alan belirtin.|
|SO_REUSEADDR|BOOL|Yuva zaten kullanımda olan bir adres bağlı olmasını sağlar. (Bkz [bağlama](#bind).)|
|SO_SNDBUF|**int**|Gönderen için arabellek boyutu belirtin.|
|TCP_NODELAY|BOOL|Gönderme birleşim Nagle algoritmasını devre dışı bırakır.|

Berkeley yazılım dağıtım (BSD) seçenekleri için desteklenmeyen `SetSockOpt` şunlardır:

|Değer|Tür|Açıklama|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Yuva dinliyor|
|SO_ERROR|**int**|Hata durumunu Al ve temizleyin.|
|SO_RCVLOWAT|**int**|Düşük su işareti alırsınız.|
|SO_RCVTIMEO|**int**|Zaman aşımı alma|
|SO_SNDLOWAT|**int**|Düşük su işareti gönderin.|
|SO_SNDTIMEO|**int**|Zaman aşımı gönderin.|
|SO_TYPE|**int**|Yuva türü.|
|IP_OPTIONS||IP üstbilgisinde seçenekleri alanını ayarlayın.|

##  <a name="shutdown"></a>  CAsyncSocket::ShutDown

Devre dışı bırakmak için bu üye işlevi gönderir, çağrı aldığında, veya her ikisini de yuvadaki.

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>Parametreler

*nHow*<br/>
Hangi tür işlem açıklayan bir bayrak artık, aşağıdaki numaralandırılmış değerlerden kullanarak izin verilir:

- **receives = 0**

- **gönderen = 1**

- **hem = 2**

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevi için geçerlidir:

- Başarılı WSANOTINITIALISED A [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API'yi kullanabilmek gerçekleşmelidir.

- WSAENETDOWN Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.

- WSAEINVAL *nHow* geçerli değil.

- WSAEINPROGRESS bir engelleme Windows Sockets işlemi devam ediyor.

- Yuva değil WSAENOTCONN (yalnızca SOCK_STREAM) bağlı.

- Bir yuva WSAENOTSOCK tanımlayıcısı değil.

### <a name="remarks"></a>Açıklamalar

`ShutDown` Yuva tüm türlerinde, alma, iletim veya her ikisini de devre dışı bırakmak için kullanılır. Varsa *nHow* 0 ise, sonraki üzerinde aldığı yuva izin verilmeyecek. Bu alt Protokolü katmanlardaki etkisizdir.

İletim Denetimi Protokolü (TCP) TCP penceresi değiştirilmez ve gelen verileri penceresi ulaşana kadar (ancak alınan değil) kabul edildi. Kullanıcı Veri Birimi Protokolü (UDP) gelen bir veri birimi kabul ve kuyruğa alındı. Hiçbir durumda bir ICMP hata paket oluşturulur. Varsa *nHow* 1 sonraki gönderir izin verilmiyor. TCP yuvaları için bir FIN gönderilir. Ayarı *nHow* hem de gönderen için 2 devre dışı bırakır ve yukarıda açıklanan şekilde alır.

Unutmayın `ShutDown` mu değil kapatmak için yuva bağlı kaynaklara ve yuva boşaltılmaz kadar `Close` çağrılır. Bir uygulama, onu kapatıldı sonra bir yuva yeniden için güvenmemelisiniz. Özellikle, Windows Sockets uygulaması kullanımını desteklemek için gerekli değildir `Connect` böyle bir yuvada.

### <a name="example"></a>Örnek

  Örneğin bakın [CAsyncSocket::OnReceive](#onreceive).

##  <a name="socket"></a>  CASyncSocket::Socket

Socket tanıtıcısı ayırır.

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

*lEvent*<br/>
Ağ olayları, uygulama, ilgileniyor bileşimini belirtir bir bit maskesi.

- `FD_READ`: Hazırlık okumak için bildirim almak istiyor.

- `FD_WRITE`: Yazma için hazırlık bildirim almak istiyor.

- `FD_OOB`: Bant dışı veri bildirim almak istiyor.

- `FD_ACCEPT`: Gelen bağlantıları bildirim almak istiyor.

- `FD_CONNECT`: Tamamlanan bağlantı bildirim almak istiyor.

- `FD_CLOSE`: Yuva kapatma bildirim almak istiyor.

*nProtocolType*<br/>
Belirtilen adresi ailesine özgü yuvası ile kullanılacak protokol.

*nAddressFormat*<br/>
Aile belirtimi adresi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `TRUE` başarı, `FALSE` başarısız.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir yuva işleyicisini ayırır. Çağrılmayan [CAsyncSocket::Bind](#bind) çağrısı yapması için belirtilen bir adrese yuvası bağlama `Bind` yuva daha sonra belirtilen bir adresin bağlanacağı. Kullanabileceğiniz [CAsyncSocket::SetSockOpt](#setsockopt) önce bağlı olarak yuva seçeneği ayarlamak için.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSocket Sınıfı](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile Sınıfı](../../mfc/reference/csocketfile-class.md)
