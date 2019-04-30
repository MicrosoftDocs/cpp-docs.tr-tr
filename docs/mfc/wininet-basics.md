---
title: WinInet Temelleri
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: 79ec102aa27440c64f03c6e22b9f2fe959cac6b9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399557"
---
# <a name="wininet-basics"></a>WinInet Temelleri

WinINet indirmek ve uygulamanız içinde dosyaları karşıya yükleme için FTP desteği eklemek için kullanabilirsiniz. Geçersiz kılabilirsiniz [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) ve *dwContext* arayın ve dosyaları indirme ilerleme durumu bilgileri kullanıcılara sunmak için parametre.

Bu makalede aşağıdaki konuları içerir:

- [Çok basit bir tarayıcı oluşturma](#_core_create_a_very_simple_browser)

- [Bir Web sayfası indirin](#_core_download_a_web_page)

- [FTP bir dosya](#_core_ftp_a_file)

- [Bir Gopher dizine alınamıyor](#_core_retrieve_a_gopher_directory)

- [Dosyaları aktarma sırasında ilerleme bilgisini görüntülemek](#_core_display_progress_information_while_transferring_files)

Aşağıdaki kod alıntıları, basit bir tarayıcı oluşturmak, bir Web sayfası, FTP bir dosya indirin ve bir gopher dosyayı aramak nasıl ekleyebileceğiniz gösterilmektedir. Tam örnekler değildir ve tüm özel durum işlemeyi içerir.

WinINet hakkında ek bilgi için bkz. [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md).

##  <a name="_core_create_a_very_simple_browser"></a> Çok basit bir tarayıcı oluşturma

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

##  <a name="_core_download_a_web_page"></a> Bir Web sayfası indirin

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

##  <a name="_core_ftp_a_file"></a> FTP bir dosya

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

##  <a name="_core_retrieve_a_gopher_directory"></a> Bir Gopher dizine alınamıyor

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>OnStatusCallback kullanın

WinINet sınıfları kullanırken kullanabileceğiniz [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) uygulamanızın üyesi [Cınternetsession](../mfc/reference/cinternetsession-class.md) durum bilgilerini almak için nesne. Kendi türetirseniz `CInternetSession` nesne, geçersiz kılma `OnStatusCallback`ve durumu geri çağırmalar etkinleştirme MFC çağırır, `OnStatusCallback` Internet oturumu hakkında tüm etkinliklerin ilerleme bilgisini işleviyle.

Tek bir oturumda (Bu, kendi ömrü boyunca birçok farklı farklı işlemler gerçekleştirebilir) birkaç bağlantılarını desteklemiyor olabilir çünkü `OnStatusCallback` belirli bir bağlantı veya işlem ile her bir durum değişikliği tanımlamak için bir mekanizma gerekir. Bu mekanizma, çoğu WinINet destek sınıflardaki üye işlevleri belirtilen bağlam kimliği parametresi tarafından sağlanır. Bu parametre her zaman türünde **DWORD** ve her zaman adlı *dwContext*.

Belirli bir Internet nesnesine atanmış içerik yalnızca etkinlik nesnesi neden olur tanımlamak için kullanılan `OnStatusCallback` üyesi `CInternetSession` nesne. Çağrı `OnStatusCallback` ; birkaç parametre alır. Bu parametre hangi işlem ve bağlantısı için hangi ilerleme yapıldı, uygulamaya bildirmek için birlikte çalışır.

Oluştururken bir `CInternetSession` belirtebileceğiniz nesnesi bir *dwContext* oluşturucusuna parametre. `CInternetSession` kendi bağlam Kimliğini kullanmaz; Bunun yerine, bağlam Kimliğini herhangi açın arabimini **InternetConnection**-türetilmiş açıkça bir bağlam kimliği, kendi elde etmezsiniz nesneleri. Buna karşılık, bu `CInternetConnection` nesneleri boyunca bağlam Kimliğine geçecek `CInternetFile` açıkça farklı bir bağlam kimliği belirtmezseniz, oluşturdukları nesneleri Öte yandan, kendinize ait bir belirli bir bağlam kimliği, nesne ve mevcut herhangi bir iş, içerik kimliği ile ilişkilendirilecek belirtirseniz Bağlam kimlikleri hangi durum bilgilerini size verilen tanımlamak için kullanabileceğiniz, `OnStatusCallback` işlevi.

##  <a name="_core_display_progress_information_while_transferring_files"></a> Dosyaları aktarma sırasında ilerleme bilgisini görüntülemek

Örneğin, bir dosyayı okumak için bir FTP sunucusuna bir bağlantı oluşturur ve ayrıca bir Web sayfası almak için bir HTTP sunucusuna bağlanan bir uygulama yazıyorsanız, sahip olacaksınız bir `CInternetSession` nesnesi, iki `CInternetConnection` nesneleri (biri olacak bir `CFtpSession` ve diğer olacaktır bir `CHttpSession`) ve iki `CInternetFile` nesneleri (her bağlantı için bir tane). Varsayılan değerleri kullandıysanız *dwContext* parametreleri olmayan okunup arasında ayrım yapmak mümkün `OnStatusCallback` FTP bağlantı ve ilerleme durumunu gösteren etkinleştirmeleri için ilerlemeyi göstermek etkinleştirmeleri HTTP bağlantısı. Belirtirseniz bir *dwContext* , daha sonra için test edebilirsiniz kimliği `OnStatusCallback`, geri çağırma işlemi oluşturulan öğrenmiş olacaksınız.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)
