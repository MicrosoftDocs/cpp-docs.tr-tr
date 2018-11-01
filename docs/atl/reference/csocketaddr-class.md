---
title: CSocketAddr sınıfı
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
ms.openlocfilehash: 9ab0367d5a83096c1bb6e9166ee2b43fe2000ab4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570462"
---
# <a name="csocketaddr-class"></a>CSocketAddr sınıfı

Bu sınıf ana bilgisayar adları hem IPv4 hem de IPv6 biçimlerini destekleyen konak adreslere dönüştürme yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSocketAddr
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSocketAddr::CSocketAddr](#csocketaddr)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSocketAddr::FindAddr](#findaddr)|Belirtilen konak adı için ana bilgisayar adresi dönüştürmek için bu yöntemi çağırın.|
|[CSocketAddr::FindINET4Addr](#findinet4addr)|IPv4 ana bilgisayar adı konak adresine dönüştürmek için bu yöntemi çağırın.|
|[CSocketAddr::FindINET6Addr](#findinet6addr)|IPv6 ana bilgisayar adı konak adresine dönüştürmek için bu yöntemi çağırın.|
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|Belirli bir öğeye bir işaretçiyi döndürmek için bu yöntemi çağıran `addrinfo` listesi.|
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|Bir işaretçi döndürmek için bu yöntemi çağırın `addrinfo` listesi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf Windows ile kullanmak için ağ adresleri bakmak için belirsiz yaklaşım API işlevleri ve kitaplıklarında yuva sarmalayıcılar yuva IP sürümü sağlar.

Ağ adreslerini aramak için kullanılan bu sınıfın üyeleri Win32 API işlevi kullanmanız [getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo). İşlev ANSI veya UNICODE sürümü, kodunuzu ANSI veya UNICODE olarak derlenmiş bağlı olarak adlandırılır.

Bu sınıf, her iki IPv4 andIPv6 ağ adreslerini destekler.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsocket.h

##  <a name="csocketaddr"></a>  CSocketAddr::CSocketAddr

Oluşturucu.

```
CSocketAddr();
```

### <a name="remarks"></a>Açıklamalar

Yeni bir oluşturur `CSocketAddr` nesne ve konak yanıt bilgilerini içeren bağlantılı liste başlatır.

##  <a name="findaddr"></a>  CSocketAddr::FindAddr

Belirtilen konak adı için ana bilgisayar adresi dönüştürmek için bu yöntemi çağırın.

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
Konak adı veya IP adresi noktalı.

*szPortOrServiceName*<br/>
Bağlantı noktası numarası veya ana bilgisayar hizmetinin adı.

*nPortNo*<br/>
Bağlantı noktası numarası.

*bayrakları*<br/>
0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST birleşimi.

*addr_family*<br/>
Adres ailesi (örneğin, PF_INET).

*sock_type*<br/>
Yuva türü (örneğin, SOCK_STREAM).

*ai_proto*<br/>
Protokol (örneğin, IPPROTO_IP veya IPPROTO_IPV6).

### <a name="return-value"></a>Dönüş Değeri

Adres başarıyla hesaplanıp hesaplanmayacağını sıfır döndürür. Sıfır olmayan bir Windows yuva hata kodu hatası döndürür. Başarılı, hesaplanan adres kullanılarak başvurulabilir bağlantılı listesinde depolanıyorsa `CSocketAddr::GetAddrInfoList` ve `CSocketAddr::GetAddrInfo`.

### <a name="remarks"></a>Açıklamalar

Konak adı parametresi IPv4 veya IPv6 biçiminde olabilir. Bu yöntem Win32 API işlevini çağırır [getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) dönüştürme gerçekleştirmek için.

##  <a name="findinet4addr"></a>  CSocketAddr::FindINET4Addr

IPv4 ana bilgisayar adı konak adresine dönüştürmek için bu yöntemi çağırın.

```
int FindINET4Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>Parametreler

*szHost*<br/>
Konak adı veya IP adresi noktalı.

*nPortNo*<br/>
Bağlantı noktası numarası.

*bayrakları*<br/>
0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST birleşimi.

*sock_type*<br/>
Yuva türü (örneğin, SOCK_STREAM).

### <a name="return-value"></a>Dönüş Değeri

Adres başarıyla hesaplanıp hesaplanmayacağını sıfır döndürür. Sıfır olmayan bir Windows yuva hata kodu hatası döndürür. Başarılı, hesaplanan adres kullanılarak başvurulabilir bağlantılı listesinde depolanıyorsa `CSocketAddr::GetAddrInfoList` ve `CSocketAddr::GetAddrInfo`.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Win32 API işlevini çağırır [getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) dönüştürme gerçekleştirmek için.

##  <a name="findinet6addr"></a>  CSocketAddr::FindINET6Addr

IPv6 ana bilgisayar adı konak adresine dönüştürmek için bu yöntemi çağırın.

```
int FindINET6Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>Parametreler

*szHost*<br/>
Konak adı veya IP adresi noktalı.

*nPortNo*<br/>
Bağlantı noktası numarası.

*bayrakları*<br/>
0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST birleşimi.

*sock_type*<br/>
Yuva türü (örneğin, SOCK_STREAM).

### <a name="return-value"></a>Dönüş Değeri

Adres başarıyla hesaplanıp hesaplanmayacağını sıfır döndürür. Sıfır olmayan bir Windows yuva hata kodu hatası döndürür. Başarılı, hesaplanan adres kullanılarak başvurulabilir bağlantılı listesinde depolanıyorsa `CSocketAddr::GetAddrInfoList` ve `CSocketAddr::GetAddrInfo`.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Win32 API işlevini çağırır [getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) dönüştürme gerçekleştirmek için.

##  <a name="getaddrinfo"></a>  CSocketAddr::GetAddrInfo

Belirli bir öğeye bir işaretçiyi döndürmek için bu yöntemi çağıran `addrinfo` listesi.

```
addrinfo* const GetAddrInfo(int nIndex = 0) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Belirli bir öğeye bir başvuru [addrinfo](https://msdn.microsoft.com/library/windows/desktop/ms737530) listesi.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndürür `addrinfo` yapısı tarafından başvurulan *nIndex* konak yanıt bilgilerini içeren bağlantılı listesinde.

##  <a name="getaddrinfolist"></a>  CSocketAddr::GetAddrInfoList

Bir işaretçi döndürmek için bu yöntemi çağırın `addrinfo` listesi.

```
addrinfo* const GetAddrInfoList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir veya daha fazla bağlantılı bir liste işaretçisi `addrinfo` konak yanıt bilgilerini içeren yapılar. Daha fazla bilgi için [addrinfo yapısı](https://msdn.microsoft.com/library/windows/desktop/ms737530).

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
