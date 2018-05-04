---
title: CSocketAddr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
dev_langs:
- C++
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 830b1087d0a4792b449c516ed12ad7e8a84b2a51
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
|[CSocketAddr::FindAddr](#findaddr)|Sağlanan ana makine adı ana bilgisayar adresine dönüştürmek için bu yöntemi çağırın.|  
|[CSocketAddr::FindINET4Addr](#findinet4addr)|IPv4 ana bilgisayar adı ana bilgisayar adresine dönüştürmek için bu yöntemi çağırın.|  
|[CSocketAddr::FindINET6Addr](#findinet6addr)|IPv6 ana bilgisayar adı ana bilgisayar adresine dönüştürmek için bu yöntemi çağırın.|  
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|Belirli bir öğe için bir işaretçi döndürmek için bu yöntemi çağırabilmeniz **addrinfo** listesi.|  
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|Bir işaretçi döndürmek için bu yöntemi çağırın **addrinfo** listesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, Windows ile kullanmak için ağ adresleri bakmak için belirsiz yaklaşımı API işlevleri ve yuva sarmalayıcıları kitaplıklarında yuva IP sürümü sağlar.  
  
 Ağ adreslerini aramak için kullanılan bu sınıfın üyeleri Win32 API işlevini [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520).  
  
 Bu sınıf, her iki IPv4 andIPv6 ağ adreslerini destekler.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsocket.h  
  
##  <a name="csocketaddr"></a>  CSocketAddr::CSocketAddr  
 Oluşturucu.  
  
```
CSocketAddr();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir `CSocketAddr` nesne ve konak yanıt bilgilerini içeren bağlantılı listesini başlatır.  
  
##  <a name="findaddr"></a>  CSocketAddr::FindAddr  
 Sağlanan ana makine adı ana bilgisayar adresine dönüştürmek için bu yöntemi çağırın.  
  
```
int FindAddr(
    const char *szHost,
    const char *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const char *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```  
  
### <a name="parameters"></a>Parametreler  
 `szHost`  
 Ana bilgisayar adı veya noktalı IP adresi.  
  
 *szPortOrServiceName*  
 Bağlantı noktası numarası veya ana bilgisayardaki hizmetin adı.  
  
 `nPortNo`  
 Bağlantı noktası numarası.  
  
 `flags`  
 0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST birleşimi.  
  
 *addr_family*  
 Adres ailesi (örneğin, PF_INET).  
  
 `sock_type`  
 Yuva türü (örneğin, SOCK_STREAM).  
  
 *ai_proto*  
 Protokol (örneğin, IPPROTO_IP veya IPPROTO_IPV6).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Adres başarılı bir şekilde hesaplanıp hesaplanmayacağını sıfır döndürür. Sıfır olmayan bir Windows yuva hata kodu hatası döndürür. Başarılı, hesaplanan adresi kullanarak başvurulabilir bağlantılı bir listede depolanıyorsa `CSocketAddr::GetAddrInfoList` ve `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Açıklamalar  
 Ana bilgisayar adı parametresi IPv4 veya IPv6 biçiminde olabilir. Bu yöntem Win32 API işlev çağrılarını [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) dönüştürme gerçekleştirmek için.  
  
##  <a name="findinet4addr"></a>  CSocketAddr::FindINET4Addr  
 IPv4 ana bilgisayar adı ana bilgisayar adresine dönüştürmek için bu yöntemi çağırın.  
  
```
int FindINET4Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>Parametreler  
 `szHost`  
 Ana bilgisayar adı veya noktalı IP adresi.  
  
 `nPortNo`  
 Bağlantı noktası numarası.  
  
 `flags`  
 0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST birleşimi.  
  
 `sock_type`  
 Yuva türü (örneğin, SOCK_STREAM).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Adres başarılı bir şekilde hesaplanıp hesaplanmayacağını sıfır döndürür. Sıfır olmayan bir Windows yuva hata kodu hatası döndürür. Başarılı, hesaplanan adresi kullanarak başvurulabilir bağlantılı bir listede depolanıyorsa `CSocketAddr::GetAddrInfoList` ve `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Win32 API işlev çağrılarını [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) dönüştürme gerçekleştirmek için.  
  
##  <a name="findinet6addr"></a>  CSocketAddr::FindINET6Addr  
 IPv6 ana bilgisayar adı ana bilgisayar adresine dönüştürmek için bu yöntemi çağırın.  
  
```
int FindINET6Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>Parametreler  
 `szHost`  
 Ana bilgisayar adı veya noktalı IP adresi.  
  
 `nPortNo`  
 Bağlantı noktası numarası.  
  
 `flags`  
 0 veya AI_PASSIVE, AI_CANONNAME veya AI_NUMERICHOST birleşimi.  
  
 `sock_type`  
 Yuva türü (örneğin, SOCK_STREAM).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Adres başarılı bir şekilde hesaplanıp hesaplanmayacağını sıfır döndürür. Sıfır olmayan bir Windows yuva hata kodu hatası döndürür. Başarılı, hesaplanan adresi kullanarak başvurulabilir bağlantılı bir listede depolanıyorsa `CSocketAddr::GetAddrInfoList` ve `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Win32 API işlev çağrılarını [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) dönüştürme gerçekleştirmek için.  
  
##  <a name="getaddrinfo"></a>  CSocketAddr::GetAddrInfo  
 Belirli bir öğe için bir işaretçi döndürmek için bu yöntemi çağırabilmeniz **addrinfo** listesi.  
  
```
addrinfo* const GetAddrInfoint nIndex = 0) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Belirli bir öğeye başvuru [addrinfo](http://msdn.microsoft.com/library/windows/desktop/ms737530) listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür **addrinfo** başvurduğu yapısı `nIndex` konak yanıt bilgilerini içeren bağlantılı listesinde.  
  
##  <a name="getaddrinfolist"></a>  CSocketAddr::GetAddrInfoList  
 Bir işaretçi döndürmek için bu yöntemi çağırın **addrinfo** listesi.  
  
```
addrinfo* const GetAddrInfoList() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir veya daha fazla bağlantılı listesini işaretçi `addrinfo` konak yanıt bilgilerini içeren yapıları. Daha fazla bilgi için bkz: [addrinfo yapısı](https://msdn.microsoft.com/library/windows/desktop/ms737530).
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
