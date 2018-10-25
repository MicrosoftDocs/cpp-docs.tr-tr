---
title: Uygulama ayarları, ATL Proje Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.atl.com.appset
dev_langs:
- C++
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 127e5187f2e6511279633ffe9b5e26b24014f6b2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070653"
---
# <a name="application-settings-atl-project-wizard"></a>Uygulama ayarları, ATL Proje Sihirbazı

Kullanım **uygulama ayarları** tasarlamak ve temel özellikleri yeni bir ATL projesine eklemek için ATL projesi sihirbazı sayfası.

## <a name="server-type"></a>Sunucu türü

Üç sunucu türlerinden birini seçin:

- **Dinamik bağlantı kitaplığı (DLL)**

   İşlem sunucusu oluşturmak için bu seçeneği seçin.

- **Yürütülebilir (EXE)**

   Yerel bir işlem dışı sunucu oluşturmak için bu seçeneği seçin. Bu seçenek, MFC veya COM + 1.0 desteği izin vermez. İçin proxy/saplama kodunun birleştirilmesine izin vermez.

- **Hizmet (EXE)**

   Windows başladığında arka planda çalışan bir Windows uygulaması oluşturmak için bu seçeneği seçin. Bu seçenek, MFC veya COM + 1.0 desteği izin vermiyor veya için proxy/saplama kodunun birleştirilmesine izin vermiyor.

## <a name="additional-options"></a>Ek Seçenekler

> [!NOTE]
> Tüm ek seçenekler, yalnızca DLL projeleri için kullanılabilir.

- **Proxy/saplama kodunun birleştirilmesine izin ver**

   Seçin **proxy/saplama kodunun birleştirilmesine izin** arabirimleri sıralama gerekli olduğunda bir kolaylık olarak onay kutusu. Bu seçenek MIDL tarafından oluşturulan proxy ve saplama kodu aynı yürütülebilir sunucusu olarak yerleştirir.

- **MFC desteği**

   Nesneniz için MFC desteği içerdiğini belirtmek için bu seçeneği seçin. Tüm sınıfları ve bunların içerdiği işlevleri erişebilmeleri bu seçenek için MFC kitaplıklarını projenize bağlar.

- **COM + 1.0 desteği**

   COM + 1.0 bileşenleri desteklemek için proje oluşturma ayarlarını değiştirmek için bu seçeneği seçin. Standart kitaplıkları listesine ek olarak sihirbaz COM + 1.0 bileşeni özgü kitaplığı comsvcs.lib ekler.

   Ayrıca, mtxex.dll, uygulamanız başlatıldığında konak sisteminde yüklü gecikmesidir.

- **Destek bileşen Kaydedicisi**

   ATL projenizin COM + 1.0 bileşenleri için destek içeriyorsa, bu seçeneği ayarlayabilirsiniz. Bileşen kayıt şirketi, COM + 1.0 nesnesinin bileşenlerin listesini alın, bileşenleri kaydetmek veya bileşenleri (tek tek veya tek seferde) kaydını sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL Projesi Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)<br/>
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)

