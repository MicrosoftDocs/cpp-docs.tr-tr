---
title: Cınternetconnection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
dev_langs:
- C++
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f30cfd4a27eb07d2e420b83730f653fb957bb4bd
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083301"
---
# <a name="cinternetconnection-class"></a>Cınternetconnection sınıfı

Internet sunucusuyla olan bağlantınızı yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CInternetConnection : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Oluşturur bir `CInternetConnection` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetConnection::GetContext](#getcontext)|Bu bağlantı nesnesi için bağlam Kimliğini alır.|
|[CInternetConnection::GetServerName](#getservername)|Bağlantı ile ilişkili sunucu adını alır.|
|[CInternetConnection::GetSession](#getsession)|Bir işaretçi alır [Cınternetsession](../../mfc/reference/cinternetsession-class.md) bağlantı ile ilişkili nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|Bir Internet oturumu için bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

MFC sınıfları için temel sınıfı olan [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md), ve [CGopherConnection](../../mfc/reference/cgopherconnection-class.md). Bu sınıfların her birini ilgili FTP, HTTP veya gopher sunucusuyla iletişim kurmak için ek işlevsellik sağlar.

Doğrudan bir Internet sunucusuyla iletişim kurmak için olmalıdır bir [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesnesi ve bir `CInternetConnection` nesne.

Nasıl iş WinINet sınıfları hakkında daha fazla bilgi için bkz [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="cinternetconnection"></a>  CInternetConnection::CInternetConnection

Bu üye işlevi aldığında çağrılan bir `CInternetConnection` nesnesi oluşturulur.

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pSession*<br/>
Bir işaretçi bir [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne.

*pstrServer*<br/>
Sunucu adını içeren bir dize işaretçisi.

*nbağlantı noktası*<br/>
Bu bağlantı için Internet bağlantı noktasını tanımlayan numara.

*dwContext*<br/>
İçerik tanımlayıcısı `CInternetConnection` nesne. Bkz: **açıklamalar** hakkında daha fazla bilgi için *dwContext*.

### <a name="remarks"></a>Açıklamalar

Hiçbir çağrı `CInternetConnection` kendiniz; bunun yerine çağrı [Cınternetsession](../../mfc/reference/cinternetsession-class.md) üye işlevi'kurmak istediğiniz bağlantı türü için:

- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

İçin varsayılan değer *dwContext* MFC'ye tarafından gönderilen `CInternetConnection`-nesneden türetilen [Cınternetsession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne **InternetConnection**- türetilen bir nesne. Varsayılan değer 1 olarak ayarlanır; Ancak, açıkça belirli bağlam tanımlayıcıda atayabilirsiniz [Cınternetsession](../../mfc/reference/cinternetsession-class.md#cinternetsession) bağlantı için oluşturucu. Nesne ve mevcut herhangi bir iş, bir bağlam kimliği ile ilişkilendirilecek İçerik tanımlayıcısı döndürülür [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) durumu ile belirtilen nesneye sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

##  <a name="getcontext"></a>  CInternetConnection::GetContext

Bu oturum için bağlam Kimliğini almak için bu üye işlevini çağırın.

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Dönüş Değeri

Atanan uygulama bir bağlam kimliği.

### <a name="remarks"></a>Açıklamalar

ID kontextu başlangıçta belirtilen [Cınternetsession](../../mfc/reference/cinternetsession-class.md) ve için yayar `CInternetConnection`- ve [Cınternetfile](../../mfc/reference/cinternetfile-class.md)-türetilmiş sınıflar, farklı şekilde açan bir işlev çağrısında belirtilmediği sürece bağlantı. Bağlam Kimliğini verilen nesnenin herhangi bir işlem ile ilişkili olan ve tarafından döndürülen işlem durumu bilgilerini tanımlayan [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

Hakkında daha fazla bilgi için `GetContext` diğer WinINet sınıfları, kullanıcı durum bilgilerini sağlamak için birlikte çalışır, başlıklı makaleye bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

##  <a name="getservername"></a>  CInternetConnection::GetServerName

Bu Internet bağlantısı ile ilişkilendirilen sunucu adını almak için bu üye işlevini çağırın.

```
CString GetServerName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sunucu adını, bu bağlantı nesnesi ile çalışmaktadır.

##  <a name="getsession"></a>  CInternetConnection::GetSession

Bu üye işlevi işaretçisi almak için arama `CInternetSession` bu bağlantıyla ilişkili nesne.

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [Cınternetsession](../../mfc/reference/cinternetsession-class.md) bu Internet bağlantı nesnesiyle ilişkili nesne.

##  <a name="operator_hinternet"></a>  CInternetConnection::operator HINTERNET

Geçerli Internet oturumu için API düzey tanıtıcısını almak için bu işleci kullanın.

```
operator HINTERNET() const;
```

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

