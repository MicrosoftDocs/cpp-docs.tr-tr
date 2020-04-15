---
title: CInternetConnection Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
ms.openlocfilehash: 6649986f279e010a833b31157922cb4fd1ea8613
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372418"
---
# <a name="cinternetconnection-class"></a>CInternetConnection Sınıfı

Bir Internet sunucusuyla bağlantınızı yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CInternetConnection : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Bir `CInternetConnection` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CInternetConnection::GetContext](#getcontext)|Bu bağlantı nesnesinin bağlam kimliğini alır.|
|[CInternetConnection::GetServerName](#getservername)|Bağlantıyla ilişkili sunucunun adını alır.|
|[CInternetConnection::GetSession](#getsession)|Bağlantıyla ilişkili [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesine bir işaretçi alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CInternetConnection::operatör HINTERNET](#operator_hinternet)|Internet oturumuiçin bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

Bu MFC sınıfları [CFtpConnection,](../../mfc/reference/cftpconnection-class.md) [CHttpConnection](../../mfc/reference/chttpconnection-class.md)ve [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)için taban sınıftır. Bu sınıfların her biri, ilgili FTP, HTTP veya gopher sunucusuyla iletişim kurmak için ek işlevler sağlar.

Bir Internet sunucusuyla doğrudan iletişim kurmak için bir [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesneniz ve nesneniz `CInternetConnection` olmalıdır.

WinInet sınıfları nasıl çalıştığı hakkında daha fazla bilgi edinmek için [WinInet ile internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="cinternetconnectioncinternetconnection"></a><a name="cinternetconnection"></a>CInternetConnection::CInternetConnection

Bir `CInternetConnection` nesne oluşturulduğunda bu üye işlev çağrılır.

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pOturum*<br/>
[CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesine işaretçi.

*pstrServer*<br/>
Sunucu adını içeren bir dize için bir işaretçi.

*nPort*<br/>
Bu bağlantı için Internet bağlantı noktasını tanımlayan numara.

*dwBağlam*<br/>
Nesneiçin bağlam tanımlayıcısı. `CInternetConnection` *dwContext*hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

### <a name="remarks"></a>Açıklamalar

Kendine asla `CInternetConnection` böyle hitap mıyorsun; bunun yerine, kurmak istediğiniz bağlantı türü için [CInternetSession](../../mfc/reference/cinternetsession-class.md) üye işlevini arayın:

- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [CinternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

*dwContext* için varsayılan değer MFC tarafından `CInternetConnection` **InternetConnection**türetilmiş nesneoluşturulan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden türetilen nesneye gönderilir. Varsayılan değer 1 olarak ayarlanır; ancak, bağlantı için [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) oluşturucusunda açıkça belirli bir bağlam tanımlayıcısı atayabilirsiniz. Nesne ve yaptığı herhangi bir çalışma bu bağlam kimliği ile ilişkilendirilecektir. Bağlam tanımlayıcısı [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan nesne üzerinde durum sağlamak için. Makaleye bakın [Internet İlk Adımlar: WinInet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi için.

## <a name="cinternetconnectiongetcontext"></a><a name="getcontext"></a>CInternetConnection::GetContext

Bu oturum için bağlam kimliğini almak için bu üye işlevini arayın.

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamaya atanan bağlam kimliği.

### <a name="remarks"></a>Açıklamalar

Bağlam kimliği başlangıçta [CInternetSession'da](../../mfc/reference/cinternetsession-class.md) belirtilir ve `CInternetConnection`bağlantıyı açan bir işleve çağrıda farklı belirtilmedikçe [CInternetFile](../../mfc/reference/cinternetfile-class.md)türetilmiş sınıflara yayılır. Bağlam kimliği, verilen nesnenin herhangi bir işlemiyle ilişkilidir ve CInternetSession tarafından döndürülen işlemin durum bilgilerini [tanımlar::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

Kullanıcı durumu bilgilerini `GetContext` vermek için diğer WinInet sınıflarıyla nasıl çalıştığı hakkında daha fazla bilgi için internet ilk adımlar makalesine bakın: Bağlam tanımlayıcısı hakkında daha fazla bilgi için [WinInet.](../../mfc/wininet-basics.md)

## <a name="cinternetconnectiongetservername"></a><a name="getservername"></a>CInternetConnection::GetServerName

Bu Internet bağlantısıyla ilişkili sunucunun adını almak için bu üye işlevini arayın.

```
CString GetServerName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu bağlantı nesnesinin çalıştığı sunucunun adı.

## <a name="cinternetconnectiongetsession"></a><a name="getsession"></a>CInternetConnection::GetSession

Bu bağlantıyla ilişkili `CInternetSession` nesneye işaretçi almak için bu üye işlevi arayın.

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu Internet bağlantısı nesnesi ile ilişkili bir [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi için bir işaretçi.

## <a name="cinternetconnectionoperator-hinternet"></a><a name="operator_hinternet"></a>CInternetConnection::operatör HINTERNET

Geçerli Internet oturumu için API düzeyi tutamacını almak için bu işleci kullanın.

```
operator HINTERNET() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
