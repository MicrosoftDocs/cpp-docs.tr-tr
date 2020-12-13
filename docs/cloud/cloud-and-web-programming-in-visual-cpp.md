---
description: 'Daha fazla bilgi edinin: Visual C++ bulut ve Web programlama'
title: Visual C++'da Bulut ve Web Programlama
ms.date: 05/14/2019
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
ms.topic: overview
ms.openlocfilehash: 3d845ea89507440c07747314c24ff01bd848cf37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151625"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Visual C++'da Bulut ve Web Programlama

C++ ' da, Web ve buluta bağlanmak için çeşitli seçenekleriniz vardır.

## <a name="microsoft-azure-sdks-and-rest-services"></a>SDK 'Ları ve REST hizmetlerini Microsoft Azure

- [C++ için Microsoft Azure Depolama Istemci kitaplığı](https://azure.github.io/azure-storage-cpp/)

  C++ için Azure Storage Istemci kitaplığı, aşağıdaki yetenekler dahil ancak bunlarla sınırlı olmamak üzere Azure Storage ile çalışmaya yönelik kapsamlı bir API sağlar:

  - Blob kapsayıcıları, tabloları ve kuyrukları oluşturun, okuyun, silin ve listeleyin.
  - Blob oluşturma, okuma, silme, listeleme ve kopyalama ile blob aralıklarını okuma ve yazma.
  - Azure tablosundaki varlıkları ekleme, silme, değiştirme, birleştirme ve sorgu oluşturma.
  - Bir Azure kuyruğundaki iletileri kuyruğa alma ve sıradan çıkarma.
  - Geç liste kapsayıcıları, Bloblar, tablolar ve kuyruklar ve geç sorgu varlıkları

- Nesnelerin İnterneti için ANSI C99 [Azure IoT Hub SDK 'ları](/azure/iot-hub/iot-hub-devguide-sdks) , IoT uygulamalarının cihazda veya arka uçta çalışmasını sağlar.

- [OneDrive ve SharePoint Microsoft Graph](https://dev.onedrive.com/README.htm)

  OneDrive API, uygulamanızı Microsoft 365 ve SharePoint Server 2016 ' deki dosyalara ve klasörlere bağlamak için bir dizi HTTP hizmeti sağlar.

## <a name="windows-and-cross-platform-networking-apis"></a>Windows ve platformlar arası ağ API 'Leri

- [C++ REST SDK (kod adı "Casablanca")](https://github.com/Microsoft/cpprestsdk)

  REST hizmetleriyle etkileşim kurmak için modern, platformlar arası, zaman uyumsuz bir API sağlar.

  - JSON belgesi ayrıştırma ve serileştirme için yerleşik destek ile herhangi bir HTTP sunucusunda REST çağrıları gerçekleştirin
  - Yerel yeniden yönlendirme dinleyicisi dahil olmak üzere OAuth 1 ve 2 ' yi destekler
  - Uzak hizmetlere karşı WebSockets bağlantıları yapın
  - Yerleşik bir iş parçacığı havuzu dahil olmak üzere PPL tabanlı tam bir zaman uyumsuz görev API 'SI

  Windows Masaüstü (7 +), Windows Server (2012 +), Evrensel Windows Platformu, Linux, OSX, Android ve iOS 'yi destekler.

- [Windows:: Web:: http:: HttpClient](/uwp/api/windows.web.http.httpclient)

  System. Web ad alanındaki aynı ada sahip .NET Framework sınıfında modellenen bir Windows Çalışma Zamanı HTTP istemci sınıfı. `HttpClient` , HTTP üzerinden zaman uyumsuz karşıya yükleme ve indirmeyi ve özel HTTP işleyicilerinin ardışık düzene eklenmesini sağlayan işlem hattı filtrelerini tam olarak destekler. Windows SDK tarifeli ağlar, OAuth kimlik doğrulaması ve daha fazlası için örnek filtreler içerir. Yalnızca Evrensel Windows Platformu hedefleyen uygulamalar için sınıfını kullanmanızı öneririz `Windows::Web:HttpClient` .

- [IXMLHTTPRequest2 arabirimi](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2)

  HTTP üzerinden Internet 'e bağlanmak ve GET, PUT ve diğer HTTP komutlarını vermek için Windows Çalışma Zamanı uygulamalarında veya Windows masaüstü uygulamalarında kullanabileceğiniz yerel bir COM arabirimi sağlar. Daha fazla bilgi için bkz. [Izlenecek yol: görevleri ve XML http Isteklerini kullanarak bağlanma](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).

- [Windows Internet (WinInet)](/windows/win32/WinInet/portal)

  Windows masaüstü uygulamalarında Internet 'e bağlanmak için kullanabileceğiniz Windows API 'SI.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md) <br/>
[Microsoft Azure C ve C++ Geliştirici Merkezi](https://azure.microsoft.com/develop/cpp/) <br/>
[Ağlar ve Web Hizmetleri (UWP)](/windows/uwp/networking/)
