---
title: CSocket sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSocket
- AFXSOCK/CSocket
- AFXSOCK/CSocket::CSocket
- AFXSOCK/CSocket::Attach
- AFXSOCK/CSocket::CancelBlockingCall
- AFXSOCK/CSocket::Create
- AFXSOCK/CSocket::FromHandle
- AFXSOCK/CSocket::IsBlocking
- AFXSOCK/CSocket::OnMessagePending
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
ms.openlocfilehash: 3c5340a8c65f804747fd8d3c8bd31fb20f80c6ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487311"
---
# <a name="csocket-class"></a>CSocket sınıfı

Öğesinden türetilen `CAsyncSocket`, Windows Sockets API'SİNİN kapsüllemesini devralır ve daha yüksek düzeyde soyutlama temsil eden bir `CAsyncSocket` nesne.

## <a name="syntax"></a>Sözdizimi

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSocket::CSocket](#csocket)|Oluşturur bir `CSocket` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSocket::Attach](#attach)|YUVA işleyici ekler bir `CSocket` nesne.|
|[CSocket::CancelBlockingCall](#cancelblockingcall)|Şu anda sürmekte olan bir engelleme çağrısının iptal eder.|
|[CSocket::Create](#create)|Bir yuva oluşturur.|
|[CSocket::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CSocket` bir YUVA belirli nesne.|
|[CSocket::IsBlocking](#isblocking)|Engelleme çağrısının ediyor olup olmadığını belirler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSocket::OnMessagePending](#onmessagepending)|Bekleyen iletileri işleme bir engelleme çağrısının tamamlanması beklenirken çağrılır.|

## <a name="remarks"></a>Açıklamalar

`CSocket` sınıflarla çalışır `CSocketFile` ve `CArchive` gönderme ve alma veri yönetmek için.

A `CSocket` nesnesi de sağlar engelleme, zaman uyumlu çalışması için gerekli olan `CArchive`. İşlevler, aşağıdakiler gibi engelleme `Receive`, `Send`, `ReceiveFrom`, `SendTo`, ve `Accept` (öğesinden devralınan tüm `CAsyncSocket`), döndürmeyin bir `WSAEWOULDBLOCK` hata `CSocket`. Bu işlevler bunun yerine, işlemi tamamlanana kadar bekleyin. Ayrıca, özgün çağrıyı WSAEINTR hata durumunda sona erer `CancelBlockingCall` Bu işlevlerden biri engelliyor sırasında çağrılır.

Kullanılacak bir `CSocket` nesne, oluşturucusunu'ı çağırın `Create` temel alınan SOCKET tanıtıcısı (YUVA türü) oluşturmak için. Varsayılan parametreleri `Create` stream yuva oluşturma ancak yuvasıyla kullanmıyorsanız bir `CArchive` nesne, bunun yerine bir veri birimi yuva oluşturun veya bir sunucu yuvası oluşturmak için belirli bir bağlantı noktasına bağlamak için bir parametre belirtebilirsiniz. Bir istemci kullanarak yuva bağlanmak `Connect` istemci tarafında ve `Accept` sunucu tarafında. Oluşturup bir `CSocketFile` nesne ve bunu `CSocket` nesnesine `CSocketFile` Oluşturucusu. Ardından, oluşturun bir `CArchive` göndermek için nesne ve (gerektiğinde) veri almak için bir sonra ilişkilendirmek kendileriyle `CSocketFile` nesnesine `CArchive` Oluşturucusu. Tam iletişimleridir, yok `CArchive`, `CSocketFile`, ve `CSocket` nesneleri. YUVA veri türü makalesinde açıklanan [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md).

Kullanırken `CArchive` ile `CSocketFile` ve `CSocket`, bir durum karşılaşabilirsiniz burada `CSocket::Receive` bir döngüye girer (tarafından `PumpMessages(FD_READ)`) istenen bayt miktarı için bekleniyor. Windows sockets FD_READ bildirim başına yalnızca bir alımı ayarlanırken çağrı izin olmasıdır ancak `CSocketFile` ve `CSocket` FD_READ başına birden çok Al çağrılarının izin verir. Hiçbir veri okumak için bir FD_READ alırsanız, uygulamanın yanıt vermemeye başlıyor. Hiçbir zaman başka bir FD_READ alırsanız, yuva iletişim kuran uygulamayı durdurur.

Aşağıdaki şekilde bu sorunu çözebilirsiniz. İçinde `OnReceive` yuva sınıfınızın çağrı yöntemi `CAsyncSocket::IOCtl(FIONREAD, ...)` çağırmadan önce `Serialize` beklenen veri yuvadan okumak için bir TCP paket (en fazla iletim birimi ağ ortamının boyutunu aştığında, ileti sınıfının yöntemi genellikle en az 1096 bayt). Kullanılabilir veri boyutu gereken daha az ise, alınması ve yalnızca okuma işlemini başlatmak tüm veriler için bekleyin.

Aşağıdaki örnekte, `m_dwExpected` yaklaşık kullanıcı almak için bekliyor bayt sayısıdır. Başka bir yerde kodunuzda bildirirken, varsayılır.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
>  Statik olarak bağlı bir MFC uygulamasında İkincil iş parçacıklarındaki MFC Yuvaları kullanılırken çağırmalısınız `AfxSocketInit` yuva kitaplıklarını başlatma yuva kullanan her bir iş parçacığı. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığında çağrılır.

Daha fazla bilgi için bkz [MFC'de Windows Yuvaları](../../mfc/windows-sockets-in-mfc.md), [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Yuvaları: Yuva arşivler ile nasıl](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Yuvaları: işlem dizisi](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Yuvaları: arşivlerle kullanılan yuvalara örnek](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxsock.h

##  <a name="attach"></a>  CSocket::Attach

Eklemek için bu üye işlevi çağrısı `hSocket` işlemek için bir `CSocket` nesne.

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>Parametreler

*hSocket*<br/>
Bir yuva için bir tanıtıcı içerir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır.

### <a name="remarks"></a>Açıklamalar

SOCKET tanıtıcısı nesnenin içinde depolanan [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) veri üyesi.

Daha fazla bilgi için [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

##  <a name="cancelblockingcall"></a>  CSocket::CancelBlockingCall

Şu anda devam eden bir engelleme çağrısının iptal etmek için bu üye işlevini çağırın.

```
void CancelBlockingCall();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, bu yuva için bekleyen tüm engelleyici işlemi iptal eder. Özgün engelleme çağrısının olabildiğince çabuk WSAEINTR hata ile sona erer.

Bir engelleme söz konusu olduğunda `Connect` işlem, Windows Sockets uygulaması sonlandırılacak engelleme çağrısının olası, ancak bağlantı tamamlandı (ve ardından sıfırlandığını kadar) yayımlanacak yuva kaynaklar için mümkün olmayabilir hemen sonra veya zaman aşımına uğradı. Bu, yalnızca uygulamayı hemen (hiçbir yuva mevcutsa) yeni bir yuva açın ya da aynı eşler arası bağlanmaya çalışırsa, belirgin olması muhtemeldir.

Dışında herhangi bir işlem iptal ediliyor `Accept` yuva belirsiz bir durumda bırakabilir. Bir uygulama bir yuvada engelleyici bir işlemi iptal ederse uygulama yuva gerçekleştirmek için bağlı yalnızca bir çağrı işlemdir `Close`, diğer işlemler, bazı Windows Sockets uygulamalarında işe yarasa da. Uygulamanız için en fazla Taşınabilirlik isterse, sonra iptal etme işlemlerini gerçekleştirme üzerinde bağımlı olmadan dikkatli olmanız gerekir.

Daha fazla bilgi için [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="create"></a>  CSocket::Create

Çağrı **Oluştur** sonra Windows yuva oluşturma ve bunu eklemek için bir yuva nesnesi oluşturulurken, üye işlevi.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Parametreler

*nSocketPort*<br/>
Bir bağlantı noktası seçmek için MFC istiyorsanız socket veya 0 ile kullanılmak üzere belirli bir bağlantı.

*nSocketType*<br/>
SOCK_STREAM veya SOCK_DGRAM.

*lpszSocketAddress*<br/>
Bağlı bir yuva, noktalı bir sayı "128.56.22.8" gibi ağ adresini içeren bir dize işaretçisi. Bu parametresi için dize NULL geçirme `CSocket` örneği istemci etkinliği tüm ağ arabirimleri üzerinde dinler.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0 ve belirli bir kodu çağrılarak alınabilir `GetLastError`.

### <a name="remarks"></a>Açıklamalar

`Create` Daha sonra çağırır `Bind` belirtilen adresine yuvası bağlama. Aşağıdaki yuva türleri desteklenir:

- SOCK_STREAM sıralı, güvenilir, çift yönlü, bağlantı tabanlı bayt akışları sağlar. İletim Denetimi Protokolü (TCP), Internet adresi ailesinde için kullanır.

- Sabit (genellikle küçük) maksimum uzunluktaki bağlantısız, güvenilir olmayan arabellek SOCK_DGRAM destekleyen veri birimi. Kullanıcı Veri Birimi Protokolü (UDP), Internet adresi ailesinde için kullanır. Bu seçeneği kullanmak için yuvasıyla kullanmamanız gerekir bir `CArchive` nesne.

    > [!NOTE]
    >  `Accept` Üye işlev yeni, boş bir başvuru alır `CSocket` parametre olarak nesne. Çağırmadan önce bu nesne oluşturmalıdır `Accept`. Aklınızda bu yuva nesnesi kapsamını, bağlantıyı kapatır aşması durumunda. Çağırmayın `Create` bu yeni bir yuva nesnesi.

Stream ve veri birimi yuvaları hakkında daha fazla bilgi için makalelere bakın [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md), [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../../mfc/windows-sockets-ports-and-socket-addresses.md), ve [Windows Yuvaları: kullanarak Yuvaların arşivlerle](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="csocket"></a>  CSocket::CSocket

Oluşturur bir `CSocket` nesne.

```
CSocket();
```

### <a name="remarks"></a>Açıklamalar

Yapı sonra çağırmalısınız `Create` üye işlevi.

Daha fazla bilgi için [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="fromhandle"></a>  CSocket::FromHandle

Bir işaretçi döndüren bir `CSocket` nesne.

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Parametreler

*hSocket*<br/>
Bir yuva için bir tanıtıcı içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CSocket` nesne veya yoksa NULL hiçbir `CSocket` nesne iliştirilmiş *hSocket*.

### <a name="remarks"></a>Açıklamalar

Bir YUVA işleyicisini varsa verildiğinde bir `CSocket` nesne tanıtıcısını bağlı değil, üye işlev NULL döndürür ve geçici bir nesne oluşturmaz.

Daha fazla bilgi için [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="isblocking"></a>  CSocket::IsBlocking

Engelleme çağrısının durumunda olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsBlocking();
```

### <a name="return-value"></a>Dönüş Değeri

Yuva engelleme olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="onmessagepending"></a>  CSocket::OnMessagePending

Bu üye işlevi ' Windows belirli iletileri arama ve, yuvaya yanıtlanması için geçersiz kılın.

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>Dönüş Değeri

İleti işlenmiş olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu gelişmiş bir, geçersiz kılınabilir.

Framework çağrıları `OnMessagePending` yuva, uygulamanıza ilgi iletileri için bir fırsat vermek için Windows iletileri Pompalama sırada. Nasıl kullanabileceğinize örnekler `OnMessagePending`, makaleye göz atın [Windows Yuvaları: Yuva sınıflarından türetme](../../mfc/windows-sockets-deriving-from-socket-classes.md).

Daha fazla bilgi için [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CAsyncSocket Sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket Sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocketFile Sınıfı](../../mfc/reference/csocketfile-class.md)
