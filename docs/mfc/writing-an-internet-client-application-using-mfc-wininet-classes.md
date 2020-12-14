---
description: 'Hakkında daha fazla bilgi edinin: MFC WinInet sınıfları kullanarak Internet Istemci uygulaması yazma'
title: MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
ms.openlocfilehash: 61cfe3e9892f2bde6d233728b7b95ca0edd16ee8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189138"
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma

Her Internet istemci uygulamasının temeli Internet oturumundur. MFC, [CInternetSession](../mfc/reference/cinternetsession-class.md)sınıfının nesneleri olarak Internet oturumlarını uygular. Bu sınıfı kullanarak bir Internet oturumu veya birkaç eşzamanlı oturum oluşturabilirsiniz.

Bir sunucuyla iletişim kurmak için bir [CInternetConnection](../mfc/reference/cinternetconnection-class.md) nesnesi ve de gereklidir `CInternetSession` . `CInternetConnection` [CInternetSession:: GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection), [CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection)veya [CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection)kullanarak bir oluşturma oluşturabilirsiniz. Bu çağrıların her biri protokol türüne özeldir. Bu çağrılar, okumak veya yazmak için sunucuda bir dosya açmaz. Veri okumayı veya yazmayı planlıyorsanız, dosyayı ayrı bir adım olarak açmanız gerekir.

Çoğu Internet oturumunda, nesne el `CInternetSession` ile bir [Cınternetdosya](../mfc/reference/cinternetfile-class.md) nesnesiyle birlikte çalışmaktadır:

- Bir Internet oturumu için bir [CInternetSession](../mfc/reference/cinternetsession-class.md)örneği oluşturmanız gerekir.

- Internet oturumunuz verileri okur veya yazar, `CInternetFile` (veya alt sınıfları, [CHttpFile](../mfc/reference/chttpfile-class.md) veya [CGopherFile](../mfc/reference/cgopherfile-class.md)) örneği oluşturmanız gerekir. Verileri bulmanın en kolay yolu [CInternetSession:: OpenURL](../mfc/reference/cinternetsession-class.md#openurl)' i çağırmalıdır. Bu işlev, sizin tarafınızdan sağlanan bir Evrensel Kaynak Konumlandırıcı 'Sını (URL) ayrıştırır, URL tarafından belirtilen sunucuya bir bağlantı açar ve salt okunurdur bir `CInternetFile` nesne döndürür. `CInternetSession::OpenURL` bir protokol türüne özgü değildir — aynı çağrı tüm FTP, HTTP veya Gopher URL 'SI için de geçerlidir. `CInternetSession::OpenURL` Yerel dosyalarla bile ( `CStdioFile` bir yerine bir olarak döndürülüyor) kullanılır `CInternetFile` .

- Internet oturumunuz verileri okumaz veya yazamaz, ancak FTP dizinindeki bir dosyayı silme gibi diğer görevleri gerçekleştiriyorsa, bir örneği oluşturmanız gerekmez `CInternetFile` .

Bir nesne oluşturmanın iki yolu vardır `CInternetFile` :

- `CInternetSession::OpenURL`Sunucu bağlantınızı kurmak için kullanırsanız, çağrısı `OpenURL` bir döndürür `CStdioFile` .

- Sunucu bağlantınızı oluşturmak için,, veya kullanıyorsanız, sırasıyla,, veya ' i `CInternetSession::GetFtpConnection` `GetGopherConnection` `GetHttpConnection` `CFtpConnection::OpenFile` `CGopherConnection::OpenFile` `CHttpConnection::OpenRequest` döndürmek için sırasıyla, veya ' `CInternetFile` `CGopherFile` i çağırmanız gerekir `CHttpFile` .

Bir Internet istemci uygulaması uygulama adımları, `OpenURL` işlevlerden birini kullanarak bir veya protokolüne özgü bir istemciye dayalı olarak genel bir İnternet istemcisi oluşturup oluşturmadığınıza bağlı olarak farklılık gösterir `GetConnection` .

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Nasıl yaparım? FTP, HTTP ve gopher ile genel olarak çalışabilen bir Internet istemci uygulaması yazma](../mfc/steps-in-a-typical-internet-client-application.md)

- [Dosya açan bir FTP istemci uygulaması Nasıl yaparım? yazma](../mfc/steps-in-a-typical-ftp-client-application.md)

- [Nasıl yaparım? dosya açan ancak dosya silme gibi bir dizin işlemi gerçekleştiren bir FTP istemci uygulaması yazın](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)

- [Nasıl yaparım? Gopher istemci uygulaması yazma](../mfc/steps-in-a-typical-gopher-client-application.md)

- [HTTP istemci uygulaması Nasıl yaparım? yazma](../mfc/steps-in-a-typical-http-client-application.md)

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (Winınet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet Istemci uygulamaları oluşturmak için MFC sınıfları](../mfc/mfc-classes-for-creating-internet-client-applications.md)<br/>
[Internet Istemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)
