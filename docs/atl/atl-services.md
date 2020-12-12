---
description: 'Daha fazla bilgi edinin: ATL Hizmetleri'
title: ATL Hizmetleri
ms.date: 11/04/2016
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
ms.openlocfilehash: 1cb1f526434cefe57dc4675d592f836e04a6cdb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148609"
---
# <a name="atl-services"></a>ATL Hizmetleri

ATL COM nesneniz bir hizmette çalışacak şekilde oluşturmak için, ATL Proje Sihirbazı 'ndaki sunucu seçenekleri listesinden hizmet (EXE) seçeneğini belirlemeniz yeterlidir. Sihirbaz daha sonra hizmeti uygulamak için öğesinden türetilmiş bir sınıf oluşturur `CAtlServiceModuleT` .

ATL COM nesnesi bir hizmet olarak yapılandırıldığında, yalnızca yerel bir sunucu olarak kaydedilir ve Denetim Masası 'ndaki Hizmetler listesinde görünmez. Bunun nedeni, hizmetin bir hizmet olarak bir yerel sunucu olarak hata ayıklamanın daha kolay olması olabilir. Hizmet olarak yüklemek için komut isteminde aşağıdaki komutu çalıştırın:

`YourEXE` `.exe /Service`

Kaldırmak için aşağıdakileri çalıştırın:

`YourEXE` `.exe /UnregServer`

Bu bölümdeki ilk dört konu, üye işlevlerinin yürütülmesi sırasında oluşan eylemleri tartışır `CAtlServiceModuleT` . Bu konular, işlevlerin genellikle çağrılmasıyla aynı sırada görüntülenir. Bu konuların anlaşılmasından yararlanarak, ATL Proje Sihirbazı tarafından oluşturulan kaynak kodu başvuru olarak kullanmak iyi bir fikirdir. Bu ilk dört konu şunlardır:

- [CAtlServiceModuleT:: Start Işlevi](../atl/reference/catlservicemodulet-class.md#start)

- [CAtlServiceModuleT:: ServiceMain Işlevi](../atl/reference/catlservicemodulet-class.md#servicemain)

- [CAtlServiceModuleT:: Run Işlevi](../atl/reference/catlservicemodulet-class.md#run)

- [CAtlServiceModuleT:: Handler Işlevi](../atl/reference/catlservicemodulet-class.md#handler)

Son üç konuda bir hizmet geliştirmeyle ilgili kavramlar ele alınmaktadır:

- ATL Hizmetleri için [kayıt defteri girişleri](../atl/registry-entries.md)

- [DCOMCNFG](../atl/dcomcnfg.md)

- ATL Hizmetleri için [hata ayıklama ipuçları](../atl/debugging-tips.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)
