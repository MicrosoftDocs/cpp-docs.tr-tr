---
description: 'Daha fazla bilgi edinin: WinINet temelleri'
title: WinInet Temelleri
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: 1ba8f9b898476849ca9bbb39b7850bbce3605154
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172784"
---
# <a name="wininet-basics"></a>WinInet Temelleri

Uygulamanızı içinden dosyaları indirmek ve karşıya yüklemek için FTP desteği eklemek üzere WinInet ' i kullanabilirsiniz. Dosya ararken ve indirdiğinizde kullanıcılara ilerleme bilgileri sağlamak için [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) öğesini geçersiz kılabilir ve *dwContext* parametresini kullanabilirsiniz.

Bu makale aşağıdaki konuları içerir:

- [Çok basit tarayıcı oluşturma](#_core_create_a_very_simple_browser)

- [Web sayfası indirme](#_core_download_a_web_page)

- [FTP a dosyası](#_core_ftp_a_file)

- [Gopher dizini alma](#_core_retrieve_a_gopher_directory)

- [Dosyaları aktarırken Ilerleme bilgilerini görüntüle](#_core_display_progress_information_while_transferring_files)

Aşağıdaki kod, basit bir tarayıcı oluşturmayı, bir Web sayfası yüklemeyi, FTP bir dosyayı indirmeyi ve gopher dosyası aramanızı göstermektedir. Bunlar, tüm örneklere sahip değildir ve hepsi özel durum işleme içermez.

WinInet hakkında daha fazla bilgi için bkz. [Win32 Internet Uzantıları (Winınet)](../mfc/win32-internet-extensions-wininet.md).

## <a name="create-a-very-simple-browser"></a><a name="_core_create_a_very_simple_browser"></a> Çok basit tarayıcı oluşturma

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

## <a name="download-a-web-page"></a><a name="_core_download_a_web_page"></a> Web sayfası indirme

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

## <a name="ftp-a-file"></a><a name="_core_ftp_a_file"></a> FTP a dosyası

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

## <a name="retrieve-a-gopher-directory"></a><a name="_core_retrieve_a_gopher_directory"></a> Gopher dizini alma

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>OnStatusCallback kullanma

WinInet sınıflarını kullanırken, durum bilgilerini almak için uygulamanızın [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesinin [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) üyesini kullanabilirsiniz. Kendi nesneniz türetirsiniz `CInternetSession` , geçersiz kılın `OnStatusCallback` ve durum geri çağırmaları ETKINLEŞTIRIRSENIZ, MFC `OnStatusCallback` Bu Internet oturumundaki tüm etkinliklerle ilgili ilerleme bilgileri ile işlevinizi çağırır.

Tek bir oturum birkaç bağlantıyı destekleyebildiğinden (Bu, yaşam sürelerinin ömrü boyunca birçok farklı işlem gerçekleştirebilir), `OnStatusCallback` her durum değişikliğini belirli bir bağlantı veya işlemle tanımlamak için bir mekanizmaya ihtiyaç duyuyor. Bu mekanizma, WinInet destek sınıflarındaki üye işlevlerinin çoğuna verilen bağlam KIMLIĞI parametresi tarafından sağlanır. Bu parametre her zaman **DWORD** türündedir ve her zaman *dwContext* olarak adlandırılır.

Belirli bir Internet nesnesine atanan bağlam, yalnızca nesnenin üyesinde nesne nedenlerini belirlemek için kullanılır `OnStatusCallback` `CInternetSession` . ' A çağrı `OnStatusCallback` birkaç parametre alır; bu parametreler, uygulamanıza hangi işlem ve bağlantı için ilerleme yapıldığını bildirmek için birlikte çalışır.

Bir `CInternetSession` nesne oluşturduğunuzda, oluşturucuya bir *dwContext* parametresi belirtebilirsiniz. `CInternetSession` , bağlam KIMLIĞINI kullanmaz; Bunun yerine, bağlam KIMLIĞINI açık bir şekilde kendi bağlam KIMLIĞI olmayan herhangi bir **InternetConnection** türetilmiş nesnesine geçirir. Buna karşılık, `CInternetConnection` `CInternetFile` açıkça farklı bır bağlam kimliği belirtmezseniz, bu nesneler içerik kimliğini oluşturdukları nesnelere iletir. Diğer taraftan, kendi özel bir bağlam KIMLIĞI belirtirseniz, nesne ve onun yaptığı tüm işler bu bağlam KIMLIĞIYLE ilişkilendirilir. İşlevinizde size hangi durum bilgilerinin verildiğini belirlemek için bağlam kimliklerini kullanabilirsiniz `OnStatusCallback` .

## <a name="display-progress-information-while-transferring-files"></a><a name="_core_display_progress_information_while_transferring_files"></a> Dosyaları aktarırken Ilerleme bilgilerini görüntüle

Örneğin, bir dosyayı okumak için bir FTP sunucusuyla bağlantı oluşturan ve ayrıca bir Web sayfası almak için bir HTTP sunucusuna bağlanan bir uygulama yazarsanız, bir `CInternetSession` nesne, iki `CInternetConnection` nesneniz (biri bir `CFtpSession` ve diğeri bir olur `CHttpSession` ) ve iki `CInternetFile` nesne (her bağlantı için bir tane) olur. *DwContext* parametreleri için varsayılan değerleri KULLANDıYSANıZ, `OnStatusCallback` FTP bağlantısı için ilerlemeyi BELIRTEN çağırmaları ve http bağlantısı için ilerlemeyi belirten etkinleştirmeleri arasında ayrım yapamazsınız. Daha sonra ' de test etmek üzere bir *dwContext* kimliği belirtirseniz `OnStatusCallback` , geri çağırma işlemini hangi işlemin üretbileceğinizi bilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 Internet Uzantıları (Winınet)](../mfc/win32-internet-extensions-wininet.md)
