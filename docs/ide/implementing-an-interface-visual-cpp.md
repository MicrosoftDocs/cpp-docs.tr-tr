---
description: 'Hakkında daha fazla bilgi edinin: arabirim uygulama'
title: Arabirim uygulama
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.impl.interface.overview
helpviewer_keywords:
- interfaces, implementing
- implement interface wizard [C++]
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
ms.openlocfilehash: 202471577ec72f4cc28fa5cdceb3566d60e04653
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313222"
---
# <a name="implement-an-interface"></a>Arabirim uygulama

Bir arabirim uygulamak için ATL COM uygulaması veya ATL desteği içeren MFC uygulaması olarak bir proje oluşturmuş olmanız gerekir. Atl uygulaması oluşturmak için ATL [Proje Sihirbazı 'nı](../atl/reference/atl-project-wizard.md) kullanabilir veya bir MFC UYGULAMASı için ATL desteği uygulamak üzere [MFC uygulamanıza ATL nesnesi ekleyebilirsiniz](../mfc/reference/adding-atl-support-to-your-mfc-project.md) .

Projeyi oluşturduktan sonra bir arabirim uygulamak için önce bir ATL nesnesi eklemeniz gerekir. ATL projenize nesne ekleyen sihirbazların bir listesi için bkz. [ATL projesine nesne ve denetim ekleme](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) .

> [!NOTE]
> Sihirbaz, atl iletişim kutularını, ATL, performans nesnelerini veya performans sayaçlarını kullanan XML Web hizmetlerini desteklemez.

[ATL denetimi eklerseniz](../atl/reference/adding-an-atl-control.md), varsayılan arabirimlerin uygulanıp yapılmayacağını belirtebilirsiniz. Varsayılan arabirimler, sihirbazın [arabirimler](../atl/reference/interfaces-atl-control-wizard.md) sayfasında listelenir ve atlcom. h içinde tanımlanır.

Nesneyi veya denetimi ekledikten sonra, arabirim uygulama Sihirbazı ' nı kullanarak kullanılabilir herhangi bir tür kitaplığında bulunan diğer arayüzleri uygulayabilirsiniz.

Yeni bir arabirim ekliyorsanız, bunu projenin. IDL dosyasına el ile eklemeniz gerekir. Daha fazla bilgi için bkz. [atl projesinde yeni arabirim ekleme](../atl/reference/adding-a-new-interface-in-an-atl-project.md).

**Bir arabirim uygulamak için:**

1. Sınıf Görünümü, ATL nesneniz için sınıf adına sağ tıklayın.

1. Kısayol menüsünden **Ekle** ' yi seçin ve arabirim [Uygulama sihirbazını](#implement-interface-wizard)göstermek için **arabirimi Uygula** ' yı seçin.

1. Uygun tür kitaplıklarından uygulanacak arabirimleri seçin ve **son**' u seçin.

1. Sınıf Görünümü, uyguladığınız arabirimi görmek için nesnenin temelleri ve arabirimler düğümünü genişletin. Ardından, kullanılabilir özellikleri, yöntemleri ve olayları görmek için arabirimin düğümünü genişletin.

   > [!NOTE]
   > Ayrıca, arabirimin üyelerini incelemek için [nesne tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code) ' nı da kullanabilirsiniz.

## <a name="in-this-section"></a>Bu bölümde

- [Arabirim uygulama Sihirbazı](#implement-interface-wizard)

## <a name="implement-interface-wizard"></a>Arabirim uygulama Sihirbazı

Bu sihirbaz bir COM nesnesi için bir arabirim uygular. Birçok arabirimin uygulamaları, Visual Studio ve Windows ile kullanılabilen COM kitaplıklarına dahildir. Bir nesne örneği oluşturulduğunda bir arabirim uygulama bir nesneyle ilişkilendirilir. Ayrıca, nesnenin sunduğu hizmetleri de sağlar.

Arabirimler ve uygulamalar ile ilgili bir tartışma için, Windows SDK içindeki [arabirimler ve arabirim uygulamaları](/windows/win32/com/interfaces-and-interface-implementations) bölümüne bakın.

- **Arabirimi uygulama**

  Arabirimin oluşturulduğu tür kitaplığının konumunu belirtir.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Project**|Tür kitaplığı projenin bir parçasıdır.|
  |**Kapsayıcı Kayıt Defteri**|Tür kitaplığı sisteme kaydedilir. Kayıtlı tür kitaplıkları **kullanılabilir tür kitaplıklarında** listelenmiştir.|
  |**Dosya**|Tür kitaplığı sistemde kayıtlı değildir, ancak bir dosyada tutulur. Dosya konumunu **konuma** girin.|

- **Kullanılabilir tür kitaplıkları**

  Uygulayabileceğiniz arabirim tanımlarını tutan kullanılabilir tür kitaplıklarını görüntüler. **Arabirim uygulama** altındaki **Dosya** ' yı seçerseniz, bu kutu değişiklik için kullanılamaz.

- **Konum**

  **Kullanılabilir tür kitaplıkları** listesinde şu anda seçili olan tür kitaplığının konumunu görüntüler. **Arabirim Uygula** altında **Dosya** ' yı seçtiyseniz, kullanılacak tür kitaplığını tutan bir dosyayı bulmak için üç nokta düğmesini seçin.

- **Arabirimler**

  Tanımları, **kullanılabilir tür kitaplıkları** kutusunda şu anda seçili olan tür kitaplığında tutulmuş olan arabirimleri görüntüler.

  > [!NOTE]
  > Seçilen nesne tarafından zaten uygulanmış olanlarla aynı ada sahip arabirimler, **arabirimler** kutusunda görüntülenmez.

  |Aktar düğmesi|Açıklama|
  |---------------------|-----------------|
  |**>**|**Arabirimler** listesinde şu anda seçili olan arabirim adını **Uygula arabirimleri** listesine ekler.|
  |**>>**|**Arabirimler** listesinde bulunan tüm arabirim adlarını **Uygula arabirimleri** listesine ekler.|
  |**\<**|**Arabirimleri Uygula** listesinde şu anda seçili olan arabirim adını kaldırır.|
  |**\<\<**|**Arabirimleri Uygula** listesinde şu anda listelenen tüm arabirim adlarını kaldırır.|

- **Arabirimleri Uygula**

  Nesneniz üzerinde uygulamak üzere seçtiğiniz arabirimlerin adlarını görüntüler.

  > [!NOTE]
  > Öğesinden türetilen birden fazla arabirim varsa `IDispatch` veya sınıfınıza zaten başka bir arabirimden türetilmiş bir arabirim uygulamaya çalışırsanız, COM_MAP girdilerini kesinleştirmeniz gerekir. Daha fazla bilgi için bkz. [COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2).
