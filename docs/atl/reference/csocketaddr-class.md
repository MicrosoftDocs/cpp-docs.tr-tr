---
title: CSocketAddr Sınıfı
ms.date: 10/22/2018
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
ms.openlocfilehash: 66d33d62212389a2b0f318250c1c16a99167c6eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330690"
---
# <a name="csocketaddr-class"></a>CSocketAddr Sınıfı

Bu sınıf, hem IPv4 hem de IPV6 biçimlerini destekleyerek ana bilgisayar adlarını ana bilgisayar adreslerine dönüştürme yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSocketAddr
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSocketAddr::CSocketAddr](#csocketaddr)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSocketAddr::FindAddr](#findaddr)|Sağlanan ana bilgisayar adını ana bilgisayar adresine dönüştürmek için bu yöntemi arayın.|
|[CSocketAddr::FindINET4Addr](#findinet4addr)|IPv4 ana bilgisayar adını ana bilgisayar adresine dönüştürmek için bu yöntemi arayın.|
|[CSocketAddr::FindINET6Addr](#findinet6addr)|IPv6 ana bilgisayar adını ana bilgisayar adresine dönüştürmek için bu yöntemi arayın.|
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|Bir işaretçiyi listedeki belirli bir `addrinfo` öğeye döndürmek için bu yöntemi çağırın.|
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|Bir işaretçiyi listeye döndürmek `addrinfo` için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, windows soketleri API işlevleri ve kitaplıklarda soket sarıcı ile kullanılmak üzere ağ adresleri aramak için bir IP sürümü agnostik bir yaklaşım sağlar.

Ağ adreslerini aramak için kullanılan bu sınıfın üyeleri Win32 API işlevini [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)kullanın. İşlevin ANSI veya UNICODE sürümü, kodunuzun ANSI veya UNICODE için derlenip derlenmediğine bağlı olarak çağrılır.

Bu sınıf hem IPv4 ve IPv6 ağ adreslerini destekler.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsocket.h

## <a name="csocketaddrcsocketaddr"></a><a name="csocketaddr"></a>CSocketAddr::CSocketAddr

Oluşturucu.

```
CSocketAddr();
```

### <a name="remarks"></a>Açıklamalar

Yeni `CSocketAddr` bir nesne oluşturur ve ana bilgisayar hakkında yanıt bilgilerini içeren bağlantılı listeyi başlatılmasını.

## <a name="csocketaddrfindaddr"></a><a name="findaddr"></a>CSocketAddr::FindAddr

Sağlanan ana bilgisayar adını ana bilgisayar adresine dönüştürmek için bu yöntemi arayın.

```
int FindAddr(
    const TCHAR *szHost,
    const TCHAR *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const TCHAR *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```

### <a name="parameters"></a>Parametreler

*szHost*<br/>
Ana bilgisayar adı veya noktalı IP adresi.

*szPortOrServiceName*<br/>
Ana bilgisayardaki bağlantı noktası numarası veya hizmet adı.

*nPortNo*<br/>
Bağlantı noktası numarası.

*bayraklar*<br/>
0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST kombinasyonu.

*addr_family*<br/>
Adres ailesi (PF_INET gibi).

*sock_type*<br/>
Soket türü (SOCK_STREAM gibi).

*ai_proto*<br/>
Protokol (IPPROTO_IP veya IPPROTO_IPV6 gibi).

### <a name="return-value"></a>Dönüş Değeri

Adres başarıyla hesaplanırsa sıfır döndürür. Hata üzerinde sıfır olmayan bir Windows Soketi hata kodu verir. Başarılı olursa, hesaplanan adres kullanılarak `CSocketAddr::GetAddrInfoList` başvurulan bağlı bir listede `CSocketAddr::GetAddrInfo`depolanır ve .

### <a name="remarks"></a>Açıklamalar

Ana bilgisayar adı parametresi IPv4 veya IPv6 biçiminde olabilir. Bu yöntem, dönüştürme gerçekleştirmek için Win32 API işlevi [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) çağırır.

## <a name="csocketaddrfindinet4addr"></a><a name="findinet4addr"></a>CSocketAddr::FindINET4Addr

IPv4 ana bilgisayar adını ana bilgisayar adresine dönüştürmek için bu yöntemi arayın.

```
int FindINET4Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>Parametreler

*szHost*<br/>
Ana bilgisayar adı veya noktalı IP adresi.

*nPortNo*<br/>
Bağlantı noktası numarası.

*bayraklar*<br/>
0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST kombinasyonu.

*sock_type*<br/>
Soket türü (SOCK_STREAM gibi).

### <a name="return-value"></a>Dönüş Değeri

Adres başarıyla hesaplanırsa sıfır döndürür. Hata üzerinde sıfır olmayan bir Windows Soketi hata kodu verir. Başarılı olursa, hesaplanan adres kullanılarak `CSocketAddr::GetAddrInfoList` başvurulan bağlı bir listede `CSocketAddr::GetAddrInfo`depolanır ve .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, dönüştürme gerçekleştirmek için Win32 API işlevi [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) çağırır.

## <a name="csocketaddrfindinet6addr"></a><a name="findinet6addr"></a>CSocketAddr::FindINET6Addr

IPv6 ana bilgisayar adını ana bilgisayar adresine dönüştürmek için bu yöntemi arayın.

```
int FindINET6Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>Parametreler

*szHost*<br/>
Ana bilgisayar adı veya noktalı IP adresi.

*nPortNo*<br/>
Bağlantı noktası numarası.

*bayraklar*<br/>
0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST kombinasyonu.

*sock_type*<br/>
Soket türü (SOCK_STREAM gibi).

### <a name="return-value"></a>Dönüş Değeri

Adres başarıyla hesaplanırsa sıfır döndürür. Hata üzerinde sıfır olmayan bir Windows Soketi hata kodu verir. Başarılı olursa, hesaplanan adres kullanılarak `CSocketAddr::GetAddrInfoList` başvurulan bağlı bir listede `CSocketAddr::GetAddrInfo`depolanır ve .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, dönüştürme gerçekleştirmek için Win32 API işlevi [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) çağırır.

## <a name="csocketaddrgetaddrinfo"></a><a name="getaddrinfo"></a>CSocketAddr::GetAddrInfo

Bir işaretçiyi listedeki belirli bir `addrinfo` öğeye döndürmek için bu yöntemi çağırın.

```
addrinfo* const GetAddrInfo(int nIndex = 0) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[Addrinfo](/windows/win32/api/ws2def/ns-ws2def-addrinfow) listesindeki belirli bir öğeye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Ana bilgisayar hakkında `addrinfo` yanıt bilgilerini içeren bağlantılı listede *nIndex* tarafından başvurulan yapıya bir işaretçi döndürür.

## <a name="csocketaddrgetaddrinfolist"></a><a name="getaddrinfolist"></a>CSocketAddr::GetAddrInfoList

Bir işaretçiyi listeye döndürmek `addrinfo` için bu yöntemi çağırın.

```
addrinfo* const GetAddrInfoList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ana bilgisayar hakkında yanıt bilgilerini `addrinfo` içeren bir veya daha fazla yapının bağlantılı bir listesini işaretçi. Daha fazla bilgi için [addrinfo yapısına](/windows/win32/api/ws2def/ns-ws2def-addrinfow)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
