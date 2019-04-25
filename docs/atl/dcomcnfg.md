---
title: DCOMCNFG
ms.date: 11/04/2016
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
ms.openlocfilehash: a389a46cd02b40cef46d687743fd3416cc4f3154
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250790"
---
# <a name="dcomcnfg"></a>DCOMCNFG

DCOMCNFG kayıt defterinde çeşitli DCOM özel ayarları yapılandırmanıza olanak veren bir Windows NT 4.0 aracıdır. DCOMCNFG penceresi üç sayfası vardır: Varsayılan güvenlik, varsayılan özellikleri ve uygulamaları. Dördüncü sayfasında, protokolleri, varsayılan Windows 2000 altında mevcuttur.

## <a name="default-security-page"></a>Varsayılan güvenlik sayfası

Varsayılan güvenlik sayfası, sistemde nesneler için varsayılan izinleri belirtmek için kullanabilirsiniz. Varsayılan güvenlik sayfada üç bölüm yer alır: Erişim, başlatma ve yapılandırma. Buna karşılık gelen bir bölümün varsayılanları değiştirmek için tıklayın **Düzenle varsayılan** düğmesi. Bu varsayılan güvenlik ayarları altındaki kayıt defterine depolanır `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`.

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

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)
