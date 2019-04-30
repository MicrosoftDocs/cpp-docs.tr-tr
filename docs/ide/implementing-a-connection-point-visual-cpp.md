---
title: Uygulama bağlantı noktası
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.impl.cp.overview
helpviewer_keywords:
- connection points [C++], implementing
- implement connection point wizard [C++]
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
ms.openlocfilehash: 7afa61246c5251936967e281f7237dc37e5be045
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344258"
---
# <a name="implement-a-connection-point"></a>Uygulama bağlantı noktası

Uygulama bağlantı noktası Sihirbazı'nı kullanarak bir bağlantı noktası uygulamak için bir proje ATL desteği içeren bir MFC uygulaması olarak veya bir ATL COM uygulaması oluşturmuş olmanız gerekir. Kullanabileceğiniz [ATL projesi Sihirbazı](../atl/reference/atl-project-wizard.md) bir ATL uygulama oluşturmak için veya [MFC uygulamanıza bir ATL nesnesi eklemek](../mfc/reference/adding-atl-support-to-your-mfc-project.md) bir MFC uygulaması için ATL desteği uygulamak için.

> [!NOTE]
> Bağlantı noktaları için bir MFC projesine uygulanması hakkında daha fazla bilgi için bkz: [bağlantı noktaları](../mfc/connection-points.md).

Bir bağlantı noktası uygulamak için projeyi oluşturduktan sonra ATL nesneyi eklemeniz gerekir. Bkz: [bir ATL projesine nesne ve denetim ekleme](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) , ATL projesine nesne eklemek sihirbazları listesi.

> [!NOTE]
> ATL iletişim kutuları, ATL Sunucu, performans nesneleri ve performans sayaçları ile oluşturulan XML Web Hizmetleri Sihirbazı'nı desteklemez.

Bağlanılabilirlik bir nesne (diğer bir deyişle, bir kaynak) bir bağlantı noktası her giden arabirimlerinden gösterebilirsiniz. Giden her arabirim bir istemcide bir nesnenin (diğer bir deyişle, bir havuz) tarafından uygulanabilir. Daha fazla bilgi için [ATL bağlantı noktaları](../atl/atl-connection-points.md).

**Bir bağlantı noktası uygulamak için:**

1. Sınıf Görünümü'nde, ATL nesneniz için sınıf adına sağ tıklayın.

1. Seçin **Ekle** kısayol menüsünden seçin **bağlantı noktası Ekle** görüntülenecek [uygulama bağlantı noktası Sihirbazı](#implement-connection-point-wizard).

1. Uygun tür kitaplıklarından uygulamak ve seçmek için bağlantı noktası arabirimleri seçin **son**.

1. Sınıf Görünümü'nde, oluşturulan her bağlantı noktası için proxy sınıfları inceleyin. Sınıflar CProxy görünür*InterfaceName*\<T > ve türetilmiş [Iconnectionpointımpl](../atl/reference/iconnectionpointimpl-class.md).

1. Bağlantı noktası sınıfı bağlantı noktasının sınıfının tanımını görüntülemek için çift tıklayın.

   - Kendi projenin arabirimi için bir bağlantı noktası uygularsanız, aşağıdaki tanımını görünür:

     ```cpp
     template< class T >
     class CProxyInterfaceName :
     public IConnectionPointImpl< T, &IID_InterfaceName >
     {
     public:
     };
     ```

   - Bir yerel arabirime uygularsanız, yöntemleri ve özellikleri sınıf gövdesine görünür.

   - Başka bir arabirim için bir bağlantı noktası uygularsanız, arabirimin yöntemlerinin tanımı içerir, her önüne `Fire_`.

## <a name="in-this-section"></a>Bu bölümde

- [Bağlantı noktası Uygulama Sihirbazı](#implement-connection-point-wizard)

## <a name="implement-connection-point-wizard"></a>Bağlantı noktası Uygulama Sihirbazı

Bu sihirbaz bir COM nesnesi için bir bağlantı noktası uygular. Bağlanılabilirlik bir nesne (diğer bir deyişle, bir kaynak) bir bağlantı noktası kendi arabirimleri veya herhangi bir giden arabirimi gösterebilirsiniz. Visual C++ hem de Windows giden arabirimlere sahip tür kitaplıkları sağlar. Giden her arabirim bir istemcide bir nesnenin (diğer bir deyişle, bir havuz) tarafından uygulanabilir.

Daha fazla bilgi için [ATL bağlantı noktaları](../atl/atl-connection-points.md).

- **Kullanılabilir tür kitaplıkları**

  Bağlantı noktaları uygulayabileceğiniz Arabirim tanımları bulunduran kullanılabilir tür kitaplıklarını görüntüler. Tür kitaplığı olan bir dosyayı bulmak için üç nokta düğmesini seçin.

- **Konum**

  Şu anda seçilen tür kitaplığının konumu görüntüler **kullanılabilir tür kitaplıklarını** listesi.

- **Arabirimler**

  Görüntüler, tanımları, tür kitaplığındaki şu anda seçili tutulur arabirimleri **kullanılabilir tür kitaplıklarını** kutusu.

  |Aktarım düğmesi|Açıklama|
  |---------------------|-----------------|
  |**>**|Ekler **uygulamak bağlantı noktaları** geçerli seçili arabirim adı listesi **arabirimleri** listesi.|
  |**>>**|Ekler **uygulamak bağlantı noktaları** bulunan tüm arabirimi adlarını listelemek **arabirimleri** listesi.|
  |**\<**|Şu anda seçili arabirim adını kaldırır **uygulamak bağlantı noktaları** listesi.|
  |**\<\<**|Şu anda listelenen adları tüm arabirim kaldırır **uygulamak bağlantı noktaları** listesi.|

- **Uygulama bağlantı noktaları**

  Kendisi için uygulamanız bağlantı noktaları seçtiğinizde arabirimleri adlarını görüntüler **son**.
