---
description: 'Daha fazla bilgi edinin: DCOMCNFG'
title: DCOMCNFG
ms.date: 11/04/2016
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
ms.openlocfilehash: d99b0018d63cedbccaf57ec4cadeb649f390dcf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153167"
---
# <a name="dcomcnfg"></a>DCOMCNFG

DCOMCNFG, kayıt defterinde DCOM 'a özgü çeşitli ayarları yapılandırmanıza olanak tanıyan bir Windows NT 4,0 yardımcı programıdır. DCOMCNFG penceresinin üç sayfası vardır: varsayılan güvenlik, varsayılan özellikler ve uygulamalar. Windows 2000 ' nin altında, varsayılan protokoller olan dördüncü bir sayfa vardır.

## <a name="default-security-page"></a>Varsayılan güvenlik sayfası

Sistemdeki nesnelere yönelik varsayılan izinleri belirtmek için varsayılan güvenlik sayfasını kullanabilirsiniz. Varsayılan güvenlik sayfasında üç bölüm vardır: erişim, başlatma ve yapılandırma. Bir bölümün varsayılan değerlerini değiştirmek için, karşılık gelen **Varsayılanı Düzenle** düğmesine tıklayın. Bu varsayılan güvenlik ayarları, altında kayıt defterinde saklanır `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE` .

## <a name="default-protocols-page"></a>Varsayılan protokoller sayfası

Bu sayfada, bu makinede DCOM için kullanılabilen ağ protokolleri kümesi listelenir. Sıra, kullanılacağı önceliği yansıtır; Listedeki ilk, en yüksek önceliğe sahiptir. Bu sayfadan protokoller eklenebilir veya silinebilir.

## <a name="default-properties-page"></a>Varsayılan Özellikler sayfası

Diğer makinelerdeki istemcilerin bu makinede çalışan COM nesnelerine erişmesini istiyorsanız Varsayılan Özellikler sayfasında **Bu bilgisayarda Dağıtılmış com 'U etkinleştir** onay kutusunu seçmeniz gerekir. Bu seçeneğin belirlenmesi `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` değerini olarak ayarlar `Y` .

## <a name="applications-page"></a>Uygulamalar sayfası

Uygulamalar sayfasını kullanarak belirli bir nesnenin ayarlarını değiştirirsiniz. Listeden uygulamayı seçmeniz yeterlidir ve **Özellikler** düğmesine tıklayın. Özellikler penceresi beş sayfa içerir:

- Genel sayfası, üzerinde çalıştığınız uygulamayı onaylar.

- Konum sayfası, bir istemci ilgili CLSID üzerinde çağrı yapıldığında Uygulamanın çalıştırılacağı yeri belirtmenize olanak tanır `CoCreateInstance` . **Uygulamayı şu bilgisayarda çalıştır** onay kutusunu işaretleyin ve bir bilgisayar adı girerseniz, `RemoteServerName` Bu uygulama için AppID altına bir değer eklenir. **Bu bilgisayarda uygulamayı çalıştır** onay kutusu temizlendiğinde değeri yeniden adlandırır `LocalService` ve bu `_LocalService` nedenle devre dışı bırakır.

- Güvenlik sayfası, bu ayarların yalnızca geçerli uygulama için geçerli olması dışında, DCOMCNFG penceresinde bulunan varsayılan güvenlik sayfasına benzerdir. Yine, ayarlar bu nesnenin AppID altında depolanır.

- Tanımla sayfası, uygulamayı çalıştırmak için hangi kullanıcının kullanıldığını tanımlar.

- Uç noktalar sayfası, seçilen DCOM sunucusunun istemcileri tarafından kullanılabilen protokoller ve uç noktalar kümesini listeler.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)
