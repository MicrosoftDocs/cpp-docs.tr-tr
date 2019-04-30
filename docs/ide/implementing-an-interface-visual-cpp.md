---
title: Arabirim uygulama
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.impl.interface.overview
helpviewer_keywords:
- interfaces, implementing
- implement interface wizard [C++]
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
ms.openlocfilehash: 8e166f806d247cd93ff0f471360d749fa95e430b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375905"
---
# <a name="implement-an-interface"></a>Arabirim uygulama

Bir arabirim uygulamak için bir projenin ATL desteği içeren bir MFC uygulaması olarak veya bir ATL COM uygulaması oluşturmuş olmanız gerekir. Kullanabileceğiniz [ATL projesi Sihirbazı](../atl/reference/atl-project-wizard.md) bir ATL uygulama oluşturmak için veya [MFC uygulamanıza bir ATL nesnesi eklemek](../mfc/reference/adding-atl-support-to-your-mfc-project.md) bir MFC uygulaması için ATL desteği uygulamak için.

Bir arabirim uygulamak için projeyi oluşturduktan sonra ATL nesneyi eklemeniz gerekir. Bkz: [bir ATL projesine nesne ve denetim ekleme](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) , ATL projesine nesne eklemek sihirbazları listesi.

> [!NOTE]
> ATL iletişim kutusu, ATL, performans nesneleri ve performans sayaçlarını kullanarak XML Web Hizmetleri Sihirbazı'nı desteklemez.

Varsa, [ATL denetimi ekleme](../atl/reference/adding-an-atl-control.md), varsayılan arabirimlerini belirtebilirsiniz. Varsayılan arabirimleri listelenir [arabirimleri](../atl/reference/interfaces-atl-control-wizard.md) sayfasında, Sihirbazı ve atlcom.h içinde tanımlanmış.

Nesne veya denetimi ekledikten sonra arabirim Uygulama Sihirbazı'nı kullanarak tüm kullanılabilir tür kitaplığında bulunan, diğer arabirim uygulayabilir.

Yeni bir arabirim ekliyorsanız, bu projenin .idl dosyasına el ile eklemelisiniz. Daha fazla bilgi için [ATL projesine yeni arabirim ekleme](../atl/reference/adding-a-new-interface-in-an-atl-project.md).

**Bir arabirim uygulamak için:**

1. Sınıf Görünümü'nde, ATL nesneniz için sınıf adına sağ tıklayın.

1. Seçin **Ekle** kısayol menüsünden seçin **arabirimi uygulayan** görüntülenecek [uygulama Arabirimi Sihirbazı](#implement-interface-wizard).

1. Uygun tür kitaplıklarından uygulamak ve arabirimleri seçin **son**.

1. Sınıf Görünümü'nde, nesnenin tabanları genişletin ve arabirimleri düğüm uygulanan arabirimi görmek için. Kullanılabilir özellikler, yöntemlerini ve olaylarını görmek için arabirimin düğümünü genişletin.

   > [!NOTE]
   > Ayrıca [Nesne Tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code) arabirimin üyelerini incelemek için.

## <a name="in-this-section"></a>Bu bölümde

- [Arabirim Uygulama Sihirbazı](#implement-interface-wizard)

## <a name="implement-interface-wizard"></a>Arabirim Uygulama Sihirbazı

Bu sihirbaz bir COM nesnesi için bir arabirim uygular. Pek çok arabirimi uygulamalarını Visual Studio ve Windows ile kullanılabilir COM kitaplıkları dahil edilmiştir. O nesnenin bir örneği oluşturulduğunda bir arabirim uygulaması bir nesne ile ilişkilidir. Ayrıca, nesnenin sunduğu hizmetleri sağlar.

Arabirimleri ve uygulamalar için bkz [arabirimleri ve arabirim uygulamalarına](/windows/desktop/com/interfaces-and-interface-implementations) Windows SDK.

- **Arabirimi Uygula**

  Arabirim oluşturulduğu tür kitaplığının konumu belirtir.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Project**|Tür kitaplığı projesi bir parçasıdır.|
  |**Kayıt defteri**|Tür kitaplığını sistemde kayıtlı. Kayıtlı bir tür kitaplığı içinde listelenen **kullanılabilir tür kitaplıklarını**.|
  |**Dosya**|Tür kitaplığını mutlaka sistemde kayıtlı değil ancak bir dosyasında tutulur. Dosya konumunda sağlamak **konumu**.|

- **Kullanılabilir tür kitaplıkları**

  Uygulayabileceğiniz arabirimi tanımları bulunduran kullanılabilir tür kitaplıklarını görüntüler. Seçerseniz **dosya** altında **uygulama arabiriminden**, bu kutusuna değişiklik için kullanılamıyor.

- **Konum**

  Şu anda seçilen tür kitaplığının konumu görüntüler **kullanılabilir tür kitaplıklarını** listesi. Seçtiyseniz **dosya** altında **uygulama arabiriminden**, kullanılacak tür kitaplığını kullanımda tutan bir dosyayı bulmak için üç nokta düğmesini seçin.

- **Arabirimler**

  Görüntüler, tanımları, tür kitaplığındaki şu anda seçili tutulur arabirimleri **kullanılabilir tür kitaplıklarını** kutusu.

  > [!NOTE]
  > Bu seçilen nesne tarafından zaten uygulanmış olarak görüntülenmez, aynı ada sahip arabirimler **arabirimleri** kutusu.

  |Aktarım düğmesi|Açıklama|
  |---------------------|-----------------|
  |**>**|Ekler **arabirimleri uygulayan** geçerli seçili arabirim adı listesi **arabirimleri** listesi.|
  |**>>**|Ekler **arabirimleri uygulayan** bulunan tüm arabirimi adlarını listelemek **arabirimleri** listesi.|
  |**\<**|Şu anda seçili arabirim adını kaldırır **arabirimleri uygulayan** listesi.|
  |**\<\<**|Şu anda listelenen adları tüm arabirim kaldırır **arabirimleri uygulayan** listesi.|

- **Arabirimi uygulayan**

  Nesneniz üzerinde uygulamak için seçtiğiniz arabirimleri adlarını görüntüler.

  > [!NOTE]
  > Öğesinden türetilen birden fazla arabirim içerip içermediğini `IDispatch`, veya sınıfınıza üzerinde zaten başka bir arabirimden türetilmiş bir arabirim uygulamak deneyin ardından COM_MAP girişlerin ayırt etmek gerekir. Daha fazla bilgi için [COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2).
