---
description: 'Daha fazla bilgi edinin: bağlantı noktası uygulama'
title: Bağlantı noktası uygulama
ms.date: 05/14/2019
helpviewer_keywords:
- connection points [C++], implementing
- implement connection point wizard [C++]
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
ms.openlocfilehash: bee04d28036ca5a2dfb0f4913adf39f1fdcca565
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281164"
---
# <a name="implement-a-connection-point"></a>Bağlantı noktası uygulama

Bağlantı noktası uygulama Sihirbazı 'Nı kullanarak bir bağlantı noktası uygulamak için, ATL COM uygulaması veya ATL desteği içeren bir MFC uygulaması olarak bir proje oluşturmuş olmanız gerekir. Atl uygulaması oluşturmak için ATL [Proje Sihirbazı 'nı](../atl/reference/atl-project-wizard.md) kullanabilir veya bir MFC UYGULAMASı için ATL desteği uygulamak üzere [MFC uygulamanıza ATL nesnesi ekleyebilirsiniz](../mfc/reference/adding-atl-support-to-your-mfc-project.md) .

> [!NOTE]
> Bir MFC projesine yönelik bağlantı noktalarını uygulama hakkında daha fazla bilgi için bkz. [bağlantı noktaları](../mfc/connection-points.md).

Projeyi oluşturduktan sonra bir bağlantı noktası uygulamak için, önce bir ATL nesnesi eklemeniz gerekir. ATL projenize nesne ekleyen sihirbazların bir listesi için bkz. [ATL projesine nesne ve denetim ekleme](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) .

> [!NOTE]
> Sihirbaz, atl iletişim kutularını, ATL sunucusu ile oluşturulan XML Web hizmetlerini, performans nesnelerini veya performans sayaçlarını desteklemez.

Bağlanılabilir bir nesne (yani bir kaynak) giden arabirimlerinden her biri için bir bağlantı noktası gösterebilir. Her giden arabirim bir nesne (yani bir havuz) üzerinde bir istemci tarafından uygulanabilir. Daha fazla bilgi için bkz. [atl bağlantı noktaları](../atl/atl-connection-points.md).

**Bir bağlantı noktası uygulamak için:**

1. Sınıf Görünümü, ATL nesneniz için sınıf adına sağ tıklayın.

1. Kısayol menüsünden **Ekle** ' yi ve ardından bağlantı **noktası Ekle** ' yi seçerek [bağlantı noktası uygulama Sihirbazı 'nı](#implement-connection-point-wizard)görüntüleyin.

1. Uygun tür kitaplıklarından uygulanacak bağlantı noktası arabirimlerini seçin ve **son**' u seçin.

1. Sınıf Görünümü, her bağlantı noktası için oluşturulan proxy sınıflarını inceleyin. Sınıflar, CProxy *InterfaceName* olarak görünür \<T> ve [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md)'den türetilir.

1. Bağlantı noktası sınıfının tanımını göstermek için bağlantı noktası sınıfına çift tıklayın.

   - Kendi projenizin arabirimi için bir bağlantı noktası uygularsanız, aşağıdaki tanım görüntülenir:

     ```cpp
     template< class T >
     class CProxyInterfaceName :
     public IConnectionPointImpl< T, &IID_InterfaceName >
     {
     public:
     };
     ```

   - Yerel bir arabirim uygularsanız, sınıf gövdesinde Yöntemler ve özellikler görünür.

   - Başka bir arabirim için bir bağlantı noktası uygularsanız, tanım, her biri tarafından önünde olan arabirimin yöntemlerini içerir `Fire_` .

## <a name="in-this-section"></a>Bu bölümde

- [Bağlantı noktası uygulama Sihirbazı](#implement-connection-point-wizard)

## <a name="implement-connection-point-wizard"></a>Bağlantı noktası uygulama Sihirbazı

Bu sihirbaz bir COM nesnesi için bağlantı noktası uygular. Bağlanılabilir bir nesne (yani bir kaynak) kendi arabirimleri veya herhangi bir giden arabirim için bir bağlantı noktası gösterebilir. MSVC ve Windows, her ikisi de giden arabirimleri olan tür kitaplıkları sağlar. Her giden arabirim bir nesne (yani bir havuz) üzerinde bir istemci tarafından uygulanabilir.

Daha fazla bilgi için bkz. [atl bağlantı noktaları](../atl/atl-connection-points.md).

- **Kullanılabilir tür kitaplıkları**

  Bağlantı noktalarını uygulayabileceğiniz arabirim tanımlarını tutan kullanılabilir tür kitaplıklarını görüntüler. Kullanılacak tür kitaplığını içeren bir dosyayı bulmak için üç nokta düğmesini seçin.

- **Konum**

  **Kullanılabilir tür kitaplıkları** listesinde şu anda seçili olan tür kitaplığının konumunu görüntüler.

- **Arabirimler**

  Tanımları, **kullanılabilir tür kitaplıkları** kutusunda şu anda seçili olan tür kitaplığında tutulmuş olan arabirimleri görüntüler.

  |Aktar düğmesi|Açıklama|
  |---------------------|-----------------|
  |**>**|, **Arabirimler** listesinde seçili olan arabirim adını **bağlantı noktalarına uygula** listesine ekler.|
  |**>>**|**Arabirim listesindeki kullanılabilir** tüm arabirim adlarını, **bağlantı noktalarını Uygula** listesine ekler.|
  |**\<**|**Bağlantı noktalarını Uygula** listesinde seçili olan arabirim adını kaldırır.|
  |**\<\<**|**Bağlantı noktalarını Uygula** listesinde şu anda listelenen tüm arabirim adlarını kaldırır.|

- **Bağlantı noktalarını Uygula**

  **Son**' u seçtiğinizde bağlantı noktalarını uyguladığınız arabirimlerin adlarını görüntüler.
