---
title: ATL Active Server Page Bileşeni Ekleme
ms.date: 05/09/2019
ms.assetid: 7be2204c-6e58-4099-8892-001b848c8987
ms.openlocfilehash: 08d49baa547342843b525f871de9570d4e752068
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921171"
---
# <a name="adding-an-atl-active-server-page-component"></a>ATL Active Server Page Bileşeni Ekleme

::: moniker range="msvc-160"

ATL Active Server Pages Bileşen Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

Projenize bir etkin şablon kitaplığı (ATL) nesnesi eklemek için projenizin bir ATL COM uygulaması veya ATL desteği içeren bir MFC uygulaması olarak oluşturulmuş olması gerekir. ATL [Projesi Sihirbazı](../../atl/reference/atl-project-wizard.md) ' nı atl uygulaması oluşturmak için kullanabilirsiniz, [Sınıf Ekle iletişim](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) kutusundan **MFC 'ye atl desteği ekle** ' yi SEÇEBILIR veya bir MFC UYGULAMASı için ATL desteği uygulamak üzere [MFC uygulamanıza ATL nesnesi ekleyebilirsiniz](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) .

Active Server Pages bileşenleri, aşağıdaki gelişmiş web geliştirme özelliklerini sağlayan Internet Information Services mimarisinin bir parçasıdır:

- Dinamik, tarayıcıdan bağımsız içerik oluşturmak için ASP bileşenlerini HTML sayfalarınıza ekleyebilirsiniz.

- Standart tabanlı veritabanı bağlantısı sağlamak için ASP sayfalarını kullanabilirsiniz.

- Web tabanlı uygulamalarınız için ASP hata işleme özelliklerini kullanabilirsiniz.

## <a name="to-add-an-atl-active-server-pages-component-to-your-project"></a>Projenize ATL Active Server Pages bileşeni eklemek için

1. **Çözüm GEZGINI** atl Active Server Pages bileşenini eklemek istediğiniz projenin adına sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Sınıf Ekle** ' ye tıklayın.

1. [Sınıf Ekle](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) Iletişim kutusundaki **Şablonlar** bölmesinde, **atl Active Server sayfa bileşeni** ' ne tıklayın ve sonra [atl Active Server sayfa bileşeni sihirbazını](../../atl/reference/atl-active-server-page-component-wizard.md)göstermek için **Aç** ' a tıklayın.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[ATL Projesine Yeni Arabirim Ekleme](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)<br/>
[Bir nesneye bağlantı noktaları ekleme](../../atl/adding-connection-points-to-an-object.md)<br/>
[Yöntem ekleme](../../ide/adding-a-method-visual-cpp.md)<br/>
[MFC Sınıfı](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Genel C++ Sınıfı Ekleme](../../ide/adding-a-generic-cpp-class.md)
