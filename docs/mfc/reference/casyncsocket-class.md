---
title: CAsyncSocket sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5eaefa40be2a6cf1d57326c2135d848fa08dbc87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="casyncsocket-class"></a>CAsyncSocket sınıfı
Bir Windows yuvasını temsil eder — ağ iletişimi bir uç nokta.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAsyncSocket : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|Oluşturan bir `CAsyncSocket` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncSocket::Accept](#accept)|Bir yuva bağlantısı kabul eder.|  
|[CAsyncSocket::AsyncSelect](#asyncselect)|Yuva için istekleri olay bildirimi.|  
|[CAsyncSocket::Attach](#attach)|Ekler için yuva tanıtıcı bir `CAsyncSocket` nesnesi.|  
|[CAsyncSocket::Bind](#bind)|Yerel bir adres yuvası ile ilişkilendirir.|  
|[CAsyncSocket::Close](#close)|Yuva kapatır.|  
|[CAsyncSocket::Connect](#connect)|Bir eş yuva bağlantı kurar.|  
|[CAsyncSocket::Create](#create)|Bir yuva oluşturur.|  
|[CAsyncSocket::Detach](#detach)|Socket tanıtıcısı gelen ayırır bir `CAsyncSocket` nesnesi.|  
|[CAsyncSocket::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CAsyncSocket` socket tanıtıcısı verilen nesnesi.|  
|[CAsyncSocket::GetLastError](#getlasterror)|Hata durumu başarısız olan son işlem alır.|  
|[CAsyncSocket::GetPeerName](#getpeername)|Yuvanın bağlı olduğu eş yuva adresini alır.|  
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Yuva bağlı (işleç IPv6 adresleri) sahip olduğu eş yuva adresini alır.|  
|[CAsyncSocket::GetSockName](#getsockname)|Bir yuva için yerel ad alır.|  
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Bir yuva (işleç IPv6 adresleri) için yerel ad alır.|  
|[CAsyncSocket::GetSockOpt](#getsockopt)|Bir yuva seçeneği alır.|  
|[CAsyncSocket::IOCtl](#ioctl)|Yuva modu denetler.|  
|[CAsyncSocket::Listen](#listen)|Gelen bağlantı isteklerini dinlemek için bir yuva oluşturur.|  
|[CAsyncSocket::Receive](#receive)|Veri yuvadan alır.|  
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Bir veri birimi alır ve kaynak adresini depolar.|  
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Bir veri birimi alır ve kaynak adresi (işleç IPv6 adresleri) depolar.|  
|[CAsyncSocket::Send](#send)|Bağlı bir yuva verileri gönderir.|  
|[CAsyncSocket::SendTo](#sendto)|Verileri belirli bir hedefe gönderir.|  
|[CAsyncSocket::SendToEx](#sendtoex)|Verileri belirli bir hedef (işleç IPv6 adresleri) gönderir.|  
|[CAsyncSocket::SetSockOpt](#setsockopt)|Bir yuva seçeneği ayarlar.|  
|[CAsyncSocket::ShutDown](#shutdown)|Devre dışı bırakır **Gönder** ve/veya **alma** yuvada çağırır.|  
|[CASyncSocket::Socket](#socket)|Socket tanıtıcısı ayırır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](#onaccept)|Bekleyen bağlantı istekleri çağırarak alabilen dinleme yuva bildirir **kabul**.|  
|[CAsyncSocket::OnClose](#onclose)|Yuva kendisine bağlı bir yuva kapattı bildirir.|  
|[CAsyncSocket::OnConnect](#onconnect)|Yuva bağlantı bağlantı denemesi olup başarıyla veya hata, tamamlandığını bildirir.|  
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|Bir alıcı yuva yuva, genellikle acil bir ileti okumak için bant dışı verileri olduğunu bildirir.|  
|[CAsyncSocket::OnReceive](#onreceive)|Dinleme yuva çağırarak alınacak veri olduğunu bildirir **alma**.|  
|[CAsyncSocket::OnSend](#onsend)|Bir yuva onu çağırarak veri gönderebilirsiniz bildirir **Gönder**.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncSocket::operator =](#operator_eq)|Yeni bir değer atayan bir `CAsyncSocket` nesnesi.|  
|[CAsyncSocket::operator YUVA](#operator_socket)|Almak için bu işleci kullanın **YUVA** , tanıtıcı `CAsyncSocket` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncSocket::m_hSocket](#m_hsocket)|Gösterir **YUVA** tanıtıcı bağlı için `CAsyncSocket` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf `CAsyncSocket` Windows yuva işlevleri MFC ile birlikte Windows Sockets kullanmak isteyen programcıları için bir nesne odaklı Özet sağlayan API yalıtır.  
  
 Bu sınıf, ağ iletişimleri anlamak varsayımına dayanır. Engelleme, bayt sırası farklar işlenmesinden sorumludur ve Unicode ve çok baytlı karakter arasında dönüştürmeler (MBCS) dizeleri ayarlayın. Bu sorunları tarafından yönetilir daha kullanışlı bir arabirim istiyorsanız bkz [CSocket](../../mfc/reference/csocket-class.md).  
  
 Kullanmak için bir `CAsyncSocket` nesne, kendi Oluşturucusu çağrısı'ı çağırın [oluşturma](#create) temel socket tanıtıcısı oluşturmak için işlevi (türü `SOCKET`), kabul edilen yuvalarda dışındaki. Bir sunucu yuva çağrısı [dinleme](#listen) üye işlevi ve bir istemci yuva çağrısı için [Bağlan](#connect) üye işlevi. Sunucu yuva çağırmalıdır [kabul](#accept) bağlantı isteği aldıklarında işlevi. Kalan kullanmak `CAsyncSocket` yuva arasındaki iletişimi yürütmek için işlevleri. Tamamlandıktan sonra destroy `CAsyncSocket` yıkıcı otomatik olarak çağırır; öbek üzerinde oluşturduysanız nesne [Kapat](#close) işlevi. `SOCKET` Veri türü makalesinde açıklanan [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md).  
  
> [!NOTE]
>  Statik olarak bağlantılı bir MFC uygulamasında İkincil iş parçacıklarındaki MFC yuva kullanırken çağırmalısınız `AfxSocketInit` yuva kitaplıklarını başlatma yuva kullanan her bir iş parçacığı. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığı denir.  
  
 Daha fazla bilgi için bkz: [Windows Yuvaları: sınıf Casyncsocket'ini kullanma](../../mfc/windows-sockets-using-class-casyncsocket.md) ve ilgili makaleler. yanı [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
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
 `rConnectedSocket`  
 Bağlantı için kullanılabilir olan yeni bir yuva tanımlayan bir başvuru.  
  
 `lpSockAddr`  
 Bir işaretçi bir [SOCKADDR](../../mfc/reference/sockaddr-structure.md) bağlanma adresi alır yapısı yuva, ağ üzerinde bilinen. Tam biçimi `lpSockAddr` bağımsız değişkeni, yuva oluşturulduğunda kurulan Adres ailesi tarafından belirlenir. Varsa `lpSockAddr` ve/veya `lpSockAddrLen` eşit olan **NULL**, kabul edilen yuva uzak adres hakkında hiçbir bilgi verilir.  
  
 `lpSockAddrLen`  
 Bir işaretçi adresi uzunluğu `lpSockAddr` bayt. `lpSockAddrLen` Değeri sonucu parametresi: başlangıçta gösterdiği alanı içermesi gereken `lpSockAddr`; döndürülen adres gerçek uzunluğunu (bayt cinsinden) içerecek dönüşte.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEFAULT** `lpSockAddrLen` değişken değeri çok küçük (boyutundan daha küçük bir [SOCKADDR](../../mfc/reference/sockaddr-structure.md) yapısı).  
  
- **WSAEINPROGRESS** engelleme Windows Sockets çağrı sürüyor.  
  
- **WSAEINVAL** `Listen` kabul etmek için çağrılan önceki değildi.  
  
- **WSAEMFILE** kabul etmek için giriş boş olduğundan ve hiçbir tanımlayıcıları kullanılabilir.  
  
- `WSAENOBUFS` Hiçbir arabellek alanı kullanılabilir.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAEOPNOTSUPP** başvurulan yuva bağlantı yönelimli hizmetini destekleyen bir tür değil.  
  
- **WSAEWOULDBLOCK** yuva işaretlenmiş olarak sayıda ve bağlantı kabul edilmesi için mevcut.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yordam bağlantıları bekleyen sırasındaki ilk bağlantı ayıklar, bu Yuva aynı özellikleri ile yeni bir yuva oluşturur ve ekler `rConnectedSocket`. Bekleyen bağlantı sıra üzerinde mevcut olup olmadığını **kabul** sıfır verir ve `GetLastError` bir hata döndürür. Kabul edilen yuva ( *rConnectedSocket)* daha fazla bağlantıları kabul etmek için kullanılamaz. Özgün yuva açık ve dinleme kalır.  
  
 Bağımsız değişken `lpSockAddr` yuva bağlantı adresi bilgileriyle doldurulan bir sonuç iletişimleri katmana bilinen parametresidir. **Kabul** yuva bağlantı tabanlı türleri ile aşağıdaki gibi kullanılır **SOCK_STREAM**.  
  
##  <a name="asyncselect"></a>  CAsyncSocket::AsyncSelect  
 Bir yuva için olay bildirimini istemek için bu üye işlevini çağırın.  
  
```  
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lEvent`  
 Ağ olayları uygulama ilgilenen bir birleşimini belirten bir bit maskesi.  
  
- **FD_READ** hazırlık okumak için bildirim alacak istiyor.  
  
- **FD_WRITE** verileri okumak kullanılabilir duruma geldiğinde bildirim almak istediğiniz.  
  
- **FD_OOB** bant dışı verileri varış bildirim almak istediğiniz.  
  
- **FD_ACCEPT** gelen bağlantıları bildirim almak istediğiniz.  
  
- **FD_CONNECT** bağlantı sonuçlarının bildirim almak istediğiniz.  
  
- **FD_CLOSE** yuva bir eş tarafından kapatıldığında bildirim almak istediğiniz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEINVAL** belirtilen parametrelerden biri geçersiz olduğunu gösterir.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, hangi MFC geri bildirim işlevleri için yuva çağrılacağı belirtmek için kullanılır. `AsyncSelect` otomatik olarak bu yuva sayıda moduna ayarlar. Daha fazla bilgi için bkz: [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="attach"></a>  CAsyncSocket::Attach  
 Bu üye işlevi ekleme çağrısı `hSocket` işlemek için bir `CAsyncSocket` nesnesi.  
  
```  
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `hSocket`  
 Bir yuva için bir tanıtıcı içerir.  
  
 `lEvent`  
 Ağ olayları uygulama ilgilenen bir birleşimini belirten bir bit maskesi.  
  
- **FD_READ** hazırlık okumak için bildirim alacak istiyor.  
  
- **FD_WRITE** verileri okumak kullanılabilir duruma geldiğinde bildirim almak istediğiniz.  
  
- **FD_OOB** bant dışı verileri varış bildirim almak istediğiniz.  
  
- **FD_ACCEPT** gelen bağlantıları bildirim almak istediğiniz.  
  
- **FD_CONNECT** bağlantı sonuçlarının bildirim almak istediğiniz.  
  
- **FD_CLOSE** yuva bir eş tarafından kapatıldığında bildirim almak istediğiniz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 **YUVA** tanıtıcı nesnesinin içinde depolanan [m_hSocket](#m_hsocket) veri üyesi.  
  
##  <a name="bind"></a>  CAsyncSocket::Bind  
 Yerel bir adres yuvası ile ilişkilendirmek için bu üye işlevini çağırın.  
  
```  
BOOL Bind(
    UINT nSocketPort,  
    LPCTSTR lpszSocketAddress = NULL);

 
BOOL Bind (
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>Parametreler  
 `nSocketPort`  
 Yuva uygulamasını tanımlayan bağlantı noktası.  
  
 `lpszSocketAddress`  
 Ağ adresi "128.56.22.8" gibi bir noktalı sayı olabilir. Geçirme **NULL** bu parametresi için dize **CAsyncSocket** örneği istemci etkinliği tüm ağ arabirimlerindeki dinler.  
  
 `lpSockAddr`  
 Bir işaretçi bir [SOCKADDR](../../mfc/reference/sockaddr-structure.md) bu yuva atamak için bir adres içeriyor yapısı.  
  
 `nSockAddrLen`  
 Adresi uzunluğu `lpSockAddr` bayt.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEADDRINUSE** belirtilen adresi zaten kullanılıyor. (Bkz **SO_REUSEADDR** yuva seçeneği altında [SetSockOpt](#setsockopt).)  
  
- **WSAEFAULT** `nSockAddrLen` değişken değeri çok küçük (boyutundan daha küçük bir [SOCKADDR](../../mfc/reference/sockaddr-structure.md) yapısı).  
  
- **WSAEINPROGRESS** engelleme Windows Sockets çağrı sürüyor.  
  
- **WSAEAFNOSUPPORT** belirtilen adres ailesi bu bağlantı noktası tarafından desteklenmiyor.  
  
- **WSAEINVAL** yuva için bir adres zaten bağlı.  
  
- `WSAENOBUFS` Yeterli kullanılabilir arabellek, çok fazla bağlantı.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yordam bir bağlantısız veri birimi veya akışa yuva önce kullanılan sonraki **Bağlan** veya `Listen` çağrıları. Bağlantı isteklerini kabul edebilmesi için önce bir dinleme sunucu gerekir bir port numarası seçin ve yuva için Windows Sockets çağırarak bilinen kolaylaştırır **bağlama**. **Bağlama** adsız bir yuva için yerel ad atayarak yerel bir ilişkilendirme (ana bilgisayar adresini/bağlantı noktası numarası) yuva oluşturur.  
  
##  <a name="casyncsocket"></a>  CAsyncSocket::CAsyncSocket  
 Boş yuva nesnesi oluşturur.  
  
```  
CAsyncSocket();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne oluşturma sonra çağırmalısınız kendi **oluşturma** oluşturmak için üye işlevi **YUVA** veri yapısı ve adresini bağlayın. (Dinleme yuva kullanmak için bir yuva oluşturduğunda Windows Sockets iletişim, sunucu tarafındaki **kabul** çağrısı, arama **oluşturma** o yuva için.)  
  
##  <a name="close"></a>  CAsyncSocket::Close  
 Yuva kapatır.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, böylece daha ayrıntılı başvuru hatası ile başarısız olur, yuva tanımlayıcısı serbest bırakır **WSAENOTSOCK**. Bu temel yuva son referansı ise, sıraya alınan verilere ve ilişkili adlandırma bilgileri atılır. Yuva nesnenin yıkıcı çağrıları **Kapat** sizin için.  
  
 İçin `CAsyncSocket`, ancak için `CSocket`, semantiği **Kapat** yuva seçenekleri tarafından etkilenen **SO_LINGER** ve **SO_DONTLINGER**. Daha fazla bilgi için üye işlevine bakın `GetSockOpt`.  
  
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
 `lpszHostAddress`  
 Bu nesne bağlı yuva ağ adresi: "ftp.microsoft.com" veya "128.56.22.8" gibi noktalı sayı gibi bir makine adı.  
  
 `nHostPort`  
 Yuva uygulamasını tanımlayan bağlantı noktası.  
  
 `lpSockAddr`  
 Bir işaretçi bir [SOCKADDR](../../mfc/reference/sockaddr-structure.md) bağlı bir yuva adresini içeren yapısı.  
  
 `nSockAddrLen`  
 Adresi uzunluğu `lpSockAddr` bayt.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Bu hata kodu gösteriyorsa **WSAEWOULDBLOCK**ve uygulamanızı geçersiz kılınabilir geri çağırmaları kullanarak, uygulamanızın alacak bir `OnConnect` bağlanma işlemi tamamlandığında, ileti. Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEADDRINUSE** belirtilen adresi zaten kullanılıyor.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets çağrı sürüyor.  
  
- **WSAEADDRNOTAVAIL** belirtilen adresi yerel makinede kullanılabilir değil.  
  
- **WSAEAFNOSUPPORT** adresleri belirtilen ailesindeki bu yuvası ile kullanılamaz.  
  
- **WSAECONNREFUSED** bağlanma girişimi reddedildi.  
  
- **WSAEDESTADDRREQ** hedef adresi gereklidir.  
  
- **WSAEFAULT** `nSockAddrLen` bağımsız değişkeni yanlış.  
  
- **WSAEINVAL** geçersiz ana bilgisayar adresi.  
  
- **WSAEISCONN** Yuva zaten bağlı.  
  
- **WSAEMFILE** hiçbir daha fazla dosya tanımlayıcıları kullanılabilir.  
  
- **WSAENETUNREACH** ağ şu anda bu konaktan erişilemiyor.  
  
- `WSAENOBUFS` Hiçbir arabellek alanı kullanılabilir. Yuva bağlanamaz.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAETIMEDOUT** bağlantı kurmadan sonuyla bağlanmayı dener.  
  
- **WSAEWOULDBLOCK** yuva işaretlenmiş olarak sayıda ve bağlantı hemen tamamlanamıyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Yuva ilişkisiz ise, sistem tarafından atanmış benzersiz değerler için yerel bir ilişkilendirme ve yuva olarak işaretlenmiş bağlı. Unutmayın tümüyle sıfırlardan adresi alandır adı yapısının **Bağlan** sıfır döndürür. Genişletilmiş hata bilgilerini için arama `GetLastError` üye işlevi.  
  
 Akış yuvaları için (tür **SOCK_STREAM**), etkin bir bağlantı yabancı konağa başlatılır. Yuva çağrısı başarıyla tamamlandığında, yuva veri Gönder/Al hazırdır.  
  
 Veri birimi yuva için (tür **SOCK_DGRAM**), hangi üzerinde sonraki kullanılacak varsayılan hedef ayarlanır **Gönder** ve **alma** çağrıları.  
  
##  <a name="create"></a>  CAsyncSocket::Create  
 Çağrı **oluşturma** Windows yuva oluşturmak ve bunu eklemek için yuva nesnesi oluşturma sonra üye işlevi.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nSocketPort`  
 Bir bağlantı noktasını seçmek için Windows Sockets istiyorsanız yuva veya 0 ile kullanılmak üzere iyi bilinen bağlantı noktası.  
  
 `nSocketType`  
 **SOCK_STREAM** veya **SOCK_DGRAM**.  
  
 `lEvent`  
 Ağ olayları uygulama ilgilenen bir birleşimini belirten bir bit maskesi.  
  
- **FD_READ** hazırlık okumak için bildirim alacak istiyor.  
  
- **FD_WRITE** hazırlığı yazmak için bildirim alacak istiyor.  
  
- **FD_OOB** bant dışı verileri varış bildirim almak istediğiniz.  
  
- **FD_ACCEPT** gelen bağlantıları bildirim almak istediğiniz.  
  
- **FD_CONNECT** tamamlanmış bağlantı bildirim almak istediğiniz.  
  
- **FD_CLOSE** yuva kapatma bildirim almak istediğiniz.  
  
 *lpszSockAddress*  
 Bağlı bir yuva, noktalı sayıyı "128.56.22.8" gibi ağ adresini içeren bir dize için bir işaretçi. Geçirme **NULL** bu parametresi için dize **CAsyncSocket** örneği istemci etkinliği tüm ağ arabirimlerindeki dinler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEAFNOSUPPORT** belirtilen adres ailesi desteklenmiyor.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAEMFILE** hiçbir daha fazla dosya tanımlayıcıları kullanılabilir.  
  
- `WSAENOBUFS` Hiçbir arabellek alanı kullanılabilir. Yuva oluşturulamıyor.  
  
- **WSAEPROTONOSUPPORT** belirtilen bağlantı noktası desteklenmiyor.  
  
- **WSAEPROTOTYPE** belirtilen bağlantı noktası bu yuva için yanlış türüdür.  
  
- **WSAESOCKTNOSUPPORT** bu adres ailesinde belirtilen yuva türü desteklenmiyor.  
  
### <a name="remarks"></a>Açıklamalar  
 **Oluşturma** çağrıları [yuva](#socket) ve başarılı olursa, çağıran [bağlamak](#bind) belirtilen adresine yuvası bağlama. Şu yuva türleri desteklenir:  
  
- **SOCK_STREAM** sağlar sıralı, güvenilir, tam çift yönlü, bağlantı tabanlı bayt akışları. İletim Denetimi Protokolü (TCP) Internet adresi ailesini kullanır.  
  
- **SOCK_DGRAM** bağlantısız, güvenilir olmayan paketlerin sabit (genellikle küçük) maksimum uzunluktaki veri birimleri destekler. Kullanıcı Veri Birimi Protokolü (UDP) Internet adresi ailesini kullanır.  
  
    > [!NOTE]
    >  **Kabul** üye işlevi yeni, boş bir başvuru alır `CSocket` , parametre olarak nesne. Arama yapmadan önce bu nesneyi oluşturmalıdır **kabul**. Aklınızda bu yuva nesnesi kapsamını, bağlantıyı kapatır kalırsa. Çağırmayın **oluşturma** bu yeni yuva nesnesi için.  
  
> [!IMPORTANT]
> **Oluşturma** olan **değil** iş parçacığı.  Burada, aynı anda farklı iş parçacıkları tarafından çağırılabilir, çok iş parçacıklı bir ortamda arıyorsanız, her bir mutex ya da diğer eşitleme kilit çağrısıyla korumak emin olun.  
  
 Akış ve veri birimi yuvaları hakkında daha fazla bilgi için makalelerine bakın [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md) ve [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../../mfc/windows-sockets-ports-and-socket-addresses.md) ve [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="detach"></a>  CAsyncSocket::Detach  
 Kullanımdan çıkarmak için bu üye işlevini çağırın **YUVA** içinde işlemek `m_hSocket` veri üyeden `CAsyncSocket` nesne ve ayarlayın `m_hSocket` için **NULL**.  
  
```  
SOCKET Detach();
```  
  
##  <a name="fromhandle"></a>  CAsyncSocket::FromHandle  
 Bir işaretçi döndüren bir `CAsyncSocket` nesnesi.  
  
```  
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Parametreler  
 `hSocket`  
 Bir yuva için bir tanıtıcı içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CAsyncSocket` nesnesi veya **NULL** yoksa hiçbir `CAsyncSocket` nesne iliştirilmiş `hSocket`.  
  
### <a name="remarks"></a>Açıklamalar  
 Verildiğinde bir **YUVA** işlemek, bir `CAsyncSocket` nesne tanıtıcısını iliştirilmemiş, üye işlevinin döndürdüğü **NULL**.  
  
##  <a name="getlasterror"></a>  CAsyncSocket::GetLastError  
 Başarısız olan son işlem için hata durumunu almak için bu üye işlevini çağırın.  
  
```  
static int PASCAL GetLastError();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri, bu iş parçacığı tarafından gerçekleştirilen son Windows Sockets API yordamı için hata kodu gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli üye işlevi bir hata oluştuğunu gösteren zaman `GetLastError` uygun hata kodu almak için çağrılmalıdır. İlgili hata kodları tek tek üye işlevi açıklamaları bir listesi için bkz.  
  
 Hata kodları hakkında daha fazla bilgi için bkz: [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="getpeername"></a>  CAsyncSocket::GetPeerName  
 Bu yuvanın bağlı olduğu eş yuva adresini almak için bu üye işlevini çağırın.  
  
```  
BOOL GetPeerName(
    CString& rPeerAddress,  
    UINT& rPeerPort);

 
BOOL GetPeerName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>Parametreler  
 `rPeerAddress`  
 Başvuru bir `CString` noktalı sayı bir IP adresi alan nesnesi.  
  
 `rPeerPort`  
 Başvuru bir **UINT** bir bağlantı noktası depolar.  
  
 `lpSockAddr`  
 Bir işaretçi [SOCKADDR](../../mfc/reference/sockaddr-structure.md) yapısı eş yuva adını alır.  
  
 `lpSockAddrLen`  
 Bir işaretçi adresi uzunluğu `lpSockAddr` bayt. Geri dönüş, `lpSockAddrLen` bağımsız değişkeni içeren gerçek boyutuna `lpSockAddr` bayt cinsinden döndürdü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEFAULT** `lpSockAddrLen` bağımsız değişken yeterince büyük değil.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets çağrı sürüyor.  
  
- **WSAENOTCONN** Yuva bağlı değil.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
### <a name="remarks"></a>Açıklamalar  
 IPv6 adresleri işlemek için kullanmak [CAsyncSocket::GetPeerNameEx](#getpeernameex).  
  
##  <a name="getpeernameex"></a>  CAsyncSocket::GetPeerNameEx  
 Bu yuva bağlı (işleç IPv6 adresleri) sahip olduğu eş yuva adresini almak için bu üye işlevini çağırın.  
  
```  
BOOL GetPeerNameEx(
    CString& rPeerAddress,  
    UINT& rPeerPort);
```  
  
### <a name="parameters"></a>Parametreler  
 `rPeerAddress`  
 Başvuru bir `CString` noktalı sayı bir IP adresi alan nesnesi.  
  
 `rPeerPort`  
 Başvuru bir **UINT** bir bağlantı noktası depolar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEFAULT** `lpSockAddrLen` bağımsız değişken yeterince büyük değil.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets çağrı sürüyor.  
  
- **WSAENOTCONN** Yuva bağlı değil.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev aynıdır [CAsyncSocket::GetPeerName](#getpeername) IPv6 işleme dışında de olarak eski protokollere giderir.  
  
##  <a name="getsockname"></a>  CAsyncSocket::GetSockName  
 Bir yuva için yerel adını almak için bu üye işlevini çağırın.  
  
```  
BOOL GetSockName(
    CString& rSocketAddress,  
    UINT& rSocketPort);

 
BOOL GetSockName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSocketAddress`  
 Başvuru bir `CString` noktalı sayı bir IP adresi alan nesnesi.  
  
 `rSocketPort`  
 Başvuru bir **UINT** bir bağlantı noktası depolar.  
  
 `lpSockAddr`  
 Bir işaretçi bir [SOCKADDR](../../mfc/reference/sockaddr-structure.md) yuva adresi alır yapısı.  
  
 `lpSockAddrLen`  
 Bir işaretçi adresi uzunluğu `lpSockAddr` bayt.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEFAULT** `lpSockAddrLen` bağımsız değişken yeterince büyük değil.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAEINVAL** yuva adresine ile bağlı değil **bağlama**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu çağrı ne zaman özellikle yararlı olur bir **Bağlan** çağrısı yapılması olmadan sağlandıktan bir **bağlamak** ilk; bu çağrı olarak belirleyebilirsiniz hangi tarafından ayarlanmış yerel bir ilişkilendirme yalnızca sağlar Sistem.  
  
 IPv6 adresleri işlemek için kullanmak [CAsyncSocket::GetSockNameEx](#getsocknameex)  
  
##  <a name="getsocknameex"></a>  CAsyncSocket::GetSockNameEx  
 Bir yuva (işleç IPv6 adresleri) için yerel adını almak için bu üye işlevini çağırın.  
  
```  
BOOL GetSockNameEx(
    CString& rSocketAddress,  
    UINT& rSocketPort);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSocketAddress`  
 Başvuru bir `CString` noktalı sayı bir IP adresi alan nesnesi.  
  
 `rSocketPort`  
 Başvuru bir **UINT** bir bağlantı noktası depolar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEFAULT** `lpSockAddrLen` bağımsız değişken yeterince büyük değil.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAEINVAL** yuva adresine ile bağlı değil **bağlama**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu çağrı aynıdır [CAsyncSocket::GetSockName](#getsockname) IPv6 işleme dışında de olarak eski protokollere giderir.  
  
 Bu çağrı ne zaman özellikle yararlı olur bir **Bağlan** çağrısı yapılması olmadan sağlandıktan bir **bağlamak** ilk; bu çağrı olarak belirleyebilirsiniz hangi tarafından ayarlanmış yerel bir ilişkilendirme yalnızca sağlar Sistem.  
  
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
 `nOptionName`  
 Değeri alınacak olduğu yuva seçeneği.  
  
 `lpOptionValue`  
 İstenen seçeneğine ilişkin değer döndürülecek arabellek için bir işaretçi. Arabellekte döndürülen seçeneği ile ilişkili değer `lpOptionValue`. Tarafından için tamsayı işaret `lpOptionLen` bayt; bu arabellek boyutu başlangıçta içermelidir ve getirisi, bu döndürülen değer boyutuna ayarlanır. İçin **SO_LINGER**, bu boyutunu olacaktır bir `LINGER` yapısı; tüm diğer seçenekleri için boyutunu olacak bir **BOOL** veya bir `int`seçeneğine bağlı olarak. Seçenekler ve boyutlarının açıklamalar bölümünde listesine bakın.  
  
 `lpOptionLen`  
 Bir işaretçi boyutunu `lpOptionValue` arabelleğinin bayt cinsinden.  
  
 `nLevel`  
 Seçenek tanımlandığı düzeyi; yalnızca desteklenen düzeyler **SOL_SOCKET** ve **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Bir seçenek ile belirlenmemişse `SetSockOpt`, ardından `GetSockOpt` seçeneği için varsayılan değeri döndürür. Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEFAULT** `lpOptionLen` bağımsız değişkeni geçersiz.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAENOPROTOOPT** bilinmeyen veya desteklenmeyen bir seçenektir. Özellikle, **SO_BROADCAST** türü yuvalarda desteklenmeyen **SOCK_STREAM**, sırada **SO_ACCEPTCONN**, **SO_DONTLINGER**,  **SO_KEEPALIVE**, **SO_LINGER**, ve **SO_OOBINLINE** türü yuvalarda desteklenmeyen **SOCK_DGRAM**.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetSockOpt` herhangi bir durum içinde herhangi bir türde bir yuvası ile ilişkili bir yuva seçeneği için geçerli değer alır ve sonuçta depolar `lpOptionValue`. Seçenekler, paketler, bant dışı veri aktarımı ve benzeri yönlendirme gibi yuva işlemlerini etkiler.  
  
 Aşağıdaki seçenekler için desteklenen `GetSockOpt`. Türü tarafından ele veri türünü tanımlayan `lpOptionValue`. **TCP_NODELAY** seçeneğini kullanan düzeyi **IPPROTO_TCP**; diğer tüm seçenekleri düzeyini kullanmak **SOL_SOCKET**.  
  
|Değer|Tür|Açıklama|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Yuva dinliyor.|  
|**SO_BROADCAST**|**BOOL**|Yuva yayın iletilerini aktarım için yapılandırılır.|  
|**SO_DEBUG**|**BOOL**|Hata ayıklama etkin.|  
|**SO_DONTLINGER**|**BOOL**|TRUE ise, **SO_LINGER** seçeneği devre dışıdır.|  
|**SO_DONTROUTE**|**BOOL**|Yönlendirme devre dışı bırakılır.|  
|**SO_ERROR**|`int`|Hata durumunu almak ve temizleyin.|  
|**SO_KEEPALIVE**|**BOOL**|Etkin tutma gönderiliyor.|  
|**SO_LINGER**|**LINGER yapısı**|Geçerli lınger seçeneklerini döndürür.|  
|**SO_OOBINLINE**|**BOOL**|Bant dışı verileri normal veri akışında alınır.|  
|**SO_SNDBUF**|`int`|Arabellek boyutu için alır.|  
|**SO_REUSEADDR**|**BOOL**|Yuva zaten kullanımda olan bir adres bağlanabilir.|  
|**SO_SNDBUF**|`int`|Arabellek boyutu için gönderir.|  
|**SO_TYPE**|`int`|Yuva türü (örneğin, **SOCK_STREAM**).|  
|**TCP_NODELAY**|**BOOL**|Gönderme birleştirmesi için Nagle algoritmayı devre dışı bırakır.|  
  
 Berkeley Software Distribution (BSD) seçenekleri desteklenmiyor `GetSockOpt` şunlardır:  
  
|Değer|Tür|Açıklama|  
|-----------|----------|-------------|  
|**SO_RCVLOWAT**|`int`|Düşük su işareti alırsınız.|  
|**SO_RCVTIMEO**|`int`|Zaman aşımı alırsınız.|  
|**SO_SNDLOWAT**|`int`|Düşük su işareti gönderin.|  
|**SO_SNDTIMEO**|`int`|Zaman aşımı gönderin.|  
|**IP_OPTIONS**||Seçenekler IP üstbilgisinde alın.|  
|**TCP_MAXSEG**|`int`|TCP en büyük kesim boyutu alın.|  
  
 Çağırma `GetSockOpt` desteklenmeyen bir seçenek hata kodunu sonuçlanır **WSAENOPROTOOPT** öğesinden döndürülen `GetLastError`.  
  
##  <a name="ioctl"></a>  CAsyncSocket::IOCtl  
 Bir yuva modunu denetlemek için bu üye işlevini çağırın.  
  
```  
BOOL IOCtl(
    long lCommand,  
    DWORD* lpArgument);
```  
  
### <a name="parameters"></a>Parametreler  
 `lCommand`  
 Yuva gerçekleştirmek için komutu.  
  
 `lpArgument`  
 İçin bir parametre için bir işaretçi `lCommand`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEINVAL** `lCommand` geçerli bir komut değil veya `lpArgument` için kabul edilebilir bir parametre değil `lCommand`, ya da komut sağlanan yuva türü için geçerli değil.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yordam, herhangi bir durum herhangi bir yuvada üzerinde kullanılabilir. Almak veya yuvasıyla protokolü ve iletişim alt sistemi bağımsız ilişkili işletim parametrelerini almak için kullanılır. Aşağıdaki komutlar desteklenir:  
  
- **FIONBIO** etkinleştirmek veya yuvadaki sayıda modunu devre dışı bırakın. `lpArgument` Parametresi işaret konumundaki bir `DWORD`, hangi sayıda modu etkinleştirilecek ise sıfır olmayan ve sıfır olur devre dışı. Varsa `AsyncSelect` herhangi kullanma girişimi sonra bir yuvada yayınlamıştır **IOCTL** yuva geri engelleme modu ayarlamak için başarısız **WSAEINVAL**. Yuva geri engelleme modu olarak ayarlanmış ve engellemek için **WSAEINVAL** hata, bir uygulama olmalıdır önce devre dışı `AsyncSelect` çağırarak `AsyncSelect` ile `lEvent` parametresi 0'a eşit'ı çağırın **IOCTL** .  
  
- **FIONREAD** biriyle okunan bayt sayısını belirlemek **alma** bu yuvadan çağırın. `lpArgument` Parametresi işaret konumundaki bir `DWORD` , **IOCTL** sonucu depolar. Bu yuva türü ise **SOCK_STREAM**, **FIONREAD** tek bir toplam hangi okunabilecek veri miktarını döndürür **alma**; Bu normalde toplam miktarı ile aynı olur Veri yuvada sıraya alındı. Bu yuva türü ise **SOCK_DGRAM**, **FIONREAD** ilk veri birimi boyutu sıraya yuvada döndürür.  
  
- **SIOCATMARK** tüm bant dışı verileri okuma olup olmadığını belirler. Bu tür bir yuva geçerlidir **SOCK_STREAM** yapılandırılmış satır içi herhangi bir bant dışı veri alımını ( **SO_OOBINLINE**). Bant dışı verileri okumak için bekliyorsa işlemi sıfır olmayan bir değer döndürür. Aksi halde 0 ve sonraki döndürür **alma** veya `ReceiveFrom` üzerinde gerçekleştirilen yuva bazı veya tüm "işareti" önceki verileri alır; uygulama kullanması gereken **SIOCATMARK** işlemi herhangi bir veri kalır olup olmadığını belirler. "Acil" (bant-) verilerin önceki herhangi bir normal veri varsa, sırayla alınır. (Unutmayın bir **alma** veya `ReceiveFrom` aynı çağrı bant dışı ve normal verilerde hiçbir zaman karışık.) `lpArgument` Parametresi işaret konumundaki bir `DWORD` , **IOCTL** sonucu depolar.  
  
 Bu işlev bir alt kümesidir **ioctl()** Berkeley yuva kullanılır. Özellikle, eşdeğerdir komutu yoktur **FIOASYNC**, sırada **SIOCATMARK** desteklenmeyen yalnızca yuva düzeyi komutu.  
  
##  <a name="listen"></a>  CAsyncSocket::Listen  
 Gelen bağlantı isteklerini dinlemek için bu üye işlevini çağırın.  
  
```  
BOOL Listen(int nConnectionBacklog = 5);
```  
  
### <a name="parameters"></a>Parametreler  
 *nConnectionBacklog*  
 Sıranın bağlantıları bekleyen büyüyebileceği maksimum uzunluğu. Geçerli aralık 1'den 5 ' dir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEADDRINUSE** bir adres kullanılıyor dinlemek için bir girişimde bulunuldu.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAEINVAL** yuva ile bağlı değil **bağlamak** veya zaten bağlı.  
  
- **WSAEISCONN** Yuva zaten bağlı.  
  
- **WSAEMFILE** hiçbir daha fazla dosya tanımlayıcıları kullanılabilir.  
  
- `WSAENOBUFS` Hiçbir arabellek alanı kullanılabilir.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAEOPNOTSUPP** başvurulan yuva destekleyen bir tür değil `Listen` işlemi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantıları kabul etmek üzere yuva ilk ile oluşturulan **oluşturma**, gelen bağlantılar için bir biriktirme listesi ile belirtilen `Listen`, ve ardından ile bağlantıları kabul **kabul**. `Listen` diğer bir deyişle, bağlantılar, destekleyen yuva türü içeriğiyle uygular **SOCK_STREAM**. Bu Yuva kabul işlem tarafından sıraya alınan gelen bağlantıları burada onaylanır ve "pasif" moduna alın.  
  
 Bu işlev genellikle sunucuları (veya bağlantılarını kabul edecek şekilde istediği herhangi bir uygulama) tarafından kullanılan aynı anda birden fazla bağlantı isteği sahip: bir bağlantı isteği kuyruğu dolu alınırsa, istemci durumilebirhataalacaksınız **WSAECONNREFUSED**.  
  
 `Listen` kullanılabilir bağlantı noktası (tanımlayıcı) olduğunda rationally çalışmaya devam etmeyi dener. Sıranın boşaltılır kadar bağlantılarını kabul eder. Bağlantı noktaları yayımlanırsa sonraki çağrı `Listen` veya **kabul** geçerli veya en son "biriktirme," kuyruğuna mümkünse Dolum ve gelen bağlantıları dinlemeyi sürdürün.  
  
##  <a name="m_hsocket"></a>  CAsyncSocket::m_hSocket  
 İçeren **YUVA** işlemek için bu tarafından kapsüllenmiş yuva `CAsyncSocket` nesnesi.  
  
```  
SOCKET m_hSocket;  
```  
  
##  <a name="onaccept"></a>  CAsyncSocket::OnAccept  
 Bekleyen bağlantı istekleri çağırarak alabilen dinleme yuva bildirmek için framework tarafından çağrılan [kabul](#accept) üye işlevi.  
  
```  
virtual void OnAccept(int nErrorCode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nErrorCode`  
 En son Yuva hatası. Aşağıdaki hata kodları uygulandığı `OnAccept` üye fonksiyonu:  
  
- **0** başarıyla yürütüldü işlevi.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onclose"></a>  CAsyncSocket::OnClose  
 Bu yuva bağlı bir yuva kendi işlem tarafından kapalı olduğunu bildirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnClose(int nErrorCode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nErrorCode`  
 En son Yuva hatası. Aşağıdaki hata kodları uygulamak `OnClose` üye fonksiyonu:  
  
- **0** başarıyla yürütüldü işlevi.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAECONNRESET** bağlantı uzak yan yana sıfırlandı.  
  
- **WSAECONNABORTED** bağlantı zaman aşımı veya diğer hata nedeniyle iptal edildi.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onconnect"></a>  CAsyncSocket::OnConnect  
 Bu yuva bağlantı, bağlantı girişimi, başarılı bir şekilde veya hata olup olmadığını tamamlandığını bildirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnConnect(int nErrorCode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nErrorCode`  
 En son Yuva hatası. Aşağıdaki hata kodları uygulamak `OnConnect` üye fonksiyonu:  
  
- **0** başarıyla yürütüldü işlevi.  
  
- **WSAEADDRINUSE** belirtilen adresi zaten kullanılıyor.  
  
- **WSAEADDRNOTAVAIL** belirtilen adresi yerel makinede kullanılabilir değil.  
  
- **WSAEAFNOSUPPORT** adresleri belirtilen ailesindeki bu yuvası ile kullanılamaz.  
  
- **WSAECONNREFUSED** bağlanma girişimi zorla reddedildi.  
  
- **WSAEDESTADDRREQ** hedef adresi gereklidir.  
  
- **WSAEFAULT** `lpSockAddrLen` bağımsız değişkeni yanlış.  
  
- **WSAEINVAL** yuva için bir adres zaten bağlı.  
  
- **WSAEISCONN** Yuva zaten bağlı.  
  
- **WSAEMFILE** hiçbir daha fazla dosya tanımlayıcıları kullanılabilir.  
  
- **WSAENETUNREACH** ağ şu anda bu konaktan erişilemiyor.  
  
- `WSAENOBUFS` Hiçbir arabellek alanı kullanılabilir. Yuva bağlanamaz.  
  
- **WSAENOTCONN** Yuva bağlı değil.  
  
- **WSAENOTSOCK** bir dosyayı bir yuva tanımlayıcıdır.  
  
- **WSAETIMEDOUT** bağlanma girişimi bağlantı kurmadan zaman aşımına uğradı.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  İçinde [CSocket](../../mfc/reference/csocket-class.md), `OnConnect` bildirim işlevi hiçbir zaman çağrılır. Bağlantılar için yalnızca çağrısı **Bağlan**, hangi döndürecektir bağlantı (başarıyla veya hata) tamamlandığında. Bağlantı bildirimleri işlenme bir MFC uygulaması ayrıntı olur.  
  
 Daha fazla bilgi için bkz: [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]  
  
##  <a name="onoutofbanddata"></a>  CAsyncSocket::OnOutOfBandData  
 Gönderen yuva göndermek için bant dışı verileri içeren alıcı yuva bildirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnOutOfBandData(int nErrorCode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nErrorCode`  
 En son Yuva hatası. Aşağıdaki hata kodları uygulamak `OnOutOfBandData` üye fonksiyonu:  
  
- **0** başarıyla yürütüldü işlevi.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bant dışı verilerdir her tür bağlı yuva çifti ile ilişkili bir mantıksal olarak bağımsızdır kanal **SOCK_STREAM**. Kanal genellikle Acil veri göndermek için kullanılır.  
  
 MFC sınıf kullanıcılarının ancak bant dışı verileri destekler `CAsyncSocket` kullanmasını önerilmez. En kolay yolu, bu tür veri geçirme için ikinci bir yuva oluşturmaktır. Bant dışı verileri hakkında daha fazla bilgi için bkz: [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onreceive"></a>  CAsyncSocket::OnReceive  
 Bu yuva olduğunu veri çağırarak alınabilir arabelleği bildirmek için framework tarafından çağrılan **alma** üye işlevi.  
  
```  
virtual void OnReceive(int nErrorCode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nErrorCode`  
 En son Yuva hatası. Aşağıdaki hata kodları uygulamak `OnReceive` üye fonksiyonu:  
  
- **0** başarıyla yürütüldü işlevi.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]  
  
##  <a name="onsend"></a>  CAsyncSocket::OnSend  
 Şimdi veri çağırarak gönderebilmesi gerektiğini yuva bildirmek için framework tarafından çağrılan **Gönder** üye işlevi.  
  
```  
virtual void OnSend(int nErrorCode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nErrorCode`  
 En son Yuva hatası. Aşağıdaki hata kodları uygulamak `OnSend` üye fonksiyonu:  
  
- **0** başarıyla yürütüldü işlevi.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [Windows Yuvaları: Yuva bildirimleri](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]  
  
##  <a name="operator_eq"></a>  CAsyncSocket::operator =  
 Yeni bir değer atayan bir `CAsyncSocket` nesnesi.  
  
```  
void operator=(const CAsyncSocket& rSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSrc`  
 Var olan bir başvuru `CAsyncSocket` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Var olan kopyalamak için bu işlevi çağırmak `CAsyncSocket` başka bir nesneye `CAsyncSocket` nesnesi.  
  
##  <a name="operator_socket"></a>  CAsyncSocket::operator YUVA  
 Almak için bu işleci kullanın **YUVA** , tanıtıcı `CAsyncSocket` nesnesi.  
  
```  
operator SOCKET() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, işleyicisini **YUVA** nesne; Aksi halde, **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows API'larını doğrudan çağırmak için tanıtıcı kullanabilirsiniz.  
  
##  <a name="receive"></a>  CAsyncSocket::Receive  
 Bir yuvadan verileri almak için bu üye işlevini çağırın.  
  
```  
virtual int Receive(
    void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpBuf`  
 Gelen veriler için bir arabellek.  
  
 `nBufLen`  
 Uzunluğu `lpBuf` bayt.  
  
 `nFlags`  
 Aramanın yapılıp yapılmadığı yolunu belirtir. Bu işlev semantiği yuva seçenekleri tarafından belirlenir ve `nFlags` parametresi. İkinci aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulan `OR` işleci:  
  
- **MSG_PEEK** gelen veri Gözat. Verileri arabelleğe kopyalanır, ancak giriş sıradan kaldırılmadı.  
  
- **MSG_OOB** işlem bant dışı verileri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Herhangi bir hata oluşursa, **alma** alınan bayt sayısını döndürür. Bağlantı kapatıldı 0 döndürür. Aksi takdirde değerini **SOCKET_ERROR** döndürülür ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAENOTCONN** Yuva bağlı değil.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAEOPNOTSUPP MSG_OOB** belirtildi, ancak yuva türü değil **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** yuva kapatıldı; çağırmak olası değil **alma** sonra bir yuvada `ShutDown` ile çağrılmış `nHow` 0 veya 2'ye ayarlayın.  
  
- **WSAEWOULDBLOCK** yuva işaretlenmiş olarak sayıda ve **alma** işlem engellendi.  
  
- **WSAEMSGSIZE** veri birimi belirtilen belleğe sığmayacak kadar büyük ve kesildi.  
  
- **WSAEINVAL** yuva ile bağlı değil **bağlama**.  
  
- **WSAECONNABORTED** sanal devreyi zaman aşımı veya diğer hata nedeniyle iptal edildi.  
  
- **WSAECONNRESET** sanal devreyi uzak yan yana sıfırlandı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bağlı akış veya veri birimi yuvaları için kullanılır ve gelen verileri okumak için kullanılır.  
  
 Yuva türü için **SOCK_STREAM**, sağlanan arabellek boyutu en fazla şu anda kullanılabilir olduğu kadar bilgi döndürülür. Satır içi bant dışı veri alımını yuva yapılandırılmışsa (Yuva seçeneği **SO_OOBINLINE**) ve bant dışı verileri okunmamış ise, yalnızca giden bant dışı verileri döndürülecek. Uygulama kullanabilir **IOCtlSIOCATMARK** seçeneği veya [OnOutOfBandData](#onoutofbanddata) daha-bant verileri okumak için kalır olup olmadığını belirlemek için.  
  
 Veri birimi yuvaları için sağlanan arabellek boyutu kadar ilk sıraya alınan veri birimi gelen veri ayıklanır. Veri birimi sağlanan arabellekten daha büyük olursa, arabelleği veri birimi ilk bölümü ile doldurulur, fazlalık veriler kaybolur ve **alma** değerini döndürür **SOCKET_ERROR** hata kodu ile ayarlamak **WSAEMSGSIZE**. Gelen veri değeri yuva kullanılabilir olup olmadığını **SOCKET_ERROR** ayarlamak hata kodu döndürdü **WSAEWOULDBLOCK**. [OnReceive](#onreceive) geri çağırma işlevi, daha fazla veri geldiğinde belirlemek için kullanılabilir.  
  
 Yuva türü ise **SOCK_STREAM** ve uzak tarafı bağlantıyı düzgün kapattı bir **alma** 0 alınan bayt ile hemen tamamlanır. Bağlantı sıfırlarsanız bir **alma** hata ile başarısız olur **WSAECONNRESET**.  
  
 **Alma** her zaman için yalnızca bir kez çağrılmalıdır [CAsyncSocket::OnReceive](#onreceive) olarak adlandırılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CAsyncSocket::OnReceive](#onreceive).  
  
##  <a name="receivefrom"></a>  CAsyncSocket::ReceiveFrom  
 Bir veri birimi almak ve kaynak adresi depolamak için bu üye işlevini çağırın [SOCKADDR](../../mfc/reference/sockaddr-structure.md) yapısı veya `rSocketAddress`.  
  
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
 `lpBuf`  
 Gelen veriler için bir arabellek.  
  
 `nBufLen`  
 Uzunluğu `lpBuf` bayt.  
  
 `rSocketAddress`  
 Başvuru bir `CString` noktalı sayı bir IP adresi alan nesnesi.  
  
 `rSocketPort`  
 Başvuru bir **UINT** bir bağlantı noktası depolar.  
  
 `lpSockAddr`  
 Bir işaretçi bir [SOCKADDR](../../mfc/reference/sockaddr-structure.md) return bağlı kaynak adresi tutan yapısı.  
  
 `lpSockAddrLen`  
 Kaynak adresi uzunluğu için bir işaretçi `lpSockAddr` bayt.  
  
 `nFlags`  
 Aramanın yapılıp yapılmadığı yolunu belirtir. Bu işlev semantiği yuva seçenekleri tarafından belirlenir ve `nFlags` parametresi. İkinci aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulan `OR` işleci:  
  
- **MSG_PEEK** gelen veri Gözat. Verileri arabelleğe kopyalanır, ancak giriş sıradan kaldırılmadı.  
  
- **MSG_OOB** işlem bant dışı verileri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Herhangi bir hata oluşursa, `ReceiveFrom` alınan bayt sayısını döndürür. Bağlantı kapatıldı 0 döndürür. Aksi takdirde değerini **SOCKET_ERROR** döndürülür ve belirli bir kodu çağırarak alınabilir `GetLastError`. Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEFAULT** `lpSockAddrLen` bağımsız değişkeni geçersiz: `lpSockAddr` arabellek eş adresi uyum sağlamak için çok küçüktü.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAEINVAL** yuva ile bağlı değil **bağlama**.  
  
- **WSAENOTCONN** Yuva bağlı değil ( **SOCK_STREAM** yalnızca).  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAEOPNOTSUPP MSG_OOB** belirtildi, ancak yuva türü değil **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** yuva kapatıldı; çağırmak olası değil `ReceiveFrom` sonra bir yuvada `ShutDown` ile çağrılmış `nHow` 0 veya 2'ye ayarlayın.  
  
- **WSAEWOULDBLOCK** yuva işaretlenmiş olarak sayıda ve `ReceiveFrom` işlem engellendi.  
  
- **WSAEMSGSIZE** veri birimi belirtilen belleğe sığmayacak kadar büyük ve kesildi.  
  
- **WSAECONNABORTED** sanal devreyi zaman aşımı veya diğer hata nedeniyle iptal edildi.  
  
- **WSAECONNRESET** sanal devreyi uzak yan yana sıfırlandı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, (büyük olasılıkla bağlı) bir yuva gelen verileri okumak ve verilerin gönderildiği adres yakalamak için kullanılır.  
  
 IPv6 adresleri işlemek için kullanmak [CAsyncSocket::ReceiveFromEx](#receivefromex).  
  
 Yuva türü için **SOCK_STREAM**, sağlanan arabellek boyutu en fazla şu anda kullanılabilir olduğu kadar bilgi döndürülür. Satır içi bant dışı veri alımını yuva yapılandırılmışsa (Yuva seçeneği **SO_OOBINLINE**) ve bant dışı verileri okunmamış ise, yalnızca giden bant dışı verileri döndürülecek. Uygulama kullanabilir **IOCtlSIOCATMARK** seçeneği veya `OnOutOfBandData` daha-bant verileri okumak için kalır olup olmadığını belirlemek için. `lpSockAddr` Ve `lpSockAddrLen` parametreleri için yoksayılır **SOCK_STREAM** yuva.  
  
 Veri birimi yuvaları için sağlanan arabellek boyutu kadar ilk sıraya alınan veri birimi gelen veri ayıklanır. Veri birimi sağlanan arabellekten daha büyük olursa, arabelleği ileti ilk bölümü ile doldurulur, fazlalık veriler kaybolur ve `ReceiveFrom` değerini döndürür **SOCKET_ERROR** hata koduyla ayarlanmış  **WSAEMSGSIZE**.  
  
 Varsa `lpSockAddr` sıfır olmayan, olduğundan ve yuva türü **SOCK_DGRAM**, karşılık gelen verileri gönderilen yuva ağ adresini kopyalanan [SOCKADDR](../../mfc/reference/sockaddr-structure.md) yapısı. Tarafından için değer işaret `lpSockAddrLen` bu yapı boyutunu başlatılır ve depolanan adresi gerçek boyutunu belirtmek return değiştirilebilir. Gelen veri yuva kullanılabilir durumdaysa `ReceiveFrom` çağrısı bekler yuva olmadığı sürece gelmesi için verileri sayıda. Bu durumda değeri **SOCKET_ERROR** ayarlamak hata kodu döndürdü **WSAEWOULDBLOCK**. `OnReceive` Geri çağırma daha fazla veri geldiğinde belirlemek için kullanılabilir.  
  
 Yuva türü ise **SOCK_STREAM** ve uzak tarafı bağlantıyı düzgün kapattı bir `ReceiveFrom` 0 alınan bayt ile hemen tamamlanır.  
  
##  <a name="receivefromex"></a>  CAsyncSocket::ReceiveFromEx  
 Bir veri birimi almak ve kaynak adresi depolamak için bu üye işlevini çağırın [SOCKADDR](../../mfc/reference/sockaddr-structure.md) yapısı veya `rSocketAddress` (IPv6 adresleri işler).  
  
```  
int ReceiveFromEx(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpBuf`  
 Gelen veriler için bir arabellek.  
  
 `nBufLen`  
 Uzunluğu `lpBuf` bayt.  
  
 `rSocketAddress`  
 Başvuru bir `CString` noktalı sayı bir IP adresi alan nesnesi.  
  
 `rSocketPort`  
 Başvuru bir **UINT** bir bağlantı noktası depolar.  
  
 `nFlags`  
 Aramanın yapılıp yapılmadığı yolunu belirtir. Bu işlev semantiği yuva seçenekleri tarafından belirlenir ve `nFlags` parametresi. İkinci aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulan `OR` işleci:  
  
- **MSG_PEEK** gelen veri Gözat. Verileri arabelleğe kopyalanır, ancak giriş sıradan kaldırılmadı.  
  
- **MSG_OOB** işlem bant dışı verileri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Herhangi bir hata oluşursa, `ReceiveFromEx` alınan bayt sayısını döndürür. Bağlantı kapatıldı 0 döndürür. Aksi takdirde değerini **SOCKET_ERROR** döndürülür ve belirli bir kodu çağırarak alınabilir `GetLastError`. Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEFAULT** `lpSockAddrLen` bağımsız değişkeni geçersiz: `lpSockAddr` arabellek eş adresi uyum sağlamak için çok küçüktü.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAEINVAL** yuva ile bağlı değil **bağlama**.  
  
- **WSAENOTCONN** Yuva bağlı değil ( **SOCK_STREAM** yalnızca).  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAEOPNOTSUPP MSG_OOB** belirtildi, ancak yuva türü değil **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** yuva kapatıldı; çağırmak olası değil `ReceiveFromEx` sonra bir yuvada `ShutDown` ile çağrılmış `nHow` 0 veya 2'ye ayarlayın.  
  
- **WSAEWOULDBLOCK** yuva işaretlenmiş olarak sayıda ve `ReceiveFromEx` işlem engellendi.  
  
- **WSAEMSGSIZE** veri birimi belirtilen belleğe sığmayacak kadar büyük ve kesildi.  
  
- **WSAECONNABORTED** sanal devreyi zaman aşımı veya diğer hata nedeniyle iptal edildi.  
  
- **WSAECONNRESET** sanal devreyi uzak yan yana sıfırlandı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, (büyük olasılıkla bağlı) bir yuva gelen verileri okumak ve verilerin gönderildiği adres yakalamak için kullanılır.  
  
 Bu işlev aynıdır [CAsyncSocket::ReceiveFrom](#receivefrom) IPv6 işleme dışında de olarak eski protokollere giderir.  
  
 Yuva türü için **SOCK_STREAM**, sağlanan arabellek boyutu en fazla şu anda kullanılabilir olduğu kadar bilgi döndürülür. Satır içi bant dışı veri alımını yuva yapılandırılmışsa (Yuva seçeneği **SO_OOBINLINE**) ve bant dışı verileri okunmamış ise, yalnızca giden bant dışı verileri döndürülecek. Uygulama kullanabilir **IOCtlSIOCATMARK** seçeneği veya `OnOutOfBandData` daha-bant verileri okumak için kalır olup olmadığını belirlemek için. `lpSockAddr` Ve `lpSockAddrLen` parametreleri için yoksayılır **SOCK_STREAM** yuva.  
  
 Veri birimi yuvaları için sağlanan arabellek boyutu kadar ilk sıraya alınan veri birimi gelen veri ayıklanır. Veri birimi sağlanan arabellekten daha büyük olursa, arabelleği ileti ilk bölümü ile doldurulur, fazlalık veriler kaybolur ve `ReceiveFromEx` değerini döndürür **SOCKET_ERROR** hata koduyla ayarlanmış  **WSAEMSGSIZE**.  
  
 Varsa `lpSockAddr` sıfır olmayan, olduğundan ve yuva türü **SOCK_DGRAM**, karşılık gelen verileri gönderilen yuva ağ adresini kopyalanan [SOCKADDR](../../mfc/reference/sockaddr-structure.md) yapısı. Tarafından için değer işaret `lpSockAddrLen` bu yapı boyutunu başlatılır ve depolanan adresi gerçek boyutunu belirtmek return değiştirilebilir. Gelen veri yuva kullanılabilir durumdaysa `ReceiveFromEx` çağrısı bekler yuva olmadığı sürece gelmesi için verileri sayıda. Bu durumda değeri **SOCKET_ERROR** ayarlamak hata kodu döndürdü **WSAEWOULDBLOCK**. `OnReceive` Geri çağırma daha fazla veri geldiğinde belirlemek için kullanılabilir.  
  
 Yuva türü ise **SOCK_STREAM** ve uzak tarafı bağlantıyı düzgün kapattı bir `ReceiveFromEx` 0 alınan bayt ile hemen tamamlanır.  
  
##  <a name="send"></a>  CAsyncSocket::Send  
 Bağlı bir yuva üzerinde veri göndermek için bu üye işlevini çağırın.  
  
```  
virtual int Send(
    const void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpBuf`  
 İletilecek verileri içeren bir arabellek.  
  
 `nBufLen`  
 Veri uzunluğu `lpBuf` bayt.  
  
 `nFlags`  
 Aramanın yapılıp yapılmadığı yolunu belirtir. Bu işlev semantiği yuva seçenekleri tarafından belirlenir ve `nFlags` parametresi. İkinci aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulan `OR` işleci:  
  
- **MSG_DONTROUTE** veri yönlendirme tabi olmamalıdır belirtir. Windows Yuvaları tedarikçi Bu bayrak göz ardı etmeyi seçebilir.  
  
- **MSG_OOB** bant dışı veri gönderme ( **SOCK_STREAM** yalnızca).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Herhangi bir hata oluşursa, **Gönder** gönderilen karakter toplam sayısını döndürür. (Bu tarafından belirtilen sayıdan daha az olabileceğini unutmayın `nBufLen`.) Aksi takdirde değerini **SOCKET_ERROR** döndürülür ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEACCES** bir yayın adresi istenen adresidir, ancak uygun bayrağı ayarlanmamış.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAEFAULT** `lpBuf` bağımsız değişkeni geçerli bir kullanıcı adres alanının parçası değil.  
  
- **WSAENETRESET** Windows Sockets uygulaması yoksaymış çünkü bağlantının sıfırlanması gerekir.  
  
- `WSAENOBUFS` Windows Yuvaları uygulama arabellek kilitlenme bildirir.  
  
- **WSAENOTCONN** Yuva bağlı değil.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAEOPNOTSUPP MSG_OOB** belirtildi, ancak yuva türü değil **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** yuva kapatıldı; çağırmak olası değil **Gönder** sonra bir yuvada `ShutDown` ile çağrılmış `nHow` 1 veya 2'ye ayarlayın.  
  
- **WSAEWOULDBLOCK** yuva işaretlenmiş olarak sayıda ve istenen işlem engellenebilir.  
  
- **WSAEMSGSIZE** yuva türünde **SOCK_DGRAM**, ve veri birimi Windows Sockets uygulaması tarafından desteklenen en çok büyük.  
  
- **WSAEINVAL** yuva ile bağlı değil **bağlama**.  
  
- **WSAECONNABORTED** sanal devreyi zaman aşımı veya diğer hata nedeniyle iptal edildi.  
  
- **WSAECONNRESET** sanal devreyi uzak yan yana sıfırlandı.  
  
### <a name="remarks"></a>Açıklamalar  
 **Gönderme** bağlı akış veya veri birimi yuvaları giden verileri yazmak için kullanılır. Veri birimi yuvaları için temel alınan alt maksimum IP paket boyutu, tarafından verilen aşmayacak şekilde dikkatli olunması gerekir **iMaxUdpDg** öğesinde [WSADATA](../../mfc/reference/wsadata-structure.md) tarafından döndürülen yapısı `AfxSocketInit`. Verileri otomatik olarak temel protokolü hata geçirmek için çok uzun olması durumunda **WSAEMSGSIZE** yoluyla döndürülen `GetLastError`, ve veri iletilir.  
  
 Bir veri birimi için başarılı şekilde tamamlandığını yuva unutmayın bir **Gönder** verileri başarıyla teslim anlamına gelmez.  
  
 Üzerinde `CAsyncSocket` türündeki nesneler **SOCK_STREAM**, yazılan bayt sayısı 1 ile yerel ve yabancı konakları arabellek kullanılabilirliğine bağlı olarak istenen uzunluğu arasında olabilir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CAsyncSocket::OnSend](#onsend).  
  
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
 `lpBuf`  
 İletilecek verileri içeren bir arabellek.  
  
 `nBufLen`  
 Veri uzunluğu `lpBuf` bayt.  
  
 `nHostPort`  
 Yuva uygulamasını tanımlayan bağlantı noktası.  
  
 `lpszHostAddress`  
 Bu nesne bağlı yuva ağ adresi: "ftp.microsoft.com" veya "128.56.22.8" gibi noktalı sayı gibi bir makine adı.  
  
 `nFlags`  
 Aramanın yapılıp yapılmadığı yolunu belirtir. Bu işlev semantiği yuva seçenekleri tarafından belirlenir ve `nFlags` parametresi. İkinci aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulan `OR` işleci:  
  
- **MSG_DONTROUTE** veri yönlendirme tabi olmamalıdır belirtir. Windows Yuvaları tedarikçi Bu bayrak göz ardı etmeyi seçebilir.  
  
- **MSG_OOB** bant dışı veri gönderme ( **SOCK_STREAM** yalnızca).  
  
 `lpSockAddr`  
 Bir işaretçi bir [SOCKADDR](../../mfc/reference/sockaddr-structure.md) hedef yuva adresini içeren yapısı.  
  
 `nSockAddrLen`  
 Adresi uzunluğu `lpSockAddr` bayt.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Herhangi bir hata oluşursa, `SendTo` gönderilen karakter toplam sayısını döndürür. (Bu tarafından belirtilen sayıdan daha az olabileceğini unutmayın `nBufLen`.) Aksi takdirde değerini **SOCKET_ERROR** döndürülür ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEACCES** bir yayın adresi istenen adresidir, ancak uygun bayrağı ayarlanmamış.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAEFAULT** `lpBuf` veya `lpSockAddr` parametreleri kullanıcı adres alanının parçası değil veya `lpSockAddr` değişken değeri çok küçük (boyutundan daha küçük bir [SOCKADDR](../../mfc/reference/sockaddr-structure.md) yapısı).  
  
- **WSAEINVAL** ana bilgisayar adı geçersiz.  
  
- **WSAENETRESET** Windows Sockets uygulaması yoksaymış çünkü bağlantının sıfırlanması gerekir.  
  
- `WSAENOBUFS` Windows Yuvaları uygulama arabellek kilitlenme bildirir.  
  
- **WSAENOTCONN** Yuva bağlı değil ( **SOCK_STREAM** yalnızca).  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAEOPNOTSUPP MSG_OOB** belirtildi, ancak yuva türü değil **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** yuva kapatıldı; çağırmak olası değil `SendTo` sonra bir yuvada `ShutDown` ile çağrılmış `nHow` 1 veya 2'ye ayarlayın.  
  
- **WSAEWOULDBLOCK** yuva işaretlenmiş olarak sayıda ve istenen işlem engellenebilir.  
  
- **WSAEMSGSIZE** yuva türünde **SOCK_DGRAM**, ve veri birimi Windows Sockets uygulaması tarafından desteklenen en çok büyük.  
  
- **WSAECONNABORTED** sanal devreyi zaman aşımı veya diğer hata nedeniyle iptal edildi.  
  
- **WSAECONNRESET** sanal devreyi uzak yan yana sıfırlandı.  
  
- **WSAEADDRNOTAVAIL** belirtilen adresi yerel makinede kullanılabilir değil.  
  
- **WSAEAFNOSUPPORT** adresleri belirtilen ailesindeki bu yuvası ile kullanılamaz.  
  
- **WSAEDESTADDRREQ** hedef adresi gereklidir.  
  
- **WSAENETUNREACH** ağ şu anda bu konaktan erişilemiyor.  
  
### <a name="remarks"></a>Açıklamalar  
 `SendTo` veri birimi veya akış yuvalarda kullanılır ve bir yuvada giden veri yazmak için kullanılır. Veri birimi yuvaları için temel alınan alt maksimum IP paket boyutu, tarafından verilen aşmayacak şekilde dikkatli olunması gerekir **iMaxUdpDg** öğesinde [WSADATA](../../mfc/reference/wsadata-structure.md) yapısı doldurulan tarafından [ Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Verileri otomatik olarak temel protokolü hata geçirmek için çok uzun olması durumunda **WSAEMSGSIZE** döndürülür ve hiçbir veri iletilir.  
  
 Unutmayın başarıyla tamamlandığında, bir `SendTo` verileri başarıyla teslim anlamına gelmez.  
  
 `SendTo` Yalnızca kullanılan bir **SOCK_DGRAM** bir veri birimi ile tanımlanan belirli bir yuva göndermek için yuva `lpSockAddr` parametresi.  
  
 Bir yayın göndermek için (üzerinde bir **SOCK_DGRAM** yalnızca), adres `lpSockAddr` parametresi oluşturulan özel IP adresini kullanarak **INADDR_BROADCAST** (Windows Sockets başlığında tanımlanır WINSOCK dosyası. H) ile birlikte istenen bağlantı noktası numarası. Veya, eğer `lpszHostAddress` parametresi **NULL**, yuva yayın için yapılandırılmış. Bir yayın datagram aktarılma parçalanma gerçekleşebilir, boyut değerini aşmasına genelde önerilmez (üstbilgileri hariç) datagram veri bölümü 512 bayt aşmamalıdır anlamına gelir.  
  
 IPv6 adresleri işlemek için kullanmak [CAsyncSocket::SendToEx](#sendtoex).  
  
##  <a name="sendtoex"></a>  CAsyncSocket::SendToEx  
 Belirli bir hedefe (işleç IPv6 adresleri) veri göndermek için bu üye işlevini çağırın.  
  
```  
int SendToEx(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpBuf`  
 İletilecek verileri içeren bir arabellek.  
  
 `nBufLen`  
 Veri uzunluğu `lpBuf` bayt.  
  
 `nHostPort`  
 Yuva uygulamasını tanımlayan bağlantı noktası.  
  
 `lpszHostAddress`  
 Bu nesne bağlı yuva ağ adresi: "ftp.microsoft.com" veya "128.56.22.8" gibi noktalı sayı gibi bir makine adı.  
  
 `nFlags`  
 Aramanın yapılıp yapılmadığı yolunu belirtir. Bu işlev semantiği yuva seçenekleri tarafından belirlenir ve `nFlags` parametresi. İkinci aşağıdaki değerlerden herhangi birini C++ ile birleştirerek oluşturulan `OR` işleci:  
  
- **MSG_DONTROUTE** veri yönlendirme tabi olmamalıdır belirtir. Windows Yuvaları tedarikçi Bu bayrak göz ardı etmeyi seçebilir.  
  
- **MSG_OOB** bant dışı veri gönderme ( **SOCK_STREAM** yalnızca).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Herhangi bir hata oluşursa, `SendToEx` gönderilen karakter toplam sayısını döndürür. (Bu tarafından belirtilen sayıdan daha az olabileceğini unutmayın `nBufLen`.) Aksi takdirde değerini **SOCKET_ERROR** döndürülür ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEACCES** bir yayın adresi istenen adresidir, ancak uygun bayrağı ayarlanmamış.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAEFAULT** `lpBuf` veya `lpSockAddr` parametreleri kullanıcı adres alanının parçası değil veya `lpSockAddr` değişken değeri çok küçük (boyutundan daha küçük bir [SOCKADDR](../../mfc/reference/sockaddr-structure.md) yapısı).  
  
- **WSAEINVAL** ana bilgisayar adı geçersiz.  
  
- **WSAENETRESET** Windows Sockets uygulaması yoksaymış çünkü bağlantının sıfırlanması gerekir.  
  
- `WSAENOBUFS` Windows Yuvaları uygulama arabellek kilitlenme bildirir.  
  
- **WSAENOTCONN** Yuva bağlı değil ( **SOCK_STREAM** yalnızca).  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
- **WSAEOPNOTSUPP MSG_OOB** belirtildi, ancak yuva türü değil **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** yuva kapatıldı; çağırmak olası değil `SendToEx` sonra bir yuvada `ShutDown` ile çağrılmış `nHow` 1 veya 2'ye ayarlayın.  
  
- **WSAEWOULDBLOCK** yuva işaretlenmiş olarak sayıda ve istenen işlem engellenebilir.  
  
- **WSAEMSGSIZE** yuva türünde **SOCK_DGRAM**, ve veri birimi Windows Sockets uygulaması tarafından desteklenen en çok büyük.  
  
- **WSAECONNABORTED** sanal devreyi zaman aşımı veya diğer hata nedeniyle iptal edildi.  
  
- **WSAECONNRESET** sanal devreyi uzak yan yana sıfırlandı.  
  
- **WSAEADDRNOTAVAIL** belirtilen adresi yerel makinede kullanılabilir değil.  
  
- **WSAEAFNOSUPPORT** adresleri belirtilen ailesindeki bu yuvası ile kullanılamaz.  
  
- **WSAEDESTADDRREQ** hedef adresi gereklidir.  
  
- **WSAENETUNREACH** ağ şu anda bu konaktan erişilemiyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ile aynıdır [CAsyncSocket::SendTo](#sendto) IPv6 işleme dışında de olarak eski protokollere giderir.  
  
 `SendToEx` veri birimi veya akış yuvalarda kullanılır ve bir yuvada giden veri yazmak için kullanılır. Veri birimi yuvaları için temel alınan alt maksimum IP paket boyutu, tarafından verilen aşmayacak şekilde dikkatli olunması gerekir **iMaxUdpDg** öğesinde [WSADATA](../../mfc/reference/wsadata-structure.md) yapısı doldurulan tarafından [ Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Verileri otomatik olarak temel protokolü hata geçirmek için çok uzun olması durumunda **WSAEMSGSIZE** döndürülür ve hiçbir veri iletilir.  
  
 Unutmayın başarıyla tamamlandığında, bir `SendToEx` verileri başarıyla teslim anlamına gelmez.  
  
 `SendToEx` Yalnızca kullanılan bir **SOCK_DGRAM** bir veri birimi ile tanımlanan belirli bir yuva göndermek için yuva `lpSockAddr` parametresi.  
  
 Bir yayın göndermek için (üzerinde bir **SOCK_DGRAM** yalnızca), adres `lpSockAddr` parametresi oluşturulan özel IP adresini kullanarak **INADDR_BROADCAST** (Windows Sockets başlığında tanımlanır WINSOCK dosyası. H) ile birlikte istenen bağlantı noktası numarası. Veya, eğer `lpszHostAddress` parametresi **NULL**, yuva yayın için yapılandırılmış. Bir yayın datagram aktarılma parçalanma gerçekleşebilir, boyut değerini aşmasına genelde önerilmez (üstbilgileri hariç) datagram veri bölümü 512 bayt aşmamalıdır anlamına gelir.  
  
##  <a name="setsockopt"></a>  CAsyncSocket::SetSockOpt  
 Bir yuva seçeneği ayarlamak için bu üye işlevini çağırın.  
  
```  
BOOL SetSockOpt(
    int nOptionName,  
    const void* lpOptionValue,  
    int nOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>Parametreler  
 `nOptionName`  
 Değeri ayarlanacak olduğu yuva seçeneği.  
  
 `lpOptionValue`  
 İstenen seçeneğine ilişkin değer sağlanan arabellek için bir işaretçi.  
  
 `nOptionLen`  
 Boyutunu `lpOptionValue` arabelleğinin bayt cinsinden.  
  
 `nLevel`  
 Seçenek tanımlandığı düzeyi; yalnızca desteklenen düzeyler **SOL_SOCKET** ve **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEFAULT** `lpOptionValue` geçerli bir işlem adres alanının parçası değil.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAEINVAL** `nLevel` geçerli değil veya bilgileri `lpOptionValue` geçerli değil.  
  
- **WSAENETRESET** bağlantı zaman aşımına ne zaman **SO_KEEPALIVE** ayarlanır.  
  
- **WSAENOPROTOOPT** bilinmeyen veya desteklenmeyen bir seçenektir. Özellikle, **SO_BROADCAST** türü yuvalarda desteklenmeyen **SOCK_STREAM**, sırada **SO_DONTLINGER**, **SO_KEEPALIVE**,  **SO_LINGER**, ve **SO_OOBINLINE** türü yuvalarda desteklenmeyen **SOCK_DGRAM**.  
  
- **WSAENOTCONN** bağlantısı açıldı ne zaman sıfırlama **SO_KEEPALIVE** ayarlanır.  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetSockOpt` herhangi bir durum içinde herhangi bir türde bir yuvası ile ilişkili bir yuva seçeneği için geçerli değeri ayarlar. Seçenekleri birden çok protokolü düzeylerinde bulunabilir ancak bu belirtimi yalnızca en üst "yuva" düzeyindedir seçenekleri tanımlar. Seçenekler yayın iletilerini yuvasına gönderilen ve benzeri olup olmadığını normal veri akışında alınan hızlandırılmış veri olup olmadığı gibi yuva işlemlerini etkiler.  
  
 İki tür yuva seçeneği vardır: etkinleştirmek veya bir özellik veya davranışı devre dışı bırakan Boolean seçenekleri ve bir tamsayı değeri veya yapısı gerektiren seçenekleri. Boole seçeneği etkinleştirmek için `lpOptionValue` sıfır olmayan bir tamsayı olarak işaret eder. Seçeneği devre dışı bırakmak için `lpOptionValue` sıfıra eşit bir tamsayı işaret eder. `nOptionLen` eşit olmalıdır **sizeof(BOOL)** Boolean seçenekleri için. Diğer seçenekler için `lpOptionValue` gösteren tamsayı veya seçeneği için istenen değeri içeren yapısı ve `nOptionLen` tamsayı veya yapısı uzunluğu.  
  
 **SO_LINGER** ne zaman gerçekleştirilecek eylemi gönderilmeyen veri kuyruğa alınır bir yuvada denetimleri ve **kapatmak** işlevi yuva kapatmak için çağrılır.  
  
 Varsayılan olarak, bir yuva bağlı olamaz (bkz [bağlamak](#bind)) zaten kullanımda olan yerel bir adres için. Bazen, ancak bunu "bir adresi bu şekilde yeniden" istenebilir. Her bağlantı yerel ve uzak adreslerini birleşimiyle benzersiz şekilde tanımlanır olduğundan, iki yuva uzak adreslerini farklı olduğu sürece aynı yerel adresine bağlı olan hiçbir sorun yoktur.  
  
 Windows Yuvaları uygulama bildirmek için bir **bağlamak** çağrısı bir yuvada değil izin verilmeyen istenen adresi zaten başka bir yuva tarafından kullanımda olduğundan, uygulama ayarlamalısınız **SO_REUSEADDR**yuva verilmeden önce seçeneği yuva için **bağlamak** çağırın. Seçeneği aynı anda yalnızca yorumlanır Not **bağlamak** çağırın:, bu nedenle, varolan bir adresine bağlı olmayan bir yuvada seçeneğini ayarlamak için (ancak zararsız) gerekli değildir ve ayarlama veya seçeneğinden sonra sıfırlama **Bağlamak** çağrısı bu üzerinde hiçbir etkisi veya başka bir yuva sahiptir.  
  
 Bir uygulama Windows Sockets uygulaması açarak İletim Denetimi Protokolü (TCP) bağlantıları "tutma" paketlerde kullanımını etkinleştirme isteyebilir **SO_KEEPALIVE** yuva seçeneği. Bir Windows Sockets uygulamasını tutma kullanımını desteklemeyen: bulursa, kesin semantiğini uygulamaya özel ancak RFC 1122 4.2.3.6 bölümüne uygun olmalıdır: "Internet ana bilgisayarı gereksinimleri — iletişim katmanları." Hata kodu "tutma" sonucu olarak bir bağlantı kesilirse **WSAENETRESET** devam eden tüm çağrıları yuvada döndürülür ve yapılan sonraki çağrılar başarısız **WSAENOTCONN**.  
  
 **TCP_NODELAY** seçeneği Nagle algoritmasını devre dışı bırakır. Nagle algoritması tam boyutlu bir paket gönderilebilir kadar bildirilmemiş gönderme veri arabelleğe alma bir ana bilgisayar tarafından gönderilen küçük paketlerin sayısını azaltmak için kullanılır. Ancak, bazı uygulamalar için bu algoritma performans, engel ve **TCP_NODELAY** devre dışı bırakmak için kullanılabilir. Uygulama yazarları değil ayarlamalıdır **TCP_NODELAY** tanınmış ve istenen, böylece etkisini itibaren ayarı olmadığı sürece **TCP_NODELAY** ağ performans üzerinde önemli olumsuz bir etkisi olabilir . **TCP_NODELAY** tek düzey kullanan olarak yuva seçeneği desteklenen **IPPROTO_TCP**; diğer tüm seçenekleri düzeyini kullanmak **SOL_SOCKET**.  
  
 Windows Yuvaları tedarik bazı uygulamaları, hata ayıklama bilgileri çıkış **SO_DEBUG** seçeneği, bir uygulama tarafından ayarlanır.  
  
 Aşağıdaki seçenekler için desteklenen `SetSockOpt`. Türü tarafından ele veri türünü tanımlayan `lpOptionValue`.  
  
|Değer|Tür|Açıklama|  
|-----------|----------|-------------|  
|**SO_BROADCAST**|**BOOL**|Yuvadaki yayın ileti aktarımını sağlar.|  
|**SO_DEBUG**|**BOOL**|Hata ayıklama bilgisi kaydı.|  
|**SO_DONTLINGER**|**BOOL**|Engelleme **Kapat** gönderilecek gönderilmemiş verileri bekleniyor. Bu seçeneğin ayarlanması eşdeğerdir ayarına **SO_LINGER** ile **l_onoff** sıfır olarak ayarlayın.|  
|**SO_DONTROUTE**|**BOOL**|Yol yok: doğrudan arabirimi gönderin.|  
|**SO_KEEPALIVE**|**BOOL**|Etkin tutma gönderin.|  
|**SO_LINGER**|**LINGER yapısı**|Lınger **Kapat** veri gönderilmeyen durumunda.|  
|**SO_OOBINLINE**|**BOOL**|Bant dışı verileri normal veri akışında alırsınız.|  
|**SO_SNDBUF**|`int`|Arabellek boyutu için alan belirtin.|  
|**SO_REUSEADDR**|**BOOL**|Yuva zaten kullanımda olan bir adres bağlı olmasını sağlar. (Bkz [bağlama](#bind).)|  
|**SO_SNDBUF**|`int`|Arabellek boyutu gönderir için belirtin.|  
|**TCP_NODELAY**|**BOOL**|Gönderme birleştirmesi için Nagle algoritmayı devre dışı bırakır.|  
  
 Berkeley Software Distribution (BSD) seçenekleri desteklenmiyor `SetSockOpt` şunlardır:  
  
|Değer|Tür|Açıklama|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Yuva dinleme|  
|**SO_ERROR**|`int`|Hata durumunu Al ve temizleyin.|  
|**SO_RCVLOWAT**|`int`|Düşük su işareti alırsınız.|  
|**SO_RCVTIMEO**|`int`|Zaman aşımı alma|  
|**SO_SNDLOWAT**|`int`|Düşük su işareti gönderin.|  
|**SO_SNDTIMEO**|`int`|Zaman aşımı gönderin.|  
|**SO_TYPE**|`int`|Yuva türü.|  
|**IP_OPTIONS**||Seçenekler alanını IP üstbilgisinde ayarlayın.|  
  
##  <a name="shutdown"></a>  CAsyncSocket::ShutDown  
 Bu üye işlevini devre dışı bırakmak için gönderir, çağrıyı alır, veya her ikisini de yuvadaki.  
  
```  
BOOL ShutDown(int nHow = sends);
```  
  
### <a name="parameters"></a>Parametreler  
 `nHow`  
 Hangi tür işlem tanımlayan bir bayrak artık, aşağıdaki numaralandırılmış değerler kullanarak izin verilir:  
  
- **alan = 0**  
  
- **gönderir = 1**  
  
- **hem = 2**  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir [GetLastError](#getlasterror). Aşağıdaki hatalar bu üye işlevini uygulayın:  
  
- **WSANOTINITIALISED** başarılı bir [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit) bu API kullanmadan önce gerçekleşmesi gerekir.  
  
- **WSAENETDOWN** Windows Sockets uygulaması ağ alt sistemi başarısız olduğunu algıladı.  
  
- **WSAEINVAL** `nHow` geçerli değil.  
  
- **WSAEINPROGRESS** engelleme Windows Sockets işlemi devam ediyor.  
  
- **WSAENOTCONN** Yuva bağlı değil ( **SOCK_STREAM** yalnızca).  
  
- **WSAENOTSOCK** tanımlayıcısı yuva değil.  
  
### <a name="remarks"></a>Açıklamalar  
 `ShutDown` Yuva tüm türleri, alma, iletim veya her ikisi de devre dışı bırakmak için kullanılır. Varsa `nHow` 0'dır, üzerinde sonraki aldığı yuva izin verilmeyecek. Bu alt protokol katmanları üzerinde hiçbir etkisi yoktur.  
  
 İletim Denetimi Protokolü (TCP) için TCP penceresi değiştirilmez ve gelen veri olacaktır penceresi ulaşana kadar (ancak alınan değil) kabul. Kullanıcı Veri Birimi Protokolü (UDP) gelen veri birimleri kabul ve sıraya alındı. Hiçbir durumda bir ICMP hata paketi oluşturulur. Varsa `nHow` 1, sonraki gönderir izin verilmiyor. TCP yuvaları için bir FIN gönderilir. Ayarı `nHow` hem gönderir 2 devre dışı bırakır ve yukarıda açıklandığı gibi alır.  
  
 Unutmayın `ShutDown` mu değil kapatmak için yuva bağlı kaynakları ve yuva değil kaldırılacaktır kadar **kapatmak** olarak adlandırılır. Bir uygulama, kapatıldı sonra yuva yeniden bölümlemeye üzerinde güvenmemelisiniz. Özellikle, bir Windows Sockets uygulamasını kullanımını desteklemek için gerekli değildir **Bağlan** böyle bir yuvada.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CAsyncSocket::OnReceive](#onreceive).  
  
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
 `nSocketType`  
 Belirtir `SOCK_STREAM` veya `SOCK_DGRAM`.  
  
 `lEvent`  
 Ağ olayları uygulama ilgilenen bir bileşimini belirtir bir bit maskesi.  
  
- `FD_READ`: Hazırlık okumak için bildirim alacak istiyorsunuz.  
  
- `FD_WRITE`: Hazırlığı yazmak için bildirim alacak istiyorsunuz.  
  
- `FD_OOB`: Bant dışı verileri varış bildirim almak istediğiniz.  
  
- `FD_ACCEPT`: Gelen bağlantıları bildirim almak istediğiniz.  
  
- `FD_CONNECT`: Tamamlanmış bağlantı bildirim almak istediğiniz.  
  
- `FD_CLOSE`: Yuva kapatma bildirim almak istediğiniz.  
  
 `nProtocolType`  
 Belirtilen adres ailesi özgü yuva ile kullanılacak protokolü.  
  
 `nAddressFormat`  
 Aile belirtimi adres.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` başarılı, `FALSE` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem socket tanıtıcısı ayırır. Arama [CAsyncSocket::Bind](#bind) çağırmanız gerekir böylece yuva belirtilen bir adresin bağlanacağı `Bind` daha sonra belirtilen adresine yuvası bağlama. Kullanabileceğiniz [CAsyncSocket::SetSockOpt](#setsockopt) bağlı olduğu önce yönelik olarak yuva seçeneği ayarlamak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CSocket sınıfı](../../mfc/reference/csocket-class.md)   
 [CSocketFile Sınıfı](../../mfc/reference/csocketfile-class.md)
