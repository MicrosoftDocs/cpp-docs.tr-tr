---
title: ATL Hizmetleri
ms.date: 11/04/2016
f1_keywords:
- CServiceModule
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
ms.openlocfilehash: 50a3eecf210cacc35cd80ad82da079b18c998c8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456114"
---
# <a name="atl-services"></a>ATL Hizmetleri

Böylece bir hizmet olarak çalışır, ATL COM nesnesi oluşturmak için hizmet (EXE) ATL projesi Sihirbazı'nda sunucu seçeneklerini listeden seçmeniz yeterlidir. Sihirbaz, ardından türetilen bir sınıf oluşturacak `CAtlServiceModuleT` hizmeti uygulamak için.

ATL COM nesnesi bir hizmet olarak yapılandırıldığında, yalnızca yerel sunucu olarak kayıtlı ve Denetim Masası'ndaki Hizmetler listesinde görünmez. Hizmet olarak yerel bir sunucuya olarak hizmeti hata ayıklaması daha kolay olmasıdır. Hizmet olarak yüklemek için komut isteminde aşağıdaki komutu çalıştırın:

`YourEXE``.exe /Service`

Kaldırmak için aşağıdaki komutu çalıştırın:

`YourEXE``.exe /UnregServer`

Bu bölümdeki ilk dört konular ele yürütülmesi sırasında oluşan eylemleri `CAtlServiceModuleT` üye işlevleri. Bu konular işlevler genellikle çağrılır aynı sırada görünür. Bu konular Anlayışınızı geliştirmek için bir başvuru olarak ATL projesi Sihirbazı tarafından oluşturulan kaynak kodu kullanmak için bir fikirdir. Bu ilk dört konular şunlardır:

- [CAtlServiceModuleT::Start işlevi](../atl/reference/catlservicemodulet-class.md#start)

- [CAtlServiceModuleT::ServiceMain işlevi](../atl/reference/catlservicemodulet-class.md#servicemain)

- [CAtlServiceModuleT::Run işlevi](../atl/reference/catlservicemodulet-class.md#run)

- [CAtlServiceModuleT::Handler işlevi](../atl/reference/catlservicemodulet-class.md#handler)

Hizmet geliştirme ile ilgili kavramları son üç konular açıklanmaktadır:

- [Kayıt defteri girdilerini](../atl/registry-entries.md) ATL Hizmetleri

- [DCOMCNFG](../atl/dcomcnfg.md)

- [Hata ayıklama ipuçları](../atl/debugging-tips.md) ATL Hizmetleri

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)

