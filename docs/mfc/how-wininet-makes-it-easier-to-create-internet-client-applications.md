---
title: WinInet'in Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], vs. WinInet
- WinInet classes [MFC], vs. WinSock
- WinInet classes [MFC], Internet client applications
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
ms.openlocfilehash: 54f63da7451dfef39a33e6b437be938cb1652326
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624568"
---
# <a name="how-wininet-makes-it-easier-to-create-internet-client-applications"></a>WinInet'in Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması

Win32 Internet uzantıları veya WinInet, Gopher, FTP ve HTTP gibi yaygın Internet protokollerine erişim sağlar. WININET kullanarak, WinSock, TCP/IP veya belirli Internet protokollerinin ayrıntıları ile uğraşmak zorunda kalmadan Internet istemci uygulamalarını daha yüksek bir programlama düzeyinde yazabilirsiniz. WinInet, bilinen bir Win32 API arabirimi ile her üç protokol için tutarlı bir işlev kümesi sağlar. Bu tutarlılık, temeldeki protokol değişirse (örneğin, FTP 'den HTTP 'ye) yapmanız gereken kod değişikliklerini en aza indirir.

Visual C++ WinInet kullanmanız için iki yol sağlar. Win32 Internet işlevlerini doğrudan çağırabilirsiniz (daha fazla bilgi için Windows SDK OLE belgelerine bakın) veya WinInet 'yi [MFC WinINet sınıfları](mfc-classes-for-creating-internet-client-applications.md)aracılığıyla kullanabilirsiniz.

**WinInet ' i kullanarak şunları yapabilirsiniz:**

- HTML sayfalarını indirin.

   HTTP, bir sunucudan bir istemci tarayıcısına HTML sayfaları aktarmak için kullanılan bir protokoldür.

- Dosyaları karşıya yüklemek veya indirmek ya da dizin listelerini almak için FTP istekleri gönderin.

   Tipik bir istek, bir dosyayı indirmek için anonim bir oturum açma işlemi olur.

- Internet 'teki kaynaklara erişmek için Gopher 'ın menü sistemini kullanın.

   Menü öğeleri, diğer menüler de dahil olmak üzere çeşitli türler, arama yaptığınız bir dizine alınmış veritabanı veya bir dosya grubu olabilir.

Üç protokolde bir bağlantı kurar, sunucuya istek yaparsınız ve bağlantıyı kapatırsınız.

**MFC WinInet sınıfları şunları kolaylaştırır:**

- Bir sabit sürücüdeki dosyaları okurken kolayca HTTP, FTP ve gopher sunucularından bilgi okuyun.

- Doğrudan WinSock veya TCP/IP 'ye programlamayla programlama yapmadan HTTP, FTP ve gopher protokollerini kullanın.

   Win32 Internet işlevlerini kullanan geliştiricilerin TCP/IP veya Windows Yuvaları hakkında bilgi sahibi olması gerekmez. Doğrudan WinSock ve TCP/IP protokollerini kullanarak yuva düzeyinde çalışmaya devam edebilirsiniz, ancak MFC WinInet sınıflarının Internet üzerinden HTTP, FTP ve gopher protokollerine erişmek için kullanılması da daha kolay olur. Birçok yaygın işlem için, geliştiricilerin kullandıkları belirli protokolün ayrıntılarını bilmeleri gerekmez.

Bilgisayarınız tarafından Internet 'teki diğer bilgisayarlara istemci olarak gerçekleştirilebilecek birçok işlem uzun sürebilir. Bu işlemlerin hızı genellikle ağ bağlantınızın hızına göre sınırlandırılır, ancak diğer ağ trafiğinden ve işlemin karmaşıklığı bundan de etkilenebilir. Örneğin, uzak bir FTP sunucusuna bağlanma, bilgisayarınızın adresini bulmak için bu sunucunun adını öncelikle bulmasını gerektirir. Uygulamanız daha sonra bu adresteki sunucuya bağlanmaya çalışır. Bağlantı açıldıktan sonra, dosyaları almak için bağlantıyı kullanabilmeniz için bilgisayarınız ve uzak sunucu, Dosya Aktarım Protokolü ile bir konuşma başlatır.

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (Winınet)](win32-internet-extensions-wininet.md)<br/>
[MFC'nin Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması](how-mfc-makes-it-easier-to-create-internet-client-applications.md)
