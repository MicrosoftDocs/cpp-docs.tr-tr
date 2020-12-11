---
description: 'Daha fazla bilgi edinin: uygulama ayarları, ATL Proje Sihirbazı'
title: Uygulama Ayarları, ATL Proje Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.atl.com.appset
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
ms.openlocfilehash: 7805fcb8760035ac232a36a42a1cf34273ee42a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158952"
---
# <a name="application-settings-atl-project-wizard"></a>Uygulama Ayarları, ATL Proje Sihirbazı

Yeni bir ATL projesine temel özellikler tasarlamak ve eklemek için ATL Proje Sihirbazı 'nın **uygulama ayarları** sayfasını kullanın.

## <a name="server-type"></a>Sunucu türü

Üç sunucu türünden birini seçin:

- **Dinamik bağlantı kitaplığı (DLL)**

   İşlem içi sunucu oluşturmayı seçin.

- **Yürütülebilir (EXE)**

   Yerel bir işlem dışı sunucu oluşturmak için seçin. Bu seçenek MFC veya COM+ 1,0 desteğine izin vermez. Proxy/saplama kodunun birleştirilmesine izin vermez.

- **Hizmet (EXE)**

   Windows başladığında arka planda çalışan bir Windows uygulaması oluşturmak için seçin. Bu seçenek, MFC veya COM+ 1,0 için desteğe izin vermez veya proxy/saplama kodunun birleştirilmesine izin vermez.

## <a name="additional-options"></a>Ek seçenekler

> [!NOTE]
> Tüm ek seçenekler yalnızca DLL projeleri için kullanılabilir.

- **Proxy/saplama kodunun birleştirilmesine izin ver**

   Oluşturma arabirimleri gerektiğinde kolaylık sağlamak için **proxy/saplama kodunu birleştirmeye Izin ver** onay kutusunu seçin. Bu seçenek, MıDL tarafından oluşturulan proxy ve saplama kodunu sunucusuyla aynı yürütülebilir dosyaya koyar.

- **MFC 'yi destekleme**

   Nesnenizin MFC desteği içerdiğini belirtmek için seçin. Bu seçenek projenizi MFC kitaplıklarına bağlar, böylece içerdikleri sınıfların ve işlevlerin hiçbirine erişebilirsiniz.

- **Destek COM+ 1,0**

   Proje derleme ayarlarını COM+ 1,0 bileşenlerini destekleyecek şekilde değiştirmek için seçin. Sihirbaz standart kitaplık listesine ek olarak, COM+ 1,0 bileşenine özel kitaplığı (comsvcs. lib) ekler

   Ayrıca, uygulamanız başlatıldığında mtxex.dll ana bilgisayar sistemine yüklenir.

- **Bileşen kaydedici desteği**

   ATL projeniz COM+ 1,0 bileşenleri için destek içeriyorsa, bu seçeneği belirleyebilirsiniz. Bileşen kaydedici, COM+ 1,0 nesnenizin bileşenlerin bir listesini almasını, bileşenleri kaydetmenizi veya bileşenlerin kaydını silmeyi (tek tek veya hepsi bir kerede) sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)<br/>
[Varsayılan ATL Proje yapılandırması](../../atl/reference/default-atl-project-configurations.md)
