---
description: Seçenekler, ATL Active Server sayfa bileşeni Sihirbazı hakkında daha fazla bilgi edinin
title: Seçenekler, ATL Active Server sayfa bileşeni Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.options
helpviewer_keywords:
- ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
ms.openlocfilehash: 6d41b5cb43aa9f0445e73bbe148a2a753e374a15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139028"
---
# <a name="options-atl-active-server-page-component-wizard"></a>Seçenekler, ATL Active Server sayfa bileşeni Sihirbazı

Nesne için daha fazla verimlilik ve hata desteğini tasarlamak üzere ATL Active Server Page Bileşen Sihirbazı 'nın bu sayfasını kullanın.

ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz. [atl com Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).

- **İş parçacığı modeli**

   İş parçacıklarını yönetme yöntemini gösterir. Varsayılan olarak, proje **apartman** iş parçacığı kullanır.

   Daha fazla bilgi için bkz. [projenin Iş parçacığı modelini belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) .

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Tek**|Nesnenin tek iş parçacığı modelini kullandığını belirtir. Tek iş parçacığı modelinde, bir nesne her zaman birincil COM iş parçacığında çalışır. Daha fazla bilgi için bkz. [tek Iş parçacıklı Apartments](/windows/win32/com/single-threaded-apartments) ve [ınprocserver32](/windows/win32/com/inprocserver32) .|
   |**Yapı**|Nesnenin apartman iş parçacığı kullandığını belirtir. Tek iş parçacığı grubu ile eşdeğerdir. Bir apartman iş parçacıklı bileşenin her nesnesine, nesne ömrü boyunca iş parçacığı için bir grup atanır; Ancak birden çok nesne için birden çok iş parçacığı kullanılabilir. Her grup belirli bir iş parçacığına bağlanır ve bir Windows ileti göndericisi (varsayılan) vardır.<br /><br /> Daha fazla bilgi için bkz. [tek Iş parçacıklı apartmanlar](/windows/win32/com/single-threaded-apartments) .|
   |**Her ikisi**|Nesnenin, oluşturduğu iş parçacığı türünden bağımsız olarak Apartment veya Free iş parçacığı kullanıp kullanbileceğini belirtir.|
   |**Ücretsiz**|Nesnenin serbest iş parçacığı kullandığını belirtir. Ücretsiz iş parçacığı, bir çoklu iş parçacığı grubu modeliyle eşdeğerdir. Daha fazla bilgi için bkz. [Çoklu Iş parçacıklı Apartments](/windows/win32/com/multithreaded-apartments) .|
   |**Kültür**|Nesnenin çok iş parçacıklı apartmanlar için yönergeleri takip eder, ancak her türlü iş parçacığı üzerinde yürütebileceğini belirtir.|

- **Toplama**

   Nesnenin [toplamayı](/windows/win32/com/aggregation)kullanıp kullanmadığını belirtir. Toplama nesnesi, istemcilere hangi arabirimlerin sunumasını seçer ve arabirimler toplama nesnesi tarafından uygulandıkları gibi gösterilir. Toplama nesnesinin istemcileri yalnızca toplama nesnesiyle iletişim kurar.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Evet**|Nesnenin toplanabilecek olduğunu belirtir. Varsayılan.|
   |**Hayır**|Nesnenin toplanmadığını belirtir.|
   |**Yalnızca**|Nesnenin toplanması gerektiğini belirtir.|

- **Destek**

   Ek destek seçenekleri:

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Iupporterrorınfo**|, Nesnenin istemciye hata bilgilerini döndürebilmesi için [ıupporterrorınfo](../../atl/reference/isupporterrorinfoimpl-class.md) arabirimi için destek oluşturur.|
   |**Bağlantı noktaları**|, Nesnenizin sınıfının [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)'den türemesini sağlayarak nesneniz için bağlantı noktalarını mümkün hale getirir.|
   |**Serbest iş parçacıklı Sıralayıcı**|Aynı işlemdeki iş parçacıkları arasında arabirim işaretçilerini etkili bir şekilde sıralamak için serbest iş parçacıklı Sıralayıcı nesnesi oluşturur. İş parçacığı modeli olarak **hem hem de** **boş** olan nesne için kullanılabilir.|

## <a name="see-also"></a>Ayrıca bkz.

[ATL Active Server Page Bileşeni Sihirbazı](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server sayfa bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)
