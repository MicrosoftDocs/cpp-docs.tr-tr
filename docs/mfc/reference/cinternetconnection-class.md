---
description: 'Daha fazla bilgi edinin: CInternetConnection sınıfı'
title: CInternetConnection sınıfı
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
ms.openlocfilehash: 2ae869e8cbf3bbfb3ce19e78088a465ae1d6aa65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143552"
---
# <a name="cinternetconnection-class"></a>CInternetConnection sınıfı

Internet sunucusuyla olan bağlantınızı yönetir.

## <a name="syntax"></a>Syntax

```
class CInternetConnection : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInternetConnection:: CInternetConnection](#cinternetconnection)|Bir `CInternetConnection` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetConnection:: GetContext](#getcontext)|Bu bağlantı nesnesi için bağlam KIMLIĞINI alır.|
|[CInternetConnection:: GetServerName](#getservername)|Bağlantıyla ilişkili sunucunun adını alır.|
|[CInternetConnection:: GetSession](#getsession)|Bağlantıyla ilişkili [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesine yönelik bir işaretçi alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetConnection:: operator HıNTERNET](#operator_hinternet)|Bir Internet oturumu için tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

[CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md)ve [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)MFC sınıfları için temel sınıftır. Bu sınıfların her biri, ilgili FTP, HTTP veya Gopher sunucusuyla iletişim kurmak için ek işlevler sağlar.

Doğrudan bir Internet sunucusuyla iletişim kurmak için bir [Cınternetoturum](../../mfc/reference/cinternetsession-class.md) nesneniz ve bir `CInternetConnection` nesneniz olmalıdır.

WinInet sınıflarının nasıl çalıştığı hakkında daha fazla bilgi edinmek için bkz. [Wininet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="cinternetconnectioncinternetconnection"></a><a name="cinternetconnection"></a> CInternetConnection:: CInternetConnection

Bu üye işlevi, bir `CInternetConnection` nesne oluşturulduğunda çağrılır.

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pSession*<br/>
[CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesine yönelik bir işaretçi.

*pstrServer*<br/>
Sunucu adını içeren bir dize işaretçisi.

*nPort*<br/>
Bu bağlantı için Internet bağlantı noktasını tanımlayan sayı.

*dwContext*<br/>
Nesnenin bağlam tanımlayıcısı `CInternetConnection` . *DwContext* hakkında daha fazla bilgi için bkz. **açıklamalar** .

### <a name="remarks"></a>Açıklamalar

Kendi kendinize hiçbir zaman çağırmayın `CInternetConnection` ; bunun yerine, oluşturmak istediğiniz bağlantı türü Için [CInternetSession](../../mfc/reference/cinternetsession-class.md) üye işlevini çağırın:

- [CInternetSession:: GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

*DwContext* için varsayılan değer, MFC tarafından, `CInternetConnection` **InternetConnection** tarafından türetilen nesneyi oluşturan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden türetilmiş nesneye gönderilir. Varsayılan değer 1 ' e ayarlanır; Bununla birlikte, bağlantının [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) oluşturucusunda belirli bir bağlam tanımlayıcısını açıkça atayabilirsiniz. Nesne ve onun yaptığı herhangi bir iş, bu bağlam KIMLIĞIYLE ilişkilendirilecektir. Bağlam tanımlayıcısı, tanımlanan nesne üzerinde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) öğesine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

## <a name="cinternetconnectiongetcontext"></a><a name="getcontext"></a> CInternetConnection:: GetContext

Bu oturum için bağlam KIMLIĞINI almak üzere bu üye işlevi çağırın.

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama tarafından atanan bağlam KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bağlam KIMLIĞI, başlangıçta [CInternetSession](../../mfc/reference/cinternetsession-class.md) 'da belirtilir ve `CInternetConnection` bağlantıyı açan bir işlev çağrısında farklı belirtilmediği takdirde, ve [cınternetdosya](../../mfc/reference/cinternetfile-class.md)tarafından türetilmiş sınıfları yayar. Bağlam KIMLIĞI verilen nesnenin herhangi bir işlemiyle ilişkilendirilir ve [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)tarafından döndürülen işlemin durum bilgilerini tanımlar.

`GetContext`Kullanıcı durumu bilgilerine izin vermek için diğer WinINet sınıflarıyla nasıl çalıştığı hakkında daha fazla bilgi için, bağlam tanımlayıcısı hakkında daha fazla bilgi Için [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

## <a name="cinternetconnectiongetservername"></a><a name="getservername"></a> CInternetConnection:: GetServerName

Bu Internet bağlantısıyla ilişkili sunucunun adını almak için bu üye işlevi çağırın.

```
CString GetServerName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu bağlantı nesnesinin üzerinde çalıştığı sunucunun adı.

## <a name="cinternetconnectiongetsession"></a><a name="getsession"></a> CInternetConnection:: GetSession

Bu bağlantıyla ilişkili nesneye bir işaretçi almak için bu üye işlevi çağırın `CInternetSession` .

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu Internet bağlantısı nesnesiyle ilişkili bir [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi işaretçisi.

## <a name="cinternetconnectionoperator-hinternet"></a><a name="operator_hinternet"></a> CInternetConnection:: operator HıNTERNET

Geçerli Internet oturumunun API düzeyi tanıtıcısını almak için bu işleci kullanın.

```
operator HINTERNET() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
