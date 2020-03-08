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
ms.openlocfilehash: a861e557b7368d13d615aaf796faded93c72b040
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78854603"
---
# <a name="csocket-class"></a>CSocket sınıfı

`CAsyncSocket`türetilir, Windows Sockets API 'sinin kapsüllemesini devralır ve bir `CAsyncSocket` nesnesinden daha yüksek bir soyutlama düzeyini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSocket:: CSocket](#csocket)|`CSocket` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSocket:: Attach](#attach)|Bir `CSocket` nesnesine bir yuva tutamacı iliştirir.|
|[CSocket:: CancelBlockingCall](#cancelblockingcall)|Şu anda devam eden bir engelleme çağrısını iptal eder.|
|[CSocket:: Create](#create)|Yuva oluşturur.|
|[CSocket:: FromHandle](#fromhandle)|YUVA tutamacı verilen `CSocket` nesnesine bir işaretçi döndürür.|
|[CSocket:: ısengelliyor](#isblocking)|Bir engelleme çağrısının devam edilip edilmeyeceğini belirler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSocket:: OnMessagePending](#onmessagepending)|Bir engelleme çağrısının tamamlanmasını beklerken bekleyen iletileri işlemek için çağırılır.|

## <a name="remarks"></a>Açıklamalar

`CSocket`, verilerin gönderilmesini ve alınmasını yönetmek için `CSocketFile` ve `CArchive` sınıflarla birlikte kullanılabilir.

`CSocket` bir nesne, `CArchive`zaman uyumlu işlemi için gerekli olan engellemeyi de sağlar. `Receive`, `Send`, `ReceiveFrom`, `SendTo`ve `Accept` (tüm `CAsyncSocket`devralınmış) gibi engelleme işlevleri, `WSAEWOULDBLOCK` bir `CSocket`hatası döndürmez. Bunun yerine, bu işlevler işlem tamamlanana kadar bekler. Ayrıca, bu işlevlerden biri engellenirken `CancelBlockingCall` çağrılırsa, özgün çağrı WSAEINTR hatası ile sonlandırılır.

`CSocket` nesnesini kullanmak için, oluşturucuyu çağırın, sonra temeldeki yuva tanıtıcısını oluşturmak için `Create` çağırın (tip yuvası). `Create` varsayılan parametreleri bir akış yuvası oluşturur, ancak yuvayı bir `CArchive` nesnesiyle kullanmıyorsanız, bunun yerine bir veri birimi yuvası oluşturmak için bir parametre belirtebilir veya bir sunucu yuvası oluşturmak için belirli bir bağlantı noktasına bağlanabilirsiniz. İstemci tarafında `Connect` ve sunucu tarafında `Accept` kullanarak bir istemci yuvasına bağlanın. Sonra bir `CSocketFile` nesnesi oluşturun ve bunu `CSocketFile` oluşturucusunda `CSocket` nesnesiyle ilişkilendirin. Daha sonra, verileri almak için bir `CArchive` nesnesi oluşturun (gerektiğinde) ve ardından bunları `CArchive` oluşturucusunda `CSocketFile` nesnesiyle ilişkilendirin. İletişimler tamamlandığında `CArchive`, `CSocketFile`ve `CSocket` nesnelerini yok edin. YUVA veri türü, [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md)makalesinde açıklanmaktadır.

`CSocketFile` ve `CSocket`ile `CArchive` kullandığınızda `CSocket::Receive`, istenen bayt miktarını bekleyen bir döngüye (`PumpMessages(FD_READ)`göre) giren bir durumla karşılaşabilirsiniz. Bunun nedeni, Windows Yuvaları FD_READ bildirimi başına yalnızca bir alma çağrısına izin ver, ancak `CSocketFile` ve `CSocket` FD_READ başına birden çok alınan çağrıya izin veriyor. Okunacak veri olmadığında bir FD_READ alırsanız uygulama askıda kalır. Daha önce başka bir FD_READ alamazsanız, uygulama yuva üzerinden iletişim kurmasını durduruyor.

Bu sorunu aşağıdaki şekilde çözebilirsiniz. Yuva sınıfınızın `OnReceive` yönteminde, yuvadan okunan beklenen veriler bir TCP paketinin boyutunu (genellikle en az 1096 bayt) aştığında, ileti sınıfınızın `Serialize` yöntemini çağırmadan önce, `CAsyncSocket::IOCtl(FIONREAD, ...)` çağırın. Kullanılabilir verilerin boyutu gerekenden küçükse, tüm verilerin alınmasını bekleyin ve sonra okuma işlemini başlatın.

Aşağıdaki örnekte `m_dwExpected`, kullanıcının almayı beklediği yaklaşık bayt sayısıdır. Kodunuzun başka bir yerinde bildirdiğiniz varsayılır.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
>  Statik olarak bağlı bir MFC uygulamasında ikincil iş parçacıklarında MFC Yuvaları kullanırken, yuva kitaplıklarını başlatmak için yuva kullanan her iş parçacığında `AfxSocketInit` çağırmanız gerekir. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığında çağırılır.

Daha fazla bilgi için bkz. [MFC 'de Windows Yuvaları](../../mfc/windows-sockets-in-mfc.md), Windows Yuvaları [: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Yuvaları: Arşivlerle ilgili yuvalar nasıl çalışır](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Yuvaları: Işlem dizisi](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Yuvaları: arşivleri kullanan yuvalar örneği](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket 'ini kullanma](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsock. h

##  <a name="attach"></a>CSocket:: Attach

`hSocket` işleyicisini bir `CSocket` nesnesine iliştirmek için bu üye işlevi çağırın.

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>Parametreler

*hSocket*<br/>
Yuva için bir tanıtıcı içerir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı.

### <a name="remarks"></a>Açıklamalar

YUVA tutamacı nesnenin [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) veri üyesinde depolanır.

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

##  <a name="cancelblockingcall"></a>CSocket:: CancelBlockingCall

Sürmekte olan bir engelleme çağrısını iptal etmek için bu üye işlevi çağırın.

```
void CancelBlockingCall();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, bu yuva için bekleyen engelleyici işlemleri iptal eder. Özgün engelleme çağrısı, WSAEINTR hatası ile mümkün olan en kısa sürede sona erecek.

Engelleme `Connect` işlemi durumunda, Windows Yuvaları uygulamasının engelleme çağrısını mümkün olan en kısa sürede sonlandıracağından, ancak bağlantı tamamlanana kadar (ve sonra sıfırlandıktan) veya zaman aşımına uğramadan yuva kaynaklarının serbest bırakılması mümkün olmayabilir. Bu, yalnızca uygulama hemen yeni bir yuva açmaya (yuva yoksa) veya aynı eşe bağlanmayı denediğinde fark edilebilir olması olasıdır.

`Accept` dışındaki herhangi bir işlemi iptal etmek, yuvayı belirsiz bir durumda bırakabilir. Bir uygulama bir yuva üzerinde engelleyici bir işlemi iptal ederse, uygulamanın yuva üzerinde gerçekleştirebilmesinin bağlı olabileceği tek işlem, bazı Windows Yuvaları uygulamalarında başka işlemler çalışabilse de `Close`bir çağrıdır. Uygulamanız için maksimum taşınabilirlik yaptıysanız, iptal işleminden sonra işlem gerçekleştirmeye bağlı olmadığından dikkatli olmanız gerekir.

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="create"></a>CSocket:: Create

Windows yuvasını oluşturmak ve eklemek için bir yuva nesnesi oluşturduktan sonra üye **Oluştur** işlevini çağırın.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Parametreler

*nSocketPort*<br/>
Belirli bir bağlantı noktası, yuvada kullanılmak üzere veya MFC 'nin bir bağlantı noktasını seçmesini istiyorsanız 0.

*nSocketType*<br/>
SOCK_STREAM veya SOCK_DGRAM.

*lpszSocketAddress*<br/>
Bağlı yuvanın ağ adresini içeren bir dize işaretçisi, "128.56.22.8" gibi noktalı bir sayıdır. Bu parametre için NULL dizenin geçirilmesi, `CSocket` örneğinin tüm ağ arabirimlerinde istemci etkinliğini dinlemesi gerektiğini gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve `GetLastError`çağırarak belirli bir hata kodu alınabilir.

### <a name="remarks"></a>Açıklamalar

`Create` ardından, yuvayı belirtilen adrese bağlamak için `Bind` çağırır. Aşağıdaki yuva türleri desteklenir:

- SOCK_STREAM sıralı, güvenilir, iki yönlü, bağlantı tabanlı bayt akışları sağlar. Internet adresi ailesi için Iletim Denetim Protokolü (TCP) kullanır.

- SOCK_DGRAM, bağlantısız, güvenilir olmayan (genellikle küçük) bir uzunluk üst sınırı olan datagramları destekler. Internet adresi ailesi için Kullanıcı Datagram Protokolü (UDP) kullanır. Bu seçeneği kullanmak için, yuvayı bir `CArchive` nesnesiyle birlikte kullanamazsınız.

    > [!NOTE]
    >  `Accept` member işlevi, parametresi olarak yeni, boş bir `CSocket` nesnesine bir başvuru alır. `Accept`çağırmadan önce bu nesneyi oluşturmanız gerekir. Bu yuva nesnesi kapsam dışına geçtiğinde bağlantının kapandığını aklınızda bulundurun. Bu yeni yuva nesnesi için `Create` çağırmayın.

Stream ve datagram yuvaları hakkında daha fazla bilgi için bkz. [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md), [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../../mfc/windows-sockets-ports-and-socket-addresses.md)ve [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="csocket"></a>CSocket:: CSocket

`CSocket` nesnesi oluşturur.

```
CSocket();
```

### <a name="remarks"></a>Açıklamalar

Oluşturma işleminden sonra `Create` üye işlevini çağırmanız gerekir.

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="fromhandle"></a>CSocket:: FromHandle

`CSocket` nesnesine bir işaretçi döndürür.

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Parametreler

*hSocket*<br/>
Yuva için bir tanıtıcı içerir.

### <a name="return-value"></a>Dönüş Değeri

`CSocket` nesnesine yönelik bir işaretçi veya *hSocket*'e iliştirilmiş bir `CSocket` NESNESI yoksa null.

### <a name="remarks"></a>Açıklamalar

Bir yuva tutamacı verildiğinde, tanıtıcıya ekli bir `CSocket` nesnesi yoksa, üye işlevi NULL döndürür ve geçici bir nesne oluşturmaz.

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="isblocking"></a>CSocket:: ısengelliyor

Bir engelleme çağrısının devam ettiğini öğrenmek için bu üye işlevi çağırın.

```
BOOL IsBlocking();
```

### <a name="return-value"></a>Dönüş Değeri

Yuva engellense sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="onmessagepending"></a>CSocket:: OnMessagePending

Windows 'dan belirli iletileri aramak ve bu üye işlevini yuvaınızdan yanıtlamak için geçersiz kılın.

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu gelişmiş bir geçersiz kılınabilir.

Çerçeve, uygulamanıza ilişkin iletilerle ilgilenme olanağı sunmak için yuva Windows iletilerini pompalarken `OnMessagePending` çağırır. `OnMessagePending`nasıl kullanabileceğinizi gösteren örnekler için, [Windows Yuvaları: yuva sınıflarından türetme](../../mfc/windows-sockets-deriving-from-socket-classes.md)makalesine bakın.

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="see-also"></a>Ayrıca bkz.

[CAsyncSocket Sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket Sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocketFile Sınıfı](../../mfc/reference/csocketfile-class.md)
