---
title: DCOMCNFG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DCOMCNFG
dev_langs: C++
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bffed7658232d11dd7741900d6eca14de341e855
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dcomcnfg"></a>DCOMCNFG
**DCOMCNFG** kayıt defterinde çeşitli DCOM özel ayarları yapılandırmanıza olanak sağlayan bir Windows NT 4.0 yardımcı programıdır. **DCOMCNFG** penceresinin üç sayfa vardır: varsayılan güvenlik, varsayılan özellikler ve uygulamalar. Windows 2000 altında dördüncü sayfasında, varsayılan protokolleri mevcuttur.  
  
## <a name="default-security-page"></a>Varsayılan güvenlik sayfası  
 Nesneler için varsayılan izinler sistemde belirtmek için varsayılan güvenlik sayfasını kullanabilirsiniz. Varsayılan güvenlik sayfasında üç bölüm bulunur: erişim, başlatma ve yapılandırma. Karşılık gelen bir bölümün varsayılanları değiştirmek için tıklatın **Varsayılanı Düzenle** düğmesi. Bu varsayılan güvenlik ayarları altında kayıt defterine depolanır `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`.  
  
## <a name="default-protocols-page"></a>Varsayılan protokolleri sayfası  
 Bu sayfada bu makinede kullanılabilir DCOM ağ protokolleri kümesi listelenir. Sırayı kullanılabilmeleri öncelik yansıtan; Listedeki ilk en yüksek önceliğe sahiptir. Protokolleri eklenemez veya bu sayfadan silinmiş.  
  
## <a name="default-properties-page"></a>Varsayılan Özellikler sayfası  
 Varsayılan Özellikler sayfasında, seçmelisiniz **bu bilgisayar üzerinde dağıtılmış COM'u etkinleştir** erişim COM nesneleri bu makinede çalışan diğer makinelere istemcilerde isterseniz onay kutusunu. Bu seçenek ayarlar seçme `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` değeri `Y`.  
  
## <a name="applications-page"></a>Uygulamalar sayfası  
 Uygulamalar sayfası belirli bir nesneyle ayarlarını değiştirin. Sadece listeden uygulamayı seçin ve tıklatın **özellikleri** düğmesi. Özellikler penceresini beş sayfası vardır:  
  
-   Genel sayfası çalıştığınız uygulama onaylar.  
  
-   Konumu sayfasında bir istemci çağırdığında uygulama çalıştırdığı belirtmenize olanak tanır `CoCreateInstance` ilgili CLSID üzerinde. Seçerseniz **uygulamayı aşağıdaki bilgisayarda Çalıştır** onay kutusunu işaretleyin ve bir bilgisayar adı girin sonra bir `RemoteServerName` değeri, bu uygulama için AppID altında eklenir. Temizleme **uygulama bu bilgisayarda çalışan** onay kutusunu yeniden adlandırır `LocalService` değeri `_LocalService` ve böylelikle, devre dışı bırakır.  
  
-   Güvenlik sayfası varsayılan sayfa bulunan güvenlik benzer **DCOMCNFG** penceresinde dışında bu ayarlar yalnızca geçerli uygulama için geçerlidir. Yeniden ayarları, bu nesne için AppID altında depolanır.  
  
-   Hangi kullanıcı uygulamayı çalıştırmak için kullanılan tanımla sayfası tanımlar.  
  
-   Uç noktalar sayfasında protokolleri ve uç noktaları seçilen DCOM sunucusunun istemcileri tarafından kullanılabilir kümesini listeler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri](../atl/atl-services.md)

