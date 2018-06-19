---
title: WinINet temelleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38506d0b25918bbc9d70ec1801971b070d620bf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385930"
---
# <a name="wininet-basics"></a>WinInet Temelleri
WinINet indirip dosyalarından, uygulamanızda karşıya yüklemek için FTP desteği eklemek için kullanabilirsiniz. Geçersiz kılabilirsiniz [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) ve `dwContext` aramak ve dosyaları karşıdan kullanıcılara ilerleme durumu bilgileri sağlamak için parametre.  
  
 Bu makalede aşağıdaki konuları içerir:  
  
-   [Çok basit bir tarayıcı oluşturma](#_core_create_a_very_simple_browser)  
  
-   [Bir Web sayfası karşıdan yükle](#_core_download_a_web_page)  
  
-   [FTP dosya](#_core_ftp_a_file)  
  
-   [Gopher dizini alma](#_core_retrieve_a_gopher_directory)  
  
-   [Dosyaları aktarma sırasında ilerleme durumu bilgilerini görüntüleme](#_core_display_progress_information_while_transferring_files)  
  
 Aşağıda kod parçalarını basit bir tarayıcı oluşturmak, bir Web sayfası, FTP bir dosyayı indirin ve bir gopher dosyayı aramak nasıl ekleyebileceğiniz gösterilmektedir. Tam örnek olarak amaçlanmamıştır ve tüm özel durum işleme içerir.  
  
 WinINet hakkında ek bilgi için bkz: [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md).  
  
##  <a name="_core_create_a_very_simple_browser"></a> Çok basit bir tarayıcı oluşturma  
 [!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]  
  
##  <a name="_core_download_a_web_page"></a> Bir Web sayfası karşıdan yükle  
 [!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]  
  
##  <a name="_core_ftp_a_file"></a> FTP dosya  
 [!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a> Gopher dizini alma  
 [!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]  
  
## <a name="use-onstatuscallback"></a>OnStatusCallback kullanın  
 WinINet sınıfları kullanırken kullanabileceğiniz [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) uygulamanızın üyesi [CInternetSession](../mfc/reference/cinternetsession-class.md) durum bilgilerini almak için nesne. Kendi türetirseniz `CInternetSession` nesne, geçersiz kılma `OnStatusCallback`ve durum geri çağırmalar etkinleştirmek MFC çağıracaktır, `OnStatusCallback` tüm etkinliklerin ilerleme bilgiler bu Internet oturumunda işlevi.  
  
 Tek bir oturumla (hangi kendi ömürleri boyunca birçok farklı farklı işlemler gerçekleştirebilir) birkaç bağlantıları desteklemiyor olabilir çünkü `OnStatusCallback` belirli bağlantı veya işlem ile her bir durum değişikliği tanımlamak için bir mekanizma gerekir. Bu mekanizma WinINet destek sınıflardaki üye işlevleri çoğunu verilen bağlam kimliği parametresi tarafından sağlanır. Bu parametre her zaman türünde `DWORD` ve her zaman adlı `dwContext`.  
  
 Belirli bir Internet nesnesine atanmış içerik yalnızca nesne neden olan etkinliği tanımlamak için kullanılan `OnStatusCallback` üyesi `CInternetSession` nesnesi. Çağrı `OnStatusCallback` birkaç parametre; aldığında bu parametreler, uygulamanızın hangi işlem ve bağlantısı için hangi ilerleme yapılmış bildirmek için birlikte çalışır.  
  
 Oluştururken bir `CInternetSession` nesnesi belirtebilirsiniz bir `dwContext` Oluşturucusu parametresi. `CInternetSession` kendisini bağlam Kimliğini kullanmaz; Bunun yerine, içerik kimliği herhangi açın geçirir **InternetConnection**-türetilmiş açıkça bir bağlam kimliği kendi almadım nesneleri. Buna açın, bu `CInternetConnection` nesneleri boyunca context ID geçecek `CInternetFile` farklı bir bağlam kimliği açıkça belirtmezseniz oluşturdukları nesneleri Diğer taraftan, kendi özel bağlamı kimliği, nesne ve mevcut herhangi bir iş, içerik kimliği ile ilişkilendirilecek belirtirseniz Hangi durum bilgilerini size verilen tanımlamak için bağlam kimlikleri kullanabilirsiniz, `OnStatusCallback` işlevi.  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a> Dosyaları aktarma sırasında ilerleme durumu bilgilerini görüntüleme  
 Örneğin, bir dosyayı okumak için bir FTP sunucusu ile bir bağlantı oluşturur ve ayrıca bir Web sayfası almak için bir HTTP sunucusuna bağlanan bir uygulama yazıyorsanız, sahip olacaksınız bir `CInternetSession` nesnesi, iki `CInternetConnection` nesneleri (biri olacak bir **CFtpSession** ve diğer olacak bir **CHttpSession**) ve iki `CInternetFile` nesneleri (her bağlantı için bir tane). Varsayılan değerleri kullandıysanız `dwContext` parametreleri, değil olacaktır ayırt mümkün `OnStatusCallback` FTP bağlantısı ve HTTP bağlantı ilerlemeyi göstermek çağrılarını ilerlemeyi göstermek çağrılarını. Belirtirseniz bir `dwContext` daha sonra için de test edebilirsiniz kimliği `OnStatusCallback`, geri çağırma işlemi oluşturulan bilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet Programlama temelleri](../mfc/mfc-internet-programming-basics.md)   
 [Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)

