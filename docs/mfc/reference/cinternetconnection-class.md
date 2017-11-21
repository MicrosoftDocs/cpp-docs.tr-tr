---
title: "CInternetConnection sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
dev_langs: C++
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8bac6982ed037ff3338ea64ecdf8fddaa15fe124
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cinternetconnection-class"></a>CInternetConnection sınıfı
Internet sunucusu bağlantınız yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CInternetConnection : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Oluşturan bir `CInternetConnection` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInternetConnection::GetContext](#getcontext)|Context ID için bu bağlantı nesnesi alır.|  
|[CInternetConnection::GetServerName](#getservername)|Bağlantı ile ilişkili sunucu adını alır.|  
|[CInternetConnection::GetSession](#getsession)|Bir işaretçi alır [CInternetSession](../../mfc/reference/cinternetsession-class.md) bağlantı ile ilişkili nesne.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|Bir Internet oturumu için bir tanıtıcı.|  
  
## <a name="remarks"></a>Açıklamalar  
 MFC sınıfları için temel sınıfı olan [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md), ve [CGopherConnection](../../mfc/reference/cgopherconnection-class.md). Bu sınıfların her biri kendi FTP, HTTP veya gopher sunucu ile iletişim kurmak için ek işlevsellik sağlar.  
  
 Doğrudan bir Internet sunucusu ile iletişim kurmak için bilmeniz gereken bir [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesne ve `CInternetConnection` nesne.  
  
 İş nasıl WinINet sınıfları hakkında daha fazla bilgi için makalesine bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="cinternetconnection"></a>CInternetConnection::CInternetConnection  
 Bu üye işlevi aldığında çağrılan bir `CInternetConnection` nesnesi oluşturulur.  
  
```  
CInternetConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSession`  
 Bir işaretçi bir [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi.  
  
 `pstrServer`  
 Sunucu adını içeren bir dize için bir işaretçi.  
  
 `nPort`  
 Bu bağlantı için Internet bağlantı noktasını tanımlar sayı.  
  
 `dwContext`  
 İçerik tanımlayıcısını `CInternetConnection` nesnesi. Bkz: **açıklamalar** hakkında daha fazla bilgi için `dwContext`.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman çağrısı `CInternetConnection` kendiniz; bunun yerine, çağrı [CInternetSession](../../mfc/reference/cinternetsession-class.md) üye işlevi oluşturmak istediğiniz bağlantı türü için:  
  
- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)  
  
- [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)  
  
- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)  
  
 İçin varsayılan değer `dwContext` MFC'ye tarafından gönderilen `CInternetConnection`-nesnesinden türetilmiş [CInternetSession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne **InternetConnection**-türetilmiş bir nesne içermelidir. Varsayılan değer 1 olarak ayarlanır; Ancak, açıkça özel bağlamı tanımlayıcıda atayabilirsiniz [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) bağlantısı Oluşturucu. Nesne ve mevcut herhangi bir iş, içerik kimliği ile ilişkilendirilecek Bağlam tanıtıcısı döndürülen [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen bir nesne üzerinde durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
##  <a name="getcontext"></a>CInternetConnection::GetContext  
 Bu oturum için bağlam Kimliğini almak için bu üye işlevini çağırın.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçerik atanan uygulama kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 İçerik kimliği başlangıçta belirtilen [CInternetSession](../../mfc/reference/cinternetsession-class.md) ve için yayar `CInternetConnection`- ve [CInternetFile](../../mfc/reference/cinternetfile-class.md)-farklı açılır bir işlev çağrısında belirtilen sürece türetilmiş sınıfları, bağlantı. İçerik kimliği verilen nesnenin herhangi bir işlem ile ilişkili olan ve tarafından döndürülen işlem durumu bilgileri tanımlar [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
 Hakkında daha fazla bilgi için **GetContext** kullanıcı durumu bilgilerini sağlamak için diğer WinINet sınıfları ile works başlıklı makaleye bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı hakkında daha fazla bilgi için tanımlayıcı.  
  
##  <a name="getservername"></a>CInternetConnection::GetServerName  
 Bu Internet bağlantısı ile ilişkilendirilen sunucu adını almak için bu üye işlevini çağırın.  
  
```  
CString GetServerName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu bağlantı nesnesi ile çalışma sunucunun adıdır.  
  
##  <a name="getsession"></a>CInternetConnection::GetSession  
 Bir işaretçi almak için bu üye işlevini çağırın `CInternetSession` bu bağlantıyla ilişkili nesne.  
  
```  
CInternetSession* GetSession() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CInternetSession](../../mfc/reference/cinternetsession-class.md) bu Internet bağlantısı nesneyle ilişkili nesne.  
  
##  <a name="operator_hinternet"></a>CInternetConnection::operator HINTERNET  
 Geçerli Internet oturumu için API düzey tanıtıcısı almak için bu işleci kullanın.  
  
```  
operator HINTERNET() const;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)



