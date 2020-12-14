---
description: 'Daha fazla bilgi edinin: CSocket sınıfı'
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
ms.openlocfilehash: e04fc0b453c4d4172fcd286b142d029bda0eb5dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345114"
---
# <a name="csocket-class"></a>CSocket sınıfı

Öğesinden türetilir `CAsyncSocket` , Windows SOCKETS API 'sinin kapsüllemesini devralır ve bir nesneden daha yüksek bir soyutlama düzeyini temsil eder `CAsyncSocket` .

## <a name="syntax"></a>Syntax

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSocket:: CSocket](#csocket)|Bir `CSocket` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSocket:: Attach](#attach)|Bir nesneye bir yuva tutamacı iliştirir `CSocket` .|
|[CSocket:: CancelBlockingCall](#cancelblockingcall)|Şu anda devam eden bir engelleme çağrısını iptal eder.|
|[CSocket:: Create](#create)|Yuva oluşturur.|
|[CSocket:: FromHandle](#fromhandle)|Bir `CSocket` yuva tutamacı verilen bir nesneye bir işaretçi döndürür.|
|[CSocket:: ısengelliyor](#isblocking)|Bir engelleme çağrısının devam edilip edilmeyeceğini belirler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSocket:: OnMessagePending](#onmessagepending)|Bir engelleme çağrısının tamamlanmasını beklerken bekleyen iletileri işlemek için çağırılır.|

## <a name="remarks"></a>Açıklamalar

`CSocket` sınıflarla birlikte çalışarak `CSocketFile` `CArchive` verilerin gönderilmesini ve alınmasını yönetir.

Bir `CSocket` nesne, zaman uyumlu işlemi için gerekli olan engellemeyi de sağlar `CArchive` . ,,, Ve gibi engelleme işlevleri,,, `Receive` `Send` `ReceiveFrom` `SendTo` ve `Accept` (tüm devralınan `CAsyncSocket` ), içinde bir hata döndürmez `WSAEWOULDBLOCK` `CSocket` . Bunun yerine, bu işlevler işlem tamamlanana kadar bekler. Ayrıca, `CancelBlockingCall` Bu işlevlerden biri engellenirken çağrıldığında, özgün çağrı WSAEINTR hatası ile sonlandırılır.

Bir nesne kullanmak için, `CSocket` oluşturucuyu çağırın, sonra `Create` temel yuva tanıtıcısını (tür yuvası) oluşturmak için çağırın. `Create`Bir akış yuvası oluşturma varsayılan parametreleri, ancak bir nesneyle bir yuva kullanmıyorsanız, `CArchive` bunun yerine bir veri birimi yuvası oluşturmak için bir parametre belirtebilir veya bir sunucu yuvası oluşturmak için belirli bir bağlantı noktasına bağlayabilirsiniz. `Connect`İstemci tarafında ve sunucu tarafında kullanarak bir istemci yuvasına bağlanın `Accept` . Sonra bir `CSocketFile` nesne oluşturun ve `CSocket` `CSocketFile` oluşturucudaki nesneyle ilişkilendirin. Daha `CArchive` sonra, göndermek için bir nesne oluşturun (gerektiğinde) ve ardından bunları `CSocketFile` `CArchive` oluşturucudaki nesnesiyle ilişkilendirin. İletişimler tamamlandığında,, `CArchive` ve nesnelerini yok edin `CSocketFile` `CSocket` . YUVA veri türü, [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md)makalesinde açıklanmaktadır.

`CArchive`Ve ile kullandığınızda `CSocketFile` `CSocket` , `CSocket::Receive` `PumpMessages(FD_READ)` istenen bayt miktarını bekleyen bir döngüye (by) giren bir durumla karşılaşabilirsiniz. Bunun nedeni, Windows Yuvaları FD_READ bildirimi başına yalnızca bir alma çağrısına izin ver, `CSocketFile` ancak `CSocket` fd_read başına birden çok alınan çağrıya izin verir. Okunacak veri olmadığında bir FD_READ alırsanız uygulama askıda kalır. Daha önce başka bir FD_READ alamazsanız, uygulama yuva üzerinden iletişim kurmasını durduruyor.

Bu sorunu aşağıdaki şekilde çözebilirsiniz. `OnReceive`Yuva sınıfınızın yönteminde, `CAsyncSocket::IOCtl(FIONREAD, ...)` `Serialize` yuvadan okunan beklenen veriler bir TCP paketinin boyutunu (genellikle en az 1096 bayt) aştığında, size ileti sınıfınızın yöntemini çağırmadan önce çağırın. Kullanılabilir verilerin boyutu gerekenden küçükse, tüm verilerin alınmasını bekleyin ve sonra okuma işlemini başlatın.

Aşağıdaki örnekte, `m_dwExpected` kullanıcının almayı beklediği yaklaşık bayt sayısıdır. Kodunuzun başka bir yerinde bildirdiğiniz varsayılır.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
> Statik olarak bağlı bir MFC uygulamasında ikincil iş parçacıklarında MFC Yuvaları kullanırken, `AfxSocketInit` yuva kitaplıklarını başlatmak için yuva kullanan her bir iş parçacığında çağrı yapmanız gerekir. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığında çağırılır.

Daha fazla bilgi için bkz. [MFC 'de Windows Yuvaları](../../mfc/windows-sockets-in-mfc.md), Windows Yuvaları [: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Yuvaları: Arşivlerle ilgili yuvalar nasıl çalışır](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Yuvaları: Işlem dizisi](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Yuvaları: arşivleri kullanan yuvalar örneği](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket 'ini kullanma](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsock. h

## <a name="csocketattach"></a><a name="attach"></a> CSocket:: Attach

Tanıtıcıyı bir nesneye iliştirmek için bu üye işlevini çağırın `hSocket` `CSocket` .

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

## <a name="csocketcancelblockingcall"></a><a name="cancelblockingcall"></a> CSocket:: CancelBlockingCall

Sürmekte olan bir engelleme çağrısını iptal etmek için bu üye işlevi çağırın.

```cpp
void CancelBlockingCall();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, bu yuva için bekleyen engelleyici işlemleri iptal eder. Özgün engelleme çağrısı, WSAEINTR hatası ile mümkün olan en kısa sürede sona erecek.

Engelleyici bir işlem söz konusu olduğunda `Connect` , Windows Yuvaları uygulamasının engelleme çağrısını mümkün olan en kısa sürede sonlandıracağından, ancak bağlantı tamamlanana (ve sonra sıfırlanmadan) veya zaman aşımına uğramadan yuva kaynaklarının serbest bırakılması mümkün olmayabilir. Bu, yalnızca uygulama hemen yeni bir yuva açmaya (yuva yoksa) veya aynı eşe bağlanmayı denediğinde fark edilebilir olması olasıdır.

Dışında herhangi bir işlemi iptal etmek `Accept` , yuvayı belirsiz bir durumda bırakabilir. Bir uygulama bir yuva üzerinde engelleyici bir işlemi iptal ederse, uygulamanın yuva üzerinde gerçekleştirebilmesinin bağımlı olabileceği tek işlem, `Close` bazı Windows Yuvaları uygulamalarında başka işlemler çalışabilse de ' a bir çağrıdır. Uygulamanız için maksimum taşınabilirlik yaptıysanız, iptal işleminden sonra işlem gerçekleştirmeye bağlı olmadığından dikkatli olmanız gerekir.

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="csocketcreate"></a><a name="create"></a> CSocket:: Create

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
Bağlı yuvanın ağ adresini içeren bir dize işaretçisi, "128.56.22.8" gibi noktalı bir sayıdır. Bu parametre için NULL dizenin geçirilmesi, `CSocket` Örneğin tüm ağ arabirimlerinde istemci etkinliğini dinlemesi gerektiğini gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0 ve belirli bir hata kodu çağırarak elde edilebilir `GetLastError` .

### <a name="remarks"></a>Açıklamalar

`Create` ardından `Bind` , yuvayı belirtilen adrese bağlamak için çağırır. Aşağıdaki yuva türleri desteklenir:

- SOCK_STREAM sıralı, güvenilir, iki yönlü, bağlantı tabanlı bayt akışları sağlar. Internet adresi ailesi için Iletim Denetim Protokolü (TCP) kullanır.

- SOCK_DGRAM, bağlantısız, güvenilir olmayan (genellikle küçük) bir uzunluk üst sınırı olan datagramları destekler. Internet adresi ailesi için Kullanıcı Datagram Protokolü (UDP) kullanır. Bu seçeneği kullanmak için, yuvasını bir nesnesiyle birlikte kullanamazsınız `CArchive` .

    > [!NOTE]
    >  `Accept`Üye işlevi, parametresi olarak yeni, boş bir nesneye başvuru alır `CSocket` . Bu nesneyi, çağrısından önce oluşturmanız gerekir `Accept` . Bu yuva nesnesi kapsam dışına geçtiğinde bağlantının kapandığını aklınızda bulundurun. `Create`Bu yeni yuva nesnesi için çağrı kullanmayın.

Stream ve datagram yuvaları hakkında daha fazla bilgi için bkz. [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md), [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../../mfc/windows-sockets-ports-and-socket-addresses.md)ve [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="csocketcsocket"></a><a name="csocket"></a> CSocket:: CSocket

Bir `CSocket` nesnesi oluşturur.

```
CSocket();
```

### <a name="remarks"></a>Açıklamalar

Oluşturma işleminden sonra üye işlevini çağırmanız gerekir `Create` .

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="csocketfromhandle"></a><a name="fromhandle"></a> CSocket:: FromHandle

Nesnesine bir işaretçi döndürür `CSocket` .

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Parametreler

*hSocket*<br/>
Yuva için bir tanıtıcı içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir nesne işaretçisi `CSocket` veya `CSocket` *hSocket*'e iliştirilmiş nesne yoksa null.

### <a name="remarks"></a>Açıklamalar

Bir yuva tutamacı verildiğinde, bir `CSocket` nesne tutamaya ekli değilse, üye IşLEVI null döndürür ve geçici bir nesne oluşturmaz.

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="csocketisblocking"></a><a name="isblocking"></a> CSocket:: ısengelliyor

Bir engelleme çağrısının devam ettiğini öğrenmek için bu üye işlevi çağırın.

```
BOOL IsBlocking();
```

### <a name="return-value"></a>Dönüş Değeri

Yuva engellense sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="csocketonmessagepending"></a><a name="onmessagepending"></a> CSocket:: OnMessagePending

Windows 'dan belirli iletileri aramak ve bu üye işlevini yuvaınızdan yanıtlamak için geçersiz kılın.

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu gelişmiş bir geçersiz kılınabilir.

Çerçeve, `OnMessagePending` size uygulamanıza ilişkin iletilerle ilgilenme fırsatı vermek için yuva Windows iletileri oluştururken çağrılır. Nasıl kullanabileceğinizi gösteren örnekler için `OnMessagePending` , [Windows Yuvaları: yuva sınıflarından türetme](../../mfc/windows-sockets-deriving-from-socket-classes.md)makalesine bakın.

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="see-also"></a>Ayrıca bkz.

[CAsyncSocket sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocketFile sınıfı](../../mfc/reference/csocketfile-class.md)
