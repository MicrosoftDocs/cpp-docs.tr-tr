---
title: WinInet Temelleri
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: b989e5c3df63ee7b5129d01468a0f869772ed286
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367330"
---
# <a name="wininet-basics"></a>WinInet Temelleri

Uygulamanızın içinden dosya indirmek ve yüklemek için FTP desteği eklemek için WinInet'i kullanabilirsiniz. [OnStatusCallback'i](../mfc/reference/cinternetsession-class.md#onstatuscallback) geçersiz kılabilir ve dosyaları ararken ve indirirken kullanıcılara ilerleme bilgileri sağlamak için *dwContext* parametresini kullanabilirsiniz.

Bu makalede aşağıdaki konular yer alıyor:

- [Çok Basit Bir Tarayıcı Oluşturun](#_core_create_a_very_simple_browser)

- [Web Sayfası İndir](#_core_download_a_web_page)

- [FTP bir Dosya](#_core_ftp_a_file)

- [Bir Gopher Dizini alın](#_core_retrieve_a_gopher_directory)

- [Dosyaları Aktarırken İlerleme Bilgilerini Görüntüleme](#_core_display_progress_information_while_transferring_files)

Aşağıdaki kod alıntıları basit bir tarayıcının nasıl oluşturulup, bir Web sayfası nın nasıl indirilir, FTP dosyasını nasıl indirilir ve bir gopher dosyası araması yapılacağını gösterir. Bunlar tam örnek olarak ifade edilmez ve tüm özel durum işleme içermez.

WinInet hakkında daha fazla bilgi için [Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)bakın.

## <a name="create-a-very-simple-browser"></a><a name="_core_create_a_very_simple_browser"></a>Çok Basit Bir Tarayıcı Oluşturun

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

## <a name="download-a-web-page"></a><a name="_core_download_a_web_page"></a>Web Sayfası İndir

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

## <a name="ftp-a-file"></a><a name="_core_ftp_a_file"></a>FTP bir Dosya

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

## <a name="retrieve-a-gopher-directory"></a><a name="_core_retrieve_a_gopher_directory"></a>Bir Gopher Dizini alın

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>OnStatusCallback'i kullanma

WinInet sınıflarını kullanırken, durum bilgilerini almak için uygulamanızın [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesinin [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) üyesini kullanabilirsiniz. Kendi `CInternetSession` nesnenizi türetiyor, `OnStatusCallback`geçersiz kılar ve durum geri aramalarını `OnStatusCallback` etkinleştiriyorsanız, MFC işlevinizi o Internet oturumundaki tüm etkinliklerle ilgili ilerleme bilgileriyle birlikte çağırır.

Tek bir oturum birkaç bağlantıyı destekleyebileceğinden (kullanım ömürleri boyunca birçok `OnStatusCallback` farklı işlem gerçekleştirebilir), belirli bir bağlantı veya işlemle her durum değişikliğini tanımlamak için bir mekanizma gerekir. Bu mekanizma, WinInet destek sınıflarında üye işlevlerin çoğuna verilen bağlam kimliği parametresi tarafından sağlanır. Bu parametre her zaman **DWORD** türündedir ve her zaman *dwContext*olarak adlandırılır.

Belirli bir Internet nesnesine atanan bağlam, yalnızca `OnStatusCallback` `CInternetSession` nesnenin nesnenin üyesinde neden olduğu etkinliği tanımlamak için kullanılır. Çağrı çeşitli `OnStatusCallback` parametreler alır; bu parametreler, uygulamanız için hangi işlem ve bağlantı için hangi ilerlemenin yapıldığını söylemek için birlikte çalışır.

Bir `CInternetSession` nesne oluşturduğunuzda, oluşturucuya *bir dwContext* parametresi belirtebilirsiniz. `CInternetSession`kendisi bağlam kimliğini kullanmaz; bunun yerine, bağlam kimliğini açıkça kendi bağlam kimliklerini almıyorum herhangi bir **InternetConnection**türetilmiş nesnelere geçirir. Buna karşılık, `CInternetConnection` farklı bir bağlam kimliği `CInternetFile` açıkça belirtmezseniz, bu nesneler içerik kimliğini oluşturdukları nesnelere geçirir. Diğer taraftan, kendi bağlam kimliğinizi belirtirseniz, nesne ve yaptığı herhangi bir çalışma bu bağlam kimliğiyle ilişkilendirilir. İşlevinizde `OnStatusCallback` size hangi durum bilgilerinin verildiğini belirlemek için bağlam kimliklerini kullanabilirsiniz.

## <a name="display-progress-information-while-transferring-files"></a><a name="_core_display_progress_information_while_transferring_files"></a>Dosyaları Aktarırken İlerleme Bilgilerini Görüntüleme

Örneğin, bir dosyayı okumak için FTP sunucusuyla bağlantı oluşturan bir uygulama yazarsanız ve ayrıca Bir Web sayfası almak `CInternetSession` için bir `CInternetConnection` HTTP sunucusuna bağlanırsa, bir `CHttpSession`nesneniz, `CInternetFile` iki nesneniz (biri bir, `CFtpSession` diğeri bir) ve iki nesne (her bağlantı için bir nesne) olur. *dwContext* parametreleri için varsayılan değerleri kullandıysanız, FTP bağlantısı `OnStatusCallback` için ilerlemeyi gösteren çağrıları ve HTTP bağlantısı için ilerlemeyi gösteren çağrıları ayırt edemeyebilirsiniz. Daha sonra test edebilirsiniz bir *dwContext* Kimliği `OnStatusCallback`belirtirseniz, hangi işlem geri arama oluşturulan bileceksiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC İnternet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 İnternet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)
