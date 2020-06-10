---
title: Internet İstemci Uygulamaları Oluşturmak için MFC Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, WinInet classes
- WinInet classes [MFC], classes
- classes [MFC], MFC
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
ms.openlocfilehash: d65a2e8b373f26fe928e4c3e7c0193aec4edf2d6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618041"
---
# <a name="mfc-classes-for-creating-internet-client-applications"></a>Internet İstemci Uygulamaları Oluşturmak için MFC Sınıfları

MFC, Internet istemci uygulamaları yazmak için aşağıdaki sınıfları ve genel işlevleri sağlar. Girintileme, bir sınıfın yukarıdaki girintisiz sınıftan türetildiğini gösterir. `CGopherFile`ve `CHttpFile` , örneğin öğesinden türet `CInternetFile` . Bu sınıflar ve genel işlevler, AFXıNET içinde bildirilmiştir. `CFileFind`AFX içinde bildirildiği, hariç. Olsun.

## <a name="classes"></a>Sınıflar

- [CInternetSession](reference/cinternetsession-class.md)

- [CInternetConnection](reference/cinternetconnection-class.md)

  - [Cftpbağlantısı](reference/cftpconnection-class.md)

  - [CGopherConnection](reference/cgopherconnection-class.md)

  - [CHttpConnection](reference/chttpconnection-class.md)

- [CInternetFile](reference/cinternetfile-class.md)

  - [CGopherFile](reference/cgopherfile-class.md)

  - [CHttpFile](reference/chttpfile-class.md)

- [CFileFind](reference/cfilefind-class.md)

  - [CFtpFileFind](reference/cftpfilefind-class.md)

  - [CGopherFileFind](reference/cgopherfilefind-class.md)

- [CGopherLocator](reference/cgopherlocator-class.md)

- [CInternetException](reference/cinternetexception-class.md)

## <a name="global-functions"></a>Genel Işlevler

- [AfxParseURL 'Si](reference/internet-url-parsing-globals.md#afxparseurl)

- [AfxGetInternetHandleType](reference/internet-url-parsing-globals.md#afxgetinternethandletype)

- [AfxThrowInternetException](reference/internet-url-parsing-globals.md#afxthrowinternetexception)

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (Winınet)](win32-internet-extensions-wininet.md)<br/>
[Internet Istemci sınıfları için Önkoşullar](prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](writing-an-internet-client-application-using-mfc-wininet-classes.md)
