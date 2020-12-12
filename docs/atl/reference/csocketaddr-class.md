---
description: 'Daha fazla bilgi edinin: Csocketadresi sınıfı'
title: Csocketadresi sınıfı
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
ms.openlocfilehash: eff93b6a8e6d0ea487e3571cd52973d9e17115d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140536"
---
# <a name="csocketaddr-class"></a>Csocketadresi sınıfı

Bu sınıf, hem IPv4 hem de ıPV6 biçimlerini destekleyen konak adlarını konak adreslerine dönüştürmek için yöntemler sağlar.

## <a name="syntax"></a>Syntax

```
class CSocketAddr
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Csocketadresi:: Csocketadresi](#csocketaddr)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Csocketadresi:: Findadddr](#findaddr)|Belirtilen ana bilgisayar adını konak adresine dönüştürmek için bu yöntemi çağırın.|
|[Csocketadresi:: FindINET4Addr](#findinet4addr)|IPv4 ana bilgisayar adını konak adresine dönüştürmek için bu yöntemi çağırın.|
|[Csocketadresi:: FindINET6Addr](#findinet6addr)|IPv6 ana bilgisayar adını konak adresine dönüştürmek için bu yöntemi çağırın.|
|[Csocketadresi:: GetAddrInfo](#getaddrinfo)|Listedeki belirli bir öğeye bir işaretçi döndürmek için bu yöntemi çağırın `addrinfo` .|
|[Csocketadresi:: GetAddrInfoList](#getaddrinfolist)|Listeye bir işaretçi döndürmek için bu yöntemi çağırın `addrinfo` .|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, kitaplıklarda Windows Sockets API işlevleri ve yuva sarmalayıcıları ile kullanmak üzere ağ adresleri aramak için bir IP sürümü belirsiz yaklaşımı sağlar.

Ağ adreslerini aramak için kullanılan bu sınıfın üyeleri, [GetAddrInfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)Win32 API işlevini kullanır. İşlevin ANSI veya UNICODE sürümü, kodunuzun ANSI veya UNICODE için derlendiğine bağlı olarak çağrılır.

Bu sınıf hem IPv4 andIPv6 ağ adreslerini destekler.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atlsocket. h

## <a name="csocketaddrcsocketaddr"></a><a name="csocketaddr"></a> Csocketadresi:: Csocketadresi

Oluşturucu.

```
CSocketAddr();
```

### <a name="remarks"></a>Açıklamalar

Yeni bir `CSocketAddr` nesne oluşturur ve ana bilgisayarla ilgili yanıt bilgilerini içeren bağlantılı listeyi başlatır.

## <a name="csocketaddrfindaddr"></a><a name="findaddr"></a> Csocketadresi:: Findadddr

Belirtilen ana bilgisayar adını konak adresine dönüştürmek için bu yöntemi çağırın.

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
Konaktaki hizmetin bağlantı noktası numarası veya adı.

*nPortNo*<br/>
Bağlantı noktası numarası.

*bayraklar*<br/>
0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST birleşimi.

*addr_family*<br/>
Adres ailesi (örneğin, PF_INET).

*sock_type*<br/>
Yuva türü (örneğin SOCK_STREAM).

*ai_proto*<br/>
Protokol (IPPROTO_IP veya IPPROTO_IPV6 gibi).

### <a name="return-value"></a>Dönüş Değeri

Adres başarıyla hesaplanıyorsa, sıfır döndürür. Hata durumunda sıfır olmayan bir Windows yuva hata kodu döndürür. Başarılı olursa, hesaplanan adres, ve kullanılarak başvurulabilen bağlantılı bir listede depolanır `CSocketAddr::GetAddrInfoList` `CSocketAddr::GetAddrInfo` .

### <a name="remarks"></a>Açıklamalar

Ana bilgisayar adı parametresi ya IPv4 ya da IPv6 biçiminde olabilir. Bu yöntem, dönüştürmeyi gerçekleştirmek için [GetAddrInfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) Win32 API işlevini çağırır.

## <a name="csocketaddrfindinet4addr"></a><a name="findinet4addr"></a> Csocketadresi:: FindINET4Addr

IPv4 ana bilgisayar adını konak adresine dönüştürmek için bu yöntemi çağırın.

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
0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST birleşimi.

*sock_type*<br/>
Yuva türü (örneğin SOCK_STREAM).

### <a name="return-value"></a>Dönüş Değeri

Adres başarıyla hesaplanıyorsa, sıfır döndürür. Hata durumunda sıfır olmayan bir Windows yuva hata kodu döndürür. Başarılı olursa, hesaplanan adres, ve kullanılarak başvurulabilen bağlantılı bir listede depolanır `CSocketAddr::GetAddrInfoList` `CSocketAddr::GetAddrInfo` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, dönüştürmeyi gerçekleştirmek için [GetAddrInfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) Win32 API işlevini çağırır.

## <a name="csocketaddrfindinet6addr"></a><a name="findinet6addr"></a> Csocketadresi:: FindINET6Addr

IPv6 ana bilgisayar adını konak adresine dönüştürmek için bu yöntemi çağırın.

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
0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST birleşimi.

*sock_type*<br/>
Yuva türü (örneğin SOCK_STREAM).

### <a name="return-value"></a>Dönüş Değeri

Adres başarıyla hesaplanıyorsa, sıfır döndürür. Hata durumunda sıfır olmayan bir Windows yuva hata kodu döndürür. Başarılı olursa, hesaplanan adres, ve kullanılarak başvurulabilen bağlantılı bir listede depolanır `CSocketAddr::GetAddrInfoList` `CSocketAddr::GetAddrInfo` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, dönüştürmeyi gerçekleştirmek için [GetAddrInfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) Win32 API işlevini çağırır.

## <a name="csocketaddrgetaddrinfo"></a><a name="getaddrinfo"></a> Csocketadresi:: GetAddrInfo

Listedeki belirli bir öğeye bir işaretçi döndürmek için bu yöntemi çağırın `addrinfo` .

```
addrinfo* const GetAddrInfo(int nIndex = 0) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
[Addrinfo](/windows/win32/api/ws2def/ns-ws2def-addrinfow) listesindeki belirli bir öğeye başvuru.

### <a name="return-value"></a>Dönüş Değeri

`addrinfo`Ana bilgisayar hakkındaki yanıt bilgilerini içeren bağlantılı listede *nIndex* tarafından başvurulan yapıya bir işaretçi döndürür.

## <a name="csocketaddrgetaddrinfolist"></a><a name="getaddrinfolist"></a> Csocketadresi:: GetAddrInfoList

Listeye bir işaretçi döndürmek için bu yöntemi çağırın `addrinfo` .

```
addrinfo* const GetAddrInfoList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Konakla ilgili yanıt bilgilerini içeren bir veya daha fazla yapının bağlı listesine yönelik işaretçi `addrinfo` . Daha fazla bilgi için bkz. [addrinfo yapısı](/windows/win32/api/ws2def/ns-ws2def-addrinfow).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
