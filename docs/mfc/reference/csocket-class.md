---
title: CSocket sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c423f1423c874dbf110cfd6951b3510fe0506af
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121883"
---
# <a name="csocket-class"></a>CSocket sınıfı
Türetilen `CAsyncSocket`, kendi kapsülleme Windows Sockets API devralır ve daha yüksek bir soyutlama düzeyi daha temsil bir `CAsyncSocket` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSocket::CSocket](#csocket)|Oluşturan bir `CSocket` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSocket::Attach](#attach)|Bir YUVA tanıtıcı ekler bir `CSocket` nesnesi.|  
|[CSocket::CancelBlockingCall](#cancelblockingcall)|Şu anda devam ediyor engelleyen bir aramayı iptal eder.|  
|[CSocket::Create](#create)|Bir yuva oluşturur.|  
|[CSocket::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CSocket` SOCKET tanıtıcısı verilen nesnesi.|  
|[CSocket::IsBlocking](#isblocking)|Bir engelleme çağrı sürüyor olup olmadığını belirler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSocket::OnMessagePending](#onmessagepending)|İşlem iletileri bekleyen bir engelleme çağrı tamamlanması beklenirken çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CSocket` çalışır sınıflarıyla `CSocketFile` ve `CArchive` gönderme ve alma veri yönetmek için.  
  
 A `CSocket` nesnesi de sağlar engellemek, zaman uyumlu çalışması için gerekli olduğu `CArchive`. İşlevler, gibi engelleme `Receive`, `Send`, `ReceiveFrom`, `SendTo`, ve `Accept` (öğesinden devralınan tüm `CAsyncSocket`), döndürmeyin bir `WSAEWOULDBLOCK` hata `CSocket`. Bunun yerine, işlemi tamamlanana kadar bu işlevler bekleyin. Ayrıca, özgün çağrısı WSAEINTR hatasıyla varsa sonlandıracak `CancelBlockingCall` Bu işlevlerden birini engelleme sırasında çağrılır.  
  
 Kullanılacak bir `CSocket` nesne, Oluşturucusu çağrısı'ı çağırın `Create` temel SOCKET tanıtıcısı (YUVA türü) oluşturmak için. Varsayılan parametreleri `Create` bir akışa yuva oluşturun ancak yuvasıyla kullanmıyorsanız bir `CArchive` nesnesi, bir veri birimi yuva oluşturun ya da bir sunucu yuva oluşturmak için belirli bir bağlantı noktasına bağlamak için bir parametre belirtebilirsiniz. Bir istemci yuva bağlamak için `Connect` istemci tarafında ve `Accept` sunucu tarafında. Ardından oluşturun bir `CSocketFile` nesne ve kendisine ilişkilendirmek `CSocket` nesnesinde `CSocketFile` Oluşturucusu. Ardından, oluşturun bir `CArchive` göndermek için nesne ve (gerektiğinde) veri almak için bir sonra ilişkilendirmek bunlarla `CSocketFile` nesnesinde `CArchive` Oluşturucusu. İletişim tamamlandığı zaman destroy `CArchive`, `CSocketFile`, ve `CSocket` nesneleri. YUVA veri türü makalesinde açıklanan [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md).  
  
 Kullandığınızda `CArchive` ile `CSocketFile` ve `CSocket`, bir durum karşılaşabilirsiniz nerede `CSocket::Receive` bir döngüye girer (tarafından `PumpMessages(FD_READ)`) istenen bayt miktarı için bekleniyor. Windows Yuvaları FD_READ bildirim başına yalnızca bir Al çağrısı izin Bunun nedeni, ancak `CSocketFile` ve `CSocket` FD_READ başına birden çok alınması çağrılarının izin verir. Okunacak veri yok olduğunda bir FD_READ alırsanız, uygulama askıda kalır. Hiçbir zaman başka bir FD_READ alırsanız, uygulama yuvası üzerinden iletişim kurmasını durdurur.  
  
 Bu sorun aşağıdaki gibi çözülebilir. İçinde `OnReceive` yöntemi sınıfınızın yuva çağrısı `CAsyncSocket::IOCtl(FIONREAD, ...)` çağırmadan önce `Serialize` yuvadan okumak için beklenen veri bir TCP paketi ağ ortamını (en büyük iletim birimi boyutunu aşarsa, ileti sınıfı yöntemi genellikle en az 1096 bayt). Kullanılabilir veri boyutu gereken daha az ise, alınması ve ardından yalnızca okuma işlemi başlatmak tüm veriler için bekleyin.  
  
 Aşağıdaki örnekte, `m_dwExpected` yaklaşık almak için kullanıcı bekliyor bayt sayısıdır. Başka bir yerde kodunuzda bildirirken olduğunu varsayılır.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]  
  
> [!NOTE]
>  Statik olarak bağlantılı bir MFC uygulamasında İkincil iş parçacıklarındaki MFC yuva kullanırken çağırmalısınız `AfxSocketInit` yuva kitaplıklarını başlatma yuva kullanan her bir iş parçacığı. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığı denir.  
  
 Daha fazla bilgi için bkz [MFC'de Windows Yuvaları](../../mfc/windows-sockets-in-mfc.md), [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Yuvaları: Yuva arşivler iş nasıl](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Yuvaları: işlem dizisi](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Yuvaları: Arşivlerle kullanılan yuvalara örnek](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxsock.h  
  
##  <a name="attach"></a>  CSocket::Attach  
 Bu üye işlevi ekleme çağrısı `hSocket` işlemek için bir `CSocket` nesnesi.  
  
```  
BOOL Attach(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Parametreler  
 *hSocket*  
 Bir yuva için bir tanıtıcı içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 SOCKET tanıtıcısı nesnesinin içinde depolanan [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) veri üyesi.  
  
 Daha fazla bilgi için bkz: [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]  
  
 [!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]  
  
##  <a name="cancelblockingcall"></a>  CSocket::CancelBlockingCall  
 Şu anda devam ediyor engelleyen bir çağrı iptal etmek için bu üye işlevini çağırın.  
  
```  
void CancelBlockingCall();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bu yuva için bekleyen tüm engelleme işlemi iptal eder. Özgün engelleme çağrısı mümkün olan en kısa sürede WSAEINTR hata ile sona erdirir.  
  
 Bir engelleme söz konusu olduğunda `Connect` işlem, Windows Sockets uygulaması sonlandırılacak engelleme çağrısı mümkün, ancak bağlantı tamamlandı (ve ardından sıfırlanmış kadar) yayımlanacak yuva kaynaklarını mümkün olmayabilir hemen veya zaman aşımına uğradı. Bu, yalnızca uygulama hemen (hiçbir yuva mevcutsa) yeni bir yuva açın ya da aynı eşler arası bağlanmaya çalışırsa belirgin olması olasıdır.  
  
 Herhangi bir işlem dışında iptal etme `Accept` yuva belirlenmemiş bir durum bırakabilirsiniz. Bir uygulama bir yuvada engelleme işlemi iptal ederse, uygulama yuvada gerçekleştirme yetkisi olan bağlı yalnızca bir çağrı işlemdir `Close`, ancak diğer işlemleri bazı Windows Sockets uygulamaları üzerinde çalışabilir. Uygulamanız için en fazla taşınabilirlik üzerinde isterse sonra iptal etme işlemlerini gerçekleştirme üzerinde bağımlı değil dikkatli olmanız gerekir.  
  
 Daha fazla bilgi için bkz: [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="create"></a>  CSocket::Create  
 Çağrı **oluşturma** Windows yuva oluşturmak ve bunu eklemek için yuva nesnesi oluşturma sonra üye işlevi.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *nSocketPort*  
 Bir bağlantı noktasını seçmek için MFC istiyorsanız yuva veya 0 ile kullanılmak üzere belirli bir bağlantı.  
  
 *nSocketType*  
 SOCK_STREAM veya SOCK_DGRAM.  
  
 *lpszSocketAddress*  
 Bağlı bir yuva, noktalı sayıyı "128.56.22.8" gibi ağ adresini içeren bir dize için bir işaretçi. Bu parametre gösterir için dizesi NULL geçirme `CSocket` örneği istemci etkinliği tüm ağ arabirimlerindeki dinler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi halde 0 ve belirli bir kodu çağırarak alınabilir `GetLastError`.  
  
### <a name="remarks"></a>Açıklamalar  
 `Create` Daha sonra çağırır `Bind` belirtilen adresine yuvası bağlama. Şu yuva türleri desteklenir:  
  
- SOCK_STREAM sıralı, güvenilir, iki yönlü, bağlantı tabanlı bayt akışları sağlar. İletim Denetimi Protokolü (TCP) Internet adresi ailesini kullanır.  
  
- Bağlantısız, güvenilir olmayan arabellek sabit (genellikle küçük) maksimum uzunluktaki SOCK_DGRAM desteklediği veri birimi. Kullanıcı Veri Birimi Protokolü (UDP) Internet adresi ailesini kullanır. Bu seçeneği kullanmak için yuvasıyla kullanmamanız gerekir bir `CArchive` nesnesi.  
  
    > [!NOTE]
    >  `Accept` Üye işlevi yeni, boş bir başvuru alır `CSocket` , parametre olarak nesne. Arama yapmadan önce bu nesneyi oluşturmalıdır `Accept`. Aklınızda bu yuva nesnesi kapsamını, bağlantıyı kapatır kalırsa. Çağırmayın `Create` bu yeni yuva nesnesi için.  
  
 Akış ve veri birimi yuvaları hakkında daha fazla bilgi için makalelerine bakın [Windows Yuvaları: arka plan](../../mfc/windows-sockets-background.md), [Windows Yuvaları: bağlantı noktaları ve yuva adresleri](../../mfc/windows-sockets-ports-and-socket-addresses.md), ve [Windows Yuvaları: kullanma Yuvaların arşivlerle](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="csocket"></a>  CSocket::CSocket  
 Oluşturan bir `CSocket` nesnesi.  
  
```  
CSocket();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yapım sonra çağırmalısınız `Create` üye işlevi.  
  
 Daha fazla bilgi için bkz: [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="fromhandle"></a>  CSocket::FromHandle  
 Bir işaretçi döndüren bir `CSocket` nesnesi.  
  
```  
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Parametreler  
 *hSocket*  
 Bir yuva için bir tanıtıcı içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CSocket` nesne veya yoksa NULL hiçbir `CSocket` nesne iliştirilmiş *hSocket*.  
  
### <a name="remarks"></a>Açıklamalar  
 SOCKET tanıtıcısı varsa verildiğinde bir `CSocket` tanıtıcısını nesnesi bağlı değil, üye fonksiyonu NULL döndürür ve geçici bir nesne oluşturmaz.  
  
 Daha fazla bilgi için bkz: [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="isblocking"></a>  CSocket::IsBlocking  
 Bir engelleme çağrı sürüyor olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsBlocking();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yuva engelliyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="onmessagepending"></a>  CSocket::OnMessagePending  
 Bu üye işlevi Windows'dan belirli iletileri arama ve onlara, yuvaya yanıt için geçersiz kılar.  
  
```  
virtual BOOL OnMessagePending();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işleniyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Gelişmiş budur geçersiz kılınabilir.  
  
 Framework çağrıları `OnMessagePending` yuva uygulamanıza ilgi iletileri uğraşmanız olanağı vermek için Windows iletileri Pompalama sırada. Nasıl kullanabileceğinize örnekler `OnMessagePending`, makaleye bakın [Windows Yuvaları: Yuva sınıflarından türetme](../../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Daha fazla bilgi için bkz: [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAsyncSocket sınıfı](../../mfc/reference/casyncsocket-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket sınıfı](../../mfc/reference/casyncsocket-class.md)   
 [CSocketFile Sınıfı](../../mfc/reference/csocketfile-class.md)
