---
title: Bağlantı Noktasını Uygulama (Visual C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
- connection points [C++], implementing
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
ms.openlocfilehash: 45e3dfcfc7e7bcb9fcbe14e08a8c238fe9bec5a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568330"
---
# <a name="implementing-a-connection-point-visual-c"></a>Bağlantı Noktasını Uygulama (Visual C++)

Uygulama bağlantı noktası Sihirbazı'nı kullanarak bir bağlantı noktası uygulamak için bir proje ATL desteği içeren bir MFC uygulaması olarak veya bir ATL COM uygulaması oluşturmuş olmanız gerekir. Kullanabileceğiniz [ATL projesi Sihirbazı](../atl/reference/atl-project-wizard.md) bir ATL uygulama oluşturmak için veya [MFC uygulamanıza bir ATL nesnesi eklemek](../mfc/reference/adding-atl-support-to-your-mfc-project.md) bir MFC uygulaması için ATL desteği uygulamak için.

> [!NOTE]
>  Bağlantı noktaları için bir MFC projesine uygulanması hakkında daha fazla bilgi için bkz: [bağlantı noktaları](../mfc/connection-points.md).

Bir bağlantı noktası uygulamak için projeyi oluşturduktan sonra ATL nesneyi eklemeniz gerekir. Bkz [nesneler ekleme ve denetimleri için ATL projesinde](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) , ATL projesine nesne eklemek sihirbazları listesi.

> [!NOTE]
>  ATL iletişim kutuları, ATL Sunucu, performans nesneleri ve performans sayaçları ile oluşturulan XML Web Hizmetleri Sihirbazı'nı desteklemez.

Bağlanılabilirlik bir nesne (diğer bir deyişle, bir kaynak), her giden arabirimlerinden biri için bir bağlantı noktası kullanıma sunabilirsiniz. Giden her arabirim bir istemcide bir nesnenin (diğer bir deyişle, bir havuz) tarafından uygulanabilir. Daha fazla bilgi için [ATL bağlantı noktaları](../atl/atl-connection-points.md).

### <a name="to-implement-a-connection-point"></a>Bir bağlantı noktası uygulamak için

1. Sınıf Görünümü'nde, ATL nesneniz için sınıf adına sağ tıklayın.

1. Tıklayın **Ekle** kısayol menüsünü ve ardından **bağlantı noktası Ekle** görüntülenecek [bağlantı noktası Uygulama Sihirbazı](../ide/implement-connection-point-wizard.md).

1. Uygun tür kitaplıklarından uygulamak ve bağlantı noktası arabirimleri seçin **son**.

1. Sınıf Görünümü'nde, oluşturulan her bağlantı noktası için proxy sınıfları inceleyin. Sınıflar CProxy görünür*InterfaceName*\<T > ve türetilmiş [Iconnectionpointımpl](../atl/reference/iconnectionpointimpl-class.md).

1. Bağlantı noktası sınıfı bağlantı noktasının sınıfının tanımını görüntülemek için çift tıklayın.

   - Kendi projenin arabirimi için bir bağlantı noktası uygularsanız, aşağıdaki tanımını görünür.

        ```
        template< class T >
        class CProxyInterfaceName :
           public IConnectionPointImpl< T, &IID_InterfaceName >
        {
        public:
        };
        ```

         If you implement a local interface, methods and properties appear in the class body.

   - Başka bir arabirim için bir bağlantı noktası uygularsanız, arabirimin yöntemlerinin tanımı içerir, her önüne `Fire_`.

## <a name="see-also"></a>Ayrıca Bkz.

[Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[Bir Nesneye Bağlantı Noktaları Ekleme](../atl/adding-connection-points-to-an-object.md)