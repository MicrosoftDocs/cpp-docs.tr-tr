---
title: Nasıl MFC Internet istemci uygulamaları oluşturmayı kolaylaştırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26380dc7e01449e4700ddf403c7395714287ed38
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407172"
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>MFC'nin Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması

Microsoft Foundation sınıfları MFC programcıları için tanıdık bir bağlam sağlar bir şekilde Win32 Internet uzantısı (WinINet) işlevleri kapsüller. MFC üç Internet dosya sınıfları sağlar ([Cınternetfile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../mfc/reference/chttpfile-class.md), ve [CGopherFile](../mfc/reference/cgopherfile-class.md)) türetilen [CStdioFile](../mfc/reference/cstdiofile-class.md) sınıfı . Yalnızca bu alma ve Internet veri düzenleme kullanmış olan programcıları sınıflarının `CStdioFile` bu sınıfların ancak yerel dosyaları için yerel dosya ve Internet dosyaları tutarlı ve şeffaf bir biçimde işleyebilirsiniz.

MFC WinINet sınıfları aynı işlevleri sağlar `CStdioFile` Internet üzerinden aktarılan veriler için. Bu sınıfların bir üst düzey uygulama programlama arabirimi, uygulamaların Internet uyumlu hale getirme için hızlı ve kolay bir yol sağlayan HTTP, FTP ve gopher Internet protokolleri soyut. Örneğin, bir FTP sunucusuna bağlanan yine de düşük bir düzeyde birkaç adım gerektirir, ancak bir MFC geliştirici olarak, yalnızca bir çağrı yapmak ihtiyacınız `CInternetSession::GetFTPConnection` bu bağlantıyı oluşturmak için.

Ayrıca, MFC WinINet sınıfları aşağıdaki avantajları sağlar:

- Arabelleğe alınan g/ç

- Verileriniz için tür açısından güvenli tanıtıcıları

- Birçok işlev için varsayılan parametreleri

- Özel durum için genel Internet hatalarını işleme

- Otomatik temizleme açık tanıtıcıları ve bağlantılar

## <a name="see-also"></a>Ayrıca Bkz.

[Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[WinInet'in Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)

