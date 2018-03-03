---
title: "Nasıl WinINet Internet istemci uygulamaları oluşturmayı kolaylaştırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], vs. WinInet
- WinInet classes [MFC], vs. WinSock
- WinInet classes [MFC], Internet client applications
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9c79404f296df09afb177930897064b8455217d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-wininet-makes-it-easier-to-create-internet-client-applications"></a>WinInet'in Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması
Win32 Internet Uzantıları veya WinINet, gopher, FTP ve HTTP gibi ortak Internet protokolleri erişim sağlar. WinINet kullanarak Internet istemci uygulamaları programlama, daha yüksek düzeyde WinSock, TCP/IP'yi veya belirli Internet protokolleri ayrıntılarını ile mücadele etmek zorunda kalmadan yazabilirsiniz. WinINet tanıdık Win32 API arabirimi ile tüm üç iletişim kuralları için tutarlı bir işlevler kümesi sağlar. Bu tutarlılık temel Protokolü (örneğin, gelen HTTP FTP) değişirse yapmanız gereken kod değişikliklerini en aza indirir.  
  
 Visual C++ WinINet kullanmanız için iki yöntem sağlar. Win32 Internet işlevlerini doğrudan çağırma (daha fazla bilgi için Windows SDK'sındaki OLE belgelere bakın) veya WinINet aracılığıyla kullanabilirsiniz [MFC WinINet sınıfları](../mfc/mfc-classes-for-creating-internet-client-applications.md).  
  
 **WinINet için kullanabilirsiniz:**  
  
-   HTML sayfaları indirin.  
  
     HTTP HTML sayfaları bir sunucudan bir istemci tarayıcısına aktarmak için kullanılan bir protokoldür.  
  
-   Karşıya yükleme dosyalarını indirin veya dizin listeleri almak için FTP istekleri göndermek.  
  
     Tipik bir dosyayı indirmek için anonim bir oturum açma isteğidir.  
  
-   Gopher'ın menü sistemi Internet üzerindeki kaynaklara erişmek için kullanır.  
  
     Menü öğeleri diğer menüleri, arama yapabilirsiniz dizini oluşturulmuş bir veritabanı, bir haber veya bir dosya gibi çeşitli türleri olabilir.  
  
 Tüm üç protokoller için bağlantı kurmak, sunucuya isteklerde ve bağlantıyı kapatın.  
  
 **MFC WinINet sınıfları kolay hale getirin:**  
  
-   Bilgi HTTP, FTP ve gopher sunucularından bir sabit diskten dosyaları okuma olarak kolayca okuyun.  
  
-   HTTP, FTP ve gopher programlamaya doğrudan WinSock veya TCP/IP olmadan protokolleri kullanır.  
  
     Win32 Internet işlevlerini kullanan geliştiriciler TCP/IP'yi veya Windows Yuvaları ile ilgili bilgi sahibi olmanız gerekmez. WinSock ve TCP/IP'yi protokollerini kullanarak doğrudan, hala yuva düzeyinde bir program ancak Internet üzerinden erişim HTTP, FTP ve gopher protokolleri MFC WinINet sınıfları kullanmak bile kolaydır. Birçok ortak işlemleri için kullanmakta olduğunuz belirli protokolü ayrıntılarını bilmek geliştiriciler gerekmez.  
  
 Bilgisayarınızın Internet üzerindeki diğer bilgisayarlara bir istemci olarak gerçekleştirilebilir birçok işlem uzun sürebilir. Bu işlem hızını, ağ bağlantınızın hızına göre genellikle sınırlı, ancak bunlar aynı zamanda diğer ağ trafiğinden ve işlem karmaşıklığını tarafından etkilenebilir. Uzak bir FTP sunucusuna bağlanırken, örneğin, bilgisayarınızı ilk adresini bulmak için o sunucunun adını arama gerektirir. Uygulamanız bu adresteki sunucusuna bağlanmak daha sonra deneyecek. Bağlantı açıldıktan sonra bilgisayarınız ve uzak sunucu dosyaları almak için bağlantı gerçekte kullanmadan önce bir konuşma Dosya Aktarım Protokolü ile başlatır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)   
 [MFC'nin Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)

