---
title: Winınet'in Internet istemci uygulamaları oluşturmayı kolaylaştırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], vs. WinInet
- WinInet classes [MFC], vs. WinSock
- WinInet classes [MFC], Internet client applications
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 356027e151dcc94891b9c4043e4f1af8b2f0b947
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430923"
---
# <a name="how-wininet-makes-it-easier-to-create-internet-client-applications"></a>WinInet'in Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması

Win32 Internet Uzantıları veya WinINet, gopher, FTP ve HTTP gibi common Internet protokolleri erişim sağlar. WinINet kullanarak Internet istemci uygulamaları için programlama, daha yüksek düzeyde WinSock, TCP/IP'yi veya belirli Internet protokolleri ayrıntılarını ile uğraşmak zorunda kalmadan yazabilirsiniz. WinINet tanıdık bir Win32 API arabirimi ile tüm üç protokolden işlevleri tutarlı özellik kümesi sunar. Bu tutarlılık, temel alınan protokoldeki (örneğin, FTP üzerinden HTTP) değişirse yapmanız gereken kod değişikliklerini en aza indirir.

Visual C++ WinINet kullanabilmeniz için iki yol sunar. Win32 Internet işlevleri doğrudan çağırabilir miyim (daha fazla bilgi için Windows SDK'sı OLE belgelerinde bakın) veya WinINet aracılığıyla kullanabileceğiniz [MFC WinINet sınıfları](../mfc/mfc-classes-for-creating-internet-client-applications.md).

**WinINet için kullanabilirsiniz:**

- HTML sayfaları indirin.

     HTML sayfaları, bir sunucudan istemci tarayıcısına aktarmak için kullanılan protokol HTTP'dir.

- FTP istekleri karşıya yükleme dosyalarını indirmek veya dizin listesinde alma gönderirler.

     Tipik bir dosyayı indirmek için anonim bir oturum açma isteğidir.

- Gopher'ın menü sistemi, Internet üzerindeki kaynaklara erişmek için kullanır.

     Menü öğelerini başka menüler, arama yapabilirsiniz dizini oluşturulmuş bir veritabanı, bir haber grubu veya bir dosya gibi çeşitli türleri olabilir.

Üç tüm protokoller için bir bağlantı, sunucuya isteklerde ve bağlantıyı kapatın.

**MFC WinINet sınıfları için kolaylaştırır:**

- Bilgi, HTTP, FTP ve gopher sunuculardan dosyaları sabit diskinizden okuma olarak kolayca okuyun.

- WinSock veya TCP/IP'yi için doğrudan programlamaya gerek kalmadan HTTP, FTP ve gopher protokolleri kullanır.

     Win32 Internet işlevleri kullanan geliştiriciler TCP/IP'yi ya da Windows Sockets ile bilgi sahibi olmanız gerekmez. WinSock ve TCP/IP protokolleri kullanarak doğrudan, yine de yuva düzeyinde bir programlama yapabilirsiniz ancak Internet üzerinden erişim HTTP, FTP ve gopher protokolleri MFC WinINet sınıfları kullanmak daha kolaydır. Birçok ortak işlemler için geliştiriciler özel Protokolü kullandıkları ayrıntılarını bilmeniz gerekmez.

Bilgisayarınızın Internet üzerindeki diğer bilgisayarlara bir istemci olarak gerçekleştirilen birçok işlem uzun sürebilir. Hızı bu işlemlerin genellikle ağ bağlantınızın hızına göre sınırlıdır, ancak bunlar aynı zamanda diğer ağ trafiğini ve işlem karmaşıklığı tarafından etkilenebilir. Uzak bir FTP sunucusuna bağlanma, örneğin, bilgisayarınızı adresini bulmak için sunucu adını ilk bakış gerektirir. Uygulamanızı daha sonra bu adresteki sunucuya bağlanma dener. Bağlantı açıldıktan sonra bilgisayarınız ve uzak sunucu dosyaları almak için bağlantı gerçekten kullanmadan önce Dosya Aktarım Protokolü ile bir konuşma başlatır.

## <a name="see-also"></a>Ayrıca Bkz.

[Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[MFC'nin Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)

