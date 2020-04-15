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
ms.openlocfilehash: 578fd5b72e6c04610aa862f1a6631895a32a9bfe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358212"
---
# <a name="mfc-classes-for-creating-internet-client-applications"></a>Internet İstemci Uygulamaları Oluşturmak için MFC Sınıfları

MFC, Internet istemcisi uygulamaları yazmak için aşağıdaki sınıfları ve genel işlevleri sağlar. Girintisi, bir sınıfın üzerindeki girintili sınıftan türetildiğianlamına geliyor. `CGopherFile`ve `CHttpFile` türetilmiştir `CInternetFile`, örneğin. Bu sınıflar ve genel işlevler AFXINET'de bildirilir. H, `CFileFind`AFX'te beyan edilen ler hariç. H.

## <a name="classes"></a>Sınıflar

- [Cınternetsession](../mfc/reference/cinternetsession-class.md)

- [Cınternetconnection](../mfc/reference/cinternetconnection-class.md)

  - [Cftpconnection](../mfc/reference/cftpconnection-class.md)

  - [Cgopherconnection](../mfc/reference/cgopherconnection-class.md)

  - [CHttpBağlantı](../mfc/reference/chttpconnection-class.md)

- [Cınternetfile](../mfc/reference/cinternetfile-class.md)

  - [Cgopherfile](../mfc/reference/cgopherfile-class.md)

  - [Chttpfile](../mfc/reference/chttpfile-class.md)

- [Cfilefind](../mfc/reference/cfilefind-class.md)

  - [Cftpfilefind](../mfc/reference/cftpfilefind-class.md)

  - [Cgopherfilefind](../mfc/reference/cgopherfilefind-class.md)

- [Cgopherlocator](../mfc/reference/cgopherlocator-class.md)

- [Cınternetexception](../mfc/reference/cinternetexception-class.md)

## <a name="global-functions"></a>Küresel Fonksiyonlar

- [AfxParseURL](reference/internet-url-parsing-globals.md#afxparseurl)

- [AfxGetInternetHandleType](reference/internet-url-parsing-globals.md#afxgetinternethandletype)

- [AfxThrowInternetException](reference/internet-url-parsing-globals.md#afxthrowinternetexception)

## <a name="see-also"></a>Ayrıca bkz.

[Win32 İnternet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet İstemci Sınıfları için Ön Koşullar](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
