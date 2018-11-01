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
ms.openlocfilehash: 7e05bfdc8af680ae8fc7412d20b57151b8581af8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554355"
---
# <a name="mfc-classes-for-creating-internet-client-applications"></a>Internet İstemci Uygulamaları Oluşturmak için MFC Sınıfları

MFC Internet istemci uygulamaları yazmak için aşağıdaki sınıflar ve genel işlevler sağlar. Yukarıdaki girintisiz sınıfından türetilmiş bir sınıf girinti gösterir. `CGopherFile` ve `CHttpFile` öğesinden türetilen `CInternetFile`, örneğin. Bu sınıflar ve genel işlevler AFXINET bildirilir. H dışında `CFileFind`, AFX bildirilir. H

## <a name="classes"></a>Sınıflar

- [Cınternetsession](../mfc/reference/cinternetsession-class.md)

- [CInternetConnection](../mfc/reference/cinternetconnection-class.md)

   - [CFtpConnection](../mfc/reference/cftpconnection-class.md)

   - [CGopherConnection](../mfc/reference/cgopherconnection-class.md)

   - [CHttpConnection](../mfc/reference/chttpconnection-class.md)

- [Cınternetfile](../mfc/reference/cinternetfile-class.md)

   - [CGopherFile](../mfc/reference/cgopherfile-class.md)

   - [CHttpFile](../mfc/reference/chttpfile-class.md)

- [CFileFind](../mfc/reference/cfilefind-class.md)

   - [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)

   - [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)

- [CGopherLocator](../mfc/reference/cgopherlocator-class.md)

- [Cınternetexception](../mfc/reference/cinternetexception-class.md)

## <a name="global-functions"></a>Genel işlevleri

- [AfxParseURL](reference/internet-url-parsing-globals.md#afxparseurl)

- [Afxgetınternethandletype](reference/internet-url-parsing-globals.md#afxgetinternethandletype)

- [Afxthrowınternetexception](reference/internet-url-parsing-globals.md#afxthrowinternetexception)

## <a name="see-also"></a>Ayrıca Bkz.

[Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet İstemci Sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
