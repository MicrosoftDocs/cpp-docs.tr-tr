---
title: "Bir bağlantı noktası (Visual C++) uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
- connection points [C++], implementing
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab065c78d8ea5d2de105abdc2fa651e05f9d1875
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-a-connection-point-visual-c"></a>Bağlantı Noktasını Uygulama (Visual C++)
Uygulama bağlantı noktası Sihirbazı'nı kullanarak bir bağlantı noktası uygulamak için bir proje ATL COM uygulamanın veya ATL desteği içeren bir MFC uygulaması olarak oluşturmuş olmanız gerekir. Kullanabileceğiniz [ATL Proje Sihirbazı](../atl/reference/atl-project-wizard.md) bir ATL uygulama oluşturmak için veya [ATL nesne MFC uygulamanıza eklemek](../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC uygulaması için ATL desteği uygulamak için.  
  
> [!NOTE]
>  Bağlantı noktaları için bir MFC projesine uygulama hakkında daha fazla bilgi için bkz: [bağlantı noktaları](../mfc/connection-points.md).  
  
 Bir bağlantı noktası uygulama projesi oluşturduktan sonra bir ATL nesne eklemeniz gerekir. Bkz: [nesneleri ekleme ve denetimleri için ATL projesinde](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) nesneleri ATL projenize ekleyin sihirbazları listesi.  
  
> [!NOTE]
>  Sihirbaz ATL iletişim kutuları, ATL Sunucu, performans nesneleri ve performans sayaçları ile oluşturulan XML Web Hizmetleri desteklemiyor.  
  
 Bağlanılabilirlik nesne (diğer bir deyişle, bir kaynak) bir bağlantı noktası her giden arabirimlerinden getirebilir. Her giden arabirimi, bir nesne (diğer bir deyişle, bir havuz) istemci tarafından uygulanabilir. Daha fazla bilgi için bkz: [ATL bağlantı noktaları](../atl/atl-connection-points.md).  
  
### <a name="to-implement-a-connection-point"></a>Bir bağlantı noktası uygulamak için  
  
1.  Sınıf Görünümü'nde ATL nesnesi için sınıf adını sağ tıklatın.  
  
2.  Tıklatın **Ekle** kısayol menüsünden ve ardından **bağlantı noktası ekleme** görüntülemek için [bağlantı noktası Uygulama Sihirbazı](../ide/implement-connection-point-wizard.md).  
  
3.  ' I tıklatın ve uygun tür kitaplıklarından uygulanması için bağlantı noktası arabirimi seçin **son**.  
  
4.  Sınıf Görünümü'nde, her bağlantı noktası için oluşturulan proxy sınıfları inceleyin. Sınıflar CProxy görünür*InterfaceName*\<T > ve türetilmiş [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md).  
  
5.  Bağlantı noktası sınıfı bağlantı noktasının sınıfının tanımını görüntülemek için çift tıklayın.  
  
    -   Kendi projenin arabirimi için bir bağlantı noktası uygularsanız, aşağıdaki tanımını görüntülenir  
  
        ```  
        template< class T >  
        class CProxyInterfaceName :  
           public IConnectionPointImpl< T, &IID_InterfaceName >  
        {  
        public:  
        };  
        ```  
  
         Bir yerel arabirime uygularsanız, yöntemleri ve özellikleri sınıfı gövdesinde yer.  
  
    -   Bir bağlantı noktası başka bir arabirim için uygularsanız, arabirimin yöntem tanımını içerir, her önünde `Fire_`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Bir Nesneye Bağlantı Noktaları Ekleme](../atl/adding-connection-points-to-an-object.md)