---
title: Bulut ve Web programlama Visual C++'ta | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-azure
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2553ac5cdc20f3d5d38a6bad77dc79fc7c1737d8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052888"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Visual C++'da Bulut ve Web Programlama

C++'da, web ve buluta bağlamak için birkaç seçeneğiniz vardır.

## <a name="cloud-programming-options"></a>Bulut programlama seçenekleri

- [Windows Azure mobil hizmetler](http://www.windowsazure.com/develop/mobile/)

   Windows Azure mobil Hizmetler'e bağlanmak için evrensel Windows Platformu (UWP) uygulamaları veya Windows masaüstü uygulamalarında kullanabileceğiniz yerel API'ler sağlar. Web sitesindeki örneklerin çoğu C# ' de olsa da, C++ de kullanabilirsiniz. Daha fazla bilgi için [hızlı başlangıç: C++ kullanarak mobil hizmet ekleme](https://msdn.microsoft.com/library/windows/apps/dn263181.aspx).

- [C++ için Microsoft Azure depolama istemci kitaplığı](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)

   C++ için Azure depolama istemci kitaplığı, ancak bunlarla sınırlı olmamak aşağıdaki yetenekleri dahil olmak üzere Azure depolama ile çalışmak için kapsamlı bir API sağlar:

  - Oluşturma, okuma, silme ve blob kapsayıcıları, tabloları ve kuyrukları listeler.
  - Oluşturma, okuma, silme, liste ve kopyalama BLOB artı okuyup blob'u aralıklarını yazabilir.
  - Ekle, Sil, Değiştir, birleştirme ve bir Azure tablosu varlıkları sorgulayın.
  - Sıraya alma ve bir Azure kuyruğundaki iletileri sıradan çıkarma.
  - Kapsayıcıları, blobları, tablolar ve Kuyruklar gevşek listelemek ve gevşek varlıkları sorgulama

- [OneDrive API](https://dev.onedrive.com/README.htm)

   OneDrive API uygulamanızı dosyalara ve klasörlere Office 365 ve SharePoint Server 2016'ya bağlanmak için HTTP Hizmetleri sunmaktadır.

- [C++ REST SDK (Codename "Kazablanka")](https://github.com/Microsoft/cpprestsdk)

   REST Hizmetleri ile etkileşim kurmaya yönelik modern, platformlar arası, zaman uyumsuz bir API sağlar.

  - JSON belgesini ayrıştırmak ve seri hale getirme için yerleşik destek sunan herhangi bir HTTP sunucusu karşı REST çağrılarını gerçekleştirme
  - OAuth 1 ve 2 ' nin yerel bir yeniden yönlendirme dinleyici dahil olmak üzere destekler
  - Uzak Hizmetleri karşı Websockets bağlantıları oluşturma
  - Tam olarak zaman uyumsuz bir görev gibi yerleşik iş parçacığı havuzu PPL üzerinde temel API

   Windows Masaüstü (7 +), Windows Server (2012 +), Evrensel Windows platformu, Linux, OSX, Android ve iOS destekler.

- [Windows::Web::http::HttpClient](https://msdn.microsoft.com/library/windows/apps/windows.web.http.httpclient.aspx)

   System.Web ad alanında aynı ada sahip bir .NET Framework sınıf üzerinde bir Windows çalışma zamanı HTTP istemci sınıfı modellenir. `HttpClient` tam olarak destekler, zaman uyumsuz indirin ve HTTP ve özel HTTP işleyicilerinin kanala ekleme etkinleştir kanal filtreleri üzerinden yükleyin. Windows SDK, ölçülmüş ağlar, OAuth kimlik doğrulaması ve daha fazlası için örnek filtreler içerir. Kullanmanızı tavsiye ederiz hedefleyen Evrensel Windows platformu uygulamaları için `Windows::Web:HttpClient` sınıfı.

- [Ixmlhttprequest2 arabirimi](/previous-versions/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2)

   HTTP üzerinden Internet'e bağlanmak için Windows çalışma zamanı uygulamaları veya Windows masaüstü uygulamalarında kullanabilirsiniz ve sorunu GET, PUT ve diğer HTTP komutlarını yerel bir COM arabirimi sağlar. Daha fazla bilgi için [izlenecek yol: görevleri kullanarak bağlanma ve XML HTTP isteklerini](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).

- [Windows Internet (WinINet)](/windows/desktop/WinInet/portal)

   Internet'e bağlanmak için Windows masaüstü uygulamalarında kullanabileceğiniz Windows API.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++](../visual-cpp-in-visual-studio.md) <br/>
[Ağlara ve web Hizmetleri](/windows/uwp/networking/)
