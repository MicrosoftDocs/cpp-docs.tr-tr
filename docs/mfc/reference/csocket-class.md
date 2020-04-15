---
title: CSocket Sınıfı
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
ms.openlocfilehash: 3f0a7a9a90250ede7b112cfbd9bc1ca14d583356
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318188"
---
# <a name="csocket-class"></a>CSocket Sınıfı

`CAsyncSocket`Windows Soketleri API'sinin kapsüllemesini devralır ve bir `CAsyncSocket` nesneninkinden daha yüksek bir soyutlama düzeyini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSocket::CSocket](#csocket)|Bir `CSocket` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSocket::Ekle](#attach)|Bir `CSocket` nesneye SOKET tutamacı bağlar.|
|[CSocket::CancelBlockingCall](#cancelblockingcall)|Şu anda devam etmekte olan engelleme çağrısını iptal eder.|
|[CSocket::Oluştur](#create)|Bir soket oluşturur.|
|[CSocket::FromHandle](#fromhandle)|SOCKET tutamacı `CSocket` verilen bir nesneye işaretçi döndürür.|
|[CSocket::Engelleme](#isblocking)|Engelleme çağrısının devam edip etmediğini belirler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSocket::OnMessagePending](#onmessagepending)|Engelleme çağrısının tamamlanmasını beklerken bekleyen iletileri işlemek için çağrıldı.|

## <a name="remarks"></a>Açıklamalar

`CSocket`sınıflarla `CSocketFile` çalışır `CArchive` ve veri gönderme ve alma işlerini yönetir.

Bir `CSocket` nesne de senkron işlemi için gerekli olan `CArchive`engelleme sağlar. Engelleme işlevleri, gibi `Receive` `Send`, `ReceiveFrom` `SendTo`, `Accept` , , ve `CAsyncSocket`(tüm devralınan ), bir `WSAEWOULDBLOCK` hata döndürmez `CSocket`. Bunun yerine, bu işlevler işlem tamamlanana kadar bekler. Ayrıca, bu işlevlerden biri engellenirken `CancelBlockingCall` çağrıldığında özgün arama WSAEINTR hatasıyla sonlanır.

Bir `CSocket` nesneyi kullanmak için oluşturucuyu `Create` çağırın, ardından altta yatan SOCKET tutamacını (TIP SOCKET) oluşturmak için arayın. Bir akış `Create` soketi oluşturmanın varsayılan parametreleri, ancak bir `CArchive` nesne ile soket kullanmıyorsanız, yerine bir veri gramgayı soketi oluşturmak için bir parametre belirtebilir veya bir sunucu yuvası oluşturmak için belirli bir bağlantı noktasına bağlayabilirsiniz. İstemci tarafında `Connect` ve `Accept` sunucu tarafında kullanarak bir istemci soketine bağlanın. Sonra bir `CSocketFile` nesne oluşturun ve `CSocket` `CSocketFile` oluşturucudaki nesneyle ilişkilendirin. Ardından, göndermek `CArchive` için bir nesne ve veri almak için bir nesne `CSocketFile` (gerektiği `CArchive` gibi) oluşturun, ardından bunları oluşturucudaki nesneyle ilişkilendirin. İletişim tamamlandığında, nesneleri `CArchive` `CSocketFile`ve `CSocket` nesneleri yok edin. SOCKET veri türü makalede [Windows Soketleri açıklanmıştır: Arka plan.](../../mfc/windows-sockets-background.md)

`CArchive` Kullandığınızda `CSocketFile` ve `CSocket`, istenilen bayt `CSocket::Receive` miktarını bekleyen bir `PumpMessages(FD_READ)`döngü (by) girer bir durumla karşılaşabilirsiniz. Bunun nedeni, `CSocketFile` Windows soketlerinin FD_READ bildirimi başına yalnızca `CSocket` bir recv araması ve FD_READ başına birden çok recv araması izni sağlamasıdır. Okunacak veri olmadığında FD_READ alırsanız, uygulama askıda kalır. Başka bir FD_READ alamazsanız, uygulama soket üzerinden iletişimi durdurur.

Bu sorunu aşağıdaki gibi çözebilirsiniz. Soket `OnReceive` sınıfının yönteminde, `CAsyncSocket::IOCtl(FIONREAD, ...)` soketten `Serialize` okunması beklenen veriler bir TCP paketinin boyutunu aştığında (genellikle en az 1096 bayt olan ağ ortamının maksimum iletim birimi) ileti sınıfının yöntemini aramadan önce arayın. Kullanılabilir verilerin boyutu gerekenden daha azsa, tüm verilerin alınmasını bekleyin ve ancak o zaman okuma işlemini başlatın.

Aşağıdaki örnekte, `m_dwExpected` kullanıcının almayı beklediği yaklaşık bayt sayısıdır. Kodunuzun başka bir yerinde beyan ettiğiniz varsayılır.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
> Statik olarak bağlı bir MFC uygulamasında ikincil iş parçacıklarında MFC `AfxSocketInit` soketleri kullanırken, soket kitaplıklarını başlatmak için soket kullanan her iş parçacığı çağırmanız gerekir. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığı denir.

Daha fazla bilgi için, [MFC'deki Windows Soketleri](../../mfc/windows-sockets-in-mfc.md), [Windows Soketleri: Arşivli Soketleri Kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Soketleri: Arşivlerle Soketler Nasıl Çalışır](../../mfc/windows-sockets-how-sockets-with-archives-work.md), Windows [Soketleri: İşlem sırası](../../mfc/windows-sockets-sequence-of-operations.md), Windows [Soketleri: Arşivleri Kullanan Soketler Örneği](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Casyncsocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsock.h

## <a name="csocketattach"></a><a name="attach"></a>CSocket::Ekle

Tutamacı bir `CSocket` nesneye `hSocket` takmak için bu üye işlevi çağırın.

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>Parametreler

*hSoket*<br/>
Bir soketiçin bir tutamaç içerir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfıra inme.

### <a name="remarks"></a>Açıklamalar

SOCKET tutamacı nesnenin [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) veri üyesinde depolanır.

Daha fazla bilgi için [Windows Soketleri: Arşivli Soketleri Kullanma.](../../mfc/windows-sockets-using-sockets-with-archives.md)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

## <a name="csocketcancelblockingcall"></a><a name="cancelblockingcall"></a>CSocket::CancelBlockingCall

Şu anda devam etmekte olan engelleme çağrısını iptal etmek için bu üye işlevini arayın.

```
void CancelBlockingCall();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, bu soket için bekleyen engelleme işlemini iptal eder. Özgün engelleme çağrısı, WSAEINTR hatasıyla mümkün olan en kısa sürede sonlanır.

Engelleme `Connect` işlemi söz konusu olduğunda, Windows Soketleri uygulaması engelleme çağrısını mümkün olan en kısa sürede sonlandırır, ancak bağlantı tamamlanana (ve sonra zamana kadar sıfırlanana) veya zaman alıyana kadar soket kaynaklarının serbest bırakılması mümkün olmayabilir. Bu durum, yalnızca uygulama hemen yeni bir soket açmaya çalışırsa (soket yoksa) veya aynı eşe bağlanmaya çalışırsa fark edilebilir.

Yuvayı belirsiz bir `Accept` durumda bırakabilecek başka bir işlemi iptal etmek. Bir uygulama bir soket üzerindeki engelleme işlemini iptal ederse, uygulamanın yuvada gerçekleştirebilmesine bağlı `Close`olabileceği tek işlem, bazı Windows Soketleri uygulamalarında çalışabilir, ancak bir çağrıdır. Uygulamanız için maksimum taşınabilirlik istiyorsanız, iptal edildikten sonra işlemleri gerçekleştirmeye bağlı olmamak için dikkatli olmalısınız.

Daha fazla bilgi için [Windows Soketleri: Arşivli Soketleri Kullanma.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketcreate"></a><a name="create"></a>CSocket::Oluştur

Windows soketi oluşturmak ve takmak için bir soket nesnesi oluşturduktan sonra **Üye Oluştur** işlevini çağırın.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Parametreler

*nSocketPort*<br/>
Soketle birlikte kullanılacak belirli bir bağlantı noktası veya MFC'nin bir bağlantı noktası seçmesini istiyorsanız 0.

*nSocketType*<br/>
SOCK_STREAM ya da SOCK_DGRAM.

*lpszSocketAddress*<br/>
Bağlı soketin ağ adresini içeren bir dize işaretçisi, "128.56.22.8" gibi noktalı bir sayı. Bu parametre için NULL dizesi geçmek, örneğin tüm ağ arabirimlerinde istemci etkinliğini dinlemesi `CSocket` gerektiğini gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 ve belirli bir hata `GetLastError`kodu arayarak alınabilir.

### <a name="remarks"></a>Açıklamalar

`Create`daha `Bind` sonra soketi belirtilen adrese bağlamak için çağırır. Aşağıdaki soket türleri desteklenir:

- SOCK_STREAM Sıralı, güvenilir, çift yönlü, bağlantı tabanlı bayt akışları sağlar. Internet adresi ailesi için İletim Denetim Protokolü 'nü (TCP) kullanır.

- SOCK_DGRAM Sabit (genellikle küçük) maksimum uzunlukta ki bağlantısız, güvenilir olmayan arabellekleri olan veri gramlarını destekler. Internet adresi ailesi için Kullanıcı VeriGram Protokolü 'nü (UDP) kullanır. Bu seçeneği kullanmak için soketi bir `CArchive` nesneyle kullanmamalısınız.

    > [!NOTE]
    >  `Accept` Üye işlev, parametresi olarak `CSocket` yeni, boş bir nesneye başvuru alır. Bu nesneyi aramadan `Accept`önce oluşturmanız gerekir. Bu soket nesnesi kapsam dışına çıkarsa, bağlantının kapandığını unutmayın. Bu yeni `Create` soket nesnesi için aramayın.

Akış ve veri gram soketleri hakkında daha fazla bilgi için [Windows Soketleri: Arka Plan,](../../mfc/windows-sockets-background.md) [Windows Soketleri: Bağlantı Noktaları ve Soket Adresleri](../../mfc/windows-sockets-ports-and-socket-addresses.md)ve Windows [Soketleri: Arşivli Soketleri Kullanma.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketcsocket"></a><a name="csocket"></a>CSocket::CSocket

Bir `CSocket` nesne inşa eder.

```
CSocket();
```

### <a name="remarks"></a>Açıklamalar

İnşaattan `Create` sonra üye işlevi aramalısınız.

Daha fazla bilgi için [Windows Soketleri: Arşivli Soketleri Kullanma.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketfromhandle"></a><a name="fromhandle"></a>CSocket::FromHandle

Bir işaretçiyi `CSocket` nesneye döndürür.

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Parametreler

*hSoket*<br/>
Bir soketiçin bir tutamaç içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir `CSocket` nesneye işaretçi veya `CSocket` *hSocket'e*bağlı bir nesne yoksa NULL .

### <a name="remarks"></a>Açıklamalar

Bir SOCKET tutamacı verildiğinde, bir `CSocket` nesne işkarasına bağlı değilse, üye işlev NULL döndürür ve geçici bir nesne oluşturmaz.

Daha fazla bilgi için [Windows Soketleri: Arşivli Soketleri Kullanma.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketisblocking"></a><a name="isblocking"></a>CSocket::Engelleme

Engelleme çağrısının devam edip etmeyolmadığını belirlemek için bu üye işlevini arayın.

```
BOOL IsBlocking();
```

### <a name="return-value"></a>Dönüş Değeri

Soket engelliyorsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Windows Soketleri: Arşivli Soketleri Kullanma.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketonmessagepending"></a><a name="onmessagepending"></a>CSocket::OnMessagePending

Windows'dan belirli iletileri aramak ve bunları yuvanızda yanıtlamak için bu üye işlevini geçersiz kılın.

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu gelişmiş bir geçersiz.

Yuva, `OnMessagePending` uygulamanızın ilgi çekici iletileriyle başa çıkma fırsatı vermek için Windows iletilerini pompalarken çerçeve çağırır. Nasıl kullanabileceğinize `OnMessagePending`örnekler için Windows [Soketleri: Soket Sınıflarından Türeyen](../../mfc/windows-sockets-deriving-from-socket-classes.md)makalesine bakın.

Daha fazla bilgi için [Windows Soketleri: Arşivli Soketleri Kullanma.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="see-also"></a>Ayrıca bkz.

[CAsyncSocket Sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket Sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[Csocketfile Sınıfı](../../mfc/reference/csocketfile-class.md)
