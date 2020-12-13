---
description: 'Daha fazla bilgi edinin: ATL projelerinde COM+ 1,0 desteği'
title: ATL projelerinde COM+ 1,0 desteği
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.MTS
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
ms.openlocfilehash: 8e196bccf25667da28532248765e47906fdcee97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141290"
---
# <a name="com-10-support-in-atl-projects"></a>ATL projelerinde COM+ 1,0 desteği

[Atl Proje Sihirbazı 'nı](../../atl/reference/creating-an-atl-project.md) kullanarak, com+ 1,0 bileşenleri için temel desteğe sahip bir proje oluşturabilirsiniz.

COM+ 1,0, dağıtılmış bileşen tabanlı uygulamalar geliştirmek için tasarlanmıştır. Ayrıca, bu uygulamaları dağıtmak ve yönetmek için çalışma zamanı altyapısı sağlar.

**Destek COM+ 1,0** onay kutusunu seçerseniz, sihirbaz bağlantı adımında derleme betiğini değiştirir. Özellikle, COM+ 1,0 projesi aşağıdaki kitaplıklara bağlantı sağlar:

- comsvcs. lib

- Mtxguid. lib

**Destek COM+ 1,0** onay kutusunu işaretlerseniz, **bileşen kayıt kaydedicisinde** da seçim yapabilirsiniz. Bileşen kaydedici, COM+ 1,0 nesnenizin bileşenlerin bir listesini almasını, bileşenleri kaydetmenizi veya bileşenlerin kaydını silmeyi (tek tek veya hepsi bir kerede) sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[ATL ve C Run-Time kodla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Varsayılan ATL Proje yapılandırması](../../atl/reference/default-atl-project-configurations.md)
