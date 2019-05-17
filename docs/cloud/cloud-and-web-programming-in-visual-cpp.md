---
title: Visual C++'da Bulut ve Web Programlama
ms.date: 05/14/2019
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
ms.openlocfilehash: 677e9da18e8d171f523994d21bfbd0411270e3c8
ms.sourcegitcommit: bc1b14f29a02685f97c7ef5c098d16db6eaf369f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/16/2019
ms.locfileid: "65790355"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Visual C++'da Bulut ve Web Programlama

C++'da, web ve buluta bağlamak için birkaç seçeneğiniz vardır.

## <a name="microsoft-azure-sdks-and-rest-services"></a>Microsoft Azure SDK'ları ve REST Hizmetleri

- [C++ için Microsoft Azure depolama istemci kitaplığı](https://azure.github.io/azure-storage-cpp/)

  C++ için Azure depolama istemci kitaplığı, ancak bunlarla sınırlı olmamak aşağıdaki yetenekleri dahil olmak üzere Azure depolama ile çalışmak için kapsamlı bir API sağlar:

  - Oluşturma, okuma, silme ve blob kapsayıcıları, tabloları ve kuyrukları listeler.
  - Oluşturma, okuma, silme, liste ve kopyalama BLOB artı okuyup blob'u aralıklarını yazabilir.
  - Ekle, Sil, Değiştir, birleştirme ve bir Azure tablosu varlıkları sorgulayın.
  - Sıraya alma ve bir Azure kuyruğundaki iletileri sıradan çıkarma.
  - Kapsayıcıları, blobları, tablolar ve Kuyruklar gevşek listelemek ve gevşek varlıkları sorgulama

- ANSI C99 [Azure IOT Hub SDK'ları](/azure/iot-hub/iot-hub-devguide-sdks) nesnelerin interneti için arka uç veya cihaz üzerinde çalıştırmak IOT uygulamaları etkinleştirin.

- [OneDrive ve SharePoint Microsoft Graph'te](https://dev.onedrive.com/README.htm)

  OneDrive API uygulamanızı dosyalara ve klasörlere Office 365 ve SharePoint Server 2016'ya bağlanmak için HTTP Hizmetleri sunmaktadır.

## <a name="windows-and-cross-platform-networking-apis"></a>Windows ve platformlar arası ağ API'leri

- [C++REST SDK (kod adı "Casablanca")](https://github.com/Microsoft/cpprestsdk)

  REST Hizmetleri ile etkileşim kurmaya yönelik modern, platformlar arası, zaman uyumsuz bir API sağlar.

  - JSON belgesini ayrıştırmak ve seri hale getirme için yerleşik destek sunan herhangi bir HTTP sunucusu karşı REST çağrılarını gerçekleştirme
  - OAuth 1 ve 2 ' nin yerel bir yeniden yönlendirme dinleyici dahil olmak üzere destekler
  - Uzak Hizmetleri karşı WebSockets bağlantıları oluşturma
  - Tam olarak zaman uyumsuz bir görev gibi yerleşik iş parçacığı havuzu PPL üzerinde temel API

  Windows Masaüstü (7 +), Windows Server (2012 +), Evrensel Windows platformu, Linux, OSX, Android ve iOS destekler.

- [Windows::Web::http::HttpClient](/uwp/api/windows.web.http.httpclient)

  System.Web ad alanında aynı ada sahip bir .NET Framework sınıf üzerinde bir Windows çalışma zamanı HTTP istemci sınıfı modellenir. `HttpClient` tam olarak destekler, zaman uyumsuz indirin ve HTTP ve özel HTTP işleyicilerinin kanala ekleme etkinleştir kanal filtreleri üzerinden yükleyin. Windows SDK, ölçülmüş ağlar, OAuth kimlik doğrulaması ve daha fazlası için örnek filtreler içerir. Kullanmanızı tavsiye ederiz hedefleyen Evrensel Windows platformu uygulamaları için `Windows::Web:HttpClient` sınıfı.

- [Ixmlhttprequest2 arabirimi](/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2)

  HTTP üzerinden Internet'e bağlanmak için Windows çalışma zamanı uygulamaları veya Windows masaüstü uygulamalarında kullanabilirsiniz ve sorunu GET, PUT ve diğer HTTP komutlarını yerel bir COM arabirimi sağlar. Daha fazla bilgi için [izlenecek yol: Görevleri ve XML HTTP isteklerini kullanarak bağlanma](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).

- [Windows Internet (WinINet)](/windows/desktop/WinInet/portal)

  Internet'e bağlanmak için Windows masaüstü uygulamalarında kullanabileceğiniz Windows API.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md) <br/>
[Microsoft Azure C ve C++ Geliştirici Merkezi](https://azure.microsoft.com/develop/cpp/) <br/>
[Ağlara ve web hizmetlerine (UWP)](/windows/uwp/networking/)
