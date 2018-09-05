---
title: DCOMCNFG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- DCOMCNFG
dev_langs:
- C++
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46a395759322651aee75541ff0b121b608b9e74d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765284"
---
# <a name="dcomcnfg"></a>DCOMCNFG

DCOMCNFG kayıt defterinde çeşitli DCOM özel ayarları yapılandırmanıza olanak veren bir Windows NT 4.0 aracıdır. DCOMCNFG penceresi üç sayfası vardır: varsayılan güvenlik, varsayılan özellikler ve uygulamalar. Dördüncü sayfasında, protokolleri, varsayılan Windows 2000 altında mevcuttur.

## <a name="default-security-page"></a>Varsayılan güvenlik sayfası

Varsayılan güvenlik sayfası, sistemde nesneler için varsayılan izinleri belirtmek için kullanabilirsiniz. Varsayılan güvenlik sayfada üç bölüm yer alır: erişim, başlatma ve yapılandırma. Buna karşılık gelen bir bölümün varsayılanları değiştirmek için tıklayın **Düzenle varsayılan** düğmesi. Bu varsayılan güvenlik ayarları altındaki kayıt defterine depolanır `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`.

## <a name="default-protocols-page"></a>Varsayılan protokolleri sayfası

Bu sayfada, bu makinede DCOM kullanılabilir ağ protokolleri kümesi listelenir. Sırayı kullanılabilmeleri öncelikli yansıtır; Listedeki ilk en yüksek önceliğe sahip. Protokolleri eklenebilir veya bu sayfadan silindi.

## <a name="default-properties-page"></a>Varsayılan Özellikler sayfası

Varsayılan Özellikler sayfasında seçmelisiniz **bu bilgisayar üzerinde dağıtılmış COM'u etkinleştir** erişim COM nesneleri bu makinede çalışan diğer makinelere istemcilerde istiyorsanız kutuyu. Bu seçeneği ayarlar seçerek `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` değerini `Y`.

## <a name="applications-page"></a>Uygulamalar sayfası

Uygulama sayfasını ile belirli bir nesnesi için ayarları değiştirin. Yalnızca uygulamayı listeden seçin ve tıklayın **özellikleri** düğmesi. Özellikler penceresinde beş sayfası vardır:

- Genel sayfası çalıştığınız uygulama onaylar.

- Burada bir istemci çağırdığında, uygulamanın çalışması gerektiğini belirtmek konum sayfası verir `CoCreateInstance` ilgili CLSID üzerinde. Seçerseniz **aşağıdaki bilgisayarda uygulamayı çalıştırın** onay kutusunu işaretleyin ve bir bilgisayar adı girin. bir `RemoteServerName` değer, bu uygulamanın AppID altında eklenir. Temizleme **uygulamayı bu bilgisayarda Çalıştır** onay kutusunu yeniden adlandırma `LocalService` değerini `_LocalService` ve böylece, devre dışı bırakır.

- Bu ayarlar yalnızca geçerli uygulama için güvenlik sayfası DCOMCNFG penceredeki varsayılan güvenlik sayfasına benzer olmasıdır. Yeniden ayarları, bu nesne için AppID altında depolanır.

- Hangi kullanıcı uygulamayı çalıştırmak için kullanılan tanımla sayfası tanımlar.

- Uç noktaları sayfası protokolleri ve seçili DCOM sunucusunun istemciler tarafından kullanılabilir uç noktaları kümesini listeler.

## <a name="see-also"></a>Ayrıca Bkz.

[Hizmetler](../atl/atl-services.md)

